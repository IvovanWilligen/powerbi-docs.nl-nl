---
title: Rapporten maken die zijn geoptimaliseerd voor de mobiele Power BI-apps
description: Informatie over het optimaliseren van rapportpagina's in Power BI Desktop voor de mobiele Power BI-apps.
services: powerbi
documentationcenter: 
author: maggiesMSFT
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 12/08/2017
ms.author: maggies
ms.openlocfilehash: 0dd906bc1b165793e9ff91f64324eeb8e1d1266c
ms.sourcegitcommit: b780b7108fd9b52398b8377b52836f0e0fedc96e
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/09/2017
---
# <a name="create-reports-optimized-for-the-power-bi-phone-apps"></a>Rapporten maken die zijn geoptimaliseerd voor de mobiele Power BI-apps
Wanneer u [een rapport maakt in Power BI Desktop](desktop-report-view.md) kunt u de ervaring van het gebruik van dit rapport in de mobiele Power BI-apps verbeteren door een versie van het rapport specifiek voor de telefoon te maken. Voor een optimale ervaring kunt u uw rapport voor de telefoon aanpassen door visuele elementen te rangschikken en de grootte ervan te wijzigen, en mogelijk niet alle op te nemen. Ook kunt u [*responsieve*visuals](#optimize-a-visual-for-any-size) en [responsieve slicers](#enhance-slicers-to-to-work-well-in-phone-reports) maken waarvan de grootte goed kan worden gewijzigd voor weergave op een telefoon. Als u filters aan uw rapport toevoegt, worden deze filters bovendien automatisch in het telefoonrapport weergegeven. De lezers van uw rapport kunnen deze filters zien en het rapport ermee filteren.

![Geoptimaliseerd rapport op een telefoon](media/desktop-create-phone-report/07-power-bi-phone-report-portrait.png)

## <a name="lay-out-a-report-page-for-the-phone-in-power-bi-desktop"></a>Een rapportpagina indelen voor de telefoon in Power BI Desktop
Nadat u [een rapport in Power BI Desktop hebt gemaakt](desktop-report-view.md), kunt u dit optimaliseren voor telefoons.

1. Selecteer in Power BI Desktop **Rapportweergave** in de linkernavigatiebalk.
   
    ![Het pictogram Rapportweergave](media/desktop-create-phone-report/pbi_reportviewinpbidesigner_changeview.png)
2. Selecteer op het tabblad **Beeld** de optie **Telefoonindeling**.  
   
    ![Het pictogram Telefoonindeling](media/desktop-create-phone-report/power-bi-phone-layout-icon.png)
   
    U ziet een leeg telefooncanvas. Alle visuele elementen op de oorspronkelijke rapportpagina worden weergegeven in het deelvenster Visualisaties aan de rechterkant.
3. Als u een visueel element aan de telefoonindeling wilt toevoegen, sleept u het vanuit het deelvenster Visualisaties naar het telefooncanvas.
   
    Telefoonrapporten maken gebruik van een rasterindeling. Wanneer u visuele elementen naar het canvas voor mobiele telefoons versleept, worden ze met dat raster uitgelijnd.
   
    ![Een visueel element slepen en neerzetten](media/desktop-create-phone-report/02_dragging_and_droping_a_vis.gif)
   
    U kunt enkele of alle visuele elementen van de hoofdrapportpagina toevoegen aan de rapportpagina voor de telefoon. U kunt elk visuele element slechts één keer toevoegen.
4. U kunt de grootte van de visuele elementen in het raster wijzigen, op dezelfde manier als u voor tegels in dashboards en mobiele dashboards doet.
   
   > [!NOTE]
   > De schaal van het telefoonrapportraster kan worden aangepast aan telefoons van verschillende groottes. Uw rapport ziet er dus goed uit op telefoons met een klein scherm en telefoons met een groot scherm.
   > 
   > 
   
   ![De grootte van een visueel element aanpassen](media/desktop-create-phone-report/03_resizing_a_viz_to_grid.gif)

## <a name="optimize-a-visual-for-any-size"></a>Een visueel element optimaliseren voor elke grootte
U kunt de visuele elementen in uw dashboard of rapport zodanig instellen dat ze *responsief* zijn. Dat wil zeggen dat ze dynamisch worden gewijzigd zodat ze de maximale hoeveelheid gegevens weergeven, ongeacht de schermgrootte. 

Als de grootte van een visueel element verandert, geeft Power BI de prioriteit aan de gegevensweergave, bijvoorbeeld door automatisch de opvulling te verwijderen en de legenda naar de bovenkant van het visuele element te verplaatsen, zodat het visuele element ook als het kleiner wordt informatief blijft.

![Reactietijd bij het wijzigen van de grootte van visuele elementen](media/desktop-create-phone-report/power-bi-responsive-visual.gif)

U kiest voor elk visueel element of u reactietijd wilt inschakelen. Lees meer over [het optimaliseren visuele elementen](desktop-create-responsive-visuals.md).

## <a name="considerations-when-creating-phone-report-layouts"></a>Overwegingen bij het maken van telefoonrapportindelingen
* U kunt alle pagina's of slechts enkele optimaliseren voor rapporten met meerdere pagina's. 
* Als u een achtergrondkleur voor een rapportpagina hebt gedefinieerd, heeft het telefoonrapport dezelfde achtergrondkleur.
* U kunt de opmaakinstellingen niet alleen voor de telefoon wijzigen. De opmaak is consistent tussen de hoofd- en mobiele indeling. Tekengrootten zijn bijvoorbeeld hetzelfde.
* Als u een visueel element wilt wijzigen, bijvoorbeeld de opmaak, gegevensset, filters of een ander kenmerk, keert u terug naar de normale rapportontwerpmodus.
* Power BI biedt standaardtitels en -paginanamen voor telefoonrapporten in de mobiele app. Als u visuele tekstelementen voor titels en paginanamen in uw rapport hebt gemaakt, kunt u overwegen deze niet aan uw telefoonrapporten toe te voegen.     

## <a name="remove-a-visual-from-the-phone-layout"></a>Een visueel element verwijderen uit de telefoonindeling
* Als u een visueel element wilt verwijderen, klikt u op de X in de rechterbovenhoek van het visuele element op het telefooncanvas of selecteert u het en drukt u op **Verwijderen**.
  
   Als u het visuele element hier verwijdert, wordt het alleen uit het canvas van de telefoonindeling verwijderd. Het visuele element en het originele rapport worden niet beïnvloed.
  
   ![Een visueel element verwijderen](media/desktop-create-phone-report/05_removing_a_vis.gif)

## <a name="enhance-slicers-to-to-work-well-in-phone-reports"></a>Slicers verbeteren zodat ze goed werken in telefoonrapporten
Met slicers kunt u rapportgegevens op het canvas filteren. Wanneer u slicers ontwerpt in de normale rapportontwerpmodus, kunt u enkele slicerinstellingen wijzigen zodat ze beter geschikt zijn voor gebruik in telefoonrapporten:

* Besluit of rapportlezers slechts één of meer dan één item kunnen selecteren.
* Plaats een vak rond de slicer om het rapport gemakkelijker te kunnen scannen.
* Maak de slicer verticaal, horizontaal of *responsief*. 

Als u de slicer responsief maakt, worden er meer of minder opties weergegeven wanneer u het formaat en de vorm wijzigt. Hij kan lang, kort, breed of smal zijn. Als u de slicer klein genoeg maakt, wordt op de rapportpagina alleen nog een filterpictogram weergegeven. 

![Power BI responsieve slicer](media/desktop-create-phone-report/power-bi-slicer-2-rows.png)

Lees meer over [responsieve slicers maken](power-bi-slicer-filter-responsive.md).

## <a name="publish-a-phone-report"></a>Een telefoonrapport publiceren
* Als u de telefoonversie van een rapport wilt publiceren, [publiceert u het hoofdrapport van de Power BI Desktop naar de Power BI Desktop-service](desktop-upload-desktop-files.md). De telefoonversie wordt dan op hetzelfde moment gepubliceerd.
  
    Lees meer over [delen en machtigingen in Power BI](service-how-to-collaborate-distribute-dashboards-reports.md).

## <a name="view-optimized-and-unoptimized-reports-on-a-phone"></a>Geoptimaliseerde en niet-geoptimaliseerde rapporten weergeven op een telefoon
In de mobiele apps op telefoons worden geoptimaliseerde en niet-geoptimaliseerde telefoonrapporten automatisch door Power BI gedetecteerd. Als een voor de telefoon geoptimaliseerd rapport bestaat, opent de Power BI-telefoon-app het rapport automatisch in de rapportmodus voor de telefoon.

Als er geen voor de telefoon geoptimaliseerd rapport bestaat, wordt het rapport geopend in de niet-geoptimaliseerde liggende weergave.  

Wanneer u een telefoonrapport hebt geopend en u de richting van de telefoon wijzigt naar liggend, wordt het rapport in de niet-geoptimaliseerde weergave geopend met de oorspronkelijke rapportindeling, of het rapport nu wel of niet is geoptimaliseerd.

Als u slechts enkele pagina’s optimaliseert, zien lezers een bericht in de portretweergave met de mededeling dat het rapport in de liggende modus beschikbaar is.

![Niet-geoptimaliseerde telefoonpagina](media/desktop-create-phone-report/06-power-bi-phone-report-page-not-optimized.png)

Rapportlezers kunnen hun telefoon zijdelings houden om de pagina in de liggende modus te bekijken. Lees meer over het [gebruiken van voor uw telefoon geoptimaliseerde Power BI-rapporten](mobile-apps-view-phone-report.md).

## <a name="next-steps"></a>Volgende stappen
* [Een telefoonweergave van een dashboard maken in Power BI](service-create-dashboard-mobile-phone-view.md)
* [Voor uw telefoon geoptimaliseerde Power BI-rapporten weergeven](mobile-apps-view-phone-report.md)
* [Responsieve visuele elementen maken die zijn geoptimaliseerd voor elke grootte](desktop-create-responsive-visuals.md)
* Hebt u nog vragen? [Misschien dat de Power BI-community het antwoord weet](http://community.powerbi.com/)
