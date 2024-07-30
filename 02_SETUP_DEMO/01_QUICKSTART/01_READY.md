[![](../../RESSOURCES/LOGOS/LOGO_STMS_001.png)](../../README.md)

# <span style="color:rgba(32, 144, 243, 1)">READY...</span>

#### Preview

![](../RESSOURCES/01_READY_001.png)

Le navigateur affiche un bouton "Prêt" qui déclenche un message "Hello World"

## <span style="color:rgba(32, 144, 243, 1)">Coding</span>

Vous pouvez afficher et télécharger tous les fichiers dans _[Quick Start - Step 1](https://sapui5.hana.ondemand.com/#/sample/sap.m.tutorial.quickstart.01/preview)_.

1. Créez un dossier sur votre machine locale qui contiendra toutes les sources de l'application que nous allons créer. Nous appellerons ce dossier le « dossier racine de l'application » (ici 00_DEMO_PROJECT/01_READY/).

2. Créez un nouveau fichier appelé ``package.json`` qui vous permettra d'exécuter des commandes et de consommer des packages à partir des informations de _[registre npm](http://help.sap.com/disclaimer?site=https://www.npmjs.com/)_ via l'interface de ligne de commande npm. Saisissez le contenu suivant :

    - ``package.json`` (Nouveau)

        ```json
        {
        "name": "quickstart-tutorial",
        "private": true,
        "version": "1.0.0",
        "author": "SAP SE",
        "description": "UI5 Demo App - Quickstart Tutorial",
        "scripts": {
            "start": "ui5 serve -o index.html",
            "build": "ui5 build"
        },
        "devDependencies": {
            "@ui5/cli": "^3"
        }
        }
        ```

3. Créez un nouveau dossier nommé ``webapp`` dans le dossier racine de l'application. Il contiendra toutes les sources qui seront disponibles ultérieurement dans le navigateur. Nous appellerons ce dossier le dossier "webapp".

4. Créez un nouveau fichier HTML nommé ``index.html`` dans votre dossier ``webapp`` et saisissez le contenu suivant :

    - ``webapp/index.html`` (Nouveau)

        ```html
        <!DOCTYPE html>
        <html>
        <head>
            <meta charset="utf-8">
            <title>Quickstart Tutorial</title>
            <script id="sap-ui-bootstrap"
                src="resources/sap-ui-core.js"
                data-sap-ui-libs="sap.m"
                data-sap-ui-compat-version="edge"
                data-sap-ui-async="true"
                data-sap-ui-on-init="module:ui5/quickstart/index"
                data-sap-ui-resource-roots='{
                    "ui5.quickstart": "./"
                }'>
            </script>
        </head>
        <body class="sapUiBody" id="content"></body>
        </html>
        ```

    Avec la balise ``<script>``, nous chargeons et initialisons SAPUI5 avec des paramètres de bootstrap typiques. Nous définissons, par exemple, un thème, des bibliothèques de contrôles, ainsi que des indicateurs de performances et de compatibilité.

    Tout d’abord, nous avons besoin d’une source à partir de laquelle charger SAPUI5. Dans ce didacticiel, nous utiliserons UI5 Tooling pour héberger les ressources OpenUI5.

    La propriété d'amorçage resourceroots définit l'espace de noms pour toutes les ressources de l'application. De cette façon, nous pouvons facilement référencer des fichiers supplémentaires que nous sommes sur le point de créer au cours de cette étape.

    Le module d'index que nous chargeons avec le paramètre onInit contiendra la logique de l'application.

    La balise body est définie avec la classe sapUiBody et l'ID de contenu. C'est ici que nous ajouterons le contenu de l'application dans les prochaines étapes.

5. Dans votre dossier ``webapp``, créez un nouveau fichier ``index.js`` qui sera appelé dès que SAPUI5 sera chargé et initialisé.

    - ``webapp/index.js`` (Nouveau)

        ```js
        sap.ui.define([
            "sap/m/Button",
            "sap/m/MessageToast"
        ], (Button, MessageToast) => {
            "use strict";

            new Button({
                text: "Ready...",
                press() {
                    MessageToast.show("Hello World!");
                }
            }).placeAt("content");

        });
        ```

    Nous chargeons deux contrôles d'interface utilisateur - un bouton et un message toast - et plaçons le bouton dans l'élément avec l'ID de contenu. Le bouton est défini avec une propriété de texte et un rappel attaché à son événement presse.

6. Créez un nouveau fichier nommé ``manifest.json`` dans le dossier ``webapp`` ; il est également connu sous le nom de "descripteur d'application". Toutes les options de configuration spécifiques à l'application que nous présenterons dans ce didacticiel seront ajoutées à ce fichier. Saisissez le contenu suivant :

    - ``webapp/manifest.json`` (Nouveau)

        ```json
        {
            "sap.app": {
                "id": "ui5.quickstart"
            }
        }
        ```

7. Ouvrez un terminal dans le dossier racine de l'application et exécutez 

        npm i -D @ui5/cli
    
    pour installer UI5 Tooling.

8. Exécutez 

        ui5 init 
    
    dans le dossier racine de l'application.

9. Exécutez 

        ui5 use OpenUI5

10. Exécuter 

        ui5 add sap.m sap.tnt sap.ui.core sap.ui.layout themelib_sap_horizon

11. Exécutez 

        npm start 
        
    pour démarrer le serveur Web et ouvrir une nouvelle fenêtre de navigateur hébergeant votre ``index.html`` nouvellement créé.

#### Information(s) associée(s)

- _[Development Environment](https://sapui5.hana.ondemand.com/#/topic/7bb04e05f9484e1b95b38a2e48ecef4f)_

- _[Variant for Bootstrapping from Content Delivery Network](https://sapui5.hana.ondemand.com/#/topic/2d3eb2f322ea4a82983c1c62a33ec4ae)_