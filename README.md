# Refonte — déploiement

## Structure attendue

    refonte/
      index.html
      vercel.json
      favicon.svg              <- À AJOUTER (le tien)
      fonts/
        refonte-ui.woff2       <- À AJOUTER (le tien)
        SpaceGrotesk.ttf
        OFL-SpaceGrotesk.txt
      vendor/
        opentype.min.js
        gif.js
        gif.worker.js
        mp4-muxer.js

Les deux fichiers marqués « À AJOUTER » ne sont pas dans cette archive :
ce sont tes fichiers. `favicon.svg` manquant n'a aucune conséquence.
`refonte-ui.woff2` manquant fait basculer toute l'interface sur une police
de secours, donc il faut vraiment le mettre.

## Déployer

    npm i -g vercel
    cd refonte
    vercel          # aperçu
    vercel --prod   # mise en ligne

Au premier `vercel` : framework preset « Other », build command vide,
output directory « . ».

## Dépendances

Plus aucun appel réseau vers un CDN. opentype.js, gif.js et mp4-muxer sont
servis depuis /vendor, la police de démo depuis /fonts.
Space Grotesk est sous licence SIL OFL 1.1 (voir fonts/OFL-SpaceGrotesk.txt).
