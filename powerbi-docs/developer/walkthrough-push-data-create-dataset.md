---
title: Een gegevensset maken
description: 'Stappen: Gegevens naar een gegevensset pushen: een gegevensset maken in Power BI'
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
ms.topic: get-started-article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 08/10/2017
ms.author: asaxton
ms.openlocfilehash: b45a6f76a710bc158d0d1763ca10f2125164952a
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/15/2017
---
# <a name="step-3-create-a-dataset-in-power-bi"></a>Stap 3: Een gegevensset maken in Power BI
Dit artikel maakt deel uit van een stapsgewijze uitleg van hoe u [gegevens naar een gegevensset pusht](walkthrough-push-data.md).

In **stap 2** van Gegevens naar een gegevensset pushen, [Een toegangstoken voor verificatie ophalen](walkthrough-push-data-get-token.md), hebt u een token opgehaald voor verificatie bij **Azure AD**. In deze stap gebruikt u de token om de bewerking [Gegevensset maken](https://msdn.microsoft.com/library/mt203562.aspx) aan te roepen.

Als u een REST-resource aanroept, gebruikt u een URL die de resource zoekt en verzendt u een JSON-tekenreeks (JavaScript Object Notation), waarin de gegevensset wordt beschreven, naar de resource van de Power BI-service. Een REST-resource geeft het deel van de Power BI-service aan waarmee u wilt werken. Als u gegevens naar de gegevensset wilt pushen, is de doelresource een **gegevensset**. De URL die een gegevensset opgeeft is https://api.PowerBI.com/v1.0/myorg/datasets. Als u gegevens pusht binnen een groep, is de URL https://api.PowerBI.com/v1.0/myorg/groups/{groeps_id}/datasets.

Als u een REST-bewerking voor Power BI wilt verifiëren, voegt u de token die u hebt gekregen in [Een toegangstoken voor verificatie ophalen](walkthrough-push-data-get-token.md) toe aan een aanvraagheader:

Wanneer u de bewerking [Gegevensset maken](https://msdn.microsoft.com/library/mt203562.aspx) aanroept, wordt een nieuwe gegevensset gemaakt. Voor voorbeelden van het gebruik van de REST-API voor Power BI raadpleegt u [REST-API voor Power BI in APIARY](http://docs.powerbi.apiary.io/).

![](media/walkthrough-push-data-create-dataset/powerbi-developer-create-dataset.png)

U maakt als volgt een gegevensset in Power BI.

## <a name="create-a-dataset-in-power-bi"></a>Een gegevensset maken in Power BI
> [!NOTE]
> Voordat u begint, zorgt u dat u de vorige stappen in [Gegevens naar een gegevensset pushen](walkthrough-push-data.md) hebt gevolgd.
> 
> 

1. In het consoletoepassingsproject dat u hebt gemaakt in [Stap 2: Een toegangstoken voor verificatie ophalen](walkthrough-push-data-get-token.md) voegt u **using System.Net;** en **using System.IO;** toe aan Program.cs.
2. Voeg de onderstaande code toe in Program.cs.
3. Voer de console-app uit en meld u aan bij uw Power BI-account. U ziet **Gegevensset gemaakt** in het consolevenster. U kunt zich ook aanmelden bij Power BI om de nieuwe gegevensset te zien.

**Voorbeeldgegevens naar een gegevensset pushen**

Voeg deze code toe in Program.cs.

* In static void Main(string[] args):
  
    ```
    static void Main(string[] args)
    {
        //Get an authentication access token
        token = GetToken();
  
        //Create a dataset in Power BI
        CreateDataset();
    }
    ```
* Voeg de methode CreateDataset() toe:
  
    ```
    #region Create a dataset in Power BI
    private static void CreateDataset()
    {
        //TODO: Add using System.Net and using System.IO
  
        string powerBIDatasetsApiUrl = "https://api.powerbi.com/v1.0/myorg/datasets";
        //POST web request to create a dataset.
        //To create a Dataset in a group, use the Groups uri: https://api.PowerBI.com/v1.0/myorg/groups/{group_id}/datasets
        HttpWebRequest request = System.Net.WebRequest.Create(powerBIDatasetsApiUrl) as System.Net.HttpWebRequest;
        request.KeepAlive = true;
        request.Method = "POST";
        request.ContentLength = 0;
        request.ContentType = "application/json";
  
        //Add token to the request header
        request.Headers.Add("Authorization", String.Format("Bearer {0}", token));
  
        //Create dataset JSON for POST request
        string datasetJson = "{\"name\": \"SalesMarketing\", \"tables\": " +
            "[{\"name\": \"Product\", \"columns\": " +
            "[{ \"name\": \"ProductID\", \"dataType\": \"Int64\"}, " +
            "{ \"name\": \"Name\", \"dataType\": \"string\"}, " +
            "{ \"name\": \"Category\", \"dataType\": \"string\"}," +
            "{ \"name\": \"IsCompete\", \"dataType\": \"bool\"}," +
            "{ \"name\": \"ManufacturedOn\", \"dataType\": \"DateTime\"}" +
            "]}]}";
  
        //POST web request
        byte[] byteArray = System.Text.Encoding.UTF8.GetBytes(datasetJson);
        request.ContentLength = byteArray.Length;
  
        //Write JSON byte[] into a Stream
        using (Stream writer = request.GetRequestStream())
        {
            writer.Write(byteArray, 0, byteArray.Length);
  
            var response = (HttpWebResponse)request.GetResponse();
  
            Console.WriteLine(string.Format("Dataset {0}", response.StatusCode.ToString()));
  
            Console.ReadLine();
        }
    }
    #endregion
    ```

In de volgende stap ziet u hoe u [een gegevensset ophaalt om rijen toe te voegen aan een Power BI-tabel](walkthrough-push-data-get-datasets.md).

Hieronder ziet u de [volledige code](#code).

<a name="code"/>

## <a name="complete-code-listing"></a>Volledige code
    using System;
    using Microsoft.IdentityModel.Clients.ActiveDirectory;
    using System.Net;
    using System.IO;

    namespace walkthrough_push_data
    {
        class Program
        {
            private static string token = string.Empty;

            static void Main(string[] args)
            {

                //Get an authentication access token
                token = GetToken();

                //Create a dataset in Power BI
                CreateDataset();

            }

            #region Get an authentication access token
            private static string GetToken()
            {
                // TODO: Install-Package Microsoft.IdentityModel.Clients.ActiveDirectory -Version 2.21.301221612
                // and add using Microsoft.IdentityModel.Clients.ActiveDirectory

                //The client id that Azure AD created when you registered your client app.
                string clientID = "{Client_ID}";

                //RedirectUri you used when you register your app.
                //For a client app, a redirect uri gives Azure AD more details on the application that it will authenticate.
                // You can use this redirect uri for your client app
                string redirectUri = "https://login.live.com/oauth20_desktop.srf";

                //Resource Uri for Power BI API
                string resourceUri = "https://analysis.windows.net/powerbi/api";

                //OAuth2 authority Uri
                string authorityUri = "https://login.windows.net/common/oauth2/authorize";

                //Get access token:
                // To call a Power BI REST operation, create an instance of AuthenticationContext and call AcquireToken
                // AuthenticationContext is part of the Active Directory Authentication Library NuGet package
                // To install the Active Directory Authentication Library NuGet package in Visual Studio,
                //  run "Install-Package Microsoft.IdentityModel.Clients.ActiveDirectory" from the nuget Package Manager Console.

                // AcquireToken will acquire an Azure access token
                // Call AcquireToken to get an Azure token from Azure Active Directory token issuance endpoint
                AuthenticationContext authContext = new AuthenticationContext(authorityUri);
                string token = authContext.AcquireToken(resourceUri, clientID, new Uri(redirectUri)).AccessToken;

                Console.WriteLine(token);
                Console.ReadLine();

                return token;
            }

            #endregion


            #region Create a dataset in Power BI
            private static void CreateDataset()
            {
                //TODO: Add using System.Net and using System.IO

                string powerBIDatasetsApiUrl = "https://api.powerbi.com/v1.0/myorg/datasets";
                //POST web request to create a dataset.
                //To create a Dataset in a group, use the Groups uri: https://api.PowerBI.com/v1.0/myorg/groups/{group_id}/datasets
                HttpWebRequest request = System.Net.WebRequest.Create(powerBIDatasetsApiUrl) as System.Net.HttpWebRequest;
                request.KeepAlive = true;
                request.Method = "POST";
                request.ContentLength = 0;
                request.ContentType = "application/json";

                //Add token to the request header
                request.Headers.Add("Authorization", String.Format("Bearer {0}", token));

                //Create dataset JSON for POST request
                string datasetJson = "{\"name\": \"SalesMarketing\", \"tables\": " +
                    "[{\"name\": \"Product\", \"columns\": " +
                    "[{ \"name\": \"ProductID\", \"dataType\": \"Int64\"}, " +
                    "{ \"name\": \"Name\", \"dataType\": \"string\"}, " +
                    "{ \"name\": \"Category\", \"dataType\": \"string\"}," +
                    "{ \"name\": \"IsCompete\", \"dataType\": \"bool\"}," +
                    "{ \"name\": \"ManufacturedOn\", \"dataType\": \"DateTime\"}" +
                    "]}]}";

                //POST web request
                byte[] byteArray = System.Text.Encoding.UTF8.GetBytes(datasetJson);
                request.ContentLength = byteArray.Length;

                //Write JSON byte[] into a Stream
                using (Stream writer = request.GetRequestStream())
                {
                    writer.Write(byteArray, 0, byteArray.Length);

                    var response = (HttpWebResponse)request.GetResponse();

                    Console.WriteLine(string.Format("Dataset {0}", response.StatusCode.ToString()));

                    Console.ReadLine();
                }
            }
            #endregion
        }
    }


[Volgende stap >](walkthrough-push-data-get-datasets.md)

## <a name="next-steps"></a>Volgende stappen
[Een gegevensset ophalen om rijen toe te voegen aan een Power BI-tabel](walkthrough-push-data-get-datasets.md)  
[Een toegangstoken voor verificatie ophalen](walkthrough-push-data-get-token.md)  
[Gegevensset maken](https://msdn.microsoft.com/library/mt203562.aspx)  
[Gegevens pushen naar een Power BI-dashboard](walkthrough-push-data.md)  
[Overzicht van de REST-API voor Power BI](overview-of-power-bi-rest-api.md)  
[Naslag voor REST-API voor Power BI](https://msdn.microsoft.com/library/mt147898.aspx)  
[REST-API voor Power BI op APIARY](http://docs.powerbi.apiary.io/)  

Hebt u nog vragen? [Misschien dat de Power BI-community het antwoord weet](http://community.powerbi.com/)
