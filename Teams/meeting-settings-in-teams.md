---
title: Verwalten von Besprechungseinstellungen
ms.author: mabond
author: mkbond007
manager: serdars
ms.reviewer: sonua
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: high
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.meetingsettings.invitationurls
- ms.teamsadmincenter.meetingsettings.network.ports
- ms.teamsadmincenter.meetingsettings.overview
ms.collection:
- M365-collaboration
- m365initiative-meetings
description: Hier erfahren Sie, wie Sie die Einstellungen für die von Benutzern in Ihrer Organisation geplanten Teams-Besprechungen verwalten.
ms.openlocfilehash: c25405dd305a8556309559d4941dd731331e6d75
ms.sourcegitcommit: 424b14534aa269bb408c97c368102a193b481656
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/14/2022
ms.locfileid: "67706502"
---
# <a name="manage-meeting-settings-in-microsoft-teams"></a>Verwalten von Besprechungseinstellungen in Microsoft Teams

Als Administrator verwenden Sie Teams-Besprechungseinstellungen, um zu steuern, ob anonyme Benutzer an Teams-Besprechungen teilnehmen können und um Besprechungsanfragen anzupassen. Wenn Sie Quality of Service (QoS) aktivieren möchten, können Sie Portbereiche für den Echtzeitdatenverkehr festlegen. Diese Einstellungen gelten für alle Teams-Besprechungen, die Benutzer in Ihrer Organisation planen. Sie verwalten diese Einstellungen über **Besprechungen** > **Besprechungseinstellungen** im Microsoft Teams Admin Center.

Mithilfe einer Richtlinieneinstellung pro Organisator können Administratoren jetzt steuern, ob bestimmte Benutzer oder Benutzergruppen anonymen Benutzern die Teilnahme an den von ihnen organisierten Besprechungen gestatten können. Die Einstellungen pro Organisator und organisationsweite Richtlinien steuern die anonyme Teilnahme, und die restriktiveren werden wirksam.

> [!Important]
 > **-DisableAnonymousJoin** ist die organisationsweite Richtlinieneinstellung. Sie wird in Zukunft veraltet sein, und dann wird die Richtlinie pro Organisator die einzige Möglichkeit sein, die anonyme Teilnahme zu steuern.

## <a name="allow-anonymous-users-to-join-meetings"></a>Anonyme Benutzer dürfen an Besprechungen teilnehmen

Bei der anonymen Teilnahme kann jeder der Besprechung als anonymer Benutzer beitreten, indem er auf den Link in der Besprechungseinladung klickt. Weitere Informationen hierzu finden Sie unter [Teilnehmen an einer Besprechung ohne ein Teams-Konto](https://support.office.com/article/join-a-meeting-without-a-teams-account-c6efc38f-4e03-4e79-b28f-e65a4c039508). Sie können die Möglichkeit anonymer Benutzer zur Teilnahme an Besprechungen entweder auf Organisationsebene oder pro Besprechungsorganisator steuern, indem Sie zwei verschiedene Richtlinieneinstellungen verwenden.

 ### <a name="using-the-microsoft-teams-admin-center-to-configure-organization-wide-policy"></a>Verwenden des Microsoft Teams Admin Centers zum Konfigurieren einer organisationsweiten Richtlinie

Sie müssen ein Teams-Administrator sein, um diese Änderungen machen zu können. Informationen zum Erhalten von Administratorrollen und -Berechtigungen finden Sie unter [Teams-Administratorrollen verwenden, um Teams zu verwalten](./using-admin-roles.md).

1. Navigieren Sie zum [Teams Admin Center](https://admin.teams.microsoft.com).

2. Navigieren Sie in der linken Navigationsleiste zu **Besprechungen** > **Besprechungseinstellungen**.

3. Aktivieren Sie unter **Teilnehmer** die Option **Anonyme Benutzer können an einer Besprechung teilnehmen**.

    ![Screenshot der Teilnehmereinstellungen für Besprechungen im Admin Center.](media/meeting-settings-participants.png "Screenshot der Teilnehmereinstellungen für Teams-Besprechungen im Microsoft Teams Admin Center")

> [!CAUTION]
> Wenn Sie nicht möchten, dass anonyme Benutzer an von Benutzern in Ihrer Organisation geplanten Besprechungen teilnehmen, deaktivieren Sie diese Einstellung.

### <a name="using-powershell-to-configure-per-organizer-policy"></a>Verwenden von PowerShell zum Konfigurieren einer Richtlinie pro Organisator

Administratoren können jetzt steuern, ob bestimmte Benutzer oder Benutzergruppen anonymen Benutzer erlauben können, an den von ihnen organisierten Besprechungen teilzunehmen. Diese neue Richtlinie pro Organisator wird mithilfe des Parameters **-AllowAnonymousUsersToJoinMeeting** in [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) gesteuert. Dies ist in der Teams-PowerShell-Version 2.6.0 und höher verfügbar.

Sie können beide Richtlinien – organisationsweit oder pro Organisator – verwenden, um die anonyme Teilnahme zu verwalten. Wir empfehlen, die Richtlinie pro Organisator zu implementieren. Die organisationsweite Richtlinieneinstellung wird in Zukunft veraltet, und die Richtlinie pro Organisator wird die einzige Möglichkeit sein, die anonyme Teilnahme zu steuern.

Da sowohl die organisationsweite Richtlinie als auch die Richtlinien pro Organisator die anonyme Teilnahme steuern, wird die restriktivere Einstellung wirksam sein. Wenn Sie beispielsweise auf Organisationsebene keine anonyme Teilnahme zulassen, ist dies Ihre effektive Richtlinie, unabhängig davon, was Sie für die Richtlinie pro Organisator konfigurieren. Um anonymen Benutzern die Teilnahme an Besprechungen zu ermöglichen, müssen Sie daher beide Richtlinien so konfigurieren, dass die anonyme Teilnahme durch Festlegen der folgenden Werte zulässig ist:

- **-DisableAnonymousJoin** auf **$false** festlegen
- **-AllowAnonymousUsersToJoinMeeting** auf **$true** festlegen

Alle anderen Wertekombinationen verhindern, dass anonyme Benutzer an Besprechungen teilnehmen können.
> [!NOTE]
> Weitere Informationen zum Verwalten von Besprechungsrichtlinien finden Sie unter [Verwalten von Besprechungsrichtlinien in Microsoft Teams](/microsoftteams/meeting-policies-overview).

### <a name="blocking-anonymous-join-for-specific-client-types"></a>Blockieren der anonymen Teilnahme für bestimmte Clienttypen

Wenn anonyme Benutzer an Besprechungen teilnehmen dürfen, können sie entweder den Teams-Client oder einen benutzerdefinierten Client verwenden, der mit [Azure Communication Services](/azure/communication-services/) erstellt wurde. Administratoren können ausgewählte Clienttypen mithilfe des Parameters **-BlockedAnonymousJoinClientTypes** in [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) blockieren.

Die folgenden Werte sind möglich:
- Null (Standard). Alle Clienttypen sind zulässig.
- Acs. Blockiert benutzerdefinierte Clients, die mit [Azure Communication Services](/azure/communication-services/)erstellt wurden.
- Teams. Blockiert den Teams-Client.

## <a name="allow-anonymous-users-to-interact-with-apps-in-meetings"></a>Zulassen, dass anonyme Benutzer in Besprechungen mit Apps interagieren

Anonyme Benutzer erben jetzt die globale Standardberechtigungsrichtlinie auf Benutzerebene. Dieses Steuerelement ermöglicht dann anonymen Benutzern die Interaktion mit Apps in Teams-Besprechungen, sofern die App von der Berechtigungsrichtlinie auf Benutzerebene aktiviert wurde. Beachten Sie, dass anonyme Benutzer nur mit Apps interagieren können, die bereits in einer Besprechung verfügbar sind, und diese Apps nicht erwerben und/oder verwalten können. 

> [!IMPORTANT]
> Standardmäßig ist die Einstellung, anonymen Benutzern die Interaktion mit Apps in Besprechungen zu erlauben, aktiviert.

 **Verwenden des Microsoft Teams Admin Centers**

Sie müssen ein Teams-Dienstadministrator sein, um auf diese Einstellung zugreifen zu können. Informationen zum Erhalten von Administratorrollen und -Berechtigungen finden Sie unter [Teams-Administratorrollen verwenden, um Teams zu verwalten](./using-admin-roles.md).

1. Navigieren Sie zum [Teams Admin Center](https://admin.teams.microsoft.com).

2. Navigieren Sie in der linken Navigationsleiste zu **Besprechungen** > **Besprechungseinstellungen**.

3. Die Einstellung für **Anonyme Benutzer können mit Apps in Besprechungen interagieren** kann unter **Teilnehmer** geändert werden.

> [!CAUTION]
> Wenn Sie nicht zulassen möchten, dass anonyme Benutzer mit Apps in von Benutzern in Ihrer Organisation geplanten Besprechungen interagieren, deaktivieren Sie diese Einstellung.

## <a name="customize-meeting-invitations"></a>Anpassen von Besprechungseinladungen

Sie können Einladungen zu Teams-Besprechung personalisieren, um die Anforderungen Ihrer Organisation zu erfüllen. So können Sie z. B. das Logo Ihrer Organisation hinzufügen, und hilfreiche Informationen wie Links zu Ihrer Supportwebsite und dem Haftungsausschluss sowie eine reine Text-Fußzeile einfügen.

### <a name="tips-for-creating-a-logo-for-meeting-invitations"></a>Tipps zum Erstellen eines Logos für Besprechungseinladungen  

1. Erstellen Sie ein Bild, das nicht mehr als 188 Pixel breit und 30 Pixel hoch ist (das ist recht klein).
2. Speichern Sie das Bild im JPG- oder PNG-Format.
3. Speichern Sie das Bild an einem Ort, auf den jeder, der die Einladung erhält, zugreifen kann, z. B. auf einer öffentlichen Website.

    Jetzt können Sie es zu Ihren Besprechungseinladungen hinzufügen. Weitere Informationen finden Sie unter den nächsten Schritten.

### <a name="customize-your-meeting-invitations"></a>Anpassen Ihrer Besprechungseinladungen

 **Verwenden des Microsoft Teams Admin Centers**

1. Navigieren Sie zum [Teams Admin Center](https://admin.teams.microsoft.com).
2. Navigieren Sie in der linken Navigationsleiste zu **Besprechungen** > **Besprechungseinstellungen**.
3. Gehen Sie unter **E-Mail-Einladung** wie folgt vor:

    ![Screenshot der Einstellungen für die Besprechungseinladung, die Sie anpassen können.](media/meeting-settings-invitation.png "Screenshot der Einstellungen für die Besprechungseinladung, die Sie für Teams-Besprechungen anpassen können")

    - **Logo-URL** Geben Sie die URL ein, unter der das Logo gespeichert ist.
    - **URL für rechtliche Hinweise** Wenn Ihre Organisation über eine Website mit rechtlichen Hinweisen verfügt, zu der Personen bei rechtliche Bedenken navigieren sollen, geben Sie die URL hier ein.
    - **Hilfe-URL** Wenn Ihre Organisation über eine Supportwebsite verfügt, zu der Personen bei Problemen navigieren sollen, geben Sie die URL hier ein.
    - **Fußzeile** Geben Sie Text ein, der als Fußzeile angezeigt werden soll.
4. Klicken Sie auf **Vorschau für Einladung**, um eine Vorschau Ihrer Besprechungseinladung anzuzeigen.
5. Klicken Sie abschließend auf **Speichern**.
6. Warten Sie eine Stunde, bis die Änderungen weitergegeben wurden. Planen Sie dann eine Teams-Besprechung, um zu sehen, wie die Besprechungseinladung aussieht.  

## <a name="set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings"></a>Festlegen, wie der Echtzeit-Mediendatenverkehr für Teams-Besprechungen gehandhabt werden soll

<a name="bknetwork"> </a>

Wenn Sie Quality of Service (QoS) zur Priorisierung des Netzwerkverkehrs verwenden, können Sie QoS-Markierungen aktivieren und Portbereiche für jede Art von Mediendatenverkehr festlegen. Das Festlegen von Portbereichen für verschiedene Datenverkehrstypen ist nur ein Schritt bei der Handhabung von Echtzeitmedien. Weitere Details finden Sie unter [Quality of Service (QoS) in Teams](qos-in-teams.md).

> [!IMPORTANT]
> Apple-basierte Systeme: Der einzige uns bekannte Fall, bei dem Apple-basierte Geräte den DSCP-Wert tatsächlich festlegen, ist, wenn alle folgenden Bedingungen erfüllt sind:
> - iOS.
> - WLAN-Netzwerk.
> - Cisco-Switches.
> - Der Netzwerkadministrator hat die App zur Liste zugelassener Apps hinzugefügt.
>
> Android-basierte Systeme: Es gibt keine bekannten Einschränkungen.
>
> Wenn Sie QoS aktivieren oder Einstellungen im Microsoft Teams Admin Center für den Teams-Dienst ändern, müssen Sie außerdem [übereinstimmende Einstellungen auf alle Benutzergeräte anwenden](QoS-in-Teams-clients.md) und auf alle internen Netzwerkgeräte, um die Änderungen an QoS in Teams vollständig zu implementieren.

  **Verwenden des Microsoft Teams Admin Centers**
1. Navigieren Sie zum [Teams Admin Center](https://admin.teams.microsoft.com).
2. Navigieren Sie in der linken Navigationsleiste zu **Besprechungen** > **Besprechungseinstellungen**.
3. Gehen Sie unter **Netzwerk** wie folgt vor:

    ![Screenshot der Netzwerkeinstellungen für Besprechungen im Admin Center.](media/meeting-settings-network.png "Screenshot der Netzwerkeinstellungen für Teams-Besprechungen im Microsoft Teams Admin Center")

    - Um die Verwendung von DSCP-Markierungen für QoS zu ermöglichen, aktivieren Sie **QoS-Markierungen (Quality of Service) für Echtzeitmedienverkehr**. Sie haben nur die Möglichkeit, Markierungen zu verwenden oder nicht; Sie können nicht für jeden Datenverkehrstyp eigene Markierungen festlegen. Weitere Informationen zu DSCP-Markierungen finden Sie unter [Auswählen einer QoS-Implementierungsmethode](QoS-in-Teams.md#select-a-qos-implementation-method).

        > [!IMPORTANT]
        > Beachten Sie, dass die Aktivierung von QoS nur für Endpunkte zum Tagging von Paketen ausgeführt wird, die den Client verlassen. Es wird weiterhin empfohlen, für eingehenden Datenverkehr passende QoS-Regeln auf alle internen Netzwerkgeräte zu anwenden.
        
        > [!NOTE]
        > Das DSCP-Markieren erfolgt normalerweise über Quellports, und der UDP-Verkehr wird standardmäßig an das Transportrelais mit dem Zielport 3478 weitergeleitet. Wenn Ihr Unternehmen das Markieren auf Zielports verlangt, kontaktieren Sie bitte den Support, um die Kommunikation zum Transportrelais mit den UDP-Ports 3479 (Audio), 3480 (Video), und 3481 (Teilen) zu aktivieren.
    - Um Portbereiche festzulegen, wählen Sie neben **Portbereich für jeden Typ von Echtzeit-Mediendatenverkehr auswählen** die Option **Portbereiche festlegen** aus, und geben Sie dann die Start- und Endports für Audio, Video und Bildschirmfreigabe ein. Die Auswahl dieser Option ist Voraussetzung für das Implementieren von QoS. 
        > [!Note]
        > Wenn **QoS-Markierungen (Quality of Service) für den Echtzeit-Medienverkehr** aktiviert sind, dann müssen Sie Ihre Porteinstellungen verwalten. Diese werden nicht automatisch verwaltet.
        
        > [!IMPORTANT]
        > Wenn Sie **Automatisch beliebige verfügbare Ports verwenden** auswählen, werden verfügbare Ports zwischen 1024 und 65535 verwendet. Verwenden Sie diese Option nur, wenn Sie QoS nicht implementieren.
        >
        > Die Auswahl eines zu engen Portbereichs führt zu Anrufabbrüchen und schlechter Anrufqualität. Die nachstehenden Empfehlungen sollten das absolute Minimum darstellen.

Wenn Sie sich nicht sicher sind, welche Portbereiche Sie in Ihrer Umgebung verwenden sollen, sind die folgenden Einstellungen ein guter Ausgangspunkt. Weitere Informationen finden Sie unter [Quality of Service (QoS) in Microsoft Teams](QoS-in-Teams.md). Dies sind die erforderlichen DSCP-Markierungen und die vorgeschlagenen entsprechenden Medienportbereiche, die sowohl von den Teams als auch von ExpressRoute verwendet werden.

### <a name="port-ranges-and-dscp-markings"></a>Portbereiche und DSCP-Markierungen

Typ des Mediendatenverkehrs| Client-Quellportbereich \* |Protokoll|DSCP-Wert|DSCP-Klasse|
|:---             |:---                         |:---    |:---      |:---      |
|Audio            | 50.000–50.019               |TCP/UDP |46        |Expedited Forwarding (EF)|
|Video            | 50.020–50.039               |TCP/UDP |34        |Assured Forwarding (AF41)|
|Anwendung/Bildschirmfreigabe| 50.040–50.059      |TCP/UDP |18        |Assured Forwarding (AF21)|
| | | | |

\* Die von Ihnen zugewiesenen Portbereiche dürfen sich nicht überlappen und sollten nebeneinander liegen.

Nachdem QoS eine Weile im Einsatz war, erhalten Sie Nutzungsinformationen über die Nachfrage für jeden dieser drei Workloads, und Sie können auswählen, welche Änderungen Sie auf der Grundlage Ihrer spezifischen Anforderungen vornehmen möchten. Das [Anrufqualitäts-Dashboard](turning-on-and-using-call-quality-dashboard.md) wird Ihnen dabei helfen.
