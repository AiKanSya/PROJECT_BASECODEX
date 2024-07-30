[![](../../RESSOURCES/LOGOS/LOGO_STMS_001.png)](../../README.md)

# <span style="color:rgba(32, 144, 243, 1)">BROWSER & PLATEFORM SUPPORT</span>

> <span style="background-color:rgba(0, 93, 147, 1)">Note</span>
>
> La seule source d'informations sur les navigateurs et les plates-formes pris en charge est la matrice de disponibilité des produits (PAM) que vous pouvez trouver sur _https://support.sap.com/pamInformation_. SAPUI5 n'est pas un produit en soi, veuillez donc vérifier le PAM du produit avec lequel vous utilisez SAPUI5. Pour plus d'informations, voir la _[note SAP 1716423](https://me.sap.com/notes/1716423)_.
>
> Les sections suivantes contiennent uniquement des informations supplémentaires sur les restrictions et les informations de prise en charge de la plateforme pour des bibliothèques SAPUI5 spécifiques sous une forme résumée.

Comme SAPUI5 est basé sur CSS3, HTML5 et ECMAScript moderne (« ES2022 »), seuls les navigateurs dotés des fonctionnalités correspondantes sont pris en charge. En général, seules les versions majeures également prises en charge par la plateforme respective peuvent être prises en charge par le framework SAPUI5.

- <span style="background-color:rgba(153, 0, 138, 0.92)">Restriction - Not supported</span>

    Avec SAPUI5 1.116, le framework exploite les fonctionnalités d'ECMAScript moderne jusqu'aux informations de _[spécification du langage ECMAScript 2022 incluses](http://help.sap.com/disclaimer?site=https://262.ecma-international.org/13.0/)_. Certaines restrictions s'appliquent cependant. Pour plus d’informations, consultez le _[support ECMAScript](https://sapui5.hana.ondemand.com/#/topic/0cb44d7a147640a0890cefa5fd7c7f8e)_.

Selon la plateforme sur laquelle vos applications SAPUI5 s'exécutent, différents navigateurs dans différentes versions sont pris en charge. Si vous savez quelle plateforme et quels navigateurs sont utilisés par vos utilisateurs, vous pouvez décider quelles bibliothèques utiliser pour votre application.

## <span style="color:rgba(32, 144, 243, 1)">Overview of Supported Browsers, Platforms, and Reference Devices</span>

Les tableaux suivants donnent un aperçu général des navigateurs, plates-formes et appareils de référence pris en charge par les principales bibliothèques SAPUI5. Certaines combinaisons appareil-navigateur connues entraînent des dégradations visuelles. Pour plus d’informations, consultez Dégradations visuelles.

> <span style="background-color:rgba(0, 93, 147, 1)">Note</span>
>
> Les navigateurs évoluent constamment sur différents appareils. Les mises à niveau du navigateur peuvent introduire des modifications qui ne sont pas rétrocompatibles et peuvent affecter le comportement de SAPUI5. SAP n'a aucun contrôle sur ces mises à niveau et ne fournit aucune garantie concernant les fonctionnalités ou qualités de ces navigateurs.

## <span style="color:rgba(32, 144, 243, 1)">Browser and Platform Support Matrix</span>

| PLATFORM             | DEVICE CATEGORY     | PLATFORM VERSION                            | SAFARI         | WEB VIEW           | MICROSOFT EDGE (CHROMIUM)[^2] | GOOGLE CHROME      | MOZILLA FIREFOX                                              | SAP FIORI CLIENT   |
|----------------------|---------------------|---------------------------------------------|----------------|--------------------|-------------------------------|--------------------|--------------------------------------------------------------|--------------------|
| ``Windows[^1]``      | Desktop             | Windows 10 Windows 11                       | -              | Latest version     | Latest version                | Latest version     | Latest version and latest Extended Support Release (ESR)[^9] | -                  |
| ``Windows[^1]``      | Touch[^5]           | Windows 10 Windows 11                       | -              | Latest version     | Latest version[^9]            | Latest version[^9] | Latest version and latest Extended Support Release (ESR)[^9] | Latest version[^7] |
| ``MasOS``            | Desktop             | Latest major 2 versions                     | Latest version | -                  | Latest version[^5]            | Latest version[^5] | -                                                            | -                  |
| ``iOS & iPadOS[^3]`` | Phone and Table[^5] | Latest version                              | Latest version | Latest version[^9] | -                             | -                  | -                                                            | Latest version[^7] |
| ``Android[^4]``      | Phone and Table[^5] | Latest major 3 versions supported by Google | -              | -                  | -                             | Latest version     | -                                                            | Latest version[^7] |
