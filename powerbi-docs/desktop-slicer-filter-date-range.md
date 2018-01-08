---
title: Een relatieve datumslicer of -filter in Power BI Desktop gebruiken
description: Informatie over het gebruik van een slicer of filter om relatieve datumbereiken te beperken in Power BI Desktop
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
ms.date: 07/20/2017
ms.author: davidi
ms.openlocfilehash: f3138e45386c07e20342b495938ea84022c072c2
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/13/2017
---
# <a name="use-a-relative-date-slicer-and-filter-in-power-bi-desktop"></a>Een relatieve datumslicer en -filter in Power BI Desktop gebruiken
Met de **relatieve datumslicer** of het **relatieve datumfilter** kunt u tijdgebaseerde filters toepassen op een datumkolom in het gegevensmodel. U kunt bijvoorbeeld de **relatieve datumslicer** gebruiken om alleen gegevens weer te geven over verkopen die hebben plaatsgevonden in de afgelopen 30 dagen (of maand of kalendermaanden, enzovoort). En wanneer u de gegevens vernieuwt, wordt de juiste relatieve datumbeperking automatisch toegepast door de relatieve periode.

![](media/desktop-slicer-filter-date-range/relative-date-range-slicer-filter_01.png)

## <a name="using-the-relative-date-range-slicer"></a>De relatieve datumbereikslicer gebruiken
U kunt de relatieve datumslicer net als elke andere slicer gebruiken. Maak eenvoudig een visueel **slicer**-element voor uw rapport en selecteer vervolgens een datumwaarde voor de waarde **Veld**. Op de volgende afbeelding is *OrderDate* geselecteerd.

![](media/desktop-slicer-filter-date-range/relative-date-range-slicer-filter_02.png)

Selecteer het dakje in de rechterbovenhoek van de **relatieve datumslicer**. Er wordt dan een menu weergegeven.

![](media/desktop-slicer-filter-date-range/relative-date-range-slicer-filter_03.png)

Selecteer *Relatief* voor de relatieve datumslicer.

Vervolgens kunt u de instellingen selecteren. Voor de eerste vervolgkeuzelijst in de *relatieve datumslicer* kunt u een keuze maken uit de volgende opties:

* Laatste
* Volgende
* Deze/dit

Deze selecties worden weergegeven op de volgende afbeelding.

![](media/desktop-slicer-filter-date-range/relative-date-range-slicer-filter_04.png)

Voor de volgende (middelste) instelling in de *relatieve datumslicer* kunt u een getal invoeren om het relatieve datumbereik te definiëren.

Voor de derde instelling kunt u de datummeetwaarde selecteren en kunt u kiezen uit de volgende opties:

* Dagen
* Weken
* Weken (kalender)
* Maanden
* Maanden (kalender)
* Jaren
* Jaren (kalender)

Deze selecties worden weergegeven op de volgende afbeelding.

![](media/desktop-slicer-filter-date-range/relative-date-range-slicer-filter_05.png)

Een voorbeeld: u selecteert *Maanden* in die lijst en voert 2 in voor de middelste instelling. Het volgende gebeurt: als het vandaag 20 juli is, geven de gegevens die zijn opgenomen in de visuele elementen en worden beperkt door de slicer gegevens weer voor de vorige twee maanden, vanaf 20 mei tot 20 juli (de datum van vandaag).

Ter vergelijking: als u *Maanden (kalender)* hebt geselecteerd, geven de visuele elementen die worden beperkt gegevens weer van 1 mei tot en met 30 juni (de laatste twee volledige kalendermaanden).

## <a name="using-the-relative-date-range-filter"></a>Het relatieve datumbereikfilter gebruiken
U kunt ook een relatief datumbereikfilter voor uw rapportpagina of het hele rapport maken. Hiertoe sleept u eenvoudigweg een datumveld naar het gebied **Filters op paginaniveau** of **Filters op rapportniveau** in het deelvenster **Veld**, zoals wordt weergegeven op de volgende afbeelding.

![](media/desktop-slicer-filter-date-range/relative-date-range-slicer-filter_06.png)

Zodra dit zich daar bevindt, kunt u het relatieve datumbereik op dezelfde manier wijzigen als hoe u de **relatieve datumslicer** hebt aangepast. Selecteer **Relatieve datumfilter** in de vervolgkeuzelijst **Filtertype**.

![](media/desktop-slicer-filter-date-range/relative-date-range-slicer-filter_07.png)

Als **Relatieve datumfilter** is geselecteerd, ziet u drie secties die u kunt wijzigen, inclusief een numeriek middelste vak, net als bij de slicer.

![](media/desktop-slicer-filter-date-range/relative-date-range-slicer-filter_08.png)

En dat is het enige dat u hoeft te doen om deze relatieve datumbeperkingen in uw rapporten te gebruiken.

## <a name="limitations-and-considerations"></a>Beperkingen en overwegingen
De volgende beperkingen en overwegingen zijn momenteel van toepassing op de **relatieve datumbereikslicer** en het relatieve datumbereikfilter.

* Gegevensmodellen in **Power BI** bevatten geen informatie over de tijdzone. De modellen kunnen tijden opslaan, maar er is geen indicatie van de tijdzone waarin ze zich bevinden.
* De slicer en het filter zijn altijd op basis van de tijd in UTC, dus als u een filter in een rapport configureert en dit te naar een collega in een andere tijdzone verzendt, ziet u beide dezelfde gegevens. Als u zich echter niet in de UTC-tijdzone bevindt, ziet u mogelijk gegevens voor een ander tijdsverschil dan verwacht.
* Gegevens die zijn vastgelegd in een lokale tijdzone kunnen worden geconverteerd naar UTC met behulp van de **Query-editor**.
