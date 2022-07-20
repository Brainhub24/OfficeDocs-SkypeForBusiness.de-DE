---
title: Einrichten von Audiokonferenzen für Microsoft Teams
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d01954f1-4f37-4cf5-a636-20039e5c59e9
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
- m365initiative-meetings
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- LIL_Placement
description: 'Hier erfahren Sie, wie Sie Einwahl- oder Audiokonferenzen für Personen in Ihrem Unternehmen einrichten, die telefonisch an Konferenzanrufen teilnehmen müssen. '
ms.openlocfilehash: 701c1b4826a52400d91d18d4aa26f11aac07d266
ms.sourcegitcommit: 312ff79ecab91412918793ec882bfc6e0143d30a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/19/2022
ms.locfileid: "66884834"
---
# <a name="set-up-audio-conferencing-for-microsoft-teams"></a>Einrichten von Audiokonferenzen für Microsoft Teams

Manchmal müssen Mitarbeiter in Ihrer Organisation ein Telefon nutzen, um sich in eine Besprechung einzuwählen. Für genau diese Situation ist die Audiokonferenzfunktion in Microsoft Teams gedacht. Die Mitarbeiter können sich mit einem Telefon in Teams-Besprechungen einwählen, anstatt die Teams-App auf einem Mobilgerät oder PC zu verwenden.
  
You only need to set up Audio Conferencing for people who plan to schedule or lead meetings. Meeting attendees who dial in don't need any licenses assigned to them or other setup.
  
Häufig gestellte Fragen zu Audiokonferenzen finden Sie unter [Häufig gestellte Fragen zu Audiokonferenzen](audio-conferencing-common-questions.md).

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="step-1-find-out-if-audio-conferencing-is-available-in-your-countryregion"></a>Schritt 1: Stellen Sie fest, ob Audiokonferenzen in Ihrem Land/Ihrer Region verfügbar sind

Gehen Sie auf [Länder- und Regionenverfügbarkeit für Audiokonferenzen und Anrufpläne](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md) und wählen Sie Ihr Land oder Ihre Region aus, um Verfügbarkeitsinformationen über Audiokonferenzen sowie Informationen über Telefonanlage, Anrufpläne, gebührenfreie Nummern und Guthaben für Kommunikationen zu erhalten.

## <a name="step-2-get-and-assign-licenses"></a>Schritt 2: Abrufen und Zuweisen von Lizenzen

1. Für Audiokonferenzen benötigen Sie eine Lizenz für jeden Benutzer, der Einwahlbesprechungen einrichtet. Informationen dazu, welche Lizenzen Sie für Audiokonferenzen erwerben müssen und was diese kosten, erhalten Sie unter [Add-On-Lizenzierung für Microsoft Teams](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md).

    >[!NOTE]
    > Audiokonferenzen sind in Office 365 Enterprise E5-Lizenzen und als Add-On enthalten.

2. Nachdem Sie die Audiokonferenz-Lizenzen erworben haben, müssen Sie diese den Personen in Ihrer Organisation zuweisen, die Besprechungen planen oder leiten werden. Lesen Sie dazu [Zuweisen von Lizenzen an Benutzer in Microsoft 365 oder Office 365 Business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc). Dies gilt für Lizenzen, die Sie für die Personen in Ihrer Organisation erworben haben, die Besprechungen planen oder leiten werden.

3. Wir empfehlen auch, dass Sie Guthaben für Kommunikations-Lizenzen (sie kosten nichts) denselben Personen zuweisen, denen Sie im vorherigen Schritt Lizenzen zugewiesen haben. Weitere Informationen zum Guthaben für Kommunikationen finden Sie unter [Einrichten von Guthaben für Kommunikationen für Ihr Unternehmen](set-up-communications-credits-for-your-organization.md).

   > [!NOTE]
   > Sie können auch [Audiokonferenzen mit Minutenabrechnung](audio-conferencing-pay-per-minute.md) einrichten.

## <a name="step-3-get-service-numbers-for-your-conferencing-bridges"></a>Schritt 3: Servicenummern für Ihre Konferenzbrücken anfordern

Für Audiokonferenzen können Sie keine Benutzertelefonnummern verwenden; Sie müssen Servicenummern anfordern. Sie können für Ihre Konferenzbrücken gebührenpflichtige oder gebührenfreie Servicenummern abrufen. Es gibt drei Möglichkeiten, gebührenpflichtige und gebührenfreie Servicenummern zu erhalten:
  
- **Über das Microsoft Teams Admin Center**. Für einige Länder/Regionen können Sie Servicenummern für Ihre Konferenzbrücken über das Microsoft Teams Admin Center erhalten. Siehe [Abrufen von Servicetelefonnummern](./getting-service-phone-numbers.md).

- **Portieren von bestehenden Servicenummern**. Portieren oder übertragen Sie vorhandene Telefonnummern von Ihrem derzeitigen Dienstanbieter oder Netzbetreiber zu Microsoft 365 oder Office 365. Über [Übertragen von Telefonnummern zu Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md) oder [Rufnummern für Ihre Organisation verwalten](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) erhalten Sie weitere hilfreiche Informationen.  
  
- **Verwenden eines Anforderungsformulars für neue Telefonnummern**. Manchmal können Sie (je nach Land/Region) Ihre neuen Servicenummern nicht über das Microsoft Teams Admin Center beziehen, oder Sie benötigen bestimmte Telefonnummern oder Ortsvorwahlen. Wenn dies der Fall ist, müssen Sie ein Formular herunterladen und an uns zurücksenden. Weitere Informationen finden Sie unter [Verwalten von Rufnummern für Ihre Organisation](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).

## <a name="step-4-assign-a-service-number-to-the-conferencing-bridge"></a>Schritt 4: Zuweisen einer Servicenummer zur Konferenzbrücke

Sobald Sie Ihre gebührenpflichtigen und/oder gebührenfreien Telefonnummern für Ihre Konferenzbrücke erhalten, müssen Sie die Nummern zuweisen, damit sie für die Einladungen zu den Besprechungen verwendet werden können.  

Führen Sie die folgenden Schritte aus, um Ihrer Audiokonferenzbrücke eine neue Rufnummer zuzuweisen:

 **Verwenden des Microsoft Teams Admin Centers**:

 1. Gehen Sie auf der Startseite zu **Sprache** > **Telefonnummern**.
 2. Wählen Sie die entsprechende Telefonnummer aus, und klicken Sie auf **Zuweisen**.

Weitere Informationen finden Sie unter [Ändern der Telefonnummern Ihrer Audiokonferenzbrücke](change-the-phone-numbers-on-your-audio-conferencing-bridge.md).

## <a name="step-5-set-the-default-and-alternate-languages-for-a-conferencing-bridge"></a>Schritt 5: Legen Sie die Standard- und Alternativsprachen für eine Konferenzbrücke fest

 Als Nächstes sollten Sie die [Sprachen für die automatische Telefonzentrale für Audiokonferenzen in Microsoft Teams](set-auto-attendant-languages-for-audio-conferencing-in-teams.md) festlegen, die die automatische Telefonkonferenzzentrale verwendet, um einen Anrufer zu begrüßen, wenn er sich mit einer Telefonnummer für Audiokonferenzen einwählt.

 **Verwenden des Microsoft Teams Admin Centers**:

1. Gehen Sie auf der Startseite zu **Besprechungen** > **Konferenzbrücken**.
2. Wählen Sie die Telefonnummer der Konferenzbrücke, klicken Sie auf **Bearbeiten**, und wählen Sie dann die Standardsprache aus.

## <a name="step-6-set-your-conferencing-bridge-settings"></a>Schritt 6: Servicenummern für Ihre Konferenzbrücken einstellen

Nachdem Sie Ihre Konferenzbrücke eingerichtet haben, vergewissern Sie sich, dass die Standardeinstellungen, wie z. B. Ein-/Ausgangsbenachrichtigungen und PIN-Länge, die sind, die Sie verwenden möchten; wenn nicht, können Sie sie ändern.

 **Verwenden des Microsoft Teams Admin Centers**:

1. Gehen Sie auf der Startseite zu **Besprechungen** > **Konferenzbrücken**.
2. Wählen Sie **Brückeneinstellungen** aus. Daraufhin wird der Bereich **Brückeneinstellungen** geöffnet.

Weitere Informationen finden Sie unter [Einstellungen für eine Audiokonferenzbrücke ändern](change-the-settings-for-an-audio-conferencing-bridge.md).

## <a name="step-7-assign-dial-in-phone-numbers-for-users-who-lead-meetings"></a>Schritt 7: Zuweisen von Einwahlnummern für Benutzer, die Besprechungen leiten

Weitere Informationen finden [Sie unter Festlegen der Telefonnummern, die in Einladungen in Microsoft Teams enthalten sind](set-the-phone-numbers-included-on-invites-in-teams.md).

Weitere Informationen finden Sie unter [Zuweisen von Microsoft als Anbieter von Audiokonferenzen](/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).

> [!NOTE]
> Sie können Telefonnummern auch festlegen, indem Sie sie der *TeamsAudioconferencingpolicy* hinzufügen und die Richtlinie Ihren Benutzern zuweisen. Gebührenpflichtige und gebührenfreie Telefonnummern, die der Richtlinie hinzugefügt wurden, haben Vorrang vor den Telefonnummern, die über den Einstellungsbereich für Audiokonferenzen einzeln für Benutzer festgelegt werden. Wenn der *Teamsaudioconferencingpolicy* keine Telefonnummern hinzugefügt werden, wird die über den Einstellungsbereich für Audiokonferenzen individuell für Benutzer festgelegte Telefonnummer in Microsoft Teams-Besprechungsanfragen angezeigt. [Die Richtlinieneinstellungen für Audiokonferenzen für gebührenpflichtige und gebührenfreie Telefonnummern](audio-conferencing-toll-free-numbers-policy.md) enthalten weitere Informationen.

> [!IMPORTANT]
> Es kann bis zu 24 Stunden dauern, bis die zugewiesenen Telefonnummern in Ihrer Besprechungseinladung angezeigt werden. Wenn aktualisierte Nummern nicht angezeigt werden, warten Sie mindestens 24 Stunden, bevor Sie sich an den Support wenden.

## <a name="step-8-set-up-meeting-invitations-optional"></a>Schritt 8: Besprechungseinladungen einrichten (optional)

Die Einwahlnummern, die für den Benutzer festgelegt sind, werden automatisch zu den Besprechungseinladungen hinzugefügt, die an die Teilnehmer gesendet werden. Sie können jedoch Ihre eigene Hilfe- und rechtlichen Links, eine Textnachricht und eine kleine Firmengrafik hinzufügen, wenn Sie dies möchten. Weitere Informationen dazu finden Sie unter [Anpassen von Besprechungseinladungen](meeting-settings-in-teams.md#customize-meeting-invitations).

## <a name="related-topics"></a>Verwandte Themen

[Allgemeine Fragen zu Audiokonferenzen](audio-conferencing-common-questions.md)
  
[Telefonnummern für Audiokonferenzen in Microsoft Teams](phone-numbers-for-audio-conferencing-in-teams.md)
  
[Festlegen von Optionen für Onlinebesprechungen und Telefonkonferenzen](https://support.office.com/article/DCD1CA39-0C1F-466C-9573-F04138FEF5E2)
