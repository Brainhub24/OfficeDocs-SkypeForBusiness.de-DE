---
title: Teams für Education des Richtlinien-Assistenten zum einfachen Anwenden von Richtlinien für sicheres Lernen
author: serdars
ms.author: serdars
manager: serdars
ms.reviewer: shajohri, angch
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- remotework
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Erfahren Sie, wie Sie mithilfe Teams für Education Richtlinien-Assistenten auf einfache Weise Richtlinien für Schüler/Studierende und Lehrkräfte anwenden, um Ihre Lernumgebung sicher zu halten.
f1keywords: ''
ms.openlocfilehash: 9834aceeffc6c5604c144e801405cea968df5a69
ms.sourcegitcommit: 2612020cd932117148440b60be818ba31208b1d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2022
ms.locfileid: "62805456"
---
# <a name="use-the-teams-for-education-policy-wizard-to-easily-apply-policies-for-a-safe-learning-environment"></a>Verwenden des Teams für Education-Richtlinien-Assistenten zum einfachen Anwenden von Richtlinien für eine sichere Lernumgebung

## <a name="overview"></a>Übersicht

Der Microsoft Teams für Education-Richtlinien-Assistent vereinfacht die Verwaltung von Richtlinien für Ihre Schüler/Studierenden und Lehrkräfte. Verwenden Sie sie, um die wichtigsten Richtlinien für die Erstellung einer sicheren und produktiven Lernumgebung auf einfache und schnelle Weise anzuwenden.

Mit Richtlinien in Teams können Sie steuern, Teams verhalten sich in Ihrer Umgebung verhält und welche Features benutzern zur Verfügung stehen. Beispielsweise gibt es Anrufrichtlinien, Besprechungsrichtlinien und Messagingrichtlinien, um nur einige zu nennen, und jeder Richtlinienbereich kann an die Anforderungen Ihrer Organisation angepasst werden.

Um eine sichere und fokussierte Lernumgebung zu erhalten, ist es wichtig, Richtlinien zu setzen, um zu steuern, welche Schüler/Studenten in der Gruppe Teams. Beispielsweise können Sie mithilfe von Richtlinien steuern, wer private Chats und private Anrufe verwenden kann, wer Besprechungen planen und welche Inhaltstypen freigegeben werden können. Sie können auch Richtlinien verwenden, um alle Teams aktivieren, die die Lernerfahrung bereichern.

Richtlinien müssen sowohl für Schüler/Studierende als auch für Lehrkräfte angepasst werden, um die Lernerfahrung zu schützen. Richtlinien für Schüler/Studierende müssen restriktiver sein, um das Risiko zu verringern, unangemessene Zugriffsebenen zu erhalten. Lehrkräfte und Mitarbeiter benötigen einen separaten Satz von Richtlinien, die möglicherweise ungenügend sind, um erfolgversprechend zu sein. Lassen Sie beispielsweise Lehrkräfte Besprechungen planen und verhindern, dass Schüler/Studierende dies tun.

:::image type="content" source="media/easy-policy-setup-institution-type.png" alt-text="Screenshot des Assistenten.":::

Dieser Artikel führt Sie durch die Ausführung des Assistenten.

> [!IMPORTANT]
> Die vom Assistenten angewendeten Richtlinien erfüllen die Anforderungen der Mehrzahl Teams für Education Kunden. Der Assistent passt die globale (organisationsweite Standard)-Definition eines Kern-Richtliniensets mit Einstellungen an, die wir für die Sicherheit von Kursteilnehmern empfehlen, und wendet sie auf Schüler/Studierende an. Der Assistent erstellt und weist außerdem einen Satz benutzerdefinierter Richtlinien für Lehrkräfte und Mitarbeiter zu. Die Teams für Education Kunden müssen nach dem Ausführen dieses Assistenten keine anderen Richtlinienzuweisungsmethoden verwenden. Verwenden Sie andere Richtlinienzuweisungsmethoden *nur* , wenn Sie Richtlinien für Ihre Schüler/Studenten, Lehrkräfte und Mitarbeiter manuell erstellen und verwalten möchten.

## <a name="teams-for-education-policy-wizard"></a>Teams für Education-Richtlinien-Assistent

<a name="polwiz_intro"> </a>

Der Assistent wendet eine Reihe von grundlegenden Richtliniendefinitionen für Schüler/Studierende und einen separaten Satz von grundlegenden Richtliniendefinitionen für Lehrkräfte und Mitarbeiter an, mit Einstellungen, die jeweils geeignet sind. Dies geschieht, wenn Sie den Assistenten ausführen.

Der Assistent richtet Richtlinien basierend auf dem Bildungseinrichtungstyp (Primäre oder **Sekundäre** oder Höhere Bildungseinrichtung **) ein**. Sie wählen den Typ Ihrer Einrichtung aus, und der Assistent führt folgende Schritte aus:

- **Schüler**/Studenten: Der Assistent passt die globale Richtliniendefinition (organisationsweite Standardrichtlinie) für jeden vom Assistenten abgedeckten Richtlinienbereich mit neuen Standardeinstellungen an, die geeignet sind, um die Sicherheit Ihrer Schüler/Studierenden zu gewährleisten. Dadurch wird sichergestellt, dass Ihre aktuellen Und-Schüler/Studierenden die restriktivsten Richtlinien erhalten.
- **Lehrkräfte und Mitarbeiter**: Der Assistent erstellt einen Satz benutzerdefinierter Richtliniendefinitionen für jeden vom Assistenten abgedeckten Richtlinienbereich mit Einstellungen, die auf die Anforderungen von Lehrkräften und Mitarbeitern zugeschnitten sind. Anschließend werden der Gruppe von Lehrkräften und Mitarbeitern, die Sie auswählen, die Richtliniendefinitionen zugewiesen. Auf diese Weise erhalten Ihre Lehrkräfte und Mitarbeiter eine Reihe von Richtlinien, die ihnen einen Erfolg ermöglichen.

Sie müssen den Assistenten nur einmal ausführen. Neuen Kursteilnehmern werden automatisch die vom Assistenten angewendeten globalen Richtliniendefinitionen (Organisationsweit) zugewiesen, und neuen Mitarbeitern, die Sie der ausgewählten Gruppe hinzufügen, werden automatisch die benutzerdefinierten Richtlinien zugewiesen.

Außerdem wird bei jedem Hinzufügen eines neuen Features zu Teams der entsprechende EDU-relevante Standardwert der Richtlinie für dieses Feature automatisch zum globalen (organisationsweiten Standard) hinzugefügt, ohne dass ein Administratoreingriff erforderlich ist. Dadurch wird sichergestellt, dass die richtigen Richtlinien aktiv sind, um die Schüler sicher und engagiert zu halten.

> [!NOTE]
> Eine [detaillierte Liste der vom](#policies-applied-by-the-wizard) Assistenten angewendeten Richtliniendefinitionen finden Sie unter Vom Assistenten angewendete Richtlinien.

Los geht's!

## <a name="run-the-wizard"></a>Ausführen des Assistenten

<a name="polwiz_run"> </a>

Führen Sie zum Ausführen des Assistenten die folgenden Schritte aus.

1. Wenn Sie noch nicht mit Teams, wird der Assistent automatisch gestartet. Andernfalls können Sie den Assistenten jederzeit über das Dashboard starten. Navigieren Sie in der linken Navigationsleiste des Microsoft Teams Admin **Centers zu Start**, und wählen Sie dann auf der Kachel Einfaches Richtlinien-Setup für eine sichere Lernumgebung die Option **Schnelleinrichtung aus**.

    :::image type="content" source="media/easy-policy-setup-quick-setup.png" alt-text="Screenshot des Assistenten im Dashboard.":::

2. Wählen Sie den Typ Ihrer Bildungseinrichtung aus (**Primäre oder Sekundäre** oder Höhere Bildungseinrichtung **), und** wählen Sie dann Weiter **aus**.

    :::image type="content" source="media/easy-policy-setup-institution-type.png" alt-text="Screenshot der Seite im Assistenten zum Auswählen des Einrichtungstyps":::

3. Suchen Und wählen Sie Gruppen aus, die Ihre Lehrkräfte und Mitarbeiter enthalten, und wählen Sie dann Weiter **aus**. Wenn Sie noch keine Gruppen für Ihre Lehrkräfte und Mitarbeiter eingerichtet [haben, erstellen](/microsoft-365/admin/create-groups/create-groups) Sie eine Gruppe, und führen Sie den Assistenten dann erneut aus. <br/><br/>Sie können bis zu drei Gruppen auswählen. Lehrkräften und Mitarbeitern in den von Ihnen ausgewählten Gruppen wird eine Reihe von benutzerdefinierten Richtlinien zugewiesen, [die auf ihre](#policies-applied-by-the-wizard) Anforderungen zugeschnitten sind. Denken Sie daran, dass dieser Richtliniensatz von den Auf Schüler/Studenten angewendeten Richtlinien getrennt ist.

    :::image type="content" source="media/edu-policy-wizard-add-3-groups.png" alt-text="Screenshot der Seite im Assistenten zum Auswählen von Lehrer- und Mitarbeitergruppen":::

4. Überprüfen Sie Ihre Auswahl.

    :::image type="content" source="media/edu-policy-wizard-3-groups-review.png" alt-text="Screenshot der Seite im Assistenten zum Überprüfen der Auswahl":::

5. Wählen Sie **Übernehmen** aus, um die Änderungen anzuwenden. Der Vorgang kann einige Minuten dauern.<br/><br/>Die Definitionen der globalen (organisationsweiten Standard)-Richtlinie werden sofort auf Schüler/Studierende angewendet. Für Ihre Lehrkräfte und Mitarbeiter kann es je nach Größe der Gruppen einige Stunden dauern, bis die benutzerdefinierten Richtlinien jedem Mitglied der ausgewählten Gruppen zugewiesen wurden. Dies geschieht im Hintergrund, nachdem Sie diesen Schritt erfolgreich abgeschlossen haben.
6. Sie sind auf dem Weg, aber Sie sind noch nicht fertig! Es gibt ein paar weitere Dinge, die Sie berücksichtigen sollten. Schauen Sie sich als Nächstes die Schritte im Abschnitt Was [nach](#what-to-do-after-running-the-wizard) dem Ausführen des Assistenten zu tun ist in diesem Artikel an.

    :::image type="content" source="media/easy-policy-setup-on-way.png" alt-text="Screenshot der Seite im Assistenten für die nächsten Schritte.":::

## <a name="what-to-do-after-running-the-wizard"></a>Was nach dem Ausführen des Assistenten zu tun ist

<a name="polwiz_remove"> </a>

### <a name="step-1-remove-existing-policy-assignments-that-conflict-with-policies-applied-by-the-wizard"></a>Schritt 1: Entfernen vorhandener Richtlinienzuweisungen, die mit den vom Assistenten angewendeten Richtlinien in Konflikt stehen

> [!IMPORTANT]
> **Führen Sie diesen Schritt nur aus, wenn Sie Schülern/Studierenden, Lehrkräften und Mitarbeitern vorhandene Richtlinien zugewiesen haben, *bevor* Sie den Assistenten ausgeführt haben**. Wenn Sie noch nicht mit Teams und über keine anderen Richtlinien als die vom Assistenten erstellten Richtlinien verfügen, überspringen Sie dies, und fahren Sie mit Schritt 2 fort.

In Teams kann eine Richtlinie für einen bestimmten Richtlinienbereich auf folgende Weise auf einen Benutzer angewendet werden:

- Direkte Benutzerzuweisung
- Zuweisung an eine Gruppe, bei der der Benutzer Mitglied ist
- Wenn dem Benutzer eine Richtlinie nicht direkt zugewiesen wurde oder kein Mitglied einer Gruppe ist, der eine Richtlinie zugewiesen wurde, erhält der Benutzer automatisch die globale (organisationsweite Standard)-Richtlinie.

Wenn für einen Benutzer mehrere dieser Richtlinienzuweisungen vorhanden sind, ermittelt Teams, welche Richtlinienzuweisung wirksam wird. Weitere Informationen finden Sie unter Welche [Richtlinie Vorrang hat](policy-assignment-overview.md#which-policy-takes-precedence) oder [Rangfolgeregeln für Gruppen](assign-policies-users-and-groups.md#precedence-rules).

|Richtlinienzuweisungen eines Benutzers|Richtlinie, die wirksam wird |
|---------|---------|
|Einer Gruppe zugewiesene Richtlinie: Nein<br/>Richtlinie, die dem Benutzer direkt zugewiesen ist: Nein    |Globale (organisationsweite) Standardrichtlinie      |
|Einer Gruppe zugewiesene Richtlinie: Nein<br/>Richtlinie, die dem Benutzer direkt zugewiesen ist: Ja    |Richtlinie, die dem Benutzer direkt zugewiesen ist         |
|Einer Gruppe zugewiesene Richtlinie: Ja<br/>Richtlinie, die dem Benutzer direkt zugewiesen ist: Ja     |Richtlinie, die dem Benutzer direkt zugewiesen ist         |
|Einer Gruppe zugewiesene Richtlinie: Ja<br/>Richtlinie, die dem Benutzer direkt zugewiesen ist: Nein     |Einer Gruppe zugewiesene Richtlinie<br/><br/>Wenn der Benutzer ein Mitglied mehrerer Gruppen ist und jeder Gruppe eine Richtlinie desselben Richtlinienbereichs zugewiesen ist, tritt die Richtlinie mit der höchsten Gruppenzuordnungsrangfolge [in](assign-policies-users-and-groups.md#group-assignment-ranking) Kraft.       |

Aufgrund dieser Reihenfolge werden die vom Assistenten erstellten Richtlinien nicht wirksam, wenn ein Benutzer über vorhandene direkte Zuordnungen oder Gruppenzuweisungen verfügt. Dies bedeutet, dass Sie die vorhandenen Richtlinienzuweisungen vom Benutzer entfernen müssen, damit die vom Assistenten angewendete Richtlinie wirksam wird.

Gehen Sie [für jeden vom Assistenten angewendeten](#policies-applied-by-the-wizard) Richtlinienbereich wie folgt vor:

- Entfernen Sie alle vorhandenen direkten Zuordnungen und Gruppenzuweisungen von den Kursteilnehmern, damit die vom Assistenten angewendete globale (organisationsweite Standard)-Richtliniendefinition wirksam wird.
- Entfernen Sie alle widersprüchlichen direkten Zuweisungen für Ihre Lehrkräfte und Mitarbeiter, damit die vom Assistenten erstellte benutzerdefinierte Richtliniendefinition wirksam wird. Ermitteln Sie mithilfe der obigen Tabelle die Szenarien, die für Sie zu gelten haben. <br/><br/>Beachten Sie, dass der Assistent Ihren Lehrkräften und Mitarbeitergruppen Richtlinien zu weist, indem er [](assign-policies-users-and-groups.md#group-assignment-ranking) die Rangfolge "1" für Gruppenzuweisungen verwendet, die höchste Einstufung. Wenn Ihren Lehrkräften und Ihrer Mitarbeitergruppe eine Richtlinie im gleichen Richtlinienbereich zugewiesen ist, wird diese vorhandene Richtlinie in eine niedrigere Rangfolge verschoben, und die vom Assistenten zugewiesene Richtlinie wird wirksam.

[Hier finden Sie](batch-group-policy-assignment-edu.md#remove-a-policy-that-was-directly-assigned-to-users) weitere Informationen zum Entfernen von Richtlinien, die Benutzern direkt zugewiesen sind.

Beispielsweise haben Sie Lehrkräften eine Besprechungsrichtlinie direkt zugewiesen, und Ihre Schüler/Studenten verfügen über die globale (organisationsweite Standard)-Besprechungsrichtlinie. Entfernen Sie in diesem Szenario die Besprechungsrichtlinie, die Sie Lehrkräften direkt zugewiesen haben, damit die benutzerdefinierte Richtliniendefinition für die vom Assistenten erstellte Besprechungsrichtlinie wirksam wird. Sie müssen mit der vorhandenen globalen (organisationsweiten) Standard-Besprechungsrichtlinie für Schüler/Studierende nichts unternehmen, da keine anderen Besprechungsrichtlinien damit in Konflikt stehen.

<a name="polwiz_addmeasures"> </a>

### <a name="step-2-check-for-additional-measures-that-you-can-take-for-student-safety"></a>Schritt 2: Überprüfen auf zusätzliche Maßnahmen, die Sie für die Sicherheit der Schüler/Studierenden ergreifen können

Diese Richtlinien werden vom Assistenten automatisch [angepasst und angewendet](#policies-applied-by-the-wizard). Es gibt ein paar zusätzliche Maßnahmen, die Sie möglicherweise basierend auf den Anforderungen Ihrer Einrichtung ergreifen sollten, um ihre Sicherheit zu gewährleisten.

Weitere [Sicherheitsempfehlungen](https://support.microsoft.com/office/keeping-students-safe-while-using-teams-for-distance-learning-f00fa399-0473-4d31-ab72-644c137e11c8#ID0EBBAAA) finden Sie unter Teams Sicherheit bei der Nutzung von Fernunterricht.

<a name="polwiz_mc"> </a>

### <a name="step-3-check-message-center-for-policy-updates"></a>Schritt 3: Überprüfen des Nachrichtencenters auf Richtlinienupdates

Derzeit wendet der Assistent unsere empfohlenen Richtlinien an, wenn Sie ihn ausführen. Es ist wichtig zu wissen, dass, sobald neue Richtlinien in Teams verfügbar werden, die globalen (organisationsweiten) Einstellungen für die Sicherheit von Kursteilnehmern vom Assistenten automatisch aktualisiert werden.

Überprüfen Sie [das Nachrichtencenter](https://admin.microsoft.com/AdminPortal/Home?#/MessageCenter) (in der Microsoft 365 Admin Center) jedoch regelmäßig, um sich über die neuen Features und deren Richtlinien und Richtlinieneinstellungen in Teams.

## <a name="make-changes-in-the-wizard"></a>Änderungen im Assistenten vornehmen

<a name="polwiz_change"> </a>

Wenn Sie nach dem Ausführen des Assistenten Änderungen vornehmen müssen, können Sie ihn erneut ausführen und Ihre Auswahl ändern.

1. Navigieren Sie in der linken Navigationsleiste des Microsoft Teams **Admin Centers zu Start**, und wählen Sie dann in der Kachel  Einfaches Einrichten einer Richtlinie für eine sichere Lernumgebung die Option **Ändern aus**.
2. Fahren Sie von hier aus mit den einzelnen Seiten des Assistenten fort, um Ihre Änderungen vorzunehmen. Sie können den Typ Ihrer Einrichtung, die Gruppen von Lehrkräften und Mitarbeitern, denen Sie Richtlinien zuweisen möchten, oder beides ändern.

In der folgenden Tabelle ist zusammengefasst, was geschieht, wenn Sie im Assistenten eine Änderung ausführen.

|Änderungstyp  |Richtlinienverhalten  |
|---------|---------|
|Ändern des Typs der Bildungseinrichtung sowie der Lehrkräfte- und Mitarbeitergruppen    |<ul><li>**Schüler** und Studenten: Die globalen Richtliniendefinitionen (Organisationsweit standard), die auf dem neuen Bildungseinrichtungstyp basieren, werden auf Schüler/Studierende angewendet.</li><li>**Lehrkräfte und Mitarbeiter**: Eine Reihe von benutzerdefinierten Richtliniendefinitionen, die auf dem neuen Bildungseinrichtungstyp basieren, wird erstellt und den neuen Lehrkräfte- und Mitarbeitergruppen zugewiesen. Die vorherigen benutzerdefinierten Richtliniendefinitionen werden aus den vorherigen Lehrkräften und Mitarbeitergruppen entfernt.</li></ul>    |
|Nur den Typ der Bildungseinrichtung ändern    |<ul><li>**Schüler** und Studenten: Die globalen Richtliniendefinitionen (Organisationsweit standard), die auf dem neuen Bildungseinrichtungstyp basieren, werden auf Schüler/Studierende angewendet.</li><li>**Lehrkräfte und Mitarbeiter**: Eine Reihe benutzerdefinierter Richtliniendefinitionen, die auf dem neuen Bildungseinrichtungstyp basieren, wird erstellt und den Lehrkräften und Mitarbeitergruppen zugewiesen. Die für den vorherigen Bildungseinrichtungstyp erstellten benutzerdefinierten Richtliniendefinitionen werden aus den Lehrkräften und Mitarbeitergruppen entfernt.</li></ul>         |
|Ändern nur der Lehrkräfte und Mitarbeitergruppen   |<ul><li>**Schüler** und Studenten: Keine Änderung an den globalen (organisationsweiten) Standardrichtliniendefinitionen, die auf Schüler/Studierende angewendet werden.</li><li>**Lehrkräfte und Mitarbeiter**: Die benutzerdefinierten Richtliniendefinitionen werden den neuen Lehrkräften und Mitarbeitergruppen zugewiesen und aus den vorherigen Lehrkräften und Mitarbeitergruppen entfernt.</li></ul>         |

## <a name="policies-applied-by-the-wizard"></a>Vom Assistenten angewendete Richtlinien

<a name="polwiz_policies"> </a>

### <a name="policy-areas"></a>Richtlinienbereiche

Hier sehen Sie die Richtlinienbereiche und die entsprechenden Richtliniennamen, die vom Assistenten abgedeckt werden. Um diese Richtlinien zu finden, wechseln Sie zum Microsoft Teams Admin Center, und wechseln Sie dann im linken Navigationsbereich zu jeder Seite des Richtlinienbereichs.

#### <a name="students"></a>[**Schüler/Studenten**](#tab/students/)

|Richtlinienbereich  |Name der primären oder sekundären Richtlinie |Name der Richtlinie für höhere Bildungseinrichtungen  |
|---------|---------|---------|
|Teams-Richtlinie    |Global (Organisationsweit Standard)         |Global (Organisationsweit Standard)           |
|Besprechungsrichtlinie    |Global (Organisationsweit Standard)           |Global (Organisationsweit Standard)           |
|Richtlinie für Liveereignisse     |Global (Organisationsweit Standard)          |  Global (Organisationsweit Standard)          |
|App-Setuprichtlinie     |Global (Organisationsweit Standard)           |Global (Organisationsweit Standard)           |
|App-Berechtigungsrichtlinie    |Global (Organisationsweit Standard)           |Global (Organisationsweit Standard)           |
|Messagingrichtlinie     |Global (Organisationsweit Standard)           |Global (Organisationsweit Standard)           |
|Anrufrichtlinie    |Global (Organisationsweit Standard)           |Global (Organisationsweit Standard)           |

#### <a name="educators-and-staff"></a>[**Lehrkräfte und Mitarbeiter**](#tab/educators/)

|Richtlinienbereich  |Name der primären oder sekundären Richtlinie |Name der Richtlinie für höhere Bildungseinrichtungen |
|---------|---------|---------|
|Teams-Richtlinie   |Primäre oder sekundäre Lehrkräfte und Mitarbeiter – Teams         |Lehrkräfte und Mitarbeiter aus höheren Bildungseinrichtungen – Teams         |
|Besprechungsrichtlinie    |Primäre oder sekundäre Lehrkräfte und Mitarbeiter – Besprechung         |Dozenten und Mitarbeiter aus höheren Bildungseinrichtungen – Besprechung         |
|Richtlinie für Liveereignisse   | Primäre oder sekundäre Lehrkräfte und Mitarbeiter – Liveereignisse         |Dozenten und Mitarbeiter aus höheren Bildungseinrichtungen – Liveereignisse         |
|Messagingrichtlinie    |Primäre oder sekundäre Lehrkräfte und Mitarbeiter – Messaging         | Lehrkräfte und Mitarbeiter in höheren Bildungseinrichtungen – Messaging         |
|Anrufrichtlinie    |Primäre oder sekundäre Lehrkräfte und Mitarbeiter – Anrufe         |Lehrkräfte und Mitarbeiter aus höheren Bildungseinrichtungen – Anrufe         |

* * *

### <a name="policy-settings"></a>Richtlinieneinstellungen

Hier ist eine Zusammenfassung der Einstellungen, die vom Assistenten für jeden Richtlinienbereich angewendet werden.

#### <a name="students"></a>[**Schüler/Studenten**](#tab/student-settings/)

Hier ist eine Liste der globalen (organisationsweiten) Richtliniendefinitionen, die vom Assistenten angepasst und auf Schüler und Studenten angewendet wurden.

|Richtlinienbereich |Unterbereich  |Richtlinieneinstellung  |Primär oder Sekundär |Höhere Bildung |
|---------|---------|---------|---------|---------|
|Teams-Richtlinie   |         |Erstellen privater Kanäle         |Aus       |Ein|
|Besprechungsrichtlinie    |Allgemein         |Jetzt in Kanälen treffen         |Aus      |Ein|
|  |        |Outlook-Add-In         |Aus       |Ein|
|  |        |Planen von Kanal-Besprechungen        |Aus      |Ein|
|  |        |Private Besprechungsplanung       |Aus      |Ein|
|  |        |Besprechungsregistrierung              |Ein       |Ein|
|  |        |Wer kann registriert werden    |Jeder in der Organisation      |Jeder in der Organisation|
|  |Audio & Video        |Transkription        |Ein       |Ein|
|  |        |Cloudaufzeichnung         |Aus      |Ein|
|  |        |Modus für IP-Audio       |Ausgehendes und eingehendes Audio aktiviert        |Ausgehendes und eingehendes Audio aktiviert|
|  |        |Modus für IP-Video         |Ausgehendes und eingehendes Video aktiviert     |Ausgehendes und eingehendes Video aktiviert|
|  |       |IP-Video         |Ein         |Ein|
|  |       |NDI-Streaming zulassen         |Aus         |Aus|
|  |       |Media-Bitrate (KBs)         |50.000         |50.000|
|  |Inhaltsfreigabe       |Bildschirmfreigabemodus         |Gesamter Bildschirm         |Gesamter Bildschirm|
|  |       |Zulassen, dass ein Teilnehmer die Steuerung erteilt oder anfordert         |Ein         |Ein|
|  |       |Zulassen, dass ein externer Teilnehmer die Steuerung übergibt oder anfordert         |Ein         |Ein|
|  |       |PowerPoint Freigeben        |Ein         |Ein|
|  |       |Whiteboard         |Ein         |Ein|
|  |       |Freigegebene Notizen         |Ein        |Ein|
|  |Teilnehmer & Gäste       |Anonymen Personen das Starten einer Besprechung gestatten       |Aus         |Ein|
|  |       |Rollen mit  Presenterrechten in Besprechungen        |EveryoneUserOverride         |EveryoneUserOverride|
|  |       |Personen automatisch zulassen        |EveryoneInCompany|EveryoneInCompany|
|  |       |Einwahlbenutzern das Umgehen des Wartebereichs gestatten        |Aus         |Aus|
|  |       |Sofortbesprechungen in privaten Besprechungen        |Aus         |Ein|
|  |       |Liveuntertitel       |Deaktiviert, aber Benutzer können außer Kraft setzen         |Deaktiviert, aber Benutzer können außer Kraft setzen|
|  |       |Chatten in Besprechungen         |Ein         |Ein|
|Richtlinie für Liveereignisse  |       |Planen von Liveereignissen         |Aus         |Aus|
|  |       |Transkription für Teilnehmer          |Ein       |Ein|
|  |       |Wer an geplanten Liveereignissen teilnehmen kann        |Jeder in der Organisation        |Jeder in der Organisation|
|  |       |Wer können ein Ereignis aufzeichnen         |Immer         |Immer|
|Messagingrichtlinie  |       |Besitzer können gesendete Nachrichten löschen         |Aus|Ein|
|  |       |Gesendete Nachrichten löschen         |Aus         |Ein|
|  |       |Gesendete Nachrichten bearbeiten         |Aus         |Ein|
|  |       |Lesebestätigungen         |Vom Benutzer gesteuert         |Vom Benutzer gesteuert|
|  |       |Chat         |Aus         |Ein|
|  |       |Giphys in Unterhaltungen         |Aus         |Ein|
|  |       |Giphy-Inhaltsklassifikation         |Streng        |Streng|
|  |       |Memes in Unterhaltungen         |Ein         |Ein|
|  |       |Aufkleber in Unterhaltungen         |Ein         |Ein|
|  |       |URL-Vorschauen        |Ein         |Ein|
|  |       |Übersetzen von Nachrichten         |Ein         |Ein|
|  |       |Immersive Reader für Nachrichten        |Ein      |Ein|
|  |       |Dringende Nachrichten mittels Benachrichtigungen mit hoher Priorität senden  |Aus         |Ein|
|  |       |Erstellen von Sprachnachrichten         |In Chats und Kanälen zulässig         |In Chats und Kanälen zulässig|
|  |       |Auf Mobilgeräten bevorzugte Kanäle über aktuellen Chats anzeigen     |Aktiviert         |Aktiviert|
|  |       |Entfernen von Benutzern aus Gruppenchats         |Aus         |Ein|
|App-Berechtigungsrichtlinie  |       |Microsoft-Apps         |Blockieren bestimmter Apps und Zulassen, dass alle > Walkie-Talkie blockiert werden         |Alle Apps zulassen|
|  |       |Drittanbieter-Apps         |Alle Apps zulassen         |Alle Apps zulassen|
|  |       |Benutzerdefinierte Apps         |Alle Apps zulassen         |Alle Apps zulassen|
|App-Setuprichtlinie  |           |Hochladen von benutzerdefinierten Apps           |Aus         |Aus|
|  |       |Anheften durch Benutzer |Ein         |Ein|
|  |       |Installierte Apps         |Keine         |Keine|
|  |       |Angeheftete Apps         |Aktivität, Kalender, Teams         |Aktivität, Chats, Teams, Kalender, Anrufe, Datei
|Anrufrichtlinie  |       |Private Anrufe führen         |Aus        |Ein|
|  |       |Anruf weiterleiten und gleichzeitiges Klingeln an Personen in Ihrer Organisation         |Aus         |Ein|
|  |       |Anruf weiterleitung und gleichzeitiges Anrufen an externe Telefonnummern         |Aus         |Ein|
|  |       |Voicemail ist für eingehende Anrufe im Routing verfügbar.         |Vom Benutzer gesteuert         |Vom Benutzer gesteuert|
|  |       |Eingehende Anrufe können an Anrufgruppen geroutet werden         |Aus        |Ein|
|  |       |Delegierung für ein- und ausgehende Anrufe zulassen         |Aus         |Ein|
|  |       |Verhindern einer gebührenpflichtigen Umgehung und Senden von Anrufen über das PSTN        |Aus         |Aus|
|  |       |"Beschäftigt" ist während eines Anrufs verfügbar         |Aus         |Aus|
|  |       |Zulassen von Anrufen über das Festnetz (Web PSTN)         |Aus         |Ein|

#### <a name="educators-and-staff"></a>[**Lehrkräfte und Mitarbeiter**](#tab/educator-settings/)

Hier ist eine Liste der benutzerdefinierten Richtliniendefinitionen, die den Im Assistenten für Lehrkräfte und Mitarbeitergruppen zugewiesen wurden.  

|Richtlinienbereich |Unterbereich  |Richtlinieneinstellung  |Primär oder Sekundär |Höhere Bildung |
|---------|---------|---------|---------|---------|
|Teams-Richtlinie   |         |Erstellen privater Kanäle         |Ein       |Ein|
|Besprechungsrichtlinie    |Allgemein         |Jetzt in Kanälen treffen         |Ein      |Ein|
|  |        |Outlook-Add-In         |Ein       |Ein|
|  |        |Planen von Kanal-Besprechungen        |Ein      |Ein|
|  |        |Private Besprechungsplanung       |Ein      |Ein|
|  |        |Besprechungsregistrierung              |Ein       |Ein|
|  |        |Wer kann registriert werden    |Jeder in der Organisation      |Jeder in der Organisation|
|  |Audio & Video        |Transkription        |Ein       |Ein|
|  |        |Cloudaufzeichnung         |Ein      |Ein|
|  |        |Modus für IP-Audio       |Ausgehendes und eingehendes Audio aktiviert        |Ausgehendes und eingehendes Audio aktiviert|
|  |        |Modus für IP-Video         |Ausgehendes und eingehendes Video aktiviert     |Ausgehendes und eingehendes Video aktiviert|
|  |       |IP-Video         |Ein         |Ein|
|  |       |NDI-Streaming zulassen         |Aus         |Aus|
|  |       |Media-Bitrate (KBs)         |50.000         |50.000|
|  |Inhaltsfreigabe       |Bildschirmfreigabemodus         |Gesamter Bildschirm         |Gesamter Bildschirm|
|  |       |Zulassen, dass ein Teilnehmer die Steuerung erteilt oder anfordert         |Ein         |Ein|
|  |       |Zulassen, dass ein externer Teilnehmer die Steuerung übergibt oder anfordert         |Ein         |Ein|
|  |       |PowerPoint Freigeben        |Ein         |Ein|
|  |       |Whiteboard         |Ein         |Ein|
|  |       |Freigegebene Notizen         |Ein        |Ein|
|  |Teilnehmer & Gäste       |Anonymen Personen das Starten einer Besprechung gestatten       |Ein        |Ein|
|  |       |Rollen mit  Presenterrechten in Besprechungen        |OrganizerOnlyUserOverride         |OrganizerOnlyUserOverride|
|  |       |Personen automatisch zulassen        |OrganizerOnly|OrganizerOnly|
|  |       |Einwahlbenutzern das Umgehen des Wartebereichs gestatten        |Aus         |Aus|
|  |       |Sofortbesprechungen in privaten Besprechungen        |Ein         |Ein|
|  |       |Liveuntertitel       |Deaktiviert, aber Benutzer können außer Kraft setzen         |Deaktiviert, aber Benutzer können außer Kraft setzen|
|  |       |Chatten in Besprechungen         |Ein         |Ein|
|Richtlinie für Liveereignisse  |       |Planen von Liveereignissen         |Ein         |Ein|
|  |       |Transkription für Teilnehmer          |Ein       |Ein|
|  |       |Wer an geplanten Liveereignissen teilnehmen kann        |Jeder in der Organisation        |Jeder in der Organisation|
|  |       |Wer können ein Ereignis aufzeichnen         |Immer aufzeichnen         |Immer aufzeichnen|
|Messagingrichtlinie  |       |Besitzer können gesendete Nachrichten löschen         |Ein|Ein|
|  |       |Gesendete Nachrichten löschen         |Ein         |Ein|
|  |       |Gesendete Nachrichten bearbeiten         |Ein         |Ein|
|  |       |Lesebestätigungen         |Vom Benutzer gesteuert         |Vom Benutzer gesteuert|
|  |       |Chat         |Ein         |Ein
|  |       |Giphys in Unterhaltungen         |Ein        |Ein|
|  |       |Giphy-Inhaltsklassifikation         |Streng        |Streng|
|  |       |Memes in Unterhaltungen         |Ein         |Ein|
|  |       |Aufkleber in Unterhaltungen         |Ein         |Ein|
|  |       |URL-Vorschauen        |Ein         |Ein|
|  |       |Übersetzen von Nachrichten         |Ein         |Ein|
|  |       |Immersive Reader für Nachrichten        |Ein      |Ein|
|  |       |Dringende Nachrichten mittels Benachrichtigungen mit hoher Priorität senden  |Ein         |Ein|
|  |       |Erstellen von Sprachnachrichten         |In Chats und Kanälen zulässig         |In Chats und Kanälen zulässig|
|  |       |Auf Mobilgeräten bevorzugte Kanäle über aktuellen Chats anzeigen     |Aktiviert         |Aktiviert|
|  |       |Entfernen von Benutzern aus Gruppenchats         |Ein        |Ein|
|Anrufrichtlinie  |       |Private Anrufe führen         |Ein       |Ein|
|  |       |Anruf weiterleiten und gleichzeitiges Klingeln an Personen in Ihrer Organisation         |Ein        |Ein|
|  |       |Anruf weiterleitung und gleichzeitiges Anrufen an externe Telefonnummern         |Ein        |Ein|
|  |       |Voicemail ist für eingehende Anrufe im Routing verfügbar.         |Vom Benutzer gesteuert         |Vom Benutzer gesteuert|
|  |       |Eingehende Anrufe können an Anrufgruppen geroutet werden         |Ein        |Ein|
|  |       |Delegierung für ein- und ausgehende Anrufe zulassen         |Ein         |Ein|
|  |       |Verhindern einer gebührenpflichtigen Umgehung und Senden von Anrufen über das PSTN        |Aus         |Aus|
|  |       |"Beschäftigt" ist während eines Anrufs verfügbar         |Aus         |Aus|
|  |       |Zulassen von Anrufen über das Festnetz (Web PSTN)         |Ein      |Ein|

* * *

## <a name="related-topics"></a>Verwandte Themen

- [Teams-Richtlinien und Richtlinienpakete für Bildung](policy-packages-edu.md)
- [Zuweisen von Richtlinien zu großen Gruppen von Benutzern in Ihrer Schule](batch-group-policy-assignment-edu.md)
- [Sicherheit von Kursteilnehmern bei der Nutzung Teams für den Fernunterricht](https://support.microsoft.com/office/keeping-students-safe-while-using-teams-for-distance-learning-f00fa399-0473-4d31-ab72-644c137e11c8)
