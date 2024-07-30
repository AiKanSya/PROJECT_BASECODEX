[![](../../RESSOURCES/LOGOS/LOGO_STMS_001.png)](../../README.md)

# <span style="color:rgba(32, 144, 243, 1)">SAPUI5 INHERITANCE</span>

SAPUI5 implémente sa propre fonctionnalité pour étendre les classes (via la méthode ``sap.ui.core.ManagedObject#extend``). L'utilisation d'une classe ECMAScript pour étendre une classe SAPUI5 n'est actuellement pas prise en charge.

## <span style="color:rgba(32, 144, 243, 1)">ECMAScript classes</span>

SAPUI5 utilise sa propre manière de définir les classes et de les étendre. Veuillez vous en tenir aux meilleures pratiques actuelles et ne pas utiliser de classes ECMAScript lors de l'extension d'une classe SAPUI5 fournie.

- <span style="background-color:rgba(0, 93, 147, 1)">Supported usage</span>

    ```js
    // Meilleure pratique d'extension d'une classe existante fournie par SAPUI5

    sap.ui.define(["sap/ui/core/mvc/Controller"], (Controller) => {
        "use strict";
        return Controller.extend("my.app.controller.MyController", {});
    });
    ```

- <span style="background-color:rgba(153, 0, 138, 0.92)">Restriction - Not supported</span>

    ```js
    // N'utilisez pas de classes ECMAScript lors de l'extension d'une classe SAPUI5 fournie

    sap.ui.define(["sap/ui/core/mvc/Controller"], (Controller) => {
        "use strict";
        return class MyController extends Controller {};
    });
    ```
## <span style="color:rgba(32, 144, 243, 1)">Expressions as Class Name</span>

N'utilisez pas d'expression, uniquement un littéral, dans le paramètre de nom de classe à l'intérieur de l'appel d'extension.

- <span style="background-color:rgba(153, 0, 138, 0.92)">Restriction - Not supported</span>

    ```js
    // N'utilisez PAS d'expression dans le paramètre de nom de classe à l'intérieur 
    // de l'appel d'extension

    const sControllerPath = "my.app.controller.";
    sap.ui.define([
        "sap/ui/core/mvc/Controller"
    ], (Controller) => {
        "use strict";
        return Controller.extend(sControllerPath + "MyController", {});
    });
    ```

## <span style="color:rgba(32, 144, 243, 1)">Variable Usages as Class Name</span>

N'utilisez pas de variable comme paramètre de nom de classe dans l'appel d'extension.

- <span style="background-color:rgba(153, 0, 138, 0.92)">Restriction - Not supported</span>

    ```js
    // N'utilisez PAS de variable comme paramètre dans l'appel d'extension

    const sController = "sap/ui/core/mvc/Controller";
    sap.ui.define([
        "sap/ui/core/mvc/Controller"
    ], (Controller) => {
        "use strict";
        return Controller.extend(sController, {});
    });
    ```

## <span style="color:rgba(32, 144, 243, 1)">Template Literals as Class Name</span>

L'utilisation de littéraux de modèle avec une ou plusieurs expressions comme paramètre de nom de classe dans l'appel d'extension n'est pas prise en charge.

- <span style="background-color:rgba(0, 93, 147, 1)">Supported usage</span>

    ```js
    // Utilisation de littéraux de modèle sans aucune expression dans l'appel d'extension

    sap.ui.define([
        "sap/ui/core/mvc/Controller"
    ], (Controller) => {
        "use strict";
        return Controller.extend(`my.app.controller.MyController`, {});
    });
    ```

- <span style="background-color:rgba(153, 0, 138, 0.92)">Restriction - Not supported</span>

    ```js
    // N'utilisez PAS de littéraux de modèle avec une ou plusieurs expressions 
    // à l'intérieur de l'appel d'extension.

    const sControllerPath = "my.app.controller.";
    sap.ui.define([
        "sap/ui/core/mvc/Controller"
    ], (Controller) => {
        "use strict";
        return Controller.extend(`${sControllerPath}MyController`, {});
    });
    ```