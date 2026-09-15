## **Privacy Policy for Jordan Prayer Times App and Watch Apps**

**Last Updated: 15/09/2026**
**App Version: 3.0.0**
**Developer: Munes Bani Fawaz (MrGiveItAwayTPK)**
**Wear OS Version: 2.6.0**
**Wear OS Developer: Hazem Afaneh**

Thank you for using the **Jordan Prayer Times** app. This document explains what permissions the app uses, why they are needed, and how your privacy is respected.

---

### **Data Collection and Sharing**

- **No Personal Data Collected**:
   The **Jordan Prayer Times** app does **not** collect, store, or share any personal information.

- **No Third-Party Sharing**:
   The app does not share any user data with third-party services, advertisers, or other entities.

- **All Data Stored Locally**:
   All app data (prayer times, settings, bookmarks) is stored locally on your device using SharedPreferences and app-specific directories. This data is automatically deleted when you uninstall the app.

---

### **Permissions and Usage**

Permissions are **optional and contextual** — the app only requests a permission when you use the feature that requires it. No permission is required upfront to install or run the app.

#### **Essential Permissions**

1. **`INTERNET`**
   - **Purpose**: To download the published prayer times from GitHub and to download Quran content.
   - **Usage**: Downloads prayer time data and Quran resources. No personal data is sent.

2. **`RECEIVE_BOOT_COMPLETED`**
   - **Purpose**: Allows the app to reschedule alarms and notifications after the device is restarted.
   - **Usage**: Ensures prayer time reminders continue to work after a reboot.

3. **`WAKE_LOCK`**
   - **Purpose**: Prevents the device from sleeping while delivering notifications.
   - **Usage**: Ensures accurate and timely prayer alerts.

4. **`SCHEDULE_EXACT_ALARM`** and **`USE_EXACT_ALARM`**
   - **Purpose**: Enables precise scheduling for alarms and notifications.
   - **Usage**: Delivers prayer times exactly at their scheduled times. This permission is essential for the app's core alarm clock functionality.

5. **`REQUEST_IGNORE_BATTERY_OPTIMIZATIONS`**
   - **Purpose**: Allows the app to run background tasks without interruption.
   - **Usage**: Ensures notifications are delivered even in battery-saving modes.

6. **`VIBRATE`**
   - **Purpose**: Allows the app to vibrate the device for notifications.
   - **Usage**: Provides a subtle alert for prayer times.

7. **`POST_NOTIFICATIONS`**
   - **Purpose**: Allows the app to display notifications on the device.
   - **Usage**: Sends prayer time reminders to the notification panel.

8. **`USE_FULL_SCREEN_INTENT`**
   - **Purpose**: Displays the prayer alarm over the lock screen.
   - **Usage**: When a prayer time arrives, the alarm screen appears over the lock screen — showing the prayer name, the time, and a Stop button — the same way an alarm clock app does. Nothing is transmitted; the screen is drawn locally.

9. **`FOREGROUND_SERVICE`** and **`FOREGROUND_SERVICE_MEDIA_PLAYBACK`**
   - **Purpose**: Allows the app to play Athan (call to prayer) audio in the background.
   - **Usage**: Ensures Athan sounds play even when the app is not in the foreground.

10. **`TURN_SCREEN_ON`**
    - **Purpose**: Wakes the screen when a prayer alarm fires.
    - **Usage**: Turns the display on so the alarm screen is visible, as an alarm clock does. Used only at the moment an alarm fires.

#### **Optional Permissions (Feature-Specific)**

11. **`ACCESS_FINE_LOCATION`** and **`ACCESS_COARSE_LOCATION`**
    - **Purpose**: Used ONLY for the Qibla compass feature to calculate the direction to Mecca (Kaaba).
    - **Usage**: Location data is:
      - ✅ Used locally on your device only
      - ✅ NOT stored or saved anywhere
      - ✅ NOT shared with any third parties
      - ✅ NOT tracked or logged
      - ✅ Only accessed when you open the Qibla tab
    - **Fallback**: If location permission is denied, the app uses Amman, Jordan as the default location.
    - **Control**: You can revoke this permission at any time in your device settings without affecting other app features.

12. **`SYSTEM_ALERT_WINDOW`** (Display Over Other Apps — Optional)
    - **Purpose**: Lets the prayer alarm screen appear while you are using another app.
    - **Usage**:
      - ✅ Entirely optional — the app explains it before sending you to the setting
      - ✅ Used only at the moment a prayer alarm fires, to show the alarm screen
      - ✅ The app never draws anything over other apps at any other time
      - ✅ Nothing is read from the screen or from other apps
    - **Without it**: The alarm still covers the lock screen and still shows a notification; it simply cannot appear on top of an app you are actively using.

13. **`ACCESS_NOTIFICATION_POLICY`** (Do Not Disturb Access — Optional)
    - **Purpose**: Lets the Athan sound while your phone is in Do Not Disturb.
    - **Usage**:
      - ✅ Entirely optional
      - ✅ Used only to mark the prayer notification channel as allowed to bypass Do Not Disturb
      - ✅ The app does not change your Do Not Disturb settings, schedules, or any other notification policy
    - **Without it**: Prayer alarms follow your Do Not Disturb setting like any other notification.

#### **Device-Specific Autostart Settings**

Some manufacturers (Xiaomi, Oppo, Vivo, Huawei, TECNO, Infinix and others) stop background apps beyond standard Android rules, which can prevent prayer alarms from firing. On these devices the app offers to open the manufacturer's own autostart screen so you can allow it. This is not a permission the app holds: it only opens a system settings screen, and the app reads nothing from it.

---

### **Background Services**

The app runs background services every **6 hours** for the following purposes:

- **Prayer Time Synchronization**: Downloads the published monthly prayer times from GitHub and caches them locally.
- **Alarm Rescheduling**: Updates prayer alarms based on fresh data.
- **Retry Logic**: If sync fails, retries every 15 minutes until successful.
- **Alarm Check**: Confirms today's prayer alarms are still scheduled and re-schedules any that the device dropped.

In addition, two checks run **entirely on your device with no internet access**: one every two hours, and one shortly before each prayer. Both simply re-read the prayer times already cached on your device and re-set any alarm that was dropped, so the app keeps working for days or weeks without being opened.

These background services strictly follow Android's **WorkManager** policies to optimize battery usage (96% more efficient than previous versions).

---

### **Downloaded Content**

#### **Quran Viewer Feature**

The app includes a complete Holy Quran viewer that downloads the following content:

- **Quranic Text**: Arabic text of the Holy Quran (Medina layout, Hafs narration)
- **Translations**: Quran translations in multiple languages
- **Audio Recitations**: MP3 files of Quran recitations by various reciters
- **Tafsir**: Islamic commentary and explanations
- **Fonts**: Specialized fonts for displaying Arabic Quranic text

**Storage:**
- All downloaded content is stored locally in app-specific directories
- Content is downloaded on-demand when you first use the Quran tab
- You can clear this data by uninstalling the app
- Total download size: Approximately 50-100 MB depending on selected features

**Sources:**
- Content is provided by the `quran_library` package from pub.dev
- No personal data is sent when downloading this content

---

### **Third-Party Services**

The app uses the following third-party services:

1. **Prayer Times Data (GitHub)**
   - **How the data gets there**: A separate service run by the developer reads the official prayer times from the Jordanian Ministry of Awqaf website (awqaf.gov.jo) and publishes them to a GitHub repository. That service runs independently of the app — your device never contacts awqaf.gov.jo
   - **What the app does**: The app reads those published files from GitHub
   - **Requests go to**: `api.github.com`, authenticated with a credential built into the app. The credential identifies the app, not you, and grants read access to the prayer times data only
   - **Data sent**: The city and month being requested. No account, name, contact detail or device identifier is sent
   - **Data received**: Prayer times for that city and month, plus the city list and any in-app announcement
   - **Note**: As with any internet request, GitHub can see the IP address the request comes from. This is standard for any app that downloads data and is governed by GitHub's own privacy policy

2. **Quran Library Package** (quran_library on pub.dev)
   - **Purpose**: Displaying Holy Quran with audio, translations, and commentary
   - **Data downloaded**: Quranic content (text, audio, translations)
   - **Privacy**: No personal data is sent

3. **Adhkar Content** (bundled, no network)
   - **Purpose**: The text of the adhkar, their translations and their narration references
   - **Source**: Hisnul Muslim (حصن المسلم) by Sa'id bin Ali bin Wahf al-Qahtani, taken from the open source muslim-data project
   - **Privacy**: The content ships inside the app. Nothing is downloaded and no request is made when you read adhkar

4. **OpenStreetMap** (via flutter_map package)
   - **Purpose**: Map tiles for the Qibla map view
   - **Data sent**: Map tile requests based on your location (when using Qibla map)
   - **Privacy**: No personal information is sent, only geographic coordinates for map tiles

---

### **Data We Store Locally**

The app stores the following data LOCALLY on your device:

1. **Prayer Times** - Monthly cache of prayer times for your selected city
2. **Selected City** - Your chosen city in Jordan
3. **App Settings** - Language preference, theme mode, clock format (12/24-hour), Hijri date adjustment, notification settings, selected sounds, alarm volume (overall and per prayer), whether alarms vibrate, which prayers have alarms enabled, and whether the optional sunrise alarm is on
4. **Reminder Settings** - Whether the wudu reminder is on and how early it fires; whether the morning, evening and before-sleep adhkar reminders are on, their timing and their sound; whether the Friday (Jumu'ah) reminder is on and how early; whether the Ramadan suhoor and iftar reminders are on and how early
5. **Widget Settings** - The theme, background transparency, text colours and language you chose for the home screen widgets
6. **Adhkar Progress** - How many times you have counted each dhikr today, and which chapters you marked as favourites
7. **Quran Bookmarks** - Your saved Quran bookmarks with color categories
8. **Onboarding Status** - Whether you've completed the first-time tutorial
9. **Sync Status** - Last successful sync timestamp
10. **Alarm Records** - For each alarm and reminder, the time it was set for, the time it actually fired and how late it was. Roughly the last week is kept, and it is what the app shows you under "Recent alarms" to tell you when your phone prevented an alarm from firing
11. **Diagnostics Log** - A local record of app and alarm events (see "Diagnostics Log" below)
12. **Dismissed Notices** - The IDs of in-app announcements you have already closed, so they are not shown again

**Important:**
- All data is stored using Android's SharedPreferences and app-specific storage
- No data is uploaded to external servers
- All data is automatically deleted when you uninstall the app
- You can clear all app data from Android Settings → Apps → Jordan Prayer Times → Storage → Clear Data

---

### **Diagnostics Log**

To help diagnose missed prayer alarms, the app keeps a log of its own activity on your device: when alarms were scheduled, when they fired and how late they were, when data was synced, and when settings changed.

- **Stored locally only** — the log is a file in the app's private storage and is never uploaded automatically
- **Size-capped** — the log is trimmed as it grows, so it cannot fill your storage
- **Automatically deleted** — entries older than your chosen retention window (1 to 14 days, 3 by default) are removed
- **Contains no personal information** — no contacts, no accounts, no browsing, no location, and no message content
- **Shared only if you choose to** — the app has a "Share logs" button. If you use it, the file is passed to the app you pick (email, messaging, notes) and includes your device model, Android version, which of the app's permissions are granted, and which prayer alarms are currently set. Nothing is sent anywhere unless you take that action, and you can read the whole file before sending it
- **Deletable at any time** — Settings › Troubleshooting › Developer Tools › clear logs, or by uninstalling the app

---

### **Sounds You Choose**

A prayer alarm or a reminder can play one of the bundled Athan recitations, the bundled chime, one of your device's own tones, or an audio file you pick yourself.

**Your device's ringtones**

- The app reads only the **names and locations** of the alarm, ringtone and notification tones from Android's ringtone list
- It does **not** browse your music, recordings or downloads to build that list

**An audio file you pick**

- Choosing "Choose a file from this device" opens **Android's own file picker**. The app cannot see your files: it receives only the single file you select, and only because you selected it
- Android grants the app long-lived read access to **that one file**, which the app keeps so the alarm can still play it days later or after a restart. It holds no access to anything else
- When you change that setting to a different sound, the app **drops the file from its list and hands that access back**
- The file is read on your device to play it. It is **never copied, uploaded or transmitted anywhere**

Your chosen sound is stored locally as a reference to the file, so it can be played when an alarm fires.

---

### **Features and Privacy**

#### **1. Prayer Times**
- Sourced from the official Ministry of Awqaf times, published to GitHub by a separate service the developer runs, and read from there by the app
- Cached locally by month for offline use — the app takes whichever months are published, so it usually holds more than one and keeps working across a month boundary
- Synced automatically every 6 hours

#### **2. Qibla Compass**
- Uses GPS location ONLY when you open the Qibla tab
- Location is not stored, tracked, or shared
- Works with compass and map views
- Fallback to Amman coordinates if location denied

#### **3. Quran Viewer**
- Complete offline Quran access after initial download
- Bookmarks stored locally
- Audio playback, search, and translations
- No tracking of reading habits

#### **4. Adhkar**
- 287 adhkar with their narration references, bundled inside the app — no download and no internet needed
- The tasbih counter, your daily counts and your favourites are stored locally on your device
- Morning, evening and before-sleep adhkar reminders are optional, off by default, and calculated on your device from your prayer times
- No reading or counting activity is tracked or shared

#### **5. Home Screen Widgets**
- Two optional widgets: the next prayer with a countdown, and today's prayer times
- Both read the prayer times already cached on your device and need no internet
- Their theme, background transparency, text colours and language are your choice and are stored locally
- Widgets contain no personal data and send nothing anywhere

#### **6. Multi-Language Support**
- Language preference (English/Arabic) stored locally
- Automatic RTL layout for Arabic
- No data sent regarding language choice

#### **7. Friday and Ramadan Reminders**
- An optional reminder before Jumu'ah, which fires on Fridays only and is worked out from your cached Dhuhr time
- Optional suhoor and iftar reminders that fire only during Ramadan
- Whether it is Ramadan is determined **on your device**, from the device's own Islamic calendar and the Hijri adjustment you set. Nothing is requested from the internet to decide this
- Both are off unless you turn them on, and their settings are stored locally

#### **8. Notifications**
- Prayer time alerts with your choice of Athan recitation, a bundled chime, or a ringtone from your device
- Alarms are scheduled through Android's alarm clock system, so they fire on time even when the app is closed. This is why the alarm icon appears in your status bar
- When a prayer arrives, the alarm screen appears over the lock screen and the Athan plays
- The app checks regularly that its alarms are still set, re-schedules any that your phone dropped, and tells you on the prayer screen if one was missed
- Tomorrow's alarms are automatically rescheduled after the last prayer fires — ensuring you never miss Fajr
- An optional wudu reminder can fire 5, 10 or 15 minutes before each prayer
- An alarm can be snoozed for five minutes, or silenced with a volume key
- One setting decides whether alarms and reminders vibrate as well as sound
- All notification preferences stored locally. No notification data is tracked or shared

#### **9. Wear OS Companion App**
- The app includes an optional Wear OS companion for Pixel Watch and other Wear OS smartwatches
- **Data synced to watch**: Selected city name and prayer times (local device-to-device communication via Android Wear Data Layer API)
- **No internet access** is used by the Wear OS app — it receives data exclusively from the phone app
- **No personal data** is collected or transmitted
- Prayer time notifications can be sent to your watch when the phone app fires alarms
- Disabling the Wear OS app does not affect the phone app in any way

---

### **Your Privacy Rights**

- **Access**: All your data is accessible through the app's settings
- **Deletion**: Uninstall the app to delete all local data
- **Control**: All permissions can be revoked in Android Settings
- **Portability**: No data is stored on external servers, so there's nothing to export

---

### **Children's Privacy**

This app does not knowingly collect any personal information from children. The app is suitable for all ages and contains only Islamic prayer times and Quran content.

---

### **Changes to This Privacy Policy**

We may update this Privacy Policy from time to time to reflect changes in app features or legal requirements. Any changes will be reflected in this document with an updated "Last Updated" date.

**Version History:**
- **3.0.0** (15/09/2026): Redesigned home screen and settings, with a help section in the app. Alarms now keep scheduling themselves without the app being opened, using checks that run on your device with no internet. You can pick **any audio file on your device** as an alarm sound — chosen through Android's own file picker, read only to play it, and released when you change that setting (see "Sounds You Choose"). Added a Friday (Jumu'ah) reminder and Ramadan suhoor and iftar reminders, both worked out on your device; an optional sunrise alarm; snooze; and one setting for vibration. Home screen widgets gained their own theme, transparency, text colours and language. The app now keeps a short record of which alarms actually fired and how late, shown under "Recent alarms". **No new permission is requested, and nothing new is sent anywhere**
- **2.6.0** (07/09/2026): Alarms moved to Android's alarm clock system with a lock screen alarm screen; self-repairing alarms and missed-alarm reporting; Adhkar section with tasbih counter; wudu and adhkar reminders; two home screen widgets; device ringtones as alarm sounds; clock format and Hijri date settings; local diagnostics log; phone and tablet layouts. **Device Administrator was removed** — it granted no policies and did nothing for alarm reliability, so the app no longer requests it. Two further permissions the app never used were also removed
- **2.3.0** (28/04/2026): Added Wear OS companion app, Device Admin option, persistent notifications, contextual permissions
- **2.0.0** (18/11/2025): Updated for Qibla compass, Quran viewer, and new permissions
- **1.0.x** (15/12/2024): Initial version

---

### **Ownership and Developer Rights**

The **Jordan Prayer Times** app is developed and owned by **Munes Bani Fawaz** (MrGiveItAwayTPK). All rights, including the app's design, source code, and intellectual property, belong to the developer.

---

### **Contact Information**

If you have any questions, concerns, or requests regarding this Privacy Policy or your data, please contact:

- **Lead Developer**: Munes Bani Fawaz (MrGiveItAwayTPK)
- **Email**: m.banifawaz@outlook.com

- **Wear OS Developer**: Hazem Afaneh
- **Email**: hazemafaneh@gmail.com

---

### **Acceptance**

By using the **Jordan Prayer Times** app, you acknowledge that you have read and understood this Privacy Policy.
