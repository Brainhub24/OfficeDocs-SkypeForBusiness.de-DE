---
title: Zuweisen von Richtlinien zu Benutzern und Gruppen
author: KarliStites
ms.author: kastites
ms.reviewer: tomkau, saragava, ritikag, jastark
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Lernen Sie die verschiedenen Methoden zum Zuweisen von Richtlinien zu Benutzern und Gruppen in Microsoft Teams.
f1keywords:
- ms.teamsadmincenter.bulkoperations.users.edit
- ms.teamsadmincenter.bulkoperations.edit
ms.openlocfilehash: 1aabc2472f612e7fff547c73c231a7b6301cc0d9
ms.sourcegitcommit: 5e9b50cd1b513f06734be6c024ac06d293b27089
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/10/2022
ms.locfileid: "62518587"
---
# <a name="assign-policies-to-users-and-groups"></a>Zuweisen von Richtlinien zu Benutzern und Gruppen

In diesem Artikel werden die verschiedenen Methoden zum Zuweisen von Richtlinien zu Benutzern und Gruppen in Microsoft Teams. Stellen Sie vor dem Lesen sicher, dass Sie unter Zuweisen von Richtlinien [in Teams – Erste Schritte gelesen haben](policy-assignment-overview.md).

## <a name="assign-a-policy-to-individual-users"></a>Zuweisen einer Richtlinie zu einzelnen Benutzern

Führen Sie die folgenden Schritte aus, um eine Richtlinie einem einzelnen Benutzer oder einer kleinen Anzahl von Benutzern gleichzeitig zuzuordnen.

### <a name="use-the-microsoft-teams-admin-center"></a>Verwenden des Microsoft Teams Admin Centers

So weisen Sie einem Benutzer eine Richtlinie zu:

1. Wechseln Sie in der linken [Navigationsleiste Microsoft Teams Admin Center](https://admin.teams.microsoft.com) zu **Benutzer** >  **Verwalten von Benutzern**.
2. Wählen Sie den Benutzer aus, indem Sie links des Benutzernamens klicken und dann **Einstellungen bearbeiten auswählen**.
3. Wählen Sie die Richtlinie aus, die Sie zuweisen möchten, und wählen Sie dann **Übernehmen aus**.

![Weisen Sie einem Benutzer im Admin Center Teams Richtlinie zu.](media/assign-policy-user.png)

> [!NOTE]
> Wenn Sie die Zuzuweisen einer speziellen Richtlinie für einen Benutzer auf "Global" **(organisationsweit) festlegen möchten, können Sie jede Richtlinie auf "Global" festlegen**.

Sie können auch die folgenden Schritte zum Zuweisen einer Richtlinie zu einem Benutzer tun:

1. Wechseln Sie in der linken Navigationsleiste Microsoft Teams Admin Center zur Richtlinienseite.
2. Wählen Sie die Richtlinie aus, die Sie zuweisen möchten, indem Sie links des Richtliniennamens klicken.
3. Wählen Sie **Nutzer verwalten** aus.
4. Suchen Sie im Bereich **Benutzer verwalten** anhand des Anzeigenamens oder des Benutzernamens nach dem Benutzer, wählen Sie den Namen aus, und klicken Sie auf **Hinzufügen**. Wiederholen Sie diesen Schritt für jeden Benutzer, den Sie hinzufügen wollen.
5. Wenn Sie mit dem Hinzufügen von Benutzern fertig sind, wählen Sie **Übernehmen aus**.

![Weisen Sie einem Benutzer im Teams Admin Center über die zweite Methode eine Richtlinie zu.](media/assign-policy-user2.png)

### <a name="use-powershell"></a>Verwenden von PowerShell

Jeder Richtlinientyp verfügt über einen eigenen Satz von Cmdlets für die Verwaltung. Verwenden Sie das `Grant-` Cmdlet für einen bestimmten Richtlinientyp, um die Richtlinie zuzuordnen. Verwenden Sie beispielsweise das Cmdlet `Grant-CsTeamsMeetingPolicy` , um Benutzern Teams Besprechungsrichtlinie zuzuordnen. Diese Cmdlets sind im PowerShell Teams Modul enthalten und werden in der Referenz [Skype for Business-Cmdlet dokumentiert](/powershell/skype).

 Laden Sie das Teams [PowerShell herunter](https://www.powershellgallery.com/packages/MicrosoftTeams/), installieren Sie es (sofern noch nicht vorhanden), und führen Sie dann die folgenden Schritte aus, um eine Verbindung herzustellen.

> [!NOTE]
> Der Skype for Business Online-Connector ist derzeit Bestandteil des aktuellen PowerShell-Moduls von Teams.
>
> Wenn Sie die neueste Version Teams [PowerShell Public Release](https://www.powershellgallery.com/packages/MicrosoftTeams/) verwenden, müssen Sie den Skype for Business Online Connector nicht installieren.

```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```

In diesem Beispiel weisen wir einem Teams namens "Student Meeting Policy" eine Besprechungsrichtlinie namens Reda zu.

```powershell
Grant-CsTeamsMeetingPolicy -Identity reda@contoso.com -PolicyName "Student Meeting Policy"
```

Weitere Informationen finden Sie unter [Verwalten von Richtlinien über PowerShell](teams-powershell-managing-teams.md#manage-policies-via-powershell).

## <a name="assign-a-policy-to-a-group"></a>Zuweisen einer Richtlinie zu einer Gruppe

Mit der Richtlinienzuweisung zu Gruppen können Sie einer Benutzergruppe, z. B. einer Sicherheitsgruppe oder Verteilerliste, eine Richtlinie zuweisen. Die Richtlinienzuweisung wird anhand von Prioritätsregeln an die Mitglieder der Gruppe weitergegeben. Wenn Mitglieder einer Gruppe hinzugefügt oder daraus entfernt werden, werden ihre geerbten Richtlinienzuweisungen entsprechend aktualisiert.

Die Richtlinienzuweisung zu Gruppen wird für Gruppen mit bis zu 50.000 Benutzern empfohlen, funktioniert aber auch mit größeren Gruppen.

Wenn Sie die Richtlinie zuweisen, wird sie der Gruppe sofort zugewiesen. Die Weitergabe der Richtlinienzuweisung an Mitglieder der Gruppe wird jedoch als Hintergrundvorgang durchgeführt und kann je nach Größe der Gruppe einige Zeit dauern. Dasselbe gilt, wenn eine Richtlinie nicht einer Gruppe zugewiesen wird, oder wenn Mitglieder einer Gruppe hinzugefügt oder aus ihr entfernt werden.

Gruppenrichtlinienzuweisungen werden nur an Benutzer weiterveriert, die direkte Mitglieder der Gruppe sind. Die Zuweisungen werden nicht an Mitglieder geschachtelter Gruppen weiterverteilen.

### <a name="what-you-need-to-know-about-policy-assignment-to-groups"></a>Wichtige Informationen zur Richtlinienzuweisung an Gruppen

Bevor Sie beginnen, ist es wichtig, Rangfolgeregeln und Rangfolge von Gruppenzuweisungen zu verstehen.

#### <a name="precedence-rules"></a>Rangfolgeregeln

Für einen bestimmten Richtlinientyp wird die effektive Richtlinie eines Benutzers wie folgt bestimmt:

- Eine Richtlinie, die einem Benutzer direkt zugewiesen ist, hat Vorrang vor allen anderen Richtlinien desselben Typs, der einer Gruppe zugewiesen ist. Mit anderen Worten: Wenn einem Benutzer direkt eine Richtlinie eines bestimmten Typs zugewiesen wird, erbt dieser Benutzer keine Richtlinie desselben Typs von einer Gruppe. Dies bedeutet auch: Wenn ein Benutzer über eine Richtlinie eines bestimmten Typs verfügt, die ihm direkt zugewiesen wurde, müssen Sie diese Richtlinie vom Benutzer entfernen, bevor er eine Richtlinie desselben Typs von einer Gruppe erben kann.
- Wenn einem Benutzer keine Richtlinie direkt zugewiesen ist und Mitglied von zwei oder mehr Gruppen ist und jeder Gruppe eine Richtlinie desselben Typs zugewiesen ist, erbt der Benutzer die Richtlinie der Gruppenzuordnung, die die höchste Rangfolge besitzt.
- Wenn ein Benutzer kein Mitglied von Gruppen ist, denen eine Richtlinie zugewiesen ist, gilt die globale (organisationsweite Standard)-Richtlinie für diesen Richtlinientyp für den Benutzer.

Die effektive Richtlinie eines Benutzers wird gemäß den folgenden Regeln aktualisiert:

- wenn ein Benutzer einer Gruppe hinzugefügt oder aus dieser entfernt wird, der eine Richtlinie zugewiesen ist.
- eine Richtlinie wird einer Gruppe nicht zugewiesen.
- eine Richtlinie, die dem Benutzer direkt zugewiesen ist, wird entfernt.

#### <a name="group-assignment-ranking"></a>Rangfolge von Gruppenzuweisungen

Wenn Sie einer Gruppe eine Richtlinie zuweisen, geben Sie eine Rangfolge für die Gruppenzuweisung an. Damit wird ermittelt, welche Richtlinie ein Benutzer als effektive Richtlinie erben soll, wenn der Benutzer Mitglied von zwei oder mehr Gruppen ist und jeder Gruppe eine Richtlinie desselben Typs zugewiesen wird.

Die Gruppenzuordnungsrangfolge ist relativ zu anderen Gruppenzuweisungen desselben Typs. Wenn Sie z. B. eine Anrufrichtlinie zwei Gruppen zuweisen, legen Sie die Rangfolge einer Aufgabe auf 1 und die andere auf 2, und 1 ist die höchste Einstufung. Die Rangfolge der Gruppenzuweisungen gibt an, welche Gruppenmitgliedschaft im Hinblick auf die Vererbung wichtiger oder relevanter als andere Gruppenmitgliedschaften ist.

Sie haben beispielsweise zwei Gruppen: Mitarbeiter Store Mitarbeiter Store Vorgesetzte. Beiden Gruppen wird eine Anrufrichtlinie Teams Richtlinie Store Mitarbeiter-Anrufrichtlinie bzw. Store Manager-Anrufrichtlinie zugewiesen. Für einen Store-Manager, der in beiden Gruppen ist, ist ihre Rolle als Manager relevanter als ihre Rolle als Mitarbeiter. Daher sollte die Anrufrichtlinie, die der Store-Manager-Gruppe zugewiesen ist, eine höhere Rangfolge haben.

|Gruppe |Teams von Anrufen der Richtlinie  |Rang|
|---------|---------|---|
|Store Manager   |Store-Anrufrichtlinie für Manager         |1|
|Store Mitarbeiter    |Store-Anrufrichtlinie für Mitarbeiter      |2|

Wenn Sie keine Rangfolge angeben, wird der Richtlinienzuweisung die niedrigste Einstufung gegeben.

### <a name="in-the-teams-admin-center"></a>Im Teams Admin Center

> [!NOTE]
> Derzeit ist die Richtlinienzuweisung an Gruppen, die das Microsoft Teams Admin Center verwenden, nur für Anrufrichtlinien für Teams,Teams-Parkrichtlinien, Teams-Richtlinien, Teams-Liveereignisse, Teams-Besprechungsrichtlinien und Teams-Messaging-Richtlinie verfügbar. Verwenden Sie PowerShell für andere Richtlinientypen.

1. Wechseln Sie in der linken Navigationsleiste Microsoft Teams Admin Center zur Seite "Richtlinientyp". Wechseln Sie z. B. zu **Besprechungsrichtlinien** >  für **Besprechungen**.
2. Wählen Sie die **Registerkarte Gruppenrichtlinienzuordnung** aus.
3. Wählen **Sie Gruppe hinzufügen** aus, und gehen Sie dann im Bereich **Richtlinie zu** Gruppe zuweisen wie folgt vor:
    1. Suchen Sie nach der Gruppe, der Sie die Richtlinie zuweisen möchten, und fügen Sie sie hinzu.
    2. Legen Sie die Rangfolge für die Gruppenzuweisung an.
    3. Wählen Sie die Richtlinie aus, die Sie zuweisen möchten.
    4. Wählen Sie **Übernehmen aus**.
    
![Weisen Sie einer Gruppe im Admin Center Teams Richtlinie zu.](media/assign-policy-group.png)

Um eine Gruppenrichtlinienzuweisung zu entfernen, wählen  Sie auf der Seite "Richtlinie" auf der Registerkarte Gruppenrichtlinienzuweisung die Gruppenzuweisung und dann Entfernen **aus**.

Um die Bewertung einer Gruppenzuordnung zu ändern, müssen Sie zuerst die Gruppenrichtlinienzuweisung entfernen. Führen Sie dann die vorstehenden Schritte aus, um die Richtlinie einer Gruppe zuzuordnen.

### <a name="use-the-powershell-option"></a>Verwenden der PowerShell-Option

> [!NOTE]
> Derzeit ist die Richtlinienzuweisung an Gruppen mithilfe von PowerShell nicht für alle Teams verfügbar. Eine Liste der unterstützten Richtlinientypen finden Sie unter [New-CsGroupPolicyAssignment](/powershell/module/teams/new-csgrouppolicyassignment) .

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a>Installieren und Herstellen einer Verbindung mit dem Microsoft Teams PowerShell-Modul

Eine Schritt-für-Schritt-Anleitung finden Sie unter [Installieren Teams PowerShell](teams-powershell-install.md).

#### <a name="assign-a-policy-to-a-group-of-users"></a>Zuweisen einer Richtlinie zu einer Benutzergruppe

Verwenden Sie [das Cmdlet New-CsGroupPolicyAssignment](/powershell/module/teams/new-csgrouppolicyassignment) , um einer Gruppe eine Richtlinie zuzuweisen. Sie können eine Gruppe mit der Objekt-ID, der SIP-Adresse oder der E-Mail-Adresse angeben.

In diesem Beispiel weisen wir einer Teams mit dem Namen "Einzelhandelsmanager-Besprechungsrichtlinie" eine Gruppe mit der Zuordnungsrangfolge 1 zu.

```powershell
New-CsGroupPolicyAssignment -GroupId d8ebfa45-0f28-4d2d-9bcc-b158a49e2d17 -PolicyType TeamsMeetingPolicy -PolicyName "Retail Managers Meeting Policy" -Rank 1
```

#### <a name="get-policy-assignments-for-a-group"></a>Erhalten von Richtlinienzuweisungen für eine Gruppe

Verwenden Sie [das Cmdlet Get-CsGroupPolicyAssignment](/powershell/module/teams/get-csgrouppolicyassignment) , um alle Richtlinien einer Gruppe zuzuweisen. Beachten Sie, dass Gruppen immer nach ihrer Gruppen-ID aufgelistet werden, auch wenn deren SIP-Adresse oder E-Mail-Adresse zum Zuweisen der Richtlinie verwendet wurde.

In diesem Beispiel rufen wir alle Richtlinien ab, die einer bestimmten Gruppe zugewiesen sind.

```powershell
Get-CsGroupPolicyAssignment -GroupId e050ce51-54bc-45b7-b3e6-c00343d31274
```

In diesem Beispiel geben wir alle Gruppen zurück, denen eine Richtlinie Teams zugewiesen ist.

```powershell
Get-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy
```

#### <a name="remove-a-policy-from-a-group"></a>Entfernen einer Richtlinie aus einer Gruppe

Verwenden Sie [das Cmdlet Remove-CsGroupPolicyAssignment](/powershell/module/teams/remove-csgrouppolicyassignment) , um eine Richtlinie aus einer Gruppe zu entfernen. Wenn Sie eine Richtlinie aus einer Gruppe entfernen, werden die Prioritäten anderer Richtlinien desselben Typs, die dieser Gruppe zugewiesen sind und eine niedrigere Rangfolge haben, aktualisiert. Wenn Sie z. B. eine Richtlinie entfernen, die eine Rangfolge von 2 hat, werden Richtlinien mit einer Rangfolge von 3 und 4 aktualisiert, um ihre neue Rangfolge wider zuspiegeln. In den beiden folgenden Tabellen ist dieses Beispiel dargestellt.

Hier ist eine Liste der Richtlinienzuweisungen und Prioritäten für eine Teams Besprechungsrichtlinie.

|Gruppenname  |Richtlinienname  |Rang|
|---------|---------|---------|
|Vertrieb    |Vertriebsrichtlinie       | 1        |
|West Region     |Richtlinie "Region Westen"         |2         |
|Division    |Abteilungsrichtlinie         |3         |
|Niederlassung   |Richtlinien für Niederlassungen        |4         |

Wenn die Richtlinie "Region Westen" aus der Gruppe Region "Westen" entfernt wird, werden die Richtlinienzuweisungen und -prioritäten wie folgt aktualisiert.

|Gruppenname  |Richtlinienname  |Rang|
|---------|---------|---------|
|Vertrieb    |Vertriebsrichtlinie       | 1        |
|Division    |Abteilungsrichtlinie         |2         |
|Niederlassung   |Richtlinien für Niederlassungen        |3        |

In diesem Beispiel entfernen wir die Teams Besprechungsrichtlinie aus einer Gruppe.

```powershell
Remove-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy -GroupId f985e013-0826-40bb-8c94-e5f367076044
```

#### <a name="change-a-policy-assignment-for-a-group"></a>Ändern einer Richtlinienzuweisung für eine Gruppe

> [!NOTE]
> Das [Cmdlet Set-CsGroupPolicyAssignment](/powershell/module/teams/set-csgrouppolicyassignment) wird in Kürze zur Verfügung stehen. In der Zwischenzeit können Sie zum Ändern einer Gruppenrichtlinienzuweisung die aktuelle Richtlinienzuweisung aus der Gruppe entfernen und dann eine neue Richtlinienzuweisung hinzufügen.

Nachdem Sie einer Gruppe eine Richtlinie zugewiesen haben, können Sie das [Cmdlet Set-CsGroupPolicyAssignment](/powershell/module/teams/set-csgrouppolicyassignment) verwenden, um die Richtlinienzuweisung dieser Gruppe wie folgt zu ändern:

- Ändern der Rangfolge
- Ändern der Richtlinie eines bestimmten Richtlinientyps
- Ändern der Richtlinie eines bestimmten Richtlinientyps und der Rangfolge

In diesem Beispiel ändern wir die Anruf parkrichtlinien einer Gruppe in Teams Richtlinie mit dem Namen SupportCallPark und die Zuweisungsrangfolge in 3.

```powershell
Set-CsGroupPolicyAssignment -GroupId 566b8d39-5c5c-4aaa-bc07-4f36278a1b38 -PolicyType TeamsMeetingPolicy -PolicyName SupportCallPark -Rank 3
```

#### <a name="change-the-effective-policy-for-a-user"></a>Ändern der effektiven Richtlinie für einen Benutzer

Hier ist ein Beispiel für das Ändern der effektiven Richtlinie für einen Benutzer, dem eine Richtlinie direkt zugewiesen wurde.

Zuerst verwenden wir das [Cmdlet Get-CsUserPolicyAssignment](/powershell/module/teams/get-csuserpolicyassignment) zusammen mit dem -Parameter, um Details zu den Teams-Richtlinien für Live meeting broadcast zu erhalten, die dem Benutzer zugeordnet sind.`PolicySource`

```powershell
Get-CsUserPolicyAssignment -Identity daniel@contoso.com -PolicyType TeamsMeetingBroadcastPolicy | select -ExpandProperty PolicySource
```

Die Ausgabe zeigt, dass dem Benutzer direkt eine Teams-Liveübertragungsrichtlinie namens "Mitarbeiterereignisse" zugewiesen wurde, die Vorrang vor der Richtlinie namens "Anbieter-Liveereignisse" hat, die einer Gruppe zugewiesen ist, der der Benutzer angehört.

```console
AssignmentType PolicyName         Reference
-------------- ----------         ---------
Direct         Employee Events
Group          Vendor Live Events 566b8d39-5c5c-4aaa-bc07-4f36278a1b38
```

Jetzt entfernen wir die Richtlinie für Mitarbeiterereignisse vom Benutzer. Dies bedeutet, dass dem Benutzer keine Richtlinie für Teams-Liveübertragung mehr direkt zugewiesen ist, und die Richtlinie "Anbieter-Liveereignisse" erbt, die der Gruppe zugewiesen ist, der der Benutzer angehört.

Verwenden Sie dazu das folgende Cmdlet Skype for Business PowerShell-Modul.

```powershell
Grant-CsTeamsMeetingBroadcastPolicy -Identity daniel@contoso.com -PolicyName $null
```

Verwenden Sie das folgende Cmdlet im Teams PowerShell-Modul, um dies im Maßstab einer Batchrichtlinienzuordnung zu erreichen, wobei $users eine Liste von Benutzern ist, die Sie angeben.

```powershell
New-CsBatchPolicyAssignmentOperation -OperationName "Assigning null at bulk" -PolicyType TeamsMeetingBroadcastPolicy -PolicyName $null -Identity $users  
```

## <a name="assign-a-policy-to-a-batch-of-users"></a>Zuweisen einer Richtlinie zu einer Gruppe von Benutzern

### <a name="use-the-admin-center"></a>Verwenden des Admin Centers

So weisen Sie Benutzern eine Richtlinie in Massen zu:

1. Wählen Sie in der linken Navigationsleiste Microsoft Teams Admin Center Benutzer **aus**.
2. Suchen Sie nach den Benutzern, die die Richtlinie zuweisen möchten, oder filtern Sie die Ansicht so, dass die von Ihnen gesuchten Benutzer angezeigt werden.
3. Wählen Sie in der Spalte **&#x2713;** (Häkchen) die Benutzer aus. Um alle Benutzer auszuwählen, klicken Sie am oberen Rand der Tabelle auf &#x2713; (Häkchen).
4. Wählen **Sie Einstellungen bearbeiten** aus, nehmen Sie die von Ihnen vorgenommenen Änderungen vor, und wählen Sie dann **Übernehmen aus**.

Um den Status Ihrer Richtlinienzuweisung zu sehen, wählen Sie in dem Banner, das oben auf der  Seite Benutzer angezeigt wird,  nachdem Sie Übernehmen ausgewählt haben, um Ihre Richtlinienzuweisung zu übermitteln die Option **Aktivitätsprotokoll aus**. Oder wechseln Sie in der linken Navigationsleiste Microsoft Teams Admin **Center zu Dashboard**, und wählen Sie dann unter Aktivitätsprotokoll die Option **Details anzeigen aus**. Im Aktivitätsprotokoll werden Richtlinienzuweisungen für Batches von mehr als 20 Benutzern im Microsoft Teams Admin Center der letzten 30 Tage angezeigt. Weitere Informationen finden Sie unter [Anzeigen Ihrer Richtlinienzuweisungen im Aktivitätsprotokoll](activity-log.md).

### <a name="use-powershell-method"></a>Verwenden der PowerShell-Methode

> [!NOTE]
> Derzeit ist die Batchrichtlinienzuweisung mithilfe von PowerShell nicht für alle Teams verfügbar. Eine Liste der unterstützten Richtlinientypen finden Sie unter [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) .

Mit der Batchrichtlinienzuweisung können Sie großen Gruppen von Benutzern gleichzeitig eine Richtlinie zuweisen, ohne ein Skript verwenden zu müssen. Sie verwenden das [Cmdlet New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) , um eine Gruppe von Benutzern und die Richtlinie zu übermitteln, die Sie zuweisen möchten. Die Zuweisungen werden als Hintergrundvorgänge verarbeitet, und für jeden Batch wird eine Vorgangs-ID generiert. Anschließend können Sie das [Cmdlet Get-CsBatchPolicyAssignmentOperation](/powershell/module/teams/get-csbatchpolicyassignmentoperation) verwenden, um den Fortschritt und Status der Zuordnungen in einem Stapel nachverfolgt.

Geben Sie Benutzer nach ihrer Objekt-ID oder der SIP-Adresse (Session Initiation Protocol) an. Die SIP-Adresse eines Benutzers hat häufig den gleichen Wert wie der Benutzerprinzipalname (User Principal Name, UPN) oder die gleiche E-Mail-Adresse, aber dies ist nicht erforderlich. Wenn ein Benutzer mit dem UPN oder der E-Mail-Adresse angegeben wird, aber einen anderen Wert als seine SIP-Adresse hat, kann die Richtlinienzuweisung für den Benutzer nicht ausgeführt werden. Wenn ein Batch doppelte Benutzer enthält, werden die Duplikate vor der Verarbeitung aus dem Batch entfernt, und der Status wird nur für die im Batch verbleibenden eindeutigen Benutzer bereitgestellt.

Ein Batch kann bis zu 5.000 Benutzer umfassen. Um optimale Ergebnisse zu erzielen, übermitteln Sie nicht mehr als ein paar Batches gleichzeitig. Lassen Sie die Verarbeitung von Batches abschließen, bevor Sie weitere Batches übermitteln.

#### <a name="install-and-connect-to-the-teams-powershell-module"></a>Installieren und Herstellen einer Verbindung mit dem Teams PowerShell-Modul

Führen Sie die folgenden Schritte aus, um [das Microsoft Teams PowerShell-Modul zu installieren](https://www.powershellgallery.com/packages/MicrosoftTeams). Vergewissern Sie sich, dass Sie Version 1.0.5 oder höher installieren.

```powershell
Install-Module -Name MicrosoftTeams
```

Führen Sie die folgenden Schritte aus, um Teams Verbindung herzustellen und eine Sitzung zu starten.

```powershell
Connect-MicrosoftTeams
```

Wenn Sie dazu aufgefordert werden, melden Sie sich mit Ihren Administratoranmeldeinformationen an.

#### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module-optional"></a>Installieren und Herstellen einer Verbindung mit Azure AD PowerShell für Graph Modul (optional)

Möglicherweise möchten Sie auch das [Azure AD PowerShell für Graph-Modul](/powershell/azure/active-directory/install-adv2) herunterladen und installieren (sofern noch nicht vorhanden) und eine Verbindung mit Azure AD herstellen, damit Sie eine Liste der Benutzer in Ihrer Organisation abrufen können.

Führen Sie die folgenden Schritte aus, um eine Verbindung mit Azure AD.

```powershell
Connect-AzureAD
```

Wenn Sie dazu aufgefordert werden, melden Sie sich mit den gleichen Administratoranmeldeinformationen an, die Sie zum Herstellen einer Verbindung mit Teams.

#### <a name="assign-a-setup-policy-to-a-batch-of-users"></a>Zuweisen einer Setuprichtlinie zu einer Gruppe von Benutzern

In diesem Beispiel verwenden wir das [Cmdlet New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) , um einer Gruppe von Benutzern, die in der Datei "users_ids.text" aufgeführt sind, eine App-Setuprichtlinie namens "HR-App-Setuprichtlinie" zuzuweisen.

```powershell
$user_ids = Get-Content .\users_ids.txt
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsAppSetupPolicy -PolicyName "HR App Setup Policy" -Identity $user_ids -OperationName "Example 1 batch"
```

In diesem Beispiel wird eine Verbindung mit Azure AD hergestellt, um eine Sammlung von Benutzern abzurufen und dann einer Gruppe von Benutzern, die über ihre SIP-Adresse angegeben wurden, eine Messagingrichtlinie mit dem Namen New Hire Messaging Policy zuzuordnen.

```powershell
Connect-AzureAD
$users = Get-AzureADUser
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMessagingPolicy -PolicyName "New Hire Messaging Policy" -Identity $users.SipProxyAddress -OperationName "Example 2 batch"
```

#### <a name="get-the-status-of-a-batch-assignment"></a>Anzeigen des Status einer Batchzuweisung

Führen Sie die folgenden Schritte aus, um den Status einer Batchzuordnung zu erhalten. Dabei steht "OperationId" für die Vorgangs-ID `New-CsBatchPolicyAssignmentOperation` , die vom Cmdlet für einen bestimmten Batch zurückgegeben wird.

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

Wenn die Ausgabe zeigt, dass ein Fehler aufgetreten ist, führen Sie die folgenden Schritte aus, um weitere Informationen zu Fehlern zu erhalten, die sich in der -Eigenschaft `UserState` befinden.

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

Weitere Informationen finden Sie unter [Get-CsBatchPolicyAssignmentOperation](/powershell/module/teams/get-csbatchpolicyassignmentoperation).

## <a name="related-topics"></a>Verwandte Themen

- [Verwalten Teams mit Richtlinien](manage-teams-with-policies.md)
- [Übersicht über PowerShell für Microsoft Teams](teams-powershell-overview.md)
- [Zuweisen von Richtlinien in Teams – Erste Schritte](policy-assignment-overview.md)
