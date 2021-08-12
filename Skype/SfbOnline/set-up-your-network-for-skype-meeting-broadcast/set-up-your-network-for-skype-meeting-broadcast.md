---
title: Einrichten Ihres Netzwerks für Skype-Livekonferenz
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: micchan
ms.topic: article
ms.assetid: dfa736b9-4920-4f48-b8c0-b5487ec6086f
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- SMB
description: Erfahren Sie mehr über Skype-Besprechung Broadcast-Feature von Skype for Business Online, mit dem Sie Besprechungen oder Ereignisse für ein großes Online-Publikum von bis zu 10.000 Teilnehmern planen, produzieren und übertragen können.
ms.openlocfilehash: 068ff156badaff9231f6e477e2f41668ea8f99fd26531f2a08155c4ee4763c05
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54308026"
---
# <a name="set-up-your-network-for-skype-meeting-broadcast"></a>Einrichten Ihres Netzwerks für Skype-Livekonferenz

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Nach der [Aktivieren von Skype-Livekonferenz](enable-skype-meeting-broadcast.md) Skype-Livekonferenz müssen Sie Ihr Netzwerk konfigurieren. Führen Sie diesen Schritt aus, wenn Sie Webinare und andere Konferenzen für Personen außerhalb Ihres Unternehmens durchführen möchten.

> [!IMPORTANT]
> Skype for Business Online wird am 31. Juli 2021 beendet, und der Zugriff auf den Dienst endet. Wir empfehlen Kunden, mit dem Upgrade auf Microsoft Teams, den zentralen Client für Kommunikation und Teamarbeit in Microsoft 365.

Wenn Sie keine Erfahrungen mit der Konfiguration Ihrer Firewall haben, sollten Sie möglicherweise einen [Microsoft-Partner](https://go.microsoft.com/fwlink/?linkid=391089) für diese Aufgabe heranziehen.

Um diesen Schritt zu überspringen und stattdessen Ihrem Verbund ein anderes Unternehmen hinzuzufügen, das Sie zu Konferenzen einladen können, führen Sie die Schritte unter [Nutzern gestatten, externe Skype for Business-Nutzer zu kontaktieren](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md) aus.

## <a name="step-1-set-up-allowed-domains"></a>Schritt 1: Einrichten von zulässigen Domänen

Verwenden Sie **eine** der folgenden Methoden, um zulässige Domänen einzurichten:

### <a name="method-1-use-the-admin-center"></a>Methode 1: Verwenden des Admin Centers

1. Wechseln Sie zum Admin Center, klicken Sie im linken Navigationsbereich auf **Einstellungen**  >  **&amp; Dienste-Add-Ins**, und wählen Sie dann Skype for Business. 

2. Wählen Sie auf  **der Seite** Externe Freigabe unter Domänenausnahmen die Option **Alle Domänen** werden blockiert mit Ausnahme von aus, und geben Sie die folgenden durch ein Komma (,) getrennten Domänen ein:

   - noammeetings.lync.com

   - emeameetings.lync.com

   - apacmeetings.lync.com

   - resources.lync.com

3. Klicken Sie auf **Speichern**.

### <a name="method-2-use-windows-powershell"></a>Methode 2: Verwenden von Windows PowerShell

- Klicken Sie **im Startmenü** mit der rechten Maustaste **Windows PowerShell** dann **auf Als Administrator ausführen.** Geben Sie **im Windows PowerShell** Zeile jede Zeile ein, und drücken Sie die EINGABETASTE.

  ```PowerShell
  $r = New-CsEdgeDomainPattern -Domain "noammeetings.lync.com"
  ```

  ```PowerShell
  $s = New-CsEdgeDomainPattern -Domain "emeameetings.lync.com"
  ```

  ```PowerShell
  $t = New-CsEdgeDomainPattern -Domain "apacmeetings.lync.com"
  ```

  ```PowerShell
  $n = New-CsEdgeDomainPattern -Domain "resources.lync.com"
  ```

  ```PowerShell
  $newAllowList = New-CsEdgeAllowList -AllowedDomain $r,$s,$t,$n
  ```

  ```PowerShell
  Set-CsTenantFederationConfiguration -AllowedDomains $newAllowList
  ```

## <a name="step-2-add-skype-meeting-broadcast-domains-urls-and-ip-addresses"></a>Schritt 2: Hinzufügen Skype-Besprechung Domänen, URLs und IP-Adressen für Übertragungen

Im zweiten Schritt des Setupvorgangs fügen Sie zuerst die benötigten Domänen hinzu. Anschließend fügen Sie die IP-Adressen und URLs hinzu, die erforderlich sind, damit Skype-Livekonferenz funktioniert.

- **Fügen Sie die erforderlichen Skype for Business Online-Endpunkt-URLs** und -IP-Adressen hinzu, indem Sie sehen, welche hier erforderlich [sind.](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_lyo)

## <a name="set-up-skype-meeting-broadcast-in-hybrid-deployments-and-organizations"></a>Einrichten von Skype-Livekonferenz in Hybridbereitstellungen und -organisationen

Wenn Sie über eine Skype for Business Online-Organisation und eine lokale Bereitstellung von Lync Server 2010, Microsoft Lync Server 2013 und Skype for Business Server 2015 verfügen und Benutzer sowohl online als auch lokal verfügbar sind, müssen Sie zusätzlich zu den oben genannten Schritte weitere Setupschritte ausführen, damit Ihre lokale Organisation mit Skype for Business Online kommunizieren und allen Benutzern die Teilnahme an einer Skype-Besprechung-Übertragung ermöglichen kann. Die entsprechenden Anforderungen finden Sie unter [Konfigurieren der lokalen Bereitstellung von Skype-Livekonferenz](../../SfbServer/deploy/configure-skype-meeting-broadcast.md).

## <a name="related-topics"></a>Verwandte Themen

[Aktivieren von Skype-Livekonferenz](enable-skype-meeting-broadcast.md)

[URLs und IP-Adressbereiche von Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)

[Einrichten von Skype for Business Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
