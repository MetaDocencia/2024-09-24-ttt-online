---
layout: workshop      # DON'T CHANGE THIS.
root: .               # DON'T CHANGE THIS EITHER.
curriculum: "Instructor Training" # DON'T CHANGE THIS EITHER. (THANK YOU.)
venue: "MetaDocencia"        # brief name of the institution that hosts the workshop without address (e.g., "Euphoric State University")
address: "online"      # full street address of workshop (e.g., "Room A, 123 Forth Street, Blimingen, Euphoria"), videoconferencing URL, or 'online'
country: "ar"      # "W3" for centrally organized online trainings or lowercase two-letter ISO country code such as "fr" of the host institution if applicable (see https://en.wikipedia.org/wiki/ISO_3166-1)
language: "es"     # lowercase two-letter ISO language code such as "fr" (see https://en.wikipedia.org/wiki/ISO_639-1)
latitude: "45"        # decimal latitude of training venue (use https://www.latlong.net/)
longitude: "-1"       # decimal longitude of the training venue (use https://www.latlong.net)
humandate: "Sep 24 - Oct 10, 2024"    # human-readable dates for the workshop (e.g., "Feb 17-18, 2020")
humantime: "14:00 pm - 18:00 pm UTC−03:00"    # human-readable times for the workshop (e.g., "9:00 am - 4:30 pm")
startdate: 2024-09-24      # machine-readable start date for the workshop in YYYY-MM-DD format like 2015-01-01
enddate: 2024-10-10        # machine-readable end date for the workshop in YYYY-MM-DD format like 2015-01-02
instructor: ["Macarena Quiroga", "Paula Pappalardo", "Jesica Formoso"] # boxed, comma-separated list of trainers' names as strings, like ["Kay McNulty", "Betty Jennings", "Betty Snyder"]
helper: ["Macarena Quiroga", "Paula Pappalardo", "Jesica Formoso"]     # boxed, comma-separated list of helpers' names, like ["Marlyn Wescoff", "Fran Bilas", "Ruth Lichterman"]
contact: ["formacion@metadocencia.org", "jesica.formoso@metadocencia.org"]    # boxed, comma-separated list of contact email addresses for the host, lead instructor, or whoever else is handling questions, like ["marlyn.wescoff@example.org", "fran.bilas@example.org", "ruth.lichterman@example.org"]
etherpad: "https://pad.carpentries.org/2024-09-24-ttt-es-online"            # optional: URL for the workshop Etherpad if there is one
eventbrite:           # optional: alphanumeric key for Eventbrite registration, e.g., "1234567890AB" (if Eventbrite is being used)
---

<!-- See instructions in the comments below for how to edit specific sections of this workshop template. -->

<!--
  HEADER

  Edit the values in the block above to be appropriate for your workshop.
  If the value is not 'true', 'false', 'null', or a number, please use
  double quotation marks around the value, unless specified otherwise.
  And run 'tools/check' *before* committing to make sure that changes are good.
-->

<!--
  EVENTBRITE

  This block includes the Eventbrite registration widget if
  'eventbrite' has been set in the header.  You can delete it if you
  are not using Eventbrite, or leave it in, since it will not be
  displayed if the 'eventbrite' field in the header is not set.
-->
{% if page.eventbrite %}
<iframe
  src="https://www.eventbrite.com/tickets-external?eid={{page.eventbrite}}&ref=etckt"
  frameborder="0"
  width="100%"
  height="248px"
  scrolling="auto">
</iframe>
{% endif %}

<h2 id="general">Información general</h2>

<!--
  INTRODUCTION

  Edit the general explanatory paragraph below if you want to change
  the pitch.
-->

<p>
<a href="{{ site.carpentries_site }}">The Carpentries</a> es una comunidad de práctica centrada en la enseñanza de habilidades fundamentales
  de programación y ciencia de datos a investigadores de todo el mundo. Este evento de Formación de Instructoras e Instructores
  (Instructor Training) está diseñado para preparar a los participantes a fin de que se certifiquen 
  y participen como Instructores de The Carpentries. Sin embargo, gran parte de nuestro plan de estudios 
  se enfoca en principios educativos que se aplican a una amplia variedad de contextos. También damos 
  la bienvenida a participantes que no planean certificarse, pero que simplemente desean mejorar como docentes.
</p>


<p>El Entrenamiento para Docentes de The Carpentries tiene los siguientes objetivos:</p>

* Introducirte a prácticas de enseñanza basadas en evidencia.
* Enseñarte cómo crear un ambiente positivo para los estudiantes en tus talleres.
* Ofrecerte oportunidades para practicar y desarrollar tus habilidades de enseñanza.
* Ayudarte a integrarte en la comunidad de Carpentries.
* Prepararte para usar estas habilidades de enseñanza en los talleres de Carpentries.

<p>Dado que tenemos un tiempo limitado, algunos temas quedan fuera del alcance de esta capacitación. No aprenderemos:</p>

* Cómo programar en R o Python, usar Git o SQL, o cualquiera de los otros temas enseñados en los talleres de <a href="{{ site.dc_site }}">Data Carpentry</a>, <a href="{{ site.lc_site }}">Library Carpentry</a> o <a href="{{ site.swc_site }}">Software Carpentry</a>.
* Cómo crear tus propias lecciones desde cero. Sin embargo, esta Formación de Instructoras e Instructores (Instructor Training) es buena precursora para [The Carpentries Lesson Developer Training]({{ site.lessondev_training_site }}).


<p> Los eventos de Formación de Instructoras e Instructores son completamente prácticos: lecciones breves se alternan 
con ejercicios prácticos individuales y grupales, incluidas sesiones de práctica de enseñanza. Este evento
de Formación de Instructoras e Instructores es el primer paso hacia la certificación como persona instructora de The Carpentries. Para más 
detalles sobre los otros 3 pasos, consulta la página de <a href="{{ site.training_site }}/checkout.html">Instrucciones de Salida (Checkout Instructions)</a>. 
Para más información, consulta nuestro <a href="{{ site.training_site }}">Currículo de Formación de Instructoras e Instructores (Instructor Training Curriculum)</a>. </p> 

<h3>Pautas de Convivencia</h3>

Todos los y las participantes deben cumplir con el <a href="{{ site.swc_site }}/conduct/">Código de Conducta</a> de The Carpentries.
A su vez, como el taller es dictado por MetaDocencia, quienes participan deben hacerlo bajo las <a href="https://www.metadocencia.org/pdc/">Pautas de Convivencia</a> de la organización. 

{% assign begin_address = page.address | slice: 0, 4 | downcase  %}
{% if page.address == "online" %}
{% assign online = "true_private" %}
{% elsif begin_address contains "http" %}
{% assign online = "true_public" %}
{% else %}
{% assign online = "false" %}
{% endif %}
<!--
  LOCATION

  This block displays the address and links to maps showing directions
  if the latitude and longitude of the workshop have been set.  You
  can use http://itouchmap.com/latlong.html to find the lat/long of an
  address.
  -->
<h3 id="where">Lugar</h3>


{% if online == "false" %}
<p id="venue">
  {{page.address}}.
  {% if page.latitude and page.longitude %}
  Get directions with
  <a href="//www.openstreetmap.org/?mlat={{page.latitude}}&mlon={{page.longitude}}&zoom=16">OpenStreetMap</a>
  or
  <a href="//maps.google.com/maps?q={{page.latitude}},{{page.longitude}}">Google Maps</a>.
  {% endif %}
</p>
{% elsif online == "true_public" %}
<p id="venue">
  Online at <a href="{{page.address}}">{{page.address}}</a>.
  The training will be conducted using the Zoom video conferencing platform. No log-in is needed.
  However, if you have not used Zoom before, please click the link a few minutes early as it may prompt you to
  install the Zoom app or browser extension. You should have received a connection link in the same email that
  directed you to this website. If you found this page by another means and did not receive the connection link,
  please check your spam folder and email instructor.training@carpentries.org with your Trainers (contact details below) on cc.
</p>
{% elsif online == "true_private" %}
<p id="venue">
  Este entrenamiento se realizará en línea.
  Las instructoras te proporcionarán la información que necesitas para conectarte a esta reunión.
</p>
{% endif %}


<h2 id="preparation" name="preparation">Cómo prepararse para la Formación de Instructoras e Instructores</h2>

Antes de tu capacitación, visite nuestra página Preparación para la capacitación de instructores para obtener instrucciones completas. Un breve resumen de estas instrucciones es el siguiente:

<p>
  Por favor, lee lo siguiente antes de comenzar el entrenamiento:
</p>
<ol>
  <li><a href="https://carpentries.github.io/instructor-training/files/papers/science-of-learning-2015.pdf">The Science of Learning</a></li>
  <li><a href="https://carpentries.org/files/reports/AnnualReport2023.pdf">The Carpentries 2023 Annual Report</a></li>
</ol>
<p>
  Por favor, también lee con detalle <em>un episodio</em> de una de las lecciones de The Carpentries  
  detalladas debajo, para que puedas hacer algunos ejercicios basándote en esta durante tu primer
  día de clase. Un episodio es una página de una lección. 
</p>

  <ul>
  <li><a href="{{ site.dc_site }}/lessons">Lecciones de Data Carpentry</a></li>
  <li><a href="{{ site.lc_site }}/lessons">Lecciones de Library Carpentry</a></li>
  <li><a href="{{ site.swc_site }}/lessons">Lecciones de Software Carpentry</a></li>
  </ul>



<p>

  <h3>Certificación: El Proceso de Certificación de Personas Instructoras</h3> 

Después del evento de capacitación, te pedimos que completes tres tareas de seguimiento para convertirte en Instructor certificado. Estos requisitos se detallan en nuestra <a href="{{ site.training_site }}/checkout.html">página de Instrucciones de Certificación</a> y se discutirán en nuestra capacitación.

{% if online == "false" %}

<h3>Qué Traer a un Evento Presencial</h3>
Los participantes deben traer una laptop con conexión a Internet y un navegador funcional. Si lo tienes, un dispositivo para grabar audio y video (teléfonos móviles y laptops son adecuados) es útil, ya que vamos a grabarnos unos a otros enseñando en parejas o tríos. No tiene que ser de alta calidad, pero debe ser lo suficientemente bueno como para entender lo que alguien está diciendo. 

{% endif %}

<h3 id="accessibility">Accesibilidad</h3>

Estamos comprometidos a hacer que esta
capacitación sea accesible para todos.
{% if online == "false" %}Organisers have checked that:

<ul>
  <li>The room is wheelchair / scooter accessible.</li>
  <li>Accessible restrooms are available.</li>
</ul>
{% endif %}

Los materiales se proporcionarán antes del evento.

No requerimos que quienes participan proporcionen documentación de discapacidades ni revelen información personal innecesaria.
Sin embargo, queremos ayudar a crear una experiencia inclusiva y accesible para todas las personas.
Te animamos a compartir cualquier información que sea útil para hacer tu experiencia más accesible.
Para solicitar una adaptación para esta capacitación, por favor completa el
<a href="https://carpentries.typeform.com/to/B2OSYaD0">formulario de solicitud de adaptación</a>.
Si tienes preguntas o necesitas asistencia con el formulario de adaptación, por favor <a href="mailto:team@carpentries.org">envíanos un correo electrónico</a>.




<h3>Asistencia y Cancelación</h3> 

Los participantes que falten más de 1 hora de la capacitación pueden ser señalados como ausentes. 
La certificación no puede completarse sin asistencia completa a un evento de Formación de Instructoras e Instructores. 
Si inesperadamente necesitas ausentarte más de 1 hora de tu evento, por favor contacta a tus instructores 
(la información de contacto está abajo).
Para eventos en los que la inscripción se realiza a través de The Carpentries vía Eventbrite, la cancelación puede realizarse en Eventbrite hasta el inicio del evento.
Los cupos cancelados no pueden ser llenados después del plazo de registro de 1 semana para estos eventos, por lo que te pedimos que solo canceles si es absolutamente necesario.

Más información sobre nuestra <a href="https://docs.carpentries.org/topic_folders/instructor_training/cancellations_and_makeups.html">política de cancelación y reposición</a> está disponible en el Manual de The Carpentries (The Carpentries Handbook).


<h3 id="contact">Contacto</h3>
<p>
Por favor, escribe a
{% if page.contact %}
  {% for contact in page.contact %}
    {% if forloop.last and page.contact.size > 1 %}
      o
    {% else %}
      {% unless forloop.first %}
      ,
      {% endunless %}
    {% endif %}
    <a href='mailto:{{contact}}'>{{contact}}</a>
  {% endfor %}
{% else %}
  to-be-announced
{% endif %}
for more information.
</p>

<hr/>

<h3 id="materials" name="materials">Materiales del entrenamiento y cronograma</h3>

<p>
  Por favor, mirá el <a href="{{ site.training_site }}/instructor/index.html#schedule">curriculum de Formación de Instructoras e Instructores (Instructor Training Curriculum)</a> para el material del curso.

</p>


<!--
NOTE: This space can be customized to reflect the unique schedule of your training. If you would like it to display,
adjust the times and titles, then delete the characters above and below that serve to comment it out.
-->

<!--
TWO DAY SCHEDULE
--->
<!--
<div class="row">
  <div class="col-md-6">
    <h3>Day 1</h3>
    <table class="table table-striped">
      <tr> <td>09:00</td> <td>Welcome </td> </tr>
      <tr> <td>09:30</td> <td>Building Skill with Practice </td> </tr>
      <tr> <td>10:30</td> <td>Morning Break </td> </tr>
      <tr> <td>10:45</td> <td>Expertise and Instruction </td> </tr>
      <tr> <td>11:30</td> <td>Memory and Cognitive Load </td> </tr>
      <tr> <td>12:15</td> <td>Building Skill with Feedback </td> </tr>
      <tr> <td>12:35</td> <td>Lunch </td> </tr>
      <tr> <td>13:35</td> <td>Motivation and Demotivation </td> </tr>
      <tr> <td>14:35</td> <td>Equity, Inclusion, and Accessibility </td> </tr>
      <tr> <td>15:15</td> <td>Afternoon Break </td> </tr>
      <tr> <td>15:30</td> <td>Teaching Is a Skill </td> </tr>
      <tr> <td>16:30</td> <td>Wrap-up and Homework </td> </tr>
      <tr> <td>16:50</td> <td>Finish </td> </tr>
    </table>
  </div>
  <div class="col-md-6">
    <h3>Day 2</h3>
    <table class="table table-striped">
      <tr> <td>09:00</td> <td>Welcome Back </td> </tr>
      <tr> <td>09:10</td> <td>Getting Started on Instructor Certification </td> </tr>
      <tr> <td>09:40</td> <td>The Carpentries: How We Operate </td> </tr>
      <tr> <td>10:25</td> <td>Morning Break </td> </tr>
      <tr> <td>10:40</td> <td>Live Coding Is a Skill </td> </tr>
      <tr> <td>11:45</td> <td>Preparing to Teach </td> </tr>
      <tr> <td>12:30</td> <td>Lunch </td> </tr>
      <tr> <td>13:30</td> <td>More Practice Live Coding </td> </tr>
      <tr> <td>14:15</td> <td>Working with Your Team</td> </tr>
      <tr> <td>15:25</td> <td>Afternoon Break </td> </tr>
      <tr> <td>15:40</td> <td>Launches and Landings </td> </tr>
      <tr> <td>16:20</td> <td>Putting it Together </td> </tr>
      <tr> <td>16:40</td> <td>Wraping Up </td> </tr>
      <tr> <td>16:50</td> <td>Post-Training Survey </td> </tr>
      <tr> <td>17:05</td> <td>Finish </td> </tr>
    </table>
  </div>
</div>

-->


<div class="row">
  <div class="col-md-6">
    <h3>Día 1</h3>
    <table class="table table-striped">
      <tr> <td>14:00</td> <td>Bienvenidos </td> </tr>
      <tr> <td>14:30</td> <td>Construir habilidad con práctica </td> </tr>
      <tr> <td>15:30</td> <td>Descanso </td> </tr>
      <tr> <td>15:45</td> <td>Experiencia e instrucción </td> </tr>
      <tr> <td>16:30</td> <td>Memoria y carga cognitiva </td> </tr>
      <tr> <td>17:15</td> <td>Contruir habilidad con feedback </td> </tr>
      <tr> <td>17:35</td> <td>Final del día 1 </td> </tr>
    </table>
  </div>
  <div class="col-md-6">
    <h3>Día 2</h3>
    <table class="table table-striped">
      <tr> <td>14:00</td> <td>Motivación y demotivación </td> </tr>
      <tr> <td>15:00</td> <td>Equidad, inclusión y accesibilidad </td> </tr>
      <tr> <td>15:40</td> <td>Descanso </td> </tr>
      <tr> <td>15:55</td> <td>Enseñar es una habilidad </td> </tr>
      <tr> <td>17:15</td> <td>Conclusión y tarea para la próxima </td> </tr>
      <tr> <td>17:30</td> <td>Final del día 2</td> </tr>
    </table>
  </div>
</div>
<div class="row">  
  <div class="col-md-6">
    <h3>Día 3</h3>
    <table class="table table-striped">
      <tr> <td>09:00</td> <td>Bienvenidos de nuevo </td> </tr>
      <tr> <td>09:10</td> <td>Primeros pasos para la certificación </td> </tr>
      <tr> <td>09:40</td> <td>The carpentries: cómo operamos </td> </tr>
      <tr> <td>10:25</td> <td>Descanso </td> </tr>
      <tr> <td>10:40</td> <td>La programación en vivo es una habilidad </td> </tr>
      <tr> <td>11:45</td> <td>Preparándonos para enseñar </td> </tr>
      <tr> <td>12:30</td> <td>Final del día 3 </td> </tr>
    </table>
  </div>
  <div class="col-md-6">
    <h3>Día 4</h3>
    <table class="table table-striped">
      <tr> <td>14:00</td> <td>Más práctica de programación en vivo </td> </tr>
      <tr> <td>14:45</td> <td>Trabajando con tu equipo</td> </tr>
      <tr> <td>15:55</td> <td>Descanso </td> </tr>
      <tr> <td>16:10</td> <td>Introducciones y conclusiones </td> </tr>
      <tr> <td>16:50</td> <td>Combinamos todo </td> </tr>
      <tr> <td>17:10</td> <td>Concluimos </td> </tr>
      <tr> <td>17:20</td> <td>Encuesta post-entrenamiento </td> </tr>
      <tr> <td>17:25</td> <td>Final del taller </td> </tr>
    </table>
  </div>
</div>



<!--
  ETHERPAD

  At `_misc/etherpad.txt` you will find a template for the etherpad.

  Display the Etherpad for the workshop.  You can set this up in
  advance or on the first day; either way, make sure you push changes
  to GitHub after you have its URL.  To create an Etherpad, go to

      http://pad.software-carpentry.org/YYYY-MM-DD-site

  where 'YYYY-MM-DD-site' is the identifier for your workshop,
  e.g., '2015-06-10-esu'.
-->
{% if page.etherpad %}


<p id="etherpad">
  <strong>Etherpad:</strong> <a href="{{page.etherpad}}">{{page.etherpad}}</a>.
  <br/>
  Usaremos este Etherpad para conversar, tomar notas y compartir URLs y fragmentos de código.
</p>

{% endif %}

<h3 id="pre_workshop_survey">Encuestas</h3>

<p>
  Antes del taller, por favor llene nuestra <a href="https://tiny.cc/ttt-Encuesta-pre">encuesta pre-entrenamiento</a>.
</p>


<p>
  Luego del taller, por favor llene nuestra <a href="https://tiny.cc/ttt-Encuesta-pre">encuesta post-entrenamiento</a>.
</p>



