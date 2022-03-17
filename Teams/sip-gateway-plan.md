---
title: Planen des SIP-Gateways
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/30/2021
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365initiative-voice
ms.reviewer: crowe
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: Erfahren Sie mehr über SIP Gateway, z. B. Anforderungen und Vorteile.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 817f3dc7ce7f0b6f407607417c0cadb92b65e943
ms.sourcegitcommit: dafe48cea1643e1bd79390482da9b002d7e9e0bb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/16/2022
ms.locfileid: "63514750"
---
# <a name="plan-for-sip-gateway"></a>Planen für das SIP-Gateway

Mit dem SIP-Gateway kann Ihre Organisation jedes kompatible SIP-Gerät Microsoft Teams, um Ihre Investitionen in SIP-Geräte zu erhalten. Jetzt können Sie sich mit Ihren Teams anmeldeinformationen anmelden und Anrufe mit einem kompatiblen SIP-Gerät senden und empfangen. Kompatible Geräte können auf SKYPE FOR BUSINESS mit Standard-SIP-Firmware, Cisco IP-Telefonen mit Multiplatform-SIP-Firmware oder SIP-Geräten von Anbietern wie Poly, Yealink und AudioCodes verwendet werden. Informationen zum Konfigurieren Ihrer SIP-Geräte für das SIP-Gateway finden Sie unter [Konfigurieren des SIP-Gateways](sip-gateway-configure.md).

## <a name="benefits-of-sip-gateway"></a>Vorteile des SIP-Gateways

Das SIP-Gateway verbindet kompatible SIP-Geräte mit Teams, damit Ihre Benutzer nahtlos zur Telefonie Teams migrieren können. Wenn Sie das SIP-Gateway verwenden, können die Benutzer folgende Aufgaben wie folgt tun:

- **Anrufe:** Benutzer von SIP-Geräten können Anrufe an das Public Switched Telephone Network (PSTN), an andere SIP-Geräte sowie an Teams und Skype for Business senden. Sip-Gerätebenutzer können nur Benutzer anrufen, die Telefonnummern haben.
- **Anrufe empfangen:** Benutzer von SIP-Geräten können einen Anruf über das PSTN, von Teams- oder Skype for Business-Benutzern mit SIP-Geräten sowie von Teams- und Skype for Business-Clientanwendungen erhalten. Das SIP-Gerät fungiert als Teams Endpunkt. Eingehende Anrufe werden auch auf das SIP-Gerät des Benutzers gerundet.
- **Mehrere gleichzeitige Anrufe:** Ein Sip-Gerätebenutzer kann den Anruf halten, um andere Anrufe zu führen oder zu empfangen. Ein Benutzer eines SIP-Geräts kann auch zwei Anrufe telefonieren.
- **Nicht stören:** Ein SIP-Gerätebenutzer kann "Nicht stören" auf dem Gerät festlegen, damit das Gerät nicht für eingehende Anrufe klingelt. Dies hat keine Auswirkungen auf den Status des Benutzers auf allen anderen Teams Endpunkten.
- **Halten/Fortsetzen und Stummschalten/Stummschaltung wieder aufschalten:** Benutzer eines SIP-Geräts können einen Anruf halten und fortsetzen oder stummschalten und die Stummschaltung wieder aufnehmen, indem er die Features für diese Aktionen auf dem Gerät verwendet.
- **Voicemail:** Benutzer von SIP-Geräten können elektronisch gespeicherte Sprachnachrichten anhören, die Anrufer für sie verlassen.
- **Indikator für Meldungswartezeichen:** Sip-Gerätebenutzer können Benachrichtigungen erhalten, die sie bei neuen Voicemailnachrichten warnen.
- **An- und Abmelden:** SIP-Geräte: Benutzer können sich auf dem Teams an- und abmelden.
- **Doppelton-Multihäufigkeit:** Benutzer von SIP-Geräten können Nummerntasten drücken, um während interaktiver Sprachantworten Eingaben zu ermöglichen.
- **Teams Besprechungen: Ein** SIP-Gerätebenutzer kann an einer Besprechung Teams, indem er die Nummer des Besprechungszugriffs wählt. Besprechungsteilnehmer können der Besprechung einen SIP-Gerätebenutzer hinzufügen, indem sie die Telefonnummer des Benutzers anrufen oder einfach einen Teilnehmer hinzufügen, indem sie auf "Teilnahme anfordern" klicken, um auch das SIP-Gerät des Benutzers zu warnen. Gastbenutzer aus einer anderen Organisation können einer Teams-Besprechung von einem Teilnehmer hinzugefügt werden, der die Nummer eines Gastbenutzers auswählt, um diesen Gast mit in die Besprechung mit einzukommen.
- **Anrufübertragungen:** Benutzer von SIP-Geräten können Anrufe durch übertragen. Das SIP-Gateway unterstützt blinde und weisungsbehinderte Übertragungen.
- **Lokale Anruf weiterleitung:** Benutzer eines SIP-Geräts können Weiterleitungsregeln (immer, timeout und beschäftigt) für das Gerät festlegen. Wenn das Gerät mit dem SIP-Gateway verbunden ist, wird der Anruf basierend auf der vom Gerätebenutzer festgelegten Regel an die Zieladresse umgeleitet. Damit die lokale Anruf weiterleitung funktioniert, muss der Administrator das - `AllowCallRedirect` Attribut in auf `Set-CsTeamsCallingPolicy` festlegen `Enabled`. 


## <a name="requirements-to-use-sip-gateway"></a>Anforderungen für die Verwendung des SIP-Gateways

Teams Benutzer müssen über eine Telefonnummer verfügen, für die PSTN-Anrufe aktiviert sind, damit sie das SIP-Gateway verwenden können.

### <a name="hardware-software-and-licenses"></a>Hardware, Software und Lizenzen

Wenn Sie über ein 3PIP- oder SIP-Gerät verfügen, müssen Sie über: 
- Eine Lizenz für Telefonsystem (über E5 oder eine eigenständige Lizenz)
- PSTN-Aktivierung (d. h. eine Telefonnummer) über Microsoft Teams Anrufplan, Direktes Routing oder Netzbetreiber Verbinden
- A Common Area Telefon license for any common area devices

## <a name="compatible-devices"></a>Kompatible Geräte

|Anbieter    |Modell      |Mindestversion der Firmware|Genehmigte Firmwareversion|Hinweise|Links|
|----------|-----------|------------|-----------|------------|------------|
|**Cisco** |           |            |           |Geräte mit Unternehmensfirmware müssen in Multiplatform-Firmware konvertiert werden. Lesen Sie die Anleitung rechts, um zu erfahren, wie das geht.|[Cisco Firmwarekonvertierungsleitfaden](https://www.cisco.com/c/en/us/products/collateral/collaboration-endpoints/unified-ip-phone-7800-series/guide-c07-742786.html)|
|          |8832       |11.3.5MPP   |11.3.5MPP  |   |   |
|          |6821       |11.1.1MPP   |11-3-3MPP  |   |   |
|          |7811       |11.1.1MPP   |11-3-3MPP  |   |   |
|          |7821       |11.1.1MPP   |11-3-3MPP  |   |   |
|          |7841       |11.1.1MPP   |11-3-3MPP  |   |   |
|          |7861       |11.1.1MPP   |11-3-3MPP  |   |   |
|          |8811       |11.1.1MPP   |11-3-3MPP  |   |   |
|          |8841       |11.1.1MPP   |11-3-3MPP  |   |   |
|          |8845       |11.1.1MPP   |11-3-3MPP  |   |   |
|          |8851       |11.1.1MPP   |11-3-3MPP  |   |   |
|          |8861       |11.1.1MPP   |11-3-3MPP  |   |   |
|          |8865       |11.1.1MPP   |11-3-3MPP  |   |   |
|**Poly**  |           |            |           |Das Gerät wird automatisch neu gestartet und die ausgewählte Firmware installiert.|   |
|          |Julien 8500  |5.9.5.3182  |7.1.1.0997 |   |   |
|          |Julien 8800  |5.9.5.3182  |7.1.1.0997 |   |   |
|          |VVX150     |5.9.5       |6.3.1.8427 |   |   |
|          |VVX201     |5.9.5       |6.3.1.8427 |   |   |
|          |VVX250     |5.9.5       |6.3.1.8427 |   |   |
|          |VVX300     |5.9.5       |5.9.6.2327 |   |   |
|          |VVX301     |5.9.5       |6.3.1.8427 |   |   |
|          |VVX310     |5.9.5       |5.9.6.2327 |   |   |
|          |VVX311     |5.9.5       |6.3.1.8427 |   |   |
|          |VVX350     |5.9.5       |6.3.1.8427 |   |   |
|          |VVX400     |5.9.5       |5.9.6.2327 |   |   |
|          |VVX401     |5.9.5       |6.3.1.8427 |   |   |
|          |VVX410     |5.9.5       |5.9.6.2327 |   |   |
|          |VVX411     |5.9.5       |6.3.1.8427 |   |   |
|          |VVX450     |5.9.5       |6.3.1.8427 |   |   |
|          |VVX500     |5.9.5       |5.9.6.2327 |   |   |
|          |VVX501     |5.9.5       |6.3.1.8427 |   |   |
|          |VVX600     |5.9.5       |5.9.6.2327 |   |   |
|          |VVX601     |5.9.5       |6.3.1.8427 |   |   |
|**Yealink**|          |            |           |   |[Yealink-Unterstützung](https://support.yealink.com/)|
|          |T40P       |83          |54.84.0.125|   |   |
|          |T41S       |83          |66.85.0.5  |   |   |
|          |T41S       |83          |66.85.0.5  |   |   |
|          |T41S       |83          |66.85.0.5  |   |   |
|          |T42G       |83          |29.83.0.130|   |   |
|          |T42S       |83          |66.85.0.5  |   |   |
|          |T42U       |83          |108.86.0.20|   |   |
|          |T43U       |83          |108.86.0.20|   |   |
|          |T46S       |83          |66.85.0.5  |   |   |
|          |T46U       |83          |108.86.0.20|   |   |
|          |T48S       |83          |66.85.0.5  |   |   |
|          |T48G       |83          |35.83.0.130|   |   |
|          |T48U       |83          |108.86.0.20|   |   |
|          |T53        |83          |96.85.0.5  |   |   |
|          |T53W       |83          |96.85.0.5  |   |   |
|          |T54W       |83          |96.85.0.5  |   |   |
|          |T57W       |83          |96.85.0.5  |   |   |
|          |T21P       |83          |52.84.0.140|   |   |
|          |T23G       |83          |44.84.0.140|   |   |
|          |T27G       |83          |69.85.0.5  |   |   |
|          |T29G       |83          |46.83.0.130|   |   |
|          |T30        |83          |124.85.0.40|   |   |
|          |T30P       |83          |124.85.0.40|   |   |
|          |T31G       |83          |124.85.0.40|   |   |
|          |T33G       |83          |124.85.0.40|   |   |
|          |T40G       |83          |76.84.0.125|   |   |
|          |T41P       |83          |36.83.0.120|   |   |
|          |T46G       |83          |28.83.0.130|   |   |
|**AudioCodes**|       |            |           |Einige AudioCodes-SIP-Geräte benötigen eine Einstellung für die Bereitstellungs-URL. Laden Sie auf der rechten Seite Upgradedateien für die betroffenen AudioCodes-Geräte herunter, und installieren Sie sie. |[Herunterladbare Dateien für betroffene Geräte bei AudioCodes](https://audiocodes.sharefile.com/share/view/sc9cdf17f9ec45d09/fo7914a2-4f3a-4000-8957-47bd6f35a3a5)|
|          |405         |2.2.8      |2.2.16.570 |   |   |
|          |405HD       |3.2.1      |2.2.16.570 |   |   |
|          |420HD       |3.2.1      |2.2.16.570 |   |   |
|          |430HD       |3.2.1      |2.2.16.570 |   |   |
|          |440HD       |3.2.1      |2.2.16.570 |   |   |
|          |450HD       |3.2.1      |3.4.6.687  |   |   |
|          |C450HD      |3.2.1      |3.4.6.687  |   |   |
|          |445HD       |3.2.1      |3.4.6.687  |   |   |
|          |TX50        |3.2.1      |3.4.6.687  |   |   |

> [!NOTE]
> Bei einigen Geräten ist die Firmware-Mindestversion höher als die genehmigte Firmwareversion. Der Grund: Die 3.X-Version ist die Skype for Business Version. Wir aktualisieren die SIP-Version 2.X.
