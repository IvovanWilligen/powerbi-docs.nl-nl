---
title: Rapporten exporteren van Power BI naar PowerPoint (Preview)
description: Leer hoe u een Power BI-rapport naar PowerPoint kunt exporteren.
services: powerbi
documentationcenter: 
author: davidiseminger
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: complete
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 07/21/2017
ms.author: davidi
ms.openlocfilehash: 879d142cba4af026cc23188173a380340b4c245b
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/15/2017
---
# <a name="export-reports-from-power-bi-to-powerpoint-preview"></a>Rapporten exporteren van Power BI naar PowerPoint (Preview)
Met Power BI kunt u nu uw rapport publiceren naar **Microsoft PowerPoint** en heel eenvoudig een presentatie op basis van uw Power BI-rapport maken. Wanneer u wilt **exporteren naar PowerPoint** gebeurt het volgende:

* Elke pagina in het Power BI-rapport wordt een afzonderlijke dia in PowerPoint
* Elke visuele element in het Power BI-rapport wordt geëxporteerd als afbeelding met een hoge resolutie in PowerPoint
* Tekstvakken in het Power BI-rapport worden bewerkbare tekstvakken in PowerPoint
* In PowerPoint wordt een koppeling gemaakt die verwijst naar het Power BI-rapport

Het ophalen van uw **Power BI-rapport** dat is geëxporteerd naar **PowerPoint** is eenvoudig. Volg de stappen in de volgende sectie.

## <a name="how-to-export-your-power-bi-report-to-powerpoint"></a>Uw Power BI-rapport naar PowerPoint exporteren
Selecteer in de Power BI-service de sectie **Rapporten** in het navigatiedeelvenster links om deze sectie uit te vouwen. Selecteer vervolgens het rapport dat u wilt weergeven op het canvas. U kunt ook een rapport uit uw sectie **Mijn werkruimte** of uw **Favorieten** selecteren als het rapport op een van deze locaties staat.

![](media/service-publish-to-powerpoint/powerbi_to_powerpoint_0.png)

Wanneer het rapport dat u wilt exporteren naar PowerPoint wordt weergegeven op het canvas, selecteert u **Bestand > Exporteren naar PowerPoint (Preview)** in de menubalk in de Power BI-service, zoals wordt weergegeven in de volgende afbeelding.

![](media/service-publish-to-powerpoint/powerbi_to_powerpoint_1.png)

Hier ziet u een meldingsbanner in de rechterbovenhoek van het browservenster van de Power BI-service die aangeeft dat het rapport wordt geëxporteerd naar PowerPoint. Dit kan enkele minuten duren; u kunt tijdens het exporteren van het rapport in Power BI blijven werken.

![](media/service-publish-to-powerpoint/powerbi_to_powerpoint_2.png)

Wanneer u klaar bent, wijzigt de meldingsbanner zodat u weet dat de Power BI-service het exportproces heeft voltooid.

![](media/service-publish-to-powerpoint/powerbi_to_powerpoint_3.png)

Het bestand is beschikbaar wanneer de gedownloade bestanden worden weergegeven in uw browser. In de volgende afbeelding wordt dit weergegeven als een downloadbanner langs de onderkant van het browservenster.

![](media/service-publish-to-powerpoint/powerbi_to_powerpoint_4.png)

Zo eenvoudig werkt dat. U kunt het bestand downloaden, openen met PowerPoint en vervolgens wijzigen of bewerken zoals u met elke andere PowerPoint-presentatie zou doen.

## <a name="checking-out-your-exported-powerpoint-file"></a>Het geëxporteerde PowerPoint-bestand bekijken
Bij het openen van het PowerPoint-bestand dat door Power BI is geëxporteerd, ziet u enkele coole en nuttige elementen. Bekijk de volgende afbeelding en vervolgens de genummerde elementen hieronder die deze coole functies beschrijven.

![](media/service-publish-to-powerpoint/powerbi_to_powerpoint_5.png)

1. De eerste pagina van de presentatie bevat de naam van uw rapport en een koppeling zodat u het rapport waarop de presentatie is gebaseerd, kunt **Weergeven in Power BI**.
2. U krijgt zo ook handige informatie over het rapport, zoals de *laatste gegevensvernieuwing* waarop het geëxporteerde rapport is gebaseerd en de *gedownload op* -tijd en -datum. Dit is het tijdstip en de datum waarop het Power BI-rapport naar een PowerPoint-bestand is geëxporteerd.
3. Elke rapportpagina is een afzonderlijke dia, zoals wordt weergegeven in het navigatiedeelvenster links.

Wanneer u naar een afzonderlijke dia gaat, zult u merken dat elk visuele element een onafhankelijke afbeelding is (zoals al eerder vermeld). Zo kunt u de afbeelding kopiëren en plakken in een andere dia of waar u maar wilt.

![](media/service-publish-to-powerpoint/powerbi_to_powerpoint_6.png)

Wat u verder doet met uw PowerPoint-presentatie, of met de afbeeldingen met hoge resolutie, is geheel aan u!

## <a name="limitations"></a>Beperkingen
Er zijn enkele overwegingen en beperkingen waar u rekening mee moet houden bij het werken met de functie **Exporteren naar PowerPoint**.

* **R-visualisaties** worden momenteel niet ondersteund. Dergelijke visuele elementen worden als een blanco afbeelding naar PowerPoint geëxporteerd met een foutmelding die aangeeft dat het visuele element niet wordt ondersteund.
* **Aangepaste visuele elementen** die zijn **gecertificeerd** worden ondersteund. Voor meer informatie over gecertificeerde aangepaste visuele elementen, inclusief een certificatie verkrijgen voor een aangepast visueel element, zie [Een certificatie verkrijgen voor een aangepast visueel element](power-bi-custom-visuals-certified.md). Aangepaste visuele elementen die niet gecertificeerd zijn, worden niet ondersteund. Dergelijke visuele elementen worden als een blanco afbeelding naar PowerPoint geëxporteerd met een foutmelding die aangeeft dat het visuele element niet wordt ondersteund.
* **Gecertificeerde aangepaste visuele elementen** worden ondersteund. Een gecertificeerd aangepast visueel element is goedgekeurd voor gebruik met Power BI, voldoet aan bepaalde codevereisten en heeft strenge veiligheidstests heeft doorstaan. Zie voor [meer informatie over **gecertificeerde aangepaste visuele elementen**](power-bi-custom-visuals-certified.md).
* Rapporten met meer dan 15 rapportpagina's kunnen momenteel niet worden geëxporteerd.
* Het proces van het exporteren van een rapport naar PowerPoint kan enkele minuten duren. Factoren die de benodigde tijd kunnen beïnvloeden zijn onder meer de structuur van het rapport en de huidige belasting van de Power BI-service.
* Als het menu-item **Exporteren naar PowerPoint (Preview)** niet beschikbaar is in de Power BI-service, heeft uw tenantbeheerder de functie waarschijnlijk uitgeschakeld. Neem contact op met uw tenantbeheerder voor meer informatie.
* Achtergrondafbeeldingen worden bijgesneden binnen het begrenzingsgebied van de grafiek. Het wordt ten zeerste aanbevolen om achtergrondafbeeldingen te verwijderen voordat u naar PowerPoint exporteert.
* **In-sessie interactiviteit** zoals markeren en filteren, inzoomen, enzovoort, worden nog niet ondersteund bij het exporteren naar PowerPoint. In de geëxporteerde PowerPoint worden de oorspronkelijke visuele elementen weergegeven zoals ze zijn opgeslagen in het rapport.
* Pagina's in PowerPoint worden altijd aangemaakt in het standaard 9:16-formaat, ongeacht de oorspronkelijke paginaformaten of afmetingen in het Power BI-rapport.
* Rapporten die eigendom zijn van een gebruiker buiten uw Power BI-tenantdomein (zoals een rapport dat eigendom is van iemand buiten uw organisatie en dat met u wordt gedeeld) kunnen niet worden gepubliceerd naar PowerPoint.
* Als u een dashboard deelt met iemand buiten uw organisatie (en daarmee een gebruiker die niet in uw Power BI-tenant is) dan kan die gebruiker de aan het gedeelde dashboard gekoppelde rapporten niet exporteren naar PowerPoint. Als u bijvoorbeeld aaron@contoso.com bent, kunt u delen met david@cohowinery.com. Maar david@cohowinery.com kan de gekoppelde rapporten niet exporteren naar PowerPoint.

## <a name="next-steps"></a>Volgende stappen
[Analyze in Excel](service-analyze-in-excel.md) (Analyseren in Excel)

[Excel-gegevens in Power BI](service-excel-workbook-files.md)

[Een aangepast visueel element laten certificeren](power-bi-custom-visuals-certified.md)
