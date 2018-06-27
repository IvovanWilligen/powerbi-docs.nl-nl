---
title: Power BI Premium-ondersteuning voor grotere gegevenssets
description: Power BI Premium ondersteunt nu gegevenssets tot 10 GB.
author: jocaplan
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-admin
ms.topic: conceptual
ms.date: 02/27/2018
ms.author: jocaplan
LocalizationGroup: Premium
ms.openlocfilehash: fa05fd6808ebe78d5d17e2ad3d93fbcf22f7d3c9
ms.sourcegitcommit: 2a7bbb1fa24a49d2278a90cb0c4be543d7267bda
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/26/2018
ms.locfileid: "34298591"
---
# <a name="power-bi-premium-support-for-large-datasets"></a>Power BI Premium-ondersteuning voor grotere gegevenssets

Power BI Premium ondersteunt uploads met Power BI Desktop-bestanden (pbix) die maximaal 10 GB groot zijn. Een gegevensset kan, na te zijn geüpload, worden vernieuwd tot een grootte van 12 GB. Als u een grote gegevensset wilt gebruiken, publiceert u deze naar een werkruimte die is toegewezen aan Premium capaciteit.
 
## <a name="best-practices"></a>Aanbevolen procedures

In deze sectie worden aanbevolen procedures beschreven voor het werken met grote gegevenssets.

**Grote modellen kunnen een aanzienlijke belasting op uw resource-capaciteit vormen**; het wordt aangeraden voor modellen groter dan 1 GB minimaal een P1 SKU te gebruiken. In de volgende tabel zijn de aanbevolen SKU's voor verschillende pbix-grootten weergegeven:


   |SKU  |Grootte van pbix-bestand   |
   |---------|---------|
   |P1    | < 3 GB        |
   |P2    | < 6 GB        |
   |P3    | tot 10 GB   |



**Uw pbix-bestanden bevatten gegevens in een sterk gecomprimeerde toestand**. De gegevens breiden waarschijnlijk meerdere keren uit wanneer ze in het geheugen worden geladen. Van daaruit breiden ze mogelijk meerdere keren uit tijdens het vernieuwen van gegevens.

**Geplande vernieuwing van grote gegevenssets kan erg lang duren** en een zware belasting voor uw resources vormen. Plan het vernieuwen van gegevens daarom niet te veel gelijktijdig. U ziet ook dat de time-out voor geplande vernieuwingstaken voor alle gegevenssets in deze capaciteit is verdubbeld tot vier uur.

**Het voor de eerste keer laden van een rapport voor grote gegevenssets kan erg lang duren** als het al enige tijd geleden is dat de gegevensset is gebruikt, omdat het model in het geheugen van de uw Premium-capaciteit wordt geladen. Voor rapporten waarvoor het laden langer duurt, wordt de laadvoortgang via een voortgangsbalk weergegeven.

**Als u de werkruimte uit de Premium-capaciteit verwijdert**, werken het model en alle gekoppelde rapporten en dashboards niet meer.

**Omdat de beperkingen van geheugen en tijd per query veel hoger zijn in Premium capaciteit**, is het raadzaam filters en slicers te gebruiken om van visuals alleen de benodigde informatie weer te geven.

## <a name="next-steps"></a>Volgende stappen
[Wat is Power BI Premium?](service-premium.md)  
[Releaseopmerkingen bij Power BI Premium](service-premium-release-notes.md)  
[Technisch document over Microsoft Power BI Premium](https://aka.ms/pbipremiumwhitepaper)  
[Een technisch document over een Power BI-implementatie voor de onderneming plannen](https://aka.ms/pbienterprisedeploy)  
[De verlengde Pro-proefversie activeren](service-extended-pro-trial.md)  

Hebt u nog vragen? [Misschien dat de Power BI-community het antwoord weet](https://community.powerbi.com/)
