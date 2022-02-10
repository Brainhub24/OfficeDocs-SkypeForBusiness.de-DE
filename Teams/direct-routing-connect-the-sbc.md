---
title: Verbinden Ihres Session Border Controller (SBC) zum direkten Routing
ms.reviewer: fillipse
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Hier erfahren Sie, wie Sie Ihren SBC konfigurieren und eine Verbindung mit Teams Telefonsystem Direct-Routing herstellen.
ms.openlocfilehash: 7983fa176fec5e4921db169e1e92a6f6ebc2f2a7
ms.sourcegitcommit: 5e9b50cd1b513f06734be6c024ac06d293b27089
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/10/2022
ms.locfileid: "62518717"
---
# <a name="connect-your-session-border-controller-sbc-to-direct-routing"></a>Verbinden Ihres Session Border Controller (SBC) zum direkten Routing

In diesem Artikel wird beschrieben, wie Sie einen Session Border Controller (SBC) konfigurieren und mit Direct Routing verbinden.  Dies ist Schritt 1 der folgenden Schritte zum Konfigurieren von Direct-Routing:

- **Schritt 1. Verbinden SBC mit Telefonsystem und Überprüfen der Verbindung** (in diesem Artikel)
- Schritt 2: [Aktivieren von Benutzern für das Direkte Routing](direct-routing-enable-users.md)
- Schritt 3: [Konfigurieren der Anrufrouting](direct-routing-voice-routing.md)
- Schritt 4: [Übersetzen von Zahlen in ein alternatives Format](direct-routing-translate-numbers.md)

Informationen zu allen erforderlichen Schritten zum Einrichten von Direct-Routing finden Sie unter [Konfigurieren von Direct-Routing](direct-routing-configure.md).

Sie können das Microsoft Teams [Admin Center](#using-the-microsoft-teams-admin-center) oder [PowerShell](#using-powershell) verwenden, um einen SBC zu konfigurieren und mit Direct Routing zu verbinden.

## <a name="using-the-microsoft-teams-admin-center"></a>Verwenden des Microsoft Teams Admin Centers

1. Wechseln Sie im linken Navigationsbereich zu **VoiceDirect** >  **Routing**, und klicken Sie dann auf die **Registerkarte SBCs**.

2. Klicken Sie auf **Hinzufügen**.

3. Geben Sie einen FQDN für den SBC ein. <br><br>Stellen Sie sicher, dass der Domänenname-Teil des FQDNs einer Domäne entspricht, die in `*.onmicrosoft.com` Ihrem Mandanten registriert ist, und beachten Sie, dass der Domänenname für den SBC-FQDN-Domänennamen nicht unterstützt wird. Wenn Sie z. B. zwei Domänennamen haben, `contoso.com` und `contoso.onmicrosoft.com`, verwenden Sie `sbc.contoso.com` als SBC-Namen. Wenn Sie eine Unterdomäne verwenden, stellen Sie sicher, dass diese Unterdomäne auch in Ihrem Mandanten registriert ist. Wenn Sie beispielsweise verwenden möchten `sbc.service.contoso.com`, muss `service.contoso.com` registriert werden.

4. Konfigurieren Sie die folgenden Einstellungen für den SBC basierend auf den Anforderungen Ihrer Organisation. Details zu jeder dieser Einstellungen finden Sie unter [SBC-Einstellungen](#sbc-settings).

    ![Screenshot der Seite "SBC hinzufügen" im Microsoft Teams Admin Center.](media/direct-routing-add-sbc.png)

5. Klicken Sie abschließend auf **Speichern**.

## <a name="using-powershell"></a>Verwendung von PowerShell

Um Ihre SBC mit Direct-Routing zu verbinden, müssen Sie:

1. [Verbinden PowerShell Skype for Business Online zu finden](#connect-to-skype-for-business-online-by-using-powershell).

2. [Verbinden SBC an den Mandanten weiter](#connect-the-sbc-to-the-tenant).

3. [Überprüfen Sie die SBC-Verbindung](#verify-the-sbc-connection).

### <a name="connect-to-skype-for-business-online-by-using-powershell"></a>Verbinden von Skype for Business Online mithilfe von PowerShell

Verwenden Sie zum Koppeln des SBC mit der Direct-Routingschnittstelle eine mit dem Mandanten verbundene PowerShell-Sitzung. Führen Sie zum Öffnen einer PowerShell-Sitzung die Schritte unter Einrichten [Ihres Computers für Windows PowerShell](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).
 
Überprüfen Sie nach dem Einrichten einer PowerShell-Remotesitzung, ob die Befehle zum Verwalten des SBC angezeigt werden. Um die Befehle zu überprüfen, geben Sie in der PowerShell-Sitzung den folgenden Befehl ein. Sie können den Befehl auch kopieren und einfügen, und drücken Sie dann die EINGABETASTE: 

```PowerShell
Get-Command *onlinePSTNGateway*
```

Der Befehl gibt die vier hier gezeigten Funktionen zurück, die Ihnen die Verwaltung der SBC ermöglichen.

<pre>
CommandType    Name                       Version    Source 
-----------    ----                       -------    ------ 
Function       Get-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       New-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       Remove-CsOnlinePSTNGateway 1.0        tmp_v5fiu1no.wxt 
Function       Set-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt
</pre>

### <a name="connect-the-sbc-to-the-tenant"></a>Verbinden des SBC an den Mandanten

Um die SBC mit dem Mandanten zu verbinden, verwenden Sie das [Cmdlet New-CsOnlinePSTNGateway](/powershell/module/skype/new-csonlinepstngateway) . Geben Sie in einer PowerShell-Sitzung Folgendes ein, und drücken Sie dann die EINGABETASTE:

```PowerShell
New-CsOnlinePSTNGateway -Fqdn <SBC FQDN> -SipSignalingPort <SBC SIP Port> -MaxConcurrentSessions <Max Concurrent Sessions the SBC can handle> -Enabled $true
```

  > [!NOTE]
  > 1. Wir empfehlen, eine maximale Anrufgrenze in SBC mithilfe von Informationen in der SBC-Dokumentation zu setzen. Das Limit löst eine Benachrichtigung aus, wenn sich der SBC auf der Kapazitätsebene befindet.
  > 2. Sie können nur dann eine Verbindung mit dem SBC herstellen, \*wenn der Domänenteil seines FQDNs einer der in Ihrem Mandanten registrierten Domänen mit Ausnahme von onmicrosoft.com. Die \*Verwendung onmicrosoft.com Domänennamen wird für den SBC-FQDN-Namen nicht unterstützt. Wenn Sie beispielsweise über zwei Domänennamen verfügen, **contoso.com** und **contoso.onmicrosoft.com**, können Sie sbc.contoso.com für den SBC-Namen verwenden. Wenn Sie versuchen, den SBC mit einem Namen wie "sbc.contoso.abc" zu verbinden, lässt das System dies nicht zu, da die Domäne nicht im Besitz dieses Mandanten ist.<br/>
  > Neben der in Ihrem Mandanten registrierten Domäne ist es wichtig, dass es einen Benutzer mit dieser Domäne und einer zugewiesenen E3- oder E5-Lizenz gibt. Andern falls nicht, wird die folgende Fehlermeldung angezeigt:<br/>
  `Can not use the "sbc.contoso.com" domain as it was not configured for this tenant`.

Nachfolgend ein Beispiel:

```PowerShell
New-CsOnlinePSTNGateway -Identity sbc.contoso.com -Enabled $true -SipSignalingPort 5067 -MaxConcurrentSessions 100 
```

Gibt zurück:

<pre>
Identity              : sbc.contoso.com 
Fqdn                  : sbc.contoso.com 
SipSignalingPort     : 5067 
FailoverTimeSeconds   : 10 
ForwardCallHistory    : False 
ForwardPai            : False 
SendSipOptions        : True 
MaxConcurrentSessions : 100 
Enabled               : True   
</pre>

> [!NOTE]
> In diesem Beispiel werden nur die minimal erforderlichen Parameter angezeigt. Es gibt zusätzliche Parameter, die Sie während des Verbindungsprozesses mit dem [New-CsOnlinePSTNGateway-Cmdlet](/powershell/module/skype/new-csonlinepstngateway) festlegen können. Weitere Informationen finden Sie unter [SBC-Einstellungen](#sbc-settings).
 
### <a name="verify-the-sbc-connection"></a>Überprüfen der SBC-Verbindung

So überprüfen Sie die Verbindung:

- [Überprüfen Sie, ob sich der SBC in der Liste der gekoppelten SBCs befindet](#check-whether-the-sbc-is-on-the-list-of-paired-sbcs).
- [Überprüfen Sie die SIP-Optionen](#validate-sip-options).
 
#### <a name="check-whether-the-sbc-is-on-the-list-of-paired-sbcs"></a>Überprüfen, ob sich der SBC in der Liste der gekoppelten SBCs befindet

Nachdem Sie eine Verbindung mit dem SBC hergestellt haben, verwenden Sie das [Cmdlet Get-CsOnlinePSTNGateway](/powershell/module/skype/get-csonlinepstngateway) , um zu überprüfen, ob der SBC in der Liste der gekoppelten SBCs enthalten ist. Geben Sie Folgendes in einer PowerShell-Remotesitzung ein, und drücken Sie dann die EINGABETASTE:

```PowerShell
Get-CsOnlinePSTNGateway -Identity sbc.contoso.com  
```

Das gekoppelte Gateway sollte wie im folgenden Beispiel gezeigt in der Liste angezeigt werden, und für den Parameter **Enabled** sollte der Wert **True angezeigt werden**.

Gibt zurück:

<pre>
Identity              : sbc.contoso.com  
Fqdn                  : sbc.contoso.com
SipSignalingPort     : 5067
CodecPriority         : SILKWB,SILKNB,PCMU,PCMA
ExcludedCodecs        :  
FailoverTimeSeconds   : 10
ForwardCallHistory    : False
ForwardPai            : False
SendSipOptions        : True
MaxConcurrentSessions : 100
Enabled               : True
</pre>

#### <a name="validate-sip-options"></a>Überprüfen von SIP-Optionen

Um die Kopplung mithilfe von ausgehenden SIP-Optionen zu überprüfen, verwenden Sie die SBC-Verwaltungsschnittstelle, und vergewissern Sie sich, dass der SBC 200 OK-Antworten auf die ausgehenden OPTIONS-Nachrichten erhält.

Wenn Direct Routing eingehende OPTIONEN sieht, beginnt es mit dem Senden ausgehender SIP Options-Nachrichten an den SBC-FQDN, der in der eingehenden OPTIONS-Nachricht im Feld Kontaktkopf konfiguriert wurde. 

Um die Kopplung mithilfe eingehender SIP-Optionen zu überprüfen, verwenden Sie die SBC-Verwaltungsschnittstelle, und überprüfen Sie, ob der SBC eine Antwort auf die OPTIONS-Nachrichten sendet, die von Direct Routing eingehen, und dass der gesendete Antwortcode 200 OK ist.

## <a name="sbc-settings"></a>SBC-Einstellungen

In dieser Tabelle sind die Optionen aufgeführt, die Sie für die SBC im Microsoft Teams Admin Center und mithilfe des [New-CsOnlinePSTNGateway-Cmdlets](/powershell/module/skype/new-csonlinepstngateway) festlegen können.

|Erforderlich?|Teams Admin Center-Einstellung|PowerShell-Parameter|Beschreibung|Standard|Mögliche Werte|Typ und Einschränkungen|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Ja|**Hinzufügen eines FQDNs für SBC**|FQDN |Keine|FQDN-Name, Beschränkung auf 63 Zeichen|Zeichenfolge finden Sie in der Liste der zulässigen und unzulässigen Zeichen zu Benennungskonventionen [in Active Directory für Computer, Domänen, Websites und Organisations-E-Mail-aktivierte Benutzer](https://support.microsoft.com/help/909264).|
|Nein|**Aktiviert**|Aktiviert|Verwenden Sie , um SBC für ausgehende Anrufe zu aktivieren. Damit können Sie den SBC während der Aktualisierung oder während der Wartung vorübergehend aus dem Dienst entfernen. |Falsch|Wahr<br/>Falsch|Boolean|
|Ja|**SIP-Signalisierungsport**|SipSignalingPort |Dies ist der Lauschport, der für die Kommunikation mit Direct-Routing mithilfe des TLS-Protokolls (Transport Layer) verwendet wird.|Keine|Beliebiger Port|0 bis 65535 |
|Nein|**SIP-Optionen senden**|SendSIPOptions |Definiert, ob der SBC Nachrichten mit SIP-Optionen sendet. Es wird dringend empfohlen, diese Einstellung zu aktivieren. Wenn diese Einstellung deaktiviert ist, wird der SBC aus dem Überwachungs- und Warnungssystem ausgeschlossen.|Wahr|Wahr<br/>Falsch|Boolean|
|Nein|**Anrufverlauf weiterleiten**|ForwardCallHistory |Gibt an, ob die Anrufverlaufsinformationen über den Trunk weitergeleitet werden. Wenn Sie dies aktivieren, sendet Microsoft 365 Proxy eine Verlaufsinfo- und eine "Referred-by"-Kopfzeile. |Falsch|Wahr<br/>Falsch|Boolean|
|Nein|**Header "Forward P-Asserted-identity" (WERDEN)**|ForwardPAI|Gibt an, ob der IHNEN-Header zusammen mit dem Anruf weitergeleitet wird. Der PAI-Header bietet eine Möglichkeit, die Identität des Anrufers zu überprüfen. Wenn diese Einstellung auf "Privacy:ID" klicken, wird auch der Header "Privacy:ID" gesendet.|Falsch|Wahr<br/>Falsch|Boolean|
|Nein|**Kapazität gleichzeitiger Anrufe**|MaxConcurrentSessions |Wenn Sie einen Wert festlegen, werden Sie vom Benachrichtigungssystem benachrichtigt, wenn die Anzahl der gleichzeitigen Sitzungen 90 % oder höher als dieser Wert ist. Wenn Sie keinen Wert festlegen, werden keine Warnungen generiert. Das Überwachungssystem gibt jedoch alle 24 Stunden die Anzahl von gleichzeitigen Sitzungen an. |Null|Null<br/>1 bis 100.000 ||
|Nein|**Failoverantwortcodes**|FailoverResponseCodes<br>|Wenn Direct Routing als Antwort auf eine ausgehende Einladung einen SIP-Fehlercode 4xx oder 6xx erhält, gilt der Anruf standardmäßig als abgeschlossen. Ausgehend bedeutet einen Anruf von einem Teams-Client zum PSTN mit Datenverkehrsfluss: Teams Client -> Direct Routing -> SBC -> telephony network). Wenn Sie einen Failoverantwortcode angeben, zwingt dies Direct Routing, einen anderen SBC auszuprobieren (wenn in der Voiceroutingrichtlinie des Benutzers ein anderer SBC vorhanden ist), wenn er die angegebenen Codes empfängt, wenn der SBC aufgrund von Netzwerk- oder anderen Problemen keinen Aufruf durchführen kann. Weitere Informationen finden Sie unter [Failover bestimmter SIP-Codes, die vom Session Border Controller (SBC) empfangen werden](direct-routing-trunk-failover-on-outbound-call.md).|408, 503, 504||Int|
|Nein|**Failoverzeiten (Sekunden)**|FailoverTimeSeconds |Wenn Sie einen Wert festlegen, werden ausgehende Anrufe, die vom Gateway nicht innerhalb der festgelegten Zeit beantwortet werden, an den nächsten verfügbaren Trunk geroutet. Wenn es keine zusätzlichen Trunks gibt, wird der Anruf automatisch verworfen. Der Standardwert beträgt 10 Sekunden. In einer Organisation mit langsamen Netzwerken und Gatewayantworten kann dies dazu führen, dass Anrufe unnötig verworfen werden.|10|Zahl|Int|
|Nein|**Bevorzugtes Land oder eine bevorzugte Region für Medienverkehr**|MediaRelayRoutingLocationOverride | Nicht für Direct-Routing anwendbar. Dieser Parameter ist für die Verwendung mit verwalteten Netzbetreibern in Anrufplänen reserviert. |Keine|||
|Nein|**SBC unterstützt PIDF/LO für Notrufe**|PidfloSupported|Geben Sie an, ob der SBC presence Information Data Format Location Object (PIDF/LO) für Notrufe unterstützt.||||
|Nein| - |MediaBypass|Diese Einstellung gibt an, ob der SBC die Medienumgehung unterstützt und ob Sie ihn für diesen SBC verwenden möchten. |Keine|Wahr<br/>Falsch|Boolean|

## <a name="see-also"></a>Mehr dazu

[Planen von direktem Routing](direct-routing-plan.md)

[Konfigurieren von direktem Routing](direct-routing-configure.md)

[Übersicht über PowerShell für Microsoft Teams](teams-powershell-overview.md)
