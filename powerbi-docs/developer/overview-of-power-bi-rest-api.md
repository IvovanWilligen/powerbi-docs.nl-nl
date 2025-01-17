---
title: Wat kan ik doen met de Power BI-API
description: Wat kan ik doen met de Power BI-API
author: rkarlin
ms.author: rkarlin
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 03/25/2019
ms.openlocfilehash: fd49c69a14d3dac6b1a045f6aba407ec7aac0deb
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/29/2019
ms.locfileid: "61269411"
---
# <a name="what-can-developers-do-with-the-power-bi-api"></a>Wat kunnen ontwikkelaars doen met de Power BI-API?

Met de Power BI REST-API kunt u apps maken die integreren met rapporten, dashboards en tegels van Power BI.

Met de Power BI REST-API is het mogelijk beheertaken uit te voeren voor Power BI-objecten, zoals rapporten, gegevenssets en werkruimten.

Hier volgen enkele dingen die u kunt doen met de Power BI-API‘s.

| **Voor meer informatie** | **Deze naslaginformatie** |
|----------------------------------------------------------------------------------|------------------------------------------------------------------------------------|
| Rapporten, dashboards en tegels insluiten voor Power BI-gebruikers en niet-Power BI-gebruikers. | [Uw Power BI-dashboards, rapporten en tegels insluiten ](embedding-content.md) |
| Beheertaken uitvoeren op Power BI-objecten. | [Power BI REST API reference](https://docs.microsoft.com/rest/api/power-bi/) (Naslag voor REST-API voor Power BI) |
| Een bestaande zakelijke werkstroom uitbreiden om belangrijke gegevens naar een Power BI-dashboard te pushen. | [Gegevens in een dashboard pushen ](walkthrough-push-data.md) |
| Verifiëren bij Power BI. | [Verifiëren bij Power BI ](get-azuread-access-token.md) |

> [!NOTE]
> In de Power BI-API's worden app-werkruimten nog steeds groepen genoemd. Als er wordt verwezen naar groepen, werkt u in feite met app-werkruimten.

## <a name="api-developer-tools"></a>API-ontwikkelhulpprogramma's

| Hulpprogramma('s) | Beschrijving |  |  |
|-------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------|---|---|
| [Speelplaats hulpprogramma](https://microsoft.github.io/PowerBI-JavaScript/demo) | Een volledig voorbeeld van het gebruik van de Power BI JavaScript-API's. Met dit hulpprogramma kunt u ook op een snelle manier verschillende typen Power BI Embedded-voorbeelden proberen. |  |  |
| [Power BI-JavaScript wiki](https://github.com/Microsoft/powerbi-javascript/wiki) | Meer informatie over de Power BI JavaScript-API's. |  |  |
| [Postman](https://www.getpostman.com/) | Aanvragen uitvoeren, testen, fouten opsporen, bewaken, geautomatiseerde tests uitvoeren en nog veel meer. |

## <a name="push-data-into-power-bi"></a>Gegevens pushen naar Power BI

U kunt de Power BI-API gebruiken om [gegevens naar een gegevensset te pushen](walkthrough-push-data.md). Met deze functie kunt u een rij aan een tabel in een gegevensset toevoegen. De nieuwe gegevens worden vervolgens weergegeven in tegels op een dashboard en in visuele elementen binnen uw rapport.

![Voorbeeld van pushen van gegevens](media/what-can-you-do/powerbi-push-data.png)

## <a name="github-repositories"></a>GitHub-opslagplaatsen

* [Voorbeelden voor Power BI-ontwikkelaars](https://github.com/Microsoft/PowerBI-Developer-Samples)
* [.NET SDK](https://github.com/Microsoft/PowerBI-CSharp)
* [JavaScript-API](https://github.com/Microsoft/PowerBI-JavaScript)

## <a name="next-steps"></a>Volgende stappen

* [Gegevens naar een gegevensset pushen](walkthrough-push-data.md)
* [Een aangepaste visual voor Power BI ontwikkelen](custom-visual-develop-tutorial.md)
* [Power BI REST API-verwijzing](rest-api-reference.md)
* [Power BI REST API's](https://docs.microsoft.com/rest/api/power-bi/)

Hebt u nog vragen? [Misschien dat de Power BI-community het antwoord weet](http://community.powerbi.com/)
