[![](../../RESSOURCES/LOGOS/LOGO_STMS_001.png)](../../README.md)

# <span style="color:rgba(32, 144, 243, 1)">ASYNC FUNCTION & EVENT HANDLER</span>

## <span style="color:rgba(32, 144, 243, 1)">SAPUI5 Lifecycle Hooks</span>

N'utilisez PAS de fonctions asynchrones lors de l'implémentation de méthodes de hook de cycle de vie SAPUI5 prédéfinies. SAPUI5 pourrait introduire ultérieurement un type de retour facultatif pour ces fonctions. L'utilisation de fonctions asynchrones ici entraînerait déjà une valeur de retour qui pourrait entrer en conflit avec une telle modification ultérieure.

Les méthodes hook de cycle de vie doivent également s’abstenir de renvoyer une valeur dans leur implémentation. Les hooks de cycle de vie incluent les méthodes suivantes :

| FRAMEWORK CLASS                                   | LIFECYCLE HOOKS                                      |
|-------------------------------------------------------|----------------------------------------------------------|
| ``sap/ui/core/mvc/Controller``                        | onInit() onExit() onBeforeRendering() onAfterRendering() |
| ``sap/ui/core/Element`` ``sap/ui/core/Control``       | init() exit()                                            |
| ``sap/ui/core/Control``                               | onBeforeRendering() onAfterRendering()                   |
| ``sap/ui/core/Component`` ``sap/ui/core/UIComponent`` | init() exit() onActivate() onDesactivate()               |

- <span style="background-color:rgba(153, 0, 138, 0.92)">Restriction - Not supported</span>

    ```js
    sap.ui.require(["sap/ui/core/mvc/Controller"], (Controller) => {
        return Controller.extend("my.controller.Sample", {
            // Do NOT use async event handlers for lifecycle hooks such as "onInit" 
            // or "onExit"
            onInit: async() => {
                await doSomething();
            },
            onExit: async() => {
                await doSomethingOnExit();
            }
        });
    });
    ```

## <span style="color:rgba(32, 144, 243, 1)">Control Event Listeners</span>

Vous pouvez implémenter un gestionnaire d'événements asynchrone pour les événements de contrôle. Cependant, SAPUI5 appelle directement le gestionnaire d'événements sans prendre en compte la promesse renvoyée ni tout ordre d'exécution.

- <span style="background-color:rgba(0, 93, 147, 1)">Supported usage</span>

    ```js
    sap.ui.require(["sap/m/Button"], (Button) => {
        const oButton = new Button({
            text: "Press me",
            press: async() => { // async "press" event handler
            await doSomethingAsync();
            }
        });
    });
    ```

- <span style="background-color:rgba(153, 0, 138, 0.92)">Caution</span>

    Gestion des erreurs

    Les erreurs dans les gestionnaires d’événements asynchrones doivent être soigneusement gérées. Si vous utilisez un wait dans un gestionnaire d'événements et qu'il génère une erreur, celle-ci ne sera généralement pas détectée par le contrôle qui a déclenché l'événement.