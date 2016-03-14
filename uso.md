# Ejemplo avanzado para recibir un formulario de contacto por email

## 1.- Recibir formularios por email
### Creamos un formulario parecido al siguiente (html)
Este debe contener:   
1.- ng-model="email"   
2.- ng-model="subject"   
3.- ng-model="message"   
```html
<!-- CONTACTO -->
<div class="col-md-6 col-sm-12">
    <div class="contact-form bottom">
        <h2>Contactar</h2>
        <form id="main-contact-form" name="contact-form">
            <div class="form-group">
                <input type="email" name="email" class="form-control" ng-model="email" required="required" placeholder="Email">
            </div>
            <div class="form-group">
                <input type="text" name="name" class="form-control" ng-model="subject" required="required" placeholder="asunto">
            </div>
            <div class="form-group">
                <textarea name="message" id="message" required="required" ng-model="message" class="form-control" rows="8" placeholder="Mensaje"></textarea>
            </div>                        
            <div class="form-group">
                <input type="submit" name="submit" class="btn btn-submit" value="Enviar"  ng-click="enviarEmail()">
            </div>
        </form>
    </div>
</div>
<!-- CONTACTO. -->
```
### Para enviar el email debemos escribir un javascript adapatado a tu web parecido a este: 
Con esto conseguimos enviar el email
```js
app.controller('footerCtrl', function ($scope, $http) {

    $scope.enviarEmail = function(){
        $http.post( '/tuweb/pwapi/', { do: 'getEmail', data:{
            'from': $scope.email, 
            'subject': $scope.subject, 
            'message': $scope.message
        }})
        .success( function (result) {  console.log("email enviado", result); })
        .error(function(data){ console.log("NO enviado", data) });             
    }


});

```
## 2.- Borrar datos del formulario
Para borrar el formulario vamos a borrar los inputs del formulario, debemos dejar el código anterior como este
```js
app.controller('footerCtrl', function ($scope, $http) {

    $scope.enviarEmail = function(){
        $http.post( '/tuweb/pwapi/', { do: 'getEmail', data:{
            'from': $scope.email, 
            'subject': $scope.subject, 
            'message': $scope.message
        }})
        .success( function (result) {  
            console.log("email enviado", result); 
            $scope.email = '';
            $scope.subject = '';
            $scope.message = '';
        })
        .error(function(data){ console.log("NO enviado", data) });             
    }


});

```

## 3.- Avisar por pantalla que el formulario se ha recibido correctamente

```js
// 1.- Para instalar avisos flotantes, en este caso toastr
// 2.- Cargar el css y js necesarios

<link href='https://cdnjs.cloudflare.com/ajax/libs/toastr.js/latest/css/toastr.min.css' rel='stylesheet' type='text/css'>
<script src="https://cdnjs.cloudflare.com/ajax/libs/toastr.js/latest/js/toastr.min.js"></script>

// 3.- buscar esta linea de código "var app=angular.module", generalmente estará en el _init.php y añadir
var app=angular.module('myApp',['ngRoute','toastr'])




````

