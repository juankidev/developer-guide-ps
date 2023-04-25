
# Redirección de ID

Muchas veces el cliente requiere asignar una solicitud anteriormente creada en provisión de servicios a otro usuario. Para resolverlo, debemos seguir los siguientes pasos:

### Pasos a seguir:

1. Buscar la solicitud en PS.Solicitud (Utilizaremos un ID de ejemplo, por favor reemplazar los valores según el caso)

```bash
  SELECT * FROM PS.Solicitud WHERE SolicitudId = 00031
```

2. Buscar el usuario al cual se requiere redireccionar la solicitud en PS.Usuario y copiar su ID

```bash
  SELECT * FROM PS.Usuario WHERE UserName = 'example@ises.com.co'
```

3. Ejecutar la sentencia UPDATE para cambiar el campo "UsuarioId" en el registro correspondiente en PS.Solicitud.

```bash
  UPDATE PS.Solicitud SET UsuarioId = 0000 WHERE SolicitudId = 00031
```

Después de seguir estos pasos se debe validar que la solicitud fue redireccionada correctamente entrando a provisión de servicios con las credenciales del usuario en cuestión y revisar su bandeja de solicitudes llendo al menú "Mis Solicitudes"

