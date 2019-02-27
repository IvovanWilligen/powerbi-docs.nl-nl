---
title: Mogelijk extra aankoop vereist - richtlijnen voor Power BI-visuals
description: Meer informatie over het publiceren van aangepaste visuals naar AppSource, zodat anderen deze na aanschaf kunnen gebruiken.
author: markingmyname
ms.author: maghan
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 11/26/2018
ms.openlocfilehash: 92d4320026164e523297cbe48ee87ce33d9ab2f7
ms.sourcegitcommit: 796bf513bf8669676e2a44627b56221b1629a6a8
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/26/2019
ms.locfileid: "56826578"
---
# <a name="guidelines-for-power-bi-visuals-with-additional-purchases"></a>Richtlijnen voor Power BI-visuals met extra aankopen

Tot voor kort accepteerde de Marketplace (AppSource) alleen gratis Power BI-visuals. Dit beleid is gewijzigd, zodat u ook visuals naar AppSource kunt verzenden met de aanduiding 'Mogelijk extra aankoop vereist'. 

Visuals met de aanduiding ‘Mogelijk extra aankoop vereist’ zijn vergelijkbaar met IAP-invoegtoepassingen (in-app aankoop) in de Office Store. Ontwikkelaars kunnen deze visuals ook indienen voor certificering nadat ze door het AppSource-team zijn goedgekeurd en nadat is gecontroleerd of ze aan de vereisten voor certificering voldoen. Zie [Gecertificeerde aangepaste visuals](../power-bi-custom-visuals-certified.md) voor meer informatie over deze vereisten.

> [!NOTE]
> * Visuals kunnen alleen worden gecertificeerd als deze geen toegang hebben tot externe services of resources.
> * In alle gratis visuals moeten de gratis functies behouden blijven die eerder ook werden aangeboden. Behalve de bestaande gratis functies kunt u ook optionele, geavanceerde, betaalde functies toevoegen. U wordt aangeraden om IAP-visuals met geavanceerde functies als nieuwe visuals in te dienen en niet de bestaande, gratis exemplaren bij te werken.


## <a name="what-changed-in-the-submission-process"></a>Wat is er veranderd in het indieningsproces?

Ontwikkelaars uploaden hun IAP-visuals naar AppSource via het Verkopersdashboard, zoals ze dat ook al deden voor gratis visuals. Om aan te geven dat de ingediende visual over IAP-functies beschikt, moeten ontwikkelaars op het Verkopersdashboard de opmerking 'Visual met in-app aankoop' toevoegen. Bovendien moeten ontwikkelaars een licentiesleutel of token opgeven zodat het validatieteam de IAP-functies kan valideren. Nadat de visual is gevalideerd en goedgekeurd, wordt bij de prijsopties in de AppSource-vermelding voor de IAP-visual 'Mogelijk extra aankoop vereist' vermeld.

## <a name="what-is-a-power-bi-visual-with-iap-features"></a>Wat is een Power BI-visual met IAP-functies?

Een IAP-visual is een gratis visual die gratis functies biedt. Zo'n visual bevat ook enkele geavanceerde functies waarvoor extra kosten in rekening kunnen worden gebracht als u ze wilt gebruiken. In de beschrijving van de visual moet de ontwikkelaar informatie geven over de functies waarvoor extra aankopen moeten worden gedaan als u ze wilt gebruiken. Op dit moment biedt Microsoft geen systeemeigen API's voor de ondersteuning van aankopen van apps en invoegtoepassingen.

Voor deze aankopen kunnen ontwikkelaars een extern betalingssysteem gebruiken. Zie ons [beleid voor de Store](https://docs.microsoft.com/office/dev/store/validation-policies#2-apps-or-add-ins-can-display-certain-ads) voor meer informatie.

> [!NOTE]
> Watermerken zijn niet toegestaan voor de gratis functies. Ontwikkelaars kunnen een pop-upvenster of watermerk weergeven als de geavanceerde betaalde functies worden gebruikt zonder geldige licentie.  

## <a name="logo-guidelines"></a>Richtlijnen voor logo's

In deze sectie worden de specificaties voor het toevoegen van logo's en logotypes in visuals beschreven.

> [!NOTE]
> Logo's zijn alleen in de bewerkingsmodus toegestaan. Logo's kunnen niet worden weergegeven in de weergavemodus.

![Definities](media/office-store-in-app-purchase-visual-guidelines/definitions.png)

![Zaken om rekening mee te houden](media/office-store-in-app-purchase-visual-guidelines/things-to-keep-in-mind.png)

![Zaken die moeten worden voorkomen](media/office-store-in-app-purchase-visual-guidelines/things-to-avoid.png)

![Grootte en opmaak](media/office-store-in-app-purchase-visual-guidelines/size-and-format.png)

![Marges en grootte](media/office-store-in-app-purchase-visual-guidelines/margins-and-sizes.png)

![De modus Bewerken](media/office-store-in-app-purchase-visual-guidelines/logos-in-edit-mode.png)

## <a name="best-practices"></a>Aanbevolen procedures

### <a name="visual-landing-page"></a>Landingspagina van visual

Gebruik de landingspagina om gebruikers te informeren hoe zij uw visual kunnen gebruiken en waar ze de licentie kunnen aanschaffen. Sluit geen video's in die automatisch worden geactiveerd. Voeg uitsluitend materiaal toe dat helpt de gebruikerservaring te verbeteren, zoals informatie of koppelingen naar details over de aankoop van licenties en instructies voor het gebruik van de IAP-functies.

### <a name="license-key-and-token"></a>Licentiesleutel en token

Voor het gemak van de gebruiker kunt u boven in het deelvenster Opmaak velden voor licentiesleutels of tokens toevoegen.

## <a name="faq"></a>Veelgestelde vragen

Voor meer informatie over visuals gaat u naar [Veelgestelde vragen over visuals met extra aankopen](https://docs.microsoft.com/power-bi/power-bi-custom-visuals-faq#visuals-with-additional-purchases).

## <a name="next-steps"></a>Volgende stappen

Meer informatie over het publiceren van aangepaste visuals naar [AppSource](office-store.md), zodat anderen deze kunnen gebruiken.
