---
title: Verwalten von Allgemeinen Besprechungsrichtlinien
ms.author: mabond
author: mkbond007
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
- ms.teamsadmincenter.meetingpolicies.general
- seo-marvel-apr2020
description: Erfahren Sie, wie Sie die Richtlinieneinstellungen für allgemeine Besprechungen in Teams verwalten.
ms.openlocfilehash: 0278133ff33e811cc4f08e1ad2973f52615d1426
ms.sourcegitcommit: 424b14534aa269bb408c97c368102a193b481656
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/14/2022
ms.locfileid: "67706954"
---
# <a name="meeting-policy-settings---general"></a>Besprechungsrichtlinien – Allgemeine Einstellungen

<a name="bkgeneral"> </a>

In diesem Artikel werden die folgenden allgemeinen Richtlinieneinstellungen für Teams-Besprechungen beschrieben:

- [Jetzt in Kanälen besprechen](#meet-now-in-channels)
- [Outlook-Add-In](#outlook-add-in)
- [Planung von Kanalbesprechungen](#channel-meeting-scheduling)
- [Planung privater Besprechungen](#private-meeting-scheduling)
- [Jetzt in privaten Besprechungen besprechen](#meet-now-in-private-meetings)
- [Festgelegter Referentenrollenmodus](#designated-presenter-role-mode)
- [Einsatzbericht](#engagement-report)
- [Besprechungsregistrierung](#meeting-registration)
- [Wer kann sich registrieren?](#who-can-register)
- [Besprechungsanbieter für den Inselmodus](#meeting-provider-for-islands-mode)
- [Sprechercoach](#speaker-coach)

## <a name="meet-now-in-channels"></a>Jetzt in Kanälen besprechen

Hierbei handelt es sich um eine benutzerspezifische Richtlinie, die angewendet wird, bevor eine Besprechung beginnt. Diese Einstellung steuert, ob ein Benutzer eine Ad-hoc-Besprechung in einem Teams-Kanal starten kann. Wenn Sie diese Option aktivieren, können Benutzer auf die Schaltfläche " **Besprechung** " klicken, um eine Ad-hoc-Besprechung zu starten oder eine Besprechung im Kanal zu planen. Der Standardwert lautet "True".

[![Screenshot mit dem Symbol "Jetzt besprechen" unter einer Nachricht.](media/meeting-policies-meet-now.png) ](media/meeting-policies-meet-now.png#lightbox)

## <a name="outlook-add-in"></a>Outlook-Add-In

Hierbei handelt es sich um eine benutzerspezifische Richtlinie, die angewendet wird, bevor eine Besprechung beginnt. Über diese Einstellung wird gesteuert, ob Microsoft Teams-Besprechungen in Outlook (Windows, Mac, Web und Mobile) geplant werden können.

![Screenshot zeigt die Funktion zur Planung einer neuen Besprechung.](media/meeting-policies-outlook-add-in.png)

Wenn Sie dies deaktivieren, können Benutzer keine Teams-Besprechungen planen, wenn sie eine neue Besprechung in Outlook erstellen. In Outlook unter Windows wird beispielsweise die Option **Neue Teams-Besprechung** nicht im Menüband angezeigt.

## <a name="channel-meeting-scheduling"></a>Planung von Kanalbesprechungen

Verwenden Sie die vorhandene "AllowChannelMeetingScheduling"-Richtlinie, um zu steuern, welche Arten von Ereignissen in den Kalendern des Team-Kanals erstellt werden können. Hierbei handelt es sich um eine benutzerspezifische Richtlinie, die angewendet wird, bevor eine Besprechung beginnt. Über diese Einstellung wird gesteuert, ob Benutzer eine Besprechung in einem Microsoft Teams-Kanal planen können. Diese Einstellung ist standardmäßig aktiviert.

Wenn diese Richtlinie deaktiviert ist, können Benutzer keine neuen Kanalbesprechungen erstellen. Bereits vorhandene Kanalbesprechungen können jedoch vom Organisator der Veranstaltung bearbeitet werden.

Die Option zum Planen von Besprechungen ist dann deaktiviert.

![Screenshot der Option "Besprechung planen" in Teams.](media/schedule-meeting-option.png)

Die Option zum Auswählen eines Kanals ist deaktiviert.

[![Screenshot der Kalenderoption zum Auswählen eines Kanals, in dem Sie eine Besprechung planen möchten.](media/meeting-policies-select-a-channel-to-meet-in.png) ](media/meeting-policies-select-a-channel-to-meet-in.png#lightbox)

Auf der Seite "Kanalbeiträge" wird Folgendes deaktiviert:

- Die Schaltfläche **Besprechung planen** im Feld zum Verfassen von Kanalantworten
  ![Screenshot mit der Kalenderoption zum Auswählen eines Kanals, in dem Sie eine Besprechung planen möchten.](media/schedule-meeting-disabled-in-chat2.png)
  
- Die Schaltfläche **Besprechung planen** im Kanal-Header.
  ![Screenshot mit der Kalenderoption zum Auswählen eines Kanals, über den Sie eine Besprechung planen möchten.](media/schedule-now-in-header.png)

Im Kanal-Kalender:

- Die Schaltfläche **Neues Ereignis hinzufügen** im Header des Kanalkalenders ist deaktiviert.
  ![Screenshot mit der Kalenderoption zum Auswählen eines Kanals, mit dem Sie eine Besprechung planen können.](media/add-new-event-disabled.png)

- Benutzer können einen Zeitblock im Kanalkalender nicht ziehen und auswählen, um eine Kanalbesprechung zu erstellen.

- Benutzer können keine Tastenkombinationen verwenden, um eine Besprechung im Kanalkalender zu erstellen.

Im Admin Center:

Die Kanalkalender-App wird auf der Seite der App-Berechtigungsrichtlinien im Abschnitt **Microsoft-Apps** angezeigt.

![Screenshot der App-Berechtigungsrichtlinie im Teams Admin Center.](media/manage-microsoft-apps-policy.png)

## <a name="private-meeting-scheduling"></a>Planung privater Besprechungen

Hierbei handelt es sich um eine benutzerspezifische Richtlinie, die angewendet wird, bevor eine Besprechung beginnt. Mit dieser Einstellung wird gesteuert, ob ein Benutzer private Besprechungen in einem Teams-Kanal planen kann. Eine Besprechung ist privat, wenn sie nicht in einem Kanal in einem Team veröffentlicht wird.

Beachten Sie, dass durch das Deaktivieren von **Planung privater Besprechungen zulassen** und **Planung von Kanalbesprechungen zulassen** die Optionen **Erforderliche Teilnehmer hinzufügen** und **Kanal hinzufügen** für Benutzer in Microsoft Teams deaktiviert werden. Diese Einstellung ist standardmäßig aktiviert.

## <a name="meet-now-in-private-meetings"></a>Jetzt in privaten Besprechungen besprechen

Hierbei handelt es sich um eine benutzerspezifische Richtlinie, die angewendet wird, bevor eine Besprechung beginnt. Diese Einstellung steuert, ob ein Benutzer eine private Ad-hoc-Besprechung starten kann.  Diese Einstellung ist standardmäßig aktiviert.

## <a name="designated-presenter-role-mode"></a>Festgelegter Referentenrollenmodus

Hierbei handelt es sich um eine benutzerspezifische Richtlinie. Diese Einstellung ermöglicht es Ihnen, den Standardwert für **Wer kann präsentieren?** in den **Besprechungsoptionen** im Microsoft Teams-Client zu ändern. Diese Richtlinieneinstellung wirkt sich auf alle Besprechungen aus, einschließlich Sofortbesprechungen.

Über die Einstellung **Wer kann präsentieren?** können Besprechungsorganisatoren die Referenten innerhalb einer Besprechung festlegen. Weitere Informationen finden Sie unter [Ändern der Teilnehmereinstellungen für eine Microsoft Teams-Besprechung](https://support.microsoft.com/article/change-participant-settings-for-a-teams-meeting-53261366-dbd5-45f9-aae9-a70e6354f88e) und [Rollen in einer Microsoft Teams-Besprechung](https://support.microsoft.com/article/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019).

Derzeit können Sie diese Richtlinieneinstellung nur mithilfe von PowerShell konfigurieren. Sie können eine vorhandene Microsoft Teams-Besprechungsrichtlinie mithilfe des Cmdlets [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) bearbeiten. Sie können aber auch eine neue Besprechungsrichtlinie für Microsoft Teams mithilfe des Cmdlets [New-CsTeamsMeetingPolicy](/powershell/module/skype/new-csteamsmeetingpolicy) erstellen und sie Benutzern zuweisen.

Um den Standardwert für die Einstellung **Wer kann präsentieren?** in Microsoft Teams anzugeben, legen Sie den Parameter **DesignatedPresenterRoleMode** auf einen der folgenden Werte fest:

- **EveryoneUserOverride**: alle Besprechungsteilnehmer können Referenten sein. Dies ist der Standardwert. Dieser Parameter entspricht der Einstellung **Jeder** in Microsoft Teams.
- **EveryoneInCompanyUserOverride**: authentifizierte Benutzer in der Organisation, einschließlich Gastbenutzer, können Referenten sein. Dieser Parameter entspricht der Einstellung **Personen in meiner Organisation** in Microsoft Teams.
- **OrganizerOnlyUserOverride**: Nur der Besprechungsorganisator kann präsentieren, alle anderen Besprechungsteilnehmer sind lediglich als Teilnehmer angegeben. Dieser Parameter entspricht der Einstellung **Nur ich** in Microsoft Teams.

Bedenken Sie, dass, nachdem Sie den Standardwert festgelegt haben, Besprechungsorganisatoren diese Einstellung in Microsoft Teams weiterhin ändern und auswählen können, wer in den von ihnen geplanten Besprechungen präsentieren kann.

## <a name="engagement-report"></a>Einsatzbericht

Hierbei handelt es sich um eine benutzerspezifische Richtlinie. Über diese Einstellung wird gesteuert, ob Besprechungsorganisatoren den [Teilnahmebericht zu einer Besprechung](teams-analytics-and-reports/meeting-attendance-report.md) herunterladen können.

Diese Richtlinie ist standardmäßig aktiviert und ermöglicht Es Ihren Organisatoren, zu sehen, wer die von ihnen eingerichteten Besprechungen und Webinare registriert und besucht hat. Um sie im Teams Admin Center zu deaktivieren, wechseln Sie zu **Besprechungsbesprechungsrichtlinien** > , und legen Sie die Einstellung des **Engagementberichts** auf **"Aus**" fest.

Sie können auch eine vorhandene Teams-Besprechungsrichtlinie mithilfe des Cmdlets [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) bearbeiten. Sie können aber auch eine neue Besprechungsrichtlinie für Microsoft Teams mithilfe des Cmdlets [New-CsTeamsMeetingPolicy](/powershell/module/skype/new-csteamsmeetingpolicy) erstellen und sie Benutzern zuweisen.

Standardmäßig ist der **AllowEngagementReport-Parameter** in PowerShell auf **"Enabled"** festgelegt. Um zu verhindern, dass ein Besprechungsorganisator den Anwesenheitsbericht der Besprechung herunterlädt, legen Sie den Parameter **"AllowEngagementReport"** auf **"Deaktiviert"** fest.

Wenn diese Richtlinie aktiviert ist, wird die Option zum Herunterladen des Anwesenheitsberichts für Besprechungen im Bereich **"Teilnehmer** " angezeigt.

> [!NOTE]
> Als Administrator können Sie den Anwesenheitsbericht für Besprechungen, die Sie nicht organisieren, nicht anzeigen. Sie können jedoch die Teilnehmerdetails für eine bestimmte Besprechung innerhalb von 24 Stunden nach dieser Besprechung anzeigen. Wechseln Sie im Teams Admin Center zu **"Benutzer** > **verwalten"**. Wählen Sie den Anzeigenamen für den Besprechungsorganisator aus. Wählen Sie die Registerkarte **"Besprechungen & Anrufe** " und dann die entsprechende Besprechungs-ID oder Anruf-ID aus. Wählen Sie dann **"Teilnehmerdetails**" aus.

Weitere Informationen, einschließlich der Grenzwerte des Engagementberichts, finden Sie [unter Anzeigen und Herunterladen von Anwesenheitsberichten zu Besprechungen in Teams](https://support.microsoft.com/office/view-and-download-meeting-attendance-reports-in-teams-ae7cf170-530c-47d3-84c1-3aedac74d310).

## <a name="meeting-registration"></a>Besprechungsregistrierung

Hierbei handelt es sich um eine benutzerspezifische Richtlinie. Wenn Sie dies aktivieren, können Benutzer in Ihrer Organisation Webinare einrichten. Diese Richtlinie ist standardmäßig aktiviert.

Um diese Richtlinie im Teams Admin Center zu bearbeiten, wechseln Sie zu **Besprechungsbesprechungsrichtlinien** > . Um die Besprechungsregistrierung zu deaktivieren, legen Sie die Richtlinie auf **"Aus**" fest.

Sie können eine vorhandene Microsoft Teams-Besprechungsrichtlinie mithilfe des Cmdlets [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) bearbeiten. Sie können aber auch eine neue Besprechungsrichtlinie für Microsoft Teams mithilfe des Cmdlets [New-CsTeamsMeetingPolicy](/powershell/module/skype/new-csteamsmeetingpolicy) erstellen und sie Benutzern zuweisen.

Um die Besprechungsregistrierung zu aktivieren, legen Sie den  **Parameter "MeetingRegistration** " auf **"True"** fest. Dies ist standardmäßig auf **"True"** festgelegt.

Um die Besprechungsregistrierung zu deaktivieren und zu verhindern, dass Benutzer Webinare planen, legen Sie den Parameter auf **"False"** fest.

## <a name="who-can-register"></a>Wer kann sich registrieren?

Diese Richtlinie steuert, welche Benutzer Webinare registrieren und daran teilnehmen können. Diese Richtlinie verfügt über zwei Optionen, die nur verfügbar sind, wenn die **Besprechungsregistrierung** aktiviert ist.

- Legen Sie **fest, wer sich bei** **"Jeder** " registrieren kann, wenn Sie zulassen möchten, dass jeder, einschließlich anonymer Benutzer, Webinare registriert und daran teilnimmt, die Benutzer in Ihrer Organisation eingerichtet haben.
- Legen Sie fest, wer sich **bei "Jeder in der Organisation****" registrieren kann**, wenn Sie nur den Benutzern in Ihrer Organisation die Registrierung und Teilnahme an Webinaren gestatten möchten.

Standardmäßig ist **"Wer kann registrieren** " auf **"Jeder**" festgelegt. Um diese Richtlinie im Teams Admin Center zu bearbeiten, wechseln Sie zu **Besprechungsbesprechungsrichtlinien** > .

Sie können eine vorhandene Microsoft Teams-Besprechungsrichtlinie mithilfe des Cmdlets [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) bearbeiten. Sie können aber auch eine neue Besprechungsrichtlinie für Microsoft Teams mithilfe des Cmdlets [New-CsTeamsMeetingPolicy](/powershell/module/skype/new-csteamsmeetingpolicy) erstellen und sie Benutzern zuweisen.

Legen Sie den **WhoCanRegister-Parameter** auf **"Jeder**" fest, um allen Benutzern, einschließlich anonymer Benutzer, die Registrierung und Teilnahme an Webinaren zu ermöglichen. Dies ist standardmäßig auf **"Jeder** " festgelegt.

Damit nur Benutzer in Ihrer Organisation Webinare registrieren und daran teilnehmen können, legen Sie den Parameter auf **"EveryoneInCompany**" fest.

## <a name="meeting-provider-for-islands-mode"></a>Besprechungsanbieter für den Inselmodus

Hierbei handelt es sich um eine benutzerspezifische Richtlinie. Über diese Einstellung wird gesteuert, welches Add-In für Outlook-Besprechungen für *Benutzer im Inselmodus* verwendet wird. Sie können festlegen, ob Benutzer nur das Add-In für Microsoft Teams-Besprechungen oder sowohl das Add-In für Microsoft Teams-Besprechungen als auch jenes für Skype for Business-Besprechungen verwenden können, um Besprechungen in Outlook zu planen.

Sie können diese Richtlinie nur für Benutzer im Inselmodus anwenden und für die der Parameter **AllowOutlookAddIn** in ihrer Microsoft Teams-Richtlinie auf **True** festgelegt ist.

Derzeit können Sie diese Richtlinie nur mithilfe von PowerShell festlegen. Sie können eine vorhandene Microsoft Teams-Besprechungsrichtlinie mithilfe des Cmdlets [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) bearbeiten. Sie können aber auch eine neue Besprechungsrichtlinie für Microsoft Teams mithilfe des Cmdlets [New-CsTeamsMeetingPolicy](/powershell/module/skype/new-csteamsmeetingpolicy) erstellen und sie Benutzern zuweisen.

Wenn Sie angeben möchten, welches Besprechungs-Add-In für Benutzer zur Verfügung stehen soll, legen Sie den Parameter **PreferredMeetingProviderForIslandsMode** wie folgt fest:

- Legen Sie den Parameter auf **TeamsAndSfB** fest, um sowohl das Add-In für Microsoft Teams-Besprechungen als auch das Skype for Business-Add-In in Outlook zu aktivieren. Dies ist der Standardwert.
- Legen Sie den Parameter auf **Teams** fest, um nur das Add-in für Microsoft Teams-Besprechungen in Outlook zu aktivieren. Diese Richtlinieneinstellung stellt sicher, dass in allen zukünftigen Besprechungen ein Link zur Teilnahme an Microsoft Teams-Besprechungen verfügbar ist. Es werden keine bestehenden Skype for Business-Besprechungslinks nach Microsoft Teams übertragen. Diese Richtlinieneinstellung wirkt sich nicht auf Anwesenheit, Chat, PSTN-Anrufe oder andere Funktionen in Skype for Business aus, was bedeutet, dass die Benutzer Skype for Business weiterhin für diese Funktionen verwenden können.

  Wenn Sie den Parameter auf **Teams** festlegen und dann zurück zu **TeamsAndSfB** ändern, werden beide Besprechungs-Add-Ins aktiviert. Beachten Sie jedoch, dass bestehende Links für die Teilnahme an Microsoft Teams-Besprechungen nicht nach Skype for Business übertragen werden. Nur in Skype for Business-Besprechungen, die nach der Änderung geplant wurden, wird es einen Link zur Teilnahme an Skype for Business-Besprechungen geben.

## <a name="meeting-reactions"></a>Besprechungsreaktionen

Die Einstellung "AllowMeetingReactions" kann nur mithilfe von PowerShell angewendet werden. Es gibt keine Option zum Aktivieren oder Deaktivieren von AllowMeetingReactions im Microsoft Teams Admin Center.

Besprechungsreaktionen sind standardmäßig deaktiviert. Das Deaktivieren der Reaktionen für einen Benutzer bedeutet nicht, dass er in von ihm geplanten Besprechungen keine Reaktionen verwenden kann. Unabhängig von der Standardeinstellung kann ein Besprechungsorganisator weiterhin Reaktionen über die Besprechungsoptionsseite aktivieren.

## <a name="speaker-coach"></a>Sprechercoach

Mit dieser Einstellung können Benutzer den Sprechercoach während einer Teams-Besprechung aktivieren. Speaker Coach lauscht auf die Audiodaten des Benutzers während der Vorführen und bietet privates Echtzeit-Feedback und Verbesserungsvorschläge. Der Benutzer erhält auch nach der Besprechung einen zusammenfassenden Bericht über sein Feedback.

> [!NOTE]
> Der Benutzer, der den Sprechercoach während der Besprechung aktiviert hat, ist der einzige, der den zusammenfassenden Feedbackbericht sehen kann. Administratoren haben keinen Zugriff auf diese Daten.

Derzeit können Sie diese Richtlinie nur in PowerShell festlegen und bearbeiten. mithilfe des Cmdlets ["Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) ". Sie können aber auch eine neue Besprechungsrichtlinie für Microsoft Teams mithilfe des Cmdlets [New-CsTeamsMeetingPolicy](/powershell/module/skype/new-csteamsmeetingpolicy) erstellen und sie Benutzern zuweisen.

Diese Einstellung ist standardmäßig aktiviert. Zum Deaktivieren legen **Sie AllowMeetingCoach** auf **"False"** fest.

## <a name="related-topics"></a>Verwandte Themen

- [Übersicht über PowerShell für Microsoft Teams](teams-powershell-overview.md)
- [Zuweisen von Richtlinien in Teams](policy-assignment-overview.md)
- [Entfernen der Microsoft Teams-Besprechungsrichtlinie "RestrictedAnonymousAccess" von Benutzern](meeting-policies-restricted-anonymous-access.md)
