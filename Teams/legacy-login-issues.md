---
title: Probleme beim Empfangen von Nachrichten und Anrufen auf älteren Systemen in Teams
ms.reviewer: ''
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 05/29/2020
ms.topic: troubleshooting
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
search.appverid: MET150
f1.keywords:
- NOCSH
description: Behandeln von Problemen im Zusammenhang mit dem Empfangen von Nachrichten und Anrufen auf Älteren Systemen
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 56499af9534c3559cdfa3311a360caa60d06d3d7
ms.sourcegitcommit: 0dda332951df3b946097d90a4923eb191fd86b4c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/14/2022
ms.locfileid: "66789520"
---
# <a name="issues-receiving-messages-and-calls-on-legacy-systems"></a>Probleme beim Empfangen von Nachrichten und Anrufen auf Älteren Systemen

Benutzer können Probleme beim Empfangen von Nachrichten oder Anrufen haben, wenn sie ältere Versionen von Teams verwenden oder sich mit anderen Anwendungen angemeldet haben.

## <a name="legacy-adu-setups"></a>Legacy-ADU-Setups

 Wenn Benutzer bei einem in eine Domäne eingebundenen Computer angemeldet sind und **Sie nicht möchten, dass ihre Benutzernamen im Anmeldebildschirm von Microsoft Teams vorab ausgefüllt werden**, können Administratoren die folgende Windows-Registrierung so einrichten, dass das Vorab-Ausfüllen des Benutzernamens (UPN) deaktiviert ist:

  Computer\HKEY_CURRENT_USER\Software\Microsoft\Office\Teams<br/>
  SkipUpnPrefill(REG_DWORD)<br/>
  0x00000001 (1)

> [!NOTE]
> Das Überspringen oder Ignorieren des Vorab-Ausfüllens von Benutzernamen ist für Benutzernamen, die in „.local“ oder „.corp“ enden, standardmäßig aktiviert, daher müssen Sie keinen Registrierungsschlüssel festlegen, um diese zu deaktivieren.

Weitere Informationen finden [Sie unter Anmelden bei Microsoft Teams mit moderner Authentifizierung](sign-in-teams.md) .

## <a name="skype-token-revocation"></a>Skype-Tokensperrung

Beim Ändern/Zurücksetzen eines Kennworts erhalten ältere Clients bis zu einer Stunde lang keine Nachrichten und Anrufe. Um dieses Problem zu beheben, starten Sie die App neu, oder wechseln Sie zu neueren Clients.


## <a name="related-topics"></a>Verwandte Themen

[Teams-Problembehandlung](/MicrosoftTeams/troubleshoot/teams)