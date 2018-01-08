---
title: Het deelvenster Analyse in Power BI Desktop gebruiken
description: Dynamische referentielijnen maken voor visuele elementen in Power BI Desktop
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
ms.date: 10/12/2017
ms.author: davidi
ms.openlocfilehash: add95532f645c143aea0f58200f9e3b1467320d0
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/15/2017
---
# <a name="using-the-analytics-pane-in-power-bi-desktop"></a>Het deelvenster Analyse in Power BI Desktop gebruiken
Met het deelvenster **Analyse** in **Power BI Desktop** kunt u dynamische *referentielijnen* toevoegen aan visuele elementen en de aandacht richten op belangrijke trends of inzichten. U vindt het deelvenster **Analyse** in het gedeelte **Visualisaties** van Power BI Desktop vanaf de release van augustus 2016 (versie 2.37.4464.321 of hoger), zoals hieronder weergegeven.

![](media/desktop-analytics-pane/analytics-pane_1.png)

> [!NOTE]
> Het deelvenster **Analyse** wordt alleen weergegeven wanneer u een visueel element op het canvas van Power BI Desktop selecteert.
> 
> 

## <a name="enable-forecasting-preview"></a>Prognose inschakelen (preview)
Met de release van september 2016 van **Power BI Desktop** (versie 2.39.4526.362 of hoger) kunt u daarnaast ook *prognoses* uitvoeren via het deelvenster **Analyse**. U kunt deze preview-functie inschakelen door te gaan naar **Bestand > Opties en instellingen > Opties** en vervolgens **Voorbeeldfuncties** in het linkerdeelvenster in te schakelen. Schakel het selectievakje naast **Prognose** in, zoals in de volgende afbeelding. U moet **Power BI Desktop** opnieuw opstarten om de wijzigingen door te voeren.

![](media/desktop-analytics-pane/analytics-pane_1b.png)

## <a name="using-the-analytics-pane"></a>Het deelvenster Analyse gebruiken
Met het deelvenster **Analyse** kunt u de volgende soorten dynamische referentielijnen maken (niet alle lijnen zijn beschikbaar voor alle soorten visuele elementen):

* Constante lijn voor de X-as
* Constante lijn voor de Y-as
* Lijn voor minimum
* Lijn voor maximum
* Lijn voor gemiddelde
* Lijn voor mediaan
* Lijn voor percentiel

In de volgende secties ziet u hoe u het deelvenster **Analyse** en dynamische referentielijnen kunt gebruiken in uw visualisaties.

Voer de volgende stappen uit als u de beschikbare dynamische referentielijnen voor een visueel element wilt weergeven:

1. Selecteer of maak een visueel element en selecteer vervolgens het pictogram **Analyse** in het gedeelte **Visualisaties**.
   
   ![](media/desktop-analytics-pane/analytics-pane_2.png)
2. Selecteer de pijl-omlaag voor het type lijn dat u wilt maken om de opties ervoor uit te breiden. In dit geval selecteren we **Lijn voor gemiddelde**.
   
   ![](media/desktop-analytics-pane/analytics-pane_3.png)
3. U voegt een nieuwe lijn toe door **+ Toevoegen** te selecteren. U kunt vervolgens een naam voor de lijn opgeven door te dubbelklikken op het tekstvak en daarna de naam te typen.
   
   U beschikt over allerlei opties voor de lijn, zoals *kleur*, *transparantie*, *stijl* en *positie* (ten opzichte van de gegevenselementen van het visuele element) selecteren en aangeven of een label moet worden toegevoegd. En wat belangrijker is, u kunt selecteren op welke **meting** in het visuele element u de lijn wilt baseren door de vervolgkeuzelijst **Meting** te selecteren die automatisch wordt gevuld met gegevenselementen uit het visuele element. In dit geval selecteren we *Weather* (Weer) als meting, voegen we het label *Average Weather* (Gemiddelde weer) toe en passen we enkele van de andere opties toe zoals hieronder wordt weergegeven.
   
   ![](media/desktop-analytics-pane/analytics-pane_4.png)
4. Als u een gegevenslabel wilt weergeven, schakelt u de schuifregelaar **Gegevenslabel** in. Als u doet dit, krijgt u allerlei extra opties voor uw gegevenslabel, zoals wordt weergegeven in de volgende afbeelding.
   
   ![](media/desktop-analytics-pane/analytics-pane_5.png)
5. Let op het getal dat wordt weergegeven naast het item **Lijn voor gemiddelde** in het deelvenster **Analyse**. Zo weet u hoeveel dynamische lijnen het visuele element momenteel bevat en van welk type. Als we een **Lijn voor maximum** toevoegen voor *Cost of Living* (Kosten van levensonderhoud), ziet u dat het deelvenster **Analyse** nu aangeeft dat ook een dynamische referentielijn van het type **Lijn voor maximum** is toegepast op dit visuele element.
   
   ![](media/desktop-analytics-pane/analytics-pane_6.png)

Als op het visuele element dat u hebt geselecteerd (in dit geval een **kaart**) geen dynamische referentielijnen kunnen worden toegepast, ziet u het volgende wanneer u het deelvenster **Analyse** selecteert.

![](media/desktop-analytics-pane/analytics-pane_7.png)

Er zijn allerlei interessante inzichten die u kunt benadrukken door dynamische referentielijnen te maken met het deelvenster **Analyse**.

We plannen meer functies en mogelijkheden, zoals uitbreiden op welke visuele elementen dynamische referentielijnen kunnen worden toegepast, dus kom regelmatig terug om te kijken wat er nieuw is.

## <a name="apply-forecasting"></a>Prognose toepassen
U kunt de functie **Prognose** gebruiken door een visueel element te selecteren en vervolgens de sectie **Prognose** van het deelvenster **Analyse** uit te breiden. U kunt allerlei soorten invoer opgeven om de prognose te wijzigen, zoals *Prognoseduur*, *Betrouwbaarheidsinterval* en andere. In de volgende afbeelding ziet u een visueel element met een eenvoudige lijn waarop een prognose is toegepast, maar u kunt ook uw eigen verbeelding gebruiken (en experimenteren met de functie *Prognose*) om te zien hoe u deze kunt toepassen op uw modellen.

![](media/desktop-analytics-pane/analytics-pane_8.png)

## <a name="limitations"></a>Beperkingen
De mogelijkheid om dynamische referentielijnen te gebruiken is gebaseerd op het type visueel element dat wordt gebruikt. In de volgende lijst wordt aangegeven welke dynamische lijnen momenteel beschikbaar zijn voor welke visuele elementen:

Volledig gebruik van dynamische lijnen is beschikbaar voor de volgende visuele elementen:

* Vlakdiagram
* Lijndiagram
* Spreidingsdiagram
* Gegroepeerd kolomdiagram
* Gegroepeerd staafdiagram

De volgende visuele elementen kunnen alleen een *constante lijn* uit het deelvenster **Analyse** gebruiken:

* Gestapeld vlakdiagram
* Gestapeld staafdiagram
* Gestapeld kolomdiagram
* 100% gestapeld staafdiagram
* 100% gestapeld kolomdiagram

Voor de volgende visuele elementen is een *trendlijn* momenteel de enige optie:

* Niet-gestapeld lijndiagram
* Gegroepeerd kolomdiagram

Tot slot kunnen voor niet-Cartesische visuele elementen momenteel geen dynamische lijnen uit het deelvenster **Analyse** worden toegepast, zoals:

* Matrix
* Cirkeldiagram
* Ringdiagram
* Tabel

## <a name="next-steps"></a>Volgende stappen
U kunt veel verschillende dingen doen met Power BI Desktop. Bekijk de volgende bronnen voor meer informatie over de vele mogelijkheden:

* [Wat is er nieuw in Power BI Desktop](desktop-latest-update.md)
* [Power BI Desktop downloaden](desktop-get-the-desktop.md)
* [Aan de slag met Power BI Desktop](desktop-getting-started.md)
* [Queryoverzicht met Power BI Desktop](desktop-query-overview.md)
* [Gegevenstypen in Power BI Desktop](desktop-data-types.md)
* [Gegevens vormgeven en combineren met Power BI Desktop](desktop-shape-and-combine-data.md)
* [Algemene querytaken in Power BI Desktop](desktop-common-query-tasks.md)    
