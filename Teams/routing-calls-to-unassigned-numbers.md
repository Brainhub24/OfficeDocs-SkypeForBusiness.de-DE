---
title: Weiterleiten von Anrufen an nicht zugewiesene Nummern
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: jenstr
ms.topic: article
ms.assetid: aa2ec464-3481-4bbb-8c14-e13e18093df5
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
description: Erfahren Sie, wie Sie Anrufe an nicht zugewiesene Nummern in Ihrer Organisation routen.
ms.openlocfilehash: f53e83b3d4f26123feed70bdecad32cb45bc5588
ms.sourcegitcommit: c7b95254dec4420ba0a697fd49d11b448364c919
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/11/2022
ms.locfileid: "63442793"
---
# <a name="routing-calls-to-unassigned-numbers"></a>Weiterleiten von Anrufen an nicht zugewiesene Nummern

Als Administrator können Sie Anrufe an nicht zugewiesene Nummern in Ihrer Organisation weiter routen. Beispielsweise können Sie Anrufe wie folgt an nicht zugewiesene Nummern weiter routen: 

- Alle Anrufe an eine bestimmte nicht zugewiesene Nummer an eine benutzerdefinierte Ankündigung weiter routen.

- Routen aller Anrufe an eine bestimmte nicht zugewiesene Nummer an die Hauptschaltfläche.

Sie können Anrufe an nicht zugewiesene Nummern an einen Benutzer, an ein Ressourcenkonto, das einem automatische Telefonzentrale- oder Anrufwarteschleifen zugeordnet ist, oder an einen Ankündigungsdienst, der dem Anrufer eine benutzerdefinierte Audiodatei wiedergibt, weiter routen.

## <a name="configuration"></a>Konfiguration

Um Anrufe an eine nicht zugewiesene Nummer weiterzuweisen, verwenden Sie das Cmdlet New/Get/Set/Remove-CsTeamsUnassignedNumberTreatment, das Teams im PowerShell-Modul 2.5.1 oder höher verfügbar ist.

Sie müssen die aufgerufene Nummer oder den Nummernbereich sowie das zugehörige Routing für Anrufe an diese Nummern angeben. Mit dem folgenden Befehl wird beispielsweise angegeben, dass alle Aufrufe der Nummer +1 (555) 222-3333 an das Ressourcenkonto und aa@contoso.com:

``` PowerShell
$RAObjectId = (Get-CsOnlineApplicationInstance -Identity aa@contoso.com).ObjectId


New-CsTeamsUnassignedNumberTreatment -Identity MainAA -Pattern "^\+15552223333$" -TargetType ResourceAccount -Target $RAObjectId -TreatmentPriority 1
```

Das nächste Beispiel gibt an, dass alle Anrufe im Nummernbereich +1 (555) 333-0000 bis +1 (555) 333-9999 an den Ankündigungsdienst umgeroutet werden, der die Audiodatei "MainAnnouncement.wav" an den Anrufer zurückgibt.

```PowerShell
$Content = Get-Content "C:\Media\MainAnnoucement.wav" -Encoding byte -ReadCount 0

$AudioFile = Import-CsOnlineAudioFile -FileName "MainAnnouncement.wav" -Content $Content

$fid = [System.Guid]::Parse($AudioFile.Id)

New-CsTeamsUnassignedNumberTreatment -Identity TR1 -Pattern "^\+1555333\d{4}$" -TargetType Announcement -Target $fid.Guid -TreatmentPriority 2
```

## <a name="notes"></a>Hinweise

- Wenn das Routing zu einer Ankündigung geht, wird die Audiodatei einmal für den Anrufer abgespielt.

- Um Anrufe an nicht zugewiesene Microsoft Calling Plan-Abonnentennummern weiter zu senden, muss Ihr Mandant über Guthaben für [Kommunikationen verfügen](what-are-communications-credits.md).

- Um Anrufe an nicht zugewiesene Microsoft-Anrufplan-Servicenummern weiter zu senden, muss Ihr Mandant mindestens eine Lizenz Telefonsystem – virtueller Benutzer haben.

- Die unterstützten Benutzerdefinierten Audiodateiformate sind WAV (unkomprimiert, linearer PCM mit 8/16/32-Bit-Tiefe in Mono oder Stereo), WMA (nur Mono) und MP3. Der Inhalt der Audiodatei darf nicht größer als 5 MB sein.

## <a name="related-topics"></a>Verwandte Themen

- [Get-CsTeamsUnassignedNumberTreatment](/powershell/module/teams/get-csteamsunassignednumbertreatment)

- [New-CsTeamsUnassignedNumberTreatment](/powershell/module/teams/new-csteamsunassignednumbertreatment)

- [Set-CsTeamsUnassignedNumberTreatment](/powershell/module/teams/set-csteamsunassignednumbertreatment)

- [Remove-CsTeamsUnassignedNumberTreatment](/powershell/module/teams/remove-csteamsunassignednumbertreatment)

- [Test-CsTeamsUnassignedNumberTreatment](/powershell/module/teams/test-csteamsunassignednumbertreatment)
