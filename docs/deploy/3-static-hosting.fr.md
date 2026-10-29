<!--
title: "Hébergement statique"
description: "Déployer sur un hébergement statique (Surge, deed.page)."
date: 2026-03-27
updated: 2026-10-29
path: documentation/deployer/hebergement-statique
-->
# Hébergement statique

Le site généré peut être envoyé tel quel vers n’importe quel service d’hébergement statique.

## Surge

> Publier des projets web doit être rapide, simple et peu risqué. Surge est un service de publication de sites statiques pour les développeurs frontend, directement depuis la CLI.

➡️ <https://surge.sh>

Terminal :

```bash
npm install -g surge
surge _site/
```

[Documentation officielle](https://surge.sh/help/)

## deed.page

> Hébergement statique sans compte : envoyez le site généré en une seule requête et obtenez une URL permanente `https://<slug>.deed.page/`.

➡️ <https://deed.page>

Terminal :

```bash
cecil build --baseurl=https://my-cecil-site.deed.page/
tar -C _site -czf site.tar.gz .
curl -T site.tar.gz "https://deed.page/v1/sites?slug=my-cecil-site"
```

La réponse JSON contient un jeton : conservez-le et envoyez-le dans un en-tête `Authorization: Bearer` pour mettre à jour le même slug plus tard. Un envoi est limité à 4 Mo.

[Documentation officielle](https://deed.page/docs)
