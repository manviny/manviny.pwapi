## Enviar email (OPCION 1),
```js
$http.post( '/tuweb/pwapi/', { do: 'sendEmail', data:{
	'to': $scope.email, 
	'subject': $scope.nombre, 
	'message': $scope.message
}})
.success( function (result) {  console.log("registrado", result); })
.error(function(data){ console.log("NO registrado", data) }); 
```

## Enviar email (OPCION 2), si queremos indicar que lo envia alguien diferente.
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