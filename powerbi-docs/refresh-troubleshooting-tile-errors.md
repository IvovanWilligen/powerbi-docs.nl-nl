---
title: Problemen met tegelfouten oplossen
description: Veelvoorkomende fouten bij het vernieuwen van een tegel in Power BI
author: mgblythe
manager: kfile
ms.reviewer: kayu
ms.custom: seodec18
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 12/06/2018
ms.author: mblythe
LocalizationGroup: Troubleshooting
ms.openlocfilehash: c1df7e6293db703922f37c3f28546bb296d1a46a
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/29/2019
ms.locfileid: "66051001"
---
# <a name="troubleshooting-tile-errors"></a>Problemen met tegelfouten oplossen
Hieronder vindt u een overzicht en uitleg van enkele veelvoorkomende fouten voor tegels.

> [!NOTE]
> Als u een fout tegenkomt die hieronder niet wordt vermeld en die problemen veroorzaakt, kunt u om hulp vragen op de [site van de community](http://community.powerbi.com/) of een [ondersteuningsticket](https://powerbi.microsoft.com/support/) maken.
> 
> 

## <a name="errors"></a>Fouten
**Er is een onverwachte fout voor Power BI opgetreden tijdens het laden van het model. Probeer het later opnieuw.**
of **Het gegevensmodel kan niet worden opgehaald. Neem contact met de eigenaar van het dashboard op om te controleren of de gegevensbronnen en het model bestaan en toegankelijk zijn.**

We hebben geen toegang tot uw gegevens omdat de gegevensbron niet bereikbaar is. Het probleem kan zich voordoen als de naam van de gegevensbron is gewijzigd, als de gegevensbron is verwijderd, verplaatst of offline is of als de machtigingen zijn gewijzigd. Controleer of de bron zich nog op de locatie bevindt waarnaar wordt verwezen en u nog over de toegangsmachtiging beschikt. Als dit het probleem niet is, is de bron mogelijk langzaam. Probeer het later opnieuw, op een moment dat de bron minder zwaar wordt belast. Als het een on-premises bron betreft, kan de eigenaar van de bron mogelijk meer informatie verstrekken.

**U hebt geen toestemming om deze tegel weer te geven of de werkmap te openen.**

Neem contact op met de eigenaar van het dashboard om te controleren of de gegevensbronnen en het model bestaan en toegankelijk zijn voor uw account.

**Aangepaste visuals zijn door uw beheerder uitgeschakeld.**

De Power BI-beheerder heeft het gebruik van aangepaste visuals voor uw organisatie of beveiligingsgroep uitgeschakeld. U kunt geen aangepaste visuals van de [Microsoft marketplace](https://appsource.microsoft.com/en-us/marketplace/apps?page=1&product=power-bi-visuals) gebruiken of persoonlijke visuals importeren vanuit een bestand. U kunt alleen de vooraf verpakte set visuals gebruiken.


**Gegevensshapes moeten minstens één groep of één berekening bevatten die gegevens uitvoert. Neem contact op met de eigenaar van het dashboard.**

Er kunnen momenteel geen gegevens worden weergegeven, omdat de query leeg is. Voeg enkel velden uit de lijst met velden toe aan uw visual en maak deze opnieuw vast.

**Kan de gegevens niet weergeven omdat de relatie tussen twee of meer velden niet kan worden vastgesteld met Power BI.**

U probeert twee of meer velden uit niet-gerelateerde tabellen te gebruiken. U moet de niet-gerelateerde velden uit de visual verwijderen en vervolgens een relatie tussen de tabellen maken. Zodra u deze wijziging hebt doorgevoerd, kunt u de velden weer toevoegen aan de visual. Dit kan worden gedaan in Power BI Desktop of Power Pivot voor Excel. [Meer informatie](desktop-create-and-manage-relationships.md)

**De groepen op de primaire en secundaire as overlappen. Groepen op de primaire as kunnen niet dezelfde sleutels hebben als groepen op de secundaire as.**

Dit is doorgaans een tijdelijk probleem. Dit gebeurt meestal wanneer u groepen uit rijen naar kolommen verplaatst. In dit geval moet de fout verdwijnen wanneer alle groepen zijn verplaatst. Als het bericht nog steeds wordt weergegeven, kunt u de velden in de rijen en kolommen wisselen of de as-legenda of verwijdert u velden uit de visual.  

**De beschikbare resources zijn overschreden voor deze weergave. U kunt filteren om de hoeveelheid weergegeven gegevens te verminderen.**

Er zijn te veel gegevens met uw visual gezocht om alle resultaten met de beschikbare bronnen te kunnen verwerken. Filter de visual om de hoeveelheid gegevens in de resultaten te reduceren.

**Kan de volgende velden niet identificeren: {0}. Werk het visuele element bij met velden die onderdeel zijn van de gegevensset.**

Het veld is waarschijnlijk verwijderd of de naam van het veld is gewijzigd. U kunt het desbetreffende veld uit de visual verwijderen, een ander veld toevoegen en dit opnieuw vastmaken.

**Kan de gegevens voor dit visuele element niet ophalen. Probeer het later opnieuw.**

Dit is doorgaans een tijdelijk probleem. Als u het later opnieuw probeert en dit bericht nog steeds wordt weergegeven, neemt u contact op met de ondersteuning.

**Tegels blijven ongefilterde gegevens worden weergegeven na het inschakelen van eenmalige aanmelding (SSO).**

Dit kan gebeuren als de onderliggende gegevensset is geconfigureerd voor het gebruik van DirectQuery-modus of een Liveverbinding met Analysis Services via een on-premises gegevensgateway. In dit geval blijven de tegels om weer te geven van de ongefilterde gegevens na het inschakelen van eenmalige aanmelding voor de gegevensbron, totdat de volgende vernieuwing van de tegel vervallen is. Power BI maakt gebruik van eenmalige aanmelding zoals geconfigureerd bij de volgende vernieuwing van de tegel en de tegels weergeven in de gegevens die zijn gefilterd op basis van de gebruikers-id. 

Als u de gefilterde gegevens onmiddellijk te zien wilt, kunt u een vernieuwing tegel afdwingen door het beletselteken (...) in de rechterbovenhoek van een dashboard selecteren en klikken op **dashboardtegels vernieuwen**.

Als de eigenaar van een gegevensset, kunt u ook de vernieuwingsfrequentie van de tegel wijzigen en stel deze in op 15 minuten te versnellen tegels vernieuwen. Selecteer het tandwielpictogram in de rechterbovenhoek van Power BI-service en selecteer vervolgens **instellingen**. Op de **instellingen** weergeeft, schakelt de **gegevenssets** tabblad. Vouw **geplande vernieuwing van cache** en wijzig **vernieuwingsfrequentie**. Zorg ervoor dat u de configuratie opnieuw instellen naar de oorspronkelijke vernieuwingsfrequentie nadat Power BI wordt uitgevoerd de volgende vernieuwing van de tegel.

> [!NOTE]
> De **geplande vernieuwing van cache** sectie is alleen beschikbaar voor gegevenssets in de modus DirectQuery/LiveConnection. Gegevenssets in de modus Import hebben een afzonderlijke tegels vernieuwen niet nodig omdat de tegels worden automatisch vernieuwd tijdens de volgende geplande gegevensvernieuwing.

## <a name="contact-support"></a>Contact opnemen met de ondersteuning
Als u nog steeds problemen ondervindt, [neemt u contact op met de ondersteuning](https://support.powerbi.com) om het probleem nader te onderzoeken.

## <a name="next-steps"></a>Volgende stappen
[Problemen met de on-premises gegevensgateway oplossen](service-gateway-onprem-tshoot.md)  
[Problemen met Power BI Gateway - Personal oplossen](service-admin-troubleshooting-power-bi-personal-gateway.md)  
Nog vragen? [Misschien dat de Power BI-community het antwoord weet](http://community.powerbi.com/)

