[![](../../RESSOURCES/LOGOS/LOGO_STMS_001.png)](../../README.md)

# <span style="color:rgba(32, 144, 243, 1)">TYPESCRIPT SUPPORT</span>

Les types peuvent être considérés comme un ajout complémentaire pour améliorer votre expérience de développement et vous aider à écrire des applications en JavaScript moderne. Vous pouvez toujours les supprimer à nouveau de votre application en cas de problème. Les navigateurs ne peuvent pas exécuter TypeScript directement ; il doit être transpilé en JavaScript, qui peut ensuite être exécuté comme d'habitude.

## <span style="color:rgba(32, 144, 243, 1)">Delivery of the SAPUI5 Type Information</span>

Lors de l'écriture de code TypeScript, les informations de type peuvent être dispersées dans le code. Mais vous pouvez également créer des fichiers de définition de type distincts pour les bibliothèques JavaScript existantes. Pour SAPUI5, nous fournissons des fichiers de définition distincts qui décrivent les API et les types SAPUI5. À l'aide de ces définitions, vous pouvez écrire des applications SAPUI5 en TypeScript et profiter de tous les avantages qui en découlent.

Les définitions de types SAPUI5 sont fournies via npm sous le nom @sapui5/types (publié directement par l'équipe de développement SAPUI5) et @types/openui5 (maintenu dans l'infrastructure DefinitelyTyped).

Fournir les définitions de type sous forme de package distinct vous permet de conserver une ancienne version des types lors de la mise à niveau du runtime SAPUI5, qui est l'une des options permettant d'atténuer les modifications incompatibles des types. Pour plus d’informations, consultez notre _[déclaration de compatibilité](https://sapui5.hana.ondemand.com/topic/a7ee9617bc794b6fad21e4df38e31128.html#loioa7ee9617bc794b6fad21e4df38e31128/section_CSTD)_.

## <span style="color:rgba(32, 144, 243, 1)">Compatibility Statement for the SAPUI5 Type Definitions</span>

Nous vous encourageons à utiliser SAPUI5 avec TypeScript pour une efficacité et une expérience de développement améliorées. TypeScript lui-même continue d'évoluer et nous essayons d'améliorer encore les définitions de type SAPUI5, de sorte qu'il pourrait y avoir des changements potentiellement incompatibles entre les versions des définitions de type. Cependant, de telles incompatibilités n'affecteraient que la compilation de votre code mais n'entraîneraient pas de problèmes d'exécution dans votre application. De plus, il existe différentes manières de les gérer facilement : vous pouvez, par exemple, simplement continuer à utiliser la version précédente des définitions de type avec un runtime SAPUI5 mis à jour. Pour plus d’informations, consultez Modifications récentes ci-dessous.

Les incompatibilités connues seront communiquées dans les _[notes de version SAPUI5-TypeScript](http://help.sap.com/disclaimer?site=https://sap.github.io/ui5-typescript/releasenotes.html)_, et dans les _[nouveautés de SAPUI5](https://sapui5.hana.ondemand.com/#/topic/99ac68a5b1c3416ab5c84c99fefa250d)_.

### <span style="color:rgba(32, 144, 243, 1)">Breaking changes</span>

SAPUI5 avec TypeScript est dans sa dernière étape de stabilité, alors n'hésitez pas à l'utiliser ! Cependant, des changements radicaux peuvent toujours se produire. Les raisons possibles sont :

- Correctifs dans la documentation de l'API qui provoquent des erreurs du compilateur TypeScript,

- Modifications dans TypeScript lui-même,

- Une amélioration significative d'une définition de type qui ne peut être obtenue qu'avec un changement radical,

- Un bug.

Pour plus d'informations, voir _[ici](http://help.sap.com/disclaimer?site=https://sap.github.io/ui5-typescript/beta-statement.html#why-will-there-still-be-breaking-changes-even-after-the-type-definitions-have-left-beta-stage)_.

Pour atténuer les modifications brutales, vous disposez de plusieurs options : certains d'entre eux sont répertoriés ici : _[Comment atténuer les modifications cassantes ?](http://help.sap.com/disclaimer?site=https://sap.github.io/ui5-typescript/beta-statement.html#how-to-mitigate-breaking-changes-within-as-well-as-after-beta-phase)_

#### Information(s) complémentaire(s)

- Documentation and resources: _[ SAPUI5 & TypeScript](http://help.sap.com/disclaimer?site=https://sap.github.io/ui5-typescript/)_

- Tutorial: _[Learn App Development in SAPUI5 and TypeScript](http://help.sap.com/disclaimer?site=https://github.com/SAP-samples/ui5-typescript-tutorial)_

- Consultez notre application de démonstration _[TypeScript To-Do List](https://sapui5.hana.ondemand.com/#/entity/sap.m.sample.TsTodos/sample/sap.m.sample.TsTodos.webapp)_, qui montre un exemple de configuration TypeScript pour le développement d'applications SAPUI5. Vous pouvez également _[exécuter les tests unitaires](https://sapui5.hana.ondemand.com/test-resources/sap/m/demokit/sample/TsTodos/test/unit/unitTests.qunit.html)_.

- Pour le développement de contrôles SAPUI5 dans TypeScript, consultez les _[directives TypeScript](https://sapui5.hana.ondemand.com/#/topic/192397d3cb954d4e986bcdc525c5205c)_.

_[npm]()_ Packages (consultez les packages individuels pour les informations de licence) :

- _[SAPUI type signatures sur npm](http://help.sap.com/disclaimer?site=https://www.npmjs.com/package/@sapui5/types)_

- _[OpenUI5 type signatures sur npm](http://help.sap.com/disclaimer?site=https://www.npmjs.com/package/@openui5/types)_