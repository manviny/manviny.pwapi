## Enviar email
```js
$http.post( '/knamax/pwapi/', { do: 'sendEmail', data:{
	'from': 'manol@indinet.es', 
	'to': $scope.email, 
	'subject': $scope.nombre, 
	'message': $scope.message
}})
.success( function (result) {  console.log("registrado", result); })
.error(function(data){ console.log("NO registrado", data) }); 
```

## Registrar usuario
```js
$http.post( '/knamax/pwapi/', { do: 'registerUser', data:{
	'name': 'manol2', 
	'email': 'manol2@indinet.es', 
	'email2': '', 
	'password': 'kakita33L', 
	'password2': 'kakita33L' 
}})
.success( function (result) {  console.log("registrado", result); })
.error(function(data){ console.log("NO registrado", data) }); 
```