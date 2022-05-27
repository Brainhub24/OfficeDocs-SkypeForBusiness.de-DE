---
title: SIS-Daten (Schülerinformationssystem) mit Education Insights synchronisieren
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: karsmith
description: SIS-Daten (Schülerinformationssystem) mit Education Insights in Microsoft Teams synchronisieren.
ms.localizationpriority: high
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 25ab96f30aca6bee084a4bac7304ababe3a0660c
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675877"
---
# <a name="sync-student-information-system-sis-data-with-education-insights"></a>SIS-Daten (Schülerinformationssystem) mit Education Insights synchronisieren

Je mehr Daten in [Education Insights](class-insights.md) eingespeist werden, desto besser können Dozenten Ihre Schüler/Studenten sowie Schulleiter ihre Dozenten unterstützen.

Um Einblicke auf Organisationsebene bereitzustellen, müssen wir [School Data Sync (SDS)](/SchoolDataSync) verwenden, um eine Verbindung mit dem Schülerinformationssystem (SIS) herzustellen, damit Insights die hierarchische Struktur des Bildungssystems richtig zugeordnet ist.

Dies ist *nicht* erforderlich für das Anzeigen von Insights auf Klassenebene als Dozent der Klasse, weil wir die Klassenstruktur und Berechtigungen von Teams verwenden.

## <a name="plan-your-school-data-sync-integration"></a>Planen der School Data Sync (SDS) Integration

Microsoft School Data Sync (SDS) stellt die Daten für das Studenteninformationssystems (SIS) und dessen hierarchische Struktur des Bildungssystems bereit, und bildet ab, welcher Benutzer wo zugewiesen ist, und liefert zusätzliche Daten zur Hierarchie von Lernenden und Organisationen.

Insights funktioniert am besten bei Verwendung des [SDS V2.1-Dateiformats](/schooldatasync/sds-v2.1-csv-file-format), unterstützt aber auch das [SDS V2-Dateiformat](/schooldatasync/sds-v2-csv-file-format) und das  [SDS V1-Dateiformat](/schooldatasync/school-data-sync-format-csv-files-for-sds) *mit eingeschränkter Funktionalität*.

### <a name="differences-between-sds-v1-and-v2-file-formats"></a>Unterschiede zwischen den Dateiformaten SDS V1 und V2

| Datentyp | V1 | V2 und V2.1 |
|:--- |:--- |:--- |
| **Benutzer** |Unterstützt nur die Rolle „Dozent“, daher müssen Berechtigungen auf Organisationsebene für Ihre Schulleiter manuell festgelegt werden.|Unterstützt mehrere Rollen, sodass rollenbasierte Berechtigungen festgelegt werden können|
| **Organisationen** | Unterstützt nur „Schulen“, Aggregationsebene.<br><br>Daher werden nicht mehrere Aggregationsebenen bereitgestellt, und es ist nur eingeschränkt möglich, verschiedene Schultypen zu vergleichen (z. B. Primäre und sekundäre Bildungseinrichtung, wissenschaftliche und künstlerische Bildungseinrichtung).|Unterstützt eine Hierarchie mit mehreren Ebenen einschließlich Bezirk/Institution, Universitäten, Hochschulen, Fakultäten, Campus, Regionen, Programme usw.<br><br>Ermöglicht mehrere Aggregationsebenen und den einfachen Vergleich zwischen Organisationseinheiten auf jeder Ebene, das Zuweisen von Berechtigungen zu bestimmten Ebenen, das Festlegen von Zielen nach Organisationsebene usw.|
| **Zusätzliche optionale Informationen** |Keine|**Nur V2.1-Dateiformat**<br><br>*Akademische Sitzungen* – Zeitrahmen für Sitzungen (Semester, Schuljahre usw.)<br><br>Demografische Daten und Schüler/Studentenflags* – Daten wie Herkunft, ethnische Zugehörigkeit und Geschlecht sowie spezielle Programme (IEP, 504)|

> [!NOTE]
> Kunden können ab dem 15. Juli 2021 kein Onboarding des Dateiformats V2 durchführen und müssen stattdessen das V2.1-Format verwenden. Alle zukünftigen Upgrades und neuen Funktionen werden im V2.1-Format durchgeführt und sind vollständig abwärtskompatibel mit dem Dateiformat V1.

### <a name="best-practices"></a>Bewährte Methoden

Die genaue Abbildung der Hierarchie und die Zuordnung der Personen innerhalb dieser Hierarchie ermöglicht es Insights, genaue Daten und präzisere und relevantere Einblicke für die verschiedenen Typen von Ausbildungsleitern zu liefern.

Je mehr Details Sie hier bereitstellen, desto besser und relevanter werden die Berichte und Spotlights sein.

#### <a name="file-format-version-to-use-adn-data-to-sync"></a>Zu verwendende Dateiformatversion und zu synchronisierende Daten

- Verwenden Sie das Dateiformat V2.1, und synchronisieren Sie die optionalen Daten, die von Education Insights verwendet werden, wie [hier](/schooldatasync/sds-for-insights-overview#education-insights-capabilities-matrix-and-sds-v21-csv) beschrieben.

#### <a name="users-and-roles"></a>Benutzer und Rollen

- Vergewissern Sie sich, dass **alle Benutzer in den Dateien aufgeführt sind**, die Sie bereitstellen und synchronisieren. Dies schließt alle Schüler/Studenten und Mitarbeiter ein, die Daten aus den für sie relevanten Organisationseinheiten sehen müssen.
- Wenn im SIS derzeit nur Dozenten aufgelistet sind, fügen Sie alle anderen Benutzer manuell hinzu, bevor Sie die Dateien in SIS hochladen und die Daten synchronisieren. Die von Insights gesammelten Statistiken stammen nur von den registrierten Schüler/Studenten. Wenn einige Schüler/Studenten fehlen, führt dies zu irreführenden Daten und Schlussfolgerungen.

- Wenn Sie SDS auch für die Bereitstellung verwenden, stellen Sie sicher, dass Sie **den Vor- und Nachnamen jedes Benutzers angeben**. Andernfalls wird auf die Schüler/Stuenten anhand ihre E-Mail-Adresse referenziert, was zu einer nicht optimalen Erfahrung führt.

- Die Klassen-/Jahrgangsstufe muss auf dieser [Zuordnungsliste](#supported-grade-level-values)basieren.

- Stellen Sie sicher, dass sie **allen Schülern/Studenten die Klassen-/Jahrgangsstufe hinzufügen** .

- Stellen Sie sicher, dass **jeder Benutzer der entsprechenden Organisationseinheit zugewiesen wird**.

  - Ein Schüler/Student kann mehr als einer Organisationseinheit zugeordnet werden, z. B. Schüler/Studenten, die in einem speziellen Programm oder an zwei Fakultäten eingeschrieben sind. Falls der Schüler/Student mehr als einer Organisationseinheit zugefügt ist, geben Sie für jede eine Zeile in der Benutzerdatei für diesen Schüler/Studenten an.

  - Der IT-Administrator kann basierend auf der Organisationseinheit Berechtigungen für Mitarbeiter erteilen. **Stellen Sie sicher, dass die Mitarbeiter der richtigen Einheitenebene** zugeordnet sind, damit sie die erforderlichen Berechtigungen erhalten. Zum Beispiel muss ein Beratungslehrer, der vier Schulen zugewiesen ist, alle Noten in diesen Schulen sehen; ein Schulleiter muss alle Klassen in seiner Schule sehen.

- **Die Rolle ist wichtig**. Obwohl diese Liste geschlossen ist, versuchen Sie, die Rolle aus [der Liste](/schooldatasync/sds-v2-csv-file-format#enumerated-values-enum-supported) mit der tatsächlichen Rolle jedes Benutzers abzustimmen, den Sie hochladen. Auf diese Weise können Sie rollenbasierte Berechtigungen entsprechend zuweisen. Geben Sie z. B. allen Schuldirektoren die Berechtigung, die Klassen in ihrer Schule zu sehen, oder allen Professoren, ihre Fakultät zu sehen.

#### <a name="organizations"></a>Organisationen

- Stellen Sie sicher, dass **die tatsächliche und vollständige Hierarchie Ihrer Organisation** widergespiegelt wird. In einigen Fällen wird diese Hierarchie nicht im SIS widergespiegelt. In diesem Fall muss sie vor der Synchronisierung manuell der CSV-Datei hinzugefügt werden.

- Stellen Sie sicher, dass **alle Organisationseinheiten entlang der Organisationsstruktur Schüler/Studenten oder Klassen enthalten**. Es wird empfohlen, dass Schüler/Studenten der untersten Organisationsebene zugewiesen werden.

> [!NOTE]
> Weitere Details zur SDS-Bereitstellung finden Sie unter [SDS planen](/schooldatasync/planning-school-data-sync).

## <a name="integrate-sis-data-using-sds"></a>Integrieren von SIS-Daten mit SDS

School Data Sync (SDS) wird mit Office 365 Education bereitgestellt. SDS liest die Daten aus dem Schülerinformationssystem (SIS) einer Bildungseinrichtung und integriert sie in Microsoft-Anwendungen wie Teams, um die automatische Erstellung von Onlineklassen und Benutzern zu ermöglichen.

Außerdem werden die SIS-Daten mit Insights synchronisiert.

Als IT-Administrator können wählen, ob Sie SDS nur für die Bereitstellung, nur Insights oder für beides verwenden.

Um Ihre SIS-Informationen mit Educations Insights zu synchronisieren, befolgen Sie die Anweisungen in [Bereitstellen von SDS for Insights](/schooldatasync/how-to-deploy-sds-for-insights).

### <a name="deploy-sds"></a>Bereitstellen von SDS

**Wenn Sie SDS bereits verwenden**, empfiehlt es sich, unsere [bewährten Methoden](#best-practices) zu berücksichtigen.

**Wenn Sie SDS noch nicht verwenden**, müssen Sie es jetzt [bereitstellen](/schooldatasync/deploying-school-data-sync).

Während des Bereitstellungsprozesses können Sie entscheiden, ob Sie SDS für die Bereitstellung von Benutzern und Klassen in Teams oder nur zur Bereitstellung der Benutzer- und Organisationshierarchie für Insights verwenden möchten.

> [!NOTE]
> Wenn es Mitte des Jahres ist und Sie Teams bereits manuell erstellt haben, verwenden Sie SDS nur, um die Benutzer- und Organisationshierarchiedaten für Insights bereitzustellen, und erwägen Sie im nächsten Jahr, SDS auch für die Bereitstellung von Benutzern und Klassen in Teams zu verwenden.

### <a name="verify-the-sync-process"></a>Überprüfen des Synchronisierungsprozesses

Um den Fortschritt des Synchronisierungsstatus zu überprüfen, befolgen Sie die Anweisungen in [SDS for Insights Datenintegrität und -Überwachung](/schooldatasync/sds-for-insights-data-health-and-monitoring).

> [!IMPORTANT]
> Wenn Probleme auftreten, hilft Ihnen der [Kundendienst](https://aka.ms/edusupport) gerne weiter.

## <a name="supported-grade-level-values"></a>Unterstützten Klassenebenen-Werte

In den SDB-Dateien wird die Klassen-/Jahrgangsstufe als Aufzählungswerte definiert. Dies bedeutet, dass Sie nur einen ausgewählten Satz von Werten in der CSV-Datei angeben können. Alles andere als die angegebenen Werte führt zu einem Fehler bei der Synchronisierungsverarbeitung.

Der folgende Abschnitt definiert die unterstützten Werte in der Datei des Benutzers.

### <a name="united-states--worldwide-grade-levels"></a>Vereinigte Staaten / weltweite Klassenstufen

|Wert in der Datei (Spalte Klasse) | Bezeichnung in Insights|
|---|---|
|IT|Säugling|
|PR|Vorschule|
|PK|Vor-Kindergarten|
|TK|Übergangskindergarten|
|KG|Kindergarten|
|01 oder 1|Erste Klasse|
|02 oder 2|Zweite Klasse|
|03 oder 3|Dritte Klasse|
|04 oder 4|Vierte Klasse|
|05 oder 5|Fünfte Klasse|
|06 oder 6|Sechste Klasse|
|07 oder 7|Siebte Klasse|
|08 oder 8|Achte Klasse|
|09 oder 9|Neunte Klasse|
|10|Zehnte Klasse|
|11|Elfte Klasse|
|12|Zwölfte Klasse|
|PS|Post-Sekundär|
|PS1|Studienanfänger|
|PS2|Stundent/Studentin im zweiten Studienjahr|
|PS3|Post-Sekundärer im dritten Studienjahr|
|PS4|Post-Sekundärer im vierten Studienjahr|
|Bachelor-Student|Bachelor-Student|
|Master-Student|Master-Student|
|Doktorand|Doktorand (Absolvent mit Schwerpunkt Forschung)|
|Ehemaliger|Ehemaliger|
|Erwachsenenbildung|Erwachsenenbildung|
|UG|Nicht bewertet|
|Andere|Andere|

### <a name="united-kingdom-year-groups"></a>Vereinigtes Königreich Jahrgangsgruppen

|Wert in der Datei (Spalte Klasse) | Bezeichnung in Insights|
|---|---|
|IT|Kindergarten|
|PR|Vorschule|
|PK|Empfang|
|01 oder 1|Jahr 1|
|02 oder 2|Jahr 2|
|03 oder 3|Jahr 3|
|04 oder 4|Jahr 4|
|05 oder 5|Jahr 5|
|06 oder 6|Jahr 6|
|07 oder 7|Jahr 7|
|08 oder 8|Jahr 8|
|09 oder 9|Jahr 9|
|10|Jahr 10|
|11|Jahr 11|
|12|Jahr 12|
|13|Jahr 13|
|PS|Post-Sekundär|
|PS1|Post-Sekundär Jahr 1|
|PS2|Post-Sekundär Jahr 2|
|PS3|Post-Sekundär Jahr 3|
|PS4|Post-Sekundär Jahr 4|
|Bachelor-Student|Bachelor-Student|
|Master-Student|Master-Student|
|Doktorand|Doktorand (Absolvent mit Schwerpunkt Forschung)|
|Ehemaliger|Ehemaliger|
|Erwachsenenbildung|Erwachsenenbildung|
|UG|Nicht bewertet|
|Andere|Andere|
