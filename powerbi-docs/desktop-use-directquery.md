---
title: DirectQuery in Power BI Desktop gebruiken
description: DirectQuery (ook wel een liveverbinding genoemd) in Power BI Desktop gebruiken
services: powerbi
documentationcenter: 
author: davidiseminger
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
ms.date: 12/25/2017
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: ec124ef4ae34b064e217b3ce646a329d538e4214
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/24/2018
---
# <a name="use-directquery-in-power-bi-desktop"></a>DirectQuery in Power BI Desktop gebruiken
Wanneer u in **Power BI Desktop** verbinding maakt met een gegevensbron, kunt u altijd een kopie van de gegevens in **Power BI Desktop** importeren. Voor sommige gegevensbronnen kunt u ook rechtstreeks verbinding maken met de gegevensbron via **DirectQuery**.

## <a name="supported-data-sources"></a>Ondersteunde gegevensbronnen
Zie [Gegevensbronnen die worden ondersteund door DirectQuery](desktop-directquery-data-sources.md) voor een volledige lijst van gegevensbronnen die worden ondersteund door **DirectQuery**.

## <a name="how-to-connect-using-directquery"></a>Verbinding maken met DirectQuery
Als u **Gegevens ophalen** gebruikt om verbinding te maken met een gegevensbron die wordt ondersteund door **DirectQuery**, kunt u in het verbindingsvenster selecteren hoe u verbinding wilt maken.  

![](media/desktop-use-directquery/directquery_2a.png)

Dit zijn de verschillen tussen **Importeren** en **DirectQuery**:

**Importeren**: de geselecteerde tabellen en kolommen worden geïmporteerd in **Power BI Desktop**. Als u een visualisatie maakt of ermee werkt, wordt in **Power BI Desktop** gebruikgemaakt van de geïmporteerde gegevens. U moet de gegevens vernieuwen om te zien welke wijzigingen zijn doorgevoerd in de onderliggende gegevens na de eerste importbewerking of de meest recente vernieuwing. Hierbij wordt de hele gegevensset opnieuw geïmporteerd.

**DirectQuery**: er worden geen gegevens geïmporteerd in of gekopieerd naar **Power BI Desktop**. Voor relationele bronnen worden de geselecteerde tabellen en kolommen weergegeven in de lijst **Velden**. Voor multidimensionale bronnen, zoals SAP Business Warehouse, worden de dimensies en metingen van de geselecteerde kubus weergegeven in de lijst **Velden**. Als u een visualisatie maakt of ermee werkt, wordt in **Power BI Desktop** een query op de onderliggende gegevensbron uitgevoerd. De weergegeven gegevens zijn dus altijd de actuele gegevens.

Er zijn veel gegevensmodellen en gegevenstransformaties beschikbaar voor **DirectQuery**, met enige beperkingen. Wanneer u een visualisatie maakt of ermee werkt, moet de onderliggende gegevens van de gegevensbron worden opgevraagd. De benodigde tijd voor het vernieuwen van de visualisatie is afhankelijk van de prestaties van de onderliggende gegevensbron. Wanneer de benodigde gegevens voor de aanvraag recentelijk zijn opgevraagd, worden in Power BI Desktop de recente gegevens gebruikt zodat de visualisatie sneller wordt weergegeven. Selecteer **Vernieuwen** in het lint **Start** als u er zeker van wilt zijn dat alle visualisaties worden vernieuwd met de actuele gegevens.

Zie het artikel [Power BI en DirectQuery](desktop-directquery-about.md) voor een gedetailleerde beschrijving van **DirectQuery**. Zie ook de volgende secties voor meer informatie over de voordelen en beperkingen en belangrijke overwegingen bij het gebruik van **DirectQuery**.

## <a name="benefits-of-using-directquery"></a>Voordelen van het gebruik van DirectQuery
Het gebruik van **DirectQuery** biedt de volgende voordelen:

* Met **DirectQuery** kunt u visualisaties maken van zeer grote gegevenssets, waarvoor het anders ondoenlijk zou zijn om eerst alle gegevens vooraf te aggregeren en te importeren
* Bij onderliggende gegevenswijzigingen kan het noodzakelijk zijn de gegevens te vernieuwen. Voor sommige rapporten kan de noodzaak tot het weergeven van de actuele gegevens leiden tot te grote gegevensoverdrachten om de gegevens opnieuw te kunnen importeren. In **DirectQuery**-rapporten worden echter altijd de actuele gegevens gebruikt
* De limiet voor de maximale grootte van een gegevensset van 1 GB geldt *niet* in **DirectQuery**

## <a name="limitations-of-directquery"></a>Beperkingen van DirectQuery
Het gebruik van **DirectQuery** is onderhevig aan de volgende beperkingen:

* Alle tabellen moeten afkomstig zijn uit één database
* Als de query in **Query-editor** te complex is, treedt er een fout op. Om de fout te verhelpen, moet u de problematische stap in **Query-editor** verwijderen, of de gegevens *importeren* in plaats van **DirectQuery** te gebruiken. Bij multidimensionale bronnen, zoals SAP Business Warehouse, is er geen **Query-editor**
* Relaties kunnen slechts worden gefilterd in één richting, in plaats van in beide richtingen (het is wel mogelijk om kruislings filteren in beide richtingen in te schakelen voor **DirectQuery** als preview-functie). Bij multidimensionale bronnen, zoals SAP Business Warehouse, zijn er geen relaties gedefinieerd in het model
* Time intelligence-functies zijn niet beschikbaar in **DirectQuery**. Speciale behandeling van datumkolommen (jaar, kwartaal, maand, dag, enzovoort) wordt bijvoorbeeld niet ondersteund in de **DirectQuery**-modus.
* Standaard worden er beperkingen gesteld aan DAX-expressies die zijn toegestaan in metingen. Zie de volgende alinea (na deze lijst met opsommingstekens) voor meer informatie
* Er worden maximaal 1 miljoen rijen met gegevens geretourneerd wanneer u **DirectQuery** gebruikt. Dit is niet van invloed op aggregaties of berekeningen die worden gebruikt om de gegevensset te maken die met **DirectQuery** wordt geretourneerd, alleen op de geretourneerde rijen. U kunt bijvoorbeeld 10 miljoen rijen aggregeren met een query die wordt uitgevoerd op de gegevensbron, en het resultaat van deze aggregatie retourneren naar Power BI met **DirectQuery**, zolang er maar minder dan 1 miljoen rijen met gegevens naar Power BI worden geretourneerd. Als er meer dan 1 miljoen rijen worden geretourneerd met **DirectQuery**, treedt er een fout op in Power BI.

Om ervoor te zorgen dat de prestaties van query's die naar de onderliggende gegevensbron worden verzonden acceptabel blijven, worden er standaard beperkingen opgelegd aan metingen. Geavanceerde gebruikers kunnen ervoor kiezen deze beperkingen als volgt te omzeilen: selecteer achtereenvolgens **Bestand > Opties**, **Instellingen > Opties en instellingen > DirectQuery** en de optie *Onbeperkte metingen toestaan in de DirectQuery-modus*. Als deze optie is geselecteerd, kan elke DAX-expressie worden gebruikt die geldig is voor een meting. Gebruikers moeten echter wel beseffen dat bepaalde expressies met hoge prestaties als de gegevens worden geïmporteerd, kunnen resulteren in erg trage query's als deze worden uitgevoerd op de back-endbron in de DirectQuery-modus.

## <a name="important-considerations-when-using-directquery"></a>Belangrijke overwegingen bij het gebruik van DirectQuery
Houd rekening met de volgende drie punten wanneer u **DirectQuery** gebruikt:

* **Prestaties en belasting**: alle **DirectQuery**-aanvragen worden verzonden naar de brondatabase, zodat de benodigde tijd voor het vernieuwen van een visueel element afhankelijk is van de tijd die deze back-end-bron nodig heeft om de resultaten van de query (of query's) te retourneren. De aanbevolen reactietijd (de tijd waarin de aangevraagde gegevens worden geretourneerd) van **DirectQuery** voor visuele elementen is vijf seconden of minder. De aanbevolen maximumreactietijd is 30 seconden. Als de reactietijd nog groter wordt, wordt de gebruikerservaring van het rapport onaanvaardbaar negatief. Als een rapport is gepubliceerd naar de Power BI-service en een query langer duurt dan een paar minuten, treedt er bovendien een time-out op en wordt er een foutbericht weergegeven.
  
  Houd ook rekening met de belasting van de brondatabase op basis van het aantal Power BI-gebruikers dat het gepubliceerde rapport gebruikt. Het gebruik van *beveiliging op rijniveau* (RLS) kan ook van grote invloed zijn. Een niet-RLS dashboardtegel die wordt gedeeld door meerdere gebruikers, resulteert slechts in één query op de database. Als echter RLS voor een dashboardtegel wordt gebruikt en die tegel moet worden vernieuwd, is er meestal een query *per gebruiker* vereist. Hierdoor kan de belasting van de brondatabase aanzienlijk toenemen, wat de prestaties negatief kan beïnvloeden.
  
  In Power BI worden zo efficiënt mogelijke query's gemaakt. In bepaalde omstandigheden is de gegenereerde query mogelijk niet efficiënt genoeg om te voorkomen dat het vernieuwen mislukt. Als met een gegenereerde query bijvoorbeeld uitzonderlijk veel rijen (meer dan 1 miljoen) worden opgehaald uit de back-endgegevensbron, treedt de volgende fout op:
  
      The resultset of a query to external data source has exceeded
      the maximum allowed size of '1000000' rows.
  
  Deze situatie kan zich voordoen bij een eenvoudig diagram met een kolom met een zeer hoge kardinaliteit, als de aggregatie-optie is ingesteld op *Niet samenvatten*. Het visuele element mag alleen kolommen bevatten met een kardinaliteit van minder dan 1 miljoen, of de juiste filters moeten worden toegepast.
* **Beveiliging**: alle gebruikers die een gepubliceerd rapport gebruiken, maken verbinding met de back-endgegevensbron met behulp van de referenties die zijn ingevoerd na de publicatie van het rapport naar de Power BI-service. Dit is in feite hetzelfde als gegevens die worden geïmporteerd: alle gebruikers zien dezelfde gegevens, ongeacht eventuele beveiligingsregels die in de back-endbron zijn gedefinieerd. Klanten die beveiliging per gebruiker willen, moeten DirectQuery-bronnen implementeren en RLS gebruiken. [Meer informatie over RLS](service-admin-rls.md).
* **Ondersteunde functies**: niet alle functies in **Power BI Desktop** worden ondersteund in de **DirectQuery**-modus, of kunnen beperkt zijn. Bovendien zijn sommige functies in de Power BI-service (zoals *Snelle inzichten*) niet beschikbaar voor gegevenssets als **DirectQuery** wordt gebruikt. Alle beperkingen van deze functies bij gebruik van **DirectQuery** moeten in aanmerking worden genomen bij het bepalen of u **DirectQuery** wilt gebruiken.   

## <a name="publish-to-the-power-bi-service"></a>Publiceren naar de Power BI-service
Rapporten die zijn gemaakt met **DirectQuery**, kunnen worden gepubliceerd naar de Power BI-service.

Als de **on-premises gegevensgateway** (**Azure SQL Database**, **Azure SQL Data Warehouse** of **Redshift**) niet vereist is voor de gegevensbron, moeten er referenties worden opgegeven voordat het gepubliceerde rapport in de Power BI-service wordt weergegeven.

Ga als volgt te werk om referenties op te geven: selecteer het tandwielpictogram **Instellingen** in Power BI en selecteer vervolgens **Instellingen**.

![](media/desktop-use-directquery/directquery_3.png)

Het venster **Instellingen** wordt weergegeven. Selecteer het tabblad **Gegevenssets**, kies de gegevensset waarvoor **DirectQuery** wordt gebruikt, en selecteer **Referenties bewerken**.

![](media/desktop-use-directquery/directquery_4.png)

Als iemand probeert een gepubliceerd rapport te openen of een gegevensset die is gemaakt met **DirectQuery** te verkennen voordat er referenties zijn opgegeven, treedt er een fout op bij het maken van verbinding met deze gegevensbronnen.

Voor andere gegevensbronnen dan **Azure SQL Database**, **Azure SQL Data Warehouse** en **Redshift** die gebruikmaken van DirectQuery, moet u een **on-premises gegevensgateway** installeren en de gegevensbron registreren voordat er een verbinding tot stand kan worden gebracht. Zie [On-premises gegevensgateway](http://go.microsoft.com/fwlink/p/?LinkID=627094) voor meer informatie.

## <a name="next-steps"></a>Volgende stappen
Bekijk de volgende bronnen voor meer informatie over **DirectQuery**:

* [DirectQuery in Power BI](desktop-directquery-about.md)
* [Data sources supported by DirectQuery](desktop-directquery-data-sources.md) (Gegevensbronnen die worden ondersteund door DirectQuery)
* [DirectQuery en SAP BW](desktop-directquery-sap-bw.md)
* [DirectQuery en SAP HANA](desktop-directquery-sap-hana.md)
* [On-premises gegevensgateway](service-gateway-onprem.md)

