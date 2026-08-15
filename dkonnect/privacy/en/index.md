---
layout: legal
lang: en
kicker: Documents · D-Konnect
title: Privacy Policy for D-Konnect
short_title: Privacy Policy
description: "Privacy Policy for the D-Konnect app: what data is processed, who receives it, and what rights you have."
version: "1.2"
effective: 15 August 2026
application: D-Konnect (DKonnect)
package: app.denis55ka.dkonnect
developer: Denis Karmyshakov, independent developer
contact: legal@denis55ka.app
channels: Google Play, RuStore, direct APK installation
url_ru: /dkonnect/privacy/ru/
url_en: /dkonnect/privacy/en/
url_root: /dkonnect/privacy/
---

This Policy explains what data the D-Konnect application processes, why, who receives it, and what rights you have. It applies to every distribution channel (app stores and direct APK installation): one and the same build is published to all of them, so the set of third-party components is identical everywhere. That set is listed in **Appendix A**.
{: .lead}

## Summary
{: #s1}

- The app requires **no account and no registration**. We do not ask for your name, e-mail or phone number, and we do not create a server-side user profile.
- The app has **no backend of our own**. Vehicle readings, settings, indicators, formulas and measurement history are stored **only on your device** and are never sent to us.
- The app **does not collect or store your geographic coordinates**. The location permission is used to obtain **speed** and **altitude** from the system for the corresponding indicators.
- What does leave the device is **anonymous technical telemetry** (crash reports and aggregated launch statistics) and the data required by the ad network. **Both are present in every build of the app**, whichever channel you installed it from (Appendix A).
- **Personalised ads can be switched off inside the app** — Settings → Privacy. Where the law requires consent to be obtained in advance (the EEA, the United Kingdom, Switzerland) the switch starts **off**, and turning it on is what gives that consent; elsewhere it starts on and can be turned off at any moment. Ads are shown either way: the switch decides how they are chosen, not whether they appear (section 5).
- We **do not sell** user data and do not share it with third parties for their own independent use, other than as described in sections 5 and 6.

## Data processed and kept on your device
{: #s2 data-toc="Data kept on your device"}

The following is stored in the app's local databases and preference files. We have no access to it: it is sent neither to us nor to third parties.

| Category | What it is | Why |
|---|---|---|
| Vehicle profiles | profile name and its set of indicators | keeping settings separate per vehicle |
| Indicators and formulas | custom and predefined indicators, units, conversion formulas, OBD request (PID) configurations | rendering readings on the dashboard |
| Connection (source) configurations | adapter initialisation command sequences (e.g. `ATZ`, `ATE0`, `ATSP0`) | correct handshake with a specific adapter |
| Vehicle data | values received from the OBD-II adapter (RPM, temperature, voltage, etc.) and values computed by your formulas | display and charting |
| Measurement history | a timestamped log of readings, errors and no-data markers; bounded in size, with the oldest rows removed automatically | charts, diagnostics, reviewing past trips |
| Known adapters | MAC address and display name of Bluetooth adapters you have connected to | quick reconnection and the known-devices list |
| App settings | interface and behaviour preferences | remembering your choices |

**Vehicle identifiers.** The app does not request a VIN and does not tie data to a vehicle automatically. If you create an indicator that reads the VIN or another control-unit identifier, that value is processed and stored **locally**, like any other reading.

**Deletion.** All of the above is removed when the app is uninstalled, and also via the system "Clear data" function (Settings → Apps → D-Konnect → Storage). Individual items (profiles, indicators, known adapters, history) can be deleted inside the app.

## Device permissions and why they are needed
{: #s3 data-toc="Device permissions"}

Permissions are requested only when needed, with the reason shown at the time of the request.

| Permission | Purpose | If denied |
|---|---|---|
| Bluetooth scan (`BLUETOOTH_SCAN`) | discover a nearby OBD-II adapter. Declared with the `neverForLocation` flag — the app **does not** derive location from Bluetooth scan results | a new adapter cannot be discovered |
| Bluetooth connect (`BLUETOOTH_CONNECT`) | connect to the selected adapter and read its name | the adapter cannot be connected |
| Location, approximate and precise (`ACCESS_COARSE_LOCATION`, `ACCESS_FINE_LOCATION`) | obtain **speed** and **altitude** from the system for the corresponding indicators. Coordinates are not stored, not displayed and not transmitted | the speed and altitude indicators do not work; everything else keeps working |
| Foreground service (`FOREGROUND_SERVICE` with the `location` and `connectedDevice` types) | keep reading from the adapter and recording history while the screen is off or the app is in the background — that is, during a drive | recording stops when the app is backgrounded |
| Notifications (`POST_NOTIFICATIONS`) | show the mandatory notice that background recording is active | Android may restrict background work; recording becomes less reliable |

Any permission can be revoked in Android system settings at any time.

## Data collected automatically while you use the app
{: #s4 data-toc="Data collected automatically"}

The app processes operational data on the device and, to the extent described below, sends part of it to third-party services:

- **Crash reports:** device make and model, OS version, app version, stack trace, crash time and a short technical trail of recent in-app actions (for example, "connection started", "adapter responded"). This trail contains no vehicle readings, no coordinates and no names you have typed.
- **Aggregated usage statistics:** app launches and session duration, which feed audience metrics (active users, retention). We do not send custom events containing your profiles, indicators or formulas.
- **Identifiers:** third-party SDKs generate their own installation identifier, and use the device advertising identifier **only while personalised ads are switched on** (section 5). The installation identifier is reset on reinstall and is not linked to your identity.

The legal basis for this processing is the developer's legitimate interest in keeping the app functional and stable (see section 8). There is **no in-app toggle for crash reports and usage statistics**; this collection stops when the app is uninstalled. Use of the advertising identifier **for personalised advertising** is a separate question with its own control — see section 5.

## Third-party services
{: #s5}

The same set of third-party components is present in **every** build, whatever the distribution channel. The full list, with links to each provider's policy, is in [Appendix A](#appendix). We pass these services only the data listed in section 4 and Appendix A; each provider processes it under its own policy.

Categories of services used:

1. **Crash reporting and technical diagnostics** — required to ship stable updates.
2. **Aggregated usage analytics** — audience-level metrics only.
3. **Advertising network** — present in **every** build of the app. An ad network may process the advertising identifier, device information and approximate location derived from the IP address in order to select and count impressions. What it is allowed to use for that depends on your choice — see "Personalised ads and your choice" below. Ads are never shown on the dashboard screen while driving.
4. **App store payment processing** — if purchases are available in your build (section 6).

### Personalised ads and your choice

The app **shows no consent dialog**. The starting position of the setting is decided by the jurisdiction the device appears to be in, and you can change it at any time.

**How the starting position is decided.** The app makes no network request to establish this: it reads the country of the SIM card, the country of the mobile network, the region of the device's own language setting and the region of the device time zone. If any of them points to the European Economic Area, the United Kingdom or Switzerland — or if none of them answers at all — the app starts with personalisation **off**. Everywhere else it starts on. These signals are read on the device and are not transmitted or stored.

**The control.** Settings → Privacy → "Personalised ads". It can be moved in either direction, as many times as you like: withdrawing is exactly as easy as giving. Your choice and the date you made it are kept on the device and sent nowhere.

**What "off" means.** The ad SDK is instructed not to use the advertising identifier, not to use the approximate location, and not to carry out install and attribution reporting. **Ads are still shown**, selected without those signals. The same choice reaches the crash-reporting and analytics SDK of section 4, which then collects no advertising identifier either — the switch is not limited to the ad network.

What "off" does *not* stop is crash reporting itself and the aggregated audience metrics: those stand on a different basis, have no in-app toggle, and once the switch is off they carry no advertising identifier.

Independently of this setting, Android's own settings let you reset or delete the advertising identifier for every app at once ("Privacy" → "Ads").

### AppMetrica serves two purposes at once

The Yandex Mobile Ads SDK ships together with the AppMetrica library, which therefore enters the app as a dependency of the ad SDK. The app also **activates** AppMetrica with its own key and uses it as its crash reporting and audience metrics service (section 4). Both are true of every build.

So the same library serves two purposes in parallel: the ad SDK's own technical needs, under Yandex's key, and ours, under the app's key. It is listed once in [Appendix A](#appendix) and the data column covers both.

## In-app purchases
{: #s6}

If your build offers paid features, payment is processed **by the app store** the app was installed from. Card details are entered in the store's own interface: the developer **does not receive, see or store them**. The app receives only the fact that a purchase exists, in order to unlock the paid features. Refunds and payment disputes are governed by the rules of that store.

## Backup and transfer to a new device
{: #s7 data-toc="Backup and transfer"}

Android may include app data in system backup and in device-to-device transfer. The backup contains **settings and configuration only**: profiles, indicators, formulas, connection configurations, the list of known adapters (including their MAC addresses) and app preferences. **Measurement history is excluded from backup.**

The backup is handled by your device's system backup service, not by the developer. Backup can be disabled in Android system settings.

## Legal bases and applicable law
{: #s8 data-toc="Legal bases"}

This Policy is written to satisfy the law of the jurisdictions the app is distributed in, in particular:

- **Russian Federation:** Federal Law No. 152-FZ of 27 July 2006 "On Personal Data". No personal data is processed on the developer's servers — there is no such infrastructure; local data is processed on the user's device.
- **EEA, United Kingdom and Switzerland:** Regulation (EU) 2016/679 (GDPR) and the equivalent UK and Swiss rules. Legal bases: *consent* — for location access and Bluetooth access (given through the system permission dialog) and for personalised advertising (given by turning on the switch described in section 5, which starts off in these countries, so no personalisation takes place until you act); *legitimate interest* — for crash diagnostics and aggregated statistics needed to keep the app working; *performance of a contract* — for providing the app's functionality and any purchased features.
- **United States (California and states with comparable laws):** these give you the right to opt out of the "sale" or "sharing" of personal information for targeted advertising. The switch in Settings → Privacy is that opt-out. We do not exchange user data for money.

The third-party services listed in Appendix A may process data outside your country; such transfers take place under those providers' own terms.

## Retention
{: #s9}

- **Local data** is kept for as long as the app is installed and you have not deleted it; the measurement history is additionally bounded in size, and the oldest records are pruned automatically.
- **Crash reports and statistics** are retained by the service providers for the periods set in their policies (typically from several months to about 18 months).

## Your rights
{: #s10}

You may:

- **be informed** about what data is processed — this Policy is the complete list;
- **delete your data** — through in-app functions, through the system "Clear data" action, or by uninstalling the app; local deletion is complete and irreversible;
- **withdraw permissions** (location, Bluetooth, notifications) in Android settings;
- **turn off personalised ads** with the switch in the app (Settings → Privacy), and additionally reset or opt out of the advertising identifier in Android settings;
- **contact the developer** (see section 15 "Contact") to request access, correction or erasure, or to complain. We respond within 30 days. Please note that, because the app has no accounts, we have no technical means to link an anonymous crash report to a specific person; in such cases we will help you delete on-device data and point you to the relevant provider;
- **lodge a complaint with a supervisory authority** in your country of residence (in the EEA/UK, your data protection authority; in Russia, Roskomnadzor).

## Children
{: #s11}

The app is intended for drivers and vehicle owners and is **not directed at children under 16**. We do not knowingly collect children's data. If you believe a child has provided data to the developer, write to us at the address in section 15 "Contact" and it will be deleted.

## Security
{: #s12}

App data is stored in the app's private directory, isolated from other apps by Android. The connection to the OBD-II adapter is local (Bluetooth); no internet connection is used to transfer vehicle data. Transmission to the third-party services listed in Appendix A is performed over secure channels by their SDKs.

No technical measure guarantees absolute security. If a vulnerability affecting users is discovered, we will disclose it in the update notes and, where necessary, through the app store.

## Safety notice
{: #s13}

The app displays on-board diagnostic data and is not a measuring instrument or a certified diagnostic device. Do not interact with the app while driving. The developer is not liable for decisions made on the basis of the app's readings.

## Changes to this Policy
{: #s14}

We may update this Policy when the app's functionality or its set of third-party services changes. The current version is always available at the address shown on the app's store listing and in the app's Settings screen. For material changes (a new category of collected data, or a new recipient) we will say so in the update notes. The version date is stated at the top of this document; earlier versions are available on request.

## Contact
{: #s15}

For any privacy or data protection question:

[legal@denis55ka.app](mailto:legal@denis55ka.app){: .contact}

## Appendix A. Third-party services
{: #appendix data-mark="A" data-toc="Third-party services"}

One and the same build is published to every distribution channel, so this list applies whichever way you installed the app. A component not listed here is **absent** — its SDK is not shipped.

| Service | Provider | Purpose | Data | Policy |
|---|---|---|---|---|
| AppMetrica | Yandex LLC | crash reporting and aggregated audience metrics, and at the same time the technical service of the ad SDK (section 5) | device model, OS and app version, stack trace, technical action trail, installation identifier; advertising identifier only while personalised ads are on (section 5) | [yandex.com/legal/metrica_termsofuse](https://yandex.com/legal/metrica_termsofuse/) |
| Yandex Mobile Ads | Yandex LLC | advertising | advertising identifier (only while personalised ads are on — section 5), device and network information, approximate location from IP, impression data | [yandex.com/legal/confidential](https://yandex.com/legal/confidential/) |

**No payment component is currently shipped.** The app offers no paid features, so neither Google Play Billing nor RuStore billing is included in the build. Section 6 describes how purchases would be handled if paid features appear; the billing service of the corresponding store will be added to this table in the same release.

**No Google analytics or crash reporting service is shipped either.** Earlier versions of the app used Firebase Crashlytics and Firebase Analytics in the Google Play build; they have been removed, and AppMetrica now performs both tasks in every channel. The build does contain Google libraries that supply the advertising identifier and the App Set ID to the SDKs above (`play-services-ads-identifier`, `play-services-appset`); these read identifiers on the device and are not themselves recipients of your data.

If a build with a different set of third-party services is released, this Appendix will be updated in the same release.
