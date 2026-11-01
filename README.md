# Autonomous Trash Tracking System

A smart waste-management system that combines sensor-equipped dustbins, an Android app for citizens, and a web dashboard for municipalities. Bins report their fill status, users find the nearest suitable bin for wet, dry, or metal waste, and municipalities manage the bins from a website.

📄 **Paper:** [Autonomous Trash Tracking System (IJSREM, 2024)](https://doi.org/10.55041/IJSREM34329)

> Reshika N, Varsha M C, Vignesh H, Vinay M, and Dr. Vasudeva G
> *International Journal of Scientific Research in Engineering and Management (IJSREM)*, Volume 08, Issue 05, May 2024
> DOI: [10.55041/IJSREM34329](https://doi.org/10.55041/IJSREM34329)

---

## Repository Status

This repository documents the design and results of the project as published. The original source code (Android app, municipal website, and Arduino firmware) is not included.

---

## Problem

Traditional waste collection runs on fixed schedules that ignore how full the bins actually are. This leads to overflowing bins, littering, and wasted collection trips. Citizens also have no easy way to find an available bin, and municipalities lack real-time data.

## Solution Overview

| Component | Purpose |
|---|---|
| **Smart dustbins** | Measure fill level and sort waste types using sensors |
| **Android app ("4DustbinApp")** | Lets users sign up, choose a waste type, find nearby bins, and navigate to them |
| **Municipal website** | Lets authorities add, view, modify, and delete bins and see their status on a map |
| **Notifications** | Alerts users or authorities when bins need attention (GSM/SMS in the hardware setup) |

### Workflow

```
User registration/login → Waste type selection → Location selection →
Sensor integration → Real-time data analysis → Communication with municipality → Notification system
```

## Hardware

The paper's prototype setup uses:

- 3 dustbins
- Inductive proximity sensors (metal detection)
- Ultrasonic sensors (fill-level measurement)
- Moisture sensors (wet vs. dry waste)
- Arduino board (central processing unit)
- GSM module (alerts by text message)
- Connecting wires

The **dustbin management** design uses two bin types (**wet** and **dry**). Each has an ultrasonic sensor with a color-coded status:

| Color | Meaning |
|---|---|
| 🟢 Green | Empty |
| 🟡 Yellow | Medium fill |
| 🔴 Red | Full |

The app also alerts the user if they put waste in the wrong bin type.

> The paper's design specifications also mention an ESP32, an IR sensor, and a moisture sensor as hardware options.

## Software

**Android app** (screens shown in the paper):

1. Sign up and log in
2. Choose the waste category (wet, dry, metal)
3. Find nearby trash cans using GPS and the **Google Places API**
4. Pick a bin and view its type, coordinates, and fill percentage
5. Navigate to it using the **Google Maps SDK**
6. Confirm disposal and give feedback

**Municipal website:**

- Admin login
- Add a bin (Bin ID, latitude, longitude, percentage, type)
- View all bins in a table and on a map
- Modify or delete bins

**Technologies the paper lists for development:** Kotlin, Java, and Swift for mobile; HTML5, CSS3, and JavaScript frameworks (React.js or Angular.js) with Node.js or Django for the web application; Arduino or Raspberry Pi for hardware prototyping.

## Results

The paper presents a working prototype demonstrated through screenshots: the sign-up and login screens, the list of nearby bins with fill percentages, map navigation, the sensor-equipped dustbins, and the municipal website with its bin table and map view. It does not report quantitative measurements such as sensor accuracy or response time.

## Scope Notes

- The conclusion refers to artificial intelligence and predictive analytics. The system described in the methodology and results is based on sensors, a mobile app, and a web dashboard, and the paper does not describe a trained prediction model.
- The paper tested a small prototype (three bins). It does not report a real-world deployment.

## Citation

```
Reshika N, Varsha M C, Vignesh H, Vinay M, and Vasudeva G,
"Autonomous Trash Tracking System,"
International Journal of Scientific Research in Engineering and Management (IJSREM),
vol. 8, no. 5, May 2024. DOI: 10.55041/IJSREM34329
```



## Authors

- **Reshika N** (Reshika Nimmala) — [@Dolly1002-source](https://github.com/Dolly1002-source)
- Varsha M C
- Vignesh H
- Vinay M
- Dr. Vasudeva G (guide), Department of Electronics and Communication, Dayananda Sagar Academy of Technology and Management, Bangalore






