# Documentación del Formato QR

Este documento describe la estructura de datos que se codifica en el código QR generado a partir del formulario de solicitud de pasaporte.

## Estructura del Arreglo

El código QR contiene un arreglo de cadenas de texto donde cada posición tiene un significado específico. A continuación se detalla cada posición del arreglo:

| Índice | Nombre del Campo | Tipo | Descripción |
|--------|------------------|------|-------------|
| 0 | tramite | String | Tipo de trámite seleccionado |
| 1 | consulado | String | Consulado seleccionado |
| 2 | fechaSolicitud | Date (YYYY-MM-DD) | Fecha de solicitud |
| 3 | numeroPasaporte | String | Número de pasaporte |
| 4 | carneIdentidad | String | Número de carné de identidad |
| 5 | primerApellido | String | Primer apellido del solicitante |
| 6 | segundoApellido | String | Segundo apellido del solicitante |
| 7 | primerNombre | String | Primer nombre del solicitante |
| 8 | segundoNombre | String | Segundo nombre del solicitante |
| 9 | fechaNacimiento | Date (YYYY-MM-DD) | Fecha de nacimiento |
| 10 | paisNacimiento | String | País de nacimiento |
| 11 | provinciaNacimiento | String | Provincia de nacimiento |
| 12 | municipioNacimiento | String | Municipio de nacimiento |
| 13 | sexo | String | Sexo (M/F) |
| 14 | estadoCivil | String | Estado civil |
| 15 | colorOjos | String | Color de ojos |
| 16 | colorPiel | String | Color de piel |
| 17 | colorCabello | String | Color de cabello |
| 18 | estatura | Number | Estatura en cm |
| 19 | nombrePadre | String | Nombre completo del padre |
| 20 | nombreMadre | String | Nombre completo de la madre |
| 21 | fechaSalidaCuba | Date (YYYY-MM-DD) | Fecha de salida de Cuba |
| 22 | direccionResidencia | String | Dirección de residencia actual |
| 23 | codigoPostalResidencia | String | Código postal de la residencia |
| 24 | provinciaEstadoResidencia | String | Provincia/Estado de residencia |
| 25 | paisResidenciaActual | String | País de residencia actual |
| 26 | telefonoResidencia | String | Teléfono de residencia |
| 27 | emailResidencia | String | Correo electrónico de residencia |
| 28 | faxResidencia | String | Fax de residencia |
| 29 | nombreCentroTrabajo | String | Nombre del centro de trabajo/estudio |
| 30 | nivelCultural | String | Nivel cultural |
| 31 | profesionTrabajo | String | Profesión |
| 32 | ocupacionTrabajo | String | Ocupación actual |
| 33 | direccionTrabajo | String | Dirección del trabajo |
| 34 | codigoPostalTrabajo | String | Código postal del trabajo |
| 35 | provinciaEstadoTrabajo | String | Provincia/Estado del trabajo |
| 36 | paisTrabajo | String | País del trabajo |
| 37 | telefonoTrabajo | String | Teléfono del trabajo |
| 38 | emailTrabajo | String | Correo electrónico del trabajo |
| 39 | faxTrabajo | String | Fax del trabajo |
| 40 | referenciaNombre | String | Nombre de la referencia en Cuba |
| 41 | tipoVinculo | String | Tipo de vínculo con la referencia |
| 42 | referenciaDireccion | String | Dirección de la referencia |
| 43 | referenciaProvincia | String | Provincia de la referencia |
| 44 | referenciaMunicipio | String | Municipio de la referencia |
| 45 | direccionCuba1 | String | Primera dirección en Cuba |
| 46 | desdeCuba1 | String | Fecha desde (primera dirección) |
| 47 | hastaCuba1 | String | Fecha hasta (primera dirección) |
| 48 | direccionCuba2 | String | Segunda dirección en Cuba |
| 49 | desdeCuba2 | String | Fecha desde (segunda dirección) |
| 50 | hastaCuba2 | String | Fecha hasta (segunda dirección) |
| 51 | foto | Base64 | Imagen de la foto en formato Base64 |
| 52 | firma | Base64 | Imagen de la firma en formato Base64 |
| 53 | huella | Base64 | Imagen de la huella en formato Base64 |

## Ejemplo del Arreglo QR

A continuación se muestra un ejemplo del arreglo que se generaría al escanear el código QR:

```javascript
[
  "renovacion",
  "consulado_habana",
  "2025-05-20",
  "C12345678",
  "85010112345",
  "Pérez",
  "González",
  "Juan",
  "Carlos",
  "1985-01-01",
  "Cuba",
  "La Habana",
  "Plaza de la Revolución",
  "M",
  "casado",
  "marrones",
  "blanco",
  "negro",
  "175",
  "José Pérez Martínez",
  "María González López",
  "2010-05-15",
  "Calle 42 #1234 e/ 12 y 14, Playa",
  "11300",
  "La Habana",
  "Cuba",
  "+5371234567",
  "juan.perez@email.com",
  "",
  "Empresa XYZ S.A.",
  "universitario",
  "Ingeniero Informático",
  "Desarrollador Senior",
  "Ave. 7ma #1234 e/ 1ra y 3ra, Miramar",
  "11300",
  "La Habana",
  "Cuba",
  "+5377654321",
  "juan.perez@empresa.com",
  "+5377654322",
  "Ana Martínez Rodríguez",
  "hermano",
  "Calle 100 #1234, Playa",
  "La Habana",
  "Playa",
  "Calle 10 #123, Vedado",
  "2005",
  "2010",
  "Calle 20 #456, Miramar",
  "2010",
  "2015",
  "data:image/jpeg;base64,/9j/4AAQSkZJRgABAQ...",
  "data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAA...",
  "data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAA..."
]
```

## Notas Importantes

1. Los campos de imágenes (foto, firma, huella) se codifican en formato Base64.
2. Las fechas siguen el formato ISO (YYYY-MM-DD).
3. Los campos opcionales que no se completen aparecerán como cadenas vacías ("").
4. Para los campos de selección múltiple, los valores se concatenan separados por comas.
5. Las direcciones en Cuba incluyen la dirección y los períodos de residencia.

## Validación de Datos

El sistema valida que los campos obligatorios estén completos antes de generar el código QR. Los campos obligatorios incluyen:
- Datos personales básicos (nombres, apellidos, fecha de nacimiento)
- Documentos de identidad
- Información de contacto
- Datos del trámite

## Consideraciones de Seguridad

- Los datos personales se codifican en el QR sin cifrado adicional.
- Se recomienda proteger el acceso a los códigos QR generados.
- No se deben incluir contraseñas o información sensible en el formulario.
