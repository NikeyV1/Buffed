# 👥 Teams

Teams verwaltest du über `/team`. Die Teamzugehörigkeit beeinflusst Friendly Fire und die Sichtbarkeit unsichtbarer Teammitglieder.

## 🛠️ Erstellen und beitreten

```text
/team create <Name>
/team invite <Spieler>
/team accept <Owner>
```

Der Teamname braucht **2–16 Zeichen**: Buchstaben, Zahlen, Unterstrich oder Bindestrich. Der Name darf noch nicht vergeben sein.

Nur der Teamleiter kann einladen. Der eingeladene Spieler muss online und ohne Team sein. Die Einladung läuft nach kurzer Zeit ab. Zum Annehmen gibst du den Namen des einladenden Teamleiters an.

## ⚙️ Einstellungen

Mit `/team settings` kannst du die aktuellen Optionen ansehen. Nur der Teamleiter kann sie ändern:

| Befehl | Funktion | Standard für neue Teams |
| --- | --- | --- |
| `/team settings friendly-fire on` oder `off` | Schaden zwischen Teammitgliedern | aus |
| `/team settings see-invisible on` oder `off` | Unsichtbare Teammitglieder füreinander sichtbar machen | an |

Die Optionen gelten für **dein Team** und bleiben über Reload und Neustart gespeichert. Unsichtbare gegnerische Spieler werden dadurch nicht sichtbar.

## 🚪 Verlassen oder auflösen

- `/team list` oder `/team` zeigt die Teamübersicht.
- `/team leave` verlässt das Team als Mitglied.
- `/team disband` löst das Team als Leiter auf.
- `/team help` zeigt die Kurzhilfe.

Ein Teamleiter muss sein Team auflösen, um selbst auszuscheiden.

