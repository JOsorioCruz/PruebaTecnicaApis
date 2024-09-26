# Casos de Prueba: Sistema de Gestión de Biblioteca

## Historias de Usuario 
1. `Registro de Usuario:` Como estudiante, quiero poder registrarme en la biblioteca para acceder a los servicios en línea y reservar libros.
2. `Inicio de sesión:` Como usuario registrado, quiero poder iniciar sesión en la biblioteca con mi usuario y contraseña.
3. `Recuperación de contraseña:` Como usuario, quiero poder restablecer mi contraseña en caso de olvido.
4. `Búsqueda de libros:` Como estudiante, quiero poder buscar libros por diferentes criterios (título, autor, categoría) para encontrar los libros que necesito.
5. `Reserva de libros:` Como estudiante, quiero poder reservar libros disponibles.
6. `Administración del perfil de usuario:` Como usuario, quiero poder administrar mi perfil y cambiar mi contraseña.
7. `Visualización del historial de préstamos:` Como usuario, quiero poder ver el historial de mis préstamos.
8. `Restricciones adicionales:` Como usuario, quiero ser informado sobre las restricciones, como horarios de reservas y acceso a funciones.

### CP001: Registro de usuario exitoso
Pasos:

1. Acceder al formulario de registro en línea
2. Ingresar nombre completo: "Jairo Osorio"
3. Ingresar número de identificación estudiantil: "1073888001"
4. Ingresar correo electrónico institucional: "jairoosorio@unicartagena.edu"
5. Ingresar contraseña: "Biblioteca2024!"
6. Confirmar contraseña: "Biblioteca2024!"
7. Enviar el formulario de registro

`Resultado esperado:` Se crea la cuenta en el sistema y se recibe un correo electrónico de confirmación.

### CP002: Registro de usuario con correo no institucional
Pasos:

1. Acceder al formulario de registro en línea
2. Ingresar nombre completo: "anna andrade"
3. Ingresar número de identificación estudiantil: "1073888001"
4. Ingresar correo electrónico no institucional: "ana.andrade@gmail.com"
5. Ingresar contraseña: "Biblio2024!"
6. Confirmar contraseña: "Biblio2024!"
7. Enviar el formulario de registro

`Resultado esperado:` El sistema muestra un mensaje de error indicando que solo se permiten correos institucionales.

### CP003: Registro de usuario con contraseña débil
Pasos:

1. Acceder al formulario de registro en línea
2. Ingresar nombre completo: "Carlos Rodríguez"
3. Ingresar número de identificación estudiantil: "1083228181"
4. Ingresar correo electrónico institucional: "crodriguez@unicartagena.edu"
5. Ingresar contraseña: "password"
6. Confirmar contraseña: "password"
7. Enviar el formulario de registro

`Resultado esperado:` El sistema muestra un mensaje de error indicando que la contraseña no cumple con los requisitos mínimos de seguridad.

### CP004: Inicio de sesión exitoso
Pasos:

1. Acceder al formulario de inicio de sesión en línea
2. Ingresar correo electrónico: "jairoosorio@unicartagena.edu"
3. Ingresar contraseña: "Biblioteca2024!"
4. Presionar el botón de iniciar sesión

`Resultado esperado:` El usuario inicia sesión correctamente y accede a los servicios en línea de la biblioteca.

### CP005: Inicio de sesión fallido
Pasos:

1. Acceder al formulario de inicio de sesión en línea
2. Ingresar correo electrónico: "jairoosorio@unicartagena.edu"
3. Ingresar contraseña incorrecta: "ContraseñaIncorrecta123"
4. Presionar el botón de iniciar sesión

`Resultado esperado:` El sistema muestra un mensaje de error indicando que las credenciales son incorrectas.

### CP006: Recuperación de contraseña
Pasos:

1. Acceder al formulario de recuperación de contraseña
2. Ingresar correo electrónico registrado: "jairoosorio@unicartagena.edu"
3. Solicitar restablecimiento de contraseña
4. Recibir correo electrónico con enlace para restablecer contraseña
5. Seguir el enlace y establecer nueva contraseña: "NuevaBiblioteca2024!"

`Resultado esperado:` El usuario puede restablecer su contraseña y acceder a su cuenta con la nueva contraseña.

### CP007: Búsqueda de libros por título
Pasos:

1. Iniciar sesión en el sistema
2. Acceder a la función de búsqueda de libros
3. Seleccionar criterio de búsqueda: "Título"
4. Ingresar término de búsqueda: "It (Eso)"
5. Presionar el botón de búsqueda

`Resultado esperado:` Se muestran los libros que contienen "It (Eso)" en el título.

### CP008: Búsqueda de libros por autor
Pasos:

1. Iniciar sesión en el sistema
2. Acceder a la función de búsqueda de libros
3. Seleccionar criterio de búsqueda: "Autor"
4. Ingresar término de búsqueda: "Stephen King"
5. Presionar el botón de búsqueda

`Resultado esperado:` Se muestran los libros escritos por Stephen King.

### CP009: Búsqueda de libros por categoría
Pasos:

1. Iniciar sesión en el sistema
2. Acceder a la función de búsqueda de libros
3. Seleccionar criterio de búsqueda: "Categoría"
4. Ingresar término de búsqueda: "Terror/Horror"
5. Presionar el botón de búsqueda

`Resultado esperado:` Se muestran los libros categorizados como Terror/Horror.

### CP010: Intento de reserva de libros fuera de horario
Pasos:

1. Iniciar sesión en el sistema
2. Buscar un libro disponible
3. Intentar reservar el libro a las 7:00 p.m.

`Resultado esperado:` El sistema muestra un mensaje indicando que las reservas solo están disponibles de lunes a viernes de 8:00 a.m. a 5:00 p.m.

### CP011: Reserva de libro exitosa
Pasos:

1. Iniciar sesión en el sistema (usuario: "jairoosorio@unicartagena.edu", contraseña: "Biblioteca2024!")
2. Buscar un libro disponible (ej. "El The Shining" (El Resplandor)")
3. Seleccionar la opción de reservar el libro
4. Confirmar la reserva

`Resultado esperado:` El sistema confirma la reserva del libro y muestra un mensaje de éxito.

### CP012: Visualización y edición del perfil de usuario
Pasos:

1. Iniciar sesión en el sistema
2. Acceder a la sección "Mi perfil"
3. Verificar que se muestren correctamente los datos del usuario
4. Editar el número de teléfono: cambiarlo a "+5730095959"
5. Guardar los cambios

`Resultado esperado:` El sistema actualiza el perfil con el nuevo número de teléfono y muestra un mensaje de confirmación.

### CP013: Visualización del historial de préstamos
Pasos:

1. Iniciar sesión en el sistema
2. Acceder a la sección "Historial de préstamos"
3. Verificar que se muestre una lista de los libros prestados anteriormente

`Resultado esperado:` Se muestra una lista con los libros prestados, incluyendo fechas de préstamo y devolución.

### CP014: Cambio de contraseña desde el perfil de usuario
Pasos:

1. Iniciar sesión en el sistema
2. Acceder a la sección "Mi perfil"
3. Seleccionar la opción "Cambiar contraseña"
4. Ingresar la contraseña actual: "Biblioteca2024!"
5. Ingresar la nueva contraseña: "NuevaBiblioteca2025!"
6. Confirmar la nueva contraseña: "NuevaBiblioteca2025!"
7. Guardar los cambios

`Resultado esperado:` El sistema actualiza la contraseña y requiere que el usuario inicie sesión nuevamente con la nueva contraseña.

### CP015: Intento de acceso a funciones restringidas sin autenticación
Pasos:

1. Acceder a la página principal del sistema sin iniciar sesión
2. Intentar acceder directamente a la URL de reserva de libros

`Resultado esperado:` El sistema redirige al usuario a la página de inicio de sesión.

### CP016: Cancelación de reserva
Pasos:

1. Iniciar sesión en el sistema
2. Acceder a la sección "Mis reservas"
3. Seleccionar una reserva activa
4. Elegir la opción "Cancelar reserva"
5. Confirmar la cancelación

`Resultado esperado:` El sistema cancela la reserva y actualiza la lista de reservas del usuario.

### CP017: Búsqueda de libros con filtros múltiples
Pasos:

1. Iniciar sesión en el sistema
2. Acceder a la función de búsqueda avanzada
3. Seleccionar categoría: "Ciencia Ficción"
4. Seleccionar año de publicación: "Después de 2000"
5. Ingresar palabra clave: "espacio"
6. Realizar la búsqueda

`Resultado esperado:` El sistema muestra los libros de ciencia ficción publicados después del año 2000 que contienen la palabra "espacio" en su título o descripción.

### CP018: Renovación de préstamo
Pasos:

1. Iniciar sesión en el sistema
2. Acceder a la sección "Mis préstamos actuales"
3. Seleccionar un libro prestado que sea elegible para renovación
4. Elegir la opción "Renovar préstamo"
5. Confirmar la renovación

`Resultado esperado:` El sistema extiende la fecha de devolución del libro y muestra la nueva fecha.

## Trazabilidad de prueba:

````
    HU001 (Registro de usuario):
        CP001: Registro de usuario exitoso.
        CP002: Registro de usuario con correo no institucional.
        CP003: Registro de usuario con contraseña débil.

    HU002 (Inicio de sesión):
        CP004: Inicio de sesión exitoso.
        CP005: Inicio de sesión fallido.

    HU003 (Recuperación de contraseña):
        CP006: Recuperación de contraseña.

    HU004 (Búsqueda de libros):
        CP007: Búsqueda de libros por título.
        CP008: Búsqueda de libros por autor.
        CP009: Búsqueda de libros por categoría.
        CP017: Búsqueda de libros con filtros múltiples.

    HU005 (Reserva de libros):
        CP011: Reserva de libro exitosa.
        CP010: Intento de reserva de libros fuera de horario.
        CP016: Cancelación de reserva.
        CP017: Búsqueda de libros con filtros múltiples.
        CP018: Renovación de préstamo.

    HU006 (Administración del perfil de usuario):
        CP012: Visualización y edición del perfil de usuario.
        CP014: Cambio de contraseña desde el perfil de usuario.

    HU007 (Visualización del historial de préstamos):
        CP013: Visualización del historial de préstamos.

    HU008 (Renovación de préstamos):
        CP018: Renovación de préstamo.

    Restricciones adicionales:
        CP010: Horario de reserva de libros.
        CP015: Acceso restringido para usuarios no autenticados.
````

## Cobertura de prueba:

Se tuvo cobertura en las siguientes áreas del sistema:

1. Registro y autenticación de usuarios.
2. Búsqueda de libros, incluyendo límites y filtros múltiples.
3. Reserva de libros, incluyendo cancelaciones y renovaciones.
4. Administración del perfil de usuario.
5. Visualización del historial de préstamos.
6. Cambios de contraseña.
7. Acceso restringido para usuarios no autenticados.
