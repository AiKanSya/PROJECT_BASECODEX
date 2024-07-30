[![](../../RESSOURCES/LOGOS/LOGO_STMS_001.png)](../../README.md)

# <span style="color:rgba(32, 144, 243, 1)">VISUAL DEGRADATIONS</span>

Les sections suivantes donnent un aperçu des dégradations connues.

## <span style="color:rgba(32, 144, 243, 1)">sap.m.TextArea: Placeholder Property</span>

Comme il n’existe aucune spécification du W3C sur la manière d’utiliser la propriété placeholder, la gestion de cette propriété par le navigateur varie. Certains navigateurs utilisent une propriété d'espace réservé native, mais pour les navigateurs qui ne la prennent pas en charge, SAP implémente sa propre version d'espace réservé.

``sap.m.TextArea`` est un contrôle multiligne et se comporte différemment selon le navigateur :

| BROWSER             | SITUATION                                                                                                                                                         |
|---------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ``Google Chrome``   | Google Chrome supports the native placeholder property and displays multiple lines along with a scrollbar ![](./RESSOURCES/02_VISUAL_DEGRADATIONS_001.png)        |
| ``Mozilla Firefox`` | Mozilla Firefox supports the native placeholder property but does not display a scrollbar or an ellipsis, instead it simply truncates the placeholder text string ![](./RESSOURCES/02_VISUAL_DEGRADATIONS_002.png) |