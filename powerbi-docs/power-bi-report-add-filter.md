---
title: Een filter toevoegen aan een rapport in Power BI
description: Een paginafilter, visualisatiefilter of rapportfilter aan rapport in Power BI toevoegen
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 06/25/2019
ms.author: maggies
LocalizationGroup: Reports
ms.openlocfilehash: 7cd2c7acbec9b8d21aeb78cbb159df2a46b12564
ms.sourcegitcommit: 58c649ec5fd2447a0f9ca4c4d45a0e9fff2f1b6a
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/27/2019
ms.locfileid: "67409768"
---
# <a name="add-a-filter-to-a-report-in-power-bi"></a>Een filter toevoegen aan een rapport in Power BI

In dit artikel wordt uitgelegd hoe u een paginafilter, visualisatiefilter, rapportfilter of drillthrough-filter toevoegt aan een rapport in Power BI. De voorbeelden in dit artikel hebben betrekking op de Power BI-service. De stappen zijn bijna identiek voor Power BI Desktop.

**Wist u dat?** Power BI heeft een nieuwe filterervaring die momenteel in preview is. Lees meer over de [nieuwe filterervaring in Power BI-rapporten](power-bi-report-filter-preview.md).

![Nieuwe filterfunctionaliteit](media/power-bi-report-add-filter/power-bi-filter-reading.png)

Power BI biedt een aantal verschillende soorten filters, van handmatige en automatische filters tot drillthrough en passthrough. Lees hier meer over de [verschillende soorten filters](power-bi-report-filter-types.md).

## <a name="filters-in-editing-view-or-reading-view"></a>Filters in de bewerkingsweergave of leesweergave
U kunt in twee verschillende weergaven werken met rapporten: Leesweergave en Bewerkingsweergave. De beschikbare filtermogelijkheden zijn afhankelijk van de weergave waarin u werkt. Zie [Over filters en markeren in Power BI-rapporten](power-bi-reports-filters-and-highlighting.md) voor uitgebreide informatie.

In dit artikel wordt beschreven hoe u filters maakt in de **bewerkingsweergave** voor rapporten.  Zie [deze snelstartgids](consumer/end-user-report-filter.md) voor meer informatie over filters in de leesweergave.

Omdat filters *behouden blijven* wanneer het rapport niet meer de focus heeft, behoudt Power BI gemaakte wijzigingen in het filter, de slicer en andere gegevensweergaven. U kunt dus verdergaan waar u bent gebleven wanneer u terugkeert naar het rapport. Als u uw filterwijzigingen niet wilt bewaren, selecteert u **Standaardinstelling herstellen** in de bovenste menubalk.

![de knop permanent filter](media/power-bi-report-add-filter/power-bi-reset-to-default.png)

## <a name="levels-of-filters-in-the-filters-pane"></a>Niveaus van filters in het deelvenster Filters
Zowel in Power BI Desktop als in de Power BI-service wordt het deelvenster Filters weergegeven aan de rechterkant van het rapportcanvas. Als het deelvenster niet wordt weergegeven, selecteert u het symbool '>' in de rechterbovenhoek om het deelvenster uit te vouwen.

U kunt filters instellen op drie verschillende niveaus voor het rapport: visualisatie, pagina en rapport. U kunt ook drillthrough-filters instellen. In dit artikel worden de verschillende niveaus uitgelegd.

![het deelvenster Filter in de leesweergave](media/power-bi-report-add-filter/power-bi-add-filter-reading-view.png)

## <a name="add-a-filter-to-a-visual"></a>Een filter aan een visualisatie toevoegen
U kunt op twee manieren een filter op het niveau van een visualisatie toevoegen aan een specifieke visualisatie. 

* Filter een veld dat al door de visualisatie wordt gebruikt.
* Zoek een veld dat nog niet door de visualisatie wordt gebruikt en voeg dit veld rechtstreeks toe aan de bucket **Filters op niveau van visuele elementen**.

In deze procedure wordt overigens het voorbeeld Retail Analysis gebruikt. U kunt dit voorbeeld downloaden om de stappen te volgen. Download het voorbeeld [Retail Analysis](sample-retail-analysis.md).

### <a name="filter-the-fields-in-the-visual"></a>De velden in de visualisatie filteren

1. Selecteer **Rapport bewerken** om het rapport in de bewerkingsweergave te openen.
   
   ![De knop Rapport bewerken](media/power-bi-report-add-filter/power-bi-edit-view.png)

2. Open het deelvenster Visualisaties en filters en het deelvenster Velden (indien nog gesloten).
   
   ![De deelvensters Visualisaties, Filters en Velden](media/power-bi-report-add-filter/power-bi-display-panes.png)
3. Selecteer een visueel element om het te activeren. Alle velden die door de visualisatie worden gebruikt, staan in het deelvenster **Velden** en ook in het deelvenster **Filters**, onder het kopje **Filters op niveau van visuele elementen**.
   
   ![Filters op visualisatieniveau selecteren](media/power-bi-report-add-filter/power-bi-default-visual-filter.png)
4. We gaan nu een filter toevoegen aan een veld dat al door de visualisatie wordt gebruikt. 
   
    Schuif omlaag naar het gebied **Filters op niveau van visuele elementen** en selecteer de pijl om het te filteren veld uit te vouwen. In dit voorbeeld filteren we het veld **StoreNumberName**.
     
    ![De pijl breidt het filter uit](media/power-bi-report-add-filter/power-bi-visual-level-filter.png) 
    
    Stel het filtertype in op **Standaardfilters toepassen**, **Geavanceerd filteren** of **Populairste N**. In dit voorbeeld gebruiken we standaardfilters om te zoeken naar **cha** en die vijf winkels te selecteren.
     
    ![Zoeken in standaardfilters](media/power-bi-report-add-filter/power-bi-search-filter.png) 
   
    Het visuele element wordt overeenkomstig het nieuwe filter gewijzigd. Als u het rapport met het filter opslaat, zien lezers van het rapport de gefilterde visualisatie en kunnen ze met het filter werken in de leesweergave door waarden te selecteren of te wissen.
     
    ![De gefilterde visualisatie](media/power-bi-report-add-filter/power-bi-search-visual-filter-results.png)

### <a name="filter-with-a-field-thats-not-in-the-visual"></a>Filteren met een veld dat niet is opgenomen in de visualisatie

Nu gaan we een nieuw veld aan de visualisatie toevoegen, als een filter op het niveau van visuele elementen.
   
1. Selecteer in het deelvenster Velden het veld dat u wilt toevoegen als een nieuw filter op het niveau van visuele elementen en sleep het veld naar het gebied **Filters op niveau van visuele elementen**.  In dit voorbeeld slepen we **District Manager** naar de bucket **Filters op niveau van visuele elementen**, zoeken we naar **an** en selecteren we die drie managers. 
     
    ![Een veld toevoegen aan het deelvenster Filters](media/power-bi-report-add-filter/power-bi-search-add-visual-filter.png)

    U ziet dat **District Manager** zelf *niet* aan de visualisatie wordt toegevoegd. De visualisatie bestaat nog steeds uit **WinkelNummerNaam** als de as en **Omzet van dit jaar** als de waarde.  
     
    ![Het veld bevindt zich niet in de visualisatie](media/power-bi-report-add-filter/power-bi-visualization.png)

    De visualisatie zelf wordt nu gefilterd om alleen de verkopen van de gefilterde managers voor de opgegeven winkels van dit jaar te laten zien.
     
    ![De gefilterde visualisatie](media/power-bi-report-add-filter/power-bi-search-visual-filter-results-2.png)

    Als u het rapport met dit filter opslaat, kunnen lezers van het rapport werken met het filter **District Manager** in de leesweergave door waarden te selecteren of te wissen.

## <a name="add-a-filter-to-an-entire-page"></a>Een filter toevoegen aan een hele pagina

U kunt ook een filter op paginaniveau toevoegen om een hele pagina te filteren.

1. Selecteer **Rapport bewerken** om het rapport in de bewerkingsweergave te openen.
   
   ![De knop Rapport bewerken](media/power-bi-report-add-filter/power-bi-edit-view.png)
2. Open het deelvenster Visualisaties en filters en het deelvenster Velden (indien nog gesloten).
3. Selecteer in het deelvenster Velden het veld dat u wilt toevoegen als een nieuw filter op paginaniveau en sleep het veld naar het gebied **Filters op paginaniveau**.  
4. Selecteer de waarden die u wilt filteren en stel het filtertype in op **Standaardfilters toepassen** of **Geavanceerd filteren**.
   
   Alle visualisaties op de pagina worden opnieuw getekend om de wijziging te weerspiegelen.
   
   ![Een filter toevoegen en waarden selecteren](media/power-bi-report-add-filter/filterpage.gif)

    Als u het rapport met het filter opslaat, kunnen lezers van het rapport met het filter werken in de leesweergave door waarden te selecteren of te wissen.

## <a name="add-a-drillthrough-filter"></a>Een drillthrough-filter toevoegen
Met drillthrough in Power BI-service en Power BI Desktop kunt u een *doelpagina* voor uw rapport maken die zich op een bepaalde entiteit richt, zoals een leverancier, klant of fabrikant. Gebruikers kunnen nu vanaf de andere rapportpagina's met de rechtermuisknop op een gegevenspunt voor die entiteit klikken en inzoomen op de betreffende pagina.

### <a name="create-a-drillthrough-filter"></a>Een drillthrough-filter maken
Als u de stappen zelf wilt uitvoeren, downloadt u het bestand [Customer Profitability Sample](sample-customer-profitability.md). Stel dat u een pagina wilt die zich richt op leidinggevende, zakelijke gebieden.

1. Selecteer **Rapport bewerken** om het rapport in de bewerkweergave te openen.
   
   ![De knop Rapport bewerken](media/power-bi-report-add-filter/power-bi-edit-view.png)

1. Voeg een nieuwe pagina aan het rapport toe en geef deze de naam **Leidinggevend team**. Deze pagina wordt het drillthrough-*doel*.
2. Voeg visualisaties toe die belangrijke metrische gegevens voor de bedrijfstakken van het leidinggevend team volgen.    
3. Voeg ook **Leidinggevende > Naam leidinggevende** toe aan de drillthrough-filters.    
   
    ![Een waarde toevoegen aan drillthrough-filters](media/power-bi-report-add-filter/power-bi-drillthrough-filter.png)
   
    Er wordt een pijl Vorige aan de rapportpagina toegevoegd.  Als een gebruiker deze pijl Vorige selecteert, wordt hij of zij teruggestuurd naar de *oorspronkelijke* rapportpagina - de pagina waarop voor drillthrough is gekozen. De pijl Vorige werkt alleen in de leesweergave.
   
     ![De pijl Terug](media/power-bi-report-add-filter/power-bi-back-arrow.png)

### <a name="use-the-drillthrough-filter"></a>Het drillthrough-filter gebruiken
We gaan nu kijken hoe het drillthrough-filter werkt.

1. Begin op de rapportpagina **Team Scorecard**.    
2. Stel dat u Andrew Ma bent en u wilt de rapportpagina Leidinggevend team filteren met slechts uw eigen gegevens.  Klik in het diagram in het gebied linksboven op een groene gegevenspunt om de menuoptie Drillthrough te openen.
   
    ![De drillthrough-actie starten](media/power-bi-report-add-filter/power-bi-drillthrough.png)
3. Selecteer **Drillthrough > Leidinggevend team** om in te zoomen op de rapportpagina met de naam **Leidinggevend team**. De pagina wordt gefilterd en er wordt informatie weergegeven over het gegevenspunt waarop u met de rechtermuisknop hebt geklikt, in dit geval Andrew Ma. Alleen het veld in de verdieping Drillthrough-filters wordt doorgegeven aan de drillthrough-pagina van het rapport.  
   
    ![De drillthrough-actie selecteren](media/power-bi-report-add-filter/power-bi-drillthrough-executive.png)

## <a name="add-a-report-level-filter-to-filter-an-entire-report"></a>Een filter op rapportniveau toevoegen om een rapport volledig te filteren

1. Selecteer **Rapport bewerken** om het rapport in de bewerkweergave te openen.
   
   ![De knop Rapport bewerken](media/power-bi-report-add-filter/power-bi-edit-view.png)

2. Open het deelvenster Visualisaties en filters en het deelvenster Velden, indien deze nog niet zijn geopend.
3. Selecteer in het deelvenster Velden het veld dat u wilt toevoegen als een nieuw filter op rapportniveau en sleep het veld naar het gebied **Filters op rapportniveau**.  
4. Selecteer de waarden die u wilt filteren.

    De visuele elementen op de actieve pagina (en ook op alle andere pagina's van het rapport) worden gewijzigd overeenkomstig het nieuwe filter. Als u het rapport met het filter opslaat, kunnen lezers van het rapport met het filter werken in de leesweergave door waarden te selecteren of te wissen.

1. Selecteer de pijl Vorige om terug te keren naar de vorige rapportpagina.

## <a name="considerations-and-troubleshooting"></a>Aandachtspunten en probleemoplossing

- Er zijn situaties waarin het filter op visueel niveau en op paginaniveau verschillende resultaten kunnen geven.  Als u bijvoorbeeld een filter op visueel niveau toevoegt, wordt er door Power BI gefilterd op de geaggregeerde resultaten.  De standaardaggregatie is Som, maar u kunt [het samenvoegingstype wijzigen](service-aggregates.md) (Engelstalig).  

    Als u vervolgens een filter op paginaniveau toevoegt, wordt er door Power BI zonder aggregeren gefilterd.  Er wordt niet geaggregeerd, omdat een pagina veel visuals kan bevatten die allemaal verschillende aggregatietypen hanteren.  Het filter wordt dus op elke gegevensrij toegepast.

- Als u het deelvenster Velden niet ziet, controleer dan of u in de [bewerkingsweergave](service-interact-with-a-report-in-editing-view.md) voor rapporten zit    
- Als u veel wijzigingen in de filters hebt aangebracht en wilt terugkeren naar de standaardinstellingen van de auteur van het rapport, selecteert u **Standaardinstelling herstellen** in de bovenste menubalk.

## <a name="next-steps"></a>Volgende stappen
[Rondleiding door het deelvenster Filters van het rapport](consumer/end-user-report-filter.md)

[Filters en markeren in rapporten](power-bi-reports-filters-and-highlighting.md)

[Verschillende soorten filters in Power BI](power-bi-report-filter-types.md)

Hebt u nog vragen? [Misschien dat de Power BI-community het antwoord weet](http://community.powerbi.com/)

