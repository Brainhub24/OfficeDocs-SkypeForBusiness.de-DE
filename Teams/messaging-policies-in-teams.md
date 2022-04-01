---
title: Verwalten von Nachrichtenrichtlinien in Teams
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.messagingpolicies.overview
- seo-marvel-apr2020
description: Erfahren Sie mehr über die Nachrichtenrichtlinie, und wie Sie sie zur Steuerung des Chat-Messagings in Teams genutzt werden können.
ms.openlocfilehash: 00146d35faac13ef511a06b6c442341832867bcc
ms.sourcegitcommit: 2388838163812eeabcbd5331aaf680b79da3ccba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/31/2022
ms.locfileid: "64592790"
---
# <a name="manage-messaging-policies-in-teams"></a>Verwalten von Nachrichtenrichtlinien in Teams

<!--- Add zone marker here--->

Nachrichtenrichtlinien werden genutzt, um zu steuern, welche Chat- und Nachrichtenkanalfunktionen den [Benutzern (Besitzern und Mitgliedern)](assign-roles-permissions.md) in Microsoft Teams zur Verfügung stehen. Sie können die globale (standardmäßig organisationsweit geltende) Richtlinie verwenden, oder benutzerdefinierte Richtlinien erstellen und diese gezielt zuweisen.

Die Benutzer in Ihrer Organisation erhalten automatisch die globale Richtlinie, es sei denn, Sie erstellen und weisen eine benutzerdefinierte Richtlinie zu. Bearbeiten Sie die Einstellungen in der globalen Richtlinie, oder erstellen und weisen Sie mindestens eine benutzerdefinierte Richtlinie zu, um die von Ihnen verwendeten Features zu aktivieren oder zu deaktivieren.

> [!NOTE]
> Um eine Synchronisierung nach einer Richtlinienänderung sicherzustellen, ist für bestimmte Instanzen möglicherweise ein Neustart erforderlich. 

## <a name="create-a-custom-messaging-policy"></a>Erstellen einer benutzerdefinierten Nachrichtenrichtlinie

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu **Nachrichtenrichtlinien**.
2. Klicken Sie auf **Hinzufügen**.
3. Geben Sie einen Namen und eine Beschreibung für die Richtlinie ein.
4. Wählen Sie die gewünschten Einstellungen aus.
5. Klicken Sie auf **Speichern**.

So möchten Sie beispielsweise sicherstellen, dass gesendete Nachrichten nicht gelöscht oder geändert werden. Erstellen Sie dann eine neue benutzerdefinierte Richtlinie namens „Gesendete Nachrichten aufbewahren“ und deaktivieren Sie die folgenden Einstellungen:

- Besitzer können gesendete Nachrichten löschen
- Benutzer können gesendete Nachrichten löschen
- Benutzer können gesendete Nachrichten bearbeiten

Weisen Sie dann die Richtlinie den Benutzern zu.

## <a name="edit-a-messaging-policy"></a>Bearbeiten einer Nachrichtenrichtlinie

Sie können die globale Standardrichtlinie oder eine von Ihnen erstellte benutzerdefinierte Richtlinie jederzeit bearbeiten.

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu **Nachrichtenrichtlinien**.
2. Wählen Sie die Richtlinie aus, indem Sie links neben die Richtlinienbezeichnung klicken, und wählen Sie dann **Bearbeiten** aus.
3. Nehmen Sie nun die gewünschten Änderungen vor.
4. Klicken Sie auf **Speichern**.

## <a name="assign-a-custom-messaging-policy-to-users"></a>Weisen Sie eine benutzerdefinierte Nachrichtenrichtlinie einem Benutzer zu

[!INCLUDE [assign-policy](includes/assign-policy.md)]

Einem Benutzer kann jeweils nur eine Nachrichtenrichtlinie zugewiesen werden.

> [!NOTE]
> Sie können eine Richtlinie nicht löschen, solange Sie Benutzern zugewiesen ist. Sie müssen allen betroffenen Benutzern erst eine andere Richtlinie zuweisen, bevor Sie die ursprüngliche Richtlinie löschen können.

<!--- End zone marker here--->

## <a name="messaging-policy-settings"></a>Nachrichtenrichtlinie – Einstellungen

Dies sind die Nachrichteneinstellungen, die Sie konfigurieren können.

- **Besitzer können gesendete Nachrichten löschen**  Verwenden Sie diese Einstellung, damit Besitzer Kanalnachrichten oder Beiträge löschen können, die Benutzer gesendet haben.
- **Gesendete Nachrichten löschen** Verwenden Sie diese Einstellung, um Benutzern das Löschen von nachrichten zu ermöglichen, die sie im Chat gesendet haben.
- **Löschen eines Chats** Verwenden Sie diese Einstellung, um Benutzern das Löschen von nachrichten zu ermöglichen, die sie im Chat gesendet haben.
- **Gesendete Nachrichten bearbeiten** Verwenden Sie diese Einstellung, um Benutzern das Bearbeiten von Nachrichten zu ermöglichen, die sie in einem Chat gesendet haben.
- **Lesebestätigungen** Lesebestätigungen ermöglichen es dem Absender einer Chatnachricht, benachrichtigt zu werden, wenn der Empfänger seine Nachricht in 1:1 und Gruppenchats 20 oder weniger Personen gelesen hat. Lesebestätigungen für Nachrichten nehmen die Ungewissheit, ob eine Nachricht gelesen wurde und verbessern so die Kommunikation im Team. In eDiscovery-Berichten werden keine Lesebestätigungen erfasst.  
    - **Benutzergesteuert**: Das bedeutet, dass Benutzer entscheiden können, ob Sie die Funktion „Lesebestätigungen“ aktivieren oder deaktivieren möchten. Die Standardeinstellung in der App ist „aktiviert“. Benutzer können Sie dann auf „deaktiviert“ ändern.
    - **Für jeden aktiviert** Dies bedeutet, dass alle Mandanten die Funktion EIN haben, ohne dass sie deaktiviert werden kann. Wenn Sie die  Einstellung Für jeden aktivieren verwenden, besteht die einzige Möglichkeit zum Festlegen von Bestätigungen für den gesamten Mandanten entweder in der Verwendung einer einzigen Messagingrichtlinie für den gesamten Mandanten (die Standardrichtlinie namens "Global (Organisationsweite Standard)") oder wenn alle Messagingrichtlinien im Mandanten dieselben Einstellungen für Bestätigungen verwenden. Das Feature "Lesebestätigungen" ist am effektivsten, wenn die Option **Für alle aktiviert** ist.
    - **Für jeden deaktiviert** Dies bedeutet, dass das Feature deaktiviert ist und niemand im Mandanten Lesebestätigungen hat und sie auch nicht aktivieren kann.
<a name="bkchat"> </a>

- **Chat**: Aktivieren Sie diese Einstellung, wenn Sie möchten, dass die Benutzer in Ihrer Organisation mithilfe der Teams-App mit anderen Personen chatten können.
- *Verwenden Von Giphy in Unterhaltungen** Wenn Sie Giphys aktivieren, können Benutzer Giphys in Chatunterhaltungen mit anderen Personen enthalten. Giphy ist eine Onlinedatenbank und Suchmaschine, die es Benutzern ermöglicht, nach animierten GIF-Dateien zu suchen und diese zu teilen. Jedem Giphy wird eine Inhaltsbewertung zugewiesen. Zusätzlich zum Aktivieren dieser Einstellung müssen Sie optionale verbundene Erfahrungen aktivieren, [](/deployoffice/privacy/manage-privacy-controls#policy-setting-for-optional-connected-experiences) um Giphys in Unterhaltungen zu ermöglichen.
- **Giphy-Inhaltsklassifikation**
  - **Keine Einschränkung**: Das bedeutet, dass Ihre Benutzer beliebige Giphys in Chats einfügen können – unabhängig von ihrer Inhaltsbewertung.
  - **Moderat**: Das bedeutet, dass Benutzer Giphys in Chats einfügen können, der Zugriff auf nicht jugendfreie Inhalte aber moderat eingeschränkt wird.
  - **Streng**: Das bedeutet, dass Benutzer Giphys in Chats einfügen können, der Zugriff auf nicht jugendfreie Inhalte aber streng eingeschränkt wird.
- **Memes in Unterhaltungen** Wenn Sie Memes aktivieren, können Benutzer Memes in Chatunterhaltungen mit anderen Personen enthalten.
- **Aufkleber in Unterhaltungen** Wenn Sie dies aktivieren, können Benutzer Aufkleber in Chatunterhaltungen mit anderen Personen hinzufügen.
- **URL-Vorschauen** Verwenden Sie diese Einstellung, um die automatische URL-Vorschau in Nachrichten zu aktivieren oder zu deaktivieren.
- **Übersetzen von Nachrichten** Aktivieren Sie diese Einstellung, damit Benutzer Ihre Teams automatisch in die Sprache übersetzen können, die in den persönlichen Spracheinstellungen für E-Mails Microsoft 365 Oder Office 365.
- **Immersive Reader für Nachrichten** Aktivieren Sie diese Einstellung, damit Benutzer Nachrichten in Microsoft-Nachrichten anzeigen Plastischer Reader. Plastischer Reader ist ein Lerntool, das zur Verbesserung der Lesbarkeit von Text eine Vollbildansicht bietet.
- **Senden von Prioritätsbenachrichtigungen**: Wenn Sie diese Funktion aktivieren, können Benutzer Nachrichten über [Prioritätsbenachrichtigungen senden](https://support.microsoft.com/article/mark-a-message-as-important-or-urgent-in-teams-ea99d5b6-1317-4550-8d75-86ff14cd4462). Prioritätsbenachrichtigungen benachrichtigen Benutzer alle 2 Minuten für 20 Minuten oder bis Nachrichten, die als dringend  gekennzeichnet sind, vom Empfänger aufgenommen und gelesen werden. Dieses Feature erhöht die Wahrscheinlichkeit, dass die Nachricht rechtzeitig reagiert wird. Sie können eine dringende Nachricht nach dem Senden nicht mehr bearbeiten.
- **Erstellen von Sprachnachrichten**
  > [!Important]
  > Sprachnachrichten werden in eDiscovery-Berichten nicht erfasst.
  - **In Chats und Kanälen zugelassen**: Das bedeutet, dass Benutzer sowohl in Chats als auch in Kanälen Sprachnachrichten hinterlassen können.
  - **Nur in Chats zugelassen**: Das bedeutet, dass Benutzer in Chats, nicht aber in Kanälen Sprachnachrichten hinterlassen können.
  - **Nicht aktiviert** Dies bedeutet, dass Benutzer keine Audionachrichten in Chats oder Kanälen erstellen können.  
- **Auf Mobilgeräten bevorzugte Kanäle über aktuellen Chats anzeigen**: Aktivieren Sie diese Einstellung, um die bevorzugten Kanäle an den oberen Rand des Bildschirms für mobile Geräte zu verschieben, damit ein Benutzer nicht scrollen muss, um Sie zu finden.
- **Entfernen von Benutzern aus Gruppenchats** Aktivieren Sie diese Einstellung, damit ein Benutzer andere Benutzer aus einem Gruppenchat entfernen kann. Mithilfe dieses Features können Sie mit einer kleineren Gruppe von Personen chatten, ohne den Chatverlauf zu verlieren.
- **Textvorhersagen** Aktivieren Sie diese Einstellung, damit Benutzer Textvorhersagen für Chatnachrichten erhalten.
- **Vorgeschlagene Antworten**  Aktivieren Sie diese Einstellung, um vorgeschlagene Antworten für Chatnachrichten zu aktivieren.
- **Chat-Berechtigungsrolle** Verwenden Sie diese Einstellung, um die Rolle des überwachten Chats des Benutzers zu definieren. Erfahren Sie mehr über den [beaufsichtigten Chat](supervise-chats-edu.md).
- **Benutzer mit vollständigen Chatberechtigungen können jede Nachricht löschen.** Verwenden Sie diese Einstellung, um Benutzern mit voll berechtigten Berechtigungen das Löschen von Gruppen- oder Besprechungschatnachrichten zu ermöglichen.

> [!NOTE]
> Einige dieser Einstellungen, z. B. die Verwendung von Giphys, können auch auf Teamebene von Teambesitzern und auf privater oder freigegebener Kanalebene von Kanalbesitzern konfiguriert werden.

### <a name="related-topics"></a>Verwandte Themen

- [Zuweisen von Richtlinien zu Benutzern und Gruppen in Teams](assign-policies-users-and-groups.md)
- [Zuweisen von Teambesitzern und -mitgliedern in Microsoft Teams](assign-roles-permissions.md)
