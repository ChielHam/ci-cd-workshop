
# Level 1 — Yoshi's Island

Doel (verhaal): Verbind het Mushroom Kingdom met Yoshi's Island.

Wat je leert:
- Een GitHub Actions workflow starten
- De applicatie builden met Gradle

Opdracht:
1. Open `.github/workflows/level-1.yml`.
2. Vervang de TODO's zodat de workflow bouwt met Java 21 en Gradle.
3. Draai de workflow handmatig via het Actions‑tab (workflow_dispatch).
4. (Optioneel) Laat de workflow ook automatisch lopen bij `push` en `pull_request`.

Acceptatiecriteria:
- Workflow runt succesvol en voert `./gradlew build` uit.
- Resultaat zichtbaar in Actions logs.

Hints:
- `actions/checkout@v4`
- `actions/setup-java@v4` met `distribution: temurin` en `java-version: '21'`
- `gradle/actions/setup-gradle@v4`

Stretch goals:
- Voeg een matrix toe voor meerdere Java versies (bijv. 21 en 23).
- Activeer caching via de Gradle action.