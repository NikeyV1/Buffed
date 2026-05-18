# Systemübersicht

Diese Seite gibt eine **kompakte Übersicht über die grundlegenden Mechaniken** des Buff SMP, ohne Inhalte aus den Buff-, Essence- oder Ritualseiten zu wiederholen.

Hier werden insbesondere das **Punkte-System**, Buff-Progression, Shops und allgemeine Regeln beschrieben.

---

## ⚙️ Allgemeine Regeln

- Jeder Spieler besitzt **genau einen Buff**
- Buffs besitzen **aktive Fähigkeiten** (Rechtsklick / Sneaken + Rechtsklick)
- Manche Buffs haben **passive Effekte**
- Aktive Fähigkeiten haben feste **Cooldowns**
- **Legendary Buffs** sind deutlich stärker und einzigartig
- **Essences:**
    - Können im Shop gekauft oder durch ein erfolgreiches Ritual aktiviert werden
    - Verstärken den Buff erheblich
    - Sichtbar durch Partikel unter dem Spieler

---

## 💠 Punkte- & Buff-System

Das frühere Lebenssystem wurde durch ein **Punkte-System** ersetzt. Jeder Spieler besitzt ein persönliches Punktekonto.

### Startpunkte
- Beim **ersten Join** startest du mit **5 Punkten**

---

### Buff-Zustand abhängig von Punkten
- **Punkte > 0:** Buff funktioniert vollständig
- **Punkte = 0:** Letzter Puffer, Buff ist noch aktiv
- **Punkte < 0:** Aktive Buff-Fähigkeiten sind **deaktiviert**
- **Untergrenze:** **−5 Punkte**

---

### Punkteänderungen durch Kills & Sterben

#### 🗡️ Spieler töten

- Standardmäßig erhält der Killer **+3 Punkte**

#### ☠️ Sterben

Der Punkteverlust hängt vom aktuellen Punktestand ab:

**Wenn der Spieler ≥ 0 Punkte hat:**

- Normaler Verlust: **−3 Punkte**
- Sonderregel:
  Würde der Tod direkt ins Minus führen, werden stattdessen nur **−2 Punkte** abgezogen

---

### Unter 0 Punkten
- Spieler mit negativen Punkten verlieren pro Tod nur **−1 Punkt**
- Das System stoppt bei **−5 Punkten** (kein weiterer Verlust)

---

## 🛒 Shop-System (`/points shop`)

Punkte können ausgegeben werden für:

- **Buff Tokens:** Ermöglichen das Kaufen eines Buff-Tokens
- **Buff Items:** Direkte Buff-Items oder Hilfsmittel
- **Essencen:** Kaufe Essences für den Buff

---

## ⌨️ Commands

Kurzer Überblick über zentrale Commands des Buff-Systems:

- **`/settings`**
  Persönliche Einstellungen, z. B. Aktivierung/Deaktivierung der **Cooldown-Anzeige**.

- **`/bufflist`**
  Zeigt alle Buffs und ob sie bereits per Ritual freigeschaltet wurden.
  Dient der Übersicht über den aktuellen Server-Fortschritt.

- **`/points`**
  Verwaltung des Punktesystems:
  Punktestand einsehen, **Shop öffnen**, Punkte ausgeben oder bezahlen.

---

## 💎 Wichtige Buff-Items

- **Revive Beacon:** Belebt gebannte Spieler wieder; selten erhältlich und wird beim Einsatz verbraucht.
- **Warden Shard:** Droppt zu 30 % von einem getöteten Warden; benötigt für den Warden Buff.
- **Reroll Book:** Tauscht den aktuellen Buff gegen einen neuen zufälligen, sofern alle rerollbaren Buffs einmal durch ein Ritual freigeschaltet wurden.
- **Tokens:** Ermöglichen die gezielte Auswahl eines Buffs; sehr teuer, aber präzise.
- **Buff Swapper:** Tauscht aktive Buffs inklusive zugehöriger Buff-Items zwischen zwei Spielern.

### 🧭 Player Tracker

#### Nutzung
- **Rechtsklick** mit dem Kompass → öffnet Übersicht aller Online-Spieler
- **Spieler auswählen** → Kompass zeigt für **30 Minuten** auf diesen Spieler
- Danach wird der Kompass **verbraucht** und kann nicht erneut genutzt werden

#### Teleport-Funktion
- Falls das Ziel mehr als **300 Blöcke entfernt** ist, kann per Rechtsklick in die Nähe teleportiert werden
- **Einschränkung:** Teleport-Funktion erst **5 Minuten nach Start des Trackings** verfügbar

#### Dimensionen
- Befindet sich das Ziel in der **Overworld**, darf es diese Dimension nicht mehr verlassen, solange das Tracking aktiv ist

#### Verhalten während des Trackings
- Das Ziel darf sich nicht dauerhaft durch folgende Methoden entziehen:
    - Weglaufen ohne Interaktion
    - Permanentes Hochbauen
    - Sich verbunkern
- Gelegentliche Fluchtversuche sind erlaubt, dauerhaftes Entkommen widerspricht der vorgesehenen Tracker-Funktion
- Das Ziel und die trackende Person sind während des Trackings in Combat
