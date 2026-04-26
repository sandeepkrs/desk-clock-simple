# 📖 Kindle Desk Clock & Weather Dashboard

A minimalist, high-contrast web dashboard optimized specifically for **Kindle Paperwhite (10th Generation)** and other E-ink devices. This project repurposes an e-reader into a dedicated desk clock, calendar, and weather station.

## ✨ Features
* **Precision Clock:** Syncs exactly with the minute rollover (00 seconds).
* **Dynamic URL Params:** Change location and timezone without editing the code.
* **E-ink Friendly:** High-contrast design with ghosting prevention (1-hour hard refresh).
* **Responsive:** Clean side-by-side layout for Time and Weather.

---

## 🚀 Dynamic Configuration (URL Parameters)

You can customize the dashboard by adding parameters to your GitHub Pages URL.

| Parameter | Description | Default Value |
| :--- | :--- | :--- |
| `city` | The city name for weather data | `Bengaluru` |
| `tz` | The IANA Timezone string | `Asia/Kolkata` |

### ⚠️ IMPORTANT
You must use the **exact** IANA Timezone string (e.g., `Asia/Kolkata`, not `IST`). If the timezone string is misspelled or formatted incorrectly, the JavaScript will fail and the page will show **"LOADING..." forever** instead of the time.

### Common Timezone & City Samples
| Region | City | Sample URL Segment |
| :--- | :--- | :--- |
| **India** | Bengaluru | `?city=Bengaluru&tz=Asia/Kolkata` |
| **UK** | London | `?city=London&tz=Europe/London` |
| **USA (East)** | New York | `?city=NewYork&tz=America/New_York` |
| **USA (West)** | San Francisco | `?city=SanFrancisco&tz=America/Los_Angeles` |
| **Dubai** | Dubai | `?city=Dubai&tz=Asia/Dubai` |
| **Singapore** | Singapore | `?city=Singapore&tz=Asia/Singapore` |

---

## 🚀 Quick Setup

### 1. View on your Kindle
1.  **Disable Sleep:** On your Kindle Home screen, search for `~ds` and press Enter. (Restart Kindle to re-enable sleep). [No longer working on latest kindle, so just increase the screen timeout]
2.  **Open Browser:** On your Kindle open Browser and enter the url `https://sandeepkrs.github.io/desk-clock-simple/?city=Bengaluru&tz=Asia/Kolkata` (including any parameters for city/tz).
3.  **Bookmark Link:** Bookmark the url to easily access this later.

### 0. Host the Code
If you plan to customize the page to your needs and host it by yourself, follow these steps:
1.  Upload your updated `index.html` file to a GitHub repository.
2.  Enable **GitHub Pages** in `Settings > Pages`.
3.  Access your page via `https://<your-username>.github.io/<repo-name>/`

---

## 🛠 Technical Details

### Power Management
E-ink displays consume very little power, but the Kindle's Wi-Fi remains active to fetch weather. 
* **Recommendation:** Keep the device connected to a power source for 24/7 desk-clock use.

### Ghosting Prevention
Every **60 minutes**, the page performs a `location.reload()`. This triggers a full-screen flash to clear E-ink "ghosting" (faint shadows of previous numbers) and ensures the browser does not freeze.

### Weather Sync
Weather is fetched every **30 minutes** from `wttr.in`. If the weather shows "OFFLINE," check your Kindle's Wi-Fi connection.

---

## ⚖️ License
MIT License - Feel free to use, modify, and share!
