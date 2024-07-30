[![](../../RESSOURCES/LOGOS/LOGO_STMS_001.png)](../../README.md)

<span style="background-color:rgba(153, 0, 138, 0.92)">Caution</span>

> Les restrictions décrites ici s'appliquent à l'utilisation des fonctionnalités ECMAScript modernes dans les projets écrits en JavaScript natif. Si votre projet est écrit en TypeScript, il vous suffit de vous assurer que les contraintes listées sont respectées par le code transpilé.

# <span style="color:rgba(32, 144, 243, 1)">Overview of Restrictions</span>

Les restrictions suivantes s'appliquent lorsque vous utilisez ECMAScript moderne :

1. N'utilisez pas de modules ECMAScript mais utilisez ``sap.ui.define`` / ``sap.ui.require`` pour le chargement des modules.

    Pour plus d'informations, voir _[Définition et chargement de modules SAPUI5](https://sapui5.hana.ondemand.com/topic/0cb44d7a147640a0890cefa5fd7c7f8e.html#loio0cb44d7a147640a0890cefa5fd7c7f8e/section_UI5Mod)_.

2. Utilisez uniquement les classes ES6+ pour les classes non dérivées des classes SAPUI5. Lorsque les classes dérivent des classes SAPUI5, procédez à la manière SAPUI5 : ``ClassName.extend()``.

    Pour plus d'informations, voir _[Héritage SAPUI5](https://sapui5.hana.ondemand.com/topic/0cb44d7a147640a0890cefa5fd7c7f8e.html#loio0cb44d7a147640a0890cefa5fd7c7f8e/section_UI5Inherit)_.

3. Utilisez uniquement des littéraux de chaîne (c'est-à-dire pas de variables, pas de littéraux de modèle de variable, pas de paramètre de propagation) pour les noms de dépendances, les noms de classes et les noms de bibliothèques.

    Pour plus d'informations, consultez _[Définition et chargement de modules SAPUI5](https://sapui5.hana.ondemand.com/topic/0cb44d7a147640a0890cefa5fd7c7f8e.html#loio0cb44d7a147640a0890cefa5fd7c7f8e/section_UI5Mod)_ (expressions en tant que dépendances et suivantes), _[Héritage SAPUI5](https://sapui5.hana.ondemand.com/topic/0cb44d7a147640a0890cefa5fd7c7f8e.html#loio0cb44d7a147640a0890cefa5fd7c7f8e/section_UI5Inherit)_ (expressions en tant que noms de classe et suivantes) et _[Initialisation de la bibliothèque](https://sapui5.hana.ondemand.com/topic/0cb44d7a147640a0890cefa5fd7c7f8e.html#loio0cb44d7a147640a0890cefa5fd7c7f8e/section_libInit)_.

4. N'utilisez pas de fonctions asynchrones ou de promesses pour définir un module.

    Pour plus d'informations, voir Fonction d'usine asynchrone dans _[Définition et chargement de modules SAPUI5](https://sapui5.hana.ondemand.com/topic/0cb44d7a147640a0890cefa5fd7c7f8e.html#loio0cb44d7a147640a0890cefa5fd7c7f8e/section_UI5Mod)_.

5. N'utilisez pas de fonctions asynchrones lors de l'implémentation de hooks de cycle de vie prédéfinis, tels que ``sap/ui/core/mvc/Controller#onInit``.

    Pour plus d’informations, consultez _[Fonctions asynchrones et gestionnaires d’événements](https://sapui5.hana.ondemand.com/topic/0cb44d7a147640a0890cefa5fd7c7f8e.html#loio0cb44d7a147640a0890cefa5fd7c7f8e/section_EHR)_.

#### Information(s) complémentaire(s)

- _[ECMAScript2022 Language Specification](http://help.sap.com/disclaimer?site=https://262.ecma-international.org/13.0/)_