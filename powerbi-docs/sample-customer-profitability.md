---
title: 'Voorbeeld van klantwinstgevendheid in Power BI: Rondleiding volgen'
description: 'Voorbeeld van klantwinstgevendheid in Power BI: Rondleiding volgen'
author: maggiesMSFT
manager: kfile
ms.reviewer: amac
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 06/20/2019
ms.author: maggies
LocalizationGroup: Samples
ms.openlocfilehash: af20d5842664311a0d543ee189ef671f7865058b
ms.sourcegitcommit: 8dee40f07d284ec84a8afa0100359f146e1dd88b
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/27/2019
ms.locfileid: "67418760"
---
# <a name="customer-profitability-sample-for-power-bi-take-a-tour"></a>Voorbeeld van klantwinstgevendheid in Power BI: Rondleiding volgen

Het inhoudspakket Voorbeeld van klantwinstgevendheid bevat een dashboard, rapport en gegevensset voor een bedrijf dat marketingmateriaal maakt. Dit dashboard is gemaakt door een CFO om de belangrijkste metrische gegevens te verzamelen over haar vijf business unit managers (leidinggevenden), producten, klanten en brutomarges. In een oogopslag kan ze zien welke factoren van invloed zijn op de winstgevendheid.

![Dashboard voor het voorbeeld van klantwinstgevendheid](media/sample-customer-profitability/power-bi-dash.png)

Dit voorbeeld is onderdeel van een serie die laat zien hoe u Power BI kunt gebruiken met bedrijfsgegevens, rapporten en dashboards. Dit voorbeeld is gemaakt met echte, geanonimiseerde gegevens van [obviEnce](http://www.obvience.com/). De gegevens zijn beschikbaar in verschillende indelingen: inhoudspakket/-app, een PBIX-bestand van Power BI Desktop of een Excel-werkmap. Zie [Voorbeelden voor Power BI](sample-datasets.md). 

Deze zelfstudie maakt gebruik van de Power BI-service en het inhoudspakket Voorbeeld van klantwinstgevendheid. Omdat de rapportervaringen zo gelijk zijn, kunt u de zelfstudie ook volgen met Power BI Desktop en het PBIX-voorbeeldbestand. 

## <a name="prerequisites"></a>Vereisten

Voordat u het voorbeeld kunt gebruiken, moet u het eerst downloaden als een [inhoudspakket](#get-the-content-pack-for-this-sample), een [PBIX-bestand](#get-the-pbix-file-for-this-sample) of een [Excel-werkmap](#get-the-excel-workbook-for-this-sample).

### <a name="get-the-content-pack-for-this-sample"></a>Het inhoudspakket voor dit voorbeeld ophalen

1. Open de Power BI-service (app.powerbi.com), meld u aan en open de werkruimte waar u het voorbeeld wilt opslaan.

2. Selecteer in de linkerbenedenhoek **Gegevens ophalen**.

   ![Selecteer Gegevens ophalen](media/sample-datasets/power-bi-get-data.png)
3. Selecteer op de pagina **Gegevens ophalen** die wordt weergegeven, de optie **Voorbeelden**.

4. Selecteer **Voorbeeld van klantwinstgevendheid** en kies vervolgens **Verbinding maken**.  

    ![Verbinding maken met voorbeeld](media/sample-customer-profitability/get-supplier-sample.png)
5. Het inhoudspakket wordt geïmporteerd in Power BI en er wordt een nieuw dashboard, een nieuw rapport en een nieuwe gegevensset toegevoegd aan de huidige werkruimte.

    ![Item Voorbeeld van klantwinstgevendheid](media/sample-customer-profitability/customer-profitability-sample-entry.png)

### <a name="get-the-pbix-file-for-this-sample"></a>Het pbix-bestand voor dit voorbeeld ophalen

U kunt het Voorbeeld van klantwinstgevendheid ook downloaden als [PBIX-bestand](http://download.microsoft.com/download/6/A/9/6A93FD6E-CBA5-40BD-B42E-4DCAE8CDD059/Customer%20Profitability%20Sample%20PBIX.pbix) dat bedoeld is voor gebruik met Power BI Desktop.

### <a name="get-the-excel-workbook-for-this-sample"></a>De Excel-werkmap ophalen voor dit voorbeeld

Als u de gegevensbron voor dit voorbeeld wilt bekijken, is het ook beschikbaar als [Excel-werkmap](http://go.microsoft.com/fwlink/?LinkId=529781). De werkmap bevat Power View-werkbladen die u kunt bekijken en wijzigen. Als u de onbewerkte gegevens wilt zien, schakelt u de invoegtoepassingen van Gegevensanalyse in en selecteert u vervolgens **Power Pivot > Beheren**. Als u de Power View- en Power Pivot-invoegtoepassingen wilt inschakelen, raadpleegt u [De Excel-voorbeelden in Excel bekijken](sample-datasets.md#optional-take-a-look-at-the-excel-samples-from-inside-excel-itself) voor meer informatie.

## <a name="what-is-our-dashboard-telling-us"></a>Wat vertelt het dashboard ons?

Zoek in de werkruimte waar u het voorbeeld hebt opgeslagen, het dashboard Klantwinstgevendheid en selecteer het:

![Dashboard voor het voorbeeld van klantwinstgevendheid](media/sample-customer-profitability/power-bi-dash.png)

### <a name="company-wide-dashboard-tiles"></a>Dashboardtegels voor de gehele onderneming
1. Open het dashboard in de Power BI-service. De dashboardtegels geven onze CFO een weergave van metrische gegevens op hoog niveau die belangrijk voor haar zijn. Wanneer ze iets interessants ziet, kan ze een tegel selecteren om dieper in de gegevens te graven.

2. Bekijk de tegels aan de linkerkant van het dashboard.

    ![Tegels voor managers](media/sample-customer-profitability/power-bi-manager.png)

   Let op de volgende details:
   - De brutomarge van het bedrijf is 42,5 %.
   - Het bedrijf heeft 80 klanten.
   - Er worden vijf verschillende producten verkocht.
   - Het laagste omzetvariantiepercentage ten opzichte van budget was in februari, gevolgd door het hoogste in maart.
   - Het grootste deel van de omzet is afkomstig uit de regio's Oost en Noord. De brutomarge heeft nooit het budget overschreden, waarbij voor de bedrijfseenheden ER-0 en MA-0 verder onderzoek nodig is.
   - Totale omzet van het jaar is bijna gelijk aan het budget.

### <a name="manager-specific-dashboard-tiles"></a>Managerspecifieke dashboardtegels
De tegels aan de rechterkant van het dashboard geven een team-scorecard weer. De CFO moet haar managers blijven volgen. Deze tegels bieden haar een overzicht op hoog niveau van de winst op basis van het brutomargepercentage. Als de trend in het brutomargepercentage voor een manager afwijkt van de verwachting, dan kan ze dit verder onderzoeken.

![Brutomargepercentage voor managers](media/sample-customer-profitability/power-bi-manager2.png)

Als we de managerspecifieke dashboardtegels analyseren, constateren we het volgende:

- Alle leidinggevenden, behalve Carlos, hebben hun verkoopdoel al overschreden. Maar de werkelijke verkopen van Carlos zijn de hoogste.
- Het brutomargepercentage van Annelie is het laagste, maar we zien een constante stijging sinds maart.
- Valery heeft haar brutomargepercentage daarentegen aanzienlijk zien afnemen.
- Andrew had een sterk wisselend jaar.

## <a name="explore-the-dashboards-underlying-data"></a>De onderliggende gegevens van het dashboard verkennen
Dit dashboard bevat tegels die gekoppeld zijn aan een rapport en aan een Excel-werkmap.

### <a name="open-the-excel-online-data-source"></a>Open de Excel Online-gegevensbron
Twee tegels op dit dashboard, **Target vs Actual** (Doel vs Realisatie) en **Year Over Year Revenue Growth** (Omzetgroei jaar na jaar) zijn vastgemaakt vanuit een Excel-werkmap. Wanneer u een van deze tegels selecteert, opent Power BI de gegevensbron, in dit geval Excel Online.

![Excel Online](media/sample-customer-profitability/power-bi-excel-online.png)

1. Selecteer één van de tegels die vanuit Excel zijn vastgemaakt. Excel Online wordt in de Power BI-service geopend.
2. U ziet dat de werkmap drie tabbladen met gegevens bevat. Open **Omzet**.
3. Laten we bekijken waarom Carlos zijn doel nog niet heeft bereikt:  

    a. Selecteer in de schuifregelaar **Leidinggevende** **Carlos Grilo**.   

    b. Uit de eerste draaitabel blijkt dat de omzetgroei van het beste product van Carlos, Primus, met 152% is gedaald in vergelijking met het afgelopen jaar. En uit de **variantiegrafiek voor de jaar-na-jaaromzet** blijkt dat hij de meeste maanden onder budget zit.  

    ![Draaitabel](media/sample-customer-profitability/power-bi-pivotchart.png)

    ![Resultaten voor Carlos](media/sample-customer-profitability/power-bi-carlos.png)

4. Ga verder met verkennen. As u iets interessant vindt, kunt u rechtsboven **Vastmaken** ![speldpictogram](media/sample-customer-profitability/power-bi-excel-pin.png) selecteren om [het aan het dashboard vast te maken](service-dashboard-pin-tile-from-excel.md).

5. Gebruik de pijl terug in uw browser om terug te keren naar het dashboard.

### <a name="open-the-underlying-power-bi-report"></a>Open het onderliggende Power BI-rapport
Veel tegels op het voorbeelddashboard Klantwinstgevendheid zijn vastgemaakt vanuit het onderliggende voorbeeldrapport Klantwinstgevendheid.

1. Selecteer één van deze tegels om het rapport in de leesweergave te openen.

   Als de tegel is gemaakt in Q&A, wordt het Q&A-venster geopend als u de tegel selecteert. Selecteer **Q&A afsluiten** om terug te keren naar het dashboard en een andere tegel te proberen.

2. Het rapport heeft drie pagina's. Elk tabblad onderaan het rapport vertegenwoordigt een andere pagina.

    ![Drie tabbladen onderaan](media/sample-customer-profitability/power-bi-report-tabs.png)

    * **Team-scorecard** richt zich op de prestaties van de vijf managers en hun bedrijfscijfers.
    * **Analyse van marge in de bedrijfstak** biedt een manier om de winst te analyseren ten opzichte van de gehele bedrijfstak.
    * **Executive-scorecard** biedt een weergave van elk van de managers met een indeling die geschikt is voor Cortana.

### <a name="team-scorecard-page"></a>De pagina Team-scorecard
![Rapportpagina Team-scorecard](media/sample-customer-profitability/customer2.png)

Laten we in detail kijken naar twee van de teamleden en zien welke inzichten kunnen worden verkregen: 

1. Selecteer in de slicer **Leidinggevende** aan de linkerkant de naam Andrew om de rapportpagina zo te filteren dat alleen gegevens over Andrew worden weergegeven:

   * Bekijk voor een snelle KPI **Omzetstatus (totaal van jaar)** van Andrew; deze is groen, wat betekent dat hij goed presteert.
   * De grafiek **Omzetafwijking in procent ten opzichte van het budget per maand en de leidinggevende** laat zien dat met uitzondering van een dip in februari Andrew het over het algemeen goed doet. Zijn dominante regio is Oost en hij verwerkt 49 klanten en vijf van de zeven producten. Zijn brutomargepercentage is niet het hoogste of het laagste.
   * In de grafiek **RevenueTY and Revenue % Var to Budget by Month** (Omzet dit jaar en omzetafwijking ten opzichte van het budget per maand) ziet u dat er sprake is van een gelijkmatige winst. Als u echter filtert door het vierkant voor **Centraal** in de regiotreemap te selecteren, ontdekt u dat Andrew alleen omzet in maart en alleen in Indiana heeft. Is dit de bedoeling of is dit iets dat moet worden onderzocht?

2. Nu naar Valery. Selecteer in de slicer **Leidinggevende** de naam Valery om de rapportpagina zo te filteren dat alleen gegevens over haar worden weergegeven. 

   ![Gegevens van Valery](media/sample-customer-profitability/customer3.png)

   * U ziet de rode KPI voor **Omzetstatus (totaal van jaar)** . Dit item moet zeker verder worden onderzocht.
   * Haar omzetvariantie schetst ook een zorgwekkend beeld; ze haalt haar inkomstenmarges niet.
   * Valery heeft slechts negen klanten, verwerkt slechts twee producten en werkt bijna exclusief met klanten in het noorden. Deze specialisatie kan de grote schommelingen in haar metrische gegevens verklaren.
   * Als u het vierkant **Noord** in de structuurkaart selecteert, kunt u zien dat de brutomarge van Valery in het noorden consistent is met haar totale marge.
   * Als u elk van de andere vierkanten **Totale omzet per regio** selecteert, ziet u iets interessants: haar brutomargepercentage varieert van 23% tot 79%. Haar omzetcijfers zijn in alle regio's behalve de regio Noord zeer seizoensgebonden.

3. Blijf onderzoeken om erachter te komen waarom het gebied van Valery niet goed presteert. Bekijk de regio's, de andere bedrijfsonderdelen en de volgende pagina in het rapport: **Analyse van marge in de bedrijfstak**.

### <a name="industry-margin-analysis"></a>Analyse van marge in de bedrijfstak
Deze rapportpagina bevat een ander deel van de gegevens. Hier wordt gekeken naar de brutomarge voor de gehele bedrijfstak, opgedeeld per segment. De CFO gebruikt deze pagina om de metrische gegevens van het bedrijf en bedrijfsonderdelen te vergelijken met de gegevens uit de bedrijfstak om trends en winstgevendheid te kunnen verklaren. U vraagt zich misschien af waarom een diagram **Percentage brutomarge per maand en leidinggevende** op deze pagina staat, aangezien dit teamspecifiek is. Doordat dit diagram hier staat, kunnen we de pagina filteren per business unit manager.  

![Rapportpagina Analyse van marge in de bedrijfstak](media/sample-customer-profitability/customer6.png)

1. Hoe verschilt de winstgevendheid per bedrijfstak? Hoe worden de producten en klanten onderverdeeld per bedrijfstak? Als u deze vragen wilt beantwoorden, selecteert u een of meer bedrijfstakken linksboven (start vanaf de bedrijfstak CPG). Als u het filter wilt wissen, selecteert u het gumpictogram.

2. De CFO zoekt in het bellendiagram (**Omzetafwijking in procenten ten opzichte van het budget, brutomargepercentage en omzet dit jaar per bedrijfstak**) de grootste bellen, omdat die de grootste invloed op de omzet hebben. Filter de pagina door de naam van een manager te selecteren in het vlakdiagram om gemakkelijk de invloed van de manager per bedrijfstaksegment te bekijken.

3. Wanneer u elke beheerder in de grafiek selecteert, moet u op de volgende details letten:
   * De invloed van Andrew omvat veel verschillende bedrijfstaksegmenten met breed uiteenlopende brutomargepercentages (de meeste aan de positieve kant) en variantiepercentages.
   * De grafiek van Annelie is vergelijkbaar, behalve dat ze zich op slechts een handvol bedrijfstakken richt met een focus op het segment Federal en het product Gladius.
   * Carlos richt zich duidelijk op het servicessegment, met een hoge winst. Hij heeft het variantiepercentage sterk verbeterd voor het High Tech-segment en een voor hem nieuw segment, Industrieel, vertoont uitzonderlijk goede prestaties in vergelijking met het budget.
   * Tina werkt met een handvol segmenten en heeft het hoogste brutomargepercentage. De voornamelijk kleine bellen laten echter zien dat haar invloed op de winstgevendheid van het bedrijf minimaal is.
   * Valery, die verantwoordelijk is voor slechts één product, werkt in slechts vijf bedrijfstakken. Haar invloed voor de bedrijfstak is seizoensgebonden, maar produceert altijd een grote bel, die wijst op een grote invloed op de winstgevendheid van het bedrijf. Bieden de bedrijfstaksegmenten een verklaring voor haar negatieve prestaties?

### <a name="executive-scorecard"></a>Executive-scorecard
Deze pagina wordt opgemaakt als een antwoordpagina voor Cortana. Zie [Aangepaste antwoordpagina's maken voor Cortana](service-cortana-answer-cards.md) voor meer informatie.

## <a name="dig-into-the-data-by-asking-questions-with-qa"></a>Dieper graven in de gegevens door vragen te stellen met Q&A
Voor onze analyse kan het handig zijn als we bepalen welke bedrijfstak de meeste omzet voor Valery genereert. Hiervoor gebruiken we Q&A.

1. Selecteer **Rapport bewerken** om het rapport in de bewerkweergave te openen. De bewerkingsweergave is alleen beschikbaar als u eigenaar van het rapport bent. Deze weergave wordt ook wel de modus *Maker* genoemd. Als dit rapport in plaats daarvan alleen met u is gedeeld, kunt u het niet openen in de bewerkingsweergave.

2.  Selecteer boven in het dashboard de optie **Een vraag stellen** om het Q&A-venster te openen.

    ![Een vraag stellen over uw gegevens](media/sample-customer-profitability/power-bi-ask-question.png)

3. Typ *totale omzet per bedrijfstak voor Valery* in het vraagvak. Zoals u ziet wordt de visualisatie bijgewerkt terwijl u de vraag typt.

    ![Typ vraag in vraagvak](media/sample-customer-profitability/power-bi-qna.png)

   Zoals u ziet, is de bedrijfstak Distributie het grootste omzetgebied voor Valery.

### <a name="dig-deeper-by-adding-filters"></a>Dieper graven door filters toe te voegen
Laten we eens kijken naar de bedrijfstak Distributie.  

1. Open de rapportpagina **Analyse van marge in de bedrijfstak**.
2. Vouw het filterdeelvenster rechts uit zonder visualisaties te selecteren op de rapportagepagina. In het deelvenster **Filters** mogen alleen **filters op paginaniveau** worden weergegeven.  

   ![Filters op paginaniveau](media/sample-customer-profitability/power-bi-filters.png)
3. Zoek het filter voor **bedrijfstak** en selecteer de pijl om de lijst uit te vouwen. We gaan een paginafilter voor de bedrijfstak Distributie toevoegen. Wis eerst alle selecties door het selectievakje **Alles selecteren** uit te schakelen. Selecteer vervolgens alleen **Distributie.**  

   ![filter voor Distributie](media/sample-customer-profitability/customer7.png)
4. Het diagram **Percentage brutomarge per maand en leidinggevende** laat zien dat alleen Valery en Tina klanten hebben in deze bedrijfstak en dat Valery alleen van juni tot en met november in deze bedrijfstak heeft gewerkt.   
5. Selecteer **Tina** en vervolgens **Valery** in de legenda van het diagram **Brutomarge per maand en leidinggevende**. U ziet dat het deel van Tina van het diagram **Totale omzet per product** klein is vergeleken met dat van Valery.
6. Als u de werkelijke omzet wilt bekijken, selecteert u het Q&A-vak in het dashboard en voert u de *totale opbrengsten voor distributie van scenario* in.  

     ![Typ vraag in Q&A-vak](media/sample-customer-profitability/power-bi-qna2.png)

    We kunnen ook andere bedrijfstakken verkennen en zelfs klanten toevoegen aan onze visuele elementen om inzicht te krijgen in de oorzaken voor de prestaties van Valery.

## <a name="next-steps-connect-to-your-data"></a>Volgende stappen: Verbinding maken met uw gegevens
Dit is een veilige omgeving om in te experimenten, omdat er geen optie is om uw wijzigingen op te slaan. Als u deze wel opslaat, kunt u altijd **Gegevens ophalen** selecteren voor een nieuw exemplaar van dit voorbeeld.

We hopen dat deze rondleiding heeft laten zien hoe Power BI-dashboards, Q&A en rapporten inzicht kunnen geven in klantgegevens. Nu is het uw beurt om verbinding met uw eigen gegevens te maken. Met Power BI kunt u verbinding maken met een groot aantal gegevensbronnen. Zie [Aan de slag met de Power BI-service](service-get-started.md) voor meer informatie.

