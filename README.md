# 🌱 EpiCircle React Native Assignment

[![React Native](https://img.shields.io/badge/React%20Native-v0.74.5-blue)](https://reactnative.dev/)
[![Expo](https://img.shields.io/badge/Expo-v51.0.0-orange)](https://expo.dev/)
[![License: MIT](https://img.shields.io/badge/License-MIT-green)](https://opensource.org/licenses/MIT)

A React Native project developed for the EpiCircle internship assignment, showcasing two mobile applications designed to support sustainable waste management:

- **Customer App**: Enables users to schedule scrap pickups and track their order history.
- **Partner App**: Allows partners to accept, manage, and track pickup requests.

This project demonstrates my proficiency in React Native, Expo, API integration, and user-centric UI/UX design, aligning with EpiCircle's mission to promote eco-friendly solutions.

---

## 📖 Table of Contents

- [Project Overview](#project-overview)
- [Features](#features)
- [Tech Stack](#tech-stack)
- [Repository Structure](#repository-structure)
- [Prerequisites](#prerequisites)
- [Setup Instructions](#setup-instructions)
- [Database Structure](#database-structure)
- [Notes](#notes)
- [Video Walkthrough](#video-walkthrough)
- [Contact](#contact)
- [License](#license)

---

## 🌟 Project Overview

The EpiCircle React Native Assignment consists of two apps built to streamline waste collection:

- **Customer App**: Empowers users to schedule scrap pickups with date, time, and location details, view their pickup history, and toggle between light/dark themes for accessibility.
- **Partner App**: Equips partners with tools to view and accept pending pickup requests, schedule new pickups, track completed orders, and monitor performance via a dashboard.

Both apps integrate with a `json-server` API, ensuring seamless coordination between customers and partners. The project highlights my skills in mobile development, API integration, and modern UI/UX design, developed under a tight deadline to meet EpiCircle’s internship requirements.

---

## ✨ Features

### Customer App
- ✅ **Login with OTP**: Secure phone-based authentication with a smooth OTP input flow.
- ✅ **Schedule Pickup**: Select date, time, and address, with live location support (assumed).
- ✅ **Order History**: Track past pickups with status updates (Pending, Completed).
- ✅ **Dark/Light Theme**: Toggle themes for enhanced accessibility and user comfort.
- ✅ **Modern UI**: Animated cards, consistent styling, and eco-friendly branding.

### Partner App
- ✅ **Login with OTP**: Secure and user-friendly authentication.
- ✅ **Dashboard**: Displays today’s pickups, earnings, and a theme toggle button.
- ✅ **View Requests**: Accept pending pickup requests with toast notifications.
- ✅ **Schedule Pickup**: Create new pickup requests with date and location inputs.
- ✅ **Order History**: Review completed pickups with a fallback for empty states.
- ✅ **Responsive Design**: Card-based UI with animations and dark mode support.

---

## 🛠️ Tech Stack

- **Frontend**: React Native v0.74.5, Expo v51.0.0
- **Navigation**: `@react-navigation/native`, `@react-navigation/stack`
- **API Integration**: `axios` for RESTful API calls
- **Animations**: `react-native-animatable`, `lottie-react-native`
- **Icons**: `@expo/vector-icons`
- **State Management**: React Hooks, Context API (`ThemeContext`)
- **Storage**: `@react-native-async-storage/async-storage`
- **Backend**: `json-server` for mock REST API
- **Development Tools**: Node.js v20.x, npm, Android Studio (emulator)

---

## 📂 Repository Structure

```
root/
├── customer-app/
│   ├── screen/
│   │   ├── LoginScreen.js
│   │   ├── OTPScreen.js
│   │   ├── DashboardScreen.js
│   │   ├── SchedulePickupScreen.js
│   │   ├── ViewHistoryScreen.js
│   │   ├── ThemeContext.js
│   ├── assets/
│   │   ├── loader.json
│   ├── App.js
│   ├── package.json
├── partner-app/
│   ├── screen/
│   │   ├── LoginScreen.js
│   │   ├── OTPScreen.js
│   │   ├── DashboardScreen.js
│   │   ├── SchedulePickupScreen.js
│   │   ├── ViewHistoryScreen.js
│   │   ├── ViewRequestsScreen.js
│   │   ├── ThemeContext.js
│   ├── assets/
│   │   ├── loader.json
│   ├── App.js
│   ├── package.json
├── db.json
├── README.md
```

---

## 🔧 Prerequisites

- **Node.js**: ≥ 16.x (20.x recommended)
- **npm**: Included with Node.js
- **Expo CLI**: For running React Native apps
- **json-server**: For mock API
- **Android Studio**: For Android emulator (optional)
- **Screen Recorder**: Kazam or OBS Studio for video demo
- **Git**: For cloning the repository

Install prerequisites on Linux (Ubuntu):
```bash
# Install Node.js via nvm
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh | bash
nvm install 20
nvm use 20

# Install Expo CLI and json-server
npm install -g expo-cli json-server

# Install Android Studio
sudo snap install android-studio --classic

# Install Kazam
sudo apt update
sudo apt install kazam
```

---

## 🚀 Setup Instructions

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/mohit-kumawat/epicircle-assignment.git
   cd epicircle-assignment
   ```

2. **Install Dependencies**:
   - Customer App:
     ```bash
     cd customer-app
     npm install
     ```
   - Partner App:
     ```bash
     cd ../partner-app
     npm install
     ```

3. **Configure Android SDK (Linux)**:
   - Open Android Studio, go to **Settings → Android SDK**, and install SDK Platform (API 33).
   - Set environment variables:
     ```bash
     nano ~/.bashrc
     ```
     Add:
     ```bash
     export ANDROID_HOME=$HOME/Android/Sdk
     export PATH=$PATH:$ANDROID_HOME/platform-tools:$ANDROID_HOME/emulator
     ```
     Apply:
     ```bash
     source ~/.bashrc
     ```

4. **Start JSON Server**:
   - In the root directory:
     ```bash
     json-server --watch db.json --host <your-local-ip> --port 3000
     ```
     - Find your IP:
       ```bash
       ip addr show
       ```
     - Update `API_URL` in `ViewRequestsScreen.js`, `ViewHistoryScreen.js`, and `SchedulePickupScreen.js` to `<your-local-ip>:3000/pickups`.

5. **Run the Customer App**:
   - In a new terminal:
     ```bash
     cd customer-app
     npx expo start --clear
     ```
   - Press `a` for Android emulator, `i` for iOS simulator, or scan the QR code with Expo Go on a device.

6. **Run the Partner App**:
   - In another terminal:
     ```bash
     cd ../partner-app
     npx expo start --clear
     ```
   - Run as above.

---

## 🗄️ Database Structure

**`db.json`** example:
```json
{
  "pickups": [
    {
      "id": 1,
      "date": "2025-07-10",
      "timeSlot": "2:00 PM",
      "address": "123 Green Street",
      "status": "Pending"
    },
    {
      "id": 2,
      "date": "2025-07-09",
      "timeSlot": "10:00 AM",
      "address": "456 Oak Avenue",
      "status": "Completed"
    }
  ]
}
```

**Status Workflow**:
- **Customer**: Creates pickup → `Pending`
- **Partner**: Accepts pickup → `In Queue`
- **Partner**: Completes pickup → `Pending for Approval`
- **Customer**: Approves → `Completed`

---

## 📝 Notes

- **Local IP**: Replace `192.168.223.239` with your machine’s IP in API URLs to ensure connectivity.
- **Expo Go**: Ensure your device and PC are on the same Wi-Fi network.
- **Dark Mode**: Toggle themes via the dashboard in both apps.
- **Emulator Issues**: If the Android emulator fails, verify `ANDROID_HOME` and restart `adb`:
  ```bash
  adb kill-server
  adb start-server
  ```
- **Dependencies**: Clear Metro cache if errors occur:
  ```bash
  npx expo start --clear
  ```

---

## 🎥 Video Walkthrough

[Video link to be added after recording]

A demo video showcasing both apps’ features, including login, OTP verification, dashboard navigation, pickup scheduling, request acceptance, and order history, will be uploaded to Google Drive or YouTube.

---

## 📧 Contact

For questions or feedback:

**Mohit Kumawat**  
📧 [mohit.kumawat23b@iiitg.ac.in](mailto:mohit.kumawat23b@iiitg.ac.in)  
🌐 [GitHub Profile](https://github.com/mohit-kumawat)  
🔗 [LinkedIn Profile](https://www.linkedin.com/in/mohit-kumawat) *(Update with your actual link)*

---

## 📜 License

This project is licensed under the [MIT License](LICENSE).

---

**Developed with 💚 for EpiCircle’s mission to create a sustainable future.**
