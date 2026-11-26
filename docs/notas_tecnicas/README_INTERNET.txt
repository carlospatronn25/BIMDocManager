BIM DOC MANAGER 7.0 — COMPARTIR ENLACE SIN CORREO
=================================================

Ahora no es necesario registrar un correo ni recibir códigos.
CUALQUIER PERSONA QUE RECIBA EL ENLACE COMPLETO podrá usar la aplicación desde
cualquier Wi-Fi o datos móviles durante esa sesión.

CÓMO INICIAR
------------
1. Descomprime el ZIP en una carpeta NUEVA, no encima de la versión anterior.
2. Entra en Program 7-0/BIM_Doc_Manager_ISO19650.
3. Si falta Cloudflare, ejecuta INSTALAR_CLOUDFLARED.bat una sola vez.
4. Abre INICIAR_INTERNET.bat (o INICIAR_INTERNET_VERIFICADO.bat).
5. Ya no te pedirá correo. Aparecerá un enlace parecido a este:
   https://nombre-temporal.trycloudflare.com/?key=CLAVE_ALEATORIA
6. Copia el enlace COMPLETO, incluyendo todo lo que va después de ?key=.
7. Compártelo de forma privada. Las personas invitadas lo abrirán en el navegador
   de su teléfono; no necesitan crear cuenta, introducir correo ni contraseña.
8. Mantén el computador encendido, conectado a Internet y la consola abierta.
9. Al terminar, descarga el ZIP/bitácora y cierra la consola (Ctrl+C).

AVISO DE PRIVACIDAD
-------------------
- El enlace completo es la ÚNICA llave de acceso. No lo publiques ni lo
  compartas con personas a las que no les darías acceso a los documentos.
- Todas las personas con el enlace completo pueden ver, editar, renombrar,
  descargar y gestionar los documentos de LA MISMA SESIÓN.
- Los documentos subidos pasan por Cloudflare y se procesan temporalmente en
  tu computador. No uses esta modalidad para documentos confidenciales sin
  autorización y evaluación de privacidad.
- Si se filtra el enlace, detén el programa con Ctrl+C, vuelve a ejecutarlo
  y comparte el nuevo enlace. El anterior deja de funcionar.
- El enlace es TEMPORAL y cambia en cada ejecución; no es un dominio fijo.
- No abre puertos en el router: el servidor escucha solo en 127.0.0.1.
- Los archivos temporales se eliminan al terminar la sesión. Descárgalos antes.
- Cloudflare Quick Tunnel está indicado para pruebas y uso temporal, no para
  alojar un servicio permanente. Requiere que el PC esté encendido.

OTROS MODOS
-----------
INICIAR.bat:             Aplicación de escritorio Windows (sin cambios).
INICIAR_MOVIL.bat:       Aplicación para móvil en la misma red Wi-Fi.
INICIAR_INTERNET.bat:    Aplicación accesible desde cualquier red con enlace.

No se modificaron los módulos de nomenclatura, ni el tema claro/negro mate,
ni el formulario, ni la generación de documentos de la versión Windows.
