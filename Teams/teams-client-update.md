---
title: Teams-Updates
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
- m365initiative-deployteams
ms.reviewer: annaray
search.appverid: MET150
f1.keywords:
- NOCSH
description: In diesem Artikel erfahren Sie mehr über den Prozess hinter der Aktualisierung des Microsoft Teams-Desktopclients.
ms.localizationpriority: high
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a7d296e296b2f5a20b5d7d10da6e598a989f0d71
ms.sourcegitcommit: cd4464fe9bf0f38ed4c3ca058a51bcd29578eef9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2022
ms.locfileid: "65316501"
---
# <a name="teams-update-process"></a>Teams-Updateprozess

Updates für Teams-Web-Apps werden in der Regel am 4. Montag eines jeden Monats veröffentlicht.

Teams-Desktop-Client-Updates werden monatlich nach strengen internen Tests und Validierungen durch unser Technology Adoption Program (TAP) veröffentlicht. Desktop-Client-Updates beginnen in der Regel am 4. Montag des Monats und werden für den Rest der Woche schrittweise für Kunden bereitgestellt. Bei wichtigen Updates wird dieser Zeitplan von Microsoft Teams umgangen, und die Updates werden freigegeben, sobald sie verfügbar sind.

Der Desktop-Client aktualisiert sich automatisch. Teams sucht im Hintergrund alle paar Stunden nach Updates, lädt sie herunter und wartet dann, bis sich der Computer im Leerlauf befindet, bevor das Update im Hintergrund installiert wird.

Benutzer können Updates auch manuell herunterladen, indem sie **Nach Updates suchen** im **...**-Dropdownmenü neben Ihrem **Profil**-Symbol oben rechts in der App auswählen. Wenn ein Update verfügbar ist, wird es heruntergeladen und im Hintergrund installiert, wenn sich der Computer im Leerlauf befindet.

Benutzer müssen angemeldet sein, damit Updates heruntergeladen werden können.

## <a name="what-about-updates-to-microsoft-365-apps-for-enterprise"></a>Was ist mit Updates für Microsoft 365 Apps for Enterprise?

Teams wird standardmäßig mit neuen Installationen von Microsoft 365 Apps for Enterprise installiert, wie in [Bereitstellen von Microsoft Teams mit Microsoft 365 Apps for Enterprise](/DeployOffice/teams-install) beschrieben.

Teams folgt einem eigenen Updateprozess, wie oben beschrieben. Dieser Updateprozess für Microsoft Teams unterscheidet sich von dem Updateprozess für die anderen Office-Apps wie Word und Excel. Weitere Informationen finden Sie unter [Übersicht über die Updatekanäle für Microsoft 365 Apps](/DeployOffice/overview-update-channels).

## <a name="can-admins-deploy-updates-instead-of-teams-auto-updating"></a>Können Administratoren Updates bereitstellen, anstelle der automatischen Aktualisierung von Teams?

Teams bietet Administratoren nicht die Möglichkeit, Updates über einen Übermittlungsmechanismus bereitzustellen.

## <a name="servicing-agreement"></a>Wartungsvertrag

Als moderner Onlinedienst wird der Teams-Client alle zwei Wochen automatisch aktualisiert. Da Teams der Modern Lifecycle-Richtlinie unterliegt, wird davon ausgegangen, dass Benutzer auf der aktuellsten Version des Desktopclients bleiben. Automatische Updates stellen sicher, dass Benutzer über die neuesten Funktionen, Leistungsverbesserungen, über Sicherheit und Dienstzuverlässigkeit verfügen.

Um zu ermitteln, wann Desktopclients veraltet sind, wird eine In-App-Warnung angezeigt, wenn die aktuelle Version des Benutzers zwischen einem und drei Monaten alt ist, und falls eine neue Version verfügbar ist. Dieses In-App-Messaging empfiehlt Benutzern, auf die neueste Version von Teams zu aktualisieren oder sich, falls nötig, an ihren IT-Administrator zu wenden. Benutzern auf Teams-Desktopclients, die älter als drei Monate sind, wird eine Sperrseite angezeigt, auf der Sie sämtliche Optionen zum Aktualisieren, zum Kontaktieren Ihres IT-Administrators oder zum Fortfahren mit Teams im Web finden.

Teams-Desktopclients in Government-Clouds haben derzeit bis auf weiteres eine Ausnahme von diesem Wartungsvertrag.

Informationen zu neuen Versionsreleases finden Sie im [Nachrichtencenter](https://admin.microsoft.com/AdminPortal/Home#/MessageCenter) oder im Client unter **Hilfe** > **Neuerungen**.

## <a name="what-about-updates-to-teams-on-vdi"></a>Wie sieht es mit Updates für Teams auf VDI aus?

Teams-Clients in Virtual Desktop Infrastructure (VDI) werden nicht automatisch auf die gleiche Weise aktualisiert wie Nicht-VDI-Teams-Clients. Sie müssen das VM-Image aktualisieren, indem Sie eine neue MSI installieren, wie im Abschnitt [Installieren oder Aktualisieren der Teams-Desktop-App auf VDI](teams-for-vdi.md) beschrieben. Sie müssen zum Aktualisieren der Teams-App die aktuelle Version deinstallieren, um auf eine neuere Version aktualisieren zu können.
