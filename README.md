# flatpak.app

**Experiment in short Flatpak URLs** by [Cassidy James](https://cassidyjames.com). As a proof-of-concept, I've taken a couple dozen of the most popular apps on Flathub (plus a few of my own for testing) and given them nice, predictable short URLs in the format of flatpak.app/name. This [mapping](https://github.com/cassidyjames/flatpak.app/blob/main/_data/apps.yaml) is openly available. 

If a result is not matched:
- If it's in RDNN-format, it's assumed to be an app listing on Flathub
- Otherwise, it's treated as a search on Flathub

As a proof-of-concept, this site is running entirely staticly on GitHub Pages (abusing the 404 template) and thus requires client-side JavaScript. A proper production version should probably be server-side. In the spirit of decentralization, it supports [remotes](https://github.com/cassidyjames/flatpak.app/blob/main/_data/remotes.yaml) other than just Flathub (if defined in the data file), though naming conflicts might be interesting.

There are a number of open questions:

1. What do we do if there are naming conflicts? E.g. if an app is on both AppCenter and Flathub.

2. Is this a terrible, unmaintainable idea?

3. How _do_ we maintain this? Community-led best-effort?

4. Does this have any value?

## Index:

<ul>
{% for each in site.data.apps %}
  {% assign shortname = each[0] %}
  {% assign app = site.data.apps[shortname] %}

  <li>
    <a href="{{ site.data.remotes[app.remote].path }}{{ app.rdnn }}">
      <strong>{{ shortname }}</strong> ({{ app.name }})
    </a>
  </li>
{% endfor %}
</ul>

## Stats

<iframe plausible-embed src="https://plausible.io/flatpak.app/?embed=true&theme=system" scrolling="no" frameborder="0" loading="lazy" style="width: 1px; min-width: 100%; height: 1600px;"></iframe>
<div style="font-size: 14px; padding-bottom: 14px;">Stats powered by <a target="_blank" style="color: #4F46E5; text-decoration: underline;" href="https://plausible.io">Plausible Analytics</a></div>
<script async src="https://plausible.io/js/embed.host.js"></script>

<script defer data-domain="flatpak.app" src="https://plausible.io/js/script.js"></script>
