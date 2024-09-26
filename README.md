# Prueba Técnica

Este proyecto es una prueba técnica que implementa validaciones utilizando Postman y generación de reportes con Newman. También se ejecutaron pruebas en la base de datos para verificar la correcta gestión de la información.

## Precondiciones

1. **Instalar Node.js**: https://nodejs.org/en/download/package-manager
2. **Instalar Newman**: https://support.postman.com/hc/en-us/articles/115003703325-How-to-install-Newman
3. **Contar con un IDE de desarrollo**: Para editar y ejecutar los scripts y archivos de configuración.

## Estructura del Proyecto

El proyecto está organizado en las siguientes carpetas:

- **Capa APIs**: Contiene los scripts de Postman en formato `.json` y datos aleatorios para las pruebas dinámicas de API.
- **Capa Base de Datos**: Incluye un archivo con las sentencias SQL para las pruebas en la base de datos.
````
├── CapaApis
│   ├── ColeccionRun.json
│   ├── dataRandom.json
├── CapaBaseDeDatos
│   ├── CapaBaseDeDatos.txt
├── node_modules
├── package.json
├── package-lock.json
├── README.md
````
---

## Carpeta Capa APIs

En esta carpeta se encuentran los archivos `.json` que contienen los scripts ejecutables de las colecciones de Postman. También incluye datos aleatorios para consumir de manera dinámica, con el objetivo de validar el comportamiento de las APIs.

### Validaciones Implementadas

#### **Método GET**:
Se validan los siguientes aspectos en la respuesta del backend:

- Los títulos y los cuerpos de las publicaciones estén presentes en la respuesta.
- Se debe desarrollar las pruebas en la sección de **Test** de Postman, para asegurarse que las categorías solicitadas estén correctamente incluidas en la respuesta de la API.

#### **Método POST**:
En este caso, se validan los siguientes puntos:

- Que los datos ingresados dinámicamente en el `body` de la solicitud, mediante un archivo `.json`, sean los mismos que la API responde.
- El ID generado en cada respuesta debe ser único para cada solicitud.

> **Nota**: Newman es utilizado para ejecutar las pruebas y generar un reporte HTML al finalizar la ejecución.
### Ejecutables APIs

Para generar el reporte, se debe ejecutar el siguiente script en el archivo `package.json`:

```json
"test-report": "newman run CapaApis/ColeccionRun.json -d dataRandom.json -r html --reporter-html-export Newman_Report.html"
```

### Ruta de la Colección de Postman

````
{Ruta_del_Archivo_Coleccion_Postman}
````

## Carpeta Capa Base de Datos

En esta carpeta se encuentra el archivo CapaBaseDeDatos.txt, que contiene las sentencias SQL necesarias para probar las funcionalidades relacionadas con la gestión de productos en una tienda en línea. Estas sentencias incluyen:
##### Funcionalidades Probadas

    - Inserción de productos: Se validó que los productos puedan ser añadidos correctamente a la base de datos.
    - Actualización de productos: Se verificó que los datos de los productos se puedan modificar adecuadamente.
    - Eliminación de productos: Se probó que los productos puedan ser eliminados correctamente.
    - Consultas JOIN: Se generaron informes que unen información de productos con otras tablas de la base de datos, como categorías o inventarios.

#  📫 Contacto
Para más información o consultas, puedes contactarme a través de mi correo electrónico: [osoriocruzjairo@gmail.com](mailto:osoriocruzjairo@gmail.com) o LinkedIn: [Jairo Osorio Cruz](https://www.linkedin.com/in/jairo-osorio-c-8461061b3/).

[![Email](https://img.shields.io/badge/-Email-D14836?style=flat&logo=gmail&logoColor=white)](mailto:osoriocruzjairo@gmail.com)
[![LinkedIn](https://img.shields.io/badge/-LinkedIn-0077B5?style=flat&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/jairo-osorio-c-8461061b3/)