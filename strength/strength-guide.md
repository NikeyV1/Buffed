# ⚡ Strength & Splitter

Strength ist dein dauerhafter Fortschritt im SMP. Sie verändert den Kampfschaden und schaltet Klassenfähigkeiten frei. Deinen aktuellen Zustand findest du mit `/strength` und `/strength class`.

## 📊 Standardwerte

| Einstellung | Standard |
| --- | --- |
| Startwert | +1 |
| Untergrenze | −1 |
| Obergrenze | +5 |
| Rohschaden je Strength-Stufe | 0,75 Schadenspunkte |
| Klassen-Passive | ab +2 |
| Ultimate | ab +5 |
| Verlust bei gültigem PvP-Tod | 1 Stufe |

Zwei Minecraft-Schadenspunkte entsprechen einem Herz. Der Strength-Schadenswert ist ein Rohwert; Rüstung und weitere Kampfeffekte beeinflussen den tatsächlichen Trefferschaden. Negative Strength senkt den Schaden entsprechend.

> **Hinweis**
> Diese Zahlen sind Plugin-Standards und können vom Server-Team angepasst werden. Mehr dazu in der [Übersicht](/strength/README.md).

## 💀 Was passiert bei einem PvP-Tod?

Bei einem gültigen Kill zwischen gegnerischen Survival-Spielern verliert das Opfer standardmäßig **eine Strength-Stufe**, solange es noch oberhalb der Untergrenze liegt. Der verlorene Punkt wird als **Strength-Splitter gedroppt**.

Der Killer erhält den Punkt nicht automatisch als zusätzliche Strength. Ein Spieler muss den Splitter aufheben und einlösen.

- Teamkills und Umgebungstode lösen keinen Strength-Transfer aus.
- An der Untergrenze verliert das Opfer keine weitere Strength; entsprechend entsteht kein zusätzlicher Splitter.

## 💎 Splitter einlösen

Halte einen gültigen **Strength-Splitter** in der Haupthand und rechtsklicke. Er wird verbraucht und gibt **+1 dauerhafte Strength**. Am Maximum lässt sich kein weiterer Splitter einlösen.

Splitter sind eigene Server-Items. Eine gewöhnliche Amethystscherbe funktioniert nicht. Du kannst sie zusätzlich [mit einem Rezept craften](/strength/items.md#crafting-rezept).

## 📤 Strength auszahlen

```text
/strength withdraw <Anzahl>
```

Beispiel: `/strength withdraw 2` zieht zwei dauerhafte Strength-Punkte ab und gibt dir zwei Splitter.

- Du musst im Überlebensmodus sein.
- Du brauchst einen freien Inventarslot.
- Die Auszahlung darf deine dauerhafte Strength nicht unter **0** bringen.
- Nur tatsächlich vorhandene positive Strength lässt sich auszahlen.
- Während eines laufenden Rituals sind Auszahlung und Einlösen gesperrt.

## 🗿 Strength durch Rituale

Ein Ritual gibt standardmäßig **+3 Strength vorläufig**, die bei erfolgreichem Abschluss dauerhaft bestätigt werden. Der Bonus kann Passives oder die Ultimate freischalten, solange das Ritual läuft. Ein vollendetes Ritual gibt zusätzlich standardmäßig ein [Auge des Jägers](/strength/items.md#auge-des-jägers).

Es muss beim Start Platz für den **gesamten** Bonus unter dem Maximum sein. Bei Maximum +5 und Bonus +3 kannst du deshalb mit höchstens +2 dauerhafter Strength starten. Bei Abbruch verschwindet der vorläufige Bonus. [Zum Ritual-Guide](/strength/rituals.md).

## 🎯 Weekend Bountys

Ein unerfüllter Wochenendauftrag kostet standardmäßig **zwei Strength**, begrenzt durch die Untergrenze. Das Erfüllen verhindert diese Strafe; die ersten drei erfolgreichen Abschlüsse pro Wochenende erhalten zusätzlich je ein [Auge des Jägers](/strength/items.md#auge-des-jägers). [Zum Bounty-Guide](/strength/bounties.md).
