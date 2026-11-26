BIM DOC MANAGER 7.0 - SESIONES INDEPENDIENTES POR NAVEGADOR
============================================================

CORRECCION
Antes, todos los usuarios del enlace veian los mismos documentos cargados.
Ahora, cada navegador recibe su propio espacio de trabajo con archivos,
metadatos, validaciones, copias, ZIP y bitacora independientes.

COMO ACTUALIZAR
1. Cierra el CMD que ejecuta la version anterior del enlace fijo.
2. Haz una copia de seguridad de tu carpeta del proyecto.
3. Descomprime este ZIP en una carpeta NUEVA.
4. Entra en Program 7-0/BIM_Doc_Manager_ISO19650.
5. Ejecuta INICIAR_ENLACE_FIJO.bat (usa tu configuracion de ngrok previa).
6. Abre el enlace completo desde dos telefonos diferentes y carga archivos
   de prueba distintos en cada uno.
7. Verifica que cada telefono solo vea su propio contenido.

FUNCIONAMIENTO
- El enlace fijo y la clave ?key= se mantienen en tu perfil de Windows.
- No se necesita correo ni crear cuentas para los visitantes.
- El token privado de cada navegador se guarda localmente en ese navegador.
- Dos pestanas del MISMO navegador pueden compartir sus documentos.
- Dos navegadores o dispositivos diferentes tienen sesiones separadas.
- Si se borran los datos del sitio / se usa modo incognito, el navegador
  puede iniciar una nueva sesion vacia.
- Los datos son TEMPORALES: se eliminan al cerrar el servidor. Descarga el
  ZIP de tus documentos antes de cerrar CMD.
- Los documentos que estaban en la version anterior (compartida) NO se
  migran automaticamente: guarda lo que necesites antes de actualizar.
- Se requiere mantener encendido el PC para uso remoto.

PRIVACIDAD
Esta mejora impide que otros navegadores vean o editen documentos con
simplemente abrir el enlace. No es un sistema de cuentas o identidad.
El enlace sigue siendo una credencial: no lo publiques ni compartas con
personas desconocidas. No uses este sistema para documentos sensibles
sin controles de acceso adicionales.

ARCHIVOS PRINCIPALES CAMBIADOS
- mobile_web.py: SessionStore aislado por navegador y API de sesiones.
- web_mobile/app.js: conserva la sesion del navegador tras actualizar.
- iniciar_enlace_fijo.py: usa SessionStore sin cambiar dominio/clave.
- iniciar_internet.py: compatibilidad del servidor temporal.
- tests/: pruebas de aislamiento, ZIP y bitacoras.
