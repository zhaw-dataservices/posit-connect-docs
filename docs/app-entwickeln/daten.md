# Datensparsamkeit & Daten

Apps auf Posit Connect sollen nur die Daten verwenden, die tatsächlich benötigt werden. Diese Seite zeigt, woher die Rohdaten für dein Dashboard kommen sollten und was zu vermeiden ist.

## Wo kommen die Rohdaten her?

Je nach Art der Daten empfehlen wir unterschiedliche Wege.

### Öffentliche Forschungsdaten

Ideal ist die Ablage in einem ORD-Repository (Open Research Data). Die App liest die Daten direkt von dort – Daten und Code bleiben getrennt und unabhängig versionierbar.

<!-- TODO: Empfohlene ORD-Repositories nennen (z. B. Zenodo, OSF, BORIS) -->

### Vertrauliche oder sensible Daten

Für vertrauliche oder personenbezogene Daten empfehlen wir REDCap. Apps können Daten direkt aus REDCap lesen. Eine gesonderte Anleitung dazu findet sich unter [REDCap-Integration](redcap.md).

### Weitere institutionelle Quellen

!!! note "In Prüfung"
    Interne Datenbanken und SharePoint sind als mögliche Quellen im Blick, die Anbindung an Posit Connect wurde aber noch nicht getestet. Diese und weitere institutionelle Optionen werden intern geprüft – Details folgen.

### Nicht empfohlen: Daten direkt im Repository

Eine Datendatei (z. B. `.RData` oder `.csv`) direkt im Code-Repository abzulegen ist technisch möglich, aber kein empfohlenes Muster: Die Daten sind nicht unabhängig vom Code versioniert, jede Aktualisierung erfordert ein Redeploy, und es besteht das Risiko, versehentlich sensible Daten einzuchecken. Falls doch nötig, dann nur für sehr kleine, statische und unkritische Datensätze als letzte Option.

## Grundsatz: Datensparsamkeit

<!-- TODO: Prinzip erklären, warum es wichtig ist -->

## Daten in der App einbinden

<!-- TODO: Wie werden Daten geladen? Direkt aus ORD-Repository, lokale Datei etc. -->

## Was nicht auf den Server gehört

<!-- TODO: Sensitive Daten, personenbezogene Daten, was ist nicht erlaubt -->
