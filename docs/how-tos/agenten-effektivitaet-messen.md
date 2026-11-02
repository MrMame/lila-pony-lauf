# Effektivität von Agenten messen

Um die Leistung eines Agenten (egal ob menschlicher Mitarbeiter im Kundenservice oder digitaler KI-Agent) anhand von Statistiken objektiv zu beurteilen, teilt man die Kennzahlen (KPIs) am besten in drei Kernbereiche auf:

1. **Produktivität**
2. **Qualität**
3. **Kundenzufriedenheit**

> Eine fundierte Leistungsbeurteilung basiert nie auf einer einzelnen Statistik, sondern immer auf dem Zusammenspiel verschiedener Metriken.

## 1. Produktivität & Effizienz

*Wie viel wird geschafft?* Diese Daten zeigen, wie schnell und ressourceneffizient der Agent arbeitet.

- **Average Handling Time (AHT):** Die durchschnittliche Bearbeitungszeit pro Fall (inklusive Nachbearbeitung).
  ⚠️ Eine zu niedrige AHT kann bedeuten, dass Kunden übereilt abgefertigt werden. [[1]][serviceocean]
- **Auslastungsgrad / Occupancy Rate:** Der Prozentsatz der Arbeitszeit, den der Agent aktiv mit der Bearbeitung von Kundenanliegen verbringt. [[1]][serviceocean]
- **Anzahl gelöster Fälle:** Die Gesamtzahl der abgeschlossenen Tickets oder Anrufe in einem bestimmten Zeitraum.

## 2. Qualität & Lösungskompetenz

*Wie gut wird es gelöst?* Reine Schnelligkeit bringt nichts, wenn das Problem nicht gelöst wurde. Diese Kennzahlen messen die Genauigkeit.

- **First Contact Resolution Rate (FCR):** Die Quote der Anliegen, die bereits beim ersten Kontakt endgültig gelöst wurden. Dies ist eine der wichtigsten Kennzahlen für Servicequalität. [[1]][serviceocean]
- **Eskalationsrate:** Wie oft muss der Agent einen Fall an die nächsthöhere Ebene (z. B. Teamleiter oder menschliche Experten bei KI) weiterleiten? Eine hohe Rate deutet auf Wissenslücken hin. [[2]][kaizo]
- **Wiederwählerquote / Reopen-Rate:** Der Prozentsatz der Kunden, die sich innerhalb kurzer Zeit wegen desselben Problems erneut melden. [[1]][serviceocean]

## 3. Kundenzufriedenheit

*Wie kommt es beim Kunden an?* Die direkteste Rückmeldung über die Leistung des Agenten.

- **Customer Satisfaction Score (CSAT):** Der Zufriedenheitswert, den Kunden direkt nach der Interaktion in einer kurzen Umfrage vergeben (z. B. auf einer Skala von 1 bis 5).
- **Net Promoter Score (NPS):** Misst die langfristige Loyalität und die Wahrscheinlichkeit, dass der Kunde das Unternehmen weiterempfiehlt.
- **Sentiment-Analyse:** KI-gestützte Tools können Text- oder Sprachdaten analysieren, um die Stimmung des Kunden während des Gesprächs (von frustriert bis glücklich) statistisch auszuwerten. [[1]][serviceocean] [[2]][kaizo]

## Direktvergleich: So interpretieren Sie die Statistiken richtig

| Wenn die Statistik zeigt … | … und diese Statistik zeigt … | Dann bedeutet das meistens: | Maßnahme |
|---|---|---|---|
| Niedrige AHT (schnell) | Niedrige FCR (oft wiederholt) | Der Agent würgt Kunden ab, ohne das Problem wirklich nachhaltig zu lösen. | Qualitätsschulung, Fokus auf Gründlichkeit statt Schnelligkeit. |
| Hohe AHT (langsam) | Hohe CSAT & FCR (sehr zufrieden) | Der Agent ist sehr gründlich und kundenorientiert, braucht aber eventuell zu lange für Standardprozesse. | System-Schulung, Nutzung von Textbausteinen prüfen. |
| Hohe Eskalationsrate | Niedrige FCR | Dem Agenten fehlt das nötige Wissen oder die Befugnis, um Fälle eigenständig zu lösen. | Wissensdatenbank erweitern, Kompetenzbereiche (Permissions) prüfen. |

## Best Practices für die Bewertung

1. **Kontext einbeziehen:** Ein Agent, der komplexe technische Probleme löst, wird immer eine schlechtere AHT haben als jemand, der nur Passwörter zurücksetzt. Vergleichen Sie Agenten nur innerhalb derselben Fallkategorien.
2. **Scorecards nutzen:** Verknüpfen Sie die harten Statistiken mit qualitativen Stichproben (z. B. durch ein Qualitäts-Scorecard-System), bei dem stichprobenartig Interaktionen nach Freundlichkeit und Richtigkeit bewertet werden.
3. **Trends statt Momentaufnahmen:** Beurteilen Sie die Leistung über Wochen oder Monate hinweg, um statistische Ausreißer (z. B. einen besonders schwierigen Kunden) auszugleichen. [[2]][kaizo]

## Offene Fragen

- Handelt es sich um menschliche Mitarbeiter (z. B. im Callcenter) oder um die Evaluierung von KI-Agenten (LLMs)?
- In welcher Branche oder für welchen Kanaltyp (Telefon, Chat, E-Mail) soll die Statistik ausgewertet werden?

## Quellen

1. [Callcenter-KPIs – serviceocean.com][serviceocean]
2. [KI-Agenten-Leistung messen – kaizo.com][kaizo]

[serviceocean]: https://www.serviceocean.com/callcenter-kpis/
[kaizo]: https://www.kaizo.com/de/blog/ki-agenten-leistung-messen/
