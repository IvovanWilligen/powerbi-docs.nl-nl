---
title: Tabelvisualisaties in Power BI-rapporten en -dashboards
description: Zelfstudie over het werken met tabelvisualisaties in Power BI-rapporten en -dashboards, met informatie over het aanpassen van de kolombreedte.
author: mihart
manager: kvivek
ms.reviewer: ''
featuredvideoid: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 06/24/2019
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: a0525d448d5337c2c1613d8bc8f6d332a05b13e3
ms.sourcegitcommit: 58c649ec5fd2447a0f9ca4c4d45a0e9fff2f1b6a
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/27/2019
ms.locfileid: "67409482"
---
# <a name="tables-in-power-bi-reports-and-dashboards"></a>Tabellen in Power BI-rapporten en -dashboards

Een tabel is een raster met gerelateerde gegevens in een logische reeks rijen en kolommen. Het kan ook koppen en een rij voor totalen bevatten. Tabellen werken goed met kwantitatieve vergelijkingen waarbij u veel waarden voor één categorie bekijkt. Deze tabel geeft bijvoorbeeld vijf verschillende eenheden voor **Categorie** weer.

![Schermopname van een tabel die vijf verschillende eenheden voor Categorie weergeeft.](media/power-bi-visualization-tables/table.png)

U kunt tabellen in rapporten maken en meerdere elementen in de tabel kruislings markeren met andere visuals op dezelfde rapportpagina. U kunt rijen en kolommen, en zelfs afzonderlijke cellen selecteren en deze kruislings markeren. Bovendien kunt u afzonderlijke cellen en selecties van meerdere cellen kopiëren en in andere toepassingen plakken.

## <a name="when-to-use-a-table"></a>Wanneer u een tabel gebruikt

Tabellen zijn een prima keuze:

* om gedetailleerde gegevens en exacte waarden (in plaats van visuele weergaven) te bekijken en vergelijken;

* om gegevens in tabelvorm weer te geven;

* om numerieke gegevens per categorie weer te geven.

> [!NOTE]
> Als een tabel te veel waarden bevat, kunt u deze converteren naar een matrix en/of inzoomen. Het maximum aantal weergegeven gegevenspunten in een tabel is 3500.

## <a name="prerequisites"></a>Vereisten

* De Power BI-service of Power BI Desktop

* Het rapport Voorbeeld van een retailanalyse

## <a name="get-the-retail-analysis-sample-report"></a>Het rapport Voorbeeld van een retailanalyse downloaden

In deze instructies wordt het voorbeeld van een retailanalyse gebruikt. Voor het maken van een visualisatie hebt u bewerkmachtigingen voor de gegevensset en het rapport nodig. De voorbeelden van Power Bi zijn allemaal bewerkbaar. Als iemand een rapport met u deelt, kunt u geen visualisaties maken in het rapport. Als u mee wilt doen, downloadt u het rapport [Voorbeeld van een retailanalyse](../sample-datasets.md).

Nadat u de gegevensset **Voorbeeld van een retailanalyse** hebt opgehaald, kunt u aan de slag.

## <a name="create-a-table"></a>Een tabel maken

U gaat de tabel aan het begin van dit artikel namaken om de omzet per artikelcategorie weer te geven.

1. Ga naar **Mijn werkruimte** en selecteer **Gegevenssets** > **Een rapport maken**.

    ![Schermopname van Gegevenssets > Een rapport maken.](media/power-bi-visualization-tables/power-bi-create-a-report.png)

1. In het deelvenster **Velden** selecteert u **Artikel** > **Categorie**.

    Power BI maakt automatisch een tabel waarin alle categorieën worden weergegeven.

    ![resultaat van categorie toevoegen](media/power-bi-visualization-tables/power-bi-table1.png)

1. Selecteer **Verkoop > Gemiddelde eenheidsprijs** en **Verkoop > Omzet van afgelopen jaar**

1. Selecteer vervolgens **Verkoop > Omzet van dit jaar** en selecteer alle drie de opties: **Waarde**, **Doel** en **Status**.

1. Zoek in het deelvenster **Visualisaties** het venster **Waarden** en versleep de waarden totdat de volgorde van de grafiekkolommen overeenkomt met de eerste afbeelding op deze pagina. Het venster **Waarden** komt er zo uit te zien:

    ![Waarden](media/power-bi-visualization-tables/power-bi-table2.png)

1. Maak de tabel aan het dashboard vast door het speldpictogram te selecteren ![punaise](media/power-bi-visualization-tables/pbi_pintile.png) in de rechterbovenhoek van de visual.

## <a name="format-the-table"></a>De tabel opmaken

Er zijn veel verschillende manieren om een tabel op te maken. Slechts een paar van die manieren komen hier aan bod. Een uitstekende manier om de andere opmaakopties te ontdekken, is door het deelvenster **Opmaak** te openen (het pictogram met de verfroller ![verfroller](media/power-bi-visualization-tables/power-bi-format.png)) en verschillende opties uit te proberen.

* Probeer het tabelraster op te maken. Hier gaat u een blauw verticaal raster toevoegen, ruimte aan de rijen toevoegen, de contouren dikker maken en de tekst groter maken.

    ![Rasterkaart](media/power-bi-visualization-tables/power-bi-table-gridnew.png)

    ![tabel met resultaten](media/power-bi-visualization-tables/power-bi-table-grid3.png)

* Voor de kolomkoppen wijzigt u de achtergrondkleur, voegt u contouren toe en maakt u het lettertype groter.

    ![Kolomkoppenkaart](media/power-bi-visualization-tables/power-bi-table-column-headers.png)

    ![opmaak koppen in tabel](media/power-bi-visualization-tables/power-bi-table-column2.png)

* U kunt zelfs opmaak toepassen op afzonderlijke kolommen en kolomkoppen. Eerst breidt u **Veldopmaak** uit en vervolgens selecteert u de op te maken kolom in de vervolgkeuzelijst. Afhankelijk van de kolomwaarden kunt u met **Veldopmaak** dingen instellen zoals weergave-eenheden, tekstkleur, aantal decimalen, achtergrond, uitlijning en meer. Nadat u de instellingen hebt aangepast, bepaalt u of u die instellingen zowel op de veldnamenrij als op de totalenrij toepast.

    ![Veldopmaak voor ‘Omzet van dit jaar’](media/power-bi-visualization-tables/power-bi-field-formatting.png)

    ![Veldopmaak voor ‘Omzet van dit jaar’ in de tabel](media/power-bi-visualization-tables/power-bi-field-formatting-1.png)

* Na een paar extra opmaakstappen is dit het resultaat.

    ![tabel met alle opmaak tot nu toe](media/power-bi-visualization-tables/power-bi-table-format.png)

### <a name="conditional-formatting"></a>Voorwaardelijke opmaak

*Voorwaardelijke opmaak* is een bepaald type opmaak. Power BI past voorwaardelijke opmaak toe op velden in het venster **Waarden** in het deelvenster **Visualisaties**.

Met voorwaardelijke opmaak voor tabellen kunt u aangepaste celachtergrondkleuren en kleuren voor lettertypen opgeven op basis van celwaarden, inclusief het gebruik van kleurovergangen.

1. Selecteer in het deelvenster **Visualisaties** het pictogram voor **Velden** ![het pictogram voor velden](media/power-bi-visualization-tables/power-bi-fields-icon.png).

1. Selecteer de pijl omlaag naast de waarde in het venster **Waarden** die u wilt opmaken (of klik met de rechtermuisknop op het veld).

    > [!NOTE]
    > U kunt voorwaardelijke opmaak alleen beheren voor velden in het gebied **Waarden** van het venster **Velden**.

    ![pad naar Achtergrondkleurschalen](media/power-bi-visualization-tables/power-bi-conditional-formatting-background.png)

1. Selecteer **Achtergrondkleur**.

1. In het dialoogvenster dat wordt weergegeven, kunt u de kleur, en de waarden voor **Minimum** en **Maximum** configureren. Als u de optie **Afwijken** selecteert, kunt u desgewenst ook een waarde configureren voor **Centreren**.

    ![scherm achtergrondkleurschalen](media/power-bi-visualization-tables/power-bi-conditional-formatting-background2.png)

    Laten we wat aangepaste opmaak toepassen op de waarden voor Gemiddelde eenheidsprijs. Selecteer **Afwijken**, voeg wat kleuren toe en selecteer **OK**.

    ![tabel met afwijkende kleuren](media/power-bi-visualization-tables/power-bi-conditional-formatting-data-background.png)
1. Voeg een nieuw veld toe aan de tabel met positieve en negatieve waarden. Selecteer **Verkoop > Afwijking van totale verkoop**.

    ![toont een nieuw veld helemaal rechts](media/power-bi-visualization-tables/power-bi-conditional-formatting2.png)

1. Voeg voorwaardelijke opmaak toe aan de gegevensbalk door de pijl omlaag te selecteren naast **Afwijking van totale verkoop** en **Voorwaardelijke opmaak > Gegevensbalken** te kiezen.

    ![pad naar geselecteerde gegevensbalken](media/power-bi-visualization-tables/power-bi-conditional-formatting-data-bars.png)

1. In het dialoogvenster dat wordt weergegeven stelt u kleuren in voor **Positieve balk** en **Negatieve balk**, selecteert u de optie **Alleen balk weergeven** en brengt u eventueel nog andere wijzigingen aan.

    ![vinkje voor Alleen balk weergeven](media/power-bi-visualization-tables/power-bi-data-bars.png)

1. Selecteer **OK**.

    Gegevensbalken vervangen de numerieke waarden in de tabel, waardoor deze eenvoudiger te lezen is.

    ![dezelfde tabel maar met balken in de laatste kolom](media/power-bi-visualization-tables/power-bi-conditional-formatting-data-bars2.png)

Als u voorwaardelijke opmaak uit een visualisatie wilt verwijderen, klikt u opnieuw met de rechtermuisknop op het veld en selecteert u **Voorwaardelijke opmaak verwijderen**.

> [!TIP]
> Voorwaardelijke opmaak is ook beschikbaar in het deelvenster **Opmaak**. Selecteer de waarde die u wilt opmaken en stel vervolgens **Kleurschalen** of **Gegevensbalken** in op **Aan** om de standaardinstellingen toe te passen. Als u de instellingen wilt aanpassen, selecteert u **Geavanceerde besturingselementen**.

## <a name="copy-values-from-power-bi-tables-for-use-in-other-applications"></a>Waarden kopiëren uit Power BI-tabellen voor gebruik in andere toepassingen

Uw tabel of matrix bevat mogelijk inhoud die u wilt gebruiken in andere toepassingen, bijvoorbeeld Dynamics CRM, Excel of zelfs andere Power BI-rapporten. Als u in Power BI met de rechtermuisknop in een cel klikt, kopieert u de gegevens in één cel of in een selectie cellen naar uw klembord en plakt u deze in de andere toepassingen.

Als u de waarde in één cel wilt kopiëren, gaat u als volgt te werk:

1. Selecteer de cel die u wilt kopiëren.

1. Klik met de rechtermuisknop in de cel.

1. Selecteer **Kopiëren** > **Waarde kopiëren**.

    ![kopieeropties](media/power-bi-visualization-tables/power-bi-copy-value.png)

    Als u de onopgemaakte celwaarde naar uw klembord hebt gekopieerd, kunt u deze in een andere toepassing plakken.

Als u meer dan één cel wilt kopiëren, gaat u als volgt te werk:

1. Selecteer een reeks cellen of gebruik **Ctrl** om één of meer cellen te selecteren.

1. Klik met de rechtermuisknop in een van de cellen die u hebt geselecteerd.

1. Selecteer **Kopiëren** > **Selectie kopiëren**.

    ![kopieeropties](media/power-bi-visualization-tables/power-bi-copy-selection.png)

    De kolomkoppen en rijkoppen zijn opgenomen in de kopie.

    ![plakken in Excel](media/power-bi-visualization-tables/power-bi-paste-selection.png)

## <a name="adjust-the-column-width-of-a-table"></a>De kolombreedte van een tabel aanpassen

In Power BI wordt soms een kolomkop in een rapport en in een dashboard afgekapt. Beweeg de muisaanwijzer over de ruimte aan de rechterkant van de kop om de dubbele pijlen zichtbaar te maken. Selecteer deze en versleep ze om de volledige kolomnaam weer te geven.

![videoclose-up van kolom vergroten of verkleinen](media/power-bi-visualization-tables/resizetable.gif)

## <a name="considerations-and-troubleshooting"></a>Aandachtspunten en probleemoplossing

Wanneer u kolomopmaak toepast, kunt u slechts één uitlijningsoptie per kolom kiezen: **Automatisch**, **Links**, **Centreren**, **Rechts**. Doorgaans bevat een kolom alleen tekst of alleen getallen, en geen combinatie daarvan. In het geval dat een kolom zowel getallen als tekst bevat, worden met de optie **Automatisch** teksten links en getallen rechts uitgelijnd. Dit gedrag ondersteunt talen die van links naar rechts worden gelezen.

## <a name="next-steps"></a>Volgende stappen

* [Treemaps in Power BI](power-bi-visualization-treemaps.md)

* [Visualization types in Power BI](power-bi-visualization-types-for-reports-and-q-and-a.md) (Typen visualisaties in Power BI)
