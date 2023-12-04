# Qualitätssicherungsmaßnahmen

## Nutzbarkeit (Usability)

### 1. Design Heuristiken nach Nielsen

- Check Liste der Heuristiken in Pull-Request-Template der Feature Branch
- Iterative Reviews über die Umsetzung im Team -> pro Sprint (Wer reviewed?)

### 2. Usability Tests

- Pro User Story Aufgaben definieren durch implementierende Person
- Am Ende eines Sprints quantitative Usability Test mit echten Nutzern durchführen (Wie viele Personen? Wie viele Wiederholungen? Wer führt sie durch?)
- Fehlerquellen identifizieren und Feedback aufnehmen -> Template Formular

-> Erst wenn Features von Usability Tests validiert sind, ist das Ticket fertig

### 3. Nutzer Dokumentation/Hilfe?

## Barrierefreiheit (Accessibility)

- [Accessibility Runs](https://docs.gitlab.com/ee/ci/testing/accessibility_testing.html) in CI/CD Pipeline
- Nutzung von speziellen [Dev Tools über Accessibility](https://chromewebstore.google.com/detail/axe-devtools-web-accessib/lhdoppojpmngadmnindnejefpokejbdd?pli=1)

Weitere Infos: https://adevait.com/qa/automated-accessibility-testing-for-svelte-applications

- Welche Aspekte von Accessibility berücksichtigen wir?
- Welche Tools nutzen wir für was?
- Wie funktionieren die Tools?
- Wie gehen wir damit um?

## Funktionalität (Functionality) -> nur für uns, nicht vorstellen

- automatisierte End to End Tests
- Testen der Responsiveness mithilfe der Browser Dev Tools -> nach dem Deployment verpflichtende Test auf mindestens einem Tablet and Smartphone pro Sprint
- Feature Based Engineering mit Pair Programming und Reviews -> mindestens 4-Augen Prinzip
