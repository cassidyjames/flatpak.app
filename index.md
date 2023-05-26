<ul>
{% for app in site.data.apps %}
  <li>
    <a href="https://flathub.org/apps/{{ app.rdnn }}">
      {{ app.shortname }}
    </a>
  </li>
{% endfor %}
</ul>
