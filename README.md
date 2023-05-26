# flatpak.app

**Experiment in short Flatpak URLs** by [Cassidy James](https://cassidyjames.com). As a proof-of-concept, I've taken a couple dozen of the most popular apps on Flathub (plus a few of my own for testing) and given them nice, predictable short URLs in the format of flatpak.app/name.

As a proof-of-concept, this site is running entirely staticly on GitHub Pages (abusing the 404 template) and thus requires client-side JavaScript. A proper production version should probably be server-side. In the spirit of decentralization, it supports remotes other than just Flathub, though naming conflicts might be interesting.

There are a number of open questions:

1. What do we do if there are naming conflicts? E.g. Akira is on both AppCenter and Flathub.

2. Is this a terrible, unmaintainable idea?

3. How do we maintain this? Community-led best-effort?

4. Does this have any value?
