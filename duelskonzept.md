# Buffed Duels, Konzept

**Stand:** 30. August 2026
**Status:** Konzept für MVP‘s

So ist der Duel-Server aktuell geplant. Das ist die Richtung, in die gebaut wird, kein fertiges Regelwerk. Vor allem beim Balancing wird sich noch einiges ändern, sobald wir echte Matches gespielt haben. Feedback gerne jederzeit.

---

## 1. Was Buffed Duels ist

Ein Duel-Server mit **unseren** Buffs, **unseren** Kits und **unseren** Regeln. Kein generisches Duel-Plugin, sondern das BuffSMP-Erlebnis im 1v1.

Der Kern ist das Herausfordern. Du forderst jemanden heraus, stellst die Einstellungen, der andere sieht sie und nimmt an oder lehnt ab. Eine offene Warteschlange kann später dazukommen, ist aber nicht der Ausgangspunkt.

**Alle 16 Buffs sind spielbar, unverändert wie auf dem SMP.** Nichts wird gesperrt, nichts wird für Duels umgebaut. Ein Buff soll sich im Duel exakt so anfühlen wie auf dem SMP.

Fairness entsteht über zwei Einstellungen pro Match: **wie der Buff zustande kommt** und **welches Inventar beide bekommen.**

---

## 2. Buff Selection Modes

| Modus | Wie der Buff zustande kommt | Essence | Ranked |
|---|---|---|---|
| `mirror` | Beide denselben Buff, gewählt oder zufällig | beidseitig an oder aus | ja |
| `blind_pick` | Beide wählen gleichzeitig verdeckt, Aufdeckung beim Start | beidseitig an oder aus | ja |
| `draft` | 2 Bans pro Spieler, danach je ein Pick | beidseitig an oder aus | ja |
| `free_pick` | Beide wählen offen, Countern ist erlaubt | beidseitig an oder aus | nein |
| `chaos_fair` | Automatisch gezogen, aber auf gleicher Machtstufe | Teil der Ziehung | ja |
| `chaos_random` | Komplett zufällig, alles möglich | pro Spieler zufällig | nein |
| `vanilla` | Kein Buff, reines Kit-Duell | keine | ja |

**Standard beim Herausfordern:** `mirror` mit zufälligem Buff, Essence aus. Das ist der Modus, den man ohne Nachdenken annehmen kann.

**Draft im Detail:** A bannt, B bannt, A bannt, B bannt, dann pickt B, dann pickt A. Der zweite Ban und der letzte Pick liegen bei verschiedenen Spielern, damit niemand beide Vorteile hat.

**Essence ist keine freie Einstellung.** Niemand kann sich einseitig eine Essence dazuwählen. In den Pick-Modi gilt ein Schalter für beide Seiten, in den Chaos-Modi entscheidet die Ziehung.

---

## 3. Tiers und Essence

### Tiers

Drei Stufen, und die große Mehrheit liegt bewusst in der Mitte. Tier 1 und Tier 3 sind nur für Fälle, die auch ohne Spielpraxis eindeutig sind.

| Tier | Punkte | Buffs |
|---|---|---|
| **1** | 3 | Dragon, Trickster |
| **2** | 2 | Archer, Assassin, Cavalry, Duelist, Guardian, Leech, Magic, Storm, Tank, Warden, Warrior, Wither |
| **3** | 1 | Grinding, Adventurer |

Die zwölf Buffs in Tier 2 sind untereinander nicht gleich stark, das ist klar. Sie jetzt in Unter-Tiers zu sortieren wäre geraten. Sobald ein paar hundert Matches in der Datenbank liegen, sagt die Winrate mehr als jede Einschätzung von heute, und dann wird nachjustiert.

Die Tiers haben genau eine Aufgabe: sie steuern die Ziehung in `chaos_fair`. Sonst greifen sie nirgends ein.

### Essence als Machtstufe

Eine Essence hebt einen Buff im Kampf ungefähr um eine Tier-Stufe. Damit wird sie zum Ausgleich: **ein Tier-2-Buff mit Essence steht auf derselben Stufe wie ein Tier-1-Buff ohne.**

Nicht jede Essence ist im Duel gleich viel wert. Grinding Essence gibt doppelte Erz-Drops, Adventurer Essence gibt Backpack und EXP, beides bringt im Kampf nichts. Deshalb hat jede Essence einen eigenen Kampfwert:

| Essence | Kampfwert |
|---|---|
| Grinding, Adventurer | 0 |
| alle übrigen 14 | 1 |

```
Machtstufe = Tier-Punkte + (Essence aktiv ? Kampfwert : 0)
```

Daraus ergeben sich vier Machtstufen:

| Stufe | Loadouts | Anzahl |
|---|---|---|
| **1** | Grinding und Adventurer, mit oder ohne Essence | 4 |
| **2** | die 12 Tier-2-Buffs ohne Essence | 12 |
| **3** | Dragon und Trickster ohne Essence, plus die 12 Tier-2-Buffs mit Essence | 14 |
| **4** | Dragon und Trickster mit Essence | 2 |

Stufe 3 ist der interessante Fall: **Dragon ohne Essence gegen Warrior mit Essence** ist eine faire Paarung. Genau dafür ist das System da.

---

## 4. Wie `chaos_fair` zieht

1. Für Spieler A wird ein Loadout gleichverteilt aus allen 32 Kombinationen gezogen. Daraus ergibt sich die Machtstufe des Matches.
2. Für Spieler B wird aus allen Loadouts **derselben Machtstufe** gezogen.
3. Vor der Ziehung von B fallen weg: bekannte Hard-Konter gegen A, danach der Buff von A selbst, damit nicht versehentlich ein Mirror entsteht, danach Buffs, die B in seinen letzten 3 Matches schon hatte.
4. Wird der Pool durch diese Filter leer, fallen sie in umgekehrter Reihenfolge weg. Der Algorithmus liefert immer ein Ergebnis.

Die Gleichverteilung läuft über Loadouts, nicht über Machtstufen. Stufe 2 und 3 haben zusammen 26 von 32 Einträgen und kommen dadurch von selbst am häufigsten vor, Stufe 4 mit ihren zwei Legendary-Paarungen bleibt selten. Genau so soll es sich anfühlen.

**Grinding gegen Adventurer ist möglich** und ausdrücklich gewollt. Ein Duell, in dem beide Seiten nur mit den Grundmechaniken arbeiten, ist ein eigener Reiz.

### Hard Konter

Manche Paarungen sind auch bei gleicher Machtstufe kaputt, weil ein Buff die Kernmechanik eines anderen aushebelt. Solche Paarungen werden in `chaos_fair` ausgeschlossen.

**Die Konter-Liste ist aktuell leer.** Sie wird nicht am Schreibtisch geraten, sondern nach echten Tests gefüllt. Wenn euch beim Spielen eine Paarung auffällt, die keine Chance lässt, sagt Bescheid, das ist danach ein Eintrag in der Config und keine Codeänderung.

Ein Eintrag ist gerichtet, also wer wen kontert, und kann am Essence-Zustand hängen, weil eine Essence eine Paarung erst kaputt machen kann. Neben harten Kontern, die eine Paarung ausschließen, ist bereits vorgesehen, dass leichtere Konter später nur die Wahrscheinlichkeit senken statt ganz zu sperren.

### Reroll

Ist vorbereitet, bleibt zum Start aber **aus**. Wenn er kommt, darf jeder Spieler einmal neu ziehen, aber nur innerhalb derselben Machtstufe und nur auf einen anderen Buff. Die Machtstufe kann sich durch einen Reroll nie ändern, sonst wäre er ein Fairness-Loch.

Am dringendsten wird er in `chaos_random`, wo die Ziehung wirklich wehtun kann.

---

## 5. Kits und Inventare

| Modus | Beschreibung | Ranked |
|---|---|---|
| `preset` | Beide dasselbe Server-Kit, z.B. SMP-Kit, Netherite oder Diamant | ja |
| `buff_kit` | Jeder das zu seinem Buff passende Server-Kit | ja |
| `challenger_custom` | Der Herausforderer wählt eins seiner Custom Kits, beide spielen dasselbe | nein |
| `own_custom` | Jeder spielt sein eigenes Custom Kit | nein |

**Standard:** `buff_kit`.

### Das Buff-Item gibt es immer

Mehrere Buffs hängen an einem konkreten Item: Storm am Trident, Leech an der Sense, Cavalry an der Lanze, Tank am Shield, Archer am Bogen, Dragon an seinem Schwert. In **allen** Kit-Modi wird das nötige Item mitgegeben, auch wenn es im gewählten Kit fehlt. Ein Custom Kit kann ergänzen, aber nie den eigenen Buff funktionsunfähig machen.

### Custom Kits

Gebaut im GUI, gespeichert unter einem Namen, maximal 5 pro Spieler. Geprüft wird zweimal, beim Speichern und nochmal beim Matchstart, weil sich Regeln ändern können und ein altes Kit sonst durchrutscht. Ungültige Items werden angezeigt und erklärt, nicht stillschweigend entfernt.

Ranked zählt nur mit `preset` oder `buff_kit`. Custom Kits sind untereinander nicht vergleichbar, eine Rangliste darauf wäre wertlos.

Die Buff-Kits für alle 16 Buffs werden ingame festgelegt, nicht auf dem Papier.

---

## 6. Regeln im Duel

Die Serverregeln werden im Duel **erzwungen, nicht moderiert**. Das ist der Unterschied zu jedem anderen Duel-Server: du musst niemandem vertrauen, das Plugin lässt es schlicht nicht zu.

**Blockiert:** Elytra, Riptide-Trident, Crystals, Anchors, Betten, Minecarts als Waffe, Mace, Debuff-Tränke, Unsichtbarkeit, getippte Pfeile, Gsit, Wasser- und Lava-Running.

**Limitiert, kommt direkt aus dem Kit:** maximal 6 Totems, maximal 3 Stacks EXP-Flaschen, Rüstungsreparatur nur über EXP-Flaschen.

**Match-Regeln:**

- Zeitlimit 5 Minuten, danach gewinnt, wer mehr Herzen übrig hat, bei Gleichstand Unentschieden
- Disconnect ist eine Niederlage, Combat-Logging ist damit unmöglich
- Arena-Grenze stößt zurück, kein Void-Tod
- Spectator greifen nicht ein und geben keine Positionen weiter

**Essences bleiben unangetastet**, auch die Teile, die im Duel keine Wirkung haben. Einzige Ausnahme ist der **Death Ban** der Trickster Essence, der im Duel hart deaktiviert ist. Ein Duel-Tod darf niemals einen Ban auslösen, das ist fest verdrahtet und keine Einstellung.

---

## 7. Match-Einstellungen im Überblick

| Einstellung | Optionen | Standard |
|---|---|---|
| Buff Selection | die 7 Modi aus Abschnitt 2 | `mirror` zufällig |
| Essence | an, aus | aus, in den Chaos-Modi gesperrt |
| Kit | `preset`, `buff_kit`, `challenger_custom`, `own_custom` | `buff_kit` |
| Map | zufällig oder gewählt | zufällig |
| Runden | Bo1, Bo3, Bo5 | Bo1 |
| Wetter | klar, Regen, zufällig | klar |
| Ranked | ja, nein | nein, nur bei ranked-fähiger Kombination |

Der Herausgeforderte sieht alle Einstellungen, bevor er annimmt. In den Chaos-Modi sieht er zusätzlich, dass die Buffs erst beim Matchstart gezogen werden.

Wetter ist keine Spielerei: die Lähmung des Storm Buffs hängt an Regen. Ohne Wettersteuerung wäre Storm je nach Arena zufällig stark oder schwach.

---

## 8. Was sich noch ändern wird

Das hier ist ein Startpunkt, kein Gesetz. Konkret erwarten wir Änderungen bei:

- **Tier-Einteilung.** Die zwölf Buffs in Tier 2 sind nicht gleich stark. Sobald genug Matches gespielt sind, wird anhand der Winrates umsortiert.
- **Essence-Werte.** Aktuell zählt jede Essence gleich viel, außer Grinding und Adventurer. Wenn eine Essence deutlich stärker ist als der Rest, bekommt sie einen höheren Wert.
- **Konter-Liste.** Startet leer und wächst durch euer Feedback aus echten Matches.
- **Reroll.** Vorbereitet, kommt nach dem Start.
- **Buff-Kits.** Werden ingame festgelegt und danach mit Sicherheit noch mehrfach angepasst.
- **Zeitlimit.** 5 Minuten sind ein Startwert. Bei defensiven Paarungen wahrscheinlich zu kurz.

Alle diese Werte liegen in der Config, nicht im Code. Ein Balancing-Update ist ein Reload und kein neues Plugin.
