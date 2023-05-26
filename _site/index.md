<ul>
{% for app in site.data.apps %}
  <li>
    <a href="{{ site.baseurl }}/{{ app.shortname }}">
      {{ app.shortname }}
    </a>
  </li>
{% endfor %}
</ul>
