[![](../../RESSOURCES/LOGOS/LOGO_STMS_001.png)](../../README.md)

# <span style="color:rgba(32, 144, 243, 1)">VERSIONING & MAINTENANCE OF SAPUI5</span>

SAPUI5 utilise un identifiant de version à trois chiffres, par exemple 1.71.22. Les chiffres ont la signification suivante :

- La première partie (1) précise le numéro de release (version majeure).

- La deuxième partie (71) précise le numéro de version (version mineure).

- La troisième partie (22) précise le numéro du patch.

Pour afficher la documentation d'une version spécifique, vérifiez sur _https://ui5.sap.com/versionoverview.html_ quelles versions sont disponibles. Vous pouvez afficher le kit de démonstration spécifique à la version en ajoutant le numéro de version à l'URL, par exemple _https://ui5.sap.com/1.71.22/_.

Pour obtenir un aperçu des nouvelles fonctionnalités de chaque version, voir _[Nouveautés de SAPUI5](https://sapui5.hana.ondemand.com/#/topic/99ac68a5b1c3416ab5c84c99fefa250d)_. Pour voir les correctifs contenus dans chaque correctif, consultez les informations du _[journal des modifications](http://help.sap.com/disclaimer?site=/releasenotes.html)_.

## <span style="color:rgba(32, 144, 243, 1)">Maintenance Strategy</span>

Chaque mois, SAPUI5 publie une nouvelle version pour une utilisation productive :

- Sur SAP Business Technology Platform, toutes les versions de SAPUI5 sont livrées.

- Sur AS ABAP, seules deux versions SAPUI5 par an sont livrées dans le cadre du composant SAP_UI.

La stratégie de publication suit le principe de « une ligne de code d'innovation » : les versions ultérieures garantissent une innovation continue avec une ligne de code évolutive. La version par défaut de nos bibliothèques a l'URL générique _https://ui5.sap.com/resources/sap-ui-core.js_ (SAPUI5). Environ 2 semaines après la sortie d'une nouvelle version SAPUI5, cette version devient la version par défaut.

Une fois par an, une version avec support à long terme est publiée et disponible sur les deux plateformes SAP. Cette version SAPUI5 est incluse dans une version du composant SAP_UI, généralement dans le cadre du SP02 de la version SAP_UI correspondante. Toutes les autres versions n'ont pas de période de maintenance et aucun correctif n'est fourni. Les correctifs requis sont disponibles avec les prochaines versions mineures ainsi que les nouvelles fonctionnalités. Cependant, dans des cas exceptionnels, la version la plus récente peut également être corrigée avec un code de correction.

Pour la décision de consommer une nouvelle version, nous recommandons la ligne directrice suivante :

- Pour SAP BTP, nous vous recommandons de mettre à niveau vers la dernière version SAPUI5 disponible, car elle inclut les dernières fonctionnalités, correctifs et correctifs de sécurité.

- Pour le serveur frontal AS ABAP/SAP Fiori, ou dans le cas où les mises à jour régulières des versions ne sont pas réalisables, nous vous recommandons de mettre à jour vers les versions de maintenance à long terme respectives, comme indiqué dans les exigences minimales d'installation et les notes du serveur frontal SAP Fiori.

Dans l'aperçu des versions sur _https://ui5.sap.com/versionoverview.html_, vous pouvez voir quelles versions de SAPUI5 disposent d'une maintenance étendue.

Pour plus d'informations sur la stratégie de maintenance SAPUI5 pour SAP NetWeaver AS pour ABAP, voir la note SAP _[2217489](https://me.sap.com/notes/2217489)_.

## <span style="color:rgba(32, 144, 243, 1)">Availability of Multiple Versions on the Akamai Content Delivery Network</span>

Les ressources SAPUI5 sont disponibles sur le réseau de diffusion de contenu d'Akamai. Vous pouvez également y trouver plusieurs versions de SAPUI5 et les utiliser dans votre code comme décrit dans [Variante pour l'amorçage à partir de Content Delivery Network](https://sapui5.hana.ondemand.com/#/topic/2d3eb2f322ea4a82983c1c62a33ec4ae).

Vérifiez les versions disponibles avec l'état de maintenance respectif sur _https://ui5.sap.com/versionoverview.html_.

## <span style="color:rgba(32, 144, 243, 1)">SAPUI5 Version</span>

Vous pouvez trouver les versions de framework que vous utilisez dans votre application dans la boîte de dialogue d'informations techniques ( Ctrl + Shift + Left Alt / Option + P ).

Pour accéder à la version SAPUI5 au moment de l'exécution, vous pouvez utiliser le code suivant :

```js
sap.ui.require([
    "sap/ui/VersionInfo",
    "sap/base/util/Version"
], (VersionInfo, VersionUtil) => {
    VersionInfo.load().then(oCurrentVersionInfo => {
    const oSAPUI5Version = new VersionUtil(oCurrentVersionInfo.version);
        // ...
    });
});
```

Le numéro de version du correctif de la version OpenUI5 (contenue dans la distribution SAPUI5) peut être différent, car OpenUI5 inclut principalement les bibliothèques d'exécution principales. Pour plus d’informations, consultez _[SAPUI5 et OpenUI5](https://sapui5.hana.ondemand.com/#/topic/5982a9734748474aa8d4af9c3d8f31c0)_.

Pour accéder spécifiquement à la version OpenUI5 dans une application SAPUI5 au moment de l'exécution, utilisez simplement l'API sap/ui/VersionInfo.load comme dans l'exemple ci-dessus, mais avec "sap.ui.core" comme argument de bibliothèque.

> <span style="background-color:rgba(0, 93, 147, 1)">Note</span>
>
> Applications autonomes, par ex. les applications utilisant la version autonome de _[UI5 ​​Tooling](http://help.sap.com/disclaimer?site=https://sap.github.io/ui5-tooling)_ indiqueront la version de l'application elle-même. Ce n'est que si les ressources du framework sont fournies par un réseau de diffusion de contenu (CDN) ou une installation partagée similaire que la version principale du framework sera récupérée comme indiqué ci-dessus.