---
title: Problemen met de on-premises gegevensgateway oplossen
description: In dit artikel worden manieren besproken om problemen met de on-premises gegevensgateway op te lossen. Het biedt mogelijke tijdelijke oplossingen voor bekende problemen, evenals hulpprogramma's om u te helpen.
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
ms.tgt_pltfrm: na
ms.workload: powerbi
ms.date: 11/21/2017
ms.author: davidi
ms.openlocfilehash: 62405898f06a75fdad9da1f635f01bebdb445d2e
ms.sourcegitcommit: 8f72ce6b35aa25979090a05e3827d4937dce6a0d
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/27/2017
---
# <a name="troubleshooting-the-on-premises-data-gateway"></a>Problemen met de on-premises gegevensgateway oplossen
In dit artikel worden enkele veelvoorkomende problemen besproken die kunnen optreden tijdens het gebruik van de **on-premises gegevensgateway**.

<!-- Shared Community & support links Include -->
[!INCLUDE [gateway-onprem-tshoot-support-links-include](./includes/gateway-onprem-tshoot-support-links-include.md)]

<!-- Shared Troubleshooting Install Include -->
[!INCLUDE [gateway-onprem-tshoot-install-include](./includes/gateway-onprem-tshoot-install-include.md)]

## <a name="configuration"></a>Configuratie
### <a name="how-to-restart-the-gateway"></a>De gateway opnieuw starten
De gateway wordt uitgevoerd als een Windows-service, dus u kunt deze op verschillende manieren stoppen en starten. U kunt bijvoorbeeld een opdrachtprompt met verhoogde bevoegdheden openen op de computer waarop de gateway wordt uitgevoerd en vervolgens een van deze opdrachten uitvoeren:

* Als u de service wilt stoppen, voert u deze opdracht uit:
  
    '''   net stop PBIEgwService   '''
* Als u de service wilt starten, voert u deze opdracht uit:
  
    '''   net start PBIEgwService   '''

### <a name="error-failed-to-create-gateway-please-try-again"></a>Fout: De gateway is niet gemaakt. Probeer het opnieuw.
Alle gegevens zijn beschikbaar, maar de aanroep naar de Power BI-service heeft een fout geretourneerd. Deze fout en een activiteits-id worden weergegeven. Dit kan gebeuren om verschillende redenen. U kunt voor meer informatie de logboeken verzamelen en bekijken, zoals hieronder wordt beschreven.

Dit kan ook voorkomen vanwege problemen met de proxyconfiguratie. De gebruikersinterface biedt geen mogelijkheid voor proxyconfiguratie. U kunt meer informatie raadplegen over het [wijzigen van de proxyconfiguratie](service-gateway-proxy.md)

### <a name="error-failed-to-update-gateway-details--please-try-again"></a>Kan de gatewaygegevens niet bijwerken.  Probeer het opnieuw.
Informatie van de Power BI-service is ontvangen op de gateway. De informatie is doorgegeven aan de lokale Windows-service, maar niet geretourneerd. Of het genereren van een symmetrische sleutel is mislukt. De interne uitzondering wordt weergegeven onder **Details weergeven**. U kunt voor meer informatie de logboeken verzamelen en bekijken, zoals hieronder wordt beschreven.

### <a name="error-power-bi-service-reported-local-gateway-as-unreachable-please-restart-the-gateway-and-try-again"></a>Fout: De Power BI-service rapporteert dat de lokale gateway niet bereikbaar is. Start de gateway opnieuw en probeer het opnieuw.
Aan het einde van de configuratie wordt de Power BI-service opnieuw aangeroepen om de gateway te valideren. De Power BI-service rapporteert niet dat de gateway *live* is. De communicatie slaagt mogelijk wel als u de Windows-service opnieuw start. U kunt voor meer informatie de logboeken verzamelen en bekijken, zoals hieronder wordt beschreven.

### <a name="script-error-during-sign-into-power-bi"></a>Scriptfout tijdens het aanmelden bij Power BI
Mogelijk treedt er een scriptfout op tijdens het aanmelden bij Power BI als onderdeel van de configuratie van de on-premises gegevensgateway. Dit probleem moet zijn opgelost na het installeren van de volgende beveiligingsupdate. De update kan worden geïnstalleerd via Windows Update.

[MS16-051: Beveiligingsupdate voor Internet Explorer: 10 mei 2016 (KB 3154070)](https://support.microsoft.com/kb/3154070)

### <a name="gateway-configuration-failed-with-a-null-reference-exception"></a>De gatewayconfiguratie is mislukt met een null-referentie-uitzondering
Mogelijk treedt er een fout op vergelijkbaar met de volgende.

        Failed to update gateway details.  Please try again.
        Error updating gateway configuration.

Hierbij wordt een stack-trace getoond, die mogelijk het volgende bevat.

        Microsoft.PowerBI.DataMovement.Pipeline.Diagnostics.CouldNotUpdateGatewayConfigurationException: Error updating gateway configuration. ----> System.ArgumentNullException: Value cannot be null.
        Parameter name: serviceSection

Als u een upgrade uitvoert van een oudere gateway, behouden we het configuratiebestand. Mogelijk ontbreekt er een sectie. Wanneer de gateway deze sectie probeert te lezen, wordt de bovenstaande null-referentie-uitzondering weergegeven.

U kunt de volgende stappen volgen om dit op te lossen.

1. Verwijder de gateway.
2. Verwijder de volgende map.
   
        c:\Program Files\on-premises data gateway
3. Installeer de gateway opnieuw.
4. Optioneel kunt u de herstelsleutel voor het herstellen van een bestaande gateway toepassen.

### <a name="support-for-tls-1112"></a>Ondersteuning voor TLS 1.1/1.2
Sinds de update van augustus 2017 maakt de on-premises gegevensgateway standaard gebruik van Transport Layer Security (TLS) 1.1 of 1.2 om te communiceren met de **Power BI-service**. Eerdere versies van de on-premises gegevensgateway maken standaard gebruik van TLS 1.0. Op 1 november 2017 wordt de ondersteuning voor TLS 1.0 beëindigd. Upgrade daarom vóór die datum de installatie van uw on-premises gegevensgateway naar de release van augustus 2017 of later om te garanderen dat uw gateways blijven functioneren.

Het is belangrijk om te weten dat TLS 1.0 tot 1 november nog steeds wordt ondersteund door de on-premises gegevensgateway en door de gateway wordt gebruikt als back-upprotocol bij problemen. Om ervoor te zorgen dat al het verkeer van en naar de gateway gebruikmaakt van TLS 1.1 of 1.2 (en om te voorkomen dat uw gateway nog TLS 1.0 gebruikt), moet u de volgende registersleutels toevoegen op de computer waarop de gateway-service wordt uitgevoerd:

        [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\v4.0.30319]"SchUseStrongCrypto"=dword:00000001
        [HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\.NETFramework\v4.0.30319]"SchUseStrongCrypto"=dword:00000001

> [!NOTE]
> Door deze registersleutels toe te voegen of te wijzigen, wordt deze wijziging toegepast voor alle .NET-toepassingen. Zie [Transport Layer Security (TLS) registry settings](https://docs.microsoft.com/windows-server/security/tls/tls-registry-settings) (Registerinstellingen voor Transport Layer Security (TLS)) voor meer informatie over registerwijzigingen die invloed hebben op TLS voor andere toepassingen.
> 
> 

## <a name="data-sources"></a>Gegevensbronnen
### <a name="error-unable-to-connect-details-invalid-connection-credentials"></a>Fout: Er kan geen verbinding worden gemaakt. Details: 'Ongeldige verbindingsreferenties'
Onder **Details weergeven** moet de foutmelding worden weergegeven die van de gegevensbron is ontvangen. Voor SQL Server ziet dit er ongeveer als volgt uit.

    Login failed for user 'username'.

Controleer of u de juiste gebruikersnaam en het juiste wachtwoord gebruikt. Controleer ook of deze referenties verbinding kunnen maken met de gegevensbron. Zorg ervoor dat het gebruikte account overeenkomt met de geselecteerde **verificatiemethode**.

### <a name="error-unable-to-connect-details-cannot-connect-to-the-database"></a>Fout: Er kan geen verbinding worden gemaakt. Details: 'Kan geen verbinding maken met de database'
Er kan wel verbinding worden gemaakt met de server, maar niet met de opgegeven database. Controleer de naam van de database en of de gebruikersreferenties de juiste machtigingen hebben voor toegang tot deze database.

Onder **Details weergeven** moet de foutmelding worden weergegeven die van de gegevensbron is ontvangen. Voor SQL Server ziet dit er ongeveer als volgt uit.

    Cannot open database "AdventureWorks" requested by the login. The login failed. Login failed for user 'username'.

### <a name="error-unable-to-connect-details-unknown-error-in-data-gateway"></a>Fout: Er kan geen verbinding worden gemaakt. Details: 'Onbekende fout in de gegevensgateway'
Deze fout kan verschillende oorzaken hebben. Controleer of u verbinding kunt maken met de gegevensbron vanaf de computer die als host fungeert voor de gateway. Dit kan voorkomen wanneer de server niet toegankelijk is.

Onder **Details weergeven** wordt de foutcode **DM_GWPipeline_UnknownError** weergegeven.

U kunt voor meer informatie ook de logboeken raadplegen: Gebeurtenislogboeken > **Logboeken Toepassingen en Services** > **On-premises gegevensgateway-service**.

### <a name="error-we-encountered-an-error-while-trying-to-connect-to-server-details-we-reached-the-data-gateway-but-the-gateway-cant-access-the-on-premises-data-source"></a>Fout: Er is een fout opgetreden tijdens het verbinden met <server>. Details: 'Er is contact gemaakt met de gegevensgateway, maar de gateway heeft geen toegang tot de on-premises gegevensbron.'
Er kan geen verbinding worden gemaakt met de opgegeven gegevensbron. Controleer de informatie die is opgegeven voor de gegevensbron.

Onder **Details weergeven** wordt de foutcode **DM_GWPipeline_Gateway_DataSourceAccessError** weergegeven.

Als de onderliggende foutmelding op de volgende melding lijkt, betekent dit dat het account dat u voor de gegevensbron gebruikt, geen serverbeheerder is voor het betreffende Analysis Services-exemplaar. [Meer informatie](https://docs.microsoft.com/sql/analysis-services/instances/grant-server-admin-rights-to-an-analysis-services-instance)

    The 'CONTOSO\account' value of the 'EffectiveUserName' XML for Analysis property is not valid.

Als de onderliggende foutmelding op de volgende melding lijkt, kan dit betekenen dat het directory-kenmerk [token-groups-global-and-universal](https://msdn.microsoft.com/library/windows/desktop/ms680300.aspx) (TGGAU) mogelijk ontbreekt voor het serviceaccount voor Analysis Services.

    The user name or password is incorrect.

Het TGGAU-kenmerk is ingeschakeld voor domeinen met toegang die compatibel is met oudere versies dan Windows 2000. Voor de meeste nieuw gemaakte domeinen is dit kenmerk echter niet standaard ingeschakeld. Meer informatie hierover vindt u op [deze pagina](https://support.microsoft.com/kb/331951).

U kunt dit controleren door de volgende stappen te volgen.

1. Maak verbinding met de Analysis Services-computer in SQL Server Management Studio. Voer in de geavanceerde verbindingseigenschappen EffectiveUserName in voor de betrokken gebruiker en kijk of de fout nog steeds optreedt.
2. U kunt het Active Directory-hulpprogramma dsacls gebruiken om te controleren of het kenmerk wordt weergegeven. Dit hulpprogramma is normaal gesproken te vinden op een domeincontroller. U moet weten wat de onderscheidende domeinnaam voor het account is en die aan het hulpprogramma doorgeven.
   
        dsacls "CN=John Doe,CN=UserAccounts,DC=contoso,DC=com"
   
    Het resultaat zou op het volgende moeten lijken.
   
            Allow BUILTIN\Windows Authorization Access Group
                                          SPECIAL ACCESS for tokenGroupsGlobalAndUniversal
                                          READ PROPERTY

Om dit probleem op te lossen, moet u TGGAU inschakelen voor het account dat wordt gebruikt voor de Windows-service van Analysis Services.

**Een andere mogelijkheid is dat de gebruikersnaam of het wachtwoord onjuist is**

Deze fout kan ook optreden als de Analysis Services-server zich in een ander domein bevindt dan de gebruikers en er geen wederzijdse vertrouwensrelatie tot stand is gebracht.

In dat geval moet u samenwerken met uw domeinbeheerders om de vertrouwensrelatie tussen de domeinen te controleren.

**Kan de gegevensbronnen van de gegevensgateway niet zien via de Analysis Services-functie 'Gegevens ophalen' van de Power BI-service**

Zorg ervoor dat uw account wordt vermeld op het tabblad **Gebruikers** van de gegevensbron in de configuratie van de gateway. Als u geen toegang tot de gateway hebt, neemt u contact op met de beheerder van de gateway en vraagt u deze de informatie te controleren. Alleen accounts die zijn opgenomen in de lijst met **Gebruikers**, zien de gegevensbron die wordt weergegeven in de Analysis Services-lijst.

## <a name="datasets"></a>Gegevenssets
### <a name="error-there-is-not-enough-space-for-this-row"></a>Fout: Er is onvoldoende ruimte voor deze rij.
Dit gebeurt als een enkele rij groter is dan 4 MB. U moet bepalen om welke rij uit de gegevensbron het gaat en deze wegfilteren of kleiner maken.

### <a name="error-the-server-name-provided-doesnt-match-the-server-name-on-the-sql-server-ssl-certificate"></a>Fout: De opgegeven servernaam komt niet overeen met de servernaam op het SSL-certificaat van SQL Server.
Dit kan gebeuren wanneer de certificaat-CN voor de servers een FQDN (volledig gekwalificeerde domeinnaam) is, maar u alleen de netbios-naam voor de server hebt opgegeven. Hierdoor komt de servernaam niet overeen met het certificaat. Om dit probleem op te lossen, moet u de servernaam in de gegevensbron van de gateway en in het PBIX-bestand instellen op de FQDN van de server.

### <a name="i-dont-see-the-on-premises-data-gateway-persent-when-configuring-scheduled-refresh"></a>De on-premises gegevensgateway wordt niet weergegeven bij het configureren van een geplande vernieuwing.
Dit kan door meerdere scenario's worden veroorzaakt.

1. Mogelijk komen de server- en databasenamen die zijn ingevoerd in Power BI Desktop, niet overeen met de geconfigureerde gegevensbron voor de gateway. Deze moeten dezelfde waarden gebruiken. De waarden zijn niet hoofdlettergevoelig.
2. Uw account wordt niet vermeld op het tabblad **Gebruikers** van de gegevensbron in de configuratie van de gateway. Neem contact op met de beheerder van de gateway om aan deze lijst te worden toegevoegd.
3. Uw Power BI Desktop-bestand bevat meerdere gegevensbronnen en niet al deze gegevensbronnen zijn geconfigureerd bij de gateway. U moet elke gegevensbron bij de gateway definiëren als u wilt dat de gateway wordt weergegeven voor geplande vernieuwing.

### <a name="error-the-received-uncompressed-data-on-the-gateway-client-has-exceeded-limit"></a>Fout: De niet-gecomprimeerde gegevens die door de gatewayclient zijn ontvangen, hebben de limiet overschreden.
De exacte beperking is 10 GB aan niet-gecomprimeerde gegevens per tabel. Als dit probleem optreedt, zijn er goede mogelijkheden om uw gegevens te optimaliseren en het probleem te voorkomen. Een gunstig resultaat bereikt u vooral met het terugdringen van het gebruik van lange tekenreekswaarden met veel herhaling en het vervangen hiervan door een genormaliseerde sleutel, en met het verwijderen van ongebruikte kolommen.

## <a name="reports"></a>Rapporten
### <a name="report-could-not-access-the-data-source-because-you-do-not-have-access-to-our-data-source-via-an-on-premises-data-gateway"></a>Rapport heeft geen toegang tot de gegevensbron omdat u geen toegang tot onze gegevensbron hebt via een on-premises gegevensgateway.
Dit wordt meestal veroorzaakt door een van de volgende dingen.

1. De informatie van de gegevensbron komt niet overeen met wat er in de onderliggende gegevensset aanwezig is. De server- en databasenaam die in de on-premises gegevensgateway zijn opgegeven voor de gegevensbron, moeten overeenkomen met wat u hebt opgegeven in Power BI Desktop. Als u in Power BI Desktop een IP-adres gebruikt, moet de gegevensbron voor de on-premises gegevensgateway ook een IP-adres gebruiken.
2. Er is op geen enkele gateway binnen uw organisatie een gegevensbron beschikbaar. U kunt de gegevensbron configureren op een nieuwe of bestaande on-premises gegevensgateway.

### <a name="error-data-source-access-error-please-contact-the-gateway-administrator"></a>Fout: Fout met toegang tot de gegevensbron. Neem contact op met de gatewaybeheerder.
Als dit rapport gebruikmaakt van een live Analysis Services-verbinding, treedt er mogelijk een probleem op waarbij er een waarde aan EffectiveUserName wordt doorgegeven die niet geldig is of geen machtigingen heeft op de Analysis Services-computer. Een verificatieprobleem wordt doorgaans veroorzaakt doordat de waarde die voor EffectiveUserName wordt doorgegeven, niet overeenkomt met een lokale User Principal Name (UPN).

Doe het volgende om dit te controleren.

1. U vindt de effectieve gebruikersnaam in de [gatewaylogboeken](#logs).
2. Wanneer u de waarde hebt achterhaald die wordt doorgegeven, controleert u of deze juist is. Als dit uw gebruiker betreft, kunt u de volgende opdracht uitvoeren vanaf de opdrachtprompt om te zien wat de UPN moet zijn. De UPN ziet eruit als een e-mailadres.
   
        whoami /upn

Eventueel kunt u nagaan wat Power BI ophaalt uit Azure Active Directory.

1. Blader hiervoor naar [https://graphexplorer.cloudapp.net](https://graphexplorer.cloudapp.net).
2. Selecteer **Aanmelden** in de rechterbovenhoek.
3. Voer de volgende query uit. Er wordt nu een vrij groot JSON-antwoord weergegeven.
   
        https://graph.windows.net/me?api-version=1.5
4. Zoek hierin naar **UserPrincipalName**.

Als uw Azure Active Directory-UPN niet overeenkomt met uw lokale Active Directory-UPN, kunt u de functie [Gebruikersnamen toewijzen](service-gateway-enterprise-manage-ssas.md#map-user-names) gebruiken om deze te vervangen door een geldige waarde. U kunt ook contact opnemen met uw tenantbeheerder of lokale Active Directory-beheerder om uw UPN te wijzigen.

<!-- Shared Troubleshooting Firewall/Proxy Include -->
[!INCLUDE [gateway-onprem-tshoot-firewall-include](./includes/gateway-onprem-tshoot-firewall-include.md)]

U vindt de datacenterregio waarin u zich bevindt, met behulp van de volgende stappen:

1. Selecteer **?** in de rechterbovenhoek van de Power BI-service.
2. Selecteer **Over Power BI**.
3. Uw gegevensregio wordt weergegeven bij **Uw gegevens worden opgeslagen in**.
   
    ![](media/service-gateway-onprem-tshoot/power-bi-data-region.png)

Als u nog steeds niet voldoende informatie hebt, kunt u een netwerktracering uitvoeren met een hulpprogramma zoals [fiddler](#fiddler) of netsh, hoewel dit geavanceerde methoden zijn en u wellicht hulp nodig hebt bij het analyseren van de verzamelde gegevens. U kunt voor hulp contact opnemen met de [ondersteuning](https://support.microsoft.com).

## <a name="performance"></a>Prestaties
<iframe width="560" height="315" src="https://www.youtube.com/embed/IJ_DJ30VNk4?showinfo=0" frameborder="0" allowfullscreen></iframe>

### <a name="performance-counters"></a>Prestatiemeters
Er zijn een aantal prestatiemeteritems die kunnen worden gebruikt voor het bijhouden van de activiteiten van de gateway. Dit is handig om te bepalen of er een grote activiteitsbelasting is en er mogelijk een nieuwe gateway moet worden gemaakt. Deze items geven niet aan hoelang iets duurt.

Deze items zijn op te vragen via het hulpprogramma Prestatiemeter van Windows.

![](media/service-gateway-onprem-tshoot/gateway-perfmon.png)

Deze prestatiemeteritems zijn in enkele algemene groepen ingedeeld.

| Type item | Beschrijving |
| --- | --- |
| ADO.NET |Dit wordt gebruikt voor DirectQuery-verbindingen. |
| ADOMD |Dit wordt gebruikt voor Analysis Services 2014 en eerdere versies. |
| OLEDB |Dit wordt gebruikt door bepaalde gegevensbronnen. Hieronder vallen SAP HANA en Analysis Services 2016 en latere versies. |
| Mashup |Hieronder vallen alle geïmporteerde gegevensbronnen. Als u geplande vernieuwing of vernieuwing op aanvraag gebruikt, verloopt dit via de mashup-engine. |

Hier volgt een overzicht van de beschikbare prestatiemeteritems.

| Prestatiemeteritem | Beschrijving |
| --- | --- |
| Aantal open ADO.NET-verbindingen uitgevoerd per seconde |Aantal open ADO.NET-verbindingsacties uitgevoerd per seconde (geslaagd of mislukt). |
| Aantal open ADO.NET-verbindingen mislukt per seconde |Aantal open ADO.NET-verbindingsacties mislukt per seconde. |
| Aantal ADO.NET-query's uitgevoerd per seconde |Aantal ADO.NET-query's uitgevoerd per seconde (geslaagd of mislukt). |
| Aantal ADO.NET-query's mislukt per seconde |Aantal mislukte ADO.NET-query's uitgevoerd per seconde. |
| Aantal open ADOMD-verbindingen uitgevoerd per seconde |Aantal open ADOMD-verbindingsacties uitgevoerd per seconde (geslaagd of mislukt). |
| Aantal open ADOMD-verbindingen mislukt per seconde |Aantal open ADOMD-verbindingsacties mislukt per seconde. |
| Aantal ADOMD-query's uitgevoerd per seconde |Aantal ADOMD-query's uitgevoerd per seconde (geslaagd of mislukt). |
| Aantal ADOMD-query's mislukt per seconde |Aantal mislukte ADOMD-query's uitgevoerd per seconde. |
| Totaal aantal open verbindingen uitgevoerd per seconde |Aantal open verbindingsacties uitgevoerd per seconde (geslaagd of mislukt). |
| Totaal aantal open verbindingen mislukt per seconde |Aantal mislukte open verbindingsacties uitgevoerd per seconde. |
| Totaal aantal query's uitgevoerd per seconde |Aantal query's uitgevoerd per seconde (geslaagd of mislukt). |
| Aantal items in de ADO.NET-verbindingsgroep |Aantal items in de ADO.NET-verbindingsgroep. |
| Aantal items in de OLEDB-verbindingsgroep |Aantal items in de OLEDB-verbindingsgroep. |
| Aantal items in de Service Bus-groep |Aantal items in de Service Bus-groep. |
| Aantal open Mashup-verbindingen uitgevoerd per seconde |Aantal open Mashup-verbindingsacties uitgevoerd per seconde (geslaagd of mislukt). |
| Aantal open Mashup-verbindingen mislukt per seconde |Aantal open Mashup-verbindingsacties mislukt per seconde. |
| Aantal Mashup-query's uitgevoerd per seconde |Aantal Mashup-query's uitgevoerd per seconde (geslaagd of mislukt). |
| Aantal Mashup-query's mislukt per seconde |Aantal mislukte Mashup-query's uitgevoerd per seconde. |
| Aantal OLEDB-query's voor sets met meerdere resultaten mislukt per seconde |Aantal mislukte OLEDB-query's voor sets met meerdere resultaten uitgevoerd per seconde. |
| Aantal OLEDB-query's voor sets met meerdere resultaten uitgevoerd per seconde |Aantal OLEDB-query's voor sets met meerdere resultaten uitgevoerd per seconde (geslaagd of mislukt). |
| Totaal aantal open OLEDB-verbindingen uitgevoerd per seconde |Aantal open OLEDB-verbindingsacties uitgevoerd per seconde (geslaagd of mislukt). |
| Totaal aantal open OLEDB-verbindingen mislukt per seconde |Aantal open OLEDB-verbindingsacties mislukt per seconde. |
| Aantal OLEDB-query's uitgevoerd per seconde |Aantal OLEDB-query's voor sets met meerdere resultaten uitgevoerd per seconde (geslaagd of mislukt). |
| Aantal OLEDB-query's mislukt per seconde |Aantal mislukte OLEDB-query's voor sets met meerdere resultaten uitgevoerd per seconde. |
| Aantal OLEDB-query's voor sets met enkelvoudige resultaten uitgevoerd per seconde |Aantal OLEDB-query's voor sets met enkelvoudige resultaten uitgevoerd per seconde (geslaagd of mislukt). |
| Aantal query's mislukt per seconde |Aantal mislukte query's uitgevoerd per seconde. |
| Aantal OLEDB-query's voor sets met enkelvoudige resultaten mislukt per seconde |Aantal mislukte OLEDB-query's voor sets met enkelvoudige resultaten uitgevoerd per seconde. |

## <a name="reviewing-slow-performing-queries"></a>Traag presterende query's controleren
Mogelijk vindt u de respons via de gateway te langzaam. Dit kan bijvoorbeeld het geval zijn voor DirectQuery-query's of bij het vernieuwen van uw geïmporteerde gegevensset. U kunt aanvullende logboekregistratie inschakelen voor query's en de bijbehorende tijdinstellingen, zodat u beter begrijpt wat de prestaties vertraagt. Wanneer u een langlopende query hebt gevonden, zijn er misschien extra aanpassingen vereist in uw gegevensbron om de queryprestaties te verbeteren. Denk bijvoorbeeld aan het aanpassen van de indexen voor een SQL Server-query.

U moet twee configuratiebestanden wijzigen om de duur van een query te bepalen.

### <a name="microsoftpowerbidatamovementpipelinegatewaycoredllconfig"></a>Microsoft.PowerBI.DataMovement.Pipeline.GatewayCore.dll.config
In het bestand *Microsoft.PowerBI.DataMovement.Pipeline.GatewayCore.dll.config* dient u de waarde `EmitQueryTraces` te wijzigen van `False` naar `True`. Dit bestand bevindt zich in *C:\Program Files\On-premises data gateway*. Als u `EmitQueryTraces` inschakelt, worden de query's bijgehouden die vanaf de gateway naar een gegevensbron worden verzonden.

> [!IMPORTANT]
> Het inschakelen van EmitQueryTraces kan ervoor zorgen dat de grootte van het logboekbestand aanzienlijk toeneemt, afhankelijk van het gatewaygebruik. Wanneer u klaar bent met het controleren van de logboeken, kunt u EmitQueryTraces het beste weer instellen op False. Het wordt afgeraden om deze instelling langere tijd ingeschakeld te laten.
> 
> 

```
<setting name="EmitQueryTraces" serializeAs="String">
    <value>True</value>
</setting>
```

**Voorbeeld van query**

```
DM.EnterpriseGateway Information: 0 : 2016-09-15T16:09:27.2664967Z DM.EnterpriseGateway    4af2c279-1f91-4c33-ae5e-b3c863946c41    d1c77e9e-3858-4b21-3e62-1b6eaf28b176    MGEQ    c32f15e3-699c-4360-9e61-2cc03e8c8f4c    FF59BC20 [DM.GatewayCore] Executing query (timeout=224) "<pi>
SELECT
TOP (1000001) [t0].[ProductCategoryName],[t0].[FiscalYear],SUM([t0].[Amount])
 AS [a0]
FROM
(
(select [$Table].[ProductCategoryName] as [ProductCategoryName],
    [$Table].[ProductSubcategory] as [ProductSubcategory],
    [$Table].[Product] as [Product],
    [$Table].[CustomerKey] as [CustomerKey],
    [$Table].[Region] as [Region],
    [$Table].[Age] as [Age],
    [$Table].[IncomeGroup] as [IncomeGroup],
    [$Table].[CalendarYear] as [CalendarYear],
    [$Table].[FiscalYear] as [FiscalYear],
    [$Table].[Month] as [Month],
    [$Table].[OrderNumber] as [OrderNumber],
    [$Table].[LineNumber] as [LineNumber],
    [$Table].[Quantity] as [Quantity],
    [$Table].[Amount] as [Amount]
from [dbo].[V_CustomerOrders] as [$Table])
)
 AS [t0]
GROUP BY [t0].[ProductCategoryName],[t0].[FiscalYear] </pi>"
```

### <a name="microsoftpowerbidatamovementpipelinegatewaycoredllconfig"></a>Microsoft.PowerBI.DataMovement.Pipeline.GatewayCore.dll.config
In het bestand *Microsoft.PowerBI.DataMovement.Pipeline.Diagnostics.dll.config* dient u de waarde `TraceVerbosity` te wijzigen van `4` naar `5`. Dit bestand bevindt zich in *C:\Program Files\On-premises data gateway*. Als u deze instelling wijzigt, worden er uitgebreide logboekvermeldingen naar het gatewaylogboek geschreven. Hierbij wordt voor vermeldingen ook de duur getoond.

> [!IMPORTANT]
> Door TraceVerbosity in te stellen op `5`, kan de grootte van het logboekbestand aanzienlijk toenemen, afhankelijk van het gatewaygebruik. Wanneer u klaar bent met het controleren van de logboeken, kunt u TraceVerbosity het beste weer instellen op `4`. Het wordt afgeraden om deze instelling langere tijd ingeschakeld te laten.
> 
> 

```
<setting name="TracingVerbosity" serializeAs="String">
    <value>5</value>
</setting>
```

<a name="activities"></a>

### <a name="activity-types"></a>Activiteitstypen
| Activiteitstype | Beschrijving |
| --- | --- |
| MGEQ |Query's uitgevoerd via ADO.NET. Hieronder vallen DirectQuery-gegevensbronnen. |
| MGEO |Query's uitgevoerd via OLEDB. Hieronder vallen SAP HANA en Analysis Services 2016. |
| MGEM |Query's uitgevoerd vanuit de Mashup-engine. Deze wordt gebruikt voor geïmporteerde gegevenssets die gebruikmaken van geplande vernieuwing of vernieuwing op verzoek. |

### <a name="determine-the-duration-of-a-query"></a>De duur van een query bepalen
Om te bepalen hoe lang het duurde om een query bij de gegevensbron uit te voeren, kunt u het volgende doen.

1. Open het logboek voor de gateway.
2. Zoek naar een [activiteitstype](#activities) om de query te vinden. Een voorbeeld hiervan is MGEQ.
3. Noteer de tweede GUID: dit is de aanvraag-id.
4. Zoek verder naar MGEQ totdat u de vermelding FireActivityCompletedSuccessfullyEvent vindt, waar de duur bij wordt getoond. Controleer vervolgens of de vermelding dezelfde aanvraag-id bevat. De duur wordt getoond in milliseconden.
   
        DM.EnterpriseGateway Verbose: 0 : 2016-09-26T23:08:56.7940067Z DM.EnterpriseGateway    baf40f21-2eb4-4af1-9c59-0950ef11ec4a    5f99f566-106d-c8ac-c864-c0808c41a606    MGEQ    21f96cc4-7496-bfdd-748c-b4915cb4b70c    B8DFCF12 [DM.Pipeline.Common.TracingTelemetryService] Event: FireActivityCompletedSuccessfullyEvent (duration=5004)
   
   > [!NOTE]
   > FireActivityCompletedSuccessfullyEvent is een uitgebreid item. Dit item wordt niet vastgelegd tenzij TraceVerbosity is ingesteld op niveau 5.
   > 
   > 

<!-- Shared Troubleshooting tools Include -->
[!INCLUDE [gateway-onprem-tshoot-tools-include](./includes/gateway-onprem-tshoot-tools-include.md)]

### <a name="refresh-history"></a>Geschiedenis vernieuwen
Wanneer u de gateway gebruikt voor geplande vernieuwing, kan de optie **Geschiedenis vernieuwen** helpen om te zien welke fouten zijn opgetreden. Daarnaast kan deze optie nuttige gegevens bieden als u een ondersteuningsaanvraag wilt aanmaken. U kunt zowel geplande vernieuwingen als vernieuwingen op aanvraag bekijken. U krijgt als volgt toegang tot de optie **Geschiedenis vernieuwen**.

1. Ga in het navigatiedeelvenster van Power BI naar **Gegevenssets**, selecteer een gegevensset &gt; Menu openen &gt; **Vernieuwen plannen**.
   
    ![](media/service-gateway-onprem-tshoot/scheduled-refresh.png)
2. Selecteer in het venster **Instellingen voor...** &gt; **Vernieuwen plannen** en selecteer **Geschiedenis vernieuwen**.
   
    ![](media/service-gateway-onprem-tshoot/scheduled-refresh-2.png)
   
    ![](media/service-gateway-onprem-tshoot/refresh-history.png)

Voor meer informatie over het oplossen van problemen met betrekking tot vernieuwen raadpleegt u het artikel [Problemen met vernieuwingsscenario's oplossen](refresh-troubleshooting-refresh-scenarios.md).

## <a name="next-steps"></a>Volgende stappen
[Configuring proxy settings for the on-premises data gateway](service-gateway-proxy.md) (Proxy-instellingen voor de on-premises gegevensgateway configureren)  
[On-premises data gateway](service-gateway-onprem.md) (On-premises gegevensgateway)  
[On-premises data gateway in-depth](service-gateway-onprem-indepth.md) (On-premises gegevensgateway - uitgebreid)  
[Manage your data source - Analysis Services](service-gateway-enterprise-manage-ssas.md) (Uw gegevensbron beheren - Analysis Services)  
[Manage your data source - SAP HANA](service-gateway-enterprise-manage-sap.md) (Uw gegevensbron beheren - SAP HANA)  
[Manage your data source - SQL Server](service-gateway-enterprise-manage-sql.md) (Uw gegevensbron beheren - SQL Server)  
[Manage your data source - Import/Scheduled refresh](service-gateway-enterprise-manage-scheduled-refresh.md) (Uw gegevensbron beheren - importeren/geplande vernieuwing)  
Hebt u nog vragen? [Misschien dat de Power BI-community het antwoord weet](http://community.powerbi.com/)
