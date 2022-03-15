---
title: Bereitstellen von Microsoft Teams-Räume
ms.author: czawideh
author: cazawideh
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-apr2020
ms.assetid: 678689e4-d547-499b-be64-7d8f16dd8668
description: Lesen Sie diesen Artikel, um zu erfahren, wie Sie Microsoft Teams-Räume bereitstellen, einschließlich der Bereitstellungsphasen.
ms.openlocfilehash: 8240eaff652a0ff465c9eb06242075b0d6baeba8
ms.sourcegitcommit: a894e9397050e09bfaab02e700e943a3bbeb1302
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2022
ms.locfileid: "63503682"
---
# <a name="deployment-overview"></a>Übersicht über die Bereitstellung

Die Bereitstellung Microsoft Teams-Räume im Wesentlichen in Phasen auf:

- Bestätigen, dass Ihre Bereitstellungsstandorte (Leerzeichen) den Bereitstellungsabhängigkeiten entsprechen
- Erstellen Microsoft Teams Kontos Skype for Business Und Exchange Konten und Zuweisen dieser Konten zu Teams-Räume (siehe Konfigurieren von Konten [für Microsoft Teams-Räume](rooms-configure-accounts.md))
- (Optional) Einrichten von Azure Monitor für Ihre Systeme (siehe [Bereitstellen Microsoft Teams-Räume Verwaltung mit Azure Monitor](azure-monitor-deploy.md)
- Einrichten von Teams-Räume in Besprechungsräumen und Anschließen der benötigten Peripheriegeräte (siehe OEM-Dokumentation für Ihre Gerätegruppe)

## <a name="site-readiness"></a>Websitebereitschaft 

Während die bestellten Geräte an Ihre Organisation übermittelt werden, arbeiten Sie mit Ihren Netzwerken, Einrichtungen und AV-Teams zusammen, um sicherzustellen, dass die Bereitstellungsabhängigkeiten erfüllt sind und jede Website und jeder Speicherplatz hinsichtlich Leistung, Netzwerk und Anzeige bereit sind. Stellen Sie außerdem sicher, dass die Anforderungen für die physische Installation erfüllt sind. Wenden Sie sich aus Gründen der physischen Installation an Ihren Anbieter, und nutzen Sie die Erfahrungen Ihres AV-Teams beim Installieren und Installieren von Bildschirmen und Beim Ausführen der Verkabelung.

Weitere Informationen zu diesen Abhängigkeiten finden Sie unter den Links für den Planungsleitfade:

-   [Überprüfen der Netzwerkverfügbarkeit](rooms-prep.md#check-network-availability)
-   [Zertifikate](rooms-prep.md#certificates)
-   [Proxy](rooms-prep.md#proxy)

**Pro Tipp**: Wenn Sie Proxyserver verwenden müssen, um Zugriff auf Teams zu ermöglichen, lesen Sie zuerst [diesen Artikel](../proxy-servers-for-skype-for-business-online.md). Wenn es um Microsoft Teams Echtzeitmedienverkehr über Proxyserver geht, empfehlen wir, Proxyserver vollständig zu umgehen. Microsoft Teams Datenverkehr bereits verschlüsselt ist, sorgen Proxyserver nicht für mehr Sicherheit und fügen Latenz für Echtzeitdatenverkehr hinzu. Im Rahmen ihrer breiteren Bereitstellung empfehlen wir, die Anleitungen unter Vorbereiten Ihres Netzwerks für [Teams](../prepare-network.md) für die Bandbreitenplanung und die Bewertung der Eignung Ihres Netzwerks für Echtzeitdatenverkehr zu befolgen.

|  &nbsp;  | &nbsp;    |
|-----------|------------|
| ![Websites bestätigen.](../media/audio_conferencing_image7.png) <br/>Entscheidungspunkte|<ul><li>Vergewissern Sie sich, dass Ihre Websites die wichtigsten Anforderungen für die Microsoft Teams-Räume.</li><li>Vergewissern Sie sich, dass Sie für jeden Standort ausreichend Bandbreite bereitgestellt haben.</li></ul>| 
| ![Gerätebereitstellung planen.](../media/audio_conferencing_image9.png)<br/>Nächste Schritte|<ul><li>Beginnen Sie mit der Planung der Gerätebereitstellung und -konfiguration.</li></ul>| 

## <a name="service-readiness"></a>Bereitschaft für den Dienst

Um sich auf die Bereitstellung Microsoft Teams-Räume Ihrer Organisation vorzubereiten, gehen Sie wie folgt vor: Zentrale Aufgaben:

-   Definieren Microsoft Teams-Räume Ressourcenkonten.
-   Wenn Sie Teams zu einem Azure Active Directory beitreten, bereiten Sie eine Azure AD-Gruppe mit dynamischer Mitgliedschaft so vor, dass alle Konten der Teams-Räume sind. Dies vereinfacht die zukünftige Verwaltung, z. B. die Anwendung von Richtlinien für bedingten Zugriff. Um dynamische Gruppen ganz einfach zu Azure AD, bestimmen Sie eine Benennungskonvention, die Ihre Teams-Räume-Ressourcenkonten eindeutig identifiziert.
-   Wenn Sie Teams Room in Active Directory verknüpfen, bereiten Sie eine Organisationseinheit und eine Active Directory-Gruppe für die Halte von Microsoft Teams-Räume-Computer- und Ressourcenkonten vor, und bereiten Sie – optional – Gruppenrichtlinienobjekte (Group Policy Objects, GPOs) vor, um die PowerShell-Entfernung zu aktivieren.

### <a name="define-microsoft-teams-rooms-resource-account-features"></a>Definieren Microsoft Teams-Räume Features des Ressourcenkontos 

Je nach den Szenarien für die Zusammenarbeit, die Sie bei Ihrer Microsoft Teams-Räume-Bereitstellung aktiviert haben, müssen Sie die Features und Funktionen ermitteln, die Sie jedem Microsoft Teams-Raum zuweisen, den Sie aktivieren.

| **Szenario** | **Beschreibung** | **Microsoft Teams-Räume "Dienstkonto"** |
|---------- |------------- | --- |
| Interaktive Besprechungen            | Verwenden von Sprache, Video und Bildschirmfreigabe Das -Microsoft Teams-Räume zu einer buchbaren Ressource machen                     | Aktiviert für Microsoft Teams-Skype for Business; aktiviert für Exchange (Ressourcenpostfach) |
| Einwahlkonferenzen            | Verwenden einer Audiokonferenz-Telefonnummer beim Tippen auf "Neue Besprechung" auf der Konsole | Aktiviert für Audiokonferenzen                                          |
| Ausgehende/eingehende PSTN-Anrufe | Aktivieren der Microsoft Teams-Räume für das Anrufen und Empfangen von PSTN-Anrufen                                         | Aktiviert für Telefonsystem                                                |

Weitere Informationen zu Microsoft Teams-Räume finden Sie unter [Konfigurieren von Konten für Microsoft Teams-Räume](rooms-configure-accounts.md).


|  &nbsp;  |  &nbsp;   |
|-----------|------------|
| ![Szenariounterstützung.](../media/audio_conferencing_image7.png) <br/>Entscheidungspunkte|<ul><li>Entscheiden Sie, welche Szenarien Unterstützt werden sollen, und identifizieren Sie die Lizenzierungsanforderungen für Ihre Microsoft Teams-Räume Ressourcenkonten.</li></ul>| 
| ![Bereiten Sie den Hostcomputer vor.](../media/audio_conferencing_image9.png)<br/>Nächste Schritte|<ul><li>Bereiten Sie das Hosten von Computer- und Ressourcenkonten vor.</li></ul>| 


_Beispiel für Microsoft Teams-Räume Ressourcenkontoplanungstabelle_

| **Standort**  | **Name des Raum** | **Raumtyp** | **Zukünftige Raumfunktionen**                                                 | **Microsoft Teams-Räume von Kontofunktionen**                                                                                         |
|-----------|---------------|---------------|------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------|
| London HQ | Curie         | Mittel        | 1 Bildschirm, Audio und Video plus Präsentation <br>Zugriff auf Einwahlkonferenzen<br> PSTN-Zugriff  | Aktiviert für Exchange (Ressourcenpostfach) <br>Aktiviert für Audiokonferenzen <br>Aktiviert für Telefonsystem |
| Sydney HQ | Hill          | Groß         | 2 Bildschirme, Audio und Video plus Präsentation<br>Zugriff auf Einwahlkonferenzen<br> PSTN-Zugriff  | Aktiviert für Skype for Business <br>Aktiviert für Exchange (Ressourcenpostfach)<br> Aktiviert für Audiokonferenzen <br>Aktiviert für Telefonsystem |


### <a name="prepare-to-host-microsoft-teams-rooms-and-resource-accounts-optional"></a>Vorbereiten des Hostens Microsoft Teams-Räume- und Ressourcenkonten (optional)

Um es Ihnen zu ermöglichen, Ihre Ressourcen- und Microsoft Teams-Räume zu verwalten und Berichte zu erstellen, bereiten Sie Ihr lokales Active Directory oder Ihre lokale Azure Active Directory (Azure AD) vor. 

Definieren Sie ein lokales Active Directory oder eine Azure Active Directory Gruppe, der alle Microsoft Teams-Räume hinzugefügt werden. Wenn Sie Azure Active Directory, erwägen Sie die Verwendung einer dynamischen Gruppe, um Ressourcenkonten automatisch hinzuzufügen und aus der Gruppe zu entfernen.

Definieren Sie in der lokalen Active Directory-Hierarchie eine Organisationseinheit für alle Microsoft Teams-Räume-Computerkonten (wenn diese der Domäne beigetreten sind) und eine Organisationseinheit für alle Microsoft Teams-Räume-Benutzerkonten. Deaktivieren Sie die Gruppenrichtlinienvererbung, um sicherzustellen, dass Sie nur die Richtlinien anwenden, die Sie auf die Domänenvererbung anwenden Microsoft Teams-Räume.

Erstellen Sie ein Gruppenrichtlinienobjekt, das der Organisationseinheit zugeordnet ist, die Ihre Microsoft Teams-Räume-Computerkonten enthält. Verwenden Sie diese Für: 

-   [Legen Sie Die Einstellungen für ein lokales Und-Konto ein](rooms-operations.md#configuring-group-policy-for-microsoft-teams-rooms).
-   Aktivieren Windows Aktualisieren.
-   Aktivieren Sie die PowerShell-Entfernung. Sie können ein Startskript für die Ausführung eines Skripts konfigurieren: Enable-PSRemoting -Force

Sie können PowerShell verwenden, um mehrere Remoteverwaltungsaktivitäten durchzuführen, darunter das Abrufen und Festlegen von Konfigurationsinformationen. Die PowerShell-Entfernung  muss aktiviert werden, bevor eine PowerShell-Remoteverwaltung stattfinden kann und als Teil Ihrer Bereitstellungsprozesse betrachtet oder über Gruppenrichtlinien konfiguriert werden sollte. Weitere Informationen zu diesen Funktionen und zu deren Aktivierung finden Sie unter [Wartung und Vorgänge](rooms-operations.md#remote-management-using-powershell). 


## <a name="configuration-and-deployment"></a>Konfiguration und Bereitstellung 

Die Planung der Konfiguration und Bereitstellung umfasst die folgenden Hauptbereiche:

-   Bereitstellung des Ressourcenkontos
-   Installation von Gerätesoftware
-   Gerätebereitstellung
-   Microsoft Teams-Räume der Konfiguration von Anwendungen und Peripheriegeräten
-    Tests
-   Postenverwaltung

### <a name="resource-account-provisioning"></a>Bereitstellung des Ressourcenkontos 

Jedes Microsoft Teams-Räume benötigt ein dediziertes und eindeutiges Ressourcenkonto, das sowohl für Microsoft Teams als Skype for Business als auch für Exchange. Dieses Konto muss über ein Raumpostfach verfügen, das auf einem Exchange. Die Kalenderverarbeitung muss so konfiguriert werden, dass das Gerät eingehende Besprechungsanfragen automatisch annehmen kann. Weitere Informationen zum Erstellen dieser Konten finden Sie unter [Konfigurieren von Konten für Microsoft Teams-Räume](rooms-configure-accounts.md). 

**Pro Tipp**: Jeder Microsoft Teams-Räume muss einen gültigen und eindeutigen Computernamen in Ihrem Netzwerk haben. Viele Überwachungs- und Warnsysteme zeigen den Computernamen als Schlüsselbezeichner an. Daher ist es wichtig, eine Benennungskonvention für Microsoft Teams-Räume-Bereitstellungen zu entwickeln, die es den Supportmitarbeitern ermöglicht, die als Handlungsaufbehalt gekennzeichnete Microsoft Teams-Räume auf einfache Weise zu finden. Ein Beispiel könnte die Verwendung eines Musters von *MTR-SiteRoom*- *Name* (MTR-LON-CURIE) sein. 

|  &nbsp;  | &nbsp;    |
|-----------|------------|
| ![die Benennungskonvention festlegen.](../media/audio_conferencing_image7.png) <br/>Entscheidungspunkte|<ul><li>Legen Sie die Benennungskonvention für Ihre Microsoft Teams-Räume-Ressourcenkonten dar.</li><li>Entscheiden Sie, ob Sie einzelne Konten erstellen oder Massenbereitstellungsskripts verwenden möchten.</li></ul>| 
| ![die nächsten Schritte ausführen.](../media/audio_conferencing_image9.png)<br/>Nächste Schritte|<ul><li>Beginnen Sie mit der Planung der Gerätebereitstellung.</li></ul>| 


### <a name="device-software-installation"></a>Installation von Gerätesoftware 

Teams-Räume wird vom Originalgerätehersteller (OEM) vorinstalliert.

Wir bieten Anleitungen zur Verwendung des [Microsoft Azure-Monitors](/skypeforbusiness/plan-your-deployment/clients-and-devices/azure-monitor) zum Überwachen der Microsoft Teams-Räume-Bereitstellung und zum Melden der Verfügbarkeit, von Hardware-/Softwarefehlern und Microsoft Teams-Räume Anwendungsversion. Wenn Sie sich für die Verwendung der Microsoft Operations Management Suite entscheiden, sollten Sie den Agent der Operations Management Suite im Rahmen des Softwareinstallationsprozesses installieren und die Arbeitsbereichsverbindungsinformationen für Ihren Arbeitsbereich konfigurieren. 

Eine zusätzliche Überlegung ist, ob Microsoft Teams-Räume dem Domänen beigetreten ist. Informationen zu den Vorteilen der Domänenregistrierung finden Sie unter [Konfigurieren von Gruppenrichtlinien für Microsoft Teams-Räume](rooms-operations.md#configuring-group-policy-for-microsoft-teams-rooms). 

| &nbsp;   |  &nbsp;   |
|-----------|------------|
| ![Entscheidungspunkte für die Gerätebenennung.](../media/audio_conferencing_image7.png) <br/>Entscheidungspunkte|<ul><li>Entscheiden Sie Microsoft Teams-Räume, welche Benennungskonvention für Ressourcenkonto während der Bereitstellung verwendet werden soll.</li><li>Entscheiden Sie, ob Sie Ihrer Microsoft Teams-Räume beitreten möchten. </li><li>Entscheiden Sie, ob Sie Azure Monitor zum Überwachen der Bereitstellung Microsoft Teams-Räume möchten.</li> 
| ![planen Sie das Gerät für die nächsten Schritte.](../media/audio_conferencing_image9.png)<br/>Nächste Schritte|<ul><li>Beginnen Sie mit der Planung Ihres Gerätebereitstellungsansatzes.</li></ul>| 


### <a name="device-deployment"></a>Gerätebereitstellung

Nachdem Sie entschieden haben, wie Sie Ihre Microsoft Teams-Räume-Ressourcenkonten erstellen und verwalten, erstellen Sie Ihren Plan, um die Geräte und die zugewiesenen Peripheriegeräte an Ihre Räume zu versenden, und fahren Sie dann mit der Installation und Konfiguration fort.


|  &nbsp;  |   &nbsp;  |
|-----------|------------|
| ![die Bereitstellung von Website zu Website verwalten.](../media/audio_conferencing_image7.png) <br/>Entscheidungspunkte|<ul><li>Entscheiden Sie, wer die Bereitstellung von Website zu Website verwalten soll.</li><li> Ermitteln Sie die Ressourcen, die Microsoft Teams-Räume auf der Website installieren sollen, und übernehmen Sie die Konfiguration und Tests.</li></ul>| 
| ![Gerätetests starten.](../media/audio_conferencing_image9.png)<br/>Nächste Schritte|<ul><li>Starten Sie die Gerätetests.</li></ul>| 

_Beispiel für eine Bereitstellungstabelle_

| **Standort**  | **Name des Raum** | **Raumtyp** | **Microsoft Teams-Räume System**  | **Peripheriegeräte**  | **Microsoft Teams-Räume Computername**  | **Microsoft Teams-Räume Ressourcenkonto**  |
|-----------|---------------|---------------|-----------------------------------|------------------|------------------------------------------|---------------------------------------------|
| London HQ | Curie         | Mittel        |                                   |                  |                                          |                                             |
| Sydney HQ | Hill          | Groß         |                                   |                  |                                          |                                             |

### <a name="microsoft-teams-rooms-application-and-peripheral-device-configuration"></a>Microsoft Teams-Räume der Konfiguration von Anwendungen und Peripheriegeräten 

Nachdem jedes Microsoft Teams-Räume-System physisch bereitgestellt wurde und die unterstützten Peripheriegeräte angeschlossen wurden, müssen Sie die Microsoft Teams-Räume-Anwendung so konfigurieren, dass sie das Microsoft Teams-Räume-Ressourcenkonto und das Kennwort zuzuordnen, um Teams-Räume, um sich bei ihrem Microsoft Teams oder Skype for Business anmelden, und Exchange.

Sie können die einzelnen Microsoft Teams-Räume konfigurieren. Alternativ können Sie eine zentral gespeicherte, Teams-Räume XML-Konfigurationsdatei verwenden, um die Anwendungseinstellungen zu verwalten.

Weitere Informationen zur Verwendung der XML-Konfigurationsdatei finden Sie unter Remoteverwaltung Microsoft Teams-Räume einstellungen einer Microsoft Teams-Räume [mit einer XML-Konfigurationsdatei](xml-config-file.md). 

Sie können [Remote-PowerShell verwenden](rooms-operations.md#remote-management-using-powershell), um die Microsoft Teams-Räume für Berichterstellungsanforderungen zu erstellen. 

| &nbsp;   |  &nbsp;   |
|-----------|------------|
| ![Entscheidungspunkt konfigurieren.](../media/audio_conferencing_image7.png) <br/>Entscheidungspunkte|<ul><li>Entscheiden Sie, ob Sie jedes System manuell Microsoft Teams-Räume oder eine zentrale XML-Datei verwenden möchten (eine pro Microsoft Teams-Räume Gerät).</li></ul>| 
| ![Remoteansatz für die nächsten Schritte.](../media/audio_conferencing_image9.png)<br/>Nächste Schritte|<ul><li>Definieren Sie den Ansatz für die Remoteverwaltung.</li></ul>| 

### <a name="testing"></a> Tests

Nachdem Teams-Räume bereitgestellt wurde, sollten Sie es testen. Überprüfen Sie, ob die in der Microsoft Teams-Räume [aufgeführten](https://support.microsoft.com/en-us/office/microsoft-teams-rooms-help-e667f40e-5aab-40c1-bd68-611fe0002ba2?ui=en-us&rs=en-us&ad=us) Funktionen auf dem bereitgestellten Gerät funktionieren. Es wird dringend empfohlen, dass das Bereitstellungsteam überprüft, Microsoft Teams-Räume im Admin Center Teams wird. Außerdem ist es wichtig, dass Sie eine Reihe von Testanrufen und -besprechungen absprechen, um die Qualität zu überprüfen. Weitere Informationen finden Sie in dieser [hilfreichen Prüfliste für die Bereitstellung](console.md#microsoft-teams-rooms-deployment-checklist).

Es wird empfohlen, im Rahmen des allgemeinen Teams- oder Skype for Business-Rollouts Gebäudedateien für das Anrufqualitätsdashboard zu konfigurieren, Qualitätstrends zu überwachen und sich an der Überprüfung der Qualität der Benutzererfahrung zu beteiligen. Weitere Informationen finden Sie unter [Verbessern und Überwachen der Anrufqualität für Teams](../monitor-call-quality-qos.md). 

### <a name="asset-management"></a>Postenverwaltung

Im Rahmen der Bereitstellung sollten Sie Ihr Ressourcenregister mit dem Raumnamen, Microsoft Teams-Räume Namen, dem Microsoft Teams-Räume Ressourcenkonto und den zugewiesenen Peripheriegeräten aktualisieren. 

_Beispiel für eine Objekttabelle_

| **Standort**  | **Name des Raum** | **Raumtyp** | **Microsoft Teams-Räume Seriennummer.**  | **Peripheriegeräte/Seriennummern/Ports**  | **Microsoft Teams-Räume Computername**  | **Microsoft Teams-Räume-Dienstkonto**  | **Bereitgestelltes Datum** |
|-----------|---------------|---------------|------------------------------------------|------------------------------------------|------------------------------------------|--------------------------------------------|-------------------|
| London HQ | Curie         | Mittel        |                                          |                                          |                                          |                                            |                   |
| Sydney HQ | Hill          | Groß         |                                          |                                          |                                          |                                            |                   |
