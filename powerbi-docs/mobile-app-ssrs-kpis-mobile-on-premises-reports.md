---
title: On-premises rapporten en KPI's weergeven in de mobiele Power BI-apps
description: Met de mobiele Power BI-apps hebt u live en mobiel via aanraking toegang tot uw on-premises bedrijfsgegevens in SQL Server 2016 Reporting Services en Power BI Report Server.
services: powerbi
documentationcenter: 
author: maggiesMSFT
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
ms.date: 10/13/2017
ms.author: maggies
ms.openlocfilehash: 99fceab5904deaa510edd213c349dcfb2e38ac28
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/13/2017
---
# <a name="view-on-premises-report-server-reports-and-kpis-in-the-power-bi-mobile-apps"></a>On-premises rapportserverrapporten en KPI's weergeven in de mobiele Power BI-apps
Van toepassing op:

| ![iPhone](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/iphone-logo-50-px.png) | ![iPad](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/ipad-logo-50-px.png) | ![Android-telefoon](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/android-phone-logo-50-px.png) | ![Android-tablet](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/android-tablet-logo-50-px.png) |
|:--- |:--- |:--- |:--- |
| iPhones |iPads |Android-telefoons |Android-tablets |

Met de mobiele Power BI-apps hebt u live en mobiel via aanraking toegang tot uw on-premises bedrijfsgegevens in Power BI Report Server en SQL Server 2016 Reporting Services (SSRS). 

 ![Startpagina van Report Server in de mobiele apps](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-ipad-pbi-report-server-home.png)

## <a name="first-things-first"></a>Om te beginnen
**In de mobiele apps geeft u Power BI-inhoud weer. U maakt de inhoud daar niet.**

* U en andere rapportmakers in uw organisatie [maken Power BI-rapporten met Power BI Desktop. Vervolgens publiceert u deze naar de webportal van Power BI Report Server](report-server/quickstart-create-powerbi-report.md). 
* U kunt [rechtstreeks in de webportal KPI's maken](https://docs.microsoft.com/sql/reporting-services/working-with-kpis-in-reporting-services), deze ordenen in mappen en uw favorieten markeren, zodat u ze eenvoudig kunt terugvinden. 
* U kunt [mobiele Reporting Services-rapporten maken](https://docs.microsoft.com/sql/reporting-services/mobile-reports/create-mobile-reports-with-sql-server-mobile-report-publisher) met SQL Server 2016 Enterprise Edition Mobile Report Publisher en deze publiceren naar de [Reporting Services-webportal](https://docs.microsoft.com/sql/reporting-services/web-portal-ssrs-native-mode).  

Vervolgens kunt u in de mobiele Power BI-apps verbinding maken met maximaal vijf rapportservers om de Power BI-rapporten en -KPI's weer te geven, geordend in mappen of verzameld als favorieten. 

## <a name="explore-samples-in-the-mobile-apps-without-a-server-connection"></a>De voorbeelden in de mobiele apps verkennen zonder serververbinding
Ook als u geen toegang hebt tot een Reporting Services-webportal, kunt u de functies van mobiele Reporting Services-rapporten en -KPI's bekijken. 

1. Tik op de knop voor globale navigatie ![Knop voor globale navigatie](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-iphone-global-nav-button.png) in de linkerbovenhoek en tik vervolgens op het tandwielpictogram in de rechterbovenhoek ![Tandwielpictogram](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-ios-settings-icon.png).
2. Tik op **Reporting Services-voorbeelden** en blader om de voorbeeld-KPI's en de voorbeelden van mobiele rapporten te gebruiken.
   
   ![Reporting Services-voorbeelden](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-iphone-ssrs-samples.png)

## <a name="connect-to-an-on-premises-server"></a>Verbinding maken met een on-premises server
Met de mobiele Power BI-apps kunt u on-premises Power BI-rapporten, mobiele Reporting Services-rapporten en KPI's weergeven in de mobiele Power BI-apps. 

1. Open de Power BI-app op uw mobiele apparaat.
2. Als u zich nog niet hebt aangemeld bij Power BI, tikt u op **Report Server**.
   
   ![Aanmelden bij een rapportserver](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-connect-to-rs-login.png)
   
   Als u zich al hebt aangemeld bij de Power BI-app, tikt u op de knop voor globale navigatie ![Knop voor globale navigatie](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-iphone-global-nav-button.png)en vervolgens op het tandwielpictogram ![Tandwielpictogram](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-ios-settings-icon.png) in de rechterbovenhoek.
3. Tik op **Verbinding maken met server**.
   
    ![Verbinding maken met server](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-android-server-sign-in.png)
4. Vul het adres van de server en uw gebruikersnaam en wachtwoord in. Gebruik deze notatie voor het adres van de server:
   
     `http://<servername>/reports`
   
     OF
   
     `https://<servername>/reports`
   
   > [!NOTE]
   > Voeg **http** of **https** toe aan het begin van de verbindingsreeks.
   > 
   > 
   
    ![Het dialoogvenster Verbinding maken met server](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-ios-connect-to-server-dialog.png)
5. (Optioneel) U kunt bij **Geavanceerde opties** desgewenst een beschrijvende naam opgeven voor de server.
6. De server (in dit voorbeeld power bi report server genoemd) wordt nu weergegeven in de linkernavigatiebalk.
   
   ![Rapportserver in het linkernavigatiedeelvenster](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-iphone-left-nav-report-server.png)

## <a name="view-power-bi-reports-and-kpis-in-the-power-bi-app"></a>Power BI-rapporten en -KPI's weergeven in de Power BI-app
Power BI-rapporten en mobiele Reporting Services-rapporten worden weergegeven in de mappen waarin ze zijn opgeslagen op de Reporting Services-webportal. 

* Tik op een Power BI-rapport ![Pictogram van een Power BI-rapport](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-rs-mobile-report-icon.png). Het rapport wordt geopend in de liggende stand. U kunt met het rapport werken in de Power BI-app.
  
    ![Power BI-rapport](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-iphone-report-server-report.png)
* In Power BI Desktop kunnen rapporteigenaren [een rapport optimaliseren](desktop-create-phone-report.md) voor de mobiele Power BI-apps. Geoptimaliseerde rapporten hebben een speciaal pictogram, ![het pictogram Geoptimaliseerd Power BI-rapport](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-rs-mobile-optimized-icon.png), en een speciale indeling.
  
    ![Power BI-rapport dat is geoptimaliseerd voor mobiel](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-rs-mobile-optimized-report.png)
* Tik op een KPI om deze weer te geven in de focusmodus.
  
    ![KPI in de focusmodus](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/pbi_ipad_ssmrp_tile.png)

## <a name="view-your-favorite-kpis-and-reports"></a>Uw favoriete KPI's en rapporten weergeven
U kunt KPI's en rapporten op het webportal markeren als favorieten en ze vervolgens weergeven in één handige map op uw mobiele apparaat, samen met uw favoriete Power BI-dashboards en -rapporten.

* Tik op **Favorieten**.
  
   ![Favorieten in het linkernavigatievenster](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-ipad-faves-pbi-report-server.png)
  
   Uw favoriete KPI's en rapporten van de webportal bevinden zich allemaal op deze pagina, samen met de Power BI-dashboards in de Power BI-service:
  
   ![Power BI-rapporten en -dashboard op de pagina Favorieten](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-ipad-favorites.png)

## <a name="remove-a-connection-to-a-report-server"></a>Een verbinding met een rapportserver verwijderen
1. Tik onder aan de linkernavigatiebalk op **Instellingen**.
2. Tik op de naam van de server waarmee u geen verbinding wilt maken.
3. Tik op **Server verwijderen**.

## <a name="next-steps"></a>Volgende stappen
* [Aan de slag met Power BI](service-get-started.md)  
* Vragen? [Misschien dat de Power BI-community het antwoord weet](http://community.powerbi.com/).
