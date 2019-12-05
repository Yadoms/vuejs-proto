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
