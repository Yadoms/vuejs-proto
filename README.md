# vuejs-proto

## etat des lieux

L'objectif de ce proto de de valider que toutes les fonctionnalités nécessaires à Yadoms sont possibles.

### Widgets
- [X] générer des widgets de façon autonome
- [X] chargement de widget asynchrones
- [ ] mutualiser un composant de base ()
- [ ] fournir une interface widgetApi aux widgets
- [ ] vérifier le dual communication (core -> widget : mise à jour d'une valeur, widget -> core : action à effectuer)

### IHM
- [ ] voir les couches material design (existent mais à creuser)
- [ ] intégration blockly


## Widgets

Dans ce prototype les widgets (sources) sont dans le répertoire "widget"
Chacun des widget et un composant au sens VueJS (widget.vue, widget2.vue, widget3.vue)
On pourrait imaginer de les mettre dans des dossiers séparés, cela ne poserait pas de pb.

En terme de répertoire de sortie, il faut les mettre dans un sous répertoire du dossier "public" (ce dossier est copié tel quel lors de la génération du site web)

Les assets des widgets (ressources graphiques, comme les images) sont référencés par le CSS, et lors de la compilation Vuejs l'identifie et l'ajoute au répertoire de sortie

````
Source
  |
  |- widget.vue
  |- public
        |- logo.png

Destination
   |- public/widgets
                |- widget1
                      |- widget1.umd.min.js
                      |- widget1.umd.min.js.map
                            |- img
                                 |- logo.xxxxxx.png
````


## Project setup
```
npm install
```

### Generate Widgets

All widgets are component bases object, which must be build separately

Build all widgets
```
npm run allwidgets
```

Build single widget
```
npm run widget1
```


### Compiles and hot-reloads for development
```
npm run serve
```

### Compiles and minifies for production
```
npm run build
```

### Run your tests
```
npm run test
```

### Lints and fixes files
```
npm run lint
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).
