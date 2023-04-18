# Voice-Assistant-GPT

Voice-Assistant-GPT es un asistente de voz inteligente que utiliza GPT-3 de OpenAI para generar respuestas y realizar diversas tareas, como contar chistes, buscar en Google, obtener el clima y mostrar las últimas noticias según la ubicación del usuario. El asistente puede cambiar entre modos de entrada de audio y escritos y alternar entre voces sintéticas y naturales.

## Requisitos

- Python 3.6 o superior
- Bibliotecas: consulta la siguiente tabla para obtener información sobre las bibliotecas utilizadas.

| Biblioteca         | Descripción                                                                                      |
| ------------------ | ------------------------------------------------------------------------------------------------ |
| openai             | Interactuar con la API de OpenAI y utilizar el modelo GPT-3 en el asistente.                     |
| typer              | Construir aplicaciones de línea de comandos con una interfaz fácil de usar y moderna.            |
| rich               | Renderizar texto enriquecido, tablas, barras de progreso y más en la terminal.                   |
| speech_recognition | Realizar reconocimiento de voz y convertir audio en texto.                                       |
| webbrowser         | Abrir páginas web en el navegador predeterminado del sistema.                                    |
| pyjokes            | Generar chistes aleatorios en diferentes idiomas.                                                |
| requests           | Realizar solicitudes HTTP y manejar la comunicación con las APIs.                                |
| json               | Trabajar con datos en formato JSON.                                                              |
| pyowm              | Interactuar con la API de OpenWeatherMap y obtener información meteorológica.                    |
| bs4                | Analizar y extraer información de documentos HTML y XML, utilizada en web scraping.              |
| pyttsx3            | Convertir texto en voz utilizando motores TTS (Text-to-Speech) del sistema.                      |
| gtts               | Convertir texto en voz utilizando el servicio Google Text-to-Speech.                             |
| pydub              | Manipular archivos de audio y realizar operaciones básicas, como reproducir y exportar.          |
| geopy              | Realizar geocodificación inversa y obtener la ubicación del usuario a partir de sus coordenadas. |
| sounddevice        | Grabar y reproducir audio utilizando la biblioteca PortAudio.                                    |
| pyaudio            | Grabar y reproducir audio en diferentes plataformas utilizando la biblioteca PortAudio.          |
| locale             | Manejar información de localización y regionalización, como idiomas y formatos de fecha y hora.  |
| zipfile            | Trabajar con archivos ZIP, permitiendo comprimir y descomprimir archivos y directorios.          |
| prettytable        | Generar tablas ASCII con datos tabulares y una apariencia agradable.                             |

## Instalación

1. Clona este repositorio en tu máquina local.
2. Instala las bibliotecas requeridas usando pip: `pip install -r requirements.txt`
3. Configura tus claves API para OpenAI, Climacell y Google News como variables de entorno. Sigue las instrucciones detalladas a continuación:

   ### Configuración de la API Key de OpenAI

   1. Registrate o ingresa y obtén una API Key en https://beta.openai.com/signup.

   2. Obtenga su clave API de OpenAI en: https://platform.openai.com/account/api-keys.

      Para usar la clave API de OpenAI para Voice-Assistant-GPT, NECESITA tener configurada la facturación (también conocida como cuenta paga).

      Puede configurar una cuenta paga en https://platform.openai.com/account/billing/overview.

      ![Cuenta paga](https://github.com/Significant-Gravitas/Auto-GPT/raw/master/docs/imgs/openai-api-key-billing-paid-account.png)

      POR FAVOR, ASEGÚRESE DE HABER REALIZADO ESTE PASO ANTES DE CONTINUAR, DE LO CONTRARIO, ¡NADA FUNCIONARÁ!

   3. Para agregar la clave como variable de entorno en Windows, sigue estos pasos:

      a. Haz clic derecho en 'Mi PC' o 'Este equipo' y selecciona 'Propiedades'.  
      b. Haz clic en 'Configuración avanzada del sistema' en el panel izquierdo.  
      c. Haz clic en 'Variables de entorno'.  
      d. En 'Variables del sistema', haz clic en 'Nuevo...'.  
      e. Establece el nombre de la variable como 'API_KEY' y su valor como la clave obtenida.  
      f. Haz clic en 'Aceptar' y reinicia cualquier consola o IDE en uso.

   4. En macOS y Linux, sigue estas guías para configurar variables de entorno:
      - https://www.cyberciti.biz/faq/set-environment-variable-unix/

   ### Configuración de la API Key de Climacell

   1. Obtén una API Key en https://www.tomorrow.io/signup
   2. Para agregar la clave como variable de entorno en Windows, sigue los pasos mencionados en la API Key de OpenAI.  
      a. Establece el nombre de la variable como 'CLIMACELL_API_KEY' y su valor como la clave obtenida.  
      b. Sigue los pasos del 2b al 2f de la sección de OpenAI para agregar la variable.
   3. En macOS y Linux, sigue las guías mencionadas en la sección de OpenAI.

   ### Configuración de la API Key de Google News

   1. Obtén una API Key en https://newsapi.org/s/google-news-api
   2. Para agregar la clave como variable de entorno en Windows, sigue los pasos mencionados en la API Key de OpenAI.  
      a. Establece el nombre de la variable como 'GOOGLE_NEWS_API_KEY' y su valor como la clave obtenida.  
      b. Sigue los pasos del 2b al 2f de la sección de OpenAI para agregar la variable.
   3. En macOS y Linux, sigue las guías mencionadas en la sección de OpenAI.

### Video de Configuración del Asistente de Voz Inteligente GPT: Creación de APIs y Variables de Entorno

Para ver un video tutorial sobre cómo crear y configurar las API Keys y las variables de entorno, mira el siguiente video en YouTube:

[![Configuración del Asistente de Voz Inteligente GPT](http://img.youtube.com/vi/tadb6eaNwj4/0.jpg)](http://www.youtube.com/watch?v=tadb6eaNwj4)

Puedes seguir estas guías para configurar variables de entorno en diferentes sistemas operativos:

- Windows: https://docs.microsoft.com/es-es/powershell/module/microsoft.powershell.core/about/about_environment_variables?view=powershell-7.1
- macOS y Linux: https://www.cyberciti.biz/faq/set-environment-variable-unix/

### Configurar 'ffmpeg.exe' para la voz natural del asistente de voz inteligente:

Si deseas utilizar la voz natural del asistente de voz inteligente, necesitas tener 'ffmpeg.exe' instalado en tu sistema y configurado correctamente. Sigue estos pasos para configurarlo en Windows:

1.  Descarga 'ffmpeg.exe' desde la página oficial de FFmpeg (https://ffmpeg.org/download.html) y descomprímelo.
    Alternativamente, si tienes el archivo 'ffmpeg.zip' en la raíz del proyecto junto a 'voice_assistant_gpt.py' o 'voice_assistant_gpt.exe', el programa intentará descomprimirlo automáticamente en "C:\".
2.  Mueve la carpeta descomprimida a "C:\" y asegúrate de que la ruta sea "C:\ffmpeg\bin\ffmpeg.exe".
3.  Agrega "C:\ffmpeg\bin" a la variable de entorno Path en Windows:  
    a. Abre el menú de inicio y busca 'Sistema' en la barra de búsqueda. Haz clic en 'Editar la variable de entorno del sistema'.  
    b. En la ventana Propiedades del sistema, haz clic en el botón 'Variables de entorno'.  
    c. Busca la variable 'Path' en la sección 'Variables del sistema' y haz clic en 'Editar'.  
    d. Haz clic en 'Nuevo' y escribe 'C:\ffmpeg\bin' (sin comillas).  
    e. Haz clic en 'Aceptar' para guardar los cambios y cierra todas las ventanas.

Ahora deberías poder utilizar la voz natural del asistente de voz inteligente. Para cambiar el tipo de voz a "natural", escribe "voz natural" en el programa y sigue las instrucciones en pantalla.

Nota: Este tutorial es para Windows. Si estás utilizando macOS o Linux, sigue las instrucciones adecuadas para instalar y configurar 'ffmpeg' en tu sistema.

## Uso

Ejecuta el archivo `voice_assistant_gpt.py` y sigue las instrucciones en pantalla para interactuar con el asistente.

## Demostración

Para ver una demostración del proyecto en acción, mira el siguiente video en YouTube:

[![Voice-Assistant-GPT Demo](http://img.youtube.com/vi/DzpzWJRYW6Y/0.jpg)](http://www.youtube.com/watch?v=DzpzWJRYW6Y)

## Consideraciones importantes

<ul>
<li>Es posible que deba modificar el código para que funcione en un entorno específico.</li>
<li>Asegúrese de manejar errores y excepciones de manera adecuada en caso de que ocurran durante la ejecución del código.</li>
<li>Este código es solo un ejemplo y debe adaptarse a sus necesidades y requisitos específicos.</li>
</ul>

## Licencia

<p>Este código se encuentra bajo la licencia MIT. Puede utilizar, modificar y distribuir este código de acuerdo a los términos de la licencia.</p>

## Autor

<p>Este código fue creado por <strong>Alexander Oviedo Fadul</strong> como ejemplo de una Inteligencia Artificial entrenable. Si tiene alguna pregunta o sugerencia, no dude en contactar al autor a través de GitHub o enviando un correo electrónico a alexander.oviedo.fadul@gmail.com.</p>

## Contribuciones

<p>Este código es un ejemplo y está disponible para que cualquiera pueda utilizarlo y modificarlo. Si desea contribuir con mejoras o correcciones, puede enviar una solicitud de pull a través de GitHub. Todas las contribuciones serán revisadas y, si se aprueban, serán incorporadas al repositorio.</p>

## Agradecimientos

<p><strong>Agradezco a Dios, a mi familia y amigos</strong>. Sin su ayuda, esta aplicación no habría sido posible.</p>

## Donaciones

<p>Somos un equipo de desarrolladores y entusiastas de la inteligencia artificial que hemos creado un asistente de voz inteligente para ayudar a las personas a entender el funcionamiento de una inteligencia artificial y facilitar sus tareas diarias.</p>

<p>Hemos visto la gran utilidad y eficiencia que nuestro asistente de voz inteligente ha brindado a nuestros usuarios, y queremos seguir ofreciéndoles este valioso servicio. Sin embargo, para seguir manteniendo y mejorando nuestro proyecto, necesitamos sostenerlo económicamente. Es por eso que te pedimos tu apoyo como donante.</p>

<p>Con tu contribución, podremos seguir brindando nuestra interfaz de usuario y asistente de voz inteligente a todos aquellos que lo necesiten. Además, tu apoyo nos permitirá seguir mejorando y ampliando nuestras funcionalidades, para que nuestro asistente de voz pueda brindar aún más valor a nuestros usuarios.</p>

<p>Tu donación, por más pequeña que sea, será muy valiosa para nosotros y nos ayudará a seguir brindando este servicio que tantas personas están encontrando útil. Agradecemos de antemano tu apoyo y esperamos que nuestro asistente de voz inteligente pueda ayudarte a ti también en tu día a día.</p>

<p>Gracias por tu tiempo y consideración.</p>

### Métodos:

<ul>
<li><a href="https://www.paypal.com/donate/?hosted_button_id=AVZSDFALB7QJQ" target="_blank">Pypal</a></li>
<li><a href="https://biz.payulatam.com/L0eeee08C27577B" target="_blank">Payu</a></li>
</ul>

<p><a href="https://www.paypal.com/donate/?hosted_button_id=AVZSDFALB7QJQ" target="_blank"><img src="https://www.paypalobjects.com/paypal-ui/logos/svg/paypal-mark-color.svg" style="height:10%; width:10%" /></a> <a href="https://biz.payulatam.com/B0eeee08C27577B"><img src="https://ecommerce.payulatam.com/img-secure-2015/boton_pagar_grande.png"></a></p>

<p><strong>Recuerda que tu imaginación es tu única frontera.</strong></p>
