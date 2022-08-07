---
title: Einrichten Ihrer Team-Adressierungshierarchie
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: andfried, acolonna
search.appverid: MET150
description: Erfahren Sie, wie Sie eine Teamhierarchie in Ihrer Organisation einrichten, um Inhalte in einer großen Gruppe von Teams zu veröffentlichen.
audience: admin
ms.localizationpriority: medium
appliesto:
- Microsoft Teams
ms.collection:
- M365-collaboration
ms.openlocfilehash: aa18168c9e8755a9b6b895ba48c38f8f79005177
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2022
ms.locfileid: "67271080"
---
# <a name="set-up-your-team-targeting-hierarchy"></a>Einrichten Ihrer Team-Adressierungshierarchie

Durch das Einrichten einer Teamadressierungshierarchie kann Ihre Organisation Inhalte in einer großen Gruppe von Teams veröffentlichen. Die Teamadressierungshierarchie definiert, wie alle Teams in Ihrer Hierarchie miteinander verbunden sind, welche Benutzer Aufgaben veröffentlichen können und für welche Teams Benutzer berechtigungen zum Veröffentlichen haben. Veröffentlichungsfeatures sind für alle Benutzer deaktiviert, es sei denn, für Ihre Organisation ist eine Teamadressierungshierarchie eingerichtet. Um eine Teamadressierungshierarchie einzurichten, müssen Sie eine Datei erstellen, die die Hierarchie definiert, und sie dann in Teams hochladen, um sie auf Ihre Organisation anzuwenden. Nachdem das Schema hochgeladen wurde, können Apps in Teams es verwenden.

> [!IMPORTANT]
> Für die erste Version unterstützt nur die Tasks-App hierarchische Teams.  Das Anwenden einer Teamzielhierarchie auf Ihre Organisation ermöglicht die [Veröffentlichung von Aufgaben](https://support.microsoft.com/office/publish-task-lists-to-create-and-track-work-in-your-organization-095409b3-f5af-40aa-9f9e-339b54e705df) in der Aufgaben-App. Es wird keine Hierarchie von Teams in anderen Bereichen von Microsoft Teams angezeigt.

Hier ist ein Beispiel für die Darstellung der Hierarchie in der Aufgaben-App in Teams. Nachdem eine Aufgabenliste erstellt wurde, können Mitglieder des Veröffentlichungsteams dann die Empfängerteams auswählen, an die die Aufgabenliste gesendet (veröffentlicht) werden soll. Bei der Auswahl von Teams kann das Veröffentlichungsteam nach Hierarchie, nach Attributen oder einer Kombination aus beidem filtern.<br>

![Screenshot der Aufgabenveröffentlichung.](media/manage-tasks-app-publish.png)

## <a name="terminology"></a>Terminologie

Die folgenden Begriffe sind wichtig, wenn Sie durch Hierarchien navigieren. Teams werden als **Knoten** bezeichnet.

* **Stammknoten** sind die obersten Knoten in der Hierarchie. Im Beispiel ist Retail Communications ein Stammknoten.
* **Übergeordnete Knoten** und **untergeordnete Knoten** sind Begriffe, die eine Beziehung zwischen zwei verbundenen Knoten darstellen. Im Beispiel ist "Bezirk 01" ein untergeordneter Knoten von Bereich 1.
* Mehrere Ebenen von untergeordneten Elementen werden als **Nachfolger** bezeichnet. District 01, Store 01, Store 03, Store 07, District 02 und District 03 sind alle Nachfolger von Area 1.
* Ein Knoten ohne untergeordnete Elemente wird als **Blattknoten** bezeichnet. Sie befinden sich am Ende einer Hierarchie.
* **Empfängerteams** sind Teams, die ausgewählt wurden, um einen bestimmten Satz von Inhalten zu erhalten, die veröffentlicht werden sollen. Sie müssen Blattknoten sein.

## <a name="plan-your-hierarchy"></a>Planen Der Hierarchie

Bevor Sie das Schema erstellen, das Ihre Hierarchie definiert, müssen Sie planen und entscheiden, wie Sie Ihre Organisation gestalten möchten.  Eine der ersten Prioritäten ist die Entscheidung, welche Organisationsgruppen Aufgaben für andere Gruppen veröffentlichen müssen. Jeder Knoten in der Hierarchie stellt eine Arbeitsgruppe oder Gruppe von Gruppen dar.

### <a name="permissions-to-publish"></a>Berechtigungen zum Veröffentlichen

Die Berechtigung zum Veröffentlichen hängt davon ab, ob ein Benutzer Mitglied von Teams in der Hierarchie ist, sowie von der Beziehung dieses Teams oder teams zu anderen Teams in der Hierarchie.

> [!NOTE]
> Dem Besitzer eines Teams werden auch Veröffentlichungsberechtigungen erteilt.

* Wenn ein Benutzer Mitglied mindestens eines Teams ist, das über Nachfolger in der Hierarchie verfügt, kann dieser Benutzer in diesen Nachfolgern veröffentlichen, ohne Mitglied aller Teams zu sein, in denen er veröffentlichen möchte.
* Wenn ein Benutzer Mitglied eines mindestens eines Teams in der Hierarchie ist, aber kein Mitglied eines Teams mit Nachfolgern in der Hierarchie ist, kann dieser Benutzer veröffentlichte Inhalte aus seiner Organisation sehen und empfangen.
* Wenn ein Benutzer kein Mitglied eines Teams in der Hierarchie ist, wird diesem Benutzer keine veröffentlichungsbezogene Funktionalität angezeigt.

### <a name="guidelines"></a>Richtlinien

* Pro Organisation kann nur eine Hierarchiedatei angewendet werden. Sie können jedoch verschiedene Teile Ihrer Organisation als unterschiedliche Hierarchien von Knoten innerhalb einer Datei zusammenschließen. Beispielsweise hat Contoso Pharmaceuticals einen Apothekenstammknoten und einen Retail-Stammknoten. Beide Stammknoten haben mehrere Zeilen von Nachfolgern, und es gibt keine Überlappung zwischen ihnen.
* Nur Blattknoten können Empfänger einer Publikation sein. Andere Knoten in der Hierarchie sind hilfreich, um Empfänger einer Publikation auszuwählen.
* Ein Team kann nur einmal in einer Hierarchie dargestellt werden.
* Eine Hierarchie kann bis zu 15.000 Knoten enthalten. Wir planen, mit Kunden zusammenzuarbeiten, um diesen Grenzwert für größere Organisationen zu erhöhen.

### <a name="example-hierarchy"></a>Beispielhierarchie

In der folgenden Hierarchie können z. B. "Rückruf", "Kommunikation" und "Personalwesen" Aufgaben an jedem unteren Knoten (Team) in der Hierarchie veröffentlichen, "Northeast Zone" kann jedoch nur Aufgaben im New York Store und im Boston Store veröffentlichen. Die Beispielhierarchie ermöglicht es den Gruppen "Rückruf", "Kommunikation" und "Personalwesen", Aufgaben zu veröffentlichen, die für das gesamte Unternehmen gelten, z. B. Informationen zu Vorteilen oder Nachrichten vom CEO. Northeast Zone kann Aufgaben wie Personalplanung, Wetterinformationen usw. nur in den Teams des New York Store und des Boston Store veröffentlichen.

![Hierarchisches Teambeispiel.](media/team-targeting-schema-example-new.png)

## <a name="create-your-hierarchy"></a>Erstellen Ihrer Hierarchie

> [!NOTE]
> Im restlichen Teil dieses Artikels wird das Einrichten einer Teamhierarchie im Kontext der Veröffentlichung von Aufgaben an Empfängerteams erläutert. Eine Übersicht über die Aufgaben-App, in der die Aufgabenveröffentlichung angezeigt wird, wenn aktiviert, finden Sie unter [Verwalten der Aufgaben-App für Ihre Organisation in Teams](./manage-tasks-app.md) .

Das Schema, das Ihre Hierarchie definiert, basiert auf einer CSV-Datei (Comma-Separated Values). Die Datei muss im UTF-8-Format vorliegen. Jede Zeile in der CSV-Datei entspricht einem Knoten innerhalb der Hierarchie von Teams. Jede Zeile enthält Informationen zum Benennen des Knotens innerhalb der Hierarchie, optional eine Verknüpfung mit einem Team und Attribute, die zum Filtern von Teams in Apps verwendet werden können, die ihn unterstützen.

Sie können auch **Buckets** definieren, bei denen es sich um Kategorien handelt, die das Veröffentlichungsteam zum Organisieren von Inhalten verwenden kann, die an Empfängerteams gesendet wurden, um ihnen das Anzeigen, Sortieren und Konzentrieren auf relevante Inhalte zu erleichtern.

### <a name="add-required-columns"></a>Hinzufügen erforderlicher Spalten

Die CSV-Datei muss die folgenden drei Spalten in der folgenden Reihenfolge enthalten, beginnend bei der ersten Spalte. Ein Knoten muss mit einem Team verknüpft sein, damit er Aufgaben empfangen kann.

| Spaltenname   | Erforderlich | Beschreibung   |
----------------|----------|---------------|
| DisplayName    | Ja      | Dieses Feld ist der Name des Knotens. Der Name kann bis zu 100 Zeichen lang sein und nur die Zeichen A-Z, a-z und 0-9 enthalten. Knotennamen müssen eindeutig sein. |
| ParentName    | Ja       | Dies ist der Name des übergeordneten Knotens. Der hier angegebene Wert muss exakt mit dem Wert im **Feld "DisplayName"** des übergeordneten Knotens übereinstimmen. Wenn Sie mehr als einen übergeordneten Knoten hinzufügen möchten, trennen Sie jeden Namen des übergeordneten Knotens durch ein Semikolon (;). Sie können bis zu 25 übergeordnete Knoten hinzufügen, und jeder Übergeordnete Knotenname kann bis zu 2500 Zeichen lang sein. Ein Knoten kann nur dann mehrere übergeordnete Knoten haben, wenn es sich bei den übergeordneten Knoten um Stammknoten handelt.   <br><br>**WICHTIG** Achten Sie darauf, keine Schleife zu erstellen, bei der ein übergeordnetes Element oben in der Hierarchie auf einen untergeordneten Knoten weiter unten in der Hierarchie verweist. Dies wird nicht unterstützt. |
| TeamId        | Ja, wenn das Team Aufgaben veröffentlicht oder Aufgaben von einem übergeordneten Knoten empfängt       | Diese enthält die ID des Teams, mit dem Sie einen Knoten verknüpfen möchten. Jeder Knoten muss auf ein eindeutiges Team verweisen, sodass jeder TeamId-Wert nur einmal in der Hierarchiedatei angezeigt werden kann. Um die ID eines Teams abzurufen, mit dem Sie einen Knoten verknüpfen möchten, führen Sie den folgenden PowerShell-Befehl aus: `Get-Team | Export-Csv TeamList.csv`. Dieser Befehl listet die Teams in Ihrer Organisation auf und enthält den Namen und die ID für jedes Team. Suchen Sie den Namen des Teams, zu dem Sie einen Link erstellen möchten, und kopieren Sie dann die ID in dieses Feld.|

> [!NOTE]
> Wenn es sich bei einem Knoten nicht um einen Stammknoten oder einen Blattknoten handelt und Sie die Teammitgliedschaft nicht benötigen, um die entsprechenden Berechtigungen für Veröffentlichung und Berichterstellung zu erteilen, können Sie die TeamId leer lassen. Diese Methode kann verwendet werden, um mehr Granularität bei der Auswahl von Empfängerteams oder zum Anzeigen von Abschlussberichten ohne ein entsprechendes Team hinzuzufügen.

### <a name="add-attribute-columns"></a>Hinzufügen von Attributspalten

Nachdem Sie die drei erforderlichen Spalten hinzugefügt haben, können Sie optionale Attributspalten hinzufügen. Diese Attribute können zum Filtern von Knoten verwendet werden, sodass Sie einfacher diejenigen auswählen können, für die Sie Aufgaben veröffentlichen möchten. Es gibt zwei Möglichkeiten, Ihre Attribute zu definieren, je nachdem, ob sich Werte für dieses Attribut gegenseitig ausschließen.

|Möglichkeiten zum Hinzufügen von Attributen|Beschreibung |Beispiel  |
|---|---------|---------|
|Wenn sich die Werte für ein Attribut gegenseitig ausschließen, wird der angegebene Spaltenname zum Namen des Attributs.|Jede Zeile kann einen Wert für dieses Attribut enthalten, und jede Attributspalte kann bis zu 50 eindeutige Werte enthalten. Jeder Wert kann bis zu 100 Zeichen lang sein. Der Satz von Attributwerten, die Sie in der Attributspalte angeben, wird als Filterwerte für dieses Attribut angezeigt, wenn Empfängerteams mithilfe der Teamadressierungshierarchie ausgewählt werden.|Sie möchten, dass Benutzer Speicher nach Layout filtern können. Die Werte für dieses Attribut schließen sich gegenseitig aus, da ein Speicher nur ein Layout aufweisen kann. <br><br>Um ein Attribut zum Filtern von Speichern nach Layout hinzuzufügen, fügen Sie eine Spalte mit dem Namen "Store-Layout" hinzu. In diesem Beispiel sind die Werte für das Store-Layoutattribut "Compact", "Standard" und "Large".
|Wenn Sie mehrere Werte für ein Attribut angeben müssen und sich die Werte nicht gegenseitig ausschließen, verwenden Sie das **Attributname:UniqueValue-Format** für die Spaltennamen. <br><br>**WICHTIG** Stellen Sie sicher, dass Sie den Doppelpunkt "Nur Englisch" (:) da Unicode nicht als Attributspaltentrennzeichen unterstützt wird. |Die Textzeichenfolge vor dem Doppelpunkt (:) wird der Name des Attributs. Alle Spalten, die dieselbe Textzeichenfolge vor den Doppelpunkt enthalten (:) werden im Filtermenü zu einem Abschnitt gruppiert. Jede der Zeichenfolgen nach dem Doppelpunkt wird zu den Werten für diesen Abschnitt.<br><br>Jede Zeile kann einen Wert von 0 (Null) oder 1 für dieses Attribut aufweisen. Der Wert "0" bedeutet, dass das Attribut nicht für den Knoten gilt, und der Wert "1" bedeutet, dass das Attribut für diesen Knoten gilt.|Sie möchten, dass Benutzer Speicher nach Abteilung filtern können. Ein Speicher kann mehrere Abteilungen haben, sodass sich die Werte für dieses Attribut nicht gegenseitig ausschließen.<br><br>In diesem Beispiel fügen wir Departments:Clothing, Departments:Electronics, Departments:Foods, Departments:Home and Garden, Departments:Sporting goods als Attributspalten hinzu. Abteilungen werden zum Attributnamen, und Benutzer können nach den Abteilungen "Bekleidung", "Elektronik", "Lebensmittel", "Haus und Garten" und "Sportartikel" filtern.|

Beachten Sie beim Hinzufügen einer Attributspalte Folgendes:

* Der angegebene Spaltenname oder der Spaltenname, den Sie vor dem Doppelpunkt angeben (:) wird der Name des Attributs. Dieser Wert wird in den Teams-Apps angezeigt, die die Hierarchie verwenden.
* In Der Hierarchie können bis zu 50 Attributspalten vorhanden sein.
* Der Spaltenname kann bis zu 100 Zeichen lang sein und nur die Zeichen A-Z, a-z und 0-9 sowie Leerzeichen enthalten. Spaltennamen müssen eindeutig sein.

### <a name="add-bucket-columns"></a>Hinzufügen von Bucketspalten

Sie können Bucketspalten hinzufügen, um Buckets zu erstellen, bei denen es sich um Gruppierungen handelt, in denen Aufgaben organisiert werden können. Jeder Bucket erhält eine eigene Spalte in der CSV-Datei. Die von Ihnen erstellten Buckets werden dem Veröffentlichungsteam zur Verfügung gestellt. Das Veröffentlichungsteam kann dann diese Buckets verwenden, um Aufgaben für die Empfängerteams zu kategorisieren. Wenn noch kein Bucket in einem Team vorhanden ist, werden Buckets bei Bedarf erstellt, wenn Aufgaben veröffentlicht werden.

Indem die Arbeitselemente einmal zentral kategorisiert werden, kann das Veröffentlichungsteam die Aufgabenliste für alle Zehn-, Hunderte- oder Tausende von Empfängerteams, die die Aufgabenliste erhalten, vorab organisieren. Die Empfängerteams können dann ihre Aufgaben nach Bucket sortieren und filtern, um sich auf den Bereich zu konzentrieren, der für ihre Arbeit am relevantesten ist.

Wenn Sie eine Bucketspalte hinzufügen, beachten Sie Folgendes:

* Der Spaltenname wird zum Namen des Buckets. Jeder von Ihnen angegebene Bucket wird in der Buckets-Liste in den Teams-Apps angezeigt, die die Hierarchie verwenden.
* Es wird empfohlen, vertrauliche Informationen nicht in Bucketnamen einzuschließen. Derzeit können Veröffentlichungsteams einen Bucket nach der Erstellung nicht mehr durch die Veröffentlichung entfernen.
* Dem Spaltennamen muss ein Hashtag (#) vorangestellt sein. Er kann bis zu 100 Zeichen lang sein und nur die Zeichen A-Z, a-z und 0-9 enthalten. Beispielsweise #Operations und #Frozen Waren.
* Eine Hierarchie kann bis zu 25 Bucketspalten enthalten. Wir planen, mit Kunden zusammenzuarbeiten, um diesen Grenzwert für größere Organisationen zu erhöhen.

### <a name="example"></a>Beispiel

Hier sehen Sie ein Beispiel für eine CSV-Schemadatei, die erstellt wurde, um die in der vorherigen Abbildung gezeigte Hierarchie zu unterstützen. Dieses Schema enthält Folgendes:

* Drei erforderliche Spalten mit dem Namen `TargetName`, `ParentName`und `TeamId`
* Drei Attributspalten mit dem Namen `Store layout`, `Departments:Clothing`und `Departments:Foods`
* Drei Bucketspalten mit dem Namen `Fresh Foods`, `Frozen Foods`und `Women's Wear`

Das `Store layout` Attribut weist Werte auf, die enthalten `Compact`, `Standard`und `Large`. Die `Departments` Attributspalten können auf einen Wert von `0` (Null) oder `1`festgelegt werden. Das `Store` Layout und `Departments` die Attribute werden in der abbildung oben nicht angezeigt. Sie werden hier hinzugefügt, um zu zeigen, wie Attribute zu Knoteneinträgen hinzugefügt werden können. Dasselbe gilt für die drei Bucketspalten.

```CSV
TargetName,ParentName,TeamId,Store layout,Departments:Clothing,Departments:Foods,#Fresh Foods,#Frozen Foods,#Women's Wear
Recall,,db23e6ba-04a6-412a-95e8-49e5b01943ba,,,,,,
Communications,,145399ce-a761-4843-a110-3077249037fc,,,,,,
HR,,125399ce-a761-4983-a125-3abc249037fc,,,,,,
East Regional Office,HR;Communications;Recall,,,,,,,
West Regional Office,HR;Communications;Recall,,,,,,,
Northeast Zone,East Regional Office,,,,,,,
Southeast Zone,East Regional Office,,,,,,,
New York Store,Northeast Zone,e2ba65f6-25e7-488b-b8f0-b8562d5de60a,Large,1,1,,,
Boston Store,Northeast Zone,0454f08a-0507-437c-969a-682eb2fae7fc,Standard,1,1,,,
Miami Store,Southeast Zone,619d6e4e-5f68-4b36-8e1f-16c98d7396c1,Compact,0,1,,,
New Orleans Store,Southeast Zone,6be960b8-72af-4561-a343-9ac4711874eb,Compact,0,1,,,
Seattle Store,West Regional Zone,487c0d20-4e55-4dc2-8187-a24c826e0fee,Standard,1,1,,,
Los Angeles Store,West Regional Zone,204a1287-2efb-4a8a-88e0-56fbaf5a2389,Large,1,1,,,
```

## <a name="apply-your-hierarchy"></a>Anwenden der Hierarchie

> [!NOTE] 
> Um diesen Schritt auszuführen, müssen Sie das öffentliche Vorschaumodul von Teams PowerShell aus dem PowerShell-Katalog installieren und verwenden. Die Schritte zum Installieren des Moduls finden Sie unter Installieren von Teams PowerShell.

> [!NOTE]
> Gcc-Kunden (Government Community Cloud) müssen [die Cmdlet-Vorschauversion 2.4.0-Vorschau](https://www.powershellgallery.com/packages/MicrosoftTeams/2.4.0-preview) oder höher verwenden, um sicherzustellen, dass Daten an die GCC-Umgebung und nicht an die öffentliche Cloudumgebung weitergeleitet werden.

Nachdem Sie Ihre Hierarchie in der CSV-Schemadatei definiert haben, können Sie sie in Teams hochladen. Führen Sie dazu den folgenden Befehl aus. Sie müssen ein globaler Administrator oder Teams-Dienstadministrator sein, um diesen Schritt ausführen zu können.

```powershell
Set-TeamTargetingHierarchy -FilePath "C:\ContosoTeamSchema.csv"
```

### <a name="update-your-hierarchy"></a>Aktualisieren Der Hierarchie

Sie können eine neue Hierarchie hochladen, um die alte mit demselben PowerShell-Befehl wie oben zu ersetzen. Jedes Mal, wenn Sie eine neue Hierarchie hochladen, ersetzt sie die vorherige Hierarchie.

### <a name="check-the-status-of-your-hierarchy"></a>Überprüfen des Status Ihrer Hierarchie

Sie können den folgenden Befehl ausführen, um den Status des Hierarchieuploads zu überprüfen.

```powershell
Get-TeamTargetingHierarchyStatus
```

Der Befehl gibt die folgenden Felder zurück:

Feld|Beschreibung
-----|------------
Id | Die eindeutige ID für den Upload.
Status | Uploadstatus. Zu den Werten zählen **"Starten**", **"Überprüfen"**, "**Erfolgreich**" und **"Fehlgeschlagen"**.
ErrorDetails | Details, wenn ein Uploadfehler vorliegt. Weitere Informationen zu den Fehlerdetails finden Sie im Abschnitt "Problembehandlung". Wenn kein Fehler auftritt, ist dieses Feld leer.
LastUpdatedAt | Zeitstempel und Datum der letzten Aktualisierung der Datei.
LastModifiedBy | Die ID des letzten Benutzers, der die Datei geändert hat.
FileName | Der Dateiname der CSV-Datei.

## <a name="remove-your-hierarchy"></a>Entfernen Der Hierarchie

Wenn Sie die Registerkarte **"Veröffentlichte Listen** " für alle Benutzer in Ihrer Organisation sofort deaktivieren möchten, können Sie Ihre Hierarchie entfernen. Benutzer haben keinen Zugriff auf die Registerkarte **"Veröffentlichte Listen** " oder eine der Funktionen auf der Registerkarte.  Dies umfasst die Möglichkeit, neue Aufgabenlisten zum Veröffentlichen, Zugreifen auf Entwurfslisten, Veröffentlichen, Aufheben der Veröffentlichung und Duplikate von Listen sowie zum Anzeigen von Berichten zu erstellen. Durch das Entfernen der Hierarchie werden die Veröffentlichungen von Aufgaben, die zuvor veröffentlicht wurden, nicht aufgehoben. Diese Aufgaben bleiben für Empfängerteams verfügbar.

Führen Sie den folgenden Befehl aus, um ihre Hierarchie zu entfernen. Sie müssen ein Administrator sein, um diesen Schritt ausführen zu können.

```powershell
Remove-TeamTargetingHierarchy
```

Beim Bestätigen des Löschvorgangs wird in der Statusmeldung weiterhin angezeigt, dass das vorherige Schema vorhanden ist, obwohl beim erneuten Löschen ein Fehler zurückgegeben wird, dass das Objekt null ist.

## <a name="create-a-sample-hierarchy"></a>Erstellen einer Beispielhierarchie

### <a name="install-the-teams-powershell-module"></a>Installieren des Teams PowerShell-Moduls

> [!IMPORTANT]
> Um diesen Schritt auszuführen, müssen Sie das öffentliche Vorschaumodul von Teams PowerShell aus dem [PowerShell-Katalog](https://www.powershellgallery.com/packages/MicrosoftTeams/) installieren und verwenden. Die Schritte zum Installieren des Moduls finden Sie unter [Installieren von Teams PowerShell](teams-powershell-install.md).

### <a name="sample-script"></a>Beispielskript

Das folgende Skript kann verwendet werden, um die Teams zu erstellen und eine .csv Datei in Ihren Microsoft Teams-Mandanten hochzuladen. Wenn Sie über eine vorhandene Hierarchie verfügen, wird sie durch dieses Skript ersetzt.

#### <a name="create-teams-for-a-simple-hierarchy"></a>Erstellen von Teams für eine einfache Hierarchie

```powershell
$tm1 = New-Team -DisplayName "HQ"
$tm2 = New-Team -DisplayName "North"
$tm3 = New-Team -DisplayName "Store 1"
$tm4 = New-Team -DisplayName "Store 2"
$tm5 = New-Team -DisplayName "South"
$tm6 = New-Team -DisplayName "Store 3"
$tm7 = New-Team -DisplayName "Store 4"
```

#### <a name="use-team-data-to-create-comma-separated-output-displayname-parentname-teamid"></a>Verwenden von Teamdaten zum Erstellen einer durch Trennzeichen getrennten Ausgabe (DisplayName, ParentName, TeamId)

```powershell
$csvOutput = "DisplayName" + "," + "ParentName" + "," + "TeamId" + "`n"
$csvOutput = $csvOutput + $tm1.DisplayName + "," + "," + $tm1.GroupID + "`n"
$csvOutput = $csvOutput + $tm2.DisplayName + "," + $tm1.DisplayName + "," + $tm2.GroupID + "`n"
$csvOutput = $csvOutput + $tm3.DisplayName + "," + $tm2.DisplayName + "," + $tm3.GroupID + "`n"
$csvOutput = $csvOutput + $tm4.DisplayName + "," + $tm2.DisplayName + "," + $tm4.GroupID + "`n"
$csvOutput = $csvOutput + $tm5.DisplayName + "," + $tm1.DisplayName + "," + $tm5.GroupID + "`n"
$csvOutput = $csvOutput + $tm6.DisplayName + "," + $tm5.DisplayName + "," + $tm6.GroupID + "`n"
$csvOutput = $csvOutput + $tm7.DisplayName + "," + $tm5.DisplayName + "," + $tm7.GroupID 
```

#### <a name="save-output-to-a-csv-file-in-the-downloads-folder"></a>Speichern der Ausgabe in einer .csv Datei im Ordner **"Downloads** "

```powershell
$csvOutputPath = $env:USERPROFILE + "\downloads\testhierarchy-" + (Get-Date -Format "yyyy-MM-dd-hhmmss") + ".csv" 
$csvOutput | Out-File $csvOutputPath
```

#### <a name="upload-the-hierarchy"></a>Hochladen der Hierarchie

```powershell
Set-TeamTargetingHierarchy -FilePath $csvOutputPath
Get-TeamTargetingHierarchyStatus
```

## <a name="troubleshooting"></a>Problembehandlung

### <a name="how-to-view-error-details"></a>Anzeigen von Fehlerdetails

Sie können den folgenden Befehl ausführen, um zu verstehen, was einen Fehler verursacht, und die Fehlerdetails zurückzugeben.

```powershell
(Get-TeamTargetingHierarchyStatus).ErrorDetails.ErrorMessage
```

### <a name="you-receive-an-error-message-when-you-upload-your-schema-csv-file"></a>Beim Hochladen der CSV-Schemadatei wird eine Fehlermeldung angezeigt.

Notieren Sie sich die Fehlermeldung, da sie Informationen zur Problembehandlung enthalten sollte, um anzugeben, warum das Schema nicht hochgeladen werden konnte. Überprüfen und bearbeiten Sie Die CSV-Schemadatei basierend auf den Informationen in der Fehlermeldung, und versuchen Sie es dann erneut.

### <a name="you-receive-an-error-invalidteamid-error-message-when-you-upload-your-schema-csv-file"></a>Beim Hochladen der CSV-Schemadatei wird die Fehlermeldung "Fehler: InvalidTeamId" angezeigt.

Wenn Sie versuchen, Ihre CSV-Schemadatei hochzuladen, wird die folgende Fehlermeldung angezeigt:

```console
Error: InvalidTeamId
Description: TeamID in row # doesn't match a valid Group ID. Please view our documentation to learn how to get the proper GroupID for each team.
```

Stellen Sie sicher, dass Sie die richtige TeamId für das Team in Ihrer CSV-Schemadatei verwenden. Die TeamId sollte mit der Gruppen-ID der Microsoft 365-Gruppe übereinstimmen, die das Team unterstützt. Sie können die Gruppen-ID des Teams im Microsoft Teams Admin Center nachschlagen.

1. Wechseln Sie im linken Navigationsbereich des [Microsoft Teams Admin Centers](https://admin.teams.microsoft.com/) zu **Teams** > **Verwalten von Teams**.
2. Wenn die **Spalte "Gruppen-ID** " in der Tabelle nicht angezeigt wird, wählen Sie " **Spalten bearbeiten"** in der oberen rechten Ecke der Tabelle aus, und aktivieren Sie dann die **Gruppen-ID**.
3. Suchen Sie das Team in der Liste, und suchen Sie dann die Gruppen-ID.

Stellen Sie sicher, dass die TeamId in Ihrer CSV-Schemadatei der Gruppen-ID entspricht, die im Microsoft Teams Admin Center angezeigt wird.

## <a name="related-topics"></a>Verwandte Themen

* [Verwalten der Aufgaben-App für Ihre Organisation in Teams](manage-tasks-app.md)
* [Übersicht über PowerShell für Microsoft Teams](teams-powershell-overview.md)
