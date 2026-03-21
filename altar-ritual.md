# Altar- & Ritualsystem

Buffs können entweder über ein **Altar-Ritual** oder **direkt ohne Ritual** aktiviert werden.  
Beide Varianten werden über einen **Token** gestartet, unterscheiden sich jedoch deutlich in Ablauf, Anforderungen und Belohnungen.

---

## 🎟️ Token-Nutzung (Auswahlmenü)

- **Rechtsklick mit einem Token** auf den Altar öffnet eine GUI mit zwei Optionen:
    1. **Einmaliges Ritual starten**
    2. **Buff ohne Ritual aktivieren**

---

## 🗿 Option 1: Ritual starten *(einmalig)*

Diese Variante entspricht dem klassischen **Altar-Ritual** und zählt als **Ritual-Freischaltung** des Buffs.

### Voraussetzungen

- **1 Token** *(wird verbraucht)*
- Das **alte Buff-Item** muss sich im Inventar befinden
- Es müssen **mindestens genauso viele Gegner wie Allies** online sein
    - Spieler müssen Angreifbar sein um als Gegner zu zählen
- Das Ritual muss vor 22:00 Uhr beendet sein
    - An Wochenenden & Feiertagen bis 22:30 Uhr
- **Ritualdauer:**
    - Normale Buffs → **25 Minuten**
    - Utility Buffs → **18 Minuten**

---

### Ablauf des Rituals

1. **Ritual bestätigen** im Auswahlmenü
2. **Während des Rituals**
    - Aufenthalt im 100-Block-Radius um den Altar
        - Verlassen des Bereichs → 30 Sekunden, um zurückzukehren
    - **Tod** des Spielers → Ritual wird sofort abgebrochen
    - Campen ist nicht erlaubt 
    - Eine **Bossbar** zeigt die verbleibende Ritualzeit an
3. **Ritualabschluss**
    - **Altes Buff-Item vorhanden**
        - Altes Buff-Item wird entfernt
        - Neuer Buff wird vergeben
    - **Erstfreischaltung dieses Buffs auf dem Server**
        - Die zugehörige Essence ist 5 Tage aktiv
    - **Kein altes Buff-Item vorhanden**
        - Ritual scheitert

---

## ⚡ Option 2: Buff ohne Ritual aktivieren

- Der Buff wird sofort aktiviert
- **Kein Ritual**, **keine Wartezeit**, **keine Gegner-Anforderung**
- Zählt nicht als Ritual-Freischaltung
- **Keine Erstfreischaltungs-Belohnung**  
  *(keine 5-Tage-Essence)*

---

## 💬 Discord-Integration

- **Start und Ende von Ritualen** werden automatisch im Discord-Channel **#server-events** gepostet
- Buff-Aktivierungen **ohne Ritual** werden **nicht** im Discord angekündigt
