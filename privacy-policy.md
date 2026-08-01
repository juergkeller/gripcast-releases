# GripCast Privacy Policy

**Effective date:** 1 August 2026

## 1. Controller

Jürg Keller
juerg.keller@outlook.com

GripCast is a free app with no ads, no accounts, and no commercial use of
your data.

## 2. What data is processed

### 2.1 Services your device contacts directly

GripCast needs no account, and your settings stay on your device. To show a
forecast, the app queries the following services directly from your device:

| Service | Receives | Purpose |
|---|---|---|
| Open-Meteo (weather data) | A grid coordinate with ~10 km resolution (e.g. "47.4,8.0") and your device's IP address | Weather forecast, soil moisture, recent precipitation |
| BigDataCloud (geocoding) | The same grid coordinate and your device's IP address | The place name shown in the app (e.g. "Aarau") |
| Expo (app updates) | Your device's IP address and technical data such as app version, runtime version, and platform | Delivering the automatic app updates |

Your exact position is **never** part of these requests: the app rounds every
outgoing coordinate to the ~10 km grid before the request leaves your device,
the same resolution it uses for the server (see Section 8).

None of these requests carry your installation ID, an account, or any other
identifier issued by GripCast. These services do see your IP address, and
their own logging is governed by their respective privacy policies.

### 2.2 Data stored on the GripCast server

There is no server-side storage unless you **enable notifications**. Only
then does the GripCast server store the following data per installation
(data categories):

| Data category | Content | Purpose |
|---|---|---|
| Coarse location | Grid coordinate with ~10 km resolution (e.g. "47.4,8.5"). The rounding happens on your device before anything is transmitted, so **your exact position never reaches the GripCast server** | Weather forecast for your region |
| Time zone | IANA time zone (e.g. "Europe/Zurich") | Delivering notifications at the correct local time (7 p.m. / morning re-check) |
| Push token | Technical delivery token from Firebase Cloud Messaging (FCM) | Delivering the notification to your device |
| Notification settings | Ride windows (weekday/weekend time slots), score threshold, 12h/24h display format, active status | Deciding whether and what to notify about |
| Notification history state | Anti-spam counter (consecutive days of good weather), last notification decision | Prevents repeated daily notifications during extended periods of good weather |

Each installation is identified by a **random, pseudonymous installation
ID**. It has no connection to device identifiers, accounts, or persons.
**The GripCast server does not collect:** your exact GPS position (see
Section 8), location name, name, email address, device IDs, advertising IDs,
or usage statistics.

In addition, the server stores aggregated **run statistics** (e.g. number
of notifications sent per run) without any reference to persons or
installations.

## 3. Purpose of processing

The sole purpose is the **calculation and delivery of bike-weather
notifications**: in the evening (and in the morning as a re-check), the
server evaluates the weather forecast for your grid coordinate and sends a
push notification if good bike weather is expected during your ride
windows. There is no use for advertising, profiling, or analytics.

## 4. Legal basis

Server-side processing (Section 2.2) is based on your **consent**, which you
give by enabling notifications in the app settings (Art. 6(1)(a) GDPR and
consent under the Swiss revFADP; also performance of a contract: the feature
cannot technically be provided without this data). You can withdraw your
consent at any time, either by disabling notifications or completely via
**"Delete server data"** (see Section 7).

The queries described in Section 2.1 are necessary to provide the app you
requested (Art. 6(1)(b) GDPR); without them the app cannot display a
forecast.

## 5. Recipients and processors

- **Google Ireland Ltd. / Google LLC (Firebase):** The GripCast server
  runs on Firebase (Cloud Firestore, Cloud Functions, Firebase Cloud
  Messaging). Storage and processing take place in the **Zurich,
  Switzerland (europe-west6)** region. Delivery of push messages via FCM
  may be **routed globally** for technical reasons. Google acts as a
  processor under the Google Cloud / Firebase **Data Processing Terms**,
  including **Standard Contractual Clauses (SCC)**; as a US provider,
  Google is subject to the CLOUD Act.
- **Open-Meteo (weather data provider):** receives data on two separate
  paths, both carrying only the **grid coordinate** (~10 km) and no
  installation ID. Requests made by the GripCast server additionally carry
  no IP address of your device; requests made by the app itself carry your
  device's IP address, as any direct request does.
- **BigDataCloud (geocoding provider):** receives the grid coordinate and
  your device's IP address when the app resolves the place name it
  displays. No installation ID, no account reference.
- **Expo / Expo Application Services (app updates):** receives your
  device's IP address and technical data (app version, runtime version,
  platform) whenever the app checks for updates.

Data is **never shared for advertising purposes** and never sold.

## 6. Storage period

- **Until you delete it** ("Delete server data" in the settings, deletes
  immediately).
- **Automatically**, without any action on your part:
  - After you uninstall the app, the push token becomes invalid; the
    server deletes the record after **3 failed delivery attempts**.
  - At the latest after **270 days without any sign of life** from the
    installation, the record is deleted by a weekly cleanup run.
- **Run statistics** (with no reference to persons) are automatically
  deleted after **30 days**.

Disabling notifications (without deletion) leaves the record in place so
that re-enabling works immediately; no notifications are calculated or
sent in the meantime. To remove all server data, use "Delete server data".

The services listed in Section 2.1 keep their own server logs under their
own retention rules. GripCast has no influence over those and receives no
data from them about you.

## 7. Your rights and the in-app deletion path

You have the right to access, rectification, erasure, restriction of
processing, and data portability, as well as the right to withdraw consent
at any time. To exercise these rights, contact juerg.keller@outlook.com.

**Deletion directly in the app:** Settings → **"Delete server data"**.
This immediately and irreversibly deletes this installation's record from
the server, discards the pseudonymous installation ID and replaces it with
a new one, and **disables** notifications. Only when you enable
notifications again (new consent) does the device re-register, under the
new ID, which cannot be linked to the deleted data.

Right to complain: you can lodge a complaint with the competent
supervisory authority (Switzerland: Federal Data Protection and
Information Commissioner, FDPIC; EU: your national data protection
authority).

## 8. Location: what goes where

You set your location either by typing a place name or by tapping the GPS
button, which queries your position **once** and stores it on your device.
There is no location tracking, and none in the background.

**Your exact position never leaves your device.** Every outgoing request,
whether to the GripCast server, to Open-Meteo, or to BigDataCloud, carries
only a coordinate rounded to a ~10 km grid; the rounding happens on your
device before the request is sent. That is also why the place name shown in
the app may occasionally be a neighbouring town: it is derived from the grid
cell, not from your exact position.

## 9. Beta phase

While GripCast is in public beta, the app is distributed as an APK outside
the Play Store, and the GripCast server runs in the developer's test
project (`gripcast-dev`), likewise in the Zurich (europe-west6) region. The
data categories, storage periods, and deletion path described in this
policy apply there unchanged.

## 10. Google Play "Data safety" form

The entries in the Google Play "Data safety" form correspond to this
policy.
