---
title: Shape-kaarten gebruiken in Power BI Desktop (preview)
description: Relatieve vergelijkingen tussen regio's maken met behulp van Shape-kaarten in Power BI Desktop
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
ms.date: 01/16/2018
ms.author: davidi
LocalizationGroup: Transform and shape data
ms.openlocfilehash: 335e9800be3d2a2cd30cc84835ab7b0173922c46
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/24/2018
---
# <a name="shape-maps-in-power-bi-desktop-preview"></a>Shape-kaarten in Power BI Desktop (preview)
In Power BI Desktop maakt u een **Shape-kaart**-visual om relatieve vergelijkingen van regio's op een kaart te laten zien door verschillende kleuren op verschillende regio's toe te passen. In tegenstelling tot de **kaart** -visual, kan **Shape Map** geen nauwkeurige geografische locaties van gegevenspunten op een kaart weergeven. In plaats daarvan is het belangrijkste doel het weergeven van relatieve vergelijkingen van regio's op een kaart door ze een andere kleur te geven.

Visuals van **Shape Map** zijn gebaseerd op ESRI/TopoJSON-kaarten die de mogelijkheid bieden om gebruik te maken van aangepaste kaarten die u kunt maken, zoals geografische kaarten, overzichten van zitplaatsen, verdiepingsplattegronden, enzovoort. De mogelijkheid om aangepaste toewijzigen te gebruiken is niet beschikbaar in deze voorbeeldrelease van **Shape Map**.

## <a name="creating-shape-maps"></a>Shape-kaarten maken
U kunt het **Shape Map**-besturingselement testen met de kaarten die bij deze Preview-versie worden geleverd of u kunt uw eigen aangepaste kaart gebruiken, zolang deze voldoet aan de vereisten die worden beschreven in de volgende sectie, **Aangepaste kaarten gebruiken**.

De **Shape Map**-visual is in Preview en moet worden ingeschakeld in Power BI Desktop. U kunt **Shape Map** inschakelen door **Bestand > Opties en instellingen > Opties > Preview-functies** te selecteren en het selectievakje **Shape Map** in te schakelen. Power BI Desktop moet opnieuw worden opgestart nadat u de selectie hebt gemaakt.

![](media/desktop-shape-map/shape-map_1a.png)

Zodra **Shape Map** is ingeschakeld, klikt u op het **Shape Map**-besturingselement vanuit het deelvenster **Visualisaties**.

![](media/desktop-shape-map/shape-map_2.png)

Power BI Desktop maakt een leeg ontwerpcanvas voor de **Shape Map**-visual.

![](media/desktop-shape-map/shape-map_3.png)

Voer de volgende stappen uit om een **Shape Map** te maken:

1. Sleep in het deelvenster **Velden** een veld met de regionamen (of afkortingen) naar de bucket **Locatie** en een veld met meetgegevens naar de bucket **Waarden** (er wordt nog geen kaart weergegeven).
   
   > [!NOTE]
> Zie de sectie **Kaartgegevens ophalen** hieronder voor informatie over het snel ophalen van kaartgegevens om **Shape Map** te testen.
   > 
   > 
   
   ![](media/desktop-shape-map/shape-map_3a.png)
2. In het instellingenvenster **Indeling** vouwt u **Vorm** uit en maakt u een selectie in de vervolgkeuzelijst **Standaardkaarten** om uw gegevens weer te geven. Op dat punt wordt de kaart weergegeven, zoals is te zien in de volgende afbeelding.
   
   ![](media/desktop-shape-map/shape-map_3b.png)
   
   > [!NOTE]
> In de sectie **Regiosleutels** aan het eind van dit artikel ziet u een verzameling tabellen met sleutels voor kaartregio's waarmee u de **Shape Map**-visual kunt testen.
   > 
   > 
3. Vervolgens kunt u vanuit het instellingenvenster **Indeling** de kaartprojectie en zoominstellingen wijzigen. U kunt ook de zoominstellingen wijzigen. U kunt bijvoorbeeld kleuren wijzigen, maximum- en minimumwaarden instellen, enzovoort.
   
   ![](media/desktop-shape-map/shape-map_3d.png)
4. U kunt ook een kolom met categoriegegevens aan de **Legenda**-bucket toevoegen en de kaartregio's classificeren op basis van categorieën.

## <a name="use-custom-maps"></a>Aangepaste kaarten gebruiken
U kunt aangepaste kaarten met **Shape Map** gebruiken zolang ze de **TopoJSON**-indeling hebben. Als de kaart een andere indeling heeft, kunt u onlineprogramma's zoals [ **Map Shaper** ](http://mapshaper.org/) gebruiken om uw *vormbestanden* of *GeoJSON*-kaarten te converteren naar de **TopoJSON**-indeling.

Als u uw **TopoJSON**-kaartbestand wilt gebruiken, voegt u een ShapeMap-visual toe aan uw rapport en enkele gegevens aan de *Locatie*- en *Waarden*-buckets. In het deelvenster **Visualisaties**, met de sectie **Indeling** geselecteerd (de verfkwast, weergegeven als (1) in de volgende afbeelding), vouwt u de sectie **Vorm** uit en selecteert u **+ Kaart toevoegen**.

![](media/desktop-shape-map/shape-map_6.png)

## <a name="getting-map-data"></a>Kaartgegevens ophalen
Om snel gegevens op te nemen in een model zodat u **Shape Map** kunt testen, kunt u een van de tabellen aan het eind van dit artikel kopiëren en **Gegevens invoeren** op het **Start**-lint selecteren.

![](media/desktop-shape-map/shape-map_4.png)

U kunt de tabel vervolgens in Power BI Desktop plakken. De bovenste rij wordt automatisch geïdentificeerd als koptekst.

![](media/desktop-shape-map/shape-map_5.png)

U kunt een nieuwe kolom invoeren door een nieuwe kolomnaam te typen (in de lege kolom rechts) en waarden in elke cel toe te voegen, net zoals u dat in Excel zou doen. Wanneer u klaar bent, selecteert u **Laden** en wordt de tabel toegevoegd aan het gegevensmodel voor Power BI Desktop.

> [!NOTE]
> Als u werkt met landen of regio's, gebruikt u de afkorting van drie letters om ervoor te zorgen dat geocodering goed werkt in kaartvisualisaties. Gebruik *geen* afkortingen van twee letters, aangezien bepaalde landen of regio's mogelijk niet goed worden herkend.
> 
> Als u alleen afkortingen van twee letters hebt, bekijkt u [dit externe blogbericht](https://blog.ailon.org/how-to-display-2-letter-country-data-on-a-power-bi-map-85fc738497d6#.yudauacxp) voor stapsgewijze instructies om de tweeletterige afkortingen voor landen/regio's aan de drieletterige afkortingen voor landen/regio's te koppelen.
> 
> 

## <a name="preview-behavior-and-requirements"></a>Preview-gedrag en -vereisten
Er zijn enkele overwegingen en vereisten voor deze Preview-versie van **Shape Map**:

* De **Shape Map**-visual is in Preview en moet worden ingeschakeld in Power BI Desktop. U kunt **Shape Map** inschakelen door **Bestand > Opties en instellingen > Opties > Preview-functies** te selecteren en het selectievakje **Shape Map** in te schakelen.
* Ook de **Waarden**-bucket moet nu zijn ingesteld zodat de **Legenda**-classificatie goed werkt
* De uiteindelijke releaseversie van **Shape Map** wordt voorzien van een gebruikersinterface waarin de kaartsleutels van de geselecteerde kaart worden weergegeven (er is geen datum ingesteld voor de uiteindelijke release en **Shape Map** bevindt zich nog in de previewfase); in deze previewrelease kunt u verwijzen naar de sleutels voor de kaartregio’s in de tabellen die te vinden zijn in de volgende sectie van dit artikel, **Regiosleutels**.
* De visual **Shape Map** brengt maximaal 1000 gegevenspunten aan in de tekening.

## <a name="region-keys"></a>Regiosleutels
Gebruik de volgende **regiosleutels** in deze Preview-versie om **Shape Map** te testen.

### <a name="australia-states"></a>Australië: staten
| id | afk | iso | naam | postcode |
| --- | --- | --- | --- | --- |
| au-wa |WA |AU-WA |West-Australië |WA |
| au-vic |Vic |AU-VIC |Victoria |VIC |
| au-tas |Tas |AU-TAS |Tasmanië |TAS |
| au-sa |SA |AU-SA |Zuid-Australië |SA |
| au-qld |Qld |AU-QLD |Queensland |QLD |
| au-nt |NT |AU-NT |Northern Territory |NT |
| au-nsw |NSW |AU-NSW |New South Wales |NSW |
| au-act |ACT |AU-ACT |Australian Capital Territory |ACT |

### <a name="austria-states"></a>Oostenrijk: deelstaten
| id | iso | naam | naam-nl | postcode |
| --- | --- | --- | --- | --- |
| at-wi |AT-9 |Wien |Wenen |WI |
| at-vo |AT-8 |Vorarlberg |Vorarlberg |VO |
| at-tr |AT-7 |Tirol |Tirol |TR |
| at-st |AT-6 |Steiermark |Stiermarken |ST |
| at-sz |AT-5 |Salzburg |Salzburg |SZ |
| at-oo |AT-4 |Oberösterreich |Opper-Oostenrijk |OO |
| at-no |AT-3 |Niederösterreich |Neder-Oostenrijk |NO |
| at-ka |AT-2 |Kärnten |Karinthië |KA |
| at-bu |AT-1 |Burgenland |Burgenland |BU |

### <a name="brazil-states"></a>Brazilië: staten
| id |
| --- |
| Tocantins |
| Pernambuco |
| Goias |
| Sergipe |
| Sao Paulo |
| Santa Catarina |
| Roraima |
| Rondonia |
| Rio groot Sul |
| Rio groot Sul |
| Rio de Janeiro, Brazilië |
| Piaui |
| Parana |
| Parana |
| Para |
| Minas Gerais |
| Mato Grosso |
| Maranhao |
| Mato Grosso Sul |
| Distrito Federal |
| Ceara |
| Espirito Santo |
| Bahia |
| Amazonas |
| Amapa |
| Alagoas |
| Acre |
| Litigated Zone 1 |
| Litigated Zone 2 |
| Litigated Zone 3 |
| Litigated Zone 4 |

### <a name="canada-provinces"></a>Canada: provincies
| id | iso | naam | postcode |
| --- | --- | --- | --- |
| ca-nu |CA-NU |Nunavut |NU |
| ca-nt |CA-NT |Northwest Territories |NT |
| ca-yt |CA-YT |Yukon |YT |
| ca-sk |CA-SK |Saskatchewan |SK |
| ca-qc |CA-QC |Quebec |QC |
| ca-pe |CA-PE |Prince Edward Island |PE |
| ca-on |CA-ON |Ontario |ON |
| ca-ns |CA-NS |Nova Scotia |NS |
| ca-nl |CA-NL |Newfoundland en Labrador |NL |
| ca-nb |CA-NB |New Brunswick |NB |
| ca-mb |CA-MB |Manitoba |MB |
| ca-bc |CA-BC |Brits-Columbia |BC |
| ca-ab |CA-AB |Alberta |AB |

### <a name="france-regions"></a>Frankrijk: regio's
| id | naam | naam-nl |
| --- | --- | --- |
| Alsace |Elzas |Elzas |
| Rhone-Alpes |Rhône-Alpes |Rhône-Alpes |
| Provence-Alpes-Cote d'Azur |Provence-Alpes-Côte d'Azur |Provence-Alpes-Côte d'Azur |
| Poitou-Charentes |Poitou-Charentes |Poitou-Charentes |
| Picardie |Picardie |Picardië |
| Pays de la Loire |Pays de la Loire |Pays de la Loire |
| Nord-Pas-de-Calais |Nord-Pas-de-Calais |Nord-Pas-de-Calais |
| Midi-Pyrenees |Midi-Pyrénées |Midi-Pyrénées |
| Lorraine |Lorraine |Lotharingen |
| Limousin |Limousin |Limousin |
| Languedoc-Roussillon |Languedoc-Roussillon |Languedoc-Roussillon |
| Ile-del-France |Île-de-France |Île-de-France |
| Haute-Normandie |Haute-Normandie |Hoog-Normandië |
| Franche-Comte |Franche-Comté |Franche-Comté |
| Corse |Corse |Corsica |
| Champagne-Ardenne |Champagne-Ardenne |Champagne-Ardenne |
| Centre-Val de Loire |Centre-Val de Loire |Centre-Val de Loire |
| Bretagne |Bretagne |Bretagne |
| Bourgogne |Bourgogne |Bourgondië |
| Basse-Normandie |Basse-Normandie |Laag-Normandië |
| Auvergne |Auvergne |Auvergne |
| Aquitaine |Aquitaine |Aquitaine |

### <a name="germany-states"></a>Duitsland: deelstaten
| id | iso | naam | naam-nl | postcode |
| --- | --- | --- | --- | --- |
| de-be |DE-BE |Berlin |Berlijn |BE |
| de-th |DE-TH |Thüringen |Thüringen |TH |
| de-st |DE-ST |Sachsen-Anhalt |Saksen-Anhalt |ST |
| de-sn |DE-SN |Sachsen |Saksen |SN |
| de-mv |DE-MV |Mecklenburg-Vorpommern |Mecklenburg-Vorpommern |MV |
| de-bb |DE-BB |Brandenburg |Brandenburg |BB |
| de-sh |DE-SH |Schleswig-Holstein |Sleeswijk-Holstein |SH |
| de-sl |DE-SL |Saarland |Saarland |SL |
| de-rp |DE-RP |Rheinland-Pfalz |Rijnland-Palts |RP |
| de-nw |DE-NW |Nordrhein-Westfalen |Noordrijn-Westfalen |NW |
| de-ni |DE-NI |Niedersachsen |Nedersaksen |NI |
| de-he |DE-HE |Hessen |Hessen |HE |
| de-hh |DE-HH |Hamburg |Hamburg |HH |
| de-hb |DE-HB |Bremen |Bremen |HB |
| de-by |DE-BY |Bayern |Beieren |BY |
| de-bw |DE-BW |Baden-Württemberg |Baden-Württemberg |BW |

### <a name="ireland-counties"></a>Ierland: county's
| id |
| --- |
| Wicklow |
| Wexford |
| Westmeath |
| Waterford |
| Sligo |
| Tipperary |
| Roscommon |
| Offaly |
| Monaghan |
| Meath |
| Mayo |
| Louth |
| Longford |
| Limerick |
| Leitrim |
| Laoighis |
| Kilkenny |
| Kildare |
| Kerry |
| Galway |
| Dublin |
| Donegal |
| Kurk |
| Clare |
| Cavan |
| Carlow |

### <a name="italy-regions"></a>Italië: regio's
| id | iso | naam | naam-nl | postcode |
| --- | --- | --- | --- | --- |
| it-vn |IT-34 |Veneto |Veneto |VN |
| it-vd |IT-23 |Valle d'Aosta |Aostavallei |VD |
| it-um |IT-55 |Umbria |Umbrië |UM |
| it-tt |IT-32 |Trentino-Alto-Adige |Trentino-Zuid-Tirol |TT |
| it-tc |IT-52 |Toscana |Toscane |TC |
| it-sc |IT-82 |Sicilia |Sicilië |SC |
| it-sd |IT-88 |Sardegna |Sardinië |SD |
| it-pm |IT-21 |Piemonte |Piëmont |PM |
| it-ml |IT-67 |Molise |Molise |ML |
| it-mh |IT-57 |Marche |Marche |MH |
| it-lm |IT-25 |Lombardia |Lombardije |LM |
| it-lg |IT-42 |Liguria |Ligurië |LG |
| it-lz |IT-62 |Lazio |Lazio |LZ |
| it-fv |IT-36 |Friuli-Venezia Giulia |Friuli-Julisch Venetië |FV |
| it-er |IT-45 |Emilia-Romagna |Emilia-Romagna |ER |
| it-cm |IT-72 |Campania |Campanië |CM |
| it-lb |IT-78 |Calabria |Calabrië |LB |
| it-bc |IT-77 |Basilicata |Basilicata |BC |
| it-pu |IT-75 |Apulia |Apulië |PU |
| it-ab |IT-65 |Abruzzo |Abruzzen |AB |

### <a name="mexico-states"></a>Mexico: staten
| id | abreviatura | iso | naam | naam-nl | postcode |
| --- | --- | --- | --- | --- | --- |
| mx-zac |Zac. |MX-ZAC |Zacatecas |Zacatecas |ZA |
| mx-yuc |Yuc. |MX-YUC |Yucatán |Yucatan |YU |
| mx-ver |Ver. |MX-VER |Veracruz |Veracruz |VE |
| mx-tla |Tlax. |MX-TLA |Tlaxcala |Tlaxcala |TL |
| mx-tam |Tamps. |MX-TAM |Tamaulipas |Tamaulipas |TM |
| mx-tab |Tab. |MX-TAB |Tabasco |Tabasco |TB |
| mx-son |Son. |MX-SON |Sonora |Sonora |SO |
| mx-sin |Sin. |MX-SIN |Sinaloa |Sinaloa |SI |
| mx-slp |S.L.P. |MX-SLP |San Luis Potosí |San Luis Potosí |SL |
| mx-roo |Q.R. |MX-ROO |Quintana Roo |Quintana Roo |QR |
| mx-que |Qro. |MX-QUE |Querétaro |Querétaro |QE |
| mx-pue |Pue. |MX-PUE |Puebla |Puebla |PU |
| mx-oax |Oax. |MX-OAX |Oaxaca |Oaxaca |OA |
| mx-nle |N.L. |MX-NLE |Nuevo León |Nuevo León |NL |
| mx-nay |Nay. |MX-NAY |Nayarit |Nayarit |NA |
| mx-mor |Mor. |MX-MOR |Morelos |Morelos |MR |
| mx-mic |Mich. |MX-MIC |Michoacán |Michoacán |MC |
| mx-mex |Méx. |MX-MEX |Estado de México |Mexico |MX |
| mx-jal |Jal. |MX-JAL |Jalisco |Jalisco |JA |
| mx-hid |Hgo. |MX-HID |Hidalgo |Hidalgo |HI |
| mx-gro |Gro. |MX-GRO |Guerrero |Guerrero |GR |
| mx-gua |Gto. |MX-GUA |Guanajuato |Guanajuato |GT |
| mx-dur |Dgo. |MX-DUR |Durango |Durango |DU |
| mx-dif |Col. |MX-DIF |Ciudad de México |Mexico-Stad |DF |
| mx-col |Coah. |MX-COL |Colima |Colima |CL |
| mx-coa |Chis. |MX-COA |Coahuila |Coahuila |CA |
| mx-chh |Chih. |MX-CHH |Chihuahua |Chihuahua |CH |
| mx-chp |CDMX. |MX-CHP |Chiapas |Chiapas |CP |
| mx-cam |Camp. |MX-CAM |Campeche |Campeche |CM |
| mx-bcs |B.C.S. |MX-BCS |Baja California Sur |Baja California Sur |BS |
| mx-bcn |B.C. |MX-BCN |Baja California |Baja California |BN |
| mx-agu |Ags. |MX-AGU |Aguascalientes |Aguascalientes |AG |

### <a name="netherlands-provinces"></a>Nederland: provincies
| id | iso | naam | naam-nl |
| --- | --- | --- | --- |
| nl-zh |NL-ZH |Zuid-Holland |South Holland |
| nl-ze |NL-ZE |Zeeland |Zeeland |
| nl-ut |NL-UT |Utrecht |Utrecht |
| nl-ov |NL-OV |Overijssel |Overijssel |
| nl-nh |NL-NH |Noord-Holland |North Holland |
| nl-nb |NL-NB |Noord-Brabant |North Brabant |
| nl-li |NL-LI |Limburg |Limburg |
| nl-gr |NL-GR |Groningen |Groningen |
| nl-ge |NL-GE |Gelderland |Gelderland |
| nl-fr |NL-FR |Fryslân |Friesland |
| nl-fl |NL-FL |Flevoland |Flevoland |
| nl-dr |NL-DR |Drenthe |Drenthe |

### <a name="uk-countries"></a>VK: landen
| id | iso | naam |
| --- | --- | --- |
| gb-wls |GB-WLS |Wales |
| gb-sct |GB-SCT |Schotland |
| gb-nir |GB-NIR |Noord-Ierland |
| gb-eng |GB-ENG |Engeland |

### <a name="usa-states"></a>VS: staten
| id | naam | postcode |
| --- | --- | --- |
| us-mi |Michigan |MI |
| us-ak |Alaska |AK |
| us-hi |Hawaii |HI |
| us-fl |Florida |FL |
| us-la |Louisiana |LA |
| us-ar |Arkansas |AR |
| us-sc |South Carolina |SC |
| us-ga |Georgia |GA |
| us-ms |Mississippi |MS |
| us-al |Alabama |AL |
| us-nm |New Mexico |NM |
| us-tx |Texas |TX |
| us-tn |Tennessee |TN |
| us-nc |North Carolina |NC |
| us-ok |Oklahoma |OK |
| us-az |Arizona |AZ |
| us-mo |Missouri |MO |
| us-va |Virginia |VA |
| us-ks |Kansas |KS |
| us-ky |Kentucky |KY |
| us-co |Colorado |CO |
| us-md |Maryland |MD |
| us-wv |West Virginia |WV |
| us-de |Delaware |DE |
| us-dc |District of Columbia |DC |
| us-il |Illinois |IL |
| us-oh |Ohio |OH |
| us-ca |Californië |CA |
| ons-ut |Utah |UT |
| ons-nv |Nevada |NV |
| us-in |Indiana |IN |
| us-nj |New Jersey |NJ |
| us-ri |Rhode Island |RI |
| us-ct |Connecticut |CT |
| us-pa |Pennsylvania |PA |
| us-ny |New York |NY |
| us-ne |Nebraska |NE |
| us-ma |Massachusetts |MA |
| us-ia |Iowa |IA |
| us-nh |New Hampshire |NH |
| us-or |Oregon |OR |
| us-mn |Minnesota |MN |
| us-vt |Vermont |VT |
| us-id |Idaho |ID |
| us-wi |Wisconsin |WI |
| us-wy |Wyoming |WY |
| us-sd |South Dakota |SD |
| us-nd |Dakota |ND |
| us-me |Maine |ME |
| us-mt |Montana |MT |
| us-wa |Washington |WA |

