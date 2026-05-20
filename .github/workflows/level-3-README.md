# Level 3 — Boo's Haunted Mansion

Doel (verhaal): Ontsnap aan Boo's spookhuis met de kracht van Quality Gates.

Wat je leert:
- Coverage meten met JaCoCo
- Een minimale coverage‑drempel afdwingen (quality gate)

Voorbereiding in Gradle (opdracht):
1. Open `build.gradle` en voeg JaCoCo toe:
```
plugins {
    id 'jacoco'
}

tasks.test {
    useJUnitPlatform()
    finalizedBy(tasks.jacocoTestReport)
}

jacocoTestReport {
    dependsOn tasks.test
    reports {
        xml.required.set(true)
        html.required.set(true)
    }
}
```
2. Commit deze wijziging.

Workflow opdracht:
1. Open `.github/workflows/level-3.yml`.
2. Zorg dat `./gradlew test jacocoTestReport` succesvol draait.
3. Parse het XML rapport `build/reports/jacoco/test/jacocoTestReport.xml` en faal de job onder bijv. 80% line coverage.
4. Upload de HTML en XML rapporten als artifact voor inspectie.

Acceptatiecriteria:
- De job faalt wanneer de coverage onder de ingestelde drempel ligt.
- Coverage rapporten zijn te downloaden als artifact.

Hints:
- Je kunt met `grep` + `sed` de `missed` en `covered` waardes uit de `<counter type="LINE" .../>` lezen en de ratio uitrekenen in `bash`/`awk`.

Stretch goals:
- Plaats de drempel in een input of environment variabele.
- Rapporteer coverage terug in een PR comment (GitHub App/Action).
