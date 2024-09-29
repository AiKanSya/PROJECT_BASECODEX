# CREATION APPLICATION UI5

## BACKEND

<details>
    <summary>CREATION - UI5 SUPERPACKAGE</summary>

- ``SE80`` - Création du package UI5 ``ZFGI_UI5`` en tant que Superpackage.

    Par convention, un ``Superpackage UI5`` est créé par module (i.e ``ZLOG``, ``ZMM``, ``ZFI``, ...). Ce dernier contiendra des packages spécifiques pour chaque ``App``.
    
    Dans l'exemple ci-dessous, le Package ``ZFGI_UI5`` sera le "Super" ``Superpackage`` de l'enemble de nos tests. Il contiendra plusieurs ``Superpackage`` (un pour chaque module) qui contiendront à leur tour un à plusieurs packages pour chaque App concerné par ce module.

    ![](../RESSOURCES/00_CREATE_APP_001.jpg)

    ![](../RESSOURCES/00_CREATE_APP_002.jpg)

    ![](../RESSOURCES/00_CREATE_APP_003.jpg)

    ![](../RESSOURCES/00_CREATE_APP_004.jpg)

    ![](../RESSOURCES/00_CREATE_APP_005.jpg)
  
</details>

<details>
    <summary>CREATION - UI5 MODULE PACKAGE</summary>

- ``SE80`` - Création du package UI5 ``ZFGI_UI5_LOG`` en tant que package pour le module EWM.

    ![](../RESSOURCES/00_CREATE_APP_006.jpg)

    ![](../RESSOURCES/00_CREATE_APP_007.jpg)

    ![](../RESSOURCES/00_CREATE_APP_008.jpg)
  
</details>

<details>
    <summary>CREATION - UI5 APP PACKAGE</summary>

- ``SE80`` - Création du package UI5 ``ZFGI_UI5_LOG_PALETTE`` en tant que package pour le module EWM.

    ![](../RESSOURCES/00_CREATE_APP_009.jpg)

    ![](../RESSOURCES/00_CREATE_APP_010.jpg)

    ![](../RESSOURCES/00_CREATE_APP_011.jpg)
  
</details>

<details>
    <summary>CREATION - GATEWAY</summary>

- ``SEGW`` - Création de la Gateway ``ZLOG_PALETTE_PAN``

    ![](../RESSOURCES/00_CREATE_APP_012.jpg)

    ![](../RESSOURCES/00_CREATE_APP_013.jpg)

    ![](../RESSOURCES/00_CREATE_APP_014.jpg)

    ![](../RESSOURCES/00_CREATE_APP_015.jpg)

    ![](../RESSOURCES/00_CREATE_APP_016.jpg)

    ![](../RESSOURCES/00_CREATE_APP_017.jpg)
  
</details>

<details>
    <summary>ACTIVATION - SERVICE</summary>

- ``/IWFND/MAINT_SERVICE`` - Activation du Service ``ZLOG_PALETTE_PAN``

    ![](../RESSOURCES/00_CREATE_APP_018.jpg)

    ![](../RESSOURCES/00_CREATE_APP_019.jpg)

    ![](../RESSOURCES/00_CREATE_APP_020.jpg)

    ![](../RESSOURCES/00_CREATE_APP_021.jpg)

    ![](../RESSOURCES/00_CREATE_APP_022.jpg)

    ![](../RESSOURCES/00_CREATE_APP_023.jpg)
  
</details>

<details>
    <summary>CHECK - SERVICE</summary>

- ``SE10`` - Vérification

    ![](../RESSOURCES/00_CREATE_APP_024.jpg)
  
</details>

## GITLAB

<details>
    <summary>CREATION - REPOSITORY</summary>

- ``GITLAB`` - Création du repository ``ZLOG_PALETTE_PAN``

    ![](../RESSOURCES/00_CREATE_APP_038.jpg)

    ![](../RESSOURCES/00_CREATE_APP_039.jpg)

    ![](../RESSOURCES/00_CREATE_APP_040.jpg)

    ![](../RESSOURCES/00_CREATE_APP_041.jpg)
  
</details>

## FRONTEND

<details>
    <summary>NAVIGATION - BTP COCKPIT</summary>

- ``SAP BUSINESS APPLICATION STUDIO`` - Création Destination & Dev Space ``ZLOG_PALETTE_PAN``

    ![](../RESSOURCES/00_CREATE_APP_029.jpg)
  
</details>

<details>
    <summary>CREATION - DESTINATIONS</summary>

- ``SAP BUSINESS TO PARTNER COCKPIT`` - Navigation vers le BAS

    ![](../RESSOURCES/00_CREATE_APP_035.jpg)

    ![](../RESSOURCES/00_CREATE_APP_036.jpg)
  
</details>

<details>
    <summary>CREATION - DEV SPACE</summary>

- ``SAP BUSINESS TO PARTNER COCKPIT`` - Navigation vers le BAS

    ![](../RESSOURCES/00_CREATE_APP_030.jpg)

    ![](../RESSOURCES/00_CREATE_APP_031.jpg)

    ![](../RESSOURCES/00_CREATE_APP_032.jpg)

    ![](../RESSOURCES/00_CREATE_APP_033.jpg)

    Additional SAP Extensions:

    - 	HTML5 Application Template
    -   Launchpad Module
    -   Development Tools for SAP Build Work Zone

    ![](../RESSOURCES/00_CREATE_APP_034.jpg)
  
</details>

<details>
    <summary>CREATION - PROJECT</summary>

- ``SAP BUSINESS APPLICATION STUDIO`` - Création du projet ``palettisationpan``

    ![](../RESSOURCES/00_CREATE_APP_042.jpg)

    ![](../RESSOURCES/00_CREATE_APP_043.jpg)

    ![](../RESSOURCES/00_CREATE_APP_044.jpg)

    ![](../RESSOURCES/00_CREATE_APP_045.jpg)

    Select Template and Target Location

    ![](../RESSOURCES/00_CREATE_APP_046.jpg)

    ![](../RESSOURCES/00_CREATE_APP_037.jpg)

    ![](../RESSOURCES/00_CREATE_APP_050.jpg)

</details>

<details>
    <summary>CONFIGURATION - MANDANT DEV100/TEST120</summary>

- ``SAP BUSINESS APPLICATION STUDIO`` - Création du projet ``palettisationpan``

    ![](../RESSOURCES/00_CREATE_APP_047.jpg)

    ![](../RESSOURCES/00_CREATE_APP_048.jpg)

</details>

<details>
    <summary>BIND - GITLAB</summary>

- ``SAP BUSINESS APPLICATION STUDIO`` - Lier le projet au repository ``palettisationpan``

    ![](../RESSOURCES/00_CREATE_APP_049.jpg)

    Process:

    - Stage all & Commit
    - Paste repository url
    - Enter username & password

</details>