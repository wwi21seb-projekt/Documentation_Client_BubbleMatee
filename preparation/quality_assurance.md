# Qualitätssicherungsmaßnahmen 

## Usability 
- 10 heuristiken
- Checkliste im Pull-Request - Abhaken durch Reviewer
- Checkliste im Sprint für gesamte App - zu viert überprüfen
- Template für Usability-Tests
- Usability Tests: 
	- alle 2 Sprints (Ende 2ter Sprint)
	- mit 4 Personen (jeder mit einer Person, nicht zwei mal gleiche Person hintereinander)
	- Aufgaben definiert von allen zu jedem Sprint, eventuell alte anpassen

## Maintainability

[TypescriptBP](https://docs.aws.amazon.com/prescriptive-guidance/latest/best-practices-cdk-typescript-iac/typescript-best-practices.html)

[SvelteBP](https://kim-jangwook.medium.com/best-practices-for-organizing-and-structuring-svelte-applications-5f85a3d5a6f5)

[CleanCodeMetriken](https://www.adesso.de/de/news/blog/clean-code-prinzipien-und-die-messbarkeit-durch-metriken.jsp)

[CodeMetrikPipeline](https://devblogs.microsoft.com/dotnet/automate-code-metrics-and-class-diagrams-with-github-actions/)

- Code Metriken festlegen, die überprüft werden
- Best Practices definieren
- Versionskontrolle mit Git
- Dependency Management wie renovate bot
- Code Analysen, um Best Practises einzuhalten
- Code Formatierungen
- Code Reviews - 4-Augen Prinzip 
- Verpflichtendes Entwicklungswerkzeug für Best Practices wie [Lighthouse](https://chromewebstore.google.com/detail/lighthouse/blipmdconlkpinefehnmjammfjpmpbjk?hl=de)
- Checklisten: 
- - Entwickler: "Ich habe self review gemacht und dabei best Practices beachtet"
- - Entwickler und Reviewer: "Ich habe meine Funktionalität mit den festgelegten Entwicklungswerkzeugen überprüft" 
- - Entwickler: "Ich habe habe code formatierungen und überprüfungen lokal durchgeführt"
- - Reviewer: "Ich habe den Code nach Best Practices überprüft"


# Qualitätssicherungsmaßnahmen (veraltet)

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
- Aspekte ausarbeiten - Web Content Accessibility Guidelines
- Welche Aspekte mit Pa11y automatisiert testbar 
- Manuelle Tests?


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
