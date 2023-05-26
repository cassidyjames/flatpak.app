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

    const apps = {{ site.data.apps | jsonify }};
    const remotes = {{ site.data.remotes | jsonify }};

    let app = apps[path];

    if (app !== undefined) {
      window.location.replace(remotes[app.remote].path + app.rdnn);
    } else if (rdnnRegex.test (path)) {
      window.location.replace("https://flathub.org/apps/" + path);
    }
  })
</script>
