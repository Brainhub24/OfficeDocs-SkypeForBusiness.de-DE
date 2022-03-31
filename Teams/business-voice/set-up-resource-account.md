---
title: Einrichten eines Microsoft Teams Telefon Systemressourcenkontos
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
ms.localizationpriority: medium
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: Erfahren Sie, wie Sie ein Microsoft Teams Telefon Systemressourcenkonto für die Verwendung mit automatischen Attendants einrichten.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7764d6b7f7d09cd2c5065ab24e73cb0fdec9c5c6
ms.sourcegitcommit: cbdc80c302e97d18a923ef57bb5d4b6cf7676d00
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/30/2022
ms.locfileid: "64556546"
---
# <a name="step-4-set-up-a-teams-phone-system-resource-account"></a>Schritt 4: Einrichten eines Teams Telefonsystem Ressourcenkontos

Ressourcenkonten werden keinem bestimmten Benutzer zugewiesen. Stattdessen werden Ressourcenkonten, für die eine kostenlose virtuelle Benutzerlizenz verwendet wird, von Geräten und Diensten in Microsoft 365. In Microsoft Teams Ressourcenkonten Telefonnummern zugewiesen und dann automatischen Telefonkonferenzen und Anrufwarteschleifen zugeordnet.

Durch Zuordnen von Ressourcenkonten zu automatischen Telefonkonferenzen und Anrufwarteschleifen können Sie eine oder mehrere gebührenpflichtige oder gebührenfreie Telefonnummern hinzufügen. So könnten Sie beispielsweise einer automatischen Telefonistennummer für Ortsanrufe ein Ressourcenkonto mit einer gebührenpflichtigen Nummer zuordnen. Bei Ferngesprächen können Sie derselben automatischen Telefon attendant ein anderes Ressourcenkonto einer gebührenfreien Nummer zuordnen.

In den Abschnitten dieses Artikels wird erläutert, wie Sie ein Ressourcenkonto einrichten und ihm dann eine Telefonnummer zuweisen. Später ordnen Sie das Ressourcenkonto einer automatischen Attendant zu.

## <a name="obtain-virtual-user-licenses"></a>Abrufen virtueller Benutzerlizenzen

Für Ressourcenkonten ist eine Lizenz erforderlich, um mit automatischen Telefonkonferenzen und Anrufwarteschleifen arbeiten zu können. Sie können eine kostenlose Lizenz *Microsoft Teams Telefon Standard – Virtual User verwenden*.

> [!NOTE]
> Sie sollten die folgenden Schritte nur ausführen müssen, wenn Sie sich für einen Testzeitraum Teams Telefon mit einer Anrufplanlizenz angemeldet haben. Wenn Sie Ihr Teams Telefon mit Anrufplan-Bündellizenzen erworben haben, sollten virtuelle Lizenzen bereits auf Ihr Konto angewendet werden.
>
> Um zu sehen, ob Sie bereits über virtuelle Lizenzen verfügen, melden Sie sich Microsoft 365 konto mit globalen Administratorberechtigungen an. Wechseln Sie dann zu Abrechnung > [Ihren Produkten](https://admin.microsoft.com/Adminportal/Home#/subscriptions). Wenn Sie über virtuelle Lizenzen verfügen, werden diese als Microsoft Teams Telefon **– Virtueller Benutzer angezeigt**.

1. Öffnen Sie Microsoft 365 Admin Center, und melden Sie sich mit einem Benutzer an, der ein globaler Administrator ist. Dies ist normalerweise das Konto, mit dem Sie sich für ihr Konto Microsoft 365.
2. Wechseln Sie im linken Navigationsbereich zu <a href="https://admin.microsoft.com/Adminportal/Home#/catalog" target="_blank">**BillingPurchase** > </a> **servicesAdd-onsSeeh** >  >  **alle Add-Ons-Produkte**.
3. Scrollen Sie bis zum Ende, um die Microsoft Teams Telefon **Standard – Virtual User-Lizenz** zu finden. Wählen **Sie Details** und dann **Kaufen aus**.
4. Wählen Sie auf der Seite Lizenzkauf die Anzahl der virtuellen Benutzerlizenzen aus, die Sie benötigen. Sie benötigen eine virtuelle Lizenz für jede automatische Telefon attendant und jede Anrufwarteschleife, die Sie einrichten möchten. Es wird empfohlen, mindestens fünf Lizenzen zu wählen, damit Sie zukünftig problemlos mehr automatische Telefonkonferenzen und Anrufwarteschleifen einrichten können, ohne sofort weitere Lizenzen erwerben zu müssen.
5. Deaktivieren Sie **Allen Benutzern ohne Lizenzen automatisch zuweisen**.
6. Wählen Sie **Jetzt auschecken aus**.
7. Bestätigen Sie Ihre Bestellung, wählen **Sie Weiter** und dann **Bestellung bestellen aus**.

> [!NOTE]
> Denken Sie daran,  **dass Sie die** Lizenz weiterhin kaufen müssen, auch wenn die Kosten hier für null liegen.

## <a name="create-a-resource-account"></a>Erstellen eines Ressourcenkontos

Nachdem Sie Ihre Lizenz Microsoft Teams Telefon *Standard – Virtual User*" erhalten haben, können Sie Ihr Ressourcenkonto erstellen.

1. Öffnen Sie Microsoft Teams Admin Center, und melden Sie sich mit einem Benutzer an, der ein globaler Administrator ist (dies ist normalerweise das Konto, mit dem Sie sich für Microsoft 365).
2. Wechseln Sie im linken Navigationsbereich zu <a href="https://admin.teams.microsoft.com/company-wide-settings/resource-accounts" target="_blank">**VoiceResource-Konten** > </a>.
3. Klicken Sie auf **Hinzufügen**.
4. Geben Sie **im Bereich Ressourcenkonto hinzufügen** die Informationen **Anzeigename** und dann Benutzername **ein**. Wählen Sie einen beschreibenden Anzeigenamen wie "Automatische Hauptleitungs-Attendant" aus, um den Zweck des Ressourcenkontos zu beschreiben.
5. Wählen **Sie unter Ressourcenkontotyp** die **Option Automatische Attendant aus**.
6. Klicken Sie auf **Speichern**.

## <a name="assign-a-license"></a>Lizenz zuweisen

Nachdem Sie Ihr Ressourcenkonto erstellt haben, müssen Sie eine Microsoft Teams Telefon *Standard – Virtual User-Lizenz* oder *Teams Telefon Standard-Lizenz* zuweisen.

1. Öffnen Sie Microsoft 365 Admin Center, und melden Sie sich mit einem Benutzer an, der ein globaler Administrator ist. Dies ist normalerweise das Konto, mit dem Sie sich für ihr Konto Microsoft 365.
1. Wechseln Sie im linken Navigationsbereich zu <a href="https://admin.microsoft.com/Adminportal/Home#/users" target="_blank">**BenutzerAktive** >  Benutzer</a>.
1. Wählen Sie Ihr Ressourcenkonto aus.
1. Wählen Sie **auf der Registerkarte Lizenzen** und Apps unter **Lizenzen** die Option **Microsoft Teams Telefon – Virtueller Benutzer aus**.
1. Wählen **Sie Änderungen speichern** und dann **Schließen aus**.

## <a name="assign-a-service-number"></a>Zuweisen einer Leistungsnummer

![Screenshot der Benutzeroberfläche "Servicenummer zuweisen".](../media/resource-account-assign-phone-number.png)

1. Öffnen Sie Microsoft Teams Admin Center, und melden Sie sich mit einem Benutzer an, der ein globaler Administrator ist (dies ist normalerweise das Konto, mit dem Sie sich für Microsoft 365).
1. Wechseln Sie im linken Navigationsbereich zu <a href="https://admin.teams.microsoft.com/company-wide-settings/resource-accounts" target="_blank">**VoiceResource-Konten** > </a>.
1. Wählen Sie das Ressourcenkonto aus, das Sie gerade erstellt haben, und klicken Sie dann auf **Zuordnen/Zuweisung wieder auf " Zuweisen"**.
1. Wählen Sie Telefon **Dropdownliste Nummer eingeben** die Option **Online aus**.
1. Suchen Sie **im Feld Zugewiesene** Telefonnummer nach der Zu verwendende Nummer, und klicken Sie auf **Hinzufügen**. Geben Sie unbedingt die Landescode an (z. B. **+1** 250 555 0012).
1. Klicken Sie auf **Speichern**.

> [!div class="nextstepaction"]
> [Nächster Schritt: Zuweisen von Telefonnummern zu Ihren Benutzern](set-up-assign-numbers.md)
