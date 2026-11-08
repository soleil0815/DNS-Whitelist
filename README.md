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
| [`whitelist-technitium.txt`](whitelist-technitium.txt) | Eine Domain pro Zeile | Technitium DNS und andere Filter, die reine Domainlisten erwarten |

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

## Hinweis zur FRITZ!Box

Die Kindersicherung der FRITZ!Box kennt zwar eine Liste „erlaubte Internetseiten“. Ist sie aktiv, erlaubt die FRITZ!Box aber **nur** diese Seiten und sperrt alles andere. Außerdem passen höchstens 500 Einträge hinein. Für den Zweck dieser Liste ist die FRITZ!Box deshalb nicht geeignet.

## Mitmachen

Wird eine Seite durch deine Blocklisten fälschlich gesperrt? Öffne gern ein Issue mit der Domain und kurz, wofür sie gebraucht wird. Neue Einträge kommen immer in **beide** Dateien.
