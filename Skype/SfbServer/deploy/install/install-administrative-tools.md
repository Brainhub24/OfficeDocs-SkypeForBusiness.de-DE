---
title: Installieren von Verwaltungstools in Skype for Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 7/14/2018
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
ms.assetid: 52ee7da4-59ba-499a-a105-d93fa9941334
description: 'Zusammenfassung: Erfahren Sie, wie Sie die für eine Installation von Skype for Business Server erforderlichen Verwaltungstools installieren.'
ms.openlocfilehash: e18ad5953eb063cdb91ea2927ad03ed1057c840a
ms.sourcegitcommit: e99471689ff60f9ab1095bc075f8b4c5569c9634
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2022
ms.locfileid: "65860526"
---
# <a name="install-administrative-tools-in-skype-for-business-server"></a>Installieren von Verwaltungstools in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie, wie Sie die für eine Installation von Skype for Business Server erforderlichen Verwaltungstools installieren.
  
Zu den Verwaltungstools gehören der Topologie-Generator und die Systemsteuerung. Die Verwaltungstools müssen auf mindestens einem Server in der Topologie oder auf einer 64-Bit-Verwaltungsarbeitsstation installiert sein, auf der eine Windows Betriebssystemversion ausgeführt wird, die für Skype for Business Server unterstützt wird. Sie können die Schritte 1 bis 5 in beliebiger Reihenfolge ausführen. Sie müssen jedoch die Schritte 6, 7 und 8 in der reihenfolge und nach den Schritten 1 bis 5 ausführen, wie im Diagramm dargestellt. Die Installation der Verwaltungstools ist Schritt 3 von 8.
  
![Übersichtsdiagramm.](../../media/d856afe8-4758-432f-bc45-e1956016419a.png)
  
## <a name="install-skype-for-business-server-administrative-tools"></a>Installieren Skype for Business Server Verwaltungstools

Das Installationsmedium für Skype for Business Server bietet eine flexible Benutzeroberfläche. Wenn Sie Setup.exe zum ersten Mal ausführen, sind der Skype for Business Server Bereitstellungs-Assistent und die Skype for Business Server-Verwaltungsshell die einzigen installierten Tools. Mithilfe dieser beiden Tools, die als Kernkomponenten bezeichnet werden, können Sie den Installationsprozess fortsetzen, bieten jedoch keine primären Funktionen für die gesamte Skype for Business Server Umgebung. Der Bereitstellungs-Assistent wird automatisch gestartet, nachdem Sie die Kernkomponenten installiert haben. Im Abschnitt des Bereitstellungs-Assistenten mit dem Titel **"Installieren von Verwaltungstools**" werden Skype for Business Server Topologie-Generator und Skype for Business Server Systemsteuerung installiert.
  
> [!IMPORTANT]
> In jeder Skype for Business Server Umgebung muss mindestens ein Server mit den installierten Verwaltungstools installiert sein. 
  
Schauen Sie sich die Videoschritte für **die Installation von Verwaltungstools an**:
  
> [!video https://www.microsoft.com/videoplayer/embed/99a5c436-963b-4eed-b423-651568c87cb1?autoplay=false]
  
### <a name="install-skype-for-business-server-administrative-tools-from-the-deployment-wizard"></a>Installieren Skype for Business Server Verwaltungstools aus dem Bereitstellungs-Assistenten

1. Fügen Sie das Skype for Business Server Installationsmedium ein. Wenn das Setup nicht automatisch beginnt, doppelklicken Sie auf **"Setup"**.
    
2. Für das Installationsmedium muss Microsoft Visual C++ ausgeführt werden. Es wird ein Dialogfeld angezeigt, in dem Sie gefragt werden, ob Sie es installieren möchten. Klicken Sie auf **Ja**.
    
3. Mithilfe von Smart Setup, einem neuen Feature in Skype for Business Server, können Sie eine Verbindung mit dem Internet herstellen, um während des Installationsvorgangs nach Updates zu suchen. Dies bietet eine bessere Erfahrung, indem Sie sicherstellen, dass Sie bei der Installation über die neuesten Updates für das Produkt verfügen. Klicken Sie auf **Installieren**, um mit der Installation zu beginnen.
    
4. Überprüfen Sie sorgfältig den Lizenzvertrag, und wenn Sie zustimmen, wählen Sie **"Ich akzeptiere die Bedingungen im Lizenzvertrag**" aus, und klicken Sie auf **"OK**".
    
5. Die Skype for Business Server Kernkomponenten werden auf dem Server installiert. 
    
    Die Kernkomponenten bestehen aus den folgenden Komponenten, wie in der Abbildung dargestellt.
    
    ![Bildschirm "Kernkomponenten in Apps".](../../media/0da1d983-4c4b-4b23-a196-c3bdba4857c6.png)
  
   - **Skype for Business Server Bereitstellungs-Assistent** Ein Bereitstellungsprogramm, das eine Startleiste für die Installation der verschiedenen Komponenten von Skype for Business Server bereitstellt.
    
   - **Skype for Business Server Verwaltungsshell** Ein vorkonfiguriertes PowerShell-Programm, das die Verwaltung von Skype for Business Server ermöglicht.
    
     Sobald die Installation der Kernkomponenten abgeschlossen ist, wird der Skype for Business Server-Bereitstellungs-Assistent automatisch gestartet, wie in der Abbildung dargestellt. 
    
     ![Skype for Business Server Bereitstellungs-Assistent.](../../media/310c3437-83f9-48fa-a1e1-9fd09009fe31.png)
  
6. Zusätzlich zu den Kernkomponenten müssen Sie auch Skype for Business Server Topologie-Generator installieren und auf mindestens einem Server in der Umgebung Skype for Business Server Systemsteuerung. Klicken Sie im Bereitstellungs-Assistenten auf **"Verwaltungstools installieren** ".
    
7. Klicken Sie auf **Weiter**, um die Installation zu starten.
    
8. Klicken Sie nach Abschluss der Installation auf **"Fertig stellen"**. Die Verwaltungstools werden nun dem Server hinzugefügt, wie in der Abbildung dargestellt.
    
    ![Skype for Business Server Verwaltungstools.](../../media/760873dd-9c87-4efb-bf98-7162d876fd18.png)
  
   - **Skype for Business Server Topologie-Generator** Ein Programm zum Erstellen, Bereitstellen und Verwalten von Topologien.
    
   - **Skype for Business Server Systemsteuerung** Ein Programm, das zum Verwalten der Installation verwendet wird.
    

