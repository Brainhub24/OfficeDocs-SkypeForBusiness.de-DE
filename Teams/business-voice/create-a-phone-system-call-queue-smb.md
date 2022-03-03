---
title: Erstellen einer Anrufwarteschleife in Microsoft Teams Telefonsystem – Kleinunternehmen-Lernprogramm
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: dobro
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.callqueues.overview"
- Phone System
description: Erfahren Sie, wie Sie Anrufwarteschleifen für kleine und mittelständische Unternehmen in Microsoft Teams Telefonsystem.
ms.openlocfilehash: 8856d447d9197be4833d95fa6262bee1832b4b44
ms.sourcegitcommit: e86e3824c300c24e022d5cb1848338278a5a96a8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/03/2022
ms.locfileid: "63053074"
---
# <a name="create-a-call-queue---small-and-medium-business-tutorial"></a>Erstellen einer Anrufwarteschleife – Lernprogramm für kleine und mittelständische Unternehmen

Anrufwarteschleifen ermöglichen es, Anrufe an Personen in Ihrer Organisation weiterzuleiten, die bei einem bestimmten Problem oder einer bestimmten Frage helfen können. Die einzelnen Anrufe werden nach und nach an die Personen (sog. *Telefonberater*) in der Warteschleife verteilt.

Für Anrufwarteschleifen gibt es die folgenden Optionen:

- Eine Begrüßungsnachricht.

- Musik, während Anrufer in der Warteschleife warten.

- Weiterleitung der Anrufe *nach Eingang* an Telefonberater.

- Optionen für das Vorgehen bei überzähligen Anrufen und Erreichen des Zeitlimits.

## <a name="video-demonstration"></a>Videodemo

In diesem Video wird gezeigt, wie Sie eine Anrufwarteschleife in Microsoft Teams.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWCF23?autoplay=false]

## <a name="before-you-begin"></a>Bevor Sie beginnen

Holen Sie [sich Microsoft Teams Telefon Standard – Virtual User-Lizenzen](../teams-add-on-licensing/virtual-user.md), wenn Sie noch nicht über diese Lizenzen verfügen. Erhalten Sie einen Für jede Anrufwarteschleife und automatische Telefonhalter, die Sie einrichten möchten. Diese Lizenzen sind kostenlos, daher empfehlen wir, ein paar zusätzliche Lizenzen für den Fall zu erhalten, dass Sie später Änderungen an Ihrem Setup vornehmen.

Da telefonierende Mitarbeiter in einer Anrufwarteschleife möglicherweise anrufen, um einen Kundenanruf zurückzukehren, sollten Sie die Anrufer-ID für Ihre Anrufer auf Ihre Haupttelefonnummer oder die Nummer einer entsprechenden automatischen Telefon attendant festlegen. Weitere Informationen finden Sie unter [Verwalten von Anrufer-ID-Richtlinien in Microsoft Teams](../caller-id-policies.md).

<a name="steps"></a>

## <a name="follow-these-steps-to-set-up-your-call-queue"></a>Führen Sie die folgenden Schritte aus, um Ihre Anrufwarteschleife zu erstellen.

### <a name="step-1---create-a-team"></a>[Schritt 1– Erstellen eines Teams](#tab/create-team)

Beim Erstellen einer Anrufwarteschleife können Sie einzelne Benutzer zur Warteschlange hinzufügen, oder Sie können eine vorhandene Sicherheitsgruppe, Microsoft 365 Sicherheitsgruppe oder ein Microsoft Teams verwenden. Wir empfehlen [die Verwendung eines Teamkanals](https://support.microsoft.com/office/9f07dabe-91c6-4a9b-a545-8ffdddd2504e). Dies ermöglicht Mitgliedern der Warteschlange, miteinander zu chatten, Ideen auszutauschen und Dokumente oder andere Ressourcen zu erstellen, damit sie Ihren Kunden helfen können. Ein Team bietet außerdem ein Sprachpostfach, über das Anrufer eine Nachricht nach Stunden hinterlassen können oder wenn die Warteschlange ihre maximale Kapazität erreicht.

So erstellen Sie ein Team

1. Klicken Sie **zuerst Teams** linken Rand der App auf Die Liste und dann unten in der Teamliste auf Einem Team beitreten oder ein Team erstellen.

2. Klicken Sie dann **auf Team erstellen** (erste Karte, obere linke Ecke).

3. Wählen **Sie Team ganz neu erstellen aus**.

4. Wählen Sie als Nächstes aus, ob Sie ein öffentliches oder privates Team haben möchten. Wir empfehlen **Privat** für Ihre Anrufwarteschleife, um zu verhindern, dass Personen versehentlich der Warteschlange beitreten, indem sie dem Team beitreten.

5. Benennen Sie Ihr Team, und fügen Sie optional eine Beschreibung hinzu.

6. Wenn Sie fertig sind, klicken Sie auf **Erstellen**.

7. Geben Sie die Namen der Personen ein, die ihre Anrufwarteschleife enthalten soll, und klicken Sie dann auf **Hinzufügen**.

8. Klicken Sie auf **Schließen**. Personen, die Sie einem Team hinzufügen, erhalten eine E-Mail, in der sie informiert werden, dass sie jetzt Mitglied Ihres Teams sind, und das Team wird in der Teamliste angezeigt.

Als Nächstes fügen wir einen Kanal hinzu, der mit der Anrufwarteschleife verwendet werden kann.

So fügen Sie einen Kanal hinzu

1. Suchen Teams Team, das Sie gerade erstellt haben, klicken Sie auf **Weitere** Optionen (...), und klicken Sie dann auf **Kanal hinzufügen**.

2. Geben Sie einen Namen und eine Beschreibung für den Kanal ein.

3. Wählen **Sie unter** Datenschutz **die Option Standard – Barrierefrei** für alle Teammitglieder aus, und klicken Sie dann auf **Hinzufügen**.

> [!div class="nextstepaction"]
> [Schritt 2 – Ressourcenkonten >](/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?tabs=resource-account#steps)

### <a name="step-2---resource-accounts"></a>[Schritt 2 – Ressourcenkonten](#tab/resource-account)

Für jede von Ihnen erstellte Anrufwarteschleife ist ein Ressourcenkonto erforderlich. Dies ähnelt einem Benutzerkonto, mit dem Ausnahme, dass das Konto mit einer automatischen Telefonkonferenz oder einer Anrufwarteschleife statt mit einer Person verknüpft ist. In diesem Schritt erstellen wir das Konto, weisen ihm eine *Microsoft Teams Telefon Standard – Virtual User-Lizenz* zu und beginnen dann mit dem Erstellen der Anrufwarteschleife.

#### <a name="create-a-resource-account"></a>Erstellen eines Ressourcenkontos

Sie können ein Ressourcenkonto im Teams Admin Center erstellen.

1. Erweitern Sie Teams Admin Center Sprachanrufe **,** und klicken Sie dann auf **Ressourcenkonten**.

2. Klicken Sie auf **Hinzufügen**.

3. Geben Sie **im Bereich Ressourcenkonto hinzufügen** die Option Anzeigename **, Benutzername** **ein,** und  wählen Sie Anrufwarteschleife für den **Ressourcenkontotyp aus**. Agents sehen den Anzeigenamen, wenn sie einen eingehenden Anruf aus der Warteschlange erhalten.

4. Klicken Sie auf **Speichern**.

   Das neue Konto wird in der Liste der Konten angezeigt.

#### <a name="assign-a-license"></a>Lizenz zuweisen

Sie müssen dem *Ressourcenkonto Microsoft Teams Telefon Standard – Virtueller Benutzer* zuweisen.

1. Klicken Sie Microsoft 365 Admin Center der Liste **Aktive** Benutzer auf das Ressourcenkonto, dem Sie eine Lizenz zuweisen möchten.

2. Wählen Sie **auf der Registerkarte Lizenzen** und Apps unter **Lizenzen** Microsoft Teams Telefon **Standard – Virtueller Benutzer aus**.

3. Klicken Sie auf **Änderungen speichern**.

#### <a name="create-a-call-queue"></a>Erstellen einer Anrufwarteschleife

Als Nächstes erstellen wir eine neue Anrufwarteschleife und weisen das Ressourcenkonto zu.

1. Erweitern Sie Teams Admin Center Sprachanrufe **,** klicken Sie auf **Anrufwarteschleifen**, und klicken Sie dann auf **Hinzufügen**.

2. Geben Sie einen Namen für die Anrufwarteschleife ein.

3. Klicken Sie auf **Konten hinzufügen**, suchen Sie nach dem Ressourcenkonto, das Sie für diese Anrufwarteschleife verwenden möchten, klicken Sie auf **Hinzufügen** und dann nochmals auf **Hinzufügen**.

4. (Optional) Klicken **Sie unter Anruf-ID** **zuweisen auf Hinzufügen**, suchen Sie nach den Ressourcenkonten, die Sie für Ihre automatische Telefon attendant erstellt haben, klicken Sie auf **Hinzufügen, und** klicken Sie dann auf **Hinzufügen**. Dadurch erhalten die Telefonanrufer die Anrufer-ID Ihrer Hauptleitung, wenn sie anrufen.

5. Wählen Sie eine Sprache aus. Diese Sprache wird für vom System generierte Sprachansagen und Voicemailtranskripte verwendet (sofern Sie diese aktivieren).

6. Legen Sie fest, ob eine Begrüßung abgespielt werden soll, wenn Anrufer in der Warteschleife eintreffen. Die gewünschte Begrüßung muss in Form einer MP3-, WAV- oder WMA-Datei hochgeladen werden.

7. In Microsoft Teams wird für Anrufer in der Warteschleife Standardmusik wiedergegeben. Wenn Sie möchten, dass eine bestimmte Audiodatei wiedergegeben wird, klicken Sie auf **Audiodatei wiedergeben**, und laden Sie eine MP3-, WAV- oder WMA-Datei hoch.

   > [!NOTE]
   > Die hochgeladene Aufzeichnung darf nicht größer als 5 MB sein.
   > Für die in Microsoft Teams-Anrufwarteschleifen wiedergegebene Standardmusik muss Ihre Organisation keine Lizenzgebühren zahlen.

> [!div class="nextstepaction"]
> [Schritt 3 – Anrufen von Agents >](/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?tabs=call-agents#steps)

### <a name="step-3---call-agents"></a>[Schritt 3 – Anrufen von Telefonmitarbeitern](#tab/call-agents)

Um agents zur Anrufwarteschleife hinzuzufügen, fügen wir sie dem Team und Kanal hinzu, die wir zuvor erstellt haben. Sie müssen ein Mitglied des Teams sein, um dies zu tun.

1. Wählen Sie die **Option Team auswählen aus** , und klicken **Sie auf Kanal hinzufügen**.
2. Geben Sie den Namen des Teams ein, das Sie erstellt haben, wählen Sie es aus, und klicken Sie auf **Hinzufügen**.
3. Wählen Sie den Kanal aus, den Sie für die Warteschlange erstellt haben.
4. Klicken Sie auf **Anwenden**.

> [!NOTE]
> Wenn neue Benutzer zum Team hinzugefügt werden, kann es bis zu acht Stunden dauern, bis der erste Anruf eintrifft.

> [!div class="nextstepaction"]
> [Schritt 4 – Ressourcenkonten >](/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?tabs=call-routing#steps)

### <a name="step-4---call-routing"></a>[Schritt 4 – Anrufrouting](#tab/call-routing)

Wählen Sie die Anrufroutingmethode aus, die Sie verwenden möchten.

1. Legen **Sie Konferenzmodus auf** **Auto.**

2. Wählen Sie die **Routingmethode aus** , die Sie verwenden möchten. Dadurch wird die Reihenfolge bestimmt, in der Agents Anrufe aus der Warteschlange erhalten. Wir empfehlen **Serielles Routing** oder **Round-n- Und-So.** Wählen Sie eine der folgenden Optionen aus:

    - Bei der **Weiterleitung durch Telefonzentrale** werden alle Telefonberater in der Warteschleife gleichzeitig angerufen. Der Anruf wird dem ersten Telefonberater, der den Anruf annimmt, zugewiesen.

    - **Das serielle Routing** klingelt bei allen Telefonvertretern eins nach dem anderen. Wenn ein Telefonberater einen Anruf ablehnt oder nicht annimmt, wird der nächste auf der Liste angerufen usf., bis der Anruf angenommen wird oder das Zeitlimit in der Warteschleife erreicht hat.

    - Beim **Round Robin** werden die eingehenden Anrufe gleichmäßig verteilt, sodass jeder Telefonberater dieselbe Anzahl von Anrufen aus der Warteschleife erhält. Dies kann in einer Inbound-Vertriebsumgebung erwünscht sein, um für gleiche Chancen für alle Telefonberater zu sorgen.

    - Bei der Option **Längste Inaktivität** wird jeder Anruf an den am längsten inaktiven Telefonberater weitergeleitet. (Agents, deren **Anwesenheitsstatus für** mehr als 10 Minuten "Ab jetzt" war, sind nicht enthalten.)

3. Aktivieren **Sie Anwesenheitsbasiertes** Routing. Dadurch werden Anrufe an Agents weitervermittelt, deren Anwesenheitsstatus verfügbar **ist**.

4. Wählen Sie aus, ob Sie zulassen möchten, dass Telefonmitarbeiter Anrufe abmelden.

5. Legen Sie eine **Agent-Benachrichtigungszeit** fest, um anzugeben, wie lange das Telefon eines Agents klingelt, bevor die Warteschlange den Anruf an den nächsten Agent weiterleitelt.

> [!div class="nextstepaction"]
> [Schritt 5 – Anrufüberlauf >](/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?tabs=call-overflow#steps)

### <a name="step-5---call-overflow"></a>[Schritt 5 – Anrufüberlauf](#tab/call-overflow)

Wählen Sie aus, wie Anrufe zu behandeln sind, die den maximal zulässigen Wert in der Warteschlange überschreiten.

1. Legen Sie **die maximale Anzahl von Anrufen in der Warteschlange festgelegt**.

2. Wählen Sie aus, was Sie tun möchten, wenn die maximale Anzahl an Anrufen erreicht ist. Sie können den Anruf trennen oder umleiten. Wir empfehlen, den Anruf an eines der folgenden Ziele umzuleiten:
    - **Person in der Organisation** – Eine Person in Ihrer Organisation, die Sprachanrufe empfangen kann
    - **Sprach-App** – eine automatische Telefon attendant oder eine andere Anrufwarteschleife. (Wählen Sie das Ressourcenkonto aus, das der automatischen Telefon attendant oder der Anrufwarteschleife zugeordnet ist, wenn Sie dieses Ziel auswählen.)
    - **Externe Telefonnummer –** beliebige Telefonnummer. Verwenden Sie dieses Format: +[Landescode][Ortswahl][Telefonnummer]
    - **Voicemail** – Sie können das Sprachpostfach des von Ihnen erstellten Teams verwenden.

> [!div class="nextstepaction"]
> [Schritt 6 – Anruftimeout >](/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?tabs=call-timeout#steps)

### <a name="step-6---call-timeout"></a>[Schritt 6 – Anruftimeout](#tab/call-timeout)

Wählen Sie aus, was geschehen soll, wenn Anrufe zu lange in der Warteschleife warteten.

1. Legen Sie die **maximale Wartezeit ein**.

2. Wählen Sie aus, was Sie tun möchten, wenn ein Anruf ein Zeit raus ist. Sie können den Anruf trennen oder umleiten. Wir empfehlen, den Anruf an eines der folgenden Ziele umzuleiten:
    - **Person in der Organisation** – Eine Person in Ihrer Organisation, die Sprachanrufe empfangen kann
    - **Sprach-App** – eine automatische Telefon attendant oder eine andere Anrufwarteschleife. (Wählen Sie das Ressourcenkonto aus, das der automatischen Telefon attendant oder der Anrufwarteschleife zugeordnet ist, wenn Sie dieses Ziel auswählen.)
    - **Externe Telefonnummer –** beliebige Telefonnummer. Verwenden Sie dieses Format: +[Landescode][Ortswahl][Telefonnummer]
    - **Voicemail** – Sie können das Sprachpostfach des von Ihnen erstellten Teams verwenden.

3. Klicken Sie auf **Speichern**.

Damit wird die Einrichtung Ihrer Anrufwarteschleife abgeschlossen. Als Nächstes können Sie eine [automatische Attendant einrichten](set-up-auto-attendant.md).

---
