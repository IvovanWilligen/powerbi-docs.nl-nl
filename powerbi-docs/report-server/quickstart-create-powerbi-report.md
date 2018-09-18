---
title: Een Power BI-rapport maken voor Power BI Report Server
description: Leer hoe u in een paar eenvoudige stappen een Power BI-rapport voor Power BI Report Server maakt.
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-report-server
ms.topic: conceptual
ms.date: 05/18/2018
ms.author: maggies
ms.openlocfilehash: 64757d6cbd82b666bf18f1ee87d8e51954872990
ms.sourcegitcommit: 67336b077668ab332e04fa670b0e9afd0a0c6489
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/12/2018
ms.locfileid: "44726726"
---
# <a name="create-a-power-bi-report-for-power-bi-report-server"></a>Een Power BI-rapport maken voor Power BI Report Server
U kunt Power BI-rapporten on-premises opslaan en beheren in de webportal van Power BI Report Server, net zoals u Power BI-rapporten kunt opslaan in de cloud in de Power BI-service (https://powerbi.com)). U maakt rapporten in Power BI Desktop en publiceert deze naar de webportal. Gebruikers in uw organisatie kunnen de rapporten weergeven in een browser of in een mobiele Power BI-app op een mobiele apparaat.

![Power BI-rapport in de webportal](media/quickstart-create-powerbi-report/report-server-powerbi-report.png)

Nu volgen vier snelle stappen om u op weg te helpen.

## <a name="step-1-install-power-bi-desktop-optimized-for-power-bi-report-server"></a>Stap 1: voor Power BI Report Server geoptimaliseerde versie van Power BI Desktop installeren

Als u al Power BI-rapporten hebt gemaakt in Power BI Desktop, bent u bijna klaar om Power BI-rapporten te maken voor Power BI Report Server. Het is raadzaam om de versie van Power BI Desktop te installeren die is geoptimaliseerd voor Power BI Report Server, zodat u zeker weet dat de server en app altijd zijn gesynchroniseerd. U kunt beide versies van Power BI Desktop op dezelfde computer installeren.

1. Selecteer in de webportal voor rapportserver de pijl **Downloaden** > **Power BI Desktop**.

    ![Power BI Desktop downloaden van de webportal](media/quickstart-create-powerbi-report/report-server-download-web-portal.png)

    U kunt ook rechtstreeks naar [Microsoft Power BI Desktop](https://www.microsoft.com/download/details.aspx?id=56723) (geoptimaliseerd voor Power BI Report Server, maart 2018) gaan in het Microsoft Downloadcentrum.

2. Selecteer **Downloaden** in het downloadcentrum.

3. Selecteer het volgende, afhankelijk van uw computer:

    - **PBIDesktopRS.msi** (de 32-bits versie) of

    - **PBIDesktopRS_x64.msi** (de 64-bits versie).

4. Nadat u het installatieprogramma hebt gedownload, voert u de installatiewizard van Power BI Desktop (maart 2018) uit.

2. Selecteer aan het einde van de installatie de optie **Power BI Desktop nu starten**.
   
    Het programma wordt automatisch gestart en u kunt aan de slag. U hebt de juiste versie als 'Power BI Desktop (maart 2018)' wordt vermeld in de titelbalk.

    ![Power BI Desktop-versie van maart 2018](media/quickstart-create-powerbi-report/report-server-desktop-march-2018.png)

3. Als u niet bekend bent met Power BI Desktop, is het misschien een goed idee om de video's op het welkomstscherm te bekijken.
   
    ![Welkomstscherm van Power BI Desktop](media/quickstart-create-powerbi-report/report-server-powerbi-desktop-start.png)

## <a name="step-2-select-a-data-source"></a>Stap 2: Een gegevensbron selecteren
U kunt verbinding maken met allerlei gegevensbronnen. Lees hier meer informatie over [het maken van verbinding met gegevensbronnen](connect-data-sources.md) (Engelstalig).

1. Selecteer **Gegevens ophalen** op het welkomstscherm.
   
    U kunt de optie **Gegevens ophalen** ook selecteren op het tabblad **Start**.
2. Selecteer uw gegevensbron, in dit voorbeeld **Analysis Services**.
   
    ![Gegevensbron selecteren](media/quickstart-create-powerbi-report/report-server-get-data-ssas.png)
3. Voer een waarde in voor **Server** en eventueel voor **Database**. Zorg ervoor dat **Live verbinding maken** is geselecteerd > **OK**.
   
    ![Servernaam](media/quickstart-create-powerbi-report/report-server-ssas-server-name.png)
4. Kies de rapportserver waarop u de rapporten wilt opslaan.
   
    ![Rapportserver selecteren](media/quickstart-create-powerbi-report/report-server-select-server.png)

## <a name="step-3-design-your-report"></a>Stap 3: Het rapport ontwerpen
Nu wordt het pas echt leuk. U gaat de visualisaties of visuele elementen maken die uw gegevens het best illustreren.

U kunt bijvoorbeeld een trechterdiagram maken van klanten en waarden groeperen op jaarlijkse omzet.

![Een rapport ontwerpen](media/quickstart-create-powerbi-report/report-server-create-funnel.png)

1. Selecteer **Trechterdiagram** bij **Visualisaties**.
2. Sleep het veld dat moet worden geteld naar het vak **Waarden**. Als het niet een numeriek veld is, wordt het type waarde automatisch gewijzigd in *Aantal van*.
3. Sleep het veld waarop u wilt groeperen naar het vak **Groep**.

Hier kunt u nog veel meer lezen over [het ontwerpen van een Power BI-rapport](../desktop-report-view.md).

## <a name="step-4-save-your-report-to-the-report-server"></a>Stap 4: Het rapport opslaan op de rapportserver
Wanneer uw rapport klaar is, kunt u het opslaan op de Power BI-rapportserver die u hebt gekozen in stap 2.

1. Selecteer in het menu **Bestand** de optie **Opslaan als** > **Power BI Report Server**.
   
    ![Opslaan op de rapportserver](media/quickstart-create-powerbi-report/report-server-save-as-powerbi-report-server.png)
2. Nu kunt u het rapport bekijken in de webportal.
   
    ![Het rapport bekijken in de webportal](media/quickstart-create-powerbi-report/report-server-powerbi-report.png)

## <a name="considerations-and-limitations"></a>Overwegingen en beperkingen
Rapporten in Power BI Report Server en in de Power BI-service (http://powerbi.com)) werken bijna exact dezelfde, op een paar functies na.

### <a name="in-a-browser"></a>In een browser
Rapporten voor Power BI Report Server ondersteunen alle visualisaties, met inbegrip van:

* Aangepaste visualisaties

Rapporten voor Power BI Report Server bieden geen ondersteuning voor:

* R-visuals
* ArcGIS-kaarten
* Breadcrumbs
* Preview-functies in Power BI Desktop

### <a name="in-the-power-bi-mobile-apps"></a>In de mobiele Power BI-apps
Rapporten voor Power BI Report Server ondersteunen alle basisfunctionaliteit in de [mobiele Power BI-apps](../consumer/mobile/mobile-apps-for-mobile-devices.md), waaronder:

* [Indeling van telefoonrapport](../desktop-create-phone-report.md): u kunt een rapport optimaliseren voor de mobiele Power BI-apps. Op uw mobiele telefoon hebben geoptimaliseerde rapporten een speciaal pictogram, ![Het pictogram Geoptimaliseerd Power BI-rapport](media/quickstart-create-powerbi-report/power-bi-rs-mobile-optimized-icon.png), en een speciale indeling.
  
    ![Rapporten geoptimaliseerd voor telefoons](media/quickstart-create-powerbi-report/power-bi-rs-mobile-optimized-report.png)

Rapporten voor Power BI Report Server bieden geen ondersteuning voor deze functies in de mobiele Power BI-apps:

* R-visuals
* ArcGIS-kaarten
* Aangepaste visualisaties
* Breadcrumbs
* Geofiltering van streepjescodes

## <a name="next-steps"></a>Volgende stappen
### <a name="power-bi-desktop"></a>Power BI Desktop
Er zijn heel interessante informatiebronnen voor het maken van rapporten in Power BI Desktop. Deze koppeling is een goed startpunt.

* [Aan de slag met Power BI Desktop](../desktop-getting-started.md)
* Zelfstudie: [Aan de slag met Power BI Desktop](../guided-learning/gettingdata.yml?tutorial-step=2)

### <a name="power-bi-report-server"></a>Power BI Report Server
* [Voor Power BI Report Server geoptimaliseerde versie van Power BI Desktop installeren](install-powerbi-desktop.md)  
* [Wat is Power BI Report Server?](get-started.md)  

Hebt u nog vragen? [Misschien dat de Power BI-community het antwoord weet](https://community.powerbi.com/)
