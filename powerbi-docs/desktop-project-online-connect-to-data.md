---
title: 'Project Online: verbinding met gegevens maken via Power BI Desktop'
description: 'Project Online: verbinding met gegevens maken via Power BI Desktop'
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.custom: seodec18
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 05/08/2019
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: b0dc84d7b2d8da0df8a9e61a43f35898d197c188
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/29/2019
ms.locfileid: "65513764"
---
# <a name="project-online-connect-to-data-through-power-bi-desktop"></a>Project Online: verbinding met gegevens maken via Power BI Desktop
U kunt verbinding maken met gegevens maken in Project Online via Power BI Desktop.

## <a name="step-1-download-power-bi-desktop"></a>Stap 1: Power BI Desktop downloaden
1. [Download Power BI Desktop](http://go.microsoft.com/fwlink/?LinkID=521662) en voer vervolgens het installatieprogramma uit om **Power BI Desktop** op uw computer te installeren.

## <a name="step-2-connect-to-project-online-with-odata"></a>Stap 2: Verbinding maken met Project Online met OData
1. Open **Power BI Desktop**.
2. Selecteer **Gegevens ophalen** in het *welkomstscherm*.
3. Kies **OData-feed** en selecteer **Verbinding maken**.
4. Voer het adres voor uw OData-feed in het URL-vak in en klik op OK.
   
   Als het adres voor uw Project Web App-site lijkt op *https://\<tenantname\>.sharepoint.com/sites/pwa*, dan is het adres dat u voor uw OData-Feed invoert *https://\<tenantname\>.sharepoint.com/sites/pwa/\_api/Projectdata*.
   
   Voor ons voorbeeld gebruiken we https://contoso.sharepoint.com/sites/pwa/default.aspx
5. Power BI Desktop vraagt u om te verifiëren met uw Office 365-account. Selecteer Organisatieaccount en voer uw referenties in.
   
   ![](media/desktop-project-online-connect-to-data/image.png)

Het account waarmee u verbinding maken met de OData-feed ten minste hebt Portfolioviewer-toegang tot de Project Web App-site. 

Vanaf hier kunt u kiezen met welke tabellen u verbinding wilt maken en een query bouwen.  Wilt u een idee krijgen van hoe u aan de slag kunt gaan?  Het volgende blogbericht bevat over het bouwen van een branden omlaag grafiek van uw Project Online-gegevens.  Deze blogpost verwijst naar het gebruik van Power Query om verbinding te maken met Project Online, maar dit is ook van toepassing op Power BI Desktop.

[Branden omlaag grafieken maken voor Project met behulp van Power Pivot en Power Query](http://blogs.office.com/2014/03/24/creating-burndown-charts-for-project-using-power-pivot-and-power-query/)

