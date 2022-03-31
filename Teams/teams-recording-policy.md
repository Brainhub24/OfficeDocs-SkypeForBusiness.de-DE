---
title: Einführung in Teams Richtlinienbasierte Aufzeichnung für Anrufe & Besprechungen
author: cabailey
ms.author: cabailey
manager: laurawi
ms.date: 05/11/2020
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: abybee
ms.localizationpriority: medium
search.appverid: MET150
description: Erfahren Sie mehr Teams Richtlinienbasierte Aufzeichnung für Anrufe & Besprechungen
f1.keywords:
- CSH
ms.custom:
- Adopt
- seo-marvel-mar2020
ms.collection:
- Teams_ITAdmin_Adopt
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 554c2e893272ca8dfca1fde6c746e72f1b462f1e
ms.sourcegitcommit: cbdc80c302e97d18a923ef57bb5d4b6cf7676d00
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/30/2022
ms.locfileid: "64556556"
---
# <a name="introduction-to-teams-policy-based-recording-for-callings--meetings"></a>Einführung in Teams Richtlinienbasierte Aufzeichnung für Anrufe & Besprechungen

Mithilfe der richtlinienbasierten Aufzeichnung können Organisationen, die Microsoft Teams für Anrufe und Besprechungen annehmen, mithilfe einer Verwaltungsrichtlinie eine Entscheidung treffen, wenn Anrufe und Onlinebesprechungen automatisch aufgezeichnet und zur nachfolgenden Verarbeitung und Aufbewahrung erfasst werden sollen, wie dies gemäß den relevanten Unternehmens- oder Gesetzlichen Richtlinien erforderlich ist.

Teams wurde um die Unterstützung der Integration von Aufzeichnungslösungen von Drittanbietern erweitert, einschließlich der Plattformfunktionen, benutzeroberflächen und administrativen Schnittstellen, die erforderlich sind, um eine End-to-End-Lösung für die Konfiguration, Verwaltung, Aufzeichnung, Speicherung und Analyse ihrer Kommunikation Teams bereitzustellen. Zu den Verbesserungen gehören APIs für die Kommunikationsplattform und Ereignisse für die Aufzeichnung, die Folgendes bieten:

- Nahtlose, hochwertige Medienaufnahme auf allen Geräten und allen unterstützten Endpunkten für Audio, Video, Bildschirmfreigabe und Chat.

- Unterstützung für die Erfassung der Interaktion zwischen Teams und unterstützten Anrufendpunkten (Teams, Teams Mobile, Skype for Business, PSTN)

- Neue Verwaltungsrichtlinien für die Complianceaufzeichnung, einschließlich der Integration in Teams administrative Anrufe, Besprechungstools und Richtlinien

Die Complianceaufzeichnung kann auf Microsoft 365 A3,A5/E3/E5/Business Premium und Office 365 A3/A5/E3/E5 aktiviert werden. 

Die Integrationsfunktionen für die Integration von Complianceaufzeichnungslösungen wurden auf der Ignite 2019 in der [Sitzung "Complianceaufzeichnung und -Microsoft Teams" überprüft](https://myignite.microsoft.com/archives/IG19-VCE40).

## <a name="teams-interaction-recording-overview"></a>Teams der Aufzeichnung von Interaktionen

Die Verwendungsfälle für die Interaktionsaufzeichnung können effektiv in vier Hauptkategorien der Aufzeichnungsfunktion eingeteilt werden: Benutzerfreundlichkeit, Funktional, Organisationseinheit und rechtmäßiger Abfangen, wie in der Abbildung dargestellt:

> [!div class="mx-imgBorder"]
> ![Screenshot der Interaktionsaufzeichnung, was und warum aufgezeichnet wird.](media/recording-taxonomy.png "Die Abbildung zeigt die Aufzeichnungskategorien.")

Für jede der Kategorien gelten unterschiedliche Anforderungen für die Art und Weise, wie Aufzeichnungen initiiert werden, was aufgezeichnet wird, wo Aufzeichnungen gespeichert werden, wer benachrichtigt wird, wer den Zugriff steuert und wie die Aufbewahrung gehandhabt wird.

| Typ                   | Komfort (regelmäßige Teams Aufzeichnung) | Organisation – geregelt (Complianceaufzeichnung) |
| ---------------------- | ------------------ | --------------- |
| Denk              | Benutzer               | Administrator (System)  |
| Target                 | Pro Anruf/Besprechung | Benutzerspezifische Richtlinie        |
| Storage Besitzer          | Benutzer               | Compliance      |
| Benachrichtigung erforderlich? | Ja                | Ja             |
| Zugriffsbesitzer           | Benutzer               | Compliance      |
| Aufbewahrungsrichtlinie?      | Optional           | Ja             |

Teams bietet verschiedene Funktionen für die [bequeme](./cloud-recording.md) und funktionale Aufzeichnung von Besprechungen und Liveereignissen. Organisationsaufzeichnung bedeutet, dass Organisationen, die Teams für Anrufe und Besprechungen übernehmen, im Rahmen einer Verwaltungsrichtlinie festlegen können, wann Anrufe und Onlinebesprechungen automatisch aufgezeichnet und für die nachfolgende Verarbeitung und Aufbewahrung erfasst werden sollen, wie dies von den relevanten Unternehmens- oder Gesetzlichen Richtlinien gefordert wird. Benutzern dieser Richtlinie ist bewusst, dass ihre digitalen Interaktionen mit Teams aufgezeichnet werden, aber sie können die Aufzeichnung nicht deaktivieren und haben keinen Zugriff auf die Aufzeichnung, nachdem die Interaktion abgeschlossen ist. Die Aufzeichnung wird Teil des Organisationsarchivs, das compliance- und juristischen Mitarbeitern für eDiscovery, gesetzliche Aufbewahrung und andere Zwecke der Unternehmensaufbewahrung zur Verfügung steht.

## <a name="example-user-needs"></a>Beispiel für Benutzeranforderungen

<table>
<thead>
<tr class="header">
<th>Persona</th>
<th>Anforderungen</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Aufgezeichnete Benutzer</td>
<td><ul>
<li><p>Werden Sie benachrichtigt, wenn die Aufzeichnung läuft.</p></li>
<li><p>Informieren Sie sich, wenn ein Fehler in der Richtlinie und/oder im Recorder-Fehler Änderungen des Anrufverhaltens verursacht.</p></li>
</ul></td>
</tr>
<tr class="even">
<td>Kommunikationsadministrator</td>
<td><ul>
<li><p>Verstehen Sie, warum und wie Sie Aufzeichnungsrichtlinien auf Teams/Endpunkte anwenden/ erzwingen.</p></li>
<li><p>Konfigurieren und verwalten Teams Aufzeichnungsrichtlinien für die Organisation.</p></li>
<li><p>Überwachen und Behandeln von Problemen mit der Aufzeichnung bei Teams von Anrufen und Besprechungen.</p></li>
<li><p>Unterstützen Sie interne Compliance Officer mit betriebsinternen Analysen zur Nutzung, Qualität und Zuverlässigkeit.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td>Compliance Officer</td>
<td><ul>
<li><p>Sammeln Sie Teams Kommunikationen in der Art und Weise, die erforderlich ist, um Compliance-Verpflichtungen in geeigneten regionalen Grenzen zu erfüllen.</p></li>
<li><p>Suchen Sie basierend auf kommunikationsbezogenen Metadaten oder Interaktionsinhalten nach Interaktionen. Zu den gängigen Beispielen gehören:</p>
<ul>
<li><p><strong>Metadaten</strong> - Teilnehmer, Uhrzeit, Richtung, gewählte Nummer, Origin-Nummer, Benutzerdefinierte Geschäftsdaten</p></li>
<li><p><strong>Content</strong> – Transkription, Stimmung, Lautschrift, zugehörige Interaktionen</p></li>
</ul></li>
<li><p>Analysieren und Interagieren mit gesammelten Kommunikationen, einschließlich der Möglichkeit, Interaktionen während deren Datenübertragung zu überwachen.</p></li>
<li><p>Stellen Sie die Sicherheit gesammelter Kommunikationen sicher, und verhindern Sie Manipulationen auf allen Stufen.</p></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="solution-architecture-overview"></a>Übersicht über die Lösungsarchitektur

Lösungen für die Complianceaufzeichnung sind in Teams integriert, wie in der folgenden Abbildung dargestellt:

> [!div class="mx-imgBorder"]
> ![Screenshot der Einstellung für die benutzerdefinierte Team-App.](media/hp-compliance-recording-for-teams-calling-and-meetings.jpg "Die Bilder zeigen den Ablauf, wenn Teams oder Anruf gesendet und empfangen wird.")

> [!NOTE]
> Diese Lösung ist speziell darauf ausgelegt, die richtlinienbasierte Konformitätsaufzeichnung mit Teams. Alle anderen Verwendungen dieser Lösung werden nicht unterstützt.

## <a name="recorder"></a>Rekorder

Die Kernkomponente der Lösung für Complianceaufzeichnungen ist die Aufzeichnung.
Aufzeichnungen werden als skalierbare Azure-basierte Dienste (Bots) entwickelt, die die [Kommunikationsplattform von Microsoft](/graph/cloud-communications-concept-overview) verwenden und sich als Anwendungen bei Microsoft Graph. Die Aufzeichnung ermöglicht die direkte Interaktion mit den [APIs](/graph/api/resources/communications-api-overview) der Teams-APIs der Kommunikationsplattform für Anrufe und Besprechungen und stellt den Endpunkt für die Medienaufnahme zur Verfügung.

Es [steht eine Beispielanwendung für Complianceaufzeichnungen](https://github.com/microsoftgraph/microsoft-graph-comms-samples/tree/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot) zur Verfügung, in der gezeigt wird, wie der Bot konfiguriert, die App-Instanz erstellt und die Compliancerichtlinien zugewiesen werden. Das Beispiel enthält außerdem Beispiele für die API-Verwendung zum Aufzeichnen bestimmter Interaktionen, [](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Http/Controllers/PlatformCallController.cs#L199-L244) z. B. Behandeln des Routings eingehender [Anrufe, Ändern](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L135-L138) des Aufzeichnungszuständes und Entfernen des benutzers, der [aufgezeichnet wird](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L121-L126).
Graph Dokumentation zu den jeweiligen APIs finden Sie hier für [updateRecordingStatus](/graph/api/call-updaterecordingstatus?tabs=http) und [incomingContext](/graph/api/resources/incomingcontext).

Die genaue Implementierung des Rekorderdiensts variiert je nach Partner, muss aber so konzipiert sein, dass mehrere Rekorder unterstützt werden, um eine hohe Verfügbarkeit und geografische Verteilung der Bereitstellung zu erzielen, um die Latenz von Teams zum Rekorder zu verringern. Darüber hinaus wird erwartet, dass die Aufzeichnungen selbst resilienz- und redundanz entwickelt werden.

Partner müssen die mindestens erforderliche Version der Microsoft Graph-Kommunikations-APIs und SDKs mit Microsoft bestätigen, bevor sie ihre Lösung zur Zertifizierung einreichen, um sicherzustellen, dass alle Anforderungen der Integration von Complianceaufzeichnungen unterstützt werden.

Zwei spezielle Anforderungen, die für das Aufzeichnen von Compliances von grundlegender Bedeutung sind:

- Recorder bot must be deployed in Azure

- Recorder bot must run on a Windows VM in Azure

Die Anforderungen für Azure und Windows VM gelten nur für die Komponente "Teams Bot", was bedeutet, dass ein Partner die restliche Plattform seiner Wahl implementieren kann, sofern er die relevanten Leistungs- und Funktionsanforderungen für die Konformitätsaufzeichnung erfüllen kann.

## <a name="compliance-recording-policy-assignment-and-provisioning"></a>Richtlinienzuweisung und -bereitstellung für die Complianceaufzeichnung

IT-Administratoren können festlegen, welche Benutzer aufgezeichnet und welche Aufzeichnungsgeräte für jeden Benutzer verwendet werden sollen, indem sie Richtlinien für die Konformitätsaufzeichnung erstellen und zuweisen. Aufzeichnungen werden basierend auf der Konfiguration dieser Richtlinien automatisch zur Teilnahme an Unterhaltungen eingeladen, wenn eine Kommunikationsinteraktion stattfindet. Richtlinien für die Complianceaufzeichnung werden mithilfe [von Microsoft PowerShell](./teams-powershell-overview.md) verwaltet und können auf Mandanten-, Benutzer- und Sicherheitsgruppenebene für jede Organisation angewendet werden. Weitere Informationen zu Besprechungsrichtlinien [Microsoft-Dokumentation Anrufrichtlinien](./meeting-policies-overview.md) und [Gruppenrichtlinien finden Sie hier](./assign-policies-users-and-groups.md#assign-a-policy-to-a-group). [](./teams-calling-policy.md)

1. Erstellen Sie eine Anwendungsinstanz in Ihrem Mandanten.

   ```powershell
   PS C:\> New-CsOnlineApplicationInstance -UserPrincipalName cr.instance@contoso.onmicrosoft.com -DisplayName ComplianceRecordingBotInstance -ApplicationId fcc88ff5-a42d-49cf-b3d8-f2e1f609d511

   RunspaceId        : 4c13efa6-77bc-42db-b5bf-bdd62cdfc5df
   ObjectId          : 5069aae5-c451-4983-9e57-9455ced220b7
   TenantId          : 5b943d7c-5e14-474b-8237-5022eb8e0dc9
   UserPrincipalName : cr.instance@contoso.onmicrosoft.com
   ApplicationId     : fcc88ff5-a42d-49cf-b3d8-f2e1f609d511
   DisplayName       : ComplianceRecordingBotInstance
   PhoneNumber       :
   ```

   ```powershell
   PS C:\> Sync-CsOnlineApplicationInstance -ObjectId 5069aae5-c451-4983-9e57-9455ced220b7
   ```

2. Erstellen Sie eine Richtlinie für die Complianceaufzeichnung.

   ```powershell
   PS C:\> New-CsTeamsComplianceRecordingPolicy -Identity TestComplianceRecordingPolicy -Enabled $true -Description "Test policy created by tenant admin"

   Identity                        : Global
   ComplianceRecordingApplications : {}
   Enabled                         : True
   WarnUserOnRemoval               : True
   Description                     : Test policy created by tenant admin
   ```

   ```powershell
   PS C:\> Set-CsTeamsComplianceRecordingPolicy -Identity TestComplianceRecordingPolicy `
   -ComplianceRecordingApplications @(New-CsTeamsComplianceRecordingApplication -Id 5069aae5-c451-4983-9e57-9455ced220b7 -Parent TestComplianceRecordingPolicy)
   ```

   Weitere [Informationen finden Sie unter Set-CsTeamsComplianceRecordingPolicy](/powershell/module/skype/set-csteamscompliancerecordingpolicy).

3. Weisen Sie einem Benutzer die Richtlinie für die Complianceaufzeichnung zu.

   ```powershell
   PS C:\> Grant-CsTeamsComplianceRecordingPolicy -Identity testuser@contoso.onmicrosoft.com -PolicyName TestComplianceRecordingPolicy
   ```

   Weitere [Informationen finden Sie unter Grant-CsTeamsComplianceRecordingPolicy](/powershell/module/skype/grant-csteamscompliancerecordingpolicy).

   ```powershell
   PS C:\> Get-CsOnlineUser testuser@contoso.onmicrosoft.com | select SipAddress, TenantId, TeamsComplianceRecordingPolicy | fl

   UserPrincipalName              : testuser@contoso.onmicrosoft.com
   TenantId                       : 5b943d7c-5e14-474b-8237-5022eb8e0dc9
   TeamsComplianceRecordingPolicy : TestComplianceRecordingPolicy
   ```

## <a name="user-experiences"></a>Benutzeroberflächen

Die Unterstützung für Benachrichtigungen wird mithilfe der Teams aktiviert. Die Be erleben eine visuelle oder eine Audiowiedergabe.

**Teams-Clients – visuelle Hinweise**
- Desktop/Web
- Mobil (iOS/Android)
- Teams-Smartphones
- Teams von Räumen

**Andere Endpunkte – Audiohinweise**
- SIP-Telefone
- Skype for Business
- Audiokonferenz
- PSTN-Anrufer

> [!NOTE]
> Die Complianceaufzeichnung wird für Anrufwarteschleifen im Konferenzmodus nicht unterstützt. Verwenden Sie Anrufwarteschleifen im Übertragungsmodus.
> Die Complianceaufzeichnung funktioniert nicht, wenn benutzer einen Internetausfall haben und PSTN-Anrufe über ein SBA-Konto starten und empfangen.

## <a name="compliance-recording-for-teams-certification-programs"></a>Complianceaufzeichnung für Teams Zertifizierungsprogramme

Neben der Veröffentlichung öffentlich verfügbarer APIs, mit denen Partner CCaaS-Lösungen in Teams entwickeln und integrieren können, haben wir die Complianceaufzeichnung für das Microsoft Teams-Zertifizierungsprogramm entwickelt, um Kunden die Sicherheit zu geben, dass die Lösung jedes teilnehmenden Partners getestet und überprüft wurde, um die von Microsoft-Lösungen zu erwartende Qualität, Kompatibilität und Zuverlässigkeit zu gewährleisten.  

Die folgenden Partner haben ihre Lösung für die Microsoft Teams.<br/><br/>

|Partner|Website der Lösung |
|:--|:--|
|ASC Technologies |[https://www.asctechnologies.com/english/ASC_Recording_Insights_Compliance_Recording_for_Microsoft_Teams.html](https://www.asctechnologies.com/english/ASC_Recording_Insights_Compliance_Recording_for_Microsoft_Teams.html) |
|AudioCodes |[https://online.audiocodes.com/smarttap-360-live-for-microsoft-teams](https://online.audiocodes.com/smarttap-360-live-for-microsoft-teams) |
|CallCabinet |[https://www.callcabinet.com/compliance-microsoft-teams-call-recording](https://www.callcabinet.com/compliance-microsoft-teams-call-recording ) |
|Dubber |[https://www.dubber.net/call-recording/](https://www.dubber.net/call-recording/) |
|Aufschlussreiche Technologie |[https://insightfultechnology.com/teams/](https://insightfultechnology.com/teams/) |
|NICE Engage |[https://www.nice.com/products/workforce-engagement/call-recording/air-and-engage](https://www.nice.com/products/workforce-engagement/call-recording/air-and-engage) |
|NICE NTR |[https://www.niceactimize.com/compliance/ms-teams-recording.html](https://www.niceactimize.com/compliance/ms-teams-recording.html) |
|Numonix |[https://numonix.cloud](https://numonix.cloud)    |
|Oak Innovation |[https://www.oakinnovate.com/clarify](https://www.oakinnovate.com/clarify) |
|Rotes Kästchen |[https://www.redboxvoice.com/compliance-recording-for-microsoft-teams](https://www.redboxvoice.com/compliance-recording-for-microsoft-teams)  |
|Theta Lake |[https://thetalake.com/integrations/microsoft/](https://thetalake.com/integrations/microsoft/) |
|Verint |[https://www.verba.com/solutions/microsoft-teams-recording](https://www.verba.com/solutions/microsoft-teams-recording) |
|Oak Innovation |[https://www.oakinnovate.com/clarify](https://www.oakinnovate.com/clarify) |

<br/>
Die folgenden Partner zertifizieren ihre Lösung für Microsoft Teams.<br/><br/>

|Partner|Website der Lösung |
|:--|:--|
|Landis Technologies |[https://landistechnologies.com/](https://landistechnologies.com/) |
|Luware |[https://luware.com/en/solution/microsoft-teams-recording/](https://luware.com/en/solution/microsoft-teams-recording/) |


Diese Liste wird aktualisiert, sobald weitere Partner beitreten und die Zertifizierungskriterien erfüllen.

## <a name="next-steps"></a>Nächste Schritte

Wenn Sie als Anbieter am Zertifizierungsprogramm teilnehmen möchten, senden Sie eine E-Mail an [Teamscategorypartner@microsoft.com](mailto:Teamscategorypartner@microsoft.com).
