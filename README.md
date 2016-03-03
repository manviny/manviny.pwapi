## Enviar email ( OPCIÓN 1 ),
```js
$http.post( '/tuweb/pwapi/', { do: 'sendEmail', data:{
	'to': $scope.email, 
	'subject': $scope.nombre, 
	'message': $scope.message
}})
.success( function (result) {  console.log("registrado", result); })
.error(function(data){ console.log("NO registrado", data) }); 
```

## Enviar email ( OPCIÓN 2 ), si queremos indicar que lo envia alguien diferente.
```js
$http.post( '/tuweb/pwapi/', { do: 'sendEmail', data:{
	'from': 'nombre@correo.com', 
	'to': $scope.email, 
	'subject': $scope.nombre, 
	'message': $scope.message
}})
.success( function (result) {  console.log("registrado", result); })
.error(function(data){ console.log("NO registrado", data) }); 
```

## Registrar usuario 
```js
$http.post( '/tuweb/pwapi/', { do: 'registerUser', data:{
	'name': 'manol2', 
	'email': 'usuario@correo.com', 
	'email2': '', 
	'password': 'password', 
	'password2': 'password' 
}})
.success( function (result) {  console.log("registrado", result); })
.error(function(data){ console.log("NO registrado", data) }); 
```
## Buscar páginas 
```js

$http.post( '/tuweb/pwapi/', { do: 'searchPages', data:{
    'query': 'title|body~=slide'
    // 'query': 'template=product, stock>0, (featured_from<=today, featured_to>=today), (highlighted=1)'
}})
.success( function (result) {  console.log("query result", result); })
.error(function(data){ console.log("NO registrado", data) }); 
```