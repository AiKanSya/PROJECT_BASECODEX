[![](../../RESSOURCES/LOGOS/LOGO_STMS_001.png)](../../README.md)

# <span style="color:rgba(32, 144, 243, 1)">DEFINE & LOAD SAPUI5 MODULES</span>

SAPUI5 implémente une manière de type AMD pour définir et charger les modules. Comme la définition de module asynchrone (AMD) n'est pas entièrement compatible avec les modules ECMAScript, l'utilisation des modules ECMAScript n'est actuellement pas prise en charge.

## <span style="color:rgba(32, 144, 243, 1)">ECMAScript Modules</span>

SAPUI5 fournit ``sap.ui.define`` et ``sap.ui.require`` comme moyens établis pour définir et charger des modules. L'utilisation des instructions d'importation et d'exportation pour charger et définir les modules SAPUI5 n'est actuellement pas prise en charge.

Veuillez continuer à utiliser les API SAPUI5 habituelles, ``sap.ui.define`` et ``sap.ui.require``.

- <span style="background-color:rgba(0, 93, 147, 1)">Supported usage</span>

  ```js
  // Bonne pratique de chargement d'un module livré par SAPUI5

  sap.ui.define([
      "sap/ui/core/mvc/Controller"
  ], (Controller) => {
      "use strict";
      return Controller.extend("my.app.controller.MyController", {});
  });
  ```

- <span style="background-color:rgba(153, 0, 138, 0.92)">Restriction - Not supported</span>

  ```js
  // N'utilisez PAS les instructions d'importation et d'exportation ECMAScript 
  // lors du chargement/définition de modules SAPUI5

  import Controller from "sap/ui/core/mvc/Controller";
  export class MyController extends Controller {};
  ```

## <span style="color:rgba(32, 144, 243, 1)">Asynchronous Factory Functions</span>

N'utilisez pas de fonction asynchrone lors du chargement ou de la définition de modules SAPUI5. Le chargeur SAPUI5 n'attendra pas une promesse renvoyée.

- <span style="background-color:rgba(153, 0, 138, 0.92)">Restriction - Not supported</span>

  ```js
  // N'utilisez PAS les instructions async/await ECMAScript lors du chargement/définition 
  // de modules

  sap.ui.define([
      "sap/ui/core/mvc/Controller"
  ], async (Controller) => {
      "use strict";
      return Controller.extend("my.app.controller.MyController", {});
  });
  ```

Ne renvoyez pas non plus de promesse lors du chargement ou de la définition de modules SAPUI5.

- <span style="background-color:rgba(153, 0, 138, 0.92)">Restriction - Not supported</span>

  ```js
  // Ne renvoie PAS de promesse lors du chargement/définition de modules

  sap.ui.define([
      "sap/ui/core/mvc/Controller"
  ], (Controller) => {
      "use strict";
      return Promise.resolve(Controller.extend("my.app.controller.MyController", {}));
  });
  ```

## <span style="color:rgba(32, 144, 243, 1)">Expressions as Dependencies</span>

Utilisez uniquement des littéraux, mais pas des expressions pour les dépendances dans le contexte des appels ``sap.ui.define`` et ``sap.ui.require``.

- <span style="background-color:rgba(153, 0, 138, 0.92)">Restriction - Not supported</span>

  ```js
  // Ne PAS utiliser d'expression dans la liste des dépendances dans un appel 
  // sap.ui.define ou sap.ui.require.

  const sController = "sap/ui/core/mvc/Controller";
  sap.ui.define([
    sController
  ], (Controller) => {
  });
  ```

## <span style="color:rgba(32, 144, 243, 1)">Spread Elements as Dependencies</span>

N'utilisez pas d'élément spread comme paramètre dans le contexte des appels ``sap.ui.define`` et ``sap.ui.require``.

- <span style="background-color:rgba(153, 0, 138, 0.92)">Restriction - Not supported</span>

  ```js
  // N'utilisez PAS d'élément spread comme paramètre dans un appel sap.ui.define 
  // ou sap.ui.require.

  const dependencies = [
      "sap/ui/core/mvc/Controller", 
      "sap/ui/mode/Filter", 
      "sap/ui/model/FilterOperator", 
      "sap/ui/model/json/JSONModel"
  ];
  sap.ui.define([
    ...dependencies
  ], (Controller, Filter, FilterOperator, JSONModel) => {
  });
  ```

## <span style="color:rgba(32, 144, 243, 1)">Template Literals as Dependencies</span>

L'utilisation de littéraux de modèle avec une ou plusieurs expressions dans le contexte des appels ``sap.ui.define`` et ``sap.ui.require`` n'est pas prise en charge.

- <span style="background-color:rgba(0, 93, 147, 1)">Supported usage</span>

  ```js
  // Utilisation de littéraux de modèle sans aucune expression à l'intérieur d'un 
  // appel sap.ui.define ou sap.ui.require est pris en charge

  sap.ui.define([
    `sap/ui/core/mvc/Controller`
  ], (Controller) => {
  });
  ```

- <span style="background-color:rgba(153, 0, 138, 0.92)">Restriction - Not supported</span>

  ```js
  // N'utilisez PAS de littéraux de modèle avec un ou plusieurs expressions à 
  // l'intérieur d'un appel sap.ui.define ou sap.ui.require.

  const sLibName = `ui/core`;
  
  sap.ui.define([
    `sap/${sLibName}/mvc/Controller`
  ], (Controller) => {
  });
  ```