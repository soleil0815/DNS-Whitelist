# DNS-Whitelist

Eine gepflegte Whitelist für DNS-Filter wie **AdGuard Home** und **Technitium DNS**.

## Wozu?

Blocklisten schützen vor Werbung, Tracking und Schadseiten, sperren aber oft mehr als nötig. Dann hängen Links in Newslettern, Shops leiten nicht weiter, Apps melden Fehler oder Banking-Seiten laden nicht richtig.

Diese Liste gibt genau solche Domains wieder frei. So bleibt der Schutz der Blocklisten erhalten, und trotzdem funktionieren Webseiten, Apps und Dienste im Alltag ohne Ärger.

## Dateien

Die Liste gibt es in zwei Formaten mit identischem Inhalt:

| Datei | Format | Für |
|---|---|---|
| [`whitelist-adguard.txt`](whitelist-adguard.txt) | Adblock-Syntax (`@@\|\|domain^`) | AdGuard Home, uBlock Origin |
| [`whitelist-technitium.txt`](whitelist-technitium.txt) | Eine Domain pro Zeile | Technitium DNS, Ausnahmen in der FRITZ!Box und andere Filter, die reine Domainlisten erwarten |

Die Einträge sind nach Bereichen gruppiert, zum Beispiel Tracking & Analytics, E-Mail & Kommunikation, Mobile Apps, Online-Shops und Banking.

## Einbinden

Am besten bindest du die Liste per URL ein. Dann holt sich dein DNS-Server Änderungen automatisch.

### AdGuard Home

1. **Filter → DNS-Zulassungslisten** öffnen
2. **Zulassungsliste hinzufügen → Benutzerdefinierte Liste hinzufügen** wählen
3. Diese URL eintragen:

```
https://raw.githubusercontent.com/soleil0815/DNS-Whitelist/main/whitelist-adguard.txt
```

### Technitium DNS

1. **Settings → Blocking** öffnen
2. Unter **Allow List URLs** diese URL eintragen:

```
https://raw.githubusercontent.com/soleil0815/DNS-Whitelist/main/whitelist-technitium.txt
```

3. Speichern

### uBlock Origin

Unter **Filterlisten → Importieren** die AdGuard-URL von oben eintragen.

### FRITZ!Box (ab FRITZ!OS 8.50)

Seit FRITZ!OS 8.50 hat die FRITZ!Box einen eigenen DNS-Filter. Domain-Ausnahmen haben dort Vorrang vor den Sperrlisten. Den Filter gibt es nicht auf jedem Modell: Die FRITZ!Box 7690 hat ihn als erste bekommen, weitere Modelle folgen nach und nach. Fehlt der Reiter **DNS-Filter**, unterstützt deine FRITZ!Box ihn noch nicht.

1. **Heimnetz → Netzwerk → Netzwerkeinstellungen → Erweiterte Netzwerkeinstellungen ändern → DNS-Filter** öffnen
2. Unter **Domain-Ausnahmen** auf **Eigene Domain hinzufügen** klicken
3. Die benötigten Domains aus [`whitelist-technitium.txt`](whitelist-technitium.txt) eintragen, jeweils nur den Namen ohne `https://` und ohne Pfad

Die Ausnahmen werden einzeln eingetragen. Am besten nimmst du nur die Domains, die du wirklich brauchst.

> **Achtung:** Nicht die Liste „Erlaubte Internetseiten“ der Kindersicherung verwenden. Ist sie aktiv, erlaubt die FRITZ!Box **nur** diese Seiten und sperrt alles andere.

## Mitmachen

Wird eine Seite durch deine Blocklisten fälschlich gesperrt? Öffne gern ein Issue mit der Domain und kurz, wofür sie gebraucht wird. Neue Einträge kommen immer in **beide** Dateien.
