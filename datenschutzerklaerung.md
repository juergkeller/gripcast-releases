# Datenschutzerklärung GripCast

**Stand:** 1. August 2026

> Diese deutsche Fassung dient der Verständlichkeit. Massgeblich ist die
> englische Fassung (`PRIVACY.md` / Privacy Policy), die auch in der Play
> Console hinterlegt ist.

## 1. Verantwortlicher

Jürg Keller
juerg.keller@outlook.com

GripCast ist eine kostenlose App ohne Werbung, ohne Konten und ohne
kommerzielle Datennutzung.

## 2. Welche Daten verarbeitet werden

### 2.1 Dienste, die dein Gerät direkt kontaktiert

GripCast braucht kein Konto, deine Einstellungen bleiben auf dem Gerät. Um
eine Vorhersage anzuzeigen, fragt die App folgende Dienste direkt vom Gerät
aus ab:

| Dienst | Erhält | Zweck |
|---|---|---|
| Open-Meteo (Wetterdaten) | Eine Rasterkoordinate mit ~10 km Auflösung (z. B. „47.4,8.0") und die IP-Adresse deines Geräts | Wettervorhersage, Bodenfeuchte, Regen der letzten Tage |
| BigDataCloud (Geodienst) | Dieselbe Rasterkoordinate und die IP-Adresse deines Geräts | Der Ortsname, der in der App angezeigt wird (z. B. „Aarau") |
| Expo (App-Updates) | Die IP-Adresse deines Geräts und technische Angaben wie App-Version, Runtime-Version und Plattform | Ausliefern der automatischen App-Updates |

Deine exakte Position ist in diesen Anfragen **nie** enthalten: Die App
rundet jede ausgehende Koordinate auf das ~10-km-Raster, bevor die Anfrage
das Gerät verlässt, in derselben Auflösung wie beim Server (siehe Ziffer 8).

Keine dieser Anfragen enthält deine Installations-ID, ein Konto oder eine
andere von GripCast vergebene Kennung. Die Dienste sehen allerdings deine
IP-Adresse; für ihre eigene Protokollierung gelten ihre jeweiligen
Datenschutzerklärungen.

### 2.2 Daten auf dem GripCast-Server

Serverseitig wird nichts gespeichert, solange du keine
**Benachrichtigungen aktivierst**. Erst dann speichert der GripCast-Server
pro Installation folgende Daten (Datenkategorien):

| Datenkategorie | Inhalt | Zweck |
|---|---|---|
| Gerundeter Standort | Rasterkoordinate mit ~10 km Auflösung (z. B. „47.4,8.5"). Die Rundung passiert auf dem Gerät, bevor etwas übertragen wird, deine **exakte Position erreicht den GripCast-Server also nie** | Wettervorhersage für deine Region |
| Zeitzone | IANA-Zeitzone (z. B. „Europe/Zurich") | Benachrichtigung zur richtigen Lokalzeit (19:00 / Morgen-Check) |
| Push-Token | Technisches Zustell-Token von Firebase Cloud Messaging (FCM) | Zustellung der Benachrichtigung an dein Gerät |
| Benachrichtigungs-Einstellungen | Ride Windows (Wochentag-/Wochenend-Zeitfenster), Score-Schwelle, 12h/24h-Anzeigeformat, Aktiv-Status | Entscheidung, ob und wofür gemeldet wird |
| Meldungs-Verlaufszustand | Anti-Spam-Zähler (Serientage mit gutem Wetter), letzter Meldeentscheid | Verhindert tägliche Wiederholungsmeldungen bei anhaltend gutem Wetter |

Die Installation wird durch eine **zufällige, pseudonyme Installations-ID**
identifiziert. Sie hat keinen Bezug zu Geräte-Identifiern, Konten oder
Personen. **Der GripCast-Server erhebt nicht:** deine exakte GPS-Position
(siehe Ziffer 8), Standortname, Name, E-Mail-Adresse, Geräte-IDs,
Werbe-IDs, Nutzungsstatistiken.

Zusätzlich speichert der Server aggregierte **Laufstatistiken** (z. B. Anzahl
versendeter Meldungen pro Lauf) ohne jeden Personen- oder Installationsbezug.

## 3. Zweck der Verarbeitung

Einziger Zweck ist die **Berechnung und Zustellung der
Bike-Wetter-Benachrichtigungen**: Der Server prüft abends (und morgens als
Kontrolle) die Wettervorhersage für deine Rasterkoordinate und sendet eine
Push-Meldung, wenn in deinen Zeitfenstern gutes Bike-Wetter zu erwarten ist.
Es findet keine Verwendung für Werbung, Profilbildung oder Analyse statt.

## 4. Rechtsgrundlage

Die serverseitige Verarbeitung (Ziffer 2.2) erfolgt auf Grundlage deiner
**Einwilligung**, die du durch das Aktivieren der Benachrichtigungen in den
App-Einstellungen erteilst (Art. 6 Abs. 1 lit. a DSGVO bzw. Einwilligung
nach revDSG; zugleich Vertragserfüllung: die Funktion ist ohne diese Daten
technisch nicht erbringbar). Du kannst die Einwilligung jederzeit
widerrufen, durch Deaktivieren der Benachrichtigungen oder vollständig über
**„Server-Daten löschen"** (siehe Ziffer 7).

Die Abfragen nach Ziffer 2.1 sind erforderlich, um die von dir angeforderte
App-Funktion bereitzustellen (Art. 6 Abs. 1 lit. b DSGVO); ohne sie kann die
App keine Vorhersage anzeigen.

## 5. Empfänger und Auftragsverarbeiter

- **Google Ireland Ltd. / Google LLC (Firebase):** Der GripCast-Server läuft
  auf Firebase (Cloud Firestore, Cloud Functions, Firebase Cloud Messaging).
  Speicherung und Verarbeitung erfolgen in der Region **Zürich, Schweiz
  (europe-west6)**. Die Zustellung von Push-Nachrichten über FCM kann
  technisch bedingt **global geroutet** werden. Google ist
  Auftragsverarbeiter auf Grundlage der Google Cloud / Firebase **Data
  Processing Terms** einschliesslich **Standardvertragsklauseln (SCC)**; als
  US-Anbieter unterliegt Google dem CLOUD Act.
- **Open-Meteo (Wetterdaten-Anbieter):** erhält Daten auf zwei getrennten
  Wegen, beide ausschliesslich mit der **Rasterkoordinate** (~10 km) und
  ohne Installations-ID. Anfragen des GripCast-Servers enthalten zusätzlich
  nicht die IP-Adresse deines Geräts; Anfragen der App selbst enthalten sie,
  wie jede direkte Anfrage.
- **BigDataCloud (Geodienst):** erhält die Rasterkoordinate und die
  IP-Adresse deines Geräts, wenn die App den angezeigten Ortsnamen auflöst.
  Keine Installations-ID, kein Kontobezug.
- **Expo / Expo Application Services (App-Updates):** erhält die IP-Adresse
  deines Geräts und technische Angaben (App-Version, Runtime-Version,
  Plattform), wenn die App nach Updates sucht.

Es findet **keine Weitergabe zu Werbezwecken** und kein Verkauf von Daten
statt.

## 6. Speicherdauer

- **Bis zur Löschung durch dich** („Server-Daten löschen" in den
  Einstellungen, löscht sofort).
- **Automatisch** ohne dein Zutun:
  - Nach Deinstallation der App wird das Push-Token ungültig; der Server
    löscht den Datensatz nach **3 fehlgeschlagenen Zustellversuchen**.
  - Spätestens nach **270 Tagen ohne Lebenszeichen** der Installation wird
    der Datensatz durch einen wöchentlichen Aufräumlauf gelöscht.
- **Laufstatistiken** (ohne Personenbezug) werden nach **30 Tagen**
  automatisch gelöscht.

Das Deaktivieren der Benachrichtigungen (ohne Löschung) lässt den Datensatz
bestehen, damit ein Wiedereinschalten sofort funktioniert; es werden dann
keine Meldungen berechnet oder gesendet. Wer alle Serverdaten entfernen
will, nutzt „Server-Daten löschen".

Die in Ziffer 2.1 genannten Dienste führen eigene Server-Protokolle nach
ihren eigenen Fristen. Darauf hat GripCast keinen Einfluss und erhält von
dort auch keine Daten über dich.

## 7. Deine Rechte und der Löschweg in der App

Du hast das Recht auf Auskunft, Berichtigung, Löschung, Einschränkung der
Verarbeitung und Datenübertragbarkeit sowie das Recht, eine erteilte
Einwilligung jederzeit zu widerrufen. Wende dich dazu an
juerg.keller@outlook.com.

**Löschung direkt in der App:** Einstellungen → **„Server-Daten löschen"**.
Damit wird der Datensatz dieser Installation sofort und unwiderruflich vom
Server gelöscht, die pseudonyme Installations-ID wird verworfen und durch
eine neue ersetzt, und die Benachrichtigungen werden **deaktiviert**. Erst
wenn du Benachrichtigungen erneut aktivierst (neue Einwilligung),
registriert sich das Gerät wieder, unter der neuen, mit den gelöschten
Daten nicht verknüpfbaren ID.

Beschwerderecht: Du kannst dich bei der zuständigen Aufsichtsbehörde
beschweren (Schweiz: Eidgenössischer Datenschutz- und
Öffentlichkeitsbeauftragter, EDÖB; EU: deine nationale
Datenschutzbehörde).

## 8. Standort: was wohin geht

Du setzt deinen Standort entweder durch Eintippen eines Ortsnamens oder über
den GPS-Knopf, der deine Position **einmalig** abfragt und auf dem Gerät
speichert. Es findet kein Standort-Tracking statt, auch nicht im
Hintergrund.

**Deine exakte Position verlässt dein Gerät nie.** Jede ausgehende Anfrage,
ob an den GripCast-Server, an Open-Meteo oder an BigDataCloud, enthält nur
eine auf ein ~10-km-Raster gerundete Koordinate; gerundet wird auf dem Gerät,
bevor die Anfrage rausgeht. Deshalb kann der in der App angezeigte Ortsname
gelegentlich ein Nachbarort sein: Er stammt aus der Rasterzelle, nicht aus
deiner exakten Position.

## 9. Beta-Phase

Solange sich GripCast in der öffentlichen Beta befindet, wird die App als
APK ausserhalb des Play Store verteilt, und der GripCast-Server läuft im
Testprojekt des Entwicklers (`gripcast-dev`), ebenfalls in der Region Zürich
(europe-west6). Datenkategorien, Speicherfristen und der Löschweg dieser
Erklärung gelten dort unverändert.

## 10. Google-Play-Formular „Datensicherheit"

Die Angaben im Google-Play-„Datensicherheit"-Formular (Data Safety)
entsprechen dieser Erklärung.
