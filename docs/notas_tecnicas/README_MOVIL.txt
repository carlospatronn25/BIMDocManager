BIM DOC MANAGER 7.0 — ACCESO DESDE UN TELEFONO
====================================================

ESTA VERSION NO ES UN APK NI UNA APLICACION iOS INSTALABLE.
Es una interfaz web adaptada a la pantalla del telefono. Ejecuta el
motor core.py original y los catalogos buildingSMART Spain desde un PC.

PASOS EN WINDOWS:
1. Descomprime el ZIP en una carpeta local.
2. Verifica que Python 3.10 o superior este instalado.
3. Haz doble clic en INICIAR_MOVIL.bat.
4. Windows podria pedir permiso de Firewall: permite REDES PRIVADAS solamente.
5. Se mostrara una direccion parecida a:
   http://192.168.1.20:8765/?key=CLAVE_TEMPORAL
6. Conecta el telefono (Android o iPhone) a la MISMA red Wi-Fi que el PC.
   Desactiva los datos moviles si interfieren con la conexion local.
7. Copia y abre la direccion COMPLETA en el navegador del telefono.
8. Usa los botones Elegir archivos / Elegir carpeta (cuando el navegador lo permita).
9. Completa la nomenclatura; valida; genera las copias y DESCARGA EL ZIP.
10. Mantén el computador y la ventana negra de INICIAR_MOVIL.bat abiertos.

LA VERSION DE ESCRITORIO SIGUE INTACTA:
- Para abrir la aplicación de Windows usa INICIAR.bat.
- Para abrir la versión en telefono usa INICIAR_MOVIL.bat.

FUNCIONES DE LA VERSION MOVIL:
- Carga de varios archivos y, si el navegador lo soporta, carpetas.
- Sugerencia inicial de descripcion; los campos obligatorios se completan a mano.
- Desplegables de Tipo de documento, Disciplina y Estado.
- Sugerencias de Volumen/Sistema y Nivel/Localizacion; codigos personalizados permitidos.
- Edicion de documentos individuales y aplicacion de cuatro datos comunes.
- Validacion con las reglas de core.py (manual buildingSMART Spain v1.1).
- Deteccion de nombres duplicados y destinos ya existentes.
- Generacion de copias, descarga de ZIP y bitacora CSV.
- Importar y exportar CSV, modo oscuro y claro, pantalla de inicio y creditos.

LIMITACIONES IMPORTANTES:
- No funciona sin que el computador mantenga corriendo INICIAR_MOVIL.bat.
- Este modo LOCAL no funciona desde otra red. Para Internet usa INICIAR_INTERNET.bat; no abras el puerto del modo local en el router.
- Los documentos se transfieren al PC y se mantienen temporalmente mientras se
  ejecuta el programa. Se borran al cerrar el servidor; descarga primero el ZIP.
- Se admiten cargas de hasta 60 MB por solicitud y 40 MB por archivo.
- En iPhone ciertos navegadores no permiten escoger carpetas completas. Usa
  Elegir archivos y selecciona varios archivos en su lugar.
- La IP local cambia segun la Wi-Fi; usa la nueva direccion al reiniciar.
- Para usarlo independientemente del PC hay que desarrollar y desplegar un servicio
  web seguro o crear una aplicacion Android/iOS nativa distinta.

Si el telefono no abre la direccion:
- Comprueba que ambos esten conectados a la misma red.
- Comprueba Firewall de Windows y que sea una red Privada.
- Si hay VPN o aislamiento de clientes Wi-Fi, desactivalos para la prueba.
- No uses el enlace http://localhost:8765 desde el telefono.
- Copia la direccion completa con ?key=...
- Prueba otro puerto: python mobile_web.py --port 8877

Motor documental conservado: core.py. No modifica el original de entrada.


ACCESO DESDE OTRA RED (NUEVO)
-----------------------------
Si quieres acceder usando datos móviles u otra Wi-Fi, ejecuta
INICIAR_INTERNET.bat (requiere cloudflared). Consulta README_INTERNET.txt.
El computador debe permanecer encendido y conectado a Internet.
