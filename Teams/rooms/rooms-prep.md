---
title: Vorbereiten Ihrer Umgebung
ms.author: czawideh
author: cazawideh
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: b4e0ad1e-12e5-4130-aec1-d8c9cd3a5965
ms.collection:
- M365-collaboration
description: Hier erfahren Sie, wie Sie Ihre Infrastruktur für Microsoft Teams-Räume Bereitstellung vorbereiten, damit Sie alle Features nutzen können.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 5203972feee8276d9d63c19f65965f62386ee7a0
ms.sourcegitcommit: a894e9397050e09bfaab02e700e943a3bbeb1302
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2022
ms.locfileid: "63503952"
---
# <a name="prepare-your-environment"></a>Vorbereiten der Umgebung

Dieser Abschnitt enthält eine Übersicht über die Schritte, die erforderlich sind, um Ihre Umgebung so vorzubereiten, dass Sie alle Features ihrer Microsoft Teams-Räume.
  
1. Bereiten Sie ein Ressourcenkonto für die einzelnen Microsoft Teams-Räume vor. Weitere [Informationen finden Microsoft Teams-Räume](rooms-deploy.md) bereitstellen.
    
2. Stellen Sie sicher, dass eine funktionierende Netzwerk-/Internetverbindung vorhanden ist, die für das Gerät verwendet werden kann.
  
3. Microsoft erfasst Daten, um die Benutzerfreundlichkeit zu verbessern. Um Microsoft das Sammeln von Daten zu ermöglichen, lassen Sie diese Websites zu:

   - Telemetrieclientendpunkt: https://vortex.data.microsoft.com/
   - Endpunkt für Telemetrieeinstellungen: https://settings.data.microsoft.com/
    
### <a name="create-and-test-a-resource-account"></a>Erstellen und Testen eines Ressourcenkontos

Ein *Ressourcenkonto ist* ein Konto, das der Microsoft Teams-Räume-Client für den Zugriff auf Features von Exchange, z. B. Kalender, und zum Herstellen einer Verbindung mit Microsoft Teams. Weitere [Informationen finden Microsoft Teams-Räume](rooms-deploy.md) bereitstellen.
  
### <a name="check-network-availability"></a>Überprüfen der Netzwerkverfügbarkeit

Um ordnungsgemäß funktionieren zu Microsoft Teams-Räume Sie Zugriff auf ein verkabeltes Netzwerk haben, das diese Anforderungen erfüllt:
  
- Zugriff auf Ihre Active Directory- oder Azure Active Directory -Instanz (Azure AD) sowie Microsoft Exchange und Microsoft Teams.

- Zugriff auf einen Server, der über DHCP eine IP-Adresse bereitstellen kann. Microsoft Teams-Räume kann beim ersten Komponentenstart nicht mit einer statischen IP-Adresse konfiguriert werden.

- Zugriff auf die HTTP-Ports 80 und 443

- DIE TCP- und UDP-Ports sind so konfiguriert, wie unter [Port](/skypeforbusiness/plan-your-deployment/network-requirements/ports-and-protocols)- und Protokollanforderungen für Server für lokale Skype for Business Server-Implementierungen oder Microsoft 365- und [Office 365-URLs](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US) und IP-Adressbereiche für Microsoft Teams beschrieben.

Wenn Sie in Ihrem Netzwerk einen Proxy verwenden, benötigen Sie außerdem die Proxyadresse oder Skriptinformationen.
    
> [!IMPORTANT]
> Microsoft Teams-Räume unterstützt keine Proxyauthentifizierung, da dies den normalen Betrieb des Raum beeinträchtigen kann. Stellen Sie sicher, Microsoft Teams-Räume von der Proxyauthentifizierung ausgenommen wurden, bevor Sie in die Produktion gehen.

> [!IMPORTANT]
> Verwenden Sie unbedingt eine 1-GBit/s-Kabelnetzwerkverbindung, um sicherzustellen, dass die benötigte Bandbreite verfügbar ist.

> [!NOTE]
> Softwareupdates für Microsoft Teams-Räume werden automatisch von der App Microsoft Store für Unternehmen. Unter [Voraussetzungen für Microsoft Store für Unternehmen und Education](/microsoft-store/prerequisites-microsoft-store-for-business) können Sie überprüfen, ob die Raumkonsole auf den Store zugreifen und die App selbst aktualisieren kann.
  
### <a name="certificates"></a>Zertifikate

Ihr Microsoft Teams-Räume verwendet Zertifikate für Exchange-Webdienste, Microsoft Teams oder Skype for Business, Netzwerkverwendung und Authentifizierung. Wenn die verwandten Server öffentliche Zertifikate verwenden (dies gilt für Onlinebereitstellungen und einige lokale Bereitstellungen), sollte vom Administrator keine weiteren Schritte zum Installieren von Zertifikaten erforderlich sein. Wenn es sich bei der Zertifizierungsstelle hingegen um eine private Zertifizierungsstelle handelt, muss das Gerät dieser Zertifizierungsstelle vertrauen. Dies bedeutet, dass die Zertifikatkette für Zertifizierungsstellen und Zertifizierungsstellen auf dem Gerät installiert ist. Wenn Sie das Gerät zur Domäne hinzufügen, wird diese Aufgabe möglicherweise automatisch ausgeführt.
  
Sie können Zertifikate genauso installieren wie für jeden anderen Windows-Client. 
  
> [!NOTE]
> Zertifikate sind möglicherweise erforderlich, um Ihre Microsoft Teams-Räume verwenden Skype for Business Server.
  
### <a name="proxy"></a>Proxy

Microsoft Teams-Räume -Objekt ist so konzipiert, dass es Proxyeinstellungen vom Betriebssystem Windows erbt. Greifen Sie wie folgt auf das Windows-Betriebssystem zu:
  
1. Klicken Sie auf der Microsoft Teams-Räume-Benutzeroberfläche auf das Zahnradsymbol Einstellungen, wo Sie aufgefordert werden, das lokale Administratorkennwort auf dem Gerät einzugeben (das Standardkennwort ist **sfb**).
2. Tippen Sie auf **Einstellungen**, gefolgt von der Schaltfläche Gehe zu **Windows**. Tippen Sie dann auf die Schaltfläche Zur Administratoranmelden  wechseln, und klicken Sie dann auf die Schaltfläche **Administrator** (wenn der Computer Mitglied der Domäne ist, wählen Sie Anderer Benutzer **aus,** und verwenden Sie dann .\admin als Benutzernamen).
3. Geben Sie **unten Windows** im Feld Suche nach links regedit ein (drücken Sie entweder lange auf den Bildschirm, oder klicken Sie mit der rechten Maustaste, und wählen Sie **Als Administrator ausführen aus**).
4. Klicken Sie auf den Ordner HKEY_USERS. (Eine Liste der Computerbenutzer-SIDs wird angezeigt.) Stellen Sie sicher, dass der Stammordner HKEY_USERS ausgewählt ist.
       
5. Klicken Sie auf Datei, und wählen Sie **Struktur laden aus.**
6. Navigieren Sie zum Ordner **"C:\Benutzer\Skype**", geben Sie im Feld Dateiname den Namen "N TINER.dat" ein, und drücken Sie die Schaltfläche "Öffnen".

7. Sie werden zur Eingabe eines Schlüsselnamens für die neu geladene Struktur aufgefordert. geben Sie Skype ein (nun sollten die Registrierungseinstellungen für den Benutzer Skype werden).
 
8. Öffnen Sie die Skype taste, navigieren Sie zu HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings stellen Sie dann sicher, dass die folgenden Einstellungen eingegeben werden: 
    
    ```console
    [HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings]
    "MigrateProxy"=dword:00000001
    "ProxyEnable"=dword:00000001
    "ProxyServer"="xx.xx.xx.xx:8080"
    ```
    
    Wenn „ProxyServer“ nicht vorhanden ist, müssen Sie diesen Schlüssel möglicherweise als Zeichenfolge hinzufügen. Ändern Sie „xx.xx.xx.xx:8080“ zu IP/Host und Port Ihres Proxyservers.
 
    Wenn der Kunde eine PAC-Datei verwendet, würde die Konfiguration wie im folgenden Beispiel aussehen:

     ```console
    [HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings]
    "MigrateProxy"=dword:00000001
    "ProxyEnable"=dword:00000001
    "AutoConfigURL"=http://contosoproxy.corp.net/proxy.pac
    ```
    
9. Markieren Sie nach Abschluss Ihrer Änderungen den Skype-Benutzerschlüssel (Stammordner für Skype), und wählen Sie aus dem Dateimenü „Registrierung“ die Option „Struktur entladen“ aus. (Sie müssen dies durch Auswahl von **Ja** bestätigen.)
    
10. Schließen Sie nun den Registrierungs-Editor, und geben Sie in das Feld der Windows-Suche „Abmelden“ ein.
    
11. Wählen Sie auf der Anmeldeseite den Benutzer **Skype** aus. Wenn alle vorherigen Schritte erfolgreich waren, kann Microsoft Teams-Räume erfolgreich anmelden.
    
Ausführliche Informationen [zu](./security.md#network-security) FQDNs, Ports und IP-Adressbereichen, die für die Netzwerksicherheit erforderlich sind, finden Sie Microsoft Teams-Räume.
  
### <a name="admin-group-management"></a>Verwaltung von Administratorgruppen

Wenn Sie sich für den Beitritt zu einer Domäne (Azure Active Directory oder Active Directory) entscheiden, können Sie Microsoft Endpoint Manager, Gruppenrichtlinie oder Lokale Computerverwaltung verwenden, um eine Sicherheitsgruppe wie einen Windows-PC in Ihrer Domäne als lokalen Administrator zu festlegen. Jeder, der Mitglied dieser Sicherheitsgruppe ist, kann seine Anmeldeinformationen eingeben und die Sperrung Einstellungen.
  
> [!NOTE]
> Wenn die Vertrauensstellung zwischen Ihrem Microsoft Teams Rooms-Gerät und der Domäne verloren geht (zum Beispiel, wenn Sie Microsoft Teams Rooms nach dem Domänenbeitritt aus der Domäne entfernen), können Sie sich nicht gegenüber dem Gerät authentifizieren und die Einstellungen öffnen. Die Lösung ist, sich mit dem lokalen Administratorkonto anzumelden. 
  
## <a name="local-accounts"></a>Lokale Konten

### <a name="microsoft-teams-rooms-local-user-account"></a>Microsoft Teams-Räume lokales Benutzerkonto

Teams-Räume enthält ein kennwortfreies lokales Konto namens "Skype". Dieses Konto wird zum Anmelden bei Windows zum Starten der App Teams-Räume verwendet. Die Anwendung eines Kennworts auf dieses Konto wird nicht unterstützt. Weitere [Microsoft Teams-Räume finden Sie unter](security.md) Sicherheit.
  
### <a name="admin---local-administrator-account"></a>"Administrator" – Lokales Administratorkonto

Microsoft Teams-Räume Standardkennwort ist auf "sfb" festgelegt. Das Kennwort kann lokal im Administratormodus oder in der AutoUnattend.xml-Datei geändert werden (verwenden Sie den Windows System Image Manager von ADK, um die Änderung an der XML-Datei zu ändern).
  
> [!CAUTION]
> Achten Sie darauf, das Kennwort Microsoft Teams-Räume so schnell wie möglich zu ändern. 
  
Das Kennwort für den lokalen Administrator ist während des Setups nicht als Option enthalten.

Weitere Informationen zum Administratorkonto finden Sie im Artikel Microsoft Teams-Räume [Sicherheitseinstellungen](security.md).
  
### <a name="machine-account"></a>Computerkonto

Ähnlich wie jedes Windows Gerät kann der Computername umbenannt werden, indem mit der rechten Maustaste in das Feld **Einstellungen** About **Rename PC geklickt** \> \> wird.
  
Wenn Sie den Computer nach dem Beitritt zu einer Domäne umbenennen möchten, verwenden Sie [Rename-Computer](/powershell/module/microsoft.powershell.management/rename-computer?view=powershell-7.2), einen PowerShell-Befehl, gefolgt vom neuen Namen des Computers.
  
## <a name="related-topics"></a>Verwandte Themen

[Planen Microsoft Teams-Räume](rooms-plan.md)

[Voraussetzungen für Microsoft Teams-Räume](requirements.md)
  
[Bereitstellen von Microsoft Teams-Räume](rooms-deploy.md)
  
[Konfigurieren einer Konsole für Microsoft Teams-Räume](console.md)
  
[Microsoft Teams-Räume verwalten](rooms-manage.md)

[Voraussetzungen für Microsoft Store für Unternehmen und Bildungseinrichtungen](/microsoft-store/prerequisites-microsoft-store-for-business)
