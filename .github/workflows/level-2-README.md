# Level 2 — Koopa's Fortress

Doel (verhaal): Versla de Koopa‑bewakers met je test‑skills.

Wat je leert:
- Tests uitvoeren in CI
- Fouten laten de pipeline falen
- Test rapporten uploaden voor analyse

Opdracht:
1. Open `.github/workflows/level-2.yml`.
2. Vul de TODO's in zodat `./gradlew test` draait en faalt bij mislukte tests.
3. Upload test rapporten als artifact (ook bij falen met `if: always()`).
4. (Optioneel) Laat de workflow automatisch lopen bij `push` en `pull_request`.

Acceptatiecriteria:
- Een failing test zorgt dat de job faalt.
- Test rapporten zijn te downloaden uit de Actions run (XML + HTML reports).

Hints:
- `actions/upload-artifact@v4`
- Rapports: `build/test-results/test` (XML) en `build/reports/tests/test` (HTML)

Stretch goals:
- Voeg een test matrix toe (bijv. OS matrix: ubuntu, macOS, windows).
- Publiceer JUnit resultaten in GitHub UI met een marketplace action.
