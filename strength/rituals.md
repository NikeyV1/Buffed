# 🗿 Rituale

Ein Ritual ist ein zeitgebundener Versuch an einem festen **Strength-Kern**. Standardmäßig bekommst du ab Start **+2 Strength vorläufig**. Überstehst du das gesamte Ritual, werden diese Punkte dauerhaft bestätigt.

## 📍 Einen Kern finden

```text
/strength ritual
```

Der Befehl zeigt die registrierten Ritualorte. Wenn noch kein Kern eingerichtet ist, meldet das Plugin dies. Der Befehl startet kein Ritual aus der Ferne.

## ▶️ Start und Ablauf

1. Gehe zum registrierten Kern.
2. Rechtsklicke ihn und bestätige den Start im Menü vor Ort.
3. Bleibe während des gesamten Versuchs im Ritualbereich.

Das Ritual durchläuft **Erwachen, Bindung und Vollendung**. Ringe, Spiralen, Sounds und eine Fortschrittsanzeige zeigen den Ablauf. Sie sehen Spieler im Ritualbereich.

| Einstellung | Standard |
| --- | --- |
| Dauer | 30 Minuten |
| Vorläufiger und später dauerhafter Bonus | +2 Strength |
| Radius um den Kern | 32 Blöcke |
| Tageswechsel | 00:00 Uhr, Europe/Berlin |

Beim Start muss der volle Bonus unter dein Strength-Maximum passen: Bei Maximum +5 und Bonus +2 darf deine dauerhafte Strength höchstens +3 sein.

Standardmäßig wird der Start mit der Position angekündigt.

## ❌ Wann scheitert das Ritual?

Der vorläufige Bonus verschwindet bei:

- Tod oder Logout;
- Wechsel aus dem Überlebensmodus;
- Verlassen des Ritualbereichs;
- zerstörtem Kern;
- manuellem Abbruch oder Serverstop.

Abbrechen kannst du mit `/strength ritual cancel`.

Während des Rituals kannst du weder Splitter einlösen noch Strength auszahlen oder ein Klassenwechsel-Buch nutzen.

## ✅ Erfolg

Nach Ablauf werden die +2 dauerhaft bestätigt. Vorläufige Strength wird nicht zusätzlich ein zweites Mal angerechnet. Deine [Passives und Ultimate](/strength/classes.md) richten sich während des Rituals bereits nach der wirksamen Strength inklusive Bonus.

> **Hinweis**
> Die genannten Zahlen entsprechen den Plugin-Standards. Kernorte, Dauer, Radius und Bonus können vom Server-Team eingestellt werden.
