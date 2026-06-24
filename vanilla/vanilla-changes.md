# 🔧 Vanilla Changes

Diese Seite listet **alle Abweichungen vom reinen Vanilla-Verhalten** auf dem Vanilla SMP. Der Kern bleibt Vanilla, einige Mechaniken sind angepasst, um das Spielgefühl fair und ausgewogen zu halten.

> [!NOTE]
> Was hier nicht steht, verhält sich exakt wie in Vanilla. Diese Liste ist die einzige verbindliche Übersicht der Änderungen.

---

## ⚡ Enderpearl

| Einstellung | Wert | Vanilla |
|---|---|---|
| Geschwindigkeits-Cap | aktiv, max. **2.2** | unbegrenzt (~2.0+ bei Boost-Würfen) |

Geboostete Enderpearl-Würfe werden auf eine maximale Geschwindigkeit von 2.2 begrenzt.

---

## 🐛 Endermite

| Einstellung | Wert | Vanilla |
|---|---|---|
| Spawn-Chance pro Wurf | **1 %** | 5 % |

Beim Werfen einer Enderpearl kann ein Endermite spawnen. Die Chance dafür ist von 5 % auf 1 % gesenkt.

---

## 🔱 Trident

| Einstellung | Wert |
|---|---|
| Void-Saving (Loyalty) | aktiv ab **Y -15** abwärts |
| Offhand-Rückkehr | aktiv |
| Loyalty durch Portale | blockiert (Nether/End) |

Ein mit Loyalty verzauberter Trident wird gerettet, wenn er unter Y -15 in den Void fällt. Aus der Offhand geworfene Tridents kehren bei manuellem Aufheben in die Offhand zurück. Loyalty-Tridents reisen nicht durch Portale, um Verlust zu vermeiden.

---

## ☀️ Tag-Nacht-Zyklus

| Phase | Dauer | Vanilla |
|---|---|---|
| Tag | **18.000 Ticks** (15 Min) | 12.000 Ticks (10 Min) |
| Nacht | **12.000 Ticks** (10 Min) | 12.000 Ticks (10 Min) |

Der Tag ist verlängert, die Nacht bleibt Vanilla-Länge.

---

## 📦 Item-Schaden

Welche Schadensarten geworfene/liegende Items zerstören können:

| Quelle | Zerstört Items? |
|---|---|
| Explosion | nein |
| Feuer | nein |
| Lava | nein |
| Kaktus | **ja** |
| Blitz | **ja** |

Items überleben Explosionen, Feuer und Lava. Kaktus und Blitz zerstören sie weiterhin.

---

## 🛠️ Custom Crafting-Rezepte

### Goldener Apfel
![Golden Apple Recipe](../images/recipes/goldenapplerecipe.png)

Ersetzt das Vanilla-Rezept (Vanilla nutzt 8 Goldbarren).

---

### Cobwebs
![Cobweb Recipe](../images/recipes/cobwebrecipe.png)

Ersetzt das Vanilla-Rezept und ergibt 2 Cobwebs pro Craft.

> [!NOTE]
> Das Rezept für den verzauberten Goldapfel ist **nicht** angepasst und verhält sich wie in Vanilla.

---

## 🧪 Tränke

| Trank | Level | Dauer |
|---|---|---|
| Stärke | **II** | 120 Sek |
| Speed | **II** | 120 Sek |

Gebraute Stärke- und Speed-Tränke kommen direkt auf Level II mit 120 Sekunden Dauer.

---

## 🌾 Ackerland

| Modus | Verhalten |
|---|---|
| FEATHER_FALLING | Ackerland wird **nur** zertrampelt, wenn der Spieler **kein** Feather Falling trägt |

Mit Feather Falling auf den Stiefeln bleibt Ackerland beim Drüberlaufen unbeschädigt.

---

## 💀 Kopf-Drops

Tötet ein Spieler einen anderen Spieler, droppt garantiert dessen Kopf. Mob-Kills und Umgebungstode lösen keinen Kopf-Drop aus. Der Kopf trägt den Namen des Opfers und zeigt im Lore die Gesamtzahl seiner Tode.

---

## 🗝️ Ominous Vault — Geänderter Loot

Der Loot der **Ominous Vaults** ist über ein Datapack angepasst. Die Pool-Struktur folgt weiterhin dem Vanilla-Aufbau: je Vault eine garantierte Rare-Roll, 1–3 Common-Rolls und eine **75 %-Chance** auf einen Unique-Drop.

### Unique-Pool (75 % Chance pro Vault)

Hier liegen die größten Änderungen. Der Pool wurde von wenigen gleichgewichteten Items auf eine breitere, gewichtete Verteilung umgestellt.

| Item | Anteil im Pool | Chance pro Vault |
|---|---|---|
| Enchanted Golden Apple | 32,14 % | **24,11 %** |
| Flow Armor Trim Template | 32,14 % | **24,11 %** |
| Flow Banner Pattern | 21,43 % | **16,07 %** |
| Music Disc (Creator) | 10,71 % | **8,04 %** |
| Heavy Core | 3,57 % | **2,68 %** |

> [!IMPORTANT]
> Der **Heavy Core** ist hier bewusst stark verseltent. In Vanilla teilt er sich den Unique-Pool gleichgewichtig mit den anderen Unique-Items und liegt dort spürbar höher. Auf dem Vanilla SMP ist er das seltenste Vault-Item.

### Rare-Pool (garantiert pro Vault)

Der Rare-Pool ist ebenfalls angepasst. Verteilung der Einträge:

| Item | Anteil |
|---|---|
| Emerald Block | 18,52 % |
| Iron Block | 14,81 % |
| Verzauberte Crossbow (Lvl 5–20) | 14,81 % |
| Goldapfel | 11,11 % |
| Verzauberte Diamantaxt (Lvl 10–20) | 11,11 % |
| Verzaubertes Diamant-Chestplate (Lvl 10–20) | 11,11 % |
| Buch: Knockback/Punch/Smite/Looting/Multishot | 7,41 % |
| Buch: Breach/Density | 3,70 % |
| Buch: Wind Burst I | 3,70 % |
| Diamond Block | 3,70 % |

> [!NOTE]
> Beim Buch **Breach/Density** hat Density die **doppelte Chance** wie Breach.

### Common-Pool

Der Common-Pool ist **unverändert** und entspricht dem Vanilla-\`reward_ominous_common\`. Pro Vault werden 1–3 Common-Rolls gezogen; fällt der Rare-Drop aus, kommt eine zusätzliche Common-Roll dazu.

---

## ✨ Exklusive Verzauberungen

Bestimmte Verzauberungen sind **exklusiv** und können weder über den Verzauberungstisch noch über Dorfbewohner-Händler erworben werden.

| Verzauberung | Vanilla-Quellen | Auf dem Vanilla SMP |
|---|---|---|
| Density | Verzauberungstisch, Dorfbewohner | ❌ gesperrt |
| Breach | Verzauberungstisch, Dorfbewohner | ❌ gesperrt |
| Wind Burst | Verzauberungstisch, Dorfbewohner | ❌ gesperrt |
| Knockback | Verzauberungstisch, Dorfbewohner | ❌ gesperrt |

> [!IMPORTANT]
> Diese Verzauberungen können nicht über Verzauberungstisch oder Dorfbewohner-Händler erworben werden.

---

> [!TIP]
> Fragen zu einer bestimmten Änderung? Öffne ein Ticket im [Discord](https://discord.gg/MQzbpd4rju).