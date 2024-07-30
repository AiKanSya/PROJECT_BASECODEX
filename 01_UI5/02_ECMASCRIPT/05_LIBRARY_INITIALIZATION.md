[![](../../RESSOURCES/LOGOS/LOGO_STMS_001.png)](../../README.md)

# <span style="color:rgba(32, 144, 243, 1)">LIBRARY INITIALIZATION</span>

Une bibliothèque SAPUI5 est généralement initialisée via un library.js qui l'accompagne. Dans ce fichier, l'objet fourni à la méthode sap/ui/core/Lib.init doit prendre en compte les restrictions suivantes :

- <span style="background-color:rgba(0, 93, 147, 1)">Supported usage</span>

    ```js
    // Bonne pratique pour initialiser une bibliothèque dans le fichier library.js

    sap.ui.define([
        "sap/ui/core/Lib"
    ], (Library) => {
        "use strict";
        const thisLib = Library.init(({
            apiVersion: 2,
            name: "my.lib",
            version: "${version}",
            designtime: "my/lib/designtime/library.designtime",
            types: [
                "my.lib.MyType"
            ],
            interfaces: [
                "my.lib.MyInterface"
            ],
            controls: [
                "my.lib.MyType"
            ],
            elements: [
                "my.lib.MyElement"
            ],
            extensions: {}
        });
    });
    ```

## <span style="color:rgba(32, 144, 243, 1)">Expressions as Parameter</span>

N'utilisez pas d'expression pour le nom de la bibliothèque lors de l'initialisation d'une bibliothèque.

- <span style="background-color:rgba(153, 0, 138, 0.92)">Restriction - Not supported</span>

    ```js
    // N'utilisez PAS d'expression pour le nom de la bibliothèque lors de l'initialisation 
    // d'une bibliothèque

    const libraryName = "lib";
    sap.ui.define([
        "sap/ui/core/Lib"
    ], (Library) => {
        "use strict";
        const thisLib = Library.init({
            name: "my." + libraryName
        });
    });
    ```

## <span style="color:rgba(32, 144, 243, 1)">Variable Usages as Parameter</span>

N'utilisez pas de variable pour le nom de la bibliothèque lors de l'initialisation d'une bibliothèque.

- <span style="background-color:rgba(153, 0, 138, 0.92)">Restriction - Not supported</span>

    ```js
    // N'utilisez PAS de variable pour le nom de la bibliothèque lors de l'initialisation
    // d'une bibliothèque

    const key = "name";
    sap.ui.define([
        "sap/ui/core/Lib"
    ], (Library) => {
        "use strict";
        const thisLib = Library.init({
            [key]: "my.lib"
        });
    });
    ```

## <span style="color:rgba(32, 144, 243, 1)">Spread Elements as Parameter</span>

N'utilisez pas d'élément spread pour le nom de la bibliothèque lors de l'initialisation d'une bibliothèque.

- <span style="background-color:rgba(153, 0, 138, 0.92)">Restriction - Not supported</span>

    ```js
    // N'utilisez PAS d'élément spread pour le nom de la bibliothèque lors de l'initialisation 
    // d'une bibliothèque.

    const mylib = {
        name: "my.lib"
    };
    sap.ui.define([
        "sap/ui/core/Lib"
    ], (Library) => {
        "use strict";
        const thisLib = Library.init({
            ...mylib
        });
    });
    ```

## <span style="color:rgba(32, 144, 243, 1)">Template Literals as Parameter</span>

N'utilisez pas de littéral de modèle avec une ou plusieurs expressions pour le nom de la bibliothèque lors de l'initialisation d'une bibliothèque.

- <span style="background-color:rgba(153, 0, 138, 0.92)">Restriction - Not supported</span>

    ```js
    // N'utilisez PAS un modèle littéral avec une ou plusieurs expressions 
    // pour le nom de la bibliothèque lors de l'initialisation d'une bibliothèque

    const libraryName = "lib";
    sap.ui.define([
        "sap/ui/core/Lib"
    ], (Library) => {
        "use strict";
        const thisLib = Library.init({
            name: `my.${libraryName}`
        });
    });
    ```