---
title: Erstellen oder Ändern einer VoIP-Richtlinie und Konfigurieren von PSTN-Verwendungsdatensätzen in Skype for Business
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: e6ff27e0-e2d1-4445-840f-08f738200c20
description: 'Zusammenfassung: Erstellen oder Ändern von VoIP-Richtlinien und Konfigurieren von PSTN-Verwendungsdatensätzen mithilfe der Skype for Business Server Systemsteuerung.'
ms.openlocfilehash: 5dedb504a6d2d3e75b168bf32ff1f0ccb7ed94f8
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60828378"
---
# <a name="create-or-modify-a-voice-policy-and-configure-pstn-usage-records-in-skype-for-business"></a>Erstellen oder Ändern einer VoIP-Richtlinie und Konfigurieren von PSTN-Verwendungsdatensätzen in Skype for Business

**Zusammenfassung:** Erstellen oder Ändern von VoIP-Richtlinien und Konfigurieren von PSTN-Verwendungsdatensätzen mithilfe der Skype for Business Server Systemsteuerung.

> [!NOTE]
> Jeder VoIP-Richtlinie muss mindestens ein PSTN-Verwendungseintrag (Public Switched Telephone Network) zugeordnet sein. Eine Liste aller PSTN-Verwendungsdatensätze, die in Ihrer Enterprise-VoIP-Bereitstellung verfügbar sind, und deren Eigenschaften finden Sie unter Anzeigen von [PSTN-Verwendungsdatensätzen in Skype for Business.](view-pstn-usage-records.md)

### <a name="to-create-a-voice-policy"></a>So erstellen Sie eine VoIP-Richtlinie

1. Öffnen Sie Skype for Business Server Systemsteuerung.

2. Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing** und dann auf **VoIP-Richtlinie**.

3. Klicken Sie auf der Seite **VoIP-Richtlinie** auf **Neu**, und wählen Sie einen Bereich für die neue Richtlinie:

   - Eine **Standortrichtlinie** wird auf einen gesamten Standort angewendet, ausgenommen auf Benutzer oder Gruppen, die einer Benutzerrichtlinie zugeordnet wurden. Wenn Sie eine Richtlinie auf Standortebene erstellen möchten, wählen Sie den gewünschten Standort im Dialogfeld **Standort auswählen**. Wenn bereits eine VoIP-Richtlinie für einen Standort erstellt wurde, wird der Standort nicht im Dialogfeld **Standort auswählen** angezeigt.

   - Eine **Benutzerrichtlinie** kann auf bestimmte Benutzer oder Gruppen angewendet werden.

4. Wenn Sie eine VoIP-Richtlinie auf Benutzerebene erstellen, geben Sie im Feld **Name** einen beschreibenden Namen für die Richtlinie ein.

    > [!NOTE]
    > Bei Erstellung einer VoIP-Richtlinie auf Standortebene wird das Feld **Name** unter **Neue VoIP-Richtlinie** mit dem Standortnamen vorausgefüllt und kann nicht geändert werden.

5. (Optional) Geben Sie zusätzliche beschreibende Informationen zur VoIP-Richtlinie ein.

6. Aktivieren oder deaktivieren Sie die folgenden Kontrollkästchen, um die **Anruffunktionen** für diese VoIP-Richtlinie zu aktivieren oder zu deaktivieren:

   - **Voicemail-Escape** verhindert, dass Anrufe sofort an das Voicemailsystem des Mobiltelefons des Benutzers weitergeleitet werden, wenn gleichzeitiges Klingeln konfiguriert ist und das Telefon ausgeschaltet, nicht genügend Akku oder außerhalb der Reichweite ist.

     > [!NOTE]
     > Dieses Feature kann nur über die Skype for Business Server-Verwaltungsshell konfiguriert werden.

   - **Anrufweiterleitung** ermöglicht Benutzern das Weiterleiten von Anrufen an andere Telefone und Clientgeräte. Skype for Business Server bietet eine deutlich größere Palette von Konfigurationsoptionen für die Anrufweiterleitung. Wenn beispielsweise eine Organisation nicht möchte, dass eingehende Anrufe extern an das PSTN weitergeleitet werden, kann ein Administrator eine spezielle VoIP-Richtlinie geltend machen, um diese Einschränkung bereitzustellen. Diese Option ist standardmäßig aktiviert.

   - **Delegierung** ermöglicht Benutzern die Angabe anderer Benutzer, die in ihrem Namen Anrufe tätigen und empfangen können. In Skype for Business Server kann ein Delegat das gleichzeitige Klingeln konfigurieren, sodass eingehende Anrufe an seinen Vorgesetzten alle Ziele für das gleichzeitige Klingeln der Stellvertretung anrufen können. Auf diese Weise kann der Stellvertreter flexibler auf die für seinen Manager bestimmten Anrufe reagieren. Diese Option ist standardmäßig aktiviert.

   - **Anrufdurchstellung** ermöglicht es, Anrufe an andere Benutzer durchzustellen. Diese Option ist standardmäßig aktiviert.

   - **Anruf parken** ermöglicht es Benutzern, Anrufe in der Warteschleife zu parken und den Anruf von einem anderen Telefon oder Client aus wiederaufzunehmen. Diese Option ist standardmäßig deaktiviert.

   - **Gleichzeitiges Klingeln** ermöglicht bei eingehenden Anrufen das gleichzeitige Klingeln auf zusätzlichen Telefonen (z. B. einem Mobiltelefon) oder anderen Endpunktgeräten. Skype for Business Server bietet eine deutlich größere Palette von Konfigurationsoptionen für gleichzeitiges Klingeln. Diese Option ist standardmäßig aktiviert.

   - **Teamanruf** ermöglicht Benutzern in einem definierten Team die Annahme von Anrufen für andere Teammitglieder. Diese Option ist standardmäßig aktiviert.

   - **Die PSTN-Umleitung** ermöglicht das Umleiten von Anrufen von Benutzern, denen diese Richtlinie zugewiesen ist, an andere Unternehmensbenutzer im PSTN, wenn das WAN überlastet oder nicht verfügbar ist. Diese Option ist standardmäßig aktiviert.

   - **Außerkraftsetzung der Bandbreitenrichtlinie** ermöglicht es Administratoren, Richtlinienentscheidungen im Rahmen der Anrufsteuerung für einen bestimmten Benutzer außer Kraft zu setzen. Diese Option ist standardmäßig deaktiviert.

     > [!NOTE]
     > Die Richtlinie wird nur für eingehende Anrufe an den Benutzer, nicht jedoch für ausgehende Anrufe außer Kraft gesetzt, die vom Benutzer getätigt werden. Nachdem die Sitzung hergestellt wurde, wird die Bandbreitenauslastung genau aufgezeichnet. Diese Einstellung sollte sparsam verwendet und für angemessene Entscheidungen der Anrufsteuerung reserviert werden.

   - **Mithilfe** der Clientbenutzeroberfläche, die wiederum die Aufrufe in den Kommunikationsdatensätzen (KDS) kennzeichnet, können Benutzer bösartige Anrufe (z. B. Bedrohungen) melden. Diese ist standardmäßig deaktiviert.

   - **Beschäftigt-Optionen** aktivieren oder deaktivieren Beschäftigt-Optionen für die angegebene VoIP-Richtlinie. Mit den Beschäftigt-Optionen können eingehende Anrufe an Voicemail weitergeleitet oder mit einem Besetztsignal abgelehnt werden, wenn sich der Zielbenutzer des Anrufs auf dem Telefon befindet. Beschäftigt-Optionen ist eine neue VoIP-Richtlinie, die im kumulativen Update vom Juli 2016 eingeführt wurde. Wenn Sie diesen Parameter aktivieren, werden beschäftigt-Optionen aktiviert, und wenn Sie ihn deaktivieren, werden die Beschäftigt-Optionen deaktiviert. Weitere Informationen finden Sie unter [Plan for Busy Options for Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/busy-options.md) and Install and configure Busy Options for [Skype for Business Server](install-and-configure-busy-options.md).

7. Führen Sie eine der folgenden Aktionen aus, um PSTN-Verwendungsdatensätze für diese VoIP-Richtlinie zuzuordnen und zu konfigurieren:

   - Klicken Sie auf **Auswählen**, um einen oder mehrere Datensätze aus einer Liste aller PSTN-Verwendungsdatensätze auszuwählen, die für Ihre Enterprise-VoIP-Bereitstellung zur Verfügung stehen. Markieren Sie die Datensätze, die Sie dieser VoIP-Richtlinie zuordnen möchten, und klicken Sie anschließend auf **OK**.

   - Markieren Sie einen Datensatz, und klicken Sie auf **Entfernen**, um einen PSTN-Verwendungsdatensatz aus der VoIP-Richtlinie zu entfernen.

   - Führen Sie die folgenden Schritte aus, um einen neuen PSTN-Verwendungsdatensatz zu definieren und dieser VoIP-Richtlinie zuzuordnen:

     a. Klicken Sie auf **Neu**.

     b. Geben Sie im Feld **Name** einen eindeutigen beschreibenden Namen für den Datensatz ein. Sie können z. B. einen PSTN-Verwendungseintrag namens "Redmond" für Vollzeitmitarbeiter in Redmond und einen weiteren namens "RedmondTemps" für Zeitarbeiter erstellen.

     > [!NOTE]
     > Der Name des PSTN-Verwendungsdatensatzes muss innerhalb der Enterprise-VoIP-Bereitstellung eindeutig sein. Nach dem Speichern des Datensatzes kann das Feld **Name** nicht mehr bearbeitet werden.

     c. Verwenden Sie eine der folgenden Methoden, um Routen für diesen PSTN-Datensatz zuzuordnen und zu konfigurieren:

   - Klicken Sie auf **Auswählen**, markieren Sie in der Liste der verfügbaren Routen in Ihrer Enterprise-VoIP-Bereitstellung eine oder mehrere gewünschte Routen, und klicken Sie dann auf **OK**.

   - Zum Entfernen einer Route aus dem PSTN-Verwendungseintrag markieren Sie die Route, und klicken Sie auf **Entfernen**.

   - Klicken Sie auf **Neu**, um eine neue Route zu definieren und sie diesem PSTN-Verwendungseintrag zuzuordnen. Ausführliche Informationen finden Sie unter [Erstellen oder Ändern einer VoIP-Route in Skype for Business.](create-or-modify-a-voice-route.md)

   - Markieren Sie die Route, und klicken Sie auf **Details anzeigen**, um eine Route zu bearbeiten, die diesem PSTN-Verwendungsdatensatz bereits zugeordnet wurde.

     d. Klicken Sie auf **OK**.

   - Führen Sie die folgenden Schritte aus, um einen PSTN-Verwendungsdatensatz zu bearbeiten, der bereits dieser VoIP-Richtlinie zugeordnet ist:

     a. Markieren Sie den PSTN-Verwendungseintrag, den Sie bearbeiten möchten, und klicken Sie auf **Details einblenden**.

     b. Verwenden Sie eine der folgenden Methoden, um Routen für diesen PSTN-Datensatz zuzuordnen und zu konfigurieren:

   - Klicken Sie auf **Auswählen**, markieren Sie in der Liste der verfügbaren Routen in Ihrer Enterprise-VoIP-Bereitstellung eine oder mehrere gewünschte Routen, und klicken Sie dann auf **OK**.

   - Zum Entfernen einer Route aus diesem PSTN-Verwendungseintrag markieren Sie die Route, und klicken Sie auf **Entfernen**.

   - Klicken Sie auf **Neu**, um eine neue Route zu definieren und sie diesem PSTN-Verwendungseintrag zuzuordnen. Ausführliche Informationen finden Sie unter [Erstellen oder Ändern einer VoIP-Route in Skype for Business.](create-or-modify-a-voice-route.md)

   - Markieren Sie die Route, und klicken Sie auf **Details einblenden**, um eine Route zu bearbeiten, die diesem PSTN-Verwendungseintrag bereits zugeordnet wurde.

     c. Klicken Sie auf **OK**.

8. Ordnen Sie die PSTN-Verwendungseinträge zur Erzielung optimaler Leistung an. Um die Position eines Datensatzes in der Liste zu ändern, markieren Sie den Datensatznamen, und klicken Sie auf den Pfeil nach oben oder unten.

    > [!IMPORTANT]
    > Die Reihenfolge, in der PSTN-Verwendungsdatensätze in der VoIP-Richtlinie aufgeführt sind, ist von Bedeutung. Skype for Business Server durchläuft die Liste von oben nach unten. Es wird empfohlen, die Liste nach Verwendungshäufigkeit zu organisieren, z. B.: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.

9. Führen Sie eine der folgenden Aktionen aus, um PSTN-Verwendungsdatensätze für die Anrufweiterleitung und gleichzeitiges Klingeln in dieser VoIP-Richtlinie zuzuordnen und zu konfigurieren:

   - Um dieselben PSTN-Verwendungsdatensätze für die Anrufweiterleitung und gleichzeitiges Klingeln zu verwenden wie diese VoIP-Richtlinie, wählen Sie die Option **Mithilfe der gleichen PSTN-Verwendungen weiterleiten** im Dropdownmenü aus.

   - Um die Anrufweiterleitung und das gleichzeitige Klingeln nur für interne Skype for Business Benutzer zuzulassen, wählen Sie im Dropdownmenü die Option **"An interne Skype for Business Benutzer** weiterleiten" aus. Anrufe werden nicht an externe PSTN-Nummern weitergeleitet.

   - Um andere PSTN-Verwendungseinträge für die Anrufweiterleitung und für das gleichzeitige Klingeln wie für diese VoIP-Richtlinie anzugeben, wählen Sie aus dem Dropdownmenü die Option **Mithilfe benutzerdefinierter PSTN-Verwendung weiterleiten** aus. Mit dieser Option wird ein Steuerelement angezeigt, um vorhandene PSTN-Verwendungseinträge auszuwählen oder um neue PSTN-Verwendungseinträge speziell für die Anrufweiterleitung und für das gleichzeitige Klingeln zu erstellen.

   - Klicken Sie auf **Auswählen**, um einen oder mehrere Einträge aus einer Liste von PSTN-Verwendungseinträgen für die Anrufweiterleitung und das gleichzeitige Klingeln auszuwählen. Markieren Sie die Einträge, die Sie dieser Richtlinie für die Anrufweiterleitung und das gleichzeitige Klingeln zuordnen möchten, und klicken Sie anschließend auf **OK**.

   - Markieren Sie einen Datensatz, und klicken Sie auf **Entfernen**, um einen PSTN-Verwendungsdatensatz aus dieser Richtlinie für die Anrufweiterleitung und gleichzeitiges Klingeln zu entfernen.

   - Führen Sie die folgenden Schritte aus, um einen neuen PSTN-Verwendungsdatensatz zu definieren und dieser Richtlinie für die Anrufweiterleitung und gleichzeitiges Klingeln zuzuordnen:

     a. Klicken Sie auf **Neu**.

     b. Geben Sie im Feld **Name** einen eindeutigen beschreibenden Namen für den Datensatz ein.

     > [!NOTE]
     > Der Name des PSTN-Verwendungsdatensatzes muss innerhalb der Enterprise-VoIP-Bereitstellung eindeutig sein. Nach dem Speichern des Datensatzes kann das Feld **Name** nicht mehr bearbeitet werden.

     c. Verwenden Sie eine der folgenden Methoden, um Routen für diesen PSTN-Datensatz zuzuordnen und zu konfigurieren:

   - Klicken Sie auf **Auswählen**, markieren Sie in der Liste der verfügbaren Routen in Ihrer Enterprise-VoIP-Bereitstellung eine oder mehrere gewünschte Routen, und klicken Sie dann auf **OK**.

   - Zum Entfernen einer Route aus dem PSTN-Verwendungsdatensatz markieren Sie die Route, und klicken Sie auf **Entfernen**.

   - Klicken Sie auf **Neu**, um eine neue Route zu definieren und sie diesem PSTN-Verwendungsdatensatz zuzuordnen. Ausführliche Informationen finden Sie unter [Erstellen oder Ändern einer VoIP-Route in Skype for Business.](create-or-modify-a-voice-route.md)

   - Markieren Sie die Route, und klicken Sie auf **Details anzeigen**, um eine Route zu bearbeiten, die diesem PSTN-Verwendungsdatensatz bereits zugeordnet wurde.

     d. Klicken Sie auf **OK**.

   - Führen Sie die folgenden Schritte aus, um einen PSTN-Verwendungsdatensatz zu bearbeiten, der bereits dieser VoIP-Richtlinie zugeordnet ist:

     a. Markieren Sie den PSTN-Verwendungseintrag, den Sie bearbeiten möchten, und klicken Sie auf **Details einblenden**.

     b. Verwenden Sie eine der folgenden Methoden, um Routen für diesen PSTN-Datensatz zuzuordnen und zu konfigurieren:

   - Klicken Sie auf **Auswählen**, markieren Sie in der Liste der verfügbaren Routen in Ihrer Enterprise-VoIP-Bereitstellung eine oder mehrere gewünschte Routen, und klicken Sie dann auf **OK**.

   - Zum Entfernen einer Route aus diesem PSTN-Verwendungsdatensatz markieren Sie die Route, und klicken Sie auf **Entfernen**.

   - Klicken Sie auf **Neu**, um eine neue Route zu definieren und sie diesem PSTN-Verwendungsdatensatz zuzuordnen. Ausführliche Informationen finden Sie unter [Erstellen oder Ändern einer VoIP-Route in Skype for Business.](create-or-modify-a-voice-route.md)

   - Markieren Sie die Route, und klicken Sie auf **Details anzeigen**, um eine Route zu bearbeiten, die diesem PSTN-Verwendungsdatensatz bereits zugeordnet wurde.

     c. Klicken Sie auf **OK**.

10. (Optional) Geben Sie eine Nummer zum Testen der VoIP-Richtlinie ein, und klicken Sie auf **Los**. Die Testergebnisse werden unter **Übersetzte Nummer für Test** angezeigt.

11. Klicken Sie auf **OK**.

12. Klicken Sie auf der Seite **VoIP-Richtlinie** auf **Commit**, und klicken Sie anschließend auf **Commit für alle**.

    > [!NOTE]
    > Jedes Mal, wenn Sie eine VoIP-Richtlinie erstellen oder ändern, müssen Sie den Befehl **Commit für alle Elemente ausführen** ausführen, um die Konfigurationsänderung zu veröffentlichen. Ausführliche Informationen finden Sie unter [Veröffentlichen ausstehender Änderungen an der VoIP-Routingkonfiguration in Skype for Business](voice-route-config-changes.md) in der Betriebsdokumentation.

13. (Optional) Voicemail Escape erkennt, dass ein Anruf sofort von der Voicemail des Mobiltelefons des Benutzers angenommen wurde, und trennt den Anruf mit der Voicemail des Mobiltelefons. Dadurch kann der Anruf weiterhin an den anderen Endpunkten des Benutzers klingeln, sodass der Benutzer den Anruf annehmen kann. Ausführliche Informationen zum Konfigurieren einer Voicemailrichtlinie finden Sie unter [Konfigurieren von Voicemail escape in Skype for Business](configure-voice-mail-escape.md).

### <a name="to-modify-a-voice-policy"></a>So ändern Sie eine VoIP-Richtlinie

1. Öffnen Sie Skype for Business Server Systemsteuerung.

2. Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing** und anschließend auf **VoIP-Richtlinie**.

3. Doppelklicken Sie auf der Seite **VoIP-Richtlinie** auf den Namen einer VoIP-Richtlinie.

    > [!NOTE]
    > Der Bereich und der Name wurden bei Erstellung der VoIP-Richtlinie festgelegt. Sie können nicht geändert werden.

4. (Optional) Geben Sie in **VoIP-Richtlinie bearbeiten** zusätzliche Informationen zur Beschreibung der VoIP-Richtlinie ein.

5. Aktivieren oder deaktivieren Sie die folgenden Kontrollkästchen, um die einzelnen **Anruffunktionen** zu aktivieren bzw. zu deaktivieren:

   - **Voicemail-Escape** verhindert, dass Anrufe sofort an das Voicemailsystem des Mobiltelefons des Benutzers weitergeleitet werden, wenn gleichzeitiges Klingeln konfiguriert ist und das Telefon ausgeschaltet, nicht genügend Akku oder außerhalb der Reichweite ist.

     > [!NOTE]
     > Dieses Feature kann nur über die Skype for Business Server-Verwaltungsshell konfiguriert werden.

   - **Anrufweiterleitung** ermöglicht Benutzern das Weiterleiten von Anrufen an andere Telefone und Clientgeräte. Skype for Business Server bietet eine deutlich größere Palette von Konfigurationsoptionen für die Anrufweiterleitung. Wenn beispielsweise eine Organisation nicht möchte, dass eingehende Anrufe extern an das PSTN weitergeleitet werden, kann ein Administrator eine spezielle VoIP-Richtlinie geltend machen, um diese Einschränkung bereitzustellen. Diese Option ist standardmäßig aktiviert.

   - **Delegierung** ermöglicht Benutzern die Angabe anderer Benutzer, die in ihrem Namen Anrufe tätigen und empfangen können. In Skype for Business Server kann ein Delegat das gleichzeitige Klingeln konfigurieren, sodass eingehende Anrufe an seinen Vorgesetzten alle Ziele für das gleichzeitige Klingeln der Stellvertretung anrufen können. Auf diese Weise kann der Stellvertreter flexibler auf die für seinen Manager bestimmten Anrufe reagieren. Diese Option ist standardmäßig aktiviert.

   - **Anrufdurchstellung** ermöglicht es, Anrufe an andere Benutzer durchzustellen. Diese Option ist standardmäßig aktiviert.

   - **Anruf parken** ermöglicht es Benutzern, Anrufe in der Warteschleife zu parken und den Anruf anschließend von einem anderen Telefon oder Client aus wiederaufzunehmen. Diese Option ist standardmäßig deaktiviert.

   - **Gleichzeitiges Klingeln** ermöglicht bei eingehenden Anrufen das gleichzeitige Klingeln auf zusätzlichen Telefonen (z. B. einem Mobiltelefon) oder anderen Endpunktgeräten. Skype for Business Server bietet eine deutlich größere Palette von Konfigurationsoptionen für gleichzeitiges Klingeln. Diese Option ist standardmäßig aktiviert.

   - **Teamanruf** ermöglicht Benutzern in einem definierten Team die Annahme von Anrufen für andere Teammitglieder. Diese Option ist standardmäßig aktiviert.

   - **Die PSTN-Umleitung** ermöglicht das Umleiten von Anrufen von Benutzern, denen diese Richtlinie zugewiesen ist, an andere Unternehmensbenutzer im PSTN, wenn das WAN überlastet oder nicht verfügbar ist. Diese Option ist standardmäßig aktiviert.

   - **Die Außerkraftsetzung von Bandbreitenrichtlinien** ermöglicht Administratoren das Außerkraftsetzen von Cac-Richtlinienentscheidungen für einen bestimmten Benutzer. Diese Option ist standardmäßig deaktiviert.

     > [!NOTE]
     > Die Richtlinie wird nur für eingehende Anrufe an den Benutzer, nicht jedoch für ausgehende Anrufe außer Kraft gesetzt, die vom Benutzer getätigt werden. Nachdem die Sitzung hergestellt wurde, wird die Bandbreitenauslastung genau aufgezeichnet. Diese Einstellung sollte sparsam verwendet werden.

   - **Die Nachverfolgung bösartiger Anrufe** ermöglicht Es Benutzern, bösartige Anrufe (z. B. Bedrohungen) über die Clientbenutzeroberfläche zu melden, die wiederum die Anrufe in den KDS kennzeichnet. Diese Option ist standardmäßig deaktiviert.

6. Führen Sie eine der folgenden Aktionen aus, um PSTN-Verwendungsdatensätze für diese VoIP-Richtlinie zuzuordnen und zu konfigurieren:

   - Klicken Sie auf **Auswählen**, um einen oder mehrere Datensätze aus einer Liste aller PSTN-Verwendungsdatensätze auszuwählen, die für Ihre Enterprise-VoIP-Bereitstellung zur Verfügung stehen. Markieren Sie die Datensätze, die Sie dieser VoIP-Richtlinie zuordnen möchten, und klicken Sie anschließend auf **OK**.

   - Markieren Sie einen Datensatz, und klicken Sie auf **Entfernen**, um einen PSTN-Verwendungsdatensatz aus der VoIP-Richtlinie zu entfernen.

   - Führen Sie die folgenden Schritte aus, um einen neuen PSTN-Verwendungsdatensatz zu definieren und dieser VoIP-Richtlinie zuzuordnen:

     a. Klicken Sie auf **Neu**.

     b. Geben Sie im Feld **Name** einen eindeutigen beschreibenden Namen für den Datensatz ein. Sie können z. B. einen PSTN-Verwendungsdatensatz namens "Redmond" für Vollzeitmitarbeiter in Redmond und einen anderen Datensatz namens "RedmondTemps" für Zeitarbeiter erstellen.

     > [!NOTE]
     > Der Name des PSTN-Verwendungsdatensatzes muss innerhalb der Enterprise-VoIP-Bereitstellung eindeutig sein. Nach dem Speichern des Datensatzes kann das Feld **Name** nicht mehr bearbeitet werden.

     c. Verwenden Sie eine der folgenden Methoden, um Routen für diesen PSTN-Datensatz zuzuordnen und zu konfigurieren:

   - Klicken Sie auf **Auswählen**, markieren Sie in der Liste der verfügbaren Routen in Ihrer Enterprise-VoIP-Bereitstellung eine oder mehrere gewünschte Routen, und klicken Sie dann auf **OK**.

   - Zum Entfernen einer Route aus dem PSTN-Verwendungsdatensatz markieren Sie die Route, und klicken Sie auf **Entfernen**.

   - Klicken Sie auf **Neu**, um eine neue Route zu definieren und sie diesem PSTN-Verwendungsdatensatz zuzuordnen. Ausführliche Informationen finden Sie unter [Erstellen oder Ändern einer VoIP-Route in Skype for Business.](create-or-modify-a-voice-route.md)

   - Markieren Sie die Route, und klicken Sie auf **Details anzeigen**, um eine Route zu bearbeiten, die diesem PSTN-Verwendungsdatensatz bereits zugeordnet wurde.

     d. Klicken Sie auf **OK**.

   - Führen Sie die folgenden Schritte aus, um einen PSTN-Verwendungsdatensatz zu bearbeiten, der bereits dieser VoIP-Richtlinie zugeordnet ist:

     a. Markieren Sie den PSTN-Verwendungsdatensatz, den Sie bearbeiten möchten, und klicken Sie auf **Details anzeigen**.

     b. Verwenden Sie eine der folgenden Methoden, um Routen für diesen PSTN-Datensatz zuzuordnen und zu konfigurieren:

   - Klicken Sie auf **Auswählen**, markieren Sie in der Liste der verfügbaren Routen in Ihrer Enterprise-VoIP-Bereitstellung eine oder mehrere gewünschte Routen, und klicken Sie dann auf **OK**.

   - Zum Entfernen einer Route aus diesem PSTN-Verwendungsdatensatz markieren Sie die Route, und klicken Sie auf **Entfernen**.

   - Klicken Sie auf **Neu**, um eine neue Route zu definieren und sie diesem PSTN-Verwendungsdatensatz zuzuordnen. Ausführliche Informationen finden Sie unter [Erstellen oder Ändern einer VoIP-Route in Skype for Business.](create-or-modify-a-voice-route.md)

   - Markieren Sie die Route, und klicken Sie auf **Details anzeigen**, um eine Route zu bearbeiten, die diesem PSTN-Verwendungsdatensatz bereits zugeordnet wurde.

     c. Klicken Sie auf **OK**.

7. Ordnen Sie die PSTN-Verwendungseinträge zur Erzielung optimaler Leistung an. Um die Position eines Datensatzes in der Liste zu ändern, markieren Sie den Datensatznamen, und klicken Sie auf den Pfeil nach oben oder unten.

    > [!NOTE]
    > Die Reihenfolge, in der PSTN-Verwendungsdatensätze in der VoIP-Richtlinie aufgeführt sind, ist von Bedeutung. Skype for Business Server durchläuft die Liste von oben nach unten. Es wird empfohlen, die Liste nach Verwendungshäufigkeit zu organisieren, z. B.: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.

8. Führen Sie eine der folgenden Aktionen aus, um PSTN-Verwendungsdatensätze für die Anrufweiterleitung und gleichzeitiges Klingeln in dieser VoIP-Richtlinie zuzuordnen und zu konfigurieren:

   - Um dieselben PSTN-Verwendungsdatensätze für die Anrufweiterleitung und gleichzeitiges Klingeln zu verwenden wie diese VoIP-Richtlinie, wählen Sie die Option **Mithilfe der gleichen PSTN-Verwendungen weiterleiten** im Dropdownmenü aus.

   - Um die Anrufweiterleitung und das gleichzeitige Klingeln nur für interne Skype for Business Benutzer zuzulassen, wählen Sie nur im Dropdownmenü die Option **"An interne Skype for Business Benutzer** weiterleiten" aus. Die Anrufe werden dann nicht an externe PSTN-Nummern weitergeleitet.

   - Um andere PSTN-Verwendungsdatensätze für die Anrufweiterleitung und gleichzeitiges Klingeln zu verwenden, als die für diese VoIP-Richtlinie verwendeten, wählen Sie die Option **Mithilfe benutzerdefinierter PSTN-Verwendungen weiterleiten** im Dropdownmenü aus. Bei Auswahl dieser Option wird ein Steuerelement angezeigt, über das vorhandene PSTN-Verwendungsdatensätze ausgewählt oder neue PSTN-Verwendungsdatensätze erstellt werden können, die speziell auf die Anrufweiterleitung und gleichzeitiges Klingeln ausgerichtet sind.

   - Klicken Sie auf **Auswählen**, um einen oder mehrere Datensätze aus einer Liste aller PSTN-Verwendungsdatensätze für die Anrufweiterleitung und gleichzeitiges Klingeln auszuwählen. Markieren Sie die Datensätze, die Sie der Richtlinie für die Anrufweiterleitung und gleichzeitiges Klingeln zuordnen möchten, und klicken Sie anschließend auf **OK**.

   - Markieren Sie einen Datensatz, und klicken Sie auf **Entfernen**, um einen PSTN-Verwendungsdatensatz aus dieser Richtlinie für die Anrufweiterleitung und gleichzeitiges Klingeln zu entfernen.

   - Führen Sie die folgenden Schritte aus, um einen neuen PSTN-Verwendungsdatensatz zu definieren und dieser Richtlinie für die Anrufweiterleitung und gleichzeitiges Klingeln zuzuordnen:

     a. Klicken Sie auf **Neu**.

     b. Geben Sie im Feld **Name** einen eindeutigen beschreibenden Namen für den Datensatz ein.

     > [!NOTE]
     > Der Name des PSTN-Verwendungsdatensatzes muss innerhalb der Enterprise-VoIP-Bereitstellung eindeutig sein. Nach dem Speichern des Datensatzes kann das Feld **Name** nicht mehr bearbeitet werden.

     c. Verwenden Sie eine der folgenden Methoden, um Routen für diesen PSTN-Datensatz zuzuordnen und zu konfigurieren:

   - Klicken Sie auf **Auswählen**, markieren Sie in der Liste der verfügbaren Routen in Ihrer Enterprise-VoIP-Bereitstellung eine oder mehrere gewünschte Routen, und klicken Sie dann auf **OK**.

   - Zum Entfernen einer Route aus dem PSTN-Verwendungsdatensatz markieren Sie die Route, und klicken Sie auf **Entfernen**.

   - Klicken Sie auf **Neu**, um eine neue Route zu definieren und sie diesem PSTN-Verwendungsdatensatz zuzuordnen. Ausführliche Informationen finden Sie unter [Erstellen oder Ändern einer VoIP-Route in Skype for Business.](create-or-modify-a-voice-route.md)

   - Markieren Sie die Route, und klicken Sie anschließend auf **Details anzeigen**, um eine Route zu bearbeiten, die diesem PSTN-Verwendungsdatensatz bereits zugeordnet wurde. Ausführliche Informationen erhalten Sie im Abschnitt [Modify a Voice Route](/previous-versions/office/lync-server-2013/lync-server-2013-modify-a-voice-route).

     d. Klicken Sie auf **OK**.

   - Führen Sie die folgenden Schritte aus, um einen PSTN-Verwendungsdatensatz zu bearbeiten, der bereits dieser VoIP-Richtlinie zugeordnet ist:

     a. Markieren Sie den PSTN-Verwendungsdatensatz, den Sie bearbeiten möchten, und klicken Sie auf **Details anzeigen**.

     b. Verwenden Sie eine der folgenden Methoden, um Routen für diesen PSTN-Datensatz zuzuordnen und zu konfigurieren:

     - Klicken Sie auf **Auswählen**, markieren Sie in der Liste der verfügbaren Routen in Ihrer Enterprise-VoIP-Bereitstellung eine oder mehrere gewünschte Routen, und klicken Sie dann auf **OK**.

     - Zum Entfernen einer Route aus diesem PSTN-Verwendungsdatensatz markieren Sie die Route, und klicken Sie auf **Entfernen**.

     - Klicken Sie auf **Neu**, um eine neue Route zu definieren und sie diesem PSTN-Verwendungsdatensatz zuzuordnen. Ausführliche Informationen finden Sie unter [Erstellen oder Ändern einer VoIP-Route in Skype for Business.](create-or-modify-a-voice-route.md)

     - Markieren Sie die Route, und klicken Sie auf **Details anzeigen**, um eine Route zu bearbeiten, die diesem PSTN-Verwendungsdatensatz bereits zugeordnet wurde. Ausführliche Informationen finden Sie unter [Modify a Voice Route](/previous-versions/office/lync-server-2013/lync-server-2013-modify-a-voice-route).

     c. Klicken Sie auf **OK**.

9. (Optional) Geben Sie eine Nummer zum Testen der VoIP-Richtlinie ein, und klicken Sie auf **Los**. Die Testergebnisse werden unter **Übersetzte Nummer für Test** angezeigt.

10. Klicken Sie auf **OK**.

11. Klicken Sie auf der Seite **VoIP-Richtlinie** auf **Commit**, und klicken Sie anschließend auf **Commit für alle**.

    > [!NOTE]
    > Jedes Mal, wenn Sie eine VoIP-Richtlinie erstellen oder ändern, müssen Sie den Befehl **Commit für alle** ausführen, um die Konfigurationsänderung zu veröffentlichen. Ausführliche Informationen finden Sie unter [Veröffentlichen ausstehender Änderungen an der VoIP-Routingkonfiguration in Skype for Business](voice-route-config-changes.md) in der Betriebsdokumentation.

12. (Optional) Voicemail Escape erkennt, dass ein Anruf sofort von der Voicemail des Mobiltelefons des Benutzers angenommen wurde, und trennt den Anruf mit der Voicemail des Mobiltelefons. Dadurch kann der Anruf weiterhin an den anderen Endpunkten des Benutzers klingeln, sodass der Benutzer den Anruf annehmen kann. Ausführliche Informationen zum Konfigurieren einer Voicemailrichtlinie finden Sie unter [Konfigurieren von Voicemail escape in Skype for Business](configure-voice-mail-escape.md).

## <a name="see-also"></a>Siehe auch

[Anzeigen von PSTN-Verwendungsdatensätzen in Skype for Business](view-pstn-usage-records.md)

[Erstellen oder Ändern einer VoIP-Route in Skype for Business](create-or-modify-a-voice-route.md)

[Veröffentlichen ausstehender Änderungen an der VoIP-Routingkonfiguration in Skype for Business](voice-route-config-changes.md)

[Konfigurieren von Voicemail escape in Skype for Business](configure-voice-mail-escape.md)