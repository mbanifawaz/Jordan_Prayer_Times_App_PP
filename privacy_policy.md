## **Privacy Policy for Jordan Prayer Times**

**Last Updated: 18/11/2025**
**App Version: 2.0.0**
**Developer: Munes Bani Fawaz (MrGiveItAwayTPK)**

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

The following permissions are requested for the app to function properly:

#### **Essential Permissions**

1. **`INTERNET`**
   - **Purpose**: To fetch prayer times from the official Jordanian Ministry of Awqaf website (awqaf.gov.jo) and download Quran content.
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
   - **Purpose**: Displays prayer time notifications on the lock screen.
   - **Usage**: Shows alarms over the lock screen to ensure you don't miss prayer times. This is a standard permission for alarm clock apps.

9. **`FOREGROUND_SERVICE`** and **`FOREGROUND_SERVICE_MEDIA_PLAYBACK`**
   - **Purpose**: Allows the app to play Athan (call to prayer) audio in the background.
   - **Usage**: Ensures Athan sounds play even when the app is not in the foreground.

#### **Optional Permissions (Feature-Specific)**

10. **`ACCESS_FINE_LOCATION`** and **`ACCESS_COARSE_LOCATION`**
    - **Purpose**: Used ONLY for the Qibla compass feature to calculate the direction to Mecca (Kaaba).
    - **Usage**: Location data is:
      - ✅ Used locally on your device only
      - ✅ NOT stored or saved anywhere
      - ✅ NOT shared with any third parties
      - ✅ NOT tracked or logged
      - ✅ Only accessed when you open the Qibla tab
    - **Fallback**: If location permission is denied, the app uses Amman, Jordan as the default location.
    - **Control**: You can revoke this permission at any time in your device settings without affecting other app features.

---

### **Background Services**

The app runs background services every **6 hours** for the following purposes:

- **Prayer Time Synchronization**: Fetches monthly prayer times from the Jordanian Ministry of Awqaf (awqaf.gov.jo) and caches them locally.
- **Alarm Rescheduling**: Updates prayer alarms based on fresh data.
- **Retry Logic**: If sync fails, retries every 15 minutes until successful.

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

1. **Jordanian Ministry of Awqaf API** (awqaf.gov.jo)
   - **Purpose**: Fetching official prayer times for Jordanian cities
   - **Data sent**: City name (e.g., "Amman")
   - **Data received**: Prayer times for the selected city
   - **Privacy**: No personal information is sent

2. **Quran Library Package** (quran_library on pub.dev)
   - **Purpose**: Displaying Holy Quran with audio, translations, and commentary
   - **Data downloaded**: Quranic content (text, audio, translations)
   - **Privacy**: No personal data is sent

3. **OpenStreetMap** (via flutter_map package)
   - **Purpose**: Map tiles for the Qibla map view
   - **Data sent**: Map tile requests based on your location (when using Qibla map)
   - **Privacy**: No personal information is sent, only geographic coordinates for map tiles

---

### **Data We Store Locally**

The app stores the following data LOCALLY on your device:

1. **Prayer Times** - Monthly cache of prayer times for your selected city
2. **Selected City** - Your chosen city in Jordan
3. **App Settings** - Language preference, theme mode, notification settings, selected Athan sound
4. **Quran Bookmarks** - Your saved Quran bookmarks with color categories
5. **Onboarding Status** - Whether you've completed the first-time tutorial
6. **Sync Status** - Last successful sync timestamp

**Important:**
- All data is stored using Android's SharedPreferences and app-specific storage
- No data is uploaded to external servers
- All data is automatically deleted when you uninstall the app
- You can clear all app data from Android Settings → Apps → Jordan Prayer Times → Storage → Clear Data

---

### **Features and Privacy**

#### **1. Prayer Times**
- Fetched from official Ministry of Awqaf source
- Cached locally for offline use (up to 7 days)
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

#### **4. Multi-Language Support**
- Language preference (English/Arabic) stored locally
- Automatic RTL layout for Arabic
- No data sent regarding language choice

#### **5. Notifications**
- Prayer time alerts with customizable Athan sounds
- All notification preferences stored locally
- No notification data is tracked or shared

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
- **2.0.0** (18/11/2025): Updated for Qibla compass, Quran viewer, and new permissions
- **1.0.x** (15/12/2024): Initial version

---

### **Ownership and Developer Rights**

The **Jordan Prayer Times** app is developed and owned by **Munes Bani Fawaz** (MrGiveItAwayTPK). All rights, including the app's design, source code, and intellectual property, belong to the developer.

---

### **Contact Information**

If you have any questions, concerns, or requests regarding this Privacy Policy or your data, please contact:

- **Developer**: Munes Bani Fawaz (MrGiveItAwayTPK)
- **Email**: m.banifawaz@outlook.com
- **GitHub**: https://github.com/mbanifawaz/Jordan_Prayer_Times_App

---

### **Acceptance**

By using the **Jordan Prayer Times** app, you acknowledge that you have read and understood this Privacy Policy.
