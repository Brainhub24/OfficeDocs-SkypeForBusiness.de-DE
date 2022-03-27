---
title: Verwenden der API Teams Zur Übermittlung von Apps zum Übermitteln und Genehmigen Ihrer benutzerdefinierten Apps
author: guptaashish
ms.author: guptaashish
manager: prkosh
ms.reviewer: joglocke, vaibhava
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
description: Hier erfahren Sie, wie Sie Ihre benutzerdefinierten Apps genehmigen, die mithilfe der API Teams Übermittlung von Apps in Microsoft Teams.
ms.openlocfilehash: c414bf8af8dc7edbea8376031592260142d67732
ms.sourcegitcommit: 39378888464ade3cb45879a449143f40f202f3e9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2022
ms.locfileid: "64456918"
---
# <a name="publish-a-custom-app-submitted-through-the-teams-app-submission-api"></a>Veröffentlichen einer benutzerdefinierten App, die über die APP Teams Übermittlungs-API übermittelt wird

## <a name="overview"></a>Übersicht

> [!NOTE]
> Wenn Sie eine benutzerdefinierte Teams veröffentlichen, steht sie Benutzern im App Store Ihrer Organisation zur Verfügung. Es gibt zwei Möglichkeiten zum Veröffentlichen einer benutzerdefinierten App, und die Art der Verwendung hängt davon ab, wie Sie die App erhalten. **Dieser Artikel befasst sich mit dem Genehmigen** und Veröffentlichen einer benutzerdefinierten App, die ein Entwickler über die API Teams App-Übermittlung übermittelt. Die andere Methode, das Hochladen einer benutzerdefinierten App, wird verwendet, wenn Ihnen ein Entwickler ein App-Paket im Format .zip sendet. Weitere Informationen zu dieser Methode finden Sie unter [Veröffentlichen einer benutzerdefinierten App durch Hochladen eines App-Pakets](/microsoftteams/upload-custom-apps). Das Widget zum Genehmigen von Apps ist in GCC nicht verfügbar.

> [!IMPORTANT]
> Diese Methode ist derzeit für andere GCC verfügbar. Sie müssen die Methode *zum Hochladen einer benutzerdefinierten App* verwenden.

Dieser Artikel enthält eine End-to-End-Anleitung, wie Sie Ihre Teams-App von der Entwicklung über die Bereitstellung bis zur Ermittlung verwenden können. Sie erhalten einen Überblick über die verbundenen Benutzererfahrungen, die von Teams während des gesamten App-Lebenszyklus bereitgestellt werden, um die Entwicklung, Bereitstellung und Verwaltung von benutzerdefinierten Apps im App Store Ihrer Organisation zu optimieren.

Wir gehen auf jeden Schritt des Lebenszyklus ein, einschließlich der Art und Weise, wie Entwickler die API für die Übermittlung von Teams-Apps verwenden können, um benutzerdefinierte Apps direkt an das Microsoft Teams Admin Center zu übermitteln, damit Sie diese überprüfen und genehmigen können, wie Richtlinien zum Verwalten von Apps für Benutzer in Ihrer Organisation festgelegt werden und wie Ihre Benutzer sie in Teams entdecken.

![Übersicht über ihre App von der Entwicklung bis zur Bereitstellung.](media/custom-app-lifecycle.png)

Dieser Leitfaden befasst sich Teams Aspekte der App und richtet sich an Administratoren und IT-Profis. Informationen zum Entwickeln Teams Apps finden Sie in der Dokumentation [Teams Entwickler.](/microsoftteams/platform)

## <a name="develop"></a>Entwickeln

### <a name="create-the-app"></a>Erstellen der App

Die Microsoft Teams-Entwicklerplattform erleichtert Entwicklern die Integration Ihrer eigenen Apps und Dienste, um die Produktivität zu steigern, Entscheidungen schneller zu treffen und die Zusammenarbeit an vorhandenen Inhalten und Workflows zu fördern. Apps, die auf der Teams-Plattform erstellt wurden, sind Brücken zwischen dem Teams-Client und Ihren Diensten und Workflows und bringen sie direkt in den Kontext Ihrer Zusammenarbeitsplattform. Weitere Informationen finden Sie in der Dokumentation [Teams Entwickler.](/microsoftteams/platform)

### <a name="submit-the-app"></a>Übermitteln der App

Wenn die App für die Produktion verwendet werden kann, kann der Entwickler die App mithilfe der TEAMS-API für die Übermittlung von Apps übermitteln, die von der [Graph-API](/graph/api/teamsapp-publish?view=graph-rest-beta&tabs=http#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog&preserve-view=true), einer integrierten Entwicklungsumgebung (Integrated Development Environment, IDE) wie Visual Studio Code oder einer Plattform wie Power Apps und Power Virtual Agents aufgerufen werden kann. Dadurch steht die App auf [der Seite Apps](/microsoftteams/manage-apps) verwalten des Teams Admin Center zur Verfügung, auf der Sie sie überprüfen und genehmigen können.

Die Teams-API für die Übermittlung von Apps, die auf [Microsoft Graph](/graph/api/teamsapp-publish?tabs=http&view=graph-rest-beta#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog&preserve-view=true) aufgebaut ist, ermöglicht Es Ihrer Organisation, auf der Plattform Ihrer Wahl zu entwickeln und den Übermittlungs-zu-Genehmigungsprozess für benutzerdefinierte Apps auf ihrem Teams.

Hier sehen Sie ein Beispiel dafür, wie dieser App-Einreichungsschritt in diesem Visual Studio Code:

![eine App im Visual Studio Code.](media/custom-app-lifecycle-submit-app.png)

Beachten Sie, dass die App dadurch noch nicht im App Store Ihrer Organisation veröffentlicht wird. Mit diesem Schritt wird die App an das Teams Admin Center übermittelt, wo Sie sie für die Veröffentlichung im App Store Ihrer Organisation genehmigen können.

Weitere Informationen zur Verwendung der -API Graph zum Übermitteln von Apps finden Sie [hier](/graph/api/teamsapp-publish?tabs=http&view=graph-rest-beta#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog&preserve-view=true).

## <a name="notify"></a>Benachrichtigen

Sie können Benachrichtigungen aktivieren, damit Sie wissen, wann Entwickler eine neue Anwendung zur Überprüfung und Genehmigung einreichen. Außerdem erhalten Sie Benachrichtigungen, wenn Entwickler App-Updates einreichen. Um Benachrichtigungen über die App-Übermittlung im Teams Admin Center zu aktivieren, wechseln Sie zu Notifications [**&** **alertsRulesApp-Übermittlungen** >  > ](https://admin.teams.microsoft.com/notifications/rules), und aktivieren Sie die Regel, indem Sie den Status in **Aktiv ändern**. Diese Einstellung ist standardmäßig deaktiviert. Sie müssen ein globaler Administrator oder ein Teams sein, um diese Einstellung aktivieren zu können.

Nachdem Sie diese Einstellung aktivieren, erhalten Sie im Team für Administratorbenachrichtigungen  und -benachrichtigungen Benachrichtigungen in einem neuen Kanal namens **App-Übermittlungen**. Alternativ können Sie ein vorhandenes Team und einen vorhandenen Kanal auswählen, um Benachrichtigungen an ein bestimmtes Team und einen bestimmten Kanal zu senden. Führen Sie hierzu folgende Schritte aus:

1. Aktivieren Sie **in der Regel für App-Übermittlungen** das Kontrollkästchen **Kanalbenachrichtigung** unter **Aktionen**.
1. Wählen Sie die **Schaltfläche Kanal auswählen** aus.
1. Suchen Sie nach einem Team, das hinzugefügt werden soll.
1. Suchen Sie nach einem Kanal, den Sie hinzufügen möchten.
1. Wählen Sie **Übernehmen aus**.

    ![Kontrollkästchen "Benachrichtigung bei benutzerdefinierten Kanälen"](media/channel-alert.png)

> [!NOTE]
> Aktivieren Sie **das Kontrollkästchen Standardkanalbenachrichtigung** , um Benachrichtigungen an das Team für **Administratorbenachrichtigungen** und -benachrichtigungen im Kanal **"App-Übermittlungen" zu** erhalten.

![Standardmäßiges Kontrollkästchen für Kanalbenachrichtigungen.](media/default-channel-alert.png)

Sie können Benachrichtigungen für einen externen Webhook auch einrichten, indem Sie nach dem Aktivieren des Kontrollkästchens **Webhook eine öffentliche Webhook-URL** angeben. Eine JSON-Benachrichtigungsnutzlast wird an die Webhook-URL gesendet.

![Benachrichtigung über die App-Übermittlung.](media/app-submission-notification.png)

Nachdem Sie die App-Übermittlungsregel eingerichtet haben, können Sie die Benachrichtigungskarten im angegebenen Kanal überprüfen, um App-Details anzuzeigen, und Details anzeigen auswählen, um Apps im Teams Admin Center zu öffnen.

## <a name="validate"></a>Überprüfen

Auf [der](/microsoftteams/manage-apps) Seite "Apps verwalten" im Teams Admin Center (wechseln Sie in [ >  der linken Navigationsleiste zu Teams-Apps **Verwalten**](https://admin.teams.microsoft.com/manage-apps) von Apps) erhalten Sie einen Einblick in alle Teams-Apps für Ihre Organisation. Mit **dem Widget Zur** Genehmigung ausstehend am oberen Rand der Seite können Sie sehen, wann eine benutzerdefinierte App zur Genehmigung eingereicht wird.

In der Tabelle zeigt eine neu übermittelte App automatisch den **Veröffentlichungsstatus** Übermittelt und **den Status blockiert** **an**. Sie können die Spalte **Veröffentlichungsstatus** in absteigender Reihenfolge sortieren, um die App schnell zu finden.

![Veröffentlichungsstatus.](media/custom-app-lifecycle-validate-app.png)

Klicken Sie auf den App-Namen, um zur Seite mit den App-Details zu wechseln. Auf der **Registerkarte** "Informationen" können Sie Details zur App anzeigen, einschließlich Beschreibung, Status, Einreichungs- und App-ID.

![App-Detailseite für eine übermittelte App.](media/custom-app-lifecycle-app-details.png)

Weitere Informationen zur Verwendung der Graph-API zum Überprüfen des **Veröffentlichungsstatus finden** Sie [hier](/graph/api/appcatalogs-list-teamsapps?tabs=http&view=graph-rest-beta#example-3-find-application-based-on-the-teams-app-manifest-id&preserve-view=true).

## <a name="publish"></a>Veröffentlichen

Wenn Sie bereit sind, die App benutzern zur Verfügung zu stellen, veröffentlichen Sie die App.

1. Melden Sie sich [Teams Admin Center an](https://admin.teams.microsoft.com/dashboard).
1. Wechseln Sie im linken Bereich zu **Teams Verwalten** >  **von Apps**.
1. Wählen Sie den App-Namen aus, um zur Seite mit den App-Details zu  wechseln, und wählen Sie dann im Feld Veröffentlichungsstatus die Option Veröffentlichen **aus**.

    ![Schaltfläche "Veröffentlichen" auf der App-Detailseite.](media/submitted-app-pending-action.png)

Nachdem Sie die App veröffentlicht haben, ändert sich der **Veröffentlichungsstatus** **in Veröffentlicht** , und **der Status** ändert sich automatisch in **Zulässig**.

## <a name="set-up-and-manage"></a>Einrichten und Verwalten

### <a name="control-access-to-the-app"></a>Steuern des Zugriffs auf die App

Standardmäßig können alle Benutzer in Ihrer Organisation im App Store Ihrer Organisation auf die App zugreifen. Um einzuschränken und zu steuern, wer über die Berechtigung zum Verwenden der App verfügt, können Sie eine App-Berechtigungsrichtlinie erstellen und zuweisen. Weitere Informationen finden Sie unter [Verwalten von Richtlinien für App-Berechtigungen in Microsoft Teams](teams-app-permission-policies.md).

### <a name="pin-and-install-the-app-for-users-to-discover"></a>Anheften und Installieren der App, die Benutzer entdecken können

Damit Benutzer die App finden können, die sie haben, müssen sie standardmäßig zum App Store Ihrer Organisation wechseln und nach der App suchen. Um Benutzern den Zugriff auf die App zu ermöglichen, können Sie die App an die App-Leiste in Teams. Erstellen Sie dazu eine App-Setuprichtlinie, und weisen Sie sie Benutzern zu. Weitere Informationen finden Sie unter [Verwalten von App-Einrichtungsrichtlinien in Microsoft Teams](teams-app-setup-policies.md).

### <a name="search-the-audit-log-for-teams-app-events"></a>Durchsuchen des Überwachungsprotokolls nach Teams App-Ereignissen

Sie können das Überwachungsprotokoll durchsuchen, um die Aktivitäten Teams Apps in Ihrer Organisation anzeigen. Weitere Informationen zum Durchsuchen des Überwachungsprotokolls und zum Einlisten der im Überwachungsprotokoll protokollierten Teams-Aktivitäten finden Sie unter Durchsuchen des Überwachungsprotokolls nach Ereignissen [in Teams](audit-log-events.md).

Damit Sie das Überwachungsprotokoll durchsuchen können, müssen Sie zuerst im [Security & Compliance Center](https://sip.protection.office.com/) die Überwachung aktivieren. Weitere Informationen finden Sie unter [Die Überwachungsprotokollsuche ein- oder ausschalten](/microsoft-365/compliance/turn-audit-log-search-on-or-off?view=o365-worldwide&preserve-view=true). Denken Sie daran, dass Überwachungsdaten nur ab dem Zeitpunkt verfügbar sind, an dem Sie die Überwachung aktiviert haben.

## <a name="discover-and-adopt"></a>Entdecken und Übernehmen

Benutzer mit Berechtigungen für die App finden sie im App Store Ihrer Organisation. Wechseln Sie **auf der *Seite Apps*** zu Für Ihre Organisation erstellt, um die benutzerdefinierten Apps Ihrer Organisation zu finden.

![Seite "Apps" mit veröffentlichter App.](media/custom-app-lifecycle-discovery.png)

Wenn Sie eine App-Setuprichtlinie erstellt und zugewiesen haben, wird die App an die App-Leiste in Teams angeheftet, um den Zugriff für die Benutzer zu ermöglichen, denen die Richtlinie zugewiesen wurde.

## <a name="update"></a>Aktualisieren

Zum Aktualisieren einer App sollten Entwickler weiterhin die Schritte im Abschnitt [Entwickeln](#develop) ausführen.

Wenn der Entwickler ein Update für eine veröffentlichte benutzerdefinierte App übermittelt, werden Sie auf der Seite Apps verwalten  im Widget Zur Genehmigung ausstehend [benachrichtigt](/microsoftteams/manage-apps). In der Tabelle wird der **Veröffentlichungsstatus** der App auf Update **übermittelt festgelegt**. Sie werden auch im Team für Administratorbenachrichtigungen und -benachrichtigungen unter dem **App-Übermittlungskanal** benachrichtigt, wenn Sie Benachrichtigungen für die App-Übermittlung aktiviert haben. Die Benachrichtigungskarte hat einen Link, über den Sie direkt zur App im admin center Teams werden. Weitere Informationen zum Aktivieren von Benachrichtigungen zur App-Übermittlung finden Sie unter [Benachrichtigen](#notify).

![Seite "Apps verwalten" mit ausstehenden Anforderungen und dem App-Status .](media/custom-app-lifecycle-update-submitted.png)

So überprüfen und veröffentlichen Sie ein App-Update:

1. Wechseln Sie in der linken Navigationsleiste Teams Admin Center zu Apps **Teams** >  **Verwalten von Apps**.
2. Klicken Sie auf den App-Namen, um zur Seite mit den App-Details zu wechseln, und wählen Sie dann **Update verfügbar** aus, um Die Details des Updates zu überprüfen.

    ![Seite "App-Details" aus.](media/custom-app-lifecycle-update-app.png)
3. Wenn Sie fertig sind, wählen Sie Veröffentlichen **aus** , um das Update zu veröffentlichen. Dadurch wird die vorhandene App ersetzt, die Versionsnummer aktualisiert und der **Veröffentlichungsstatus** in **Veröffentlicht geändert**. Alle App-Berechtigungs- und App-Setuprichtlinien bleiben für die aktualisierte App erhalten.

    Wenn Sie das Update ablehnen, bleibt die frühere Version der App veröffentlicht.

Beachten Sie Folgendes:

- Wenn eine App genehmigt wurde, kann jeder Benutzer ein Update für die App einreichen. Dies bedeutet, dass andere Entwickler , einschließlich des Entwicklers, der die App ursprünglich eingereicht hat, ein Update an die App übermitteln können.
- Wenn ein Entwickler eine App übermittelt und die Anforderung aussteht, kann nur dieser Entwickler ein Update an die App übermitteln. Andere Entwickler können ein Update erst dann übermitteln, wenn die App genehmigt wurde.

Weitere Informationen zur Verwendung der -API Graph zum Aktualisieren von Apps finden Sie [hier](/graph/api/teamsapp-update?view=graph-rest-1.0&tabs=http&preserve-view=true).

## <a name="related-topics"></a>Verwandte Themen

- [Veröffentlichen einer benutzerdefinierten App durch Hochladen eines App-Pakets](upload-custom-apps.md)
- [Verwalten Ihrer Apps im Microsoft Teams Admin Center](manage-apps.md)
- [Verwalten von benutzerdefinierten App-Richtlinien und Einstellungen in Teams](teams-custom-app-policies-and-settings.md)
- [Verwalten von Richtlinien für App-Berechtigungen in Teams](teams-app-permission-policies.md)
- [Verwalten von Richtlinien für App-Setup in Teams](teams-app-setup-policies.md)
- [Teams überwachen und warnen](alerts/teams-admin-alerts.md)
- [Microsoft Graph-API für Teams-Apps](alerts/teams-admin-alerts.md)
