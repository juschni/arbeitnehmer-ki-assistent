# Monetarisierungsmodell – CareerAI / Arbeitnehmer-KI-Assistent

**Status:** v1.0 – Best Practice (Stand 2025-09-25)

## Grundprinzip (aus der Charta)

- Preis und Leistung bleiben nachvollziehbar
- Vertrauen vor kurzfristigem Wachstum
- Orientierung statt Rechtsberatung
- Keine künstliche Verknappung, keine Dark Patterns

## Empfohlenes Modell: Freemium + einmaliger Boost

### 1. Kostenlos (Einstieg)
- Unbegrenzte grundlegende Fragen
- Standard-Antwortstruktur (Kurzfassung → Optionen → Nächste Schritte)
- Keine Dokumenten-Uploads
- Keine längeren Sitzungen / History

**Ziel:** Vertrauen aufbauen, Nutzen zeigen, Conversion vorbereiten.

### 2. Premium – „Karriere-Boost“ (Einmalzahlung)
**Preisempfehlung:** 19 € (einmalig)

Enthalten:
- Erweiterte GPT-Version (längere, tiefere Analysen)
- Dokumenten-Upload (Zeugnis, Abmahnung, Arbeitsvertrag, Gehaltsangebot)
- Formulierungshilfe (Anschreiben, Widerspruch, Verhandlungstexte)
- 30 Tage Zugang ab Kauf
- PDF-Export der Analysen

**Warum 19 €?**
- Niedrige Einstiegshürde
- Entspricht dem wahrgenommenen Wert einer guten Beratungseinheit
- Passt zu „Preis und Leistung nachvollziehbar“
- Hohe Conversion bei klarer Nutzenargumentation

### 3. Optional später: Abo „Karriere-Begleiter“
**Preis:** 9,90 € / Monat  
Nur aktivieren, wenn echte wiederkehrende Nutzung nachweisbar ist.

---

## Technische Umsetzung (Minimal)

1. Landingpage zeigt klare Preise + Nutzen
2. Stripe Checkout (oder Lemon Squeezy) für 19 €
3. Nach Zahlung: Zugangscode oder automatischer Link zur Premium-Version
4. Premium-Version = eigene Hugging-Face-Space-Instanz oder passwortgeschützte Seite mit verbessertem Prompt

## Rechtliche Mindesttexte (Pflicht)

- Impressum
- Datenschutzerklärung (DSGVO)
- AGB / Nutzungsbedingungen
- Klarer Disclaimer: „Orientierung und Vorbereitung – keine Rechtsberatung“

## Nächste konkrete Schritte

1. Preise + Texte final freigeben
2. Stripe-Account anlegen + Produkt „Karriere-Boost 19 €“ erstellen
3. Landingpage um Pricing-Section erweitern
4. Zugangslogik (Code oder Login) implementieren
5. Rechtstexte ergänzen
