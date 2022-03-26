---
title: Verwalten von Besprechungsrichtlinien für die Inhaltsfreigabe
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: sonua, shalenc
audience: admin
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.meetingpolicies.contentsharing
- seo-marvel-apr2020
description: Erfahren Sie, wie Sie Besprechungsrichtlinieneinstellungen in Teams für die Inhaltsfreigabe verwalten.
ms.openlocfilehash: dccf36a257cde5731c140f2000e3d0733d3366c3
ms.sourcegitcommit: 42c355d3f4bbe52c063b8f2119baefc0b88f9563
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2022
ms.locfileid: "64403986"
---
# <a name="meeting-policy-settings---content-sharing"></a>Besprechungsrichtlinieneinstellungen – Inhaltsfreigabe

<a name="bkcontentsharing"> </a>

In diesem Artikel werden die folgenden Besprechungsrichtlinieneinstellungen im Zusammenhang mit der Inhaltsfreigabe beschrieben:

- [Bildschirmübertragungsmodus](#screen-sharing-mode)
- [Zulassen, dass ein Teilnehmer die Steuerung erteilt oder anfordert](#allow-a-participant-to-give-or-request-control)
- [Zulassen, dass ein externer Teilnehmer die Steuerung erteilt oder anfordert](#allow-an-external-participant-to-give-or-request-control)
- [PowerPoint Live](#powerpoint-live)
- [Whiteboard](#whiteboard)
- [Freigegebene Notizen](#shared-notes)

## <a name="screen-sharing-mode"></a>Bildschirmfreigabemodus

Diese Einstellung ist eine Kombination aus richtlinien pro Organisator und Benutzer. Mit dieser Einstellung wird steuert, ob die Desktop- und Fensterfreigabe in der Besprechung des Benutzers zulässig ist. Besprechungsteilnehmer, denen keine Richtlinien zugewiesen sind (z. b. anonyme Teilnehmer, Gäste, B2B-Teilnehmer und Partner), erben die Richtlinie des Besprechungsorganisators.

|Einstellungswert |Verhalten  |
|---------|---------|
|**Gesamter Bildschirm**    | Die vollständige Desktop- und Anwendungsfreigabe ist in der Besprechung zulässig. |
|**Einzelne Anwendung**   | Die Anwendungsfreigabe ist in der Besprechung zulässig.        |
|**Deaktiviert**     |Die Bildschirm- und Anwendungsfreigabe ist in der Besprechung deaktiviert.       |

Sehen Sie sich das folgende Beispiel an.

|Benutzer |Besprechungsrichtlinie |Bildschirmübertragungsmodus |
|---------|---------|---------|
|Daniela  | Global   | Gesamter Bildschirm |
|Amala   | Location1MeetingPolicy  | Deaktiviert |

Besprechungen, die von Daniela gehostet werden, ermöglichen Besprechungsteilnehmern, den gesamten Bildschirm oder eine bestimmte Anwendung freizugeben. Wenn Amanda an Danielas Besprechung teilnimmt, kann Amanda ihren Bildschirm oder eine bestimmte Anwendung nicht teilen, da die Richtlinieneinstellung für sie deaktiviert ist. In Besprechungen, die von Amanda gehostet werden, darf niemand seinen Bildschirm oder eine Anwendung teilen – unabhängig von der Richtlinie für den Bildschirmfreigabemodus, die dem jeweiligen Benutzer zugewiesen wurde.  Folglich kann Daniela ihren Bildschirm oder eine einzelne Anwendung in Amandas Besprechungen nicht freigeben.  

Derzeit können Benutzer in einer Microsoft Teams-Besprechung keine Videos abspielen oder ihren Bildschirm freigeben, wenn sie Google Chrome verwenden.

## <a name="allow-a-participant-to-give-or-request-control"></a>Zulassen, dass ein Teilnehmer die Steuerung erteilt oder anfordert

Bei dieser Einstellung handelt es sich um eine Benutzerrichtlinie. Mit dieser Einstellung wird gesteuert, ob der Benutzer die Steuerung des übertragenen Desktops oder Fensters an andere Besprechungsteilnehmer übergeben kann. Um die Steuerung zu übergeben, zeigen Sie auf den oberen Bereich des Bildschirms.

Wenn diese Einstellung für den Benutzer aktiviert ist, wird die Option **Steuerung übergeben** in der oberen Leiste einer Freigabesitzung angezeigt.

![Screenshot zeigt die Option „Steuerung übergeben“.](media/meeting-policies-give-control.png)

Wenn die Einstellung für den Benutzer deaktiviert ist, ist die Option **Steuerung übergeben** nicht verfügbar.

![Screenshot zeigt, dass die Option „Steuerung übergeben“ nicht verfügbar ist.](media/meeting-policies-give-control-not-available.png)

Sehen Sie sich das folgende Beispiel an.

|Benutzer |Besprechungsrichtlinie  |Zulassen, dass ein Teilnehmer die Steuerung erteilt oder anfordert |
|---------|---------|---------|
|Daniela   | Global   | Ein       |
|Bert    | Location1MeetingPolicy        | Aus   |

Daniela kann anderen Teilnehmern einer von Danielk organisierten Besprechung die Steuerung des freigegebenen Desktops oder Fensters geben. Allerdings kann Nochk anderen Teilnehmern die Steuerung nicht geben.

Verwenden Sie das Cmdlet "AllowParticipantGiveRequestControl", um mithilfe von PowerShell festzulegen, wer die Steuerung übergeben bzw. entsprechende Anforderungen annehmen kann.

> [!NOTE]
> Um die Steuerung über freigegebene Inhalte während der Freigabe übergeben und übernehmen zu können, müssen beide Parteien den Microsoft Teams-Desktopclient verwenden. Die Steuerung wird nicht unterstützt, wenn eine der beiden Parteien Teams in einem Browser ausführt. Dies ist auf eine technische Einschränkung zurückzuführen, die wir planen zu beheben.

## <a name="allow-an-external-participant-to-give-or-request-control"></a>Zulassen, dass ein externer Teilnehmer die Steuerung übergibt oder anfordert

Bei dieser Einstellung handelt es sich um eine Benutzerrichtlinie. Ob eine Organisation diese Richtlinie für einen Benutzer festgelegt hat, kontrolliert nicht, was externe Teilnehmer tun können, unabhängig davon, was der Besprechungsorganisator festgelegt hat. Über diesen Parameter wird gesteuert, ob externen Teilnehmern die Steuerung des von jemand anderen freigegebenen Bildschirms übergeben werden kann bzw. ob sie dies anfordern können, je nachdem, was der freigebende Benutzer in den Besprechungsrichtlinien seiner Organisation festgelegt hat. Externe Teilnehmer an Microsoft Teams-Besprechungen können wie folgt kategorisiert werden:  

- Anonymer Benutzer
- Gastbenutzer  
- B2B-Benutzer
- Verbundbenutzer  

Über diese Einstellung wird gesteuert, ob Verbundbenutzer externen Benutzern die Steuerung übergeben können, während die Steuerung der Freigabe über die Einstellung **Zulassen, dass ein externer Teilnehmer die Steuerung übergibt oder anfordert** in ihrer Organisation erfolgt.

Verwenden Sie das "AllowExternalParticipantGiveRequestControl"-Cmdlet, um mithilfe von PowerShell zu steuern, ob externe Teilnehmer die Steuerung übergeben oder entsprechende Anforderungen annehmen können.

### <a name="powerpoint-live"></a>PowerPoint Live

Hierbei handelt es sich um eine benutzerspezifische Richtlinie. Mit dieser Einstellung wird gesteuert, ob der Benutzer PowerPoint-Folien in einer Besprechung übertragen kann. Externe Benutzer, einschließlich anonyme, Gast- und Verbundbenutzer, erben die Richtlinie des Besprechungsorganisators.

Sehen Sie sich das folgende Beispiel an.

|Benutzer |Besprechungsrichtlinie  |PowerPoint Live |
|---------|---------|---------|
|Daniela   | Global   | Ein       |
|Amalia   | Location1MeetingPolicy        | Aus   |

Amanda kann keine PowerPoint-Folien in Besprechungen teilen, selbst wenn sie die Besprechungsorganisatorin ist. Daniela kann PowerPoint-Folien übertragen, auch wenn die Besprechung von Amanda organisiert wurde. Amanda kann die von anderen Personen in der Besprechung übertragenen PowerPoint-Folien anzeigen, auch wenn Sie selbst keine PowerPoint-Folien übetragen kann.

## <a name="whiteboard"></a>Whiteboard

Bei dieser Einstellung handelt es sich um eine Benutzerrichtlinie. Mit dieser Einstellung wird gesteuert, ob ein Benutzer in einer Besprechung das Whiteboard übertragen kann. Externe Benutzer, einschließlich anonyme, B2B- und Verbundbenutzer, erben die Richtlinie des Besprechungsorganisators.

Sehen Sie sich das folgende Beispiel an.

|Benutzer |Besprechungsrichtlinie  |Whiteboard|
|---------|---------|---------|
|Daniela   | Global   | Ein       |
|Amalia   | Location1MeetingPolicy        | Aus   |

Amanda kann das Whiteboard in einer Besprechung nicht teilen, selbst wenn sie die Besprechungsorganisatorin ist. Daniela kann das Whiteboard auch dann übertragen, wenn eine Besprechung von Amanda organisiert wird.  

## <a name="shared-notes"></a>Freigegebene Notizen

Bei dieser Einstellung handelt es sich um eine Benutzerrichtlinie. Mit dieser Einstellung wird gesteuert, ob ein Benutzer in einer Besprechung Notizen erstellen und übertragen kann. Externe Benutzer, einschließlich anonyme, B2B- und Verbundbenutzer, erben die Richtlinie des Besprechungsorganisators. Die Registerkarte **Besprechungsnotizen** wird derzeit nur in Besprechungen mit weniger als 20 Teilnehmern unterstützt.

Sehen Sie sich das folgende Beispiel an.

|Benutzer |Besprechungsrichtlinie  |Freigegebene Notizen |
|---------|---------|---------|
|Daniela   | Global   | Ein       |
|Amalia   | Location1MeetingPolicy | Aus |

Daniela kann sich in Amandas Besprechungen Notizen machen, Amanda kann hingegen in keiner Besprechung Notizen machen.




## <a name="related-topics"></a>Verwandte Themen

- [Übersicht über PowerShell für Microsoft Teams](teams-powershell-overview.md)
- [Benutzern in Microsoft Teams Richtlinien zuweisen](policy-assignment-overview.md)
- [Entfernen der Microsoft Teams-Besprechungsrichtlinie "RestrictedAnonymousAccess" von Benutzern](meeting-policies-restricted-anonymous-access.md)
