---
title: Verwalten vertrauenswürdiger Anwendungen
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Eine vertrauenswürdige Anwendung ist eine Anwendung, die auf dem Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK basiert, das von Skype for Business Server als vertrauenswürdig eingestuft wird.
ms.openlocfilehash: 909ade1fbb44410d6b2acb695b8111e43d766e50
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/25/2022
ms.locfileid: "65674537"
---
# <a name="manage-trusted-applications-in-skype-for-business-server"></a>Verwalten vertrauenswürdiger Anwendungen in Skype for Business Server

Eine *vertrauenswürdige Anwendung* ist eine Anwendung, die auf dem Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK basiert und von Skype for Business Server als vertrauenswürdig eingestuft wird. Ausführliche Informationen zu UCMA-Anwendungen finden Sie unter "Unified Communications Managed API 3.0 Core SDK Documentation" unter https://go.microsoft.com/fwlink/p/?linkId=210320.

Für eine erfolgreiche Veröffentlichung, Aktivierung oder Deaktivierung einer Topologie beim Hinzufügen oder Entfernen einer Serverrolle müssen Sie als Mitglied der Gruppen "RTCUniversalServerAdmins" und "Domänen-Admins" angemeldet sein. 

In diesem Artikel erfahren Sie, wie Sie einen neuen vertrauenswürdigen Anwendungsserver konfigurieren, eine Liste vertrauenswürdiger Anwendungen anzeigen und Informationen zu vertrauenswürdigen Anwendungen anzeigen. 

## <a name="configure-a-new-trusted-application-server"></a>Konfigurieren eines neuen vertrauenswürdigen Anwendungsservers

1.  Melden Sie sich auf dem Computer, auf dem der Topologie-Generator installiert ist, als Mitglied der Gruppe "Domänen-Admins" oder "RTCUniversalServerAdmins" an.

2.  Topologie-Generator starten: Klicken Sie auf **"Start**", dann auf **"Alle Programme**", klicken Sie auf **Skype for Business Server**, und klicken Sie dann auf **Skype for Business Server Topologie-Generator**.

3.  Wählen Sie **Topologie aus einer vorhandenen Bereitstellung herunterladen**, und klicken Sie dann auf **OK**.

4.  Klicken Sie im Dialogfeld " **Topologie speichern** unter" auf die Topologie-Generator-Datei, die Sie verwenden möchten, und klicken Sie dann auf **"Speichern"**.

5.  Klicken Sie im linken Bereich mit der rechten Maustaste auf **vertrauenswürdige Anwendungsserver**, und klicken Sie dann auf **"Neuer vertrauenswürdiger Anwendungspool"**.

6.  Geben Sie den **Pool-FQDN** des vertrauenswürdigen Anwendungspools ein, wählen Sie aus, ob es sich um einen einzelnen oder mehrere Server handelt, und klicken Sie dann auf **"Weiter**".

7.  **Wählen Sie auf der Seite "Nächsten Hop auswählen**" in der Liste den Skype for Business Server Front-End-Pool aus.

8.  Klicken Sie auf **Fertig stellen**.

9.  Wählen Sie den oberen Knoten **Skype for Business Server** aus, und klicken Sie dann im Menü **"Aktionen**" auf "**Topologie veröffentlichen"**.
    
    Der **Pool für vertrauenswürdige Anwendungen** sollte erfolgreich erstellt und dem richtigen Front-End-Pool zugeordnet sein.


## <a name="view-a-list-of-trusted-applications"></a>Anzeigen einer Liste vertrauenswürdiger Anwendungen

Sie können die Skype for Business Server Systemsteuerung verwenden, um eine Liste der vertrauenswürdigen Anwendungen anzuzeigen, die Sie in Ihrer Skype for Business Server-Umgebung bereitgestellt haben. Eine vertrauenswürdige Anwendung ist eine Anwendung, die auf dem Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK basiert, das von Skype for Business Server als vertrauenswürdig eingestuft wird. Die Eigenschaften dieser Vertrauensbeziehung werden in der folgenden Liste zusammengefasst:

  - Vertrauenswürdige Anwendungen werden von Skype for Business Server nicht zur Authentifizierung aufgefordert.

  - Vertrauenswürdige Anwendungen werden nicht durch Skype for Business Server für SIP-Transaktionen, Verbindungen oder ausgehende VoIP-Anrufe (Voice over Internet Protocol) gedrosselt.

  - Vertrauenswürdige Anwendungen können die Identität beliebiger Benutzer annehmen und Konferenzen beitreten, ohne in Konferenzlisten aufzutauchen.

  - Vertrauenswürdige Anwendungen sind hochverfügbar und ausfallsicher.

Im Skype for Business Server Systemsteuerung können Sie den Namen der Anwendungen, den Pool, in dem sie ausgeführt werden, und den verwendeten Port sehen.


### <a name="to-view-a-list-of-trusted-applications"></a>So zeigen Sie eine Liste der vertrauenswürdigen Anwendungen an

1.  Melden Sie sich über ein Benutzerkonto, das der Rolle "CsServerAdministrator", "CsAdministrator", "CsHelpDesk" oder "CsViewOnlyAdministrator" zugewiesen ist, bei einem beliebigen Computer in Ihrer internen Bereitstellung an. Ausführliche Informationen zu den in Skype for Business Server verfügbaren vordefinierten Administratorrollen finden Sie unter [Rollenbasierte Zugriffssteuerung (Role-Based Access Control, RBAC).](../plan-your-deployment/security/role-based-access-control-rbac.md)

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Admin URL ein, um die Skype for Business Server Systemsteuerung zu öffnen.

3.  Klicken Sie in der linken Navigationsleiste auf **"Topologie**" und dann auf " **Vertrauenswürdige Anwendung"**.

4.  Klicken Sie auf der Seite **Vertrauenswürdige Anwendung** auf eine Spaltenüberschrift, um die Anwendungen bei Bedarf zu sortieren.


## <a name="view-trusted-application-information"></a>Anzeigen von Informationen zu vertrauenswürdigen Anwendungen

Sie können Informationen zu Ihren vertrauenswürdigen Anwendungen mithilfe von Windows PowerShell und dem Cmdlet **"Get-CsTrustedApplication**" anzeigen. Dieses Cmdlet kann entweder über die Skype for Business Server-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausgeführt werden. 


### <a name="to-view-trusted-applications"></a>So zeigen Sie vertrauenswürdige Anwendungen an

Um alle vertrauenswürdigen Anwendungen anzuzeigen, geben Sie den folgenden Befehl in die Skype for Business Server Verwaltungsshell ein, und drücken Sie dann die EINGABETASTE:
    
   **Get-CsConferenceDisclaimer**
    
   Mit diesem Befehl werden Informationen zu den einzelnen vertrauenswürdigen Anwendungen nach folgendem Muster zurückgegeben:
    
   Identität : CN={5dedf4b0-a590-49b3-80cf-f16f914bbef9},CN=Application Contacts,CN=RTC Service,CN=Services,CN=Configuration,DC=litware,DC=com<br/>
   RegistrarPool : 487279971<br/>
   HomeServer : CN=Lc Services,CN=Microsoft,CN=co1:2,CN=Pools,CN=RTC Service,CN=Services,CN=Configuration,DC=litware,DC=com OwnerUrn : urn:application:helpdesk<br/>
   SipAddress : sip:RtcApplication-dbf5142f-2bb2-4c4f-9531-b7fea45c5000@litware.com<br/>
   Displayname:<br/>
   DisplayNumber :<br/>
   LineURI :<br/>
   PrimaryLanguage : 0<br/>
   SecondaryLanguages : {}<br/>
   EnterpriseVoiceEnabled : True<br/>
   ExUmEnabled : False<br/>
   Enabled : True<br/>
    
   Ausführliche Informationen finden Sie unter [Get-CsTrustedApplication](/powershell/module/skype/Get-CsTrustedApplication).