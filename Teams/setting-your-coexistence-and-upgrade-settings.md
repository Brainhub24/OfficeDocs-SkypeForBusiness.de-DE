---
title: Festlegen Ihrer Einstellungen für Koexistenz und Upgrades
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: bjwhalen
search.appverid: MET150
description: Erfahren Sie, wie Sie Koexistenz- und Upgradeeinstellungen für alle Benutzer in Ihrer Organisation auf einmal oder für einen einzelnen oder eine Gruppe von Benutzern in Ihrer Organisation festlegen.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 474c5fc55476e664ba03b9dd82608d8c244b7982
ms.sourcegitcommit: 9bee7cb9433bfc687387647a102f814dc52c8591
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/13/2022
ms.locfileid: "64839186"
---
# <a name="set-your-coexistence-and-upgrade-settings"></a>Festlegen Ihrer Einstellungen für Koexistenz und Upgrades


Wenn Sie Ihre Skype for Business-Benutzer zur Verwendung von Teams aktualisieren, stehen Ihnen mehrere Optionen zur Verfügung, mit denen Sie den Umstieg für Ihre Benutzer nahtlos gestalten können. Sie haben die Option, die Einstellungen für Koexistenz und Upgrade für alle Benutzer in Ihrer Organisation gleichzeitig bzw. für einzelne Personen oder Benutzergruppe in Ihrer Organisation festzulegen bzw daran Änderungen vorzunehmen. Beachten Sie, dass in älteren Versionen der Skype for Business-Clients diese Einstellungen möglicherweise nicht unterstützt werden. Weitere Informationen über die Clientversionen von Skype for Business finden Sie auf der [Seite Skype for Business-Downloads und -Updates](/skypeforbusiness/software-updates). 

Sie können die verfügbaren Modi besser verstehen, indem Sie Microsoft Teams [verstehen und Skype for Business Koexistenz und Interoperabilität](teams-and-skypeforbusiness-coexistence-and-interoperability.md) oder [Koexistenz mit Skype for Business](coexistence-chat-calls-presence.md) lesen.  

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]


## <a name="set-upgrade-options-for-all-users-in-your-organization"></a>Festlegen von Aktualisierungsoptionen für alle Benutzer in Ihrer Organisation

 **Verwenden des Microsoft Teams Admin Centers**

1. Wechseln Sie im [Microsoft Teams Admin Center](https://admin.teams.microsoft.com/) im linken Navigationsbereich zu **Teams** >  **Teams Upgradeeinstellungen**. 

2. Ändern Sie oben auf der Seite **Teams Upgrade** die folgenden Optionen nach Bedarf.

    - Legen Sie den **Koexistenzmodus** fest.
        - **Inseln** – Verwenden Sie diese Einstellung, wenn Sie möchten, dass die Benutzer Skype for Business und Teams gleichzeitig verwenden können.
        - **Nur Skype for Business** – Verwenden Sie diese Einstellung, wenn Sie möchten, dass Ihre Benutzer nur Skype for Business verwenden.
        - **Skype for Business mit Zusammenarbeit in Microsoft Teams** – Verwenden Sie diese Einstellung, wenn Sie möchten, dass Ihre Benutzer Skype for Business neben Teams für die Gruppenzusammenarbeit (Kanäle) verwenden.
        - **Skype for Business mit Zusammenarbeit und Besprechungen in Microsoft Teams** – Verwenden Sie diese Einstellung, wenn Sie möchten, dass Ihre Benutzer Skype for Business neben Teams für die Gruppenzusammenarbeit (Kanäle) und für Teams-Besprechungen verwenden.
        - **nur Teams** – Verwenden Sie diese Einstellung, wenn Ihre Benutzer nur Teams verwenden sollen. Beachten Sie, dass Benutzer trotz dieser Einstellung weiterhin an in Skype for Business gehosteten Besprechungen teilnehmen können.

          > [!IMPORTANT]
          > Sie können den TeamsOnly-Modus nur dem gesamten Mandanten zuweisen, nachdem beide der folgenden Schritte abgeschlossen wurden:
          >  - Alle lokalen Benutzer wurden zu Teams Nur mit Move-CsUser im lokalen Toolset Skype for Business Server verschoben.
          >  - Sie haben alle Skype for Business DNS-Einträge aktualisiert, um auf Microsoft 365 zu verweisen. 
          >
          > Weitere Informationen finden Sie unter [Deaktivieren der Hybridkonfiguration, um die Migration auf "Nur Teams" abzuschließen](/skypeforbusiness/hybrid/cloud-consolidation-disabling-hybrid).
        
    - **Skype for Business-Benutzern benachrichtigen, dass ein Upgrade für Teams zur Verfügung steht** einstellen. Wenn Sie diese Funktion aktivieren, teilt sie Skype for Business-Benutzern mit, dass sie in Kürze auf die Teams-App umsteigen werden.

    - Legen Sie die **Bevorzugte App für Benutzer zur Teilnahme an Skype for Business-Besprechungen** fest. Diese Einstellung bestimmt, welche App zur Teilnahme an Skype for Business-Besprechungen verwendet wird und wird unabhängig vom Wert des Koexistenzmodus berücksichtigt.
      - **Skype-Besprechungs-App**
      - **Skype for Business mit eingeschränkten Funktionen**

    - Wählen, Sie, ob die Funktion **Teams-App im Hintergrund für Benutzer von Skype for Business herunterladen** durchgeführt werden sollte. Mit dieser Einstellung wird die Teams-App für Benutzer, die Skype for Business unter Windows ausführen, automatisch heruntergeladen. Dies erfolgt nur, wenn der Koexistenzmodus für den Benutzer auf „Nur Teams“ gesetzt ist oder eine ausstehende Aktualisierungsbenachrichtigung in der Skype for Business-App aktiviert ist.

3. Nachdem Sie die gewünschten Änderungen vorgenommen haben, drücken Sie **Speichern**.

## <a name="set-upgrade-options-for-a-single-user-in-your-organization"></a>Festlegen von Aktualisierungsoptionen für einen einzelnen Benutzer in Ihrer Organisation

 **Verwenden des Microsoft Teams Admin Centers**

1. Wechseln Sie in der linken Navigationsleiste zu **"UsersManage** > **"-Benutzer**, und wählen Sie dann den Benutzer aus der Liste aus. 
2. Klicken Sie auf der Registerkarte **Konto** für den Benutzer unter **Teams-Upgrade** auf **Bearbeiten**.
3. Sie können den **Koexistenzmodus** festlegen. Andere Modi als Teams Nur kann nur auf Benutzer angewendet werden, die in Skype for Business Server lokal verwaltet werden, und umgekehrt können nur Benutzer, die in der Cloud verwaltet werden, über den TeamsOnly-Modus verfügen.  Wählen Sie aus den folgenden Optionen aus:
     - **Organisationsweite Einstellungen verwenden** – Verwenden Sie diese Einstellung, wenn Sie möchten, dass der Benutzer die Einstellungen in den **Organisationsweiten** Einstellungen verwendet. 
     - **Inseln** – Verwenden Sie diese Einstellung, wenn Sie möchten, dass der Benutzer Skype for Business und Teams zusammen verwenden kann. 
     - **Nur Skype for Business** – Verwenden Sie diese Einstellung, wenn Sie möchten, dass der Benutzer nur Skype for Business verwendet.
     - **Skype for Business mit Zusammenarbeit in Microsoft Teams** – Verwenden Sie diese Einstellung, wenn Sie möchten, dass der Benutzer Skype for Business neben Teams für die Gruppenzusammenarbeit (Kanäle) verwendet.
      - **Skype for Business mit Zusammenarbeit und Besprechungen in Microsoft Teams** – Verwenden Sie diese Einstellung, wenn Sie möchten, dass der Benutzer Skype for Business neben Teams für die Gruppenzusammenarbeit (Kanäle) und für Teams-Besprechungen verwendet.
     - **Nur Teams** – Verwenden Sie diese Einstellung, wenn Sie möchten, dass der Benutzer nur Teams verwendet. Der Benutzer kann weiterhin an Skype for Business-Besprechungen teilnehmen.
4. Wenn Sie einen anderen **Koexistenzmodus** als **Organisationsweite Einstellungen** verwenden wählen, haben Sie die Möglichkeit, in der Skype for Business-App des Nutzers Benachrichtigungen zu aktivieren, dass das Upgrade auf Teams demnächst erfolgt. Sie können diese Benachrichtigung für den Benutzer aktivieren, indem Sie die Option **Den Skype for Business-Benutzer benachrichtigen** aktivieren.
5. Nachdem Sie die gewünschten Änderungen vorgenommen haben, drücken Sie **Speichern**.

### <a name="related-topics"></a>Verwandte Themen
[Die Reise planen](upgrade-plan-journey.md)

[Die Koexistenz und den Upgrade-Prozess für Skype for Business und Teams verstehen](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

[Anleitungen zur Migration und Interoperabilität für Organisationen, die Teams zusammen mit Skype for Business verwenden](migration-interop-guidance-for-teams-with-skype.md)

[Außerbetriebnahme ihrer lokalen Skype for Business-Umgebung](/skypeforbusiness/hybrid/decommission-on-prem-overview)
