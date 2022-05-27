---
title: Für Direct Routing zertifizierte Sitzungsrahmencontroller
ms.author: crowe
ms.reviewer: FilippSe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.localizationpriority: high
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
hideEdit: true
f1.keywords:
- NOCSH
description: Erfahren Sie, welche Session Border Controller (SBCs) für Direct Routing zertifiziert wurden.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 2583ec6e2e4eeb8f983d85779c37a91e1abfa646
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675687"
---
# <a name="session-border-controllers-certified-for-direct-routing"></a>Für Direct Routing zertifizierte Session Border Controller

Microsoft arbeitet mit ausgewählten SBC-Anbietern (Session Border Controller) zusammen, um ihre SBCs für den Einsatz mit direktem Routing zu zertifizieren.

Microsoft arbeitet mit jedem Anbieter zusammen, um folgende Schritte zu unternehmen:

- Gemeinsam an den SIP-Verbindungsprotokollen zu arbeiten.
- Intensive Tests mithilfe eines Drittanbieterlabors durchzuführen. Nur Geräte, die die Tests bestehen, sind zertifiziert.
- Alle zertifizierten Geräte werden täglich in Produktions- und Präproduktionsumgebungen getestet. Die Validierung der Geräte in Präproduktionsumgebungen gewährleistet, dass neue Versionen des Codes für direktes Routing in der Cloud auf zertifizierten SBCs funktionieren.
- Einen gemeinsamen Supportprozess mit den SBC-Anbietern bereitzustellen.

  > [!NOTE]
  > Microsoft unterstützt das Telefonsystem mit Direct Routing nur, wenn es mit zertifizierten Geräten verwendet wird. Bei Problemen müssen Sie sich zuerst an den Kundensupport Ihres SBC-Lieferanten wenden. Bei Bedarf wird der SBC-Lieferant das Problem über interne Kanäle an Microsoft eskalieren. Microsoft behält sich das Recht vor, Supportfälle abzulehnen, in denen ein nicht zertifiziertes Gerät über Direct Routing mit dem Telefonsystem verbunden ist. Wenn Microsoft feststellt, dass das Direct Routing-Problem eines Kunden mit dem SBC-Gerät eines Lieferanten zusammenhängt, muss der Kunde den SBC-Anbieter erneut engagieren, um Support zu erhalten.
  >
  > Die Zertifizierung wird für bestimmte SBC-Firmwareversionen gewährt. Jede nachstehend dokumentierte SBC-Firmwareversion ist zertifiziert und wird unterstützt. Höhere Firmwareversionen als jene, die dokumentiert sind, werden unterstützt, solange die Haupt-.Nebenversion gleich ist.
  >
  > Beispiel:
  >
  > - Unterstützt 6.10.258 – In diesem Fall unterstützt Microsoft die Firmwareversionen 6.10.(258 oder höher).
  > - Empfohlen 6.20.100 – In diesem Fall empfiehlt Microsoft die Firmwareversionen 6.20.(100 oder höher).
  > - Wenn Sie Fragen zur Unterstützung einer bestimmten Version haben, wenden Sie sich an Ihren SBC-Anbieter.

Die folgende Tabelle enthält eine Liste der für direktes Routing zertifizierten Geräte. (Informationen dazu, welche SBC-Anbieter die Lokale Medienoptimierung unterstützen, finden Sie unter [Optimierung lokaler Medien für Direktes Routing konfigurieren](direct-routing-media-optimization-configure.md).)

[Hier finden Sie weitere Informationen zu direktem Routing](https://aka.ms/dr).

Hinweis: Bis auf weiteres akzeptieren wir keine neuen Nominierungen für Zertifizierungen.

## <a name="certified-sbc-vendors"></a>Zertifizierte SBC-Anbieter

|Anbieter|Produkt|Nicht-Medienumgehung|Medienumgehung|Softwareversion|Notruf-Dienstanbieterfähig*|ELIN-fähig|
|---|---|---|---|---|---|---|
|[AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)|Mediant 500 SBC|&#10004;|&#10004;|Unterstützt 7.20A.258 (empfohlen 7.40A.100 oder 7.40A.250)|&#10004;|&#10004;|
||Mediant 800 SBC|&#10004;|&#10004;|Unterstützt 7.20A.258 (empfohlen 7.40A.100 oder 7.40A.250)|&#10004;|&#10004;|
||Mediant 2600 SBC|&#10004;|&#10004;|Unterstützt 7.20A.258 (empfohlen 7.40A.100 oder 7.40A.250)|&#10004;|&#10004;|
||Mediant 4000 SBC|&#10004;|&#10004;|Unterstützt 7.20A.258 (empfohlen 7.40A.100 oder 7.40A.250)|&#10004;|&#10004;|
||Mediant 1000B SBC|&#10004;|&#10004;|Unterstützt 7.20A.250 (empfohlen 7.40A.100 oder 7.40A.250)|&#10004;|&#10004;|
||Mediant 9000  SBC|&#10004;|&#10004;|Unterstützt 7.20A.258 (empfohlen 7.40A.100 oder 7.40A.250)|&#10004;|&#10004;|
||Virtual Edition SBC|&#10004;|&#10004;|Unterstützt 7.20A.258 (empfohlen 7.40A.100 oder 7.40A.250)|&#10004;|&#10004;|
||Mediant Cloud Edition SBC|&#10004;|&#10004;|Unterstützt 7.20A.258 (empfohlen 7.40A.100 oder 7.40A.250)|&#10004;|&#10004;|
|[Menübandkommunikation](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-skype-business)|SBC 5100/5110|&#10004;|&#10004;|Unterstützt 9.2, 8.2 und 7.2 (Empfohlen 10.1)|&#10004;||
||SBC 5200/5210|&#10004;|&#10004;|Unterstützt 9.2, 8.2 und 7.2 (Empfohlen 10.1)|&#10004;||
||SBC 5400|&#10004;|&#10004;|Unterstützt 9.2, 8.2 und 7.2 (Empfohlen 10.1)|&#10004;||
||SBC 7000|&#10004;|&#10004;|Unterstützt 9.2, 8.2 und 7.2 (Empfohlen 10.1)|&#10004;||
||SBC SWe|&#10004;|&#10004;|Unterstützt 9.2, 8.2 und 7.2 (Empfohlen 10.1)|&#10004;||
||SBC 1000|&#10004;|&#10004;|8.x oder 9.x|&#10004;|&#10004;|
||SBC 2000|&#10004;|&#10004;|8.x oder 9.x|&#10004;|&#10004;|
||Lite SBC Schwedisch|&#10004;|&#10004;|8.x oder 9.x|&#10004;|&#10004;|
||EdgeMarc-Serie|&#10004;||15.6.1||
|[Thinktel](https://www.thinktel.ca/services/think-365/think-365-overview/)|Think 365 SBC|&#10004;||1.4|||
|[Oracle](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)|AP 1100|&#10004;|&#10004;|Unterstützt 8.3.0.0.1; empfohlen 8.4.x und 9.x|&#10004;|&#10004;|
||AP 3900|&#10004;|&#10004;|Unterstützt 8.3.0.0.1; empfohlen 8.4.x und 9.x|&#10004;|&#10004;|
||AP 4600|&#10004;|&#10004;|Unterstützt 8.3.0.0.1; empfohlen 8.4.x und 9.x|&#10004;|&#10004;|
||AP 6300|&#10004;|&#10004;|Unterstützt 8.3.0.0.1; empfohlen 8.4.x und 9.x|&#10004;|&#10004;|
||AP 6350|&#10004;|&#10004;|Unterstützt 8.3.0.0.1; empfohlen 8.4.x und 9.x|&#10004;|&#10004;|
||VME|&#10004;|&#10004;|Unterstützt 8.3.0.0.1; empfohlen 8.4.x und 9.x|&#10004;|&#10004;|
||AP 3950|&#10004;|&#10004;|Unterstützt 9.x|&#10004;|&#10004;|
||AP 4900|&#10004;|&#10004;|Unterstützt 9.x|&#10004;|&#10004;|
|[TE-SYSTEMS](https://www.anynode.de/anynode-and-microsoft-teams/)|anynode|&#10004;|&#10004;|Unterstützt 3.20 (empfohlen 4.0)|&#10004;|&#10004;|
|[Metaswitch](https://www.metaswitch.com/products/core-network/perimeta-sbc)|Perimeta-SBC|&#10004;|&#10004;|4.7 (4.9 für Medienumgehung)|&#10004;|&#10004;|
|[Cisco](https://www.cisco.com/c/en/us/solutions/enterprise/interoperability-portal/networking_solutions_products_genericcontent0900aecd805bd13d.html)|Cisco Unified Border Element (CUBE) für Router der Serie 1000 Integrated Services|&#10004;|&#10004;|Unterstützte IOS XE Amsterdam 17.2.1r (Empfohlen: 17.6.1a)|&#10004;||
||Cisco Unified Border Element (CUBE) für Router der Serie 4000 Integrated Services|&#10004;|&#10004;|Unterstützte IOS XE Amsterdam 17.2.1r (Empfohlen: 17.6.1a)|&#10004;||
||Cisco Unified Border Element (CUBE) für Cloud Services Router der 1000V-Serie|&#10004;|&#10004;|Unterstützte IOS XE Amsterdam- und 17.2.1r-Versionen (Empfohlen: 17.3.3)|&#10004;||
||Cisco Unified Border Element (CUBE) für Aggregation Services-Router der 1000-Serie|&#10004;|&#10004;|Unterstützte IOS XE Amsterdam 17.2.1r (Empfohlen: 17.6.1a)|&#10004;||
||Cisco Unified Border Element (CUBE) für 8000 Edge Platforms|&#10004;|&#10004;|Unterstützte IOS XE Amsterdam 17.3.2-Version (Empfohlen 17.6.1a)|&#10004;||
|[Avaya](https://support.avaya.com/products/P0997/avaya-session-border-controller-for-enterprise/8.1.x)|Avaya Session Border Controller for Enterprise (ASBCE)|&#10004;|&#10004;|Release 8.1.1 (8.1.2 für Medienumgehung)|||
|[Nokia](https://documentation.nokia.com/aces/cgi-bin/chk_access.cgi/3TB30222GBAAACZZA.zip)|Nokia Session Border Controller|&#10004;|&#10004;|22.0|&#10004;||
|[Italtel](https://www.italtel.com/italtel-provides-direct-routing-sbc-for-microsoft-teams/)|NetMatch-S CI|&#10004;|&#10004;|Unterstützt 5.0, 5.1 (Empfohlen 5.3)|||
|[Ericsson](https://www.ericsson.com/en/portfolio/digital-services/cloud-communication/enterprise-communication/business-communication-services-and-enablers/sip-trunking)|vSBC 2.16|&#10004;|||||
|[Cataleya](https://cataleya.com/orchidplatforms/)|Orchid-Link|&#10004;||3.1|||
|[ULTATEL](https://www.ultatel.com/services/direct-routing-teams-sbc)|Teams-SBC|&#10004;|&#10004;|1.6|||
|[Atos](https://unify.com/en/solutions/voice-platforms/session-border-controller)|Atos Unify OpenScape-Sitzungsrahmencontroller|&#10004;|&#10004;|V10R2.2.0|||
|[Sansay Inc.](https://www.sansay.com/solutions/microsoft-teams/)|vmVSXi|&#10004;|&#10004;|10.5.1.354-vm-S-x64|&#10004;||
|[Enghouse-Netzwerke](https://www.enghousenetworks.com/portfolio/network-infrastructure/cloud-native-session-border-controller-sbc/)|Dialogischer BorderNet-SBC|&#10004;|&#10004;|3.9.0-786|||
|[Patton Electronics Co.](https://www.patton.com/microsoft/)|Patton SmartNode eSBC|&#10004;||3.19.x|||
|[M5 Technologies (früher bekannt als Media5 Corporation)](https://www.m5t.com/solutions/sentinel-sbc-ms-teams-certified/)|Mediatrix Sentinel-Serie|&#10004;||DGW 48.0.2340 (Recommended DGW 48.1.2503)|||
|[Ekinops](https://www.ekinops.com/solutions/voice-data-access/microsoft-direct-routing-sbc)|Ekinops Session Border Controller (ONeSBC)|&#10004;|&#10004;|6.6.1m5ha1|||
||Ekinops Virtual Session Border Controller (ONEvSBC)|&#10004;|&#10004;|6.6.1m5ha1|||
|[46 Labs LLC](https://46labs.com/docs/hcvoice/teams/)|Hyperkonvergente Stimme|&#10004;|&#10004;|HCVoice 1.0.6|||
|[Frafos](https://www.frafos.com/ms-teams-abc-sbc)|ABC SBC|&#10004;||4.6|||

<br/>

\* **Notruf-Dienstanbieter**

- [Dynamisches Routing von Bandbreitenstandorten](https://www.bandwidth.com/partners/microsoft-teams-direct-routing/)
- [Intrado-Notfallroutingdienst (ERS)](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)
- [Intrado-Notfallgateway (EGW)](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)
- [Inteliquent](https://www.inteliquent.com/services/emergency-services/e911)

## <a name="support-for-local-media-optimization"></a>Unterstützung für die Optimierung lokaler Medien

In der folgenden Tabelle wird beschrieben, welche SBC-Anbieter [Lokale Medienoptimierung](direct-routing-media-optimization.md)unterstützen.

|Anbieter|Produkt|Softwareversion|
|:---|:---|:---|
|[AudioCodes](https://www.audiocodes.com/media/13253/connecting-audiocodes-sbc-to-microsoft-teams-direct-routing-enterprise-model-configuration-note.pdf)|Mediant 500 SBC|7.20A.256|
||Mediant 800 SBC|Unterstützt 7.20A.258 (empfohlen 7.40A.100)|
||Mediant 2600 SBC|Unterstützt 7.20A.258 (empfohlen 7.40A.100)|
||Mediant 4000 SBC|Unterstützt 7.20A.258 (empfohlen 7.40A.100)|
||Mediant 1000B SBC|Unterstützt 7.20A.258 (empfohlen 7.40A.100)|
||Mediant 9000 SBC|Unterstützt 7.20A.258 (empfohlen 7.40A.100)|
||Mediant Virtual Edition SBC|Unterstützt 7.20A.258 (empfohlen 7.40A.100)|
||Mediant Cloud Edition SBC|Unterstützt 7.20A.258 (empfohlen 7.40A.100)|
|[Ribbon SBC Core](https://support.sonus.net/display/ALLDOC/SBC+8.2+-+Configure+Local+Media+Optimization)|SBC 5110|8.2|
||SBC 5210|8.2|
||SBC 5400|8.2|
||SBC 7000|8.2|
||SBC SWe|8.2|
|[Ribbon SBC Edge](https://support.sonus.net/display/UXDOC81/Best+Practice+-+Configuring+Microsoft+Teams+Local+Media+Optimization)|SBC SWe Lite|8.1.5|
||SBC 1000|8.1.5|
||SBC 2000|8.1.5|
|[TE-SYSTEMS](https://www.anynode.de/local_media_optimization/)|anynode|4.0.1+|
|[Oracle](https://www.oracle.com/industries/communications/enterprise-communications/session-border-controller/microsoft.html)|AP 1100|8.4.0.0.0|
||AP 3900|8.4.0.0.1 und 9.x|
||AP 4600|8.4.0.0.1 und 9.x|
||AP 6300|8.4.0.0.1 und 9.x|
||AP 6350|8.4.0.0.1 und 9.x|
||VME|8.4.0.0.1 und 9.x|
||AP 3950|9.x|
||AP 4900|9.x|
|[Avaya](https://support.avaya.com/products/P0997/avaya-session-border-controller-for-enterprise/8.1.x)|Avaya Session Border Controller for Enterprise (ASBCE)|10.1.2|

## <a name="direct-routing-and-analog-devices-interoperability"></a>Direktes Routing und Interoperabilität analoger Geräte

In der folgenden Tabelle sind Geräte aufgeführt, die für Interoperabilität zwischen Direct Routing und Analog Devices verifiziert sind.

|Anbieter|Produkt|Überprüfte
|---|---|---|
|[AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)|[ATA-1](https://www.audiocodes.com/media/2373/mp-1xx-and-mp-124-datasheet.pdf)|&#10004;|
|[AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)|[ATA-2](https://www.audiocodes.com/media/2399/mediapack-20x-mp-20x-analog-telephone-adapters-datasheet.pdf)|&#10004;|
|[Cisco](https://www.cisco.com/c/en/us/products/collateral/unified-communications/ata-190-series-analog-telephone-adapters/datasheet-c78-740013.html)|ATA 191 Multiplatform Analog-Telefonadapter|&#10004;|
|[Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html)|AP 1100-Softwareversion: unterstützt 8.3.0.1.2; empfohlen 8.4.x oder 9.x|&#10004;|
|[Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html)|AP 3900-Softwareversion: unterstützt 8.3.0.1.2; empfohlen 8.4.x oder 9.x|&#10004;|
|[Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html)|AP 4600-Softwareversion: unterstützt 8.3.0.1.2; empfohlen 8.4.x oder 9.x|&#10004;|
|[Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html)|AP 6300-Softwareversion: unterstützt 8.3.0.1.2; empfohlen 8.4.x oder 9.x|&#10004;|
|[Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html)|AP 6350-Softwareversion: unterstützt 8.3.0.1.2; empfohlen 8.4.x oder 9.x|&#10004;|
|[Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html)|VME-Softwareversion: unterstützt 8.3.0.1.2; empfohlen 8.4.x oder 9.x|&#10004;|
|[Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html)|AP 3950-Softwareversion: unterstützt 9.x|&#10004;|
|[Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html)|AP 4900-Softwareversion: unterstützt 9.x|&#10004;|
|[Ribbon](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions)|[SBC 1000. Softwareversion: 8.1.1 (Build 527)](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Analog+Devices)|&#10004;|
|[Ribbon](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions)|[SBC 2000. Softwareversion: 8.1.1 (Build 527)](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Analog+Devices)|&#10004;|
|[Ribbon](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions)|[EdgeMarc 302. Softwareversion: 16.1.1](https://ribboncommunications.com/products/service-provider-products/cloud-and-edge/session-border-controllers/session-border-controllers-edge-appliances)|&#10004;|
|[Ribbon](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions)|[EdgeMarc 304. Softwareversion: 16.1.1](https://ribboncommunications.com/products/service-provider-products/cloud-and-edge/session-border-controllers/session-border-controllers-edge-appliances)|&#10004;|
|[Ribbon](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions)|[EdgeMarc 2900A. Softwareversion: 16.1.1](https://ribboncommunications.com/products/service-provider-products/cloud-and-edge/session-border-controllers/session-border-controllers-edge-appliances)|&#10004;|
|[Ribbon](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions)|[EdgeMarc 4806. Softwareversion: 16.1.1](https://ribboncommunications.com/products/service-provider-products/cloud-and-edge/session-border-controllers/session-border-controllers-edge-appliances)|&#10004;|
|[Ribbon](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions)|[EdgeMarc 4808. Softwareversion: 16.1.1](https://ribboncommunications.com/products/service-provider-products/cloud-and-edge/session-border-controllers/session-border-controllers-edge-appliances)|&#10004;|
|[Ribbon](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions)|[EdgeMarc 6000. Softwareversion: 16.1.1](https://ribboncommunications.com/products/service-provider-products/cloud-and-edge/session-border-controllers/session-border-controllers-edge-appliances)|&#10004;|
|[TE-SYSTEMS](https://www.anynode.de/anynode-and-microsoft-teams/)|anynode mit Grandstream GXW42xx (V1.0.7.10)|&#10004;|

Beachten Sie die Zertifizierung, die einer Hauptversion erteilt wurde. Das bedeutet, dass Firmware mit einer beliebigen Anzahl in der SBC-Firmware nach der Hauptversion unterstützt wird.

Feedback zu Teams, z. B. Ideen für neue Features, finden Sie im [Microsoft-Feedbackportal](https://feedbackportal.microsoft.com/).
