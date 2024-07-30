[![](../../RESSOURCES/LOGOS/LOGO_STMS_001.png)](../../README.md)

# <span style="color:rgba(32, 144, 243, 1)">COMPATIBILITY RULES</span>

> <span style="background-color:rgba(153, 0, 138, 0.92)">Attention</span>
>
> - Il est possible de manipuler du HTML/CSS via JavaScript (domRef.className = "someCSSClass";) ou directement via CSS, par exemple. Mais attention : le HTML et le CSS générés par SAPUI5 ne font pas partie de l'API publique et peuvent changer dans les correctifs et les versions mineures. Si vous décidez de remplacer les styles, vous devez tester et mettre à jour vos modifications à chaque mise à jour de SAPUI5. La condition préalable est que vous ayez le contrôle sur la version de SAPUI5 utilisée, par exemple, dans un scénario autonome. Cela n'est pas possible lors de l'exécution de votre application dans la barre de lancement SAP Fiori où SAPUI5 est chargé de manière centralisée pour toutes les applications. En tant que telles, les applications de la barre de lancement SAP Fiori ne doivent pas remplacer les styles.
>
>   Suivez toujours nos recommandations sous Problèmes de style CSS.
>
> - N'utilisez ou ne remplacez jamais des fonctions « privées » qui ne font pas partie de la référence API. Les fonctions privées sont généralement (mais pas toujours) préfixées par un "_" précédent. Vérifiez toujours la référence API, les fonctions privées n’y sont pas répertoriées.

## <span style="color:rgba(32, 144, 243, 1)">API Evolution</span>

Sauf indication contraire, le mot « API » dans cette section fait référence à « API publique », c'est-à-dire les fonctions, classes, espaces de noms, contrôles ainsi que leurs propriétés déclarées, agrégations, etc. La seule définition de l'API publique est la _[référence API](https://sapui5.hana.ondemand.com/#/api/sap.ui)_, qui est incluse dans le kit de démonstration SAPUI5. Les fonctionnalités qui n’y sont pas mentionnées ne font pas partie de l’API.

Les règles suivantes s'appliquent pour l'introduction de nouvelles API ou pour apporter des modifications incompatibles aux API existantes :

- Version majeure (x.yy.zz) : 

    une nouvelle version majeure peut introduire de nouvelles API ou apporter des modifications incompatibles aux API existantes.

- Version mineure (x.yy.zz) : 

    une nouvelle version mineure peut introduire de nouvelles API mais ne doit pas contenir de modifications incompatibles avec les API.

- Version du correctif (x.yy.zz) : 

    une nouvelle version du correctif contient uniquement des correctifs pour l'implémentation existante, mais ne contient généralement pas de nouvelles fonctionnalités ni de modifications d'API incompatibles.

> <span style="background-color:rgba(0, 93, 147, 1)">Note</span>
>
> Des exceptions à ces règles sont possibles, mais uniquement dans des cas très urgents tels que des problèmes de sécurité. Ces exceptions sont documentées dans le _[journal des modifications](https://sapui5.hana.ondemand.com/releasenotes.html)_.

## <span style="color:rgba(32, 144, 243, 1)">Compatible Changes</span>

Les modifications suivantes apportées aux API existantes sont compatibles et peuvent être effectuées à tout moment :

- Ajout de nouvelles bibliothèques, contrôles, classes, propriétés, fonctions ou espaces de noms

- Généraliser les propriétés, c'est-à-dire déplacer les propriétés vers le haut dans la hiérarchie d'héritage

- Ajout de nouvelles valeurs aux types d'énumération ; cela signifie que lorsque vous traitez des propriétés d'énumération, soyez toujours prêt à accepter de nouvelles valeurs, par exemple en implémentant un chemin « par défaut » ou « autrement » lorsque vous réagissez aux valeurs d'énumération.

## <span style="color:rgba(32, 144, 243, 1)">Incompatible Changes</span>

Les éléments suivants ne font pas partie de l'API publique et peuvent changer dans les correctifs et les versions mineures :

- Bibliothèques open source (voir _[Bibliothèques open source tierces](https://sapui5.hana.ondemand.com/topic/91f087396f4d1014b6dd926db0e91070.html#loio91f087396f4d1014b6dd926db0e91070/Open_Source)_)

- Messages du journal

Les modifications suivantes apportées aux API existantes sont incompatibles, mais peuvent être effectuées dans une nouvelle version majeure :

- Renommer une API (bibliothèque, espace de noms, fonction, propriété, contrôle, événements, etc.)

- Suppression de la prise en charge des paramètres

- Suppression de la prise en charge des entrées de configuration

- Réduire la visibilité d'une API ; cela ne casse pas les applications JavaScript, mais modifie le contrat

- Supprimer ou réorganiser les paramètres dans une signature API

- Réduire la plage de valeurs acceptée, par exemple le paramètre d'une fonction

- Élargissement de la plage de valeurs d'une valeur de retour (ou d'une propriété). Exception : les énumérations

- Déplacement d'artefacts JavaScript (espaces de noms, fonctions, classes) entre modules

- Remplacement des assertions par des vérifications de préconditions

- Déplacer les propriétés (et ainsi de suite) vers le bas dans la hiérarchie d'héritage

- Changer le nom des valeurs d'énumération

- Modification des valeurs par défaut (propriétés, paramètres de fonction)

- Renommer ou supprimer des fichiers

## <span style="color:rgba(32, 144, 243, 1)">Inheritance</span>

Hériter d'objets SAPUI5 (par exemple en appelant extend sur une classe de contrôle pour ajouter des fonctionnalités personnalisées) peut mettre en danger la possibilité de mise à jour de votre code.

Lors du remplacement d'une méthode de cycle de vie SAPUI5 (telle que init, exit, onBeforeRendering et onAfterRendering), vous devez vous assurer que l'implémentation de la super classe est appelée, par exemple comme ceci :

```js
MyClass.prototype.onAfterRendering = function() {
  SuperClass.prototype.onAfterRendering.apply(this, arguments);
  // ...
};

MyClass.prototype.exit = function() {
  // Cleanups of your subclass ...
  // Invoke the exit method of the superclass at the end:
  SuperClass.prototype.exit.apply(this, arguments);
};
```

SAP peut ajouter, supprimer ou modifier l'implémentation interne de la classe parent à tout moment. Surtout, vous ne devez pas vous fier aux fonctionnalités suivantes :

- Structures et méthodes internes qui ne font pas partie de l'API publique

- Toute logique interne et tout comportement de l'objet qui ne sont pas reflétés dans l'API publique

- La hiérarchie parent des objets, en particulier pour les composites où le parent API diffère du parent réel (par exemple, objet parent > objet interne > objet enfant). Pour plus d'informations, voir _[Référence API : ``sap.ui.base.ManagedObject``](https://sapui5.hana.ondemand.com/#/api/sap.ui.base.ManagedObject)_.

- Toutes les fonctionnalités de rendu d'un contrôle, y compris la structure HTML et les classes CSS

- Nommer les collisions avec les structures et méthodes SAPUI5. SAPUI5 peut introduire ultérieurement de nouvelles API ou structures internes qui entrent en conflit avec votre implémentation. Pour éviter les collisions, un préfixe personnalisé peut être appliqué. N'utilisez pas d'espaces de noms commençant par sap.m.* ou sap.ui.* dans votre application.

Nous vous recommandons de tester très attentivement les classes héritées après la mise à jour de SAPUI5 pour vous assurer que les fonctionnalités étendues fonctionnent toujours comme prévu.

## <span style="color:rgba(32, 144, 243, 1)">Deprecation</span>

Si cela est possible et approprié, nous marquons les anciens artefacts comme obsolètes et créons de nouveaux artefacts, au lieu d'apporter des modifications incompatibles. Un commentaire de dépréciation dans la documentation de l'API correspondante, et peut-être aussi une entrée de journal dans l'implémentation, expliquent pourquoi et quand un artefact a été obsolète et incluent des conseils sur la façon d'obtenir les mêmes résultats sans utiliser de fonctionnalités obsolètes.

## <span style="color:rgba(32, 144, 243, 1)">Experimental API</span>

Certaines fonctionnalités ou contrôles fournis avec la version actuelle de SAPUI5 sont marqués comme « expérimentaux ». Ces fonctionnalités et contrôles expérimentaux ne font pas partie de la portée publiée de la version SAPUI5 fournie. N'utilisez pas de fonctionnalités ou de contrôles expérimentaux dans un environnement productif ou avec des données qui n'ont pas été suffisamment sauvegardées.

Les fonctionnalités et contrôles expérimentaux peuvent être modifiés ou supprimés à tout moment sans préavis et sans processus de dépréciation formel. Ils peuvent également être incompatibles avec les modifications apportées dans une mise à niveau.

## <span style="color:rgba(32, 144, 243, 1)">Experimental API</span>

SAPUI5 contient et utilise plusieurs bibliothèques open source tierces, telles que jQuery. Ces bibliothèques peuvent également être utilisées par des applications et/ou des bibliothèques de contrôles personnalisées, mais les règles de compatibilité SAPUI5 décrites dans ce document ne s'appliquent pas à ces bibliothèques tierces.

Si vous souhaitez utiliser les bibliothèques open source tierces incluses dans SAPUI5, notez les restrictions suivantes :

- SAP décide quelles versions et modules des bibliothèques utilisées sont fournis.

- SAP peut mettre à niveau vers une version supérieure des bibliothèques utilisées même dans le cadre d'une version de correctif.

- Si nous passons à une nouvelle version par défaut d'une bibliothèque, nous documentons nos résultats qui pourraient avoir un effet sur les applications SAPUI5 (voir _[Mise à niveau](https://sapui5.hana.ondemand.com/#/topic/9638e4fce1bd45f4bebf7c219672908c)_). Assurez-vous d’adapter votre code si nécessaire !

- Pour des raisons importantes telles que la sécurité, SAPUI5 peut cesser de fournir une bibliothèque à tout moment.

- Les bibliothèques tierces sont fournies « telles quelles ». Les extensions, adaptations et support ne sont ni effectués ni fournis par SAP.

> <span style="background-color:rgba(0, 93, 147, 1)">Note</span>
>
> N'utilisez pas de versions différentes de ces bibliothèques car cela pourrait entraîner des effets secondaires imprévus.

Pour obtenir la liste des logiciels open source tiers utilisés dans SAPUI5, choisissez Plus d'informations → À propos et sélectionnez le lien Logiciels tiers inclus.

#### Information(s) associée(s)

- _[Versioning and Maintenance of SAPUI5](https://sapui5.hana.ondemand.com/#/topic/91f021426f4d1014b6dd926db0e91070)_

- _[API Reference](https://sapui5.hana.ondemand.com/#/api/sap.ui)_