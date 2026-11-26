BIM DOC MANAGER 7.0 — ENLACE FIJO (NGROK)
=========================================

OBJETIVO
Cada vez que abras el programa, tanto el dominio HTTPS asignado a tu cuenta
ngrok como la clave privada en ?key= deben ser exactamente los mismos.
Cualquiera que tenga el enlace completo podrá acceder sin correo.

PRIMER USO (en Windows)
1) Descomprime el ZIP en una carpeta nueva.
2) Instala ngrok desde https://ngrok.com/download/windows
   - Alternativa por winget: winget install ngrok -s msstore
3) Crea una cuenta gratuita en https://dashboard.ngrok.com/signup
4) Ejecuta CONFIGURAR_NGROK.bat y pega TU AUTHTOKEN desde tu panel de ngrok.
   IMPORTANTE: es una configuracion local, no debes compartir el token.
5) Ejecuta INICIAR_ENLACE_FIJO.bat.
6) Copia el enlace HTTPS completo, con ?key=, y compartelo de forma privada.
7) Desde el celular abre el enlace por otra Wi-Fi o datos moviles.
   Nota: ngrok gratis puede mostrar un aviso previo al abrir el sitio.

PROXIMAS VECES
Solo abre INICIAR_ENLACE_FIJO.bat. No necesitas reconfigurar ngrok.
El enlace sera el MISMO mientras uses la misma cuenta/dominio ngrok y no
cambies la clave en la configuracion local.

SEGURIDAD Y LIMITACIONES
- El acceso es SIN CORREO, pero el enlace con ?key= es una credencial.
- Cada navegador dispone de un espacio de trabajo independiente.
- Abrir el mismo enlace en otro navegador o telefono no muestra los documentos de otros.
- Las pestanas del mismo navegador comparten el espacio de trabajo del navegador.
- Las sesiones dependen del almacenamiento local del navegador; borrar los datos
  del sitio puede crear un espacio de trabajo nuevo.
- Quien tenga el enlace completo puede abrir la aplicacion sin correo; el enlace
  sigue siendo privado y no sustituye la autenticacion de usuarios.
- Para revocar el enlace ejecuta CAMBIAR_CLAVE_ENLACE.bat con el servidor cerrado:
  la URL base sigue igual, pero cambiara la parte ?key= y deberas compartir el nuevo.
- La clave se guarda en tu propio computador, no se incluye en el archivo ZIP,
  en %LOCALAPPDATA%\BIM_Doc_Manager_7_0\enlace_fijo.json.
- Mantén encendido el PC, su acceso a Internet y la consola mientras lo uses.
- Los documentos subidos se almacenan temporalmente en el PC; descárgalos
  antes de cerrar la consola. Se eliminan al terminar.
- No compartas documentos confidenciales sin autorización.
- El servicio gratis de ngrok puede tener limites de consumo o un aviso inicial.
- Si cambias de cuenta ngrok o de dominio asignado, el programa mostrara error
  en vez de prometer que conserva el mismo enlace.
- No tienes que desinstalar Cloudflare: el metodo nuevo no lo utiliza.
- No se modifico el funcionamiento de BIM DOC MANAGER en Windows ni la app movil.

ARCHIVOS DE INICIO
  INICIAR.bat                 -> programa Windows
  INICIAR_MOVIL.bat           -> telefono en la misma Wi-Fi
  INICIAR_INTERNET.bat        -> Cloudflare temporal (enlace cambia)
  INICIAR_ENLACE_FIJO.bat     -> ngrok con enlace fijo (recomendado)
  CONFIGURAR_NGROK.bat       -> configura cuenta ngrok una vez
  CAMBIAR_CLAVE_ENLACE.bat    -> invalida el enlace anterior

FUENTE OFICIAL
  https://ngrok.com/docs/gateway/domains
