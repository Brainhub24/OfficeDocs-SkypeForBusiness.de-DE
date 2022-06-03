---
title: Erstellen von DNS-Einträgen für Skype for Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 798a663c-0b63-4f75-b0a3-9c553cef8c5f
description: 'Zusammenfassung: Erfahren Sie, wie Sie DNS konfigurieren und DNS-Einträge für eine Installation von Skype for Business Server erstellen.'
ms.openlocfilehash: 5e974df94aba8b879c672250b69432dfd0a5f1f3
ms.sourcegitcommit: e99471689ff60f9ab1095bc075f8b4c5569c9634
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2022
ms.locfileid: "65860536"
---
# <a name="create-dns-records-for-skype-for-business-server"></a>Erstellen von DNS-Einträgen für Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie, wie Sie DNS konfigurieren und DNS-Einträge für eine Installation von Skype for Business Server erstellen.
  
Damit Skype for Business Server ordnungsgemäß funktionieren, müssen eine Reihe von DNS-Einstellungen (Domain Name System) vorhanden sein. Dies ist so, dass Clients wissen, wie sie auf die Dienste zugreifen können, und dass die Server voneinander wissen. Diese Einstellungen müssen nur einmal pro Bereitstellung abgeschlossen werden, da sie nach dem Zuweisen eines DNS-Eintrags in der gesamten Domäne verfügbar sind. Sie können die Schritte 1 bis 5 in beliebiger Reihenfolge ausführen. Sie müssen jedoch die Schritte 6, 7 und 8 in der reihenfolge und nach den Schritten 1 bis 5 ausführen, wie im Diagramm dargestellt. Das Erstellen von DNS-Einträgen umfasst Schritt 5 von 8. Weitere Informationen zur Planung von DNS finden Sie unter [Environmental requirements for Skype for Business Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) or [Server requirements for Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).
  
> [!IMPORTANT]
> Es ist wichtig zu beachten, dass dies nur ein Beispiel für das Erstellen von DNS-Einträgen in einer Windows Server-DNS-Umgebung ist. Es gibt viele andere DNS-Einträge, die für Skype for Business Server erforderlich sind, und das Verfahren zum Erstellen von DNS-Einträgen hängt vom System ab, das Sie zum Verwalten von DNS in Ihrer Organisation verwenden. Eine vollständige Liste der Anforderungen für DNS finden Sie unter [DNS-Anforderungen für Skype for Business Server](../../plan-your-deployment/network-requirements/dns.md). 
  
![Übersichtsdiagramm.](../../media/d2fc733c-6a80-4d17-a02f-93b8c4bfb999.png)
  
## <a name="configure-dns"></a>Konfigurieren von DNS

DNS-Einträge sind erforderlich, damit Skype for Business Server ordnungsgemäß funktionieren und für Benutzer zugänglich sind.
  
In diesem Beispiel wird ein DNS-FQDN mit dem Namen "pool.contoso.local" verwendet. Dieser Pool besteht aus drei Servern, auf denen Skype for Business Server Enterprise Edition ausgeführt werden. Ein Standard Edition Front-End-Server kann nur einen einzelnen Server enthalten. Mithilfe von Standard Edition würden Sie nur den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des einzelnen Standard Edition Servers verwenden, wenn Sie auf die Front-End-Rolle verweisen, anstatt einen DNS-Lastenausgleichspool mit Servern zu erstellen, wie in diesem Beispiel gezeigt. Dieses einfache Beispiel, in dem nur die Front-End-Rolle verwendet wird, enthält die DNS-Einträge in der folgenden Tabelle. Informationen zum Planen Ihrer spezifischen DNS-Anforderungen finden Sie unter [DNS-Anforderungen für Skype for Business Server](../../plan-your-deployment/network-requirements/dns.md). 
  
 
|**Beschreibung**|**Record type**|**Name**|**Wird aufgelöst zu**|**Lastenausgleichstyp**|
|:-----|:-----|:-----|:-----|:-----|
|FQDN für interne Webdienste  <br/> |Ein  <br/> |webint.contoso.local  <br/> |VIP für interne Webdienste  <br/> |Unterstützte Software und Hardware  <br/> |
|Pool-FQDN  <br/> |Ein  <br/> |pool.contoso.local  <br/> |IP-Adresse des Servers SFB01  <br/> |DNS  <br/> |
|SFB01-FQDN  <br/> |Ein  <br/> |SFB01.contoso.local  <br/> |IP-Adresse des Servers SFB01  <br/> |DNS  <br/> |
|Pool-FQDN  <br/> |Ein  <br/> |pool.contoso.local  <br/> |IP-Adresse des Servers SFB02  <br/> |DNS  <br/> |
|SFB02 FQDN  <br/> |Ein  <br/> |SFB02.contoso.local  <br/> |IP-Adresse des Servers SFB02  <br/> |DNS  <br/> |
|Pool-FQDN  <br/> |Ein  <br/> |pool.contoso.local  <br/> |IP-Adresse des Servers SFB03  <br/> |DNS  <br/> |
|SFB03 FQDN  <br/> |Ein  <br/> |SFB03.contoso.local  <br/> |IP-Adresse des Servers SFB03  <br/> |DNS  <br/> |
|Skype for Business Automatische Ermittlung  <br/> |Ein  <br/> |lyncdiscoverinternal.contoso.local  <br/> |VIP für interne Webdienste  <br/> |Unterstützte Software und Hardware  <br/> |
|Einfache Besprechungs-URL  <br/> |Ein  <br/> |meet.contoso.local  <br/> |VIP für interne Webdienste  <br/> |Unterstützte Software und Hardware  <br/> |
|Einfache URL zum Einwählen  <br/> |Ein  <br/> |dialin.contoso.local  <br/> |VIP für interne Webdienste  <br/> |Unterstützte Software und Hardware  <br/> |
|Einfache URL des Webplaners  <br/> |Ein  <br/> |scheduler.contoso.local  <br/> |VIP für interne Webdienste  <br/> |Unterstützte Software und Hardware  <br/> |
|Einfache URL für die Verwaltung  <br/> |Ein  <br/> |admin.contoso.local  <br/> |VIP für interne Webdienste  <br/> |Unterstützte Software und Hardware  <br/> |
|Legacyermittlung  <br/> |SRV  <br/> |_sipinternaltls._tcp.contoso.local  <br/> |Pool-FQDN (Port 5061)  <br/> |Nicht zutreffend  <br/> |
   
### <a name="create-dns-records"></a>Erstellen von DNS-Einträgen

1. Melden Sie sich beim DNS-Server an, und öffnen **Sie Server-Manager**.
    
2. Klicken Sie auf das Dropdownmenü **"Extras** " und dann auf **"DNS"**.
    
3. Erweitern Sie in der Konsolenstruktur für Ihre SIP-Domäne "**Forward Lookup Zones**" und dann die SIP-Domäne, in der Skype for Business Server installiert wird.
    
4. Klicken Sie mit der rechten Maustaste auf die SIP-Domäne, und wählen Sie " **Neuer Host (A oder AAAA)**" aus, wie in der Abbildung dargestellt.
    
     ![Den neuen A-Eintrag auswählen.](../../media/f89c5c1f-b5b7-428c-a6e3-2bcd12e878c3.png)
  
5. Geben Sie im **Feld "Name** " den Namen des Hostdatensatzes ein (der Domänenname wird automatisch angefügt).
    
6. Geben Sie im **Feld "IP-Adresse"** die IP-Adresse des einzelnen Front-End-Servers ein, und wählen **Sie dann ptr-Eintrag (Create associated pointer)** oder **Allow any authenticated user to update DNS records with the same owner name**, if applicable. Beachten Sie, dass dabei davon ausgegangen wird, dass DNS verwendet wird, um den gesamten Datenverkehr mit Ausnahme von Webdiensten auszugleichen. In diesem Beispiel haben wir drei Front-End-Server, wie in der Tabelle dargestellt.
    
   |**Servername**|**Type**|**Data**|
   |:-----|:-----|:-----|
   |SFB01  <br/> |Host (A)  <br/> |10.0.0.5  <br/> |
   |SFB02  <br/> |Host (A)  <br/> |10.0.0.6  <br/> |
   |SFB03  <br/> |Host (A)  <br/> |10.0.0.7  <br/> |
   
7. Erstellen Sie als Nächstes die DNS-Lastenausgleichseinträge für den Pool. Der DNS-Lastenausgleich ermöglicht DNS das Senden von Anforderungen an die einzelnen Server im Pool unter Verwendung desselben DNS-Poolnamens. Weitere Informationen zu DNS und Lastenausgleich finden Sie unter [DNS-Anforderungen für Skype for Business Server](../../plan-your-deployment/network-requirements/dns.md). 
    
    > [!NOTE]
    > Das Zusammenfassen mehrerer Server ist nur in Enterprise Edition Bereitstellungen verfügbar. Wenn Sie einen einzelnen Enterprise Server oder Standard Edition Server bereitstellen, müssen Sie nur einen A-Eintrag für den einzelnen Server erstellen. 
  
    Wenn Sie beispielsweise über einen Pool mit dem Namen "pool.contoso.local" und drei Front-End-Server verfügen, würden Sie die folgenden DNS-Einträge erstellen:
    
   |**FQDN**|**Type**|**Data**|
   |:-----|:-----|:-----|
   |pool.contoso.local  <br/> |Host (A)  <br/> |10.0.0.5  <br/> |
   |pool.contoso.local  <br/> |Host (A)  <br/> |10.0.0.6  <br/> |
   |pool.contoso.local  <br/> |Host (A)  <br/> |10.0.0.7  <br/> |
   
8. Erstellen Sie weiterhin A-Einträge für alle Server in der geplanten Bereitstellung. 
    
9. Um den Dienstdatensatz (SRV) für die Legacyermittlung zu erstellen, klicken Sie mit der rechten Maustaste auf die SIP-Domäne, und wählen Sie **"Andere neue Datensätze" aus**.
    
10. Klicken **Sie in "Ressourcendatensatztyp auswählen**" auf **"Dienstspeicherort(SRV)**", und klicken Sie dann auf **"Datensatz erstellen"**.
    
11. Klicken Sie auf **"Dienst**", und geben Sie **_sipinternaltls** ein.
    
12. Klicken Sie auf **Protokoll**, und geben Sie **_tcp** ein.
    
13. Klicken Sie auf **Portnummer**, und geben Sie **5061** ein.
    
14. Klicken Sie auf Host, der **diesen Dienst anbietet**, und geben Sie dann den FQDN des Pools oder Standard Edition Servers ein.
    
     ![Screenshot des Dialogfelds "Neuer Ressourcendatensatz".](../../media/54b1aac5-a2ec-41fe-90c0-02eaeaa9d1b4.png)
  
15. Klicken Sie auf **OK** und dann auf **Fertig**.
    
### <a name="verify-dns-records"></a>Überprüfen von DNS-Einträgen

1. Melden Sie sich bei einem Clientcomputer in der Domäne mit einem Konto an, das Mitglied der Gruppe "Authentifizierte Benutzer" ist oder über entsprechende Berechtigungen verfügt.
    
2. Klicken Sie auf **"Start**", geben **Sie "cmd**" ein, und drücken Sie die EINGABETASTE.
    
3. Geben Sie **nslookup \<FQDN of the Front End pool\>** oder **\<FQDN of the Standard Edition server or single Enterprise Edition server\>** ein, und drücken Sie die EINGABETASTE.
    
4. Überprüfen Sie weiterhin die restlichen A-Einträge für Ihre Bereitstellung.
    
5. Wenn Sie Legacyclients unterstützen und den SRV-Eintrag erstellt haben, überprüfen Sie ihn, indem Sie **"set type=srv** " an der **nslookup-Eingabeaufforderung** eingeben, und drücken Sie dann die EINGABETASTE.
    
6. Geben Sie **_sipinternaltls._tcp ein. *Domäne*** (z. B. _sipinternaltls._tcp.contoso.local), und drücken Sie dann die EINGABETASTE.
    
7. Die erwartete Ausgabe sollte der in der Abbildung gezeigten ähnlich sein. Beachten Sie, dass nicht alle DNS-Einträge in der Beispielausgabe angezeigt werden, aber alle Einträge sollten überprüft werden. 
    
     ![Überprüfen Sie die DNS-Einstellungen.](../../media/4fcaa70f-7717-4939-9652-d2048d6293cc.png)
  

