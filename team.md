---
layout: page
title: Team
permalink: /team/
---

<div class="row row-cols-2 row-cols-md-3 g-6">
{% for person in site.data.team.team %}
<div class = "col">
    <div class="card">
    {% if person.img%}
        <img src= "{{person.img}}" class="card-img-top rounded-circle" alt="...">
        {% else %}
        <img src="/assets/img/profiles/default.png" class="card-img-top">
    {% endif %}
    <div class="card-body">
        <h5 class="card-title">{{person.name}}</h5>
        <p class="card-text"> {{person.position}} </p>
    </div>
    </div>
</div>
{% endfor %}
</div>