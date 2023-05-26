---
permalink: 404.html
---

# Page Not Found

## Hm… whatever you're looking for, it isn't here!

Try heading to [the homepage](/)? If you've disabled JavaScript, this proof-of-concept won't work for you.

<script>
  document.addEventListener ('DOMContentLoaded', (event) => {
    let path = window.location.pathname.slice (1, window.location.pathname.length);
    const rdnns = [{% for app in site.data.apps %}
      "{{ app.rdnn }}",
    {% endfor %}];
  })
</script>
