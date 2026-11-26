BIM DOC MANAGER 7.0 - DESTINO DE LAS COPIAS (VERSIÓN WEB)
=========================================================

CAMBIO
En la pantalla web, en «02 Procesar y exportar», se añadió
«Guardar copias en…» junto al botón ya existente «Descargar ZIP».

FUNCIONAMIENTO
1. Carga documentos, completa su nomenclatura y pulsa «Validar nomenclatura».
2. Pulsa «Generar copias válidas».
3. Pulsa «Guardar copias en…».
   - Si el navegador admite elegir carpetas (File System Access API), selecciona
     una carpeta del dispositivo. La aplicación creará «renombrados_BIM» dentro
     de ella y guardará los documentos con sus nombres normalizados, además de
     «bitacora_BIM.csv» en la carpeta seleccionada.
   - Si el navegador permite elegir dónde guardar un archivo pero no carpetas,
     se abrirá un selector para guardar el ZIP.
   - Si el dispositivo permite compartir archivos desde el navegador, aparecerá
     la opción «Compartir / Guardar en Archivos»; selecciónala y elige el destino
     en el menú nativo del dispositivo (según las opciones disponibles).
   - Si el navegador no admite ninguna de esas opciones, se descargará un ZIP.
     En Android, busca Descargas o Mis archivos. En iPhone, abre Archivos >
     Descargas (o el gestor de descargas del navegador) y mueve o extrae el ZIP
     a la carpeta deseada.
4. Como alternativa, «Descargar ZIP» siempre descarga un ZIP normal.

IMPORTANTE
- Los navegadores no permiten que un sitio web escriba libremente en cualquier
  carpeta del teléfono o del PC. Por eso, no hay una opción universal de elegir
  carpeta y la conducta varía según el navegador y el sistema operativo.
- No puedes elegir con la web una carpeta arbitraria del computador SERVIDOR
  desde un teléfono remoto. El guardado local necesita permiso del navegador.
- Los documentos del servidor siguen siendo temporales; descarga tus resultados.
- Cada navegador mantiene su propio espacio de trabajo y sus descargas.
- El inicio ngrok y la dirección fija siguen funcionando como antes.
- No se modificaron la versión de escritorio, core.py ni las reglas BIM.

ARCHIVOS MODIFICADOS
mobile_web.py        : API para obtener cada copia generada individualmente.
web_mobile/app.js    : nuevo botón con guardado adaptado al navegador.
web_mobile/index.html: botón y ayuda contextual.
tests/test_mobile_web.py: pruebas de guardado y aislamiento de sesiones.
