NUEVA OPCION: ENLACE FIJO NGROK (MISMA URL EN CADA EJECUCION)
------------------------------------------------------------
Primero lee README_ENLACE_FIJO.txt.
CONFIGURAR_NGROK.bat -> una sola vez (requiere cuenta gratuita ngrok)
INICIAR_ENLACE_FIJO.bat -> el mismo enlace cuando se reinicia el programa

BIM DOC MANAGER – NORMALIZACIÓN DE NOMBRES BIM
==============================================

PROPÓSITO
---------
Tomar documentos que llegan con nombres informales (por ejemplo, "plano final.pdf"),
permitir completar sus metadatos y proponer un nombre de archivo según el Manual de
Nomenclatura de Documentos al utilizar BIM de buildingSMART Spain, revisión 1.1 (2023).
El manual está alineado con la serie ISO 19650. El propio manual aclara que es una propuesta
consensuada y adaptable, no una norma ISO obligatoria.

ARCHIVOS
--------
app.py          Interfaz gráfica principal.
ui_theme.py     Tema claro / negro mate y preferencias de apariencia.
core.py         Lectura, normalización, validación, copia y exportación.
catalogos.json  Catálogos de tipos de documento, disciplinas y estados recogidos del manual.
tests/          Pruebas automatizadas del motor.

REQUISITOS
----------
Python 3.10 o superior. No requiere instalar paquetes externos: usa la biblioteca estándar.

EJECUCIÓN
---------
1. Descomprime la carpeta en tu computador.
2. Abre una terminal dentro de la carpeta BIM_Doc_Manager_ISO19650.
3. Ejecuta: python app.py
4. Pulsa "Seleccionar archivos…" para elegir uno o varios archivos (Ctrl o Shift),
   y/o "Seleccionar carpeta…" para agregar todos los documentos de una carpeta.
   Puedes repetir ambas acciones para combinar archivos de distintas ubicaciones.
   La opción "Limpiar" borra la selección actual (no borra archivos del disco).
5. Selecciona o confirma la carpeta de salida.
6. Pulsa "Cargar documentos". Los archivos repetidos se cargan una sola vez.
7. Haz doble clic en cada fila para completar los campos requeridos. Los campos obligatorios
   no se deducen automáticamente del nombre informal.
8. También puedes seleccionar varias filas y usar "Aplicar datos comunes" para Proyecto,
   Creador, Volumen/Sistema y Nivel/Localización.
9. Pulsa "Validar nomenclatura" y revisa los nombres propuestos y observaciones.
10. Solo después de revisar, pulsa "Generar copias válidas" y confirma.
11. Exporta la bitácora o una plantilla CSV si necesitas completar muchos documentos en Excel.

NOTA: El selector nativo de Windows/Tkinter distingue entre archivos y carpetas.
Por eso la interfaz ofrece dos botones, que pueden usarse juntos en un mismo lote.

CAMPOS SEGÚN EL MANUAL (PÁGINA 9)
---------------------------------
Proyecto: 2 a 12 caracteres alfanuméricos (obligatorio).
Creador: 3 a 6 caracteres alfanuméricos (obligatorio).
Volumen/Sistema: 2 a 3 caracteres alfanuméricos (obligatorio).
Nivel/Localización: 3 caracteres alfanuméricos (obligatorio).
Tipo de documento: código del Anexo I (obligatorio).
Disciplina: código de 3 letras del Anexo II (obligatorio).
Número: tres dígitos, de 001 a 999 (obligatorio).
Descripción: opcional; se normaliza como UpperCamelCase.
Estado: opcional; se comprueba con los estados incluidos en el catálogo.
Revisión: opcional; cuatro dígitos (dos pares: versión mayor y menor).

Los campos se unen en el orden del manual con guiones medios. La extensión original se conserva.
El manual recomienda que el nombre total no exceda 60 caracteres; la aplicación lo informa como
advertencia, sin convertir esa recomendación en un bloqueo obligatorio.

LIMITACIONES IMPORTANTES
------------------------
- La herramienta no interpreta el contenido técnico de un PDF, DWG, RVT u otro documento.
- No puede deducir con certeza Proyecto, Creador, Volumen, Nivel, Tipo, Disciplina, Número,
  Estado o Revisión solo a partir de un nombre informal.
- La descripción inicial es solo una sugerencia textual basada en el nombre original; el usuario
  debe revisarla.
- El usuario o el responsable del proyecto debe confirmar los códigos y valores específicos
  del proyecto. No se inventan códigos.
- El programa crea copias y conserva los originales. Nunca sobrescribe un archivo de salida.

PRUEBAS
-------
Ejecuta desde esta carpeta: python -m unittest discover -s tests -v

ACTUALIZACIÓN: PUNTOS 2 Y 3 — VALIDACIÓN Y CAMPOS DESPLEGABLES
----------------------------------------------------------------
Se reparó el formulario de edición de documentos: ahora aparecen los 10 campos.
Volumen/Sistema y Nivel/Localización ofrecen listas desplegables con ejemplos del
manual buildingSMART Spain (pp. 11-12), pero aceptan códigos definidos en un proyecto.
El botón Guardar campos comprueba longitud, caracteres y códigos de los catálogos y
explica los errores antes de cerrar. Aplicar datos comunes valida los valores nuevos.
Los dos campos guardan solamente el código seleccionado (por ejemplo, E01 o P00).
El archivo INICIAR.bat ejecuta esta versión de app.py.

ACTUALIZACIÓN: MODO OSCURO (VERSIÓN 7.0)
--------------------------------------
En la esquina superior derecha de la ventana principal encontrarás un botón
con una LUNA «☾ Modo oscuro». Púlsalo para activar el estilo negro mate.
En modo oscuro cambia a «☀ Modo claro» para volver al diseño original.

El cambio afecta a la ventana principal, la tabla de documentos, los botones,
los campos, los desplegables, el formulario «Completar nomenclatura» y la
ventana «Aplicar datos comunes». No modifica la nomenclatura, la validación,
las rutas ni los archivos originales. Los diálogos del sistema operativo
(como el explorador y las alertas de Windows) pueden conservar su tema nativo.

El modo que elijas se recordará cuando cierres y vuelvas a abrir el programa.
Se guarda en un pequeño archivo de configuración en la carpeta de usuario:
    .bim_doc_manager_theme.json
Si no se puede guardar esta preferencia, el cambio de modo funcionará igualmente
hasta cerrar el programa.
No requiere instalar paquetes adicionales.


ACCESO DESDE TELEFONO (NUEVO)
----------------------------
Para abrir la misma lógica de nomenclatura desde un navegador de telefono
Android o iPhone, ejecuta INICIAR_MOVIL.bat en el PC.
Conecta el telefono a la misma Wi-Fi y abre la URL que aparece.
Lee README_MOVIL.txt antes de iniciar. No es APK ni app autonoma.
Este modo no cambia el funcionamiento de INICIAR.bat.


ACCESO REMOTO DESDE CUALQUIER RED
--------------------------------
Ejecuta INICIAR_INTERNET.bat y consulta README_INTERNET.txt.
Requiere cloudflared (Cloudflare Tunnel) y mantiene el PC como servidor temporal.
No solicita correo; cualquiera con el enlace completo, incluida la clave,
puede abrirlo mientras este activo. No modifica la app principal ni el motor documental.

NOTA DE VERSION - ACCESO REMOTO VERIFICADO
Si INICIAR_INTERNET.bat muestra por error "MISMA red Wi-Fi", extrae este ZIP
completo en una carpeta nueva y prueba INICIAR_INTERNET_VERIFICADO.bat.
No mezcles el contenido del ZIP con instalaciones anteriores.
