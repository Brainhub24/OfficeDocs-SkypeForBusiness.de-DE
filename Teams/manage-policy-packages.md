---
title: Verwalten von Richtlinienpaketen in Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.reviewer: sekrantz, aaglick
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.policypackages.overview
- seo-marvel-apr2020
ms.localizationpriority: medium
search.appverid: MET150
description: Erfahren Sie, wie Sie Richtlinienpakete in Microsoft Teams verwenden und verwalten, um die Verwaltung von Richtlinien für Benutzergruppen zu vereinfachen, zu optimieren und für Einheitlichkeit zu sorgen.
ms.openlocfilehash: f90febffb5385a3b91859d63db1b4b320e0a94a7
ms.sourcegitcommit: 5880de47e986854fca873ae75f76a7ecad194dff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2022
ms.locfileid: "62425306"
---
# <a name="manage-policy-packages-for-microsoft-teams"></a>Verwalten von Richtlinienpaketen für Microsoft Teams

Ein Richtlinienpaket in Microsoft Teams ist eine Sammlung vordefinierter Richtlinien und Richtlinieneinstellungen, die Sie Benutzern zuweisen können, die ähnliche Rollen in Ihrer Organisation haben. Wir haben Richtlinienpakete erstellt, um die Verwaltung von Richtlinien für Benutzergruppen in Ihrer Organisation zu vereinfachen, zu optimieren und für Konsistenz zu sorgen.  

Sie können die in der Richtlinie [enthaltenen Teams](#policy-packages-included-in-teams) oder eigene benutzerdefinierte [Richtlinienpakete erstellen](#custom-policy-packages).

:::image type="content" source="media/policy-packages-admin-center.png" alt-text="Screenshot der Seite "Richtlinienpakete" im Admin Center":::

Sie können die Einstellungen der Richtlinien in einem Richtlinienpaket an die Anforderungen Ihrer Benutzer anpassen. Wenn Sie die Einstellungen der Richtlinien in einem Paket ändern, erhalten alle diesem Paket zugewiesenen Benutzer die aktualisierten Einstellungen. Sie verwalten Richtlinienpakete mithilfe des Microsoft Teams Admin Centers oder von PowerShell.

> [!NOTE]
> Dieses Feature steht vorübergehend in der öffentlichen Vorschau für alle Microsoft Teams zur Verfügung. Um dieses Feature nach der Vorschau zu erhalten, benötigt jeder Benutzer die Add-On-Lizenz für Advanced Communications. Weitere Informationen finden Sie unter [Add-On für erweiterte Kommunikation für Microsoft Teams](/microsoftteams/teams-add-on-licensing/advanced-communications).

## <a name="what-is-a-policy-package"></a>Was ist ein Richtlinienpaket?

Mit Richtlinienpaketen können Sie Teams, die Sie für bestimmte Gruppen von Personen in Ihrer Organisation zulassen oder einschränken möchten. Jedes Richtlinienpaket in Teams ist auf eine Benutzerrolle ausgelegt und enthält vordefinierte Richtlinien und Richtlinieneinstellungen, die die für diese Rolle typischen Zusammenarbeits- und Kommunikationsaktivitäten unterstützen.

Richtlinienpakete unterstützen die folgenden Teams Richtlinientypen:

- Messagingrichtlinie
- Besprechungsrichtlinie
- App-Setuprichtlinie
- Anrufrichtlinie
- Richtlinie für Liveereignisse

## <a name="policy-packages-included-in-teams"></a>In den Richtlinienpaketen enthaltene Teams

Teams enthält derzeit die folgenden Richtlinienpakete.

| Paketname | Beschreibung |
|---------|---------|
|Education (Student im Bildungswesen)    |Erstellt einen Satz von Richtlinien und Richtlinieneinstellungen, die für Studierende höherer Bildungseinrichtungen gelten.|
|Education (Grundschüler)   |Erstellt einen Satz von Richtlinien und Richtlinieneinstellungen, die für primäre Schüler/Studierende gelten.|
|Education (Schüler an einer Sekundärschule)    |Erstellt einen Satz von Richtlinien und Richtlinieneinstellungen, die für sekundäre Schüler/Studenten gelten.         |
|Education (Lehrer)    |Erstellt einen Satz von Richtlinien und Richtlinieneinstellungen, die für Lehrkräfte gelten.      |
|Education (Lehrkraft einer Grundschule mit Fernunterricht)    |Erstellt eine Reihe von Richtlinien, um die Sicherheit und Zusammenarbeit der Lehrkräfte beim Lernen per Fernzugriff zu maximieren.      |
|Education (Grundschüler mit Fernunterricht)    |Erstellt eine Reihe von Richtlinien, um die Sicherheit und Zusammenarbeit der Schüler beim Lernen per Fernzugriff zu maximieren.      |
|Frontline-Manager |Erstellt einen Satz von Richtlinien und wendet diese Einstellungen auf Frontline-Manager in Ihrer Organisation an. |
|Frontline-Worker |Erstellt einen Satz von Richtlinien und wendet diese Einstellungen auf Frontline-Mitarbeiter in Ihrer Organisation an. |
|Klinischer Mitarbeiter im Gesundheitswesen  |Erstellt eine Reihe von Richtlinien und Richtlinieneinstellungen, mit denen klinische Mitarbeiter wie Krankenschwestern, Krankenschwestern, Ärzte und Sozialarbeiter uneingeschränkten Zugriff auf Chat, Anrufe, Schichtmanagement und Besprechungen erhalten. |
|Informationsbeauftragter für das Gesundheitswesen  |Erstellt eine Reihe von Richtlinien und Richtlinieneinstellungen, mit denen Informationsbeauftragte wie IT-Personal, Informatikpersonal, Finanzpersonal und Compliance-Beauftragte uneingeschränkten Zugriff auf Chat, Anrufe und Besprechungen erhalten.|
|Patientenzimmer im Gesundheitswesen  |Erstellt eine Reihe von Richtlinien und Richtlinieneinstellungen, die für Patientenzimmer in Ihrer Gesundheitsorganisation gelten.|
|Benutzer für kleine und mittelständische Unternehmen (Teams Telefon Anrufplan) |Erstellt eine App-Setuprichtlinie, die die Apps für einen Anrufplan Teams Telefon Anrufplanerfahrung enthält.|
|Benutzer für kleine und mittelständische Unternehmen (Teams Telefon Anrufplan) |Erstellt eine App-Setuprichtlinie, die für kleine und mittelständische Teams (Nicht-Benutzer Teams Telefon Anrufplanerfahrung) relevant ist.
|Public Safety Officer   |Erstellt einen Satz von Richtlinien und Richtlinieneinstellungen, die für Öffentliche Sicherheitsbeauftragte in Ihrer Organisation gelten.|

> [!NOTE]
> Wir werden in zukünftigen Versionen von Teams weitere Richtlinienpakete hinzufügen, überprüfen Sie daher die neuesten Informationen.  

Jede einzelne Richtlinie erhält den Namen des Richtlinienpakets, sodass Sie die Richtlinien, die mit einem Richtlinienpaket verknüpft sind, leicht identifizieren können.
Wenn Sie beispielsweise das Richtlinienpaket für Bildungseinrichtungen (Lehrer) Lehrkräften in Ihrer Schule zuweisen, wird für jede Richtlinie im Paket eine Richtlinie mit dem Namen Education_Teacher erstellt.

![Screenshot des Richtlinienpakets für Bildungseinrichtungen (Lehrer).](media/policy-packages-education_teacher.png)

## <a name="custom-policy-packages"></a>Benutzerdefinierte Richtlinienpakete

Mit benutzerdefinierten Richtlinienpaketen können Sie eigene Richtlinien für Benutzer mit ähnlichen Rollen in Ihrer Organisation bündeln. Erstellen Sie eigene Richtlinienpakete, indem Sie die benötigten Richtlinientypen und Richtlinien hinzufügen.

So erstellen Sie ein neues benutzerdefiniertes Richtlinienpaket:

1. Wählen Sie im linken Navigationsbereich Microsoft Teams Admin Center **Richtlinienpakete** aus, und klicken Sie dann auf **Hinzufügen**.

    :::image type="content" source="media/policy-packages-add.png" alt-text="Screenshot der Schaltfläche "Hinzufügen" auf der Seite "Richtlinienpakete" im Admin Center":::

2. Geben Sie einen Namen und eine Beschreibung für das Paket ein.

    :::image type="content" source="media/policy-packages-add-custom.png" alt-text="Screenshot zum Hinzufügen eines neuen benutzerdefinierten Richtlinienpakets":::

3. Wählen Sie die Richtlinientypen und Richtliniennamen aus, die in das Paket enthalten sein müssen.

4. Klicken Sie auf **Speichern**.

## <a name="how-to-use-policy-packages"></a>Verwenden von Richtlinienpaketen

Im Folgenden wird die Verwendung von Richtlinienpaketen in Ihrer Organisation erläutert.

![Übersicht über die Verwendung von Richtlinienpaketen.](media/manage-policy-packages-overview.png)

- **[Ansicht](#view-the-settings-of-a-policy-in-a-policy-package)**: Anzeigen der Richtlinien in einem Richtlinienpaket. Zeigen Sie dann die Einstellungen jeder Richtlinie in einem Paket an, bevor Sie das Paket zuweisen. Stellen Sie sicher, dass Sie die einzelnen Einstellungen verstehen. Entscheiden Sie, ob die vordefinierten Werte für Ihre Organisation geeignet sind oder ob sie je nach Anforderungen Ihrer Organisation restriktiver oder lenienter sein müssen.

    Wenn eine Richtlinie gelöscht wurde, können Sie die Einstellungen zwar weiterhin anzeigen, jedoch keine Einstellungen ändern. Beim Zuweisen des Richtlinienpakets wird eine gelöschte Richtlinie mit den vordefinierten Einstellungen neu erstellt.

- **[Anpassen](#customize-policies-in-a-policy-package)**: Passen Sie die Einstellungen der Richtlinien im Richtlinienpaket an die Anforderungen Ihrer Organisation an.

- **[Zuweisen](#assign-a-policy-package)**: Weisen Sie das Richtlinienpaket Benutzern zu.  

> [!NOTE]
> Sie können die Einstellungen von Richtlinien in einem Richtlinienpaket auch ändern, nachdem Sie ein Paket zugewiesen haben. Alle Änderungen, die Sie an den Richtlinieneinstellungen vornehmen, werden automatisch auf Benutzer angewendet, denen das Paket zugewiesen wird.

Hier sind die Schritte zum Anzeigen, Zuweisen und Anpassen von Richtlinienpaketen im Microsoft Teams Admin Center.

### <a name="view-the-settings-of-a-policy-in-a-policy-package"></a>Anzeigen der Einstellungen einer Richtlinie in einem Richtlinienpaket

1. Wählen Sie im linken Navigationsbereich Microsoft Teams Admin Center Richtlinienpakete **aus, und** wählen Sie dann ein Richtlinienpaket aus, indem Sie links neben dem Paketnamen klicken.

2. Klicken Sie auf die Richtlinie, die Sie anzeigen möchten.

### <a name="customize-policies-in-a-policy-package"></a>Anpassen von Richtlinien in einem Richtlinienpaket

Sie können die Einstellungen einer Richtlinie über die Seite "Richtlinienpakete" oder direkt zur Richtlinienseite im Microsoft Teams Admin Center ändern.

1. Gehen Sie im linken Navigationsbereich Microsoft Teams Admin Center wie folgt vor:
    - Klicken **Sie auf Richtlinienpakete**, und wählen Sie dann das Richtlinienpaket aus, indem Sie links des Paketnamens klicken.
    - Klicken Sie auf den Richtlinientyp.  Klicken Sie beispielsweise auf **Messagingrichtlinien**.

2. Wählen Sie die Richtlinie aus, die Sie bearbeiten möchten. Richtlinien, die mit einem Richtlinienpaket verknüpft sind, haben denselben Namen wie das Richtlinienpaket.

3. Nehmen Sie die von Ihnen vorgenommenen Änderungen vor, und klicken Sie dann auf **Speichern**.

### <a name="assign-a-policy-package"></a>Zuweisen eines Richtlinienpakets

Sie können ein Richtlinienpaket einem einzelnen Benutzer, einer Gruppe oder einer Gruppe von Benutzern zuweisen. Weitere Informationen zum Zuweisen von Richtlinienpaketen finden Sie unter Zuweisen von [Richtlinienpaketen zu Benutzern und Gruppen](assign-policy-packages.md).

## <a name="related-topics"></a>Verwandte Themen

- [Zuweisen von Richtlinienpaketen](assign-policy-packages.md)
- [Teams von Richtlinienpaketen für EDU-Administratoren](policy-packages-edu.md)
- [Teams Richtlinienpakete-Pakete für das Gesundheitswesen](policy-packages-healthcare.md)
- [Teams von Richtlinienpaketen für Behörden](policy-packages-gov.md)
