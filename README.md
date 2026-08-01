# GripCast (Beta für Android)

**Aktuelle Version: 1.1.0 · 19. Juli 2026 · [Link zum APK-Download in den Releases]**

> Beta-Software: GripCast funktioniert, wird aber aktiv weiterentwickelt.
> Genau dafür suchen wir Tester. Details unten unter [Feedback](#feedback).

## Was ist GripCast?

GripCast zeigt dir, ob und wann sich Mountainbiken in den nächsten drei Tagen lohnt.
Jeder Tag ist in vier Zeitfenster geteilt (Morgen, Mittag, Nachmittag, Abend);
jedes Fenster bekommt einen Trail Score von 0–100 und ein klares Urteil:
**GO / MAYBE / NO**. In den Score fliessen neben der Wettervorhersage auch
Bodenfeuchtedaten ein; also nicht nur „regnet es?", sondern auch „wie nass
ist der Boden noch vom Regen gestern?". Bei Gewitterrisiko steht ein Fenster
immer auf NO, egal wie gut der Rest aussieht.

Das Herzstück ist die Benachrichtigung: Um 19:00 meldet sich GripCast,
wenn **morgen** in deinen Fahrzeitfenstern gutes Bike-Wetter ansteht. Kippt
die Vorhersage über Nacht, kommt früh am Morgen eine Korrektur. Ab welchem
Score gemeldet wird, stellst du selbst ein, ebenso deine Fahrzeitfenster
(werktags/Wochenende getrennt).

<img width="437" height="850" alt="image" src="https://github.com/user-attachments/assets/fdf2950d-2bde-4bff-9939-30128025b70c" />


Die App-Oberfläche ist derzeit auf Englisch.


## Beta-Status: was du erwarten kannst

- Score-Anzeige, Zeitfenster-Urteile und die Benachrichtigungen funktionieren.
- **Die Benachrichtigungslogik ist genau das, was wir testen wollen:** Kommt
  die Meldung zuverlässig? Zum richtigen Zeitpunkt? Zu oft, zu selten?
- Die Score-Kalibrierung (wie streng die App urteilt) wird während der Beta
  noch nachjustiert. Auch dazu ist dein Eindruck wertvoll.
- **Updates kommen automatisch über die App** du musst nichts tun, beim
  nächsten App-Start ist die neue Version da. Nur wenn hier im Repo ein
  neues APK-Release erscheint, ist einmal eine Neuinstallation nötig
  (das neue APK einfach über das alte installieren, deine Einstellungen
  bleiben erhalten).

## Installation (ohne Play Store)

GripCast ist noch nicht im Play Store. Die Beta wird als APK-Datei
installiert („Sideload"). Voraussetzung: **Android 7.0 oder neuer**.

1. Lade die APK-Datei aus dem aktuellen Release herunter: [Link](https://github.com/juergkeller/gripcast-releases/releases/download/v1.1.0-beta.1/GripCast-a351576a-4b34-4cfc-84df-a8e53ea23928.apk)
2. Öffne die heruntergeladene Datei (Benachrichtigung „Download abgeschlossen"
   antippen, oder über die Dateien-App).
3. Android fragt beim ersten Mal, ob dein Browser bzw. deine Dateien-App
   „unbekannte Apps installieren" darf, das musst du einmalig erlauben.
4. **Play Protect wird warnen**, dass die App nicht aus dem Play Store stammt
   bzw. der Entwickler unbekannt ist („App wurde zum Schutz deines Geräts
   blockiert"). Das ist bei jeder App ausserhalb des Stores so und kein
   Fehler, aber es stimmt: Du installierst hier Software an der Store-Prüfung
   vorbei und musst dem Herausgeber vertrauen. Genau deshalb steht in diesem
   Dokument vollständig, was die App darf und wohin Daten fliessen.
   > ⚠️ **Achtung, hier ist der häufigste Stolperstein:** In diesem Dialog ist
   > der grosse, auffällige Knopf **„Ok"**, der **bricht die Installation ab**.
   > Um fortzufahren, tippst du den kleinen, unscheinbaren Text
   > **„Trotzdem installieren"** darüber. Nicht „Ok".
5. Falls Play Protect die Installation trotzdem ganz verweigert (es erscheint
   wieder „App nicht installiert"): Öffne den Play Store → tippe oben auf dein
   Profilbild → **Play Protect** → Zahnrad/Einstellungen → schalte
   **„Apps mit Play Protect scannen" vorübergehend aus**, installiere die APK,
   und schalte es danach **wieder ein**.
6. App öffnen, Standort setzen (siehe unten), Benachrichtigungen erlauben, fertig.

## Berechtigungen

Die App fragt bzw. deklariert folgende Android-Berechtigungen. Vollständige
Liste, nichts weggelassen:

| Berechtigung | Wofür |
|---|---|
| Internet | Wettervorhersage und Bodenfeuchtedaten abrufen, Benachrichtigungen empfangen, Updates laden. |
| Benachrichtigungen | Die 19:00-Meldung und die Morgen-Korrektur: der Kern der App. |
| Standort (genau + ungefähr) | Nur wenn du in den Einstellungen auf den GPS-Knopf tippst, wird die Position **einmalig** abgefragt und gespeichert. Es gibt keine laufende Ortung im Hintergrund. Du kannst die Berechtigung auch verweigern und stattdessen einfach einen Ortsnamen eintippen. |
| Start nach Geräte-Neustart | Damit geplante Benachrichtigungen einen Neustart des Handys überleben. |
| Gerät kurz aufwecken (Wake Lock) | Für den kurzen Wettercheck im Hintergrund, der die Morgen-Korrektur ermöglicht. |
| Speicher lesen/schreiben (alt) | Wird vom App-Baukasten standardmässig eingetragen. GripCast greift auf keine Dateien, Fotos oder Medien zu; auf aktuellen Android-Versionen (11 bzw. 13 und neuer) sind diese alten Berechtigungen ohnehin wirkungslos. |

## Daten & Privatsphäre

**Kein Konto, keine Anmeldung, keine Werbung.** Es sind keine Werbe- oder
Analyse-Dienste eingebaut.

**Mit diesen Servern spricht die App:**

- **Open-Meteo** (Wetterdienst): bekommt deine Koordinaten, um Vorhersage und
  Bodenfeuchte für deinen Standort zu liefern. Wenn du deinen Standort per
  Ortsname setzt, läuft auch diese Suche über Open-Meteo.
- **BigDataCloud** (Geodienst): bekommt deine Koordinaten, um daraus den
  Ortsnamen für die Anzeige in der App zu machen (z.B. „Aarau").
- **GripCast-Server** (Firebase, Region Zürich): verschickt die
  Benachrichtigungen. Während der Beta läuft er in der Test-Umgebung des
  Entwicklers. Was dort gespeichert wird, steht unten.
- **Google Firebase Cloud Messaging**: stellt die Push-Nachrichten aufs
  Gerät zu (der technische Push-Kanal jedes Android-Handys).
- **Expo-Update-Server**: liefert die automatischen App-Updates.

**Was der GripCast-Server über dich speichert**: unter einer zufälligen
Geräte-ID, ohne Bezug zu deinem Namen, Google-Konto oder deiner Telefonnummer:

- deine Position **auf ~10 km gerundet** (die exakte Position verlässt für
  die Benachrichtigungen nie dein Gerät),
- Zeitzone, Fahrzeitfenster und deine Benachrichtigungs-Einstellungen
  (Schwellenwert, Uhrzeit-/Temperaturformat),
- den technischen Push-Zustellcode (Token) und den letzten
  Benachrichtigungs-Entscheid des Servers.

**Du hast die Kontrolle:**

- Benachrichtigungen lassen sich in den Einstellungen jederzeit abschalten.
- **„Delete Server Data"** in den Einstellungen löscht deinen Eintrag auf dem
  Server sofort und vollständig; die App funktioniert danach weiter.
- Einträge von Geräten, die sich lange nicht mehr melden, löscht der Server
  automatisch (nach rund 9 Monaten).
- App deinstallieren beendet alles. Es gibt nichts, was ohne die App
  weiterläuft.

## Feedback

Feedback bitte hier: **[Forumsthread-Link / E-Mail-Adresse] oder via juerg.keller@outlook.com**

Besonders wertvoll sind Antworten auf diese Fragen:

1. **Kamen die Benachrichtigungen an? Und zum richtigen Zeitpunkt?**
   (19:00-Meldung, Morgen-Korrektur, oder blieb eine Meldung aus, obwohl das
   Wetter gut war?)
2. **Meldet sich die App zu oft oder zu selten?** Passt der
   Standard-Schwellenwert, oder musstest du ihn verstellen?
3. **Passt der Score zum echten Trail-Zustand?** Also: War der Boden wirklich
   fahrbar, als die App GO sagte; und umgekehrt?
3. **Ist die App für dich nützlich?** 
   Siehst du Verbesserungs-Potential?

Bitte gib bei Problemen die Versionszeile aus den Einstellungen an (ganz
unten, z.B. `v1.1.0 (abc1234) · beta`). Damit lässt sich dein Stand exakt
zuordnen.

## Ausblick

Nach der Beta soll GripCast in den Play Store. Davor gibt es eine zweite
Testrunde als geschlossenen Test („Closed Test") über den Play Store selbst. 
Wer jetzt mittestet, bekommt dafür gerne wieder eine Einladung. Beim Umstieg
auf die Play-Store-Version wird einmalig eine Neuinstallation nötig sein
(andere Signatur), das kündigen wir rechtzeitig an.
