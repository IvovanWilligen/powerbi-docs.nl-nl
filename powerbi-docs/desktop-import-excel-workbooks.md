---
title: Excel-werkmappen in Power BI Desktop importeren
description: Excel-werkmappen in Power BI Desktop importeren
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
ms.date: 09/06/2017
ms.author: davidi
ms.openlocfilehash: 5daed750b6e9b80c04f568c39b4e0931c01bbc05
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/15/2017
---
# <a name="import-excel-workbooks-into-power-bi-desktop"></a>Excel-werkmappen in Power BI Desktop importeren
Met **Power BI Desktop** kunt u eenvoudig Excel-werkmappen met Power Query-query's, Power Pivot-modellen en Power View-werkbladen in Power BI Desktop importeren. Er worden automatisch rapporten en visualisaties gemaakt op basis van de Excel-werkmap, en wanneer ze eenmaal zijn geïmporteerd kunt u deze rapporten blijven verbeteren en verfijnen met Power BI Desktop, met behulp van de bestaande functies en nieuwe functies die met elke maandelijkse update van Power BI Desktop worden uitgebracht.

We zijn van plan in de toekomst aanvullende communicatie tussen Excel en Power BI Desktop aan te bieden(zoals importeren/exporteren). Deze huidige mogelijkheid om werkmappen te importeren in Power BI Desktop maakt het bestaande Excel-gebruikers mogelijk aan de slag te gaan met Power BI Desktop.

## <a name="how-do-i-import-an-excel-workbook"></a>Hoe kan ik een Excel-werkmap importeren?
Als u een werkmap wilt importeren, selecteert u in Power BI Desktop **Bestand -\> Importeren -\> Inhoud van Excel-werkmap**.

![](media/desktop-import-excel-workbooks/importexceltopbi_1.png)

Er verschijnt een venster waarin u de te importeren werkmap kunt selecteren. Er is momenteel geen beperking aan de omvang of het aantal objecten in de werkmap, maar met grotere werkmappen duurt het langer om ze in Power BI Desktop te analyseren en te importeren.

> [!NOTE]
> Als u Excel-bestanden wilt laden of importeren vanuit **gedeelde mappen van OneDrive voor Bedrijven** of uit mappen van **Office 365-groepen**, gebruikt u de URL van het Excel-bestand en voert u deze in de **Web**-gegevensbron in Power BI Desktop. Er zijn enkele stappen die u moet volgen om de URL voor **OneDrive voor Bedrijven** op de juiste manier in te delen. Raadpleeg [Use OneDrive for Business links in Power BI Desktop](desktop-use-onedrive-business-links.md) (Koppelingen van OneDrive voor Bedrijven gebruiken in Power BI Desktop) voor meer informatie en de juiste stappen.
> 
> 

Nadat u een werkmap hebt geselecteerd, wordt de werkmap in Power BI Desktop geanalyseerd en geconverteerd naar een Power BI Desktop-bestand (.pbix). Dit is een eenmalige gebeurtenis. Nadat het Power BI Desktop-bestand met deze stappen is gemaakt, is het niet meer afhankelijk van de oorspronkelijke Excel-werkmap en kan het worden gewijzigd of veranderd (en opgeslagen, en gedeeld) zonder de oorspronkelijke werkmap te beïnvloeden.

![](media/desktop-import-excel-workbooks/importexceltopbi_2.png)

Nadat het importeren is voltooid, wordt de pagina **Overzicht** weergegeven, waarin de geconverteerde items worden beschreven. De pagina bevat ook een lijst met alle items die niet konden worden geïmporteerd.

![](media/desktop-import-excel-workbooks/importexceltopbi_3.png)

Wanneer u **Sluiten** selecteert, wordt het rapport in Power BI Desktop geladen. In de volgende afbeelding ziet u Power BI Desktop nadat een Excel-werkmap is geïmporteerd. Power BI Desktop heeft het rapport automatisch geladen op basis van de inhoud van de werkmap.

![](media/desktop-import-excel-workbooks/importexceltopbi_4.png)

Nu de werkmap is geïmporteerd, kunt u met behulp van de functies en mogelijkheden van Power BI Desktop verder werken aan het rapport en bijvoorbeeld nieuwe visualisaties maken, gegevens toevoegen en nieuwe pagina's in het rapport maken.

## <a name="which-workbook-elements-are-imported"></a>Welke werkmap-elementen worden geïmporteerd?
Power BI Desktop kan de volgende elementen, gewoonlijk aangeduid als *objecten*, in Excel importeren.

| Object in Excel-werkmap | Eindresultaat in Power BI Desktop-bestand |
| --- | --- |
| Power Query-query’s |Alle Power Query-query's uit Excel worden geconverteerd naar query's in Power BI Desktop. Als er querygroepen waren gedefinieerd in de Excel-werkmap, wordt dezelfde organisatie gerepliceerd in Power BI Desktop. Alle query's worden geladen, tenzij ze in Excel zijn ingesteld op 'Alleen verbinding maken'. Het laadgedrag kan worden aangepast in het dialoogvenster **Eigenschappen** van het tabblad **Start** tabblad van **Query-editor** in Power BI Desktop. |
| Externe Power Pivot-gegevensverbindingen |Alle externe Power Pivot-gegevensverbindingen worden geconverteerd naar query's in Power BI Desktop. |
| Gekoppelde tabellen of tabellen uit de huidige werkmap |Als er een werkbladtabel in Excel is gekoppeld aan het gegevensmodel of gekoppeld aan een query (met behulp van *Van tabel* of de functie *Excel.CurrentWorkbook()* in M), worden de volgende opties weergegeven     1. De tabel in het Power BI Desktop-bestand importeren. Dit is een momentopname van de gegevens, waarna u de gegevens in de tabel niet in Power BI Desktop kunt bewerken. Er geldt een maximale grootte van 1 miljoen tekens (het totaal van alle kolomkoppen en cellen) voor tabellen die zijn gemaakt met deze optie.    2. Verbinding houden met de oorspronkelijke werkmap. U kunt ook een verbinding met de oorspronkelijke Excel-werkmap behouden. Dan haalt Power BI Desktop bij elke vernieuwing de meest recente inhoud in deze tabel op, net als bij elke andere query op een Excel-werkmap in Power BI Desktop. |
| Berekende kolommen, metingen, categorieën en relaties van gegevensmodellen |Deze gegevensmodelobjecten worden geconverteerd naar de equivalente objecten in Power BI Desktop. Houd er rekening mee dat er bepaalde gegevenscategorieën zijn die nog niet beschikbaar zijn in Power BI Desktop, zoals **Afbeelding**. In dergelijke gevallen wordt de gegevenscategorie-informatie voor de desbetreffende kolommen weer ingesteld op de standaardinstelling. |
| Power View-werkbladen |Er wordt een nieuwe rapportpagina gemaakt voor elk Power View-werkblad in Excel. De namen en de volgorde van deze rapportpagina's komen overeen met de oorspronkelijke Excel-werkmap. |

## <a name="are-there-any-limitations-to-importing-a-workbook"></a>Zijn er beperkingen voor het importeren van een werkmap?
Er zijn enkele beperkingen voor het importeren van een werkmap in Power BI Desktop, namelijk de volgende:

1. **Externe verbindingen met Analysis Services-modellen in tabelvorm:** In Excel 2013 is het mogelijk een verbinding te maken met SQL Server Analysis Services modellen in tabelvorm en Power View-rapporten te maken op basis van deze modellen zonder de gegevens te hoeven importeren. Dit type verbinding wordt momenteel niet ondersteund als onderdeel van het importeren van Excel-werkmappen in Power BI Desktop, maar komt beschikbaar in een toekomstige update. In de tussentijd moet u deze externe verbindingen opnieuw maken in Power BI Desktop.
2. **KPI's:** dit type gegevensmodelobject wordt momenteel niet ondersteund in Power BI Desktop. Daarom worden KPI's overgeslagen bij het importeren van een Excel-werkmap in Power BI Desktop.
3. **Hiërarchieën:** dit type gegevensmodelobject wordt momenteel niet ondersteund in Power BI Desktop. Daarom worden hiërarchieën overgeslagen bij het importeren van een Excel-werkmap in Power BI Desktop.
4. **Binaire-gegevenskolommen:** dit type gegevensmodelkolom wordt momenteel niet ondersteund in Power BI Desktop. Kolommen met binaire gegevens worden verwijderd uit de resulterende tabel in Power BI Desktop.
5. **Niet-ondersteunde Power View-elementen:** er zijn enkele functies in Power View die nog niet beschikbaar zijn in Power BI Desktop, zoals thema's of bepaalde soorten visualisaties (spreidingsdiagrammen met afspeelas, inzoom gedrag, enzovoort). Deze niet-ondersteunde visualisaties veroorzaken *Niet-ondersteunde visualisatie*-berichten op de betreffende locaties in het Power BI Desktop-rapport, die u naar behoefte kunt verwijderen of opnieuw configureren.
6. **Benoemde bereiken met** ***Van tabel*** **in Power Query, of met**  ***Excel.CurrentWorkbook*** **in M:** het importeren van gegevens uit deze benoemde bereiken in Power BI Desktop wordt momenteel niet ondersteund, maar het is een geplande update voor Power BI Desktop. Deze benoemde bereiken worden momenteel in Power BI Desktop geladen als een verbinding met de externe Excel-werkmap.
7. **PowerPivot naar SSRS:** externe PowerPivot-verbindingen naar SQL Server Reporting Services (SSRS) worden momenteel niet ondersteund, omdat deze gegevensbron momenteel niet beschikbaar is in Power BI Desktop.
