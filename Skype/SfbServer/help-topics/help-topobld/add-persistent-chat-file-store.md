---
title: Hinzufügen des Dateispeichers für beständigen Chat
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddPersistentChatFileStorePage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: e1068706-ff61-4a98-8e51-4202111d936a
description: Sie müssen eine Dateifreigabe angeben, die als Dateispeicher für den Standard Edition-Server oder Front-End-Pool der Enterprise Edition verwendet werden soll. Sie können als Dateispeicher eine vorhandene Dateifreigabe oder eine neue Dateifreigabe auswählen, indem Sie den vollqualifizierten Domänennamen (FQDN) des Dateiservers, auf dem sich die Dateifreigabe befindet, und einen Ordnernamen für die neue Dateifreigabe angeben.
ms.openlocfilehash: 17ef0ff681b3a583c9423c5ea693f88b35db904d
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58615741"
---
# <a name="add-persistent-chat-file-store"></a>Hinzufügen des Dateispeichers für beständigen Chat
 
Sie müssen eine Dateifreigabe angeben, die als Dateispeicher für den Standard Edition-Server oder Front-End-Pool der Enterprise Edition verwendet werden soll. Sie können als Dateispeicher eine vorhandene Dateifreigabe oder eine neue Dateifreigabe auswählen, indem Sie den vollqualifizierten Domänennamen (FQDN) des Dateiservers, auf dem sich die Dateifreigabe befindet, und einen Ordnernamen für die neue Dateifreigabe angeben.
  
> [!IMPORTANT]
> Die Dateifreigabe für Skype for Business Server kann nicht auf dem Enterprise Edition Front-End-Server, sondern auf einem Standard Edition Server gespeichert werden. 
  
> [!IMPORTANT]
> Sie können die Dateifreigabe im Topologie-Generator definieren, bevor Sie die Dateifreigabe erstellen, aber Sie müssen die Dateifreigabe am angegebenen Speicherort erstellen, ehe Sie die Topologie veröffentlichen. 
  
> [!IMPORTANT]
> Wenn Sie Ihrer Topologie einen Server für beständigen Chat oder einen Serverpool für beständigen Chat hinzufügen, muss der Topologie-Generator in der Lage sein, den Dateispeicher einzurichten und DACLs (Discretionary Access Control Lists) für die Dateifreigabe zu konfigurieren, die für den Dateispeicher verwendet werden soll. Deshalb müssen Sie bei Ausführung des Topologie-Generators zum Veröffentlichen der neuen Topologie mit einem Konto mit Vollzugriffsberechtigungen (Lesen/Schreiben/Ändern) für die Dateifreigabe angemeldet sein. 
  
## <a name="see-also"></a>Siehe auch

[Planen des Servers für beständigen Chat in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[Hinzufügen des Servers für beständigen Chat zu Ihrer Skype for Business Server 2015-Topologie](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
  
[Hardware- und Softwareanforderungen für den Server für beständigen Chat in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[Serveranforderungen für Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[Topologiegrundlagen für Skype for Business Server 2015](../../plan-your-deployment/topology-basics/topology-basics.md)
