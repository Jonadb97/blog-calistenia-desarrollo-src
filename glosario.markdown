---
layout: default
title: Glosario de ejercicios
---
<div class="col-8 col-mx-auto">
<h1>Glosario de ejercicios</h1>
<div class="flexrow">
<div class="flexcolumn" >
<h2>Por tipo de ejercicio:</h2>
<div class="card-body" id="cuerpoEjercicios">
{% assign tags =  site.ejercicios | map: 'tags' | join: ','  | split: ',' | uniq %}
{% for tag in tags %}

<div class="dropdown text-bold text-capitalize ">
  <a class="btn btn-link dropdown-toggle strong b" tabindex="0">
    {{ tag }} <i class="icon icon-caret"></i>
  </a>
  <!-- menu component -->
  <ul class="menu strong b ">
    {% for ejercicio in site.ejercicios %}
    {% if ejercicio.tags contains tag %}
    <li class="strong b"><a class="strong b" href="{{ site.baseurl }}{{ ejercicio.url }}">{{ ejercicio.title }}</a></li>
    {% endif %}
  {% endfor %}
  </ul>
</div>
{% endfor %}
</div>
</div>
<div class="flexcolumn card">
<div class="card-header"><h2>Todos los ejercicios:</h2></div>
<div class="card-body">
{% for ejercicio in site.ejercicios %}

   <a id="extitle" href="/calisteniablog{{ ejercicio.url }}">
      {{ ejercicio.title }}
   </a>
   <br>
{% endfor %}

</div>
</div>
</div>
<!--
<ul>
  {% for ejercicio in site.ejercicios %}
    <li>
      <h2><a href="{{ ejercicio.url }}">{{ ejercicio.title }}</a></h2>
      <p>{{ ejercicio.content | markdownify }}</p>
    </li>
  {% endfor %}
</ul>

-->
