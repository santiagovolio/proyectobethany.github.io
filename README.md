# Proyecto Bethany · Sistema de salidas de fin de semana

Aplicación web para que las mamás residentes de **Proyecto Bethany** soliciten permiso para dormir fuera del hogar durante los fines de semana, y para que la administración revise, apruebe o rechace esas solicitudes y lleve un registro ordenado en Excel.

🔗 **Página:** https://santiagovolio.github.io/proyectobethany.github.io/

---

## Sobre Proyecto Bethany

Proyecto Bethany es un ministerio cristiano sin fines de lucro en Costa Rica que camina al lado de madres solteras y sus hijos. Les ofrece vivienda, acompañamiento integral y la oportunidad de cursar una carrera universitaria.

Como parte de la convivencia en el hogar, las residentes pueden pasar algunas noches fuera durante los fines de semana, con un número máximo de días por mes. Antes de este sistema, ese control no tenía un registro automatizado.

## Contexto: Trabajo Comunal Universitario (TCU)

Este sistema se desarrolló como parte del **Trabajo Comunal Universitario (TCU)** de **Santiago Volio Argüello**, estudiante del Bachillerato en Ingeniería en Ciencia de Datos de **LEAD University**, en el área de Tecnologías de Información de Proyecto Bethany, durante 2026.

El objetivo del proyecto fue darle a la ONG una herramienta gratuita, fácil de usar desde el celular y fácil de mantener, que reemplace el control manual de los permisos de salida.

## ¿Qué hace?

### Para las mamás
- Crear su cuenta con su perfil: cédula, datos de contacto, universidad, carrera, beca y datos de sus hijos e hijas.
- Ingresar con su **cédula o nombre de usuario**.
- Ver cuántos días de salida le quedan en el mes actual y en el siguiente.
- Enviar una solicitud con fecha y hora de salida y de regreso, más un comentario para la administración.
- Ver sus solicitudes pendientes, aprobadas y rechazadas, y cancelar las pendientes.
- Recibir **notificaciones** dentro de la app y, si lo desea, por correo.

### Para la administración
- Activar, desactivar o eliminar cuentas de mamás y asignar contraseñas temporales.
- Revisar las solicitudes pendientes y **aprobarlas o rechazarlas**, con una nota para la mamá.
- Consultar el registro de salidas por mes y ver quién está fuera hoy.
- Configurar el límite de días por mes y los días en que puede iniciar una salida.
- Descargar los libros de Excel con toda la información.

### Reglas que aplica automáticamente
- Cada noche fuera cuenta como un día. Una salida que cruza de un mes a otro se reparte entre ambos meses.
- Las solicitudes pendientes ya se descuentan de los días disponibles.
- No permite fechas que se crucen con otra salida ni salidas que inicien en días no permitidos.
- Vuelve a revisar el límite en el momento de aprobar.

## Registro en Excel

El sistema mantiene libros de Google Sheets que se actualizan solos y se pueden descargar como `.xlsx`:

| Libro | Contenido |
|---|---|
| **Solicitudes** | Hojas *Todas*, *Aprobadas*, *Rechazadas* y *Pendientes*, con colores por estado. |
| **Solicitudes aprobadas** | Registro de quiénes salen, con fechas, horas, comentario y quién aprobó. |
| **Residentes** | Hoja *Mamás* (perfil completo) y hoja *Hijos* (cédula, fecha de nacimiento, edad y género). |

## ¿Cómo está construido?

- **Aplicación:** Google Apps Script (servidor) con una interfaz en HTML, CSS y JavaScript.
- **Datos:** Google Sheets, dentro de la cuenta de Google de la organización.
- **Publicación:** esta página de GitHub Pages muestra la aplicación a pantalla completa.
- **Costo:** ninguno. No requiere servidores propios.

### Contenido de este repositorio

| Archivo | Para qué sirve |
|---|---|
| `index.html` | Página que carga la aplicación de Apps Script a pantalla completa. |
| `manifest.webmanifest` | Permite agregar la app a la pantalla de inicio del celular. |
| `apple-touch-icon.png`, `icon-192.png`, `icon-512.png`, `favicon-32.png` | Íconos con el logo de Proyecto Bethany. |
| `README.md` | Este documento. |

El código del servidor y la interfaz completa están en el proyecto de Google Apps Script de la organización, no en este repositorio.

## Privacidad y seguridad

- El sistema guarda datos personales de las mamás y de sus hijos e hijas. Al crear la cuenta, cada mamá acepta su uso según la **Ley N.º 8968** de Protección de la Persona frente al Tratamiento de sus Datos Personales.
- Solo la administración puede ver los datos. Las mamás solo ven su propia información.
- Las contraseñas se guardan cifradas. El ingreso se bloquea temporalmente después de varios intentos fallidos.
- Las cuentas nuevas quedan pendientes hasta que la administración las activa.
- Este repositorio **no contiene datos personales** ni contraseñas.

## Estado del proyecto

Versión inicial en etapa de **pruebas y piloto**. Antes de usarla con todas las residentes, se recomienda:
1. Confirmar con la administración las reglas de salida (límite mensual, días permitidos y feriados).
2. Dejar la aplicación, los libros de Excel y este repositorio a nombre de cuentas de Proyecto Bethany.
3. Hacer un piloto con pocas mamás antes de usarla con todas.

## Créditos

- **Desarrollo:** Santiago Volio Argüello, Trabajo Comunal Universitario, LEAD University.
- **Organización:** Proyecto Bethany, Costa Rica.
- Desarrollado con apoyo de herramientas de inteligencia artificial.
