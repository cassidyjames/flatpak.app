---
permalink: 404.html
---

# Page Not Found

## Hm… whatever you're looking for, it isn't here!

Try heading to [the homepage]({{ site.baseurl }})? If you've disabled JavaScript, this proof-of-concept won't work for you.

<script>
  document.addEventListener ('DOMContentLoaded', (event) => {
    let path = window.location.pathname.replace ("{{ site.baseurl }}/", "");
    let rdnnRegex = /[A-Z,a-z,0-9][A-Z,a-z,0-9,-]*[A-Z,a-z,0-9]\.[A-Z,a-z,0-9][A-Z,a-z,0-9,-]*[A-Z,a-z,0-9]\.[A-Z,a-z,0-9]/;
    const shortnames = [{% for app in site.data.apps %}
      "{{ app.shortname }}",
    {% endfor %}];

    if (shortnames.includes (path)) {
      window.location.replace("https://flathub.org/apps/" + path);
    } else if (rdnnRegex.test (path)) {
      window.location.replace("https://flathub.org/apps/" + path);
    }
  })
</script>
