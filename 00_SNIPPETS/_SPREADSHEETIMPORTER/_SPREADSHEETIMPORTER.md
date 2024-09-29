# SPREADSHEET IMPORTER (COMPONENT NPM)

[SpreadsheetImporter - Deployment](https://docs.spreadsheet-importer.com/pages/GettingStarted/)

<details>
    <summary>NPM - INSTAL COMPONENT</summary>

- Aller dans la racine du projet, puis

        npm install ui5-cc-spreadsheetimporter@0.33.2

    Le composant `ui5-cc-spreadsheetimporter` s'installera dans `node_modules`. Vérifier cependant que la version installer est la bonne dans le fichier `ui5.yaml`

    ```yaml
    specVersion: '2.6'
    type: module
    metadata:
    name: ui5-cc-spreadsheetimporter
    resources:
    configuration:
        paths:
        /thirdparty/customControl/spreadsheetImporter/v0_33_2/: ./dist/
    ```
  
</details>

<details>
    <summary>MANIFEST.JSON</summary>

- Aller dans le `manifest.json` et ajouter `spreadsheetImporter` ainsi que `resourceRoots` :

    ```json
    "sap.ui5": {
        "flexEnabled": false,
        "componentUsages": {
        "spreadsheetImporter": {
            "name": "cc.spreadsheetimporter.v0_33_2"
            }
        },
        "resourceRoots": {
            "cc.spreadsheetimporter.v0_33_2": "./thirdparty/customControl/spreadsheetImporter/v0_33_2"
            },
        },
        //...
    }
    ```

</details>

<details>
    <summary>PACKAGE.JSON</summary>

- Aller dans le `package.json` et ajouter `dependencies` :

    ```json
    "dependencies": {
        "ui5-cc-spreadsheetimporter": "^0.33.2"
    },
    ```
    
</details>

<details>
    <summary>MAIN.XML</summary>

- Aller dans le `main.xml` et ajouter un bouton de test :

    ```xml
    <m:Button
        text="Importer un fichier Excel"
        press="onOpenXUP" />
    ```
    
</details>

<details>
    <summary>MAIN.CONTROLER.JS</summary>

- Aller dans le `main.controller.js` et ajouter un bouton de test :

    ```js
    onOpenXUP: async function (oEvent) {
        this.getView().setBusyIndicatorDelay(0);
        this.getView().setBusy(true);
        this.spreadsheetUpload = await this.getView()
            .getController()
            .getOwnerComponent()
            .createComponent({
                usage: "spreadsheetImporter",
                async: true,
                componentData: {
                    context: this,
                    tableId: "tableOrder",
                    columns: [
                        "Ebeln",
                        "Lifnr",
                        "Matnr",
                        "Charg",
                        "Vfdat",
                        "Menge",
                        "Meins",
                        "Nobob",
                        "Nopal",
                        "Nocha",
                    ],
                    spreadsheetFileName: "Delivery.xlsx",
                    decimalSeparator: ".",
                    readAllSheets: false,
                    hidePreview: true,
                    showBackendErrorMessages: true,
                    batchSize: 300,
                    sampleData: [
                        {
                            Ebeln: "4200000010",
                            Lifnr: "TO1200",
                            Matnr: "400000",
                            Charg: "A1123A01",
                            Vfdat: "20251205",
                            Menge: 219.6,
                            Meins: "KG",
                            Nobob: "A1123A012102",
                            Nopal: "210295",
                            Nocha: "100000",
                        },
                    ],
                },
            });

        this.spreadsheetUpload.openSpreadsheetUploadDialog();
        this.getView().setBusy(false);
    },
    ```
    
</details>