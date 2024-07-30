[![](../../RESSOURCES/LOGOS/LOGO_STMS_001.png)](../../README.md)

# <span style="color:rgba(32, 144, 243, 1)">SAPUI5 VS OPENUI5</span>

## <span style="color:rgba(32, 144, 243, 1)">Licenses</span>

La principale différence est la licence.

OpenUI5 est Open Source, gratuit à utiliser, publié sous la licence Apache 2.0. Comme nous utilisons également de nombreuses bibliothèques Open Source, nous essayons de leur rendre la pareille et de bénéficier également de l'expérience et des connaissances des développeurs du monde entier.

SAPUI5 est intégré par exemple dans les produits suivants :

- SAP HANA

- Plateforme technologique d'entreprise SAP

- SAP NetWeaver 7.4 ou supérieur ainsi que la plateforme ABAP 1809 ou supérieure (inclus dans le composant Technologies UI (SAP_UI))

- Module complémentaire d'interface utilisateur pour SAP NetWeaver Application Server 7.3x

## <span style="color:rgba(32, 144, 243, 1)">Content</span>

Le moyen le plus simple d'avoir un aperçu des bibliothèques fournies est de consulter la référence API de chaque kit de démonstration. Vous verrez que la liste des bibliothèques dans SAPUI5 est bien plus longue... ce qui ne veut en aucun cas dire qu'OpenUI5 n'offre qu'un périmètre très limité !

Plus important encore, le noyau contenant toutes les fonctionnalités centrales et les bibliothèques de contrôle les plus couramment utilisées est identique dans les deux livraisons. (Par exemple, ``sap.m``, ``sap.ui.layout``, ``sap.ui.unified``)

Ainsi, OpenUI5 vous offre également toutes les fonctionnalités importantes nécessaires pour créer des applications Web riches en fonctionnalités.

Les bibliothèques supplémentaires de SAPUI5 incluent davantage de contrôles en haut, comme des graphiques, et SAPUI5 vous permet également d'utiliser des « contrôles intelligents », par exemple, qui sont des contrôles automatiquement configurés par les annotations OData depuis le back-end. La gamme exacte de fonctionnalités de SAPUI5 dépend également de la plateforme que vous utilisez. Par exemple, vous ne pouvez utiliser le référentiel ABAP qu'avec SAP NetWeaver et non sur SAP BTP.

## <span style="color:rgba(32, 144, 243, 1)">Contributing to OpenUI5</span>

OpenUI5 est Open Source et est disponible sur [GitHub](http://help.sap.com/disclaimer?site=https://github.com/SAP/openui5/).

Si vous trouvez un bug ou avez une idée pour une nouvelle fonctionnalité, allez-y et proposez un problème ou une modification GitHub. Mais avant de le faire, veuillez d'abord lire nos directives : [Contribuer à OpenUI5](http://help.sap.com/disclaimer?site=https://github.com/SAP/openui5/blob/-/CONTRIBUTING.md).

## <span style="color:rgba(32, 144, 243, 1)">Resources</span>

Pour la version OpenUI5, visitez _https://openui5.org/_ où vous pouvez télécharger le runtime et le Demo Kit (SDK) sur _https://openui5.org/releases/_.

Pour les ressources SAPUI5, vérifiez l'installation de votre plateforme.

Les deux ressources sont également disponibles en ligne via le fournisseur de réseau de diffusion de contenu Akamai à l'adresse _https://sdk.openui5.org/_ et _https://ui5.sap.com/_.

## <span style="color:rgba(32, 144, 243, 1)">Compatibility of OpenUI5 and SAPUI5</span>

Techniquement, vous pouvez basculer entre OpenUI5 et SAPUI5 (à condition que vous disposiez d'un produit dans lequel SAPUI5 est inclus), par exemple, si vous souhaitez utiliser les fonctionnalités spécifiques à SAPUI5.

Tout d'abord, vérifiez de quelle version de SAPUI5 vous avez besoin, car les numéros de version d'OpenUI5 et de SAPUI5 peuvent différer selon le niveau de correctif (dernier numéro). Vous pouvez trouver ces informations dans la boîte de dialogue d'informations techniques ( Ctrl + Alt + Shift + P ).

Si vous utilisez le réseau de diffusion de contenu, vous pouvez simplement vous référer respectivement à _https://sdk.openui5.org/_ (pour OpenUI5) ou _https://ui5.sap.com/_ (pour SAPUI5). Pour plus d’informations, consultez _[Variante pour l’amorçage à partir du réseau de diffusion de contenu](https://sapui5.hana.ondemand.com/#/topic/2d3eb2f322ea4a82983c1c62a33ec4ae)_.

Dans tous les autres cas, remplacez le runtime. Étant donné que les noms techniques (des contrôles, des bibliothèques, etc.) et des API sont les mêmes dans OpenUI5 et SAPUI5, le code fonctionnera toujours et vous pourrez commencer à l'améliorer directement.