---
title: Overzicht van het ontwikkelaarshandboek voor Power BI Report Server
description: Welkom bij het ontwikkelaarshandboek voor Power BI Report Server, een on-premises locatie om uw Power BI-rapporten, mobiele rapporten en gepagineerde rapporten op te slaan en te beheren.
services: powerbi
documentationcenter: 
author: guyinacube
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
ms.date: 11/01/2017
ms.author: asaxton
ms.openlocfilehash: eed858da341bb8544834b4aa43823d90ff38ce37
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/13/2017
---
# <a name="developer-handbook-overview-power-bi-report-server"></a>Overzicht van het ontwikkelaarshandboek voor Power BI Report Server
Welkom bij het ontwikkelaarshandboek voor Power BI Report Server, een on-premises locatie om uw Power BI-rapporten, mobiele rapporten en gepagineerde rapporten op te slaan en te beheren.

![](media/developer-handbook-overview/admin-handbook.png)

In dit handboek worden de opties besproken waarover u als ontwikkelaar beschikt om te werken met Power BI Report Server.

## <a name="embedding"></a>Insluiten
U kunt elk rapport in Power BI Report Server insluiten in een iFrame door de parameter `?rs:Embed=true` voor de querytekenreeks toe te voegen aan de URL. Dit werkt voor Power BI-rapporten en voor andere rapporttypen.

### <a name="report-viewer-control"></a>Besturingselement van de rapportviewer
Voor gepagineerde rapporten kunt u profiteren van het besturingselement van de rapportviewer. Hiermee kunt u het besturingselement binnen een .NET Windows- of webtoepassing plaatsen. Zie [Get started with the Report Viewer Control](https://docs.microsoft.com/sql/reporting-services/application-integration/integrating-reporting-services-using-reportviewer-controls-get-started) (Aan de slag met het besturingselement van de rapportviewer) voor meer informatie.

## <a name="apis"></a>API's
U hebt verschillende API-opties voor interactie met Power BI Report Server. Onder andere:

* [REST API’s](rest-api.md)
* [URL-toegang](https://docs.microsoft.com/sql/reporting-services/url-access-ssrs)
* [WMI-provider](https://docs.microsoft.com/sql/reporting-services/wmi-provider-library-reference/reporting-services-wmi-provider-library-reference-ssrs)

U kunt ook de [open source-hulpprogramma’s van PowerShell](https://github.com/Microsoft/ReportingServicesTools) gebruiken om de rapportserver te beheren.

> [!NOTE]
> De hulpprogramma's van PowerShell bieden momenteel geen ondersteuning voor Power BI Desktop-bestanden (.pbix).
> 
> 

## <a name="custom-extensions"></a>Aangepaste extensies
De extensiebibliotheek is een set klassen, interfaces en waardetypen die zijn opgenomen in Power BI Report Server. Deze bibliotheek biedt toegang tot systeemfuncties en is ontworpen als basis voor het gebruik van Microsoft .NET Framework-toepassingen voor het uitbreiden van Power BI Report Server-onderdelen.

U kunt verschillende typen extensies bouwen.

* Extensies voor gegevensverwerking
* Extensies voor bezorging
* Extensies voor het weergeven van gepagineerde rapporten
* Extensies voor beveiliging

Zie [Extension library](https://docs.microsoft.com/sql/reporting-services/extensions/reporting-services-extension-library) (Extensiebibliotheek) voor meer informatie.

## <a name="next-steps"></a>Volgende stappen
[Get started with the Report Viewer Control](https://docs.microsoft.com/sql/reporting-services/application-integration/integrating-reporting-services-using-reportviewer-controls-get-started) (Aan de slag met het besturingselement van de rapportviewer)  
[Building Applications Using the Web Service and the .NET Framework](https://docs.microsoft.com/sql/reporting-services/report-server-web-service/net-framework/building-applications-using-the-web-service-and-the-net-framework) (Toepassingen bouwen met behulp van de webservice en .NET Framework)  
[URL-toegang](https://docs.microsoft.com/sql/reporting-services/url-access-ssrs)  
[Extensiebibliotheek](https://docs.microsoft.com/sql/reporting-services/extensions/reporting-services-extension-library)  
[WMI-provider](https://docs.microsoft.com/sql/reporting-services/wmi-provider-library-reference/reporting-services-wmi-provider-library-reference-ssrs)

Hebt u nog vragen? [Misschien dat de Power BI-community het antwoord weet](https://community.powerbi.com/)
