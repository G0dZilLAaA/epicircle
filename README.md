# EpiCircle React Native Assignment

A React Native project for EpiCircle's internship assignment, consisting of two separate apps:

- **Customer App** – for users to schedule scrap pickups and view their order history.
- **Partner App** – for partners to accept pickup requests, manage pickups, and track order history.

---

## ✨ Features

### Customer App
✅ User Login with OTP flow  
✅ Schedule Pickup (Date, Time, Address, Live Location)  
✅ Order History with status tracking  
✅ Dark/Light Theme toggle  
✅ Modern UI with animations

### Partner App
✅ Login with OTP flow  
✅ Dashboard with stats and theme toggle  
✅ View and accept pending pickup requests  
✅ View completed pickup history  
✅ Clean, responsive UI with brand colors

---

## 📂 Repo Structure

root/
customer-app/
partner-app/
db.json
README.md

yaml
Copy
Edit

---

## 🛠️ Prerequisites

- Node.js (recommended ≥ 16.x)
- npm
- Expo CLI:

```bash
npm install -g expo-cli
json-server:

bash
Copy
Edit
npm install -g json-server
⚡️ Quick Start Guide
1️⃣ Clone the repository
bash
Copy
Edit
git clone <your-repo-url>
cd <repo-name>
2️⃣ Install Dependencies for Both Apps
Customer App
bash
Copy
Edit
cd customer-app
npm install
Partner App
bash
Copy
Edit
cd ../partner-app
npm install
3️⃣ Setup and Start JSON Server
From the root of the repo:

bash
Copy
Edit
json-server --watch db.json --port 3000
✅ This will start the fake REST API at:

arduino
Copy
Edit
http://localhost:3000
Example endpoint:

bash
Copy
Edit
http://localhost:3000/pickups
4️⃣ Start the Customer App
In a new terminal tab:

bash
Copy
Edit
cd customer-app
npx expo start
Choose to run on Web, Android Emulator, or Expo Go on your device.

For web, you can also run:

bash
Copy
Edit
npx expo start --web
5️⃣ Start the Partner App
In another terminal tab:

bash
Copy
Edit
cd partner-app
npx expo start
✅ Similarly, choose Android, iOS, Web, or Expo Go.

🗂️ Database Structure Example
Example db.json:

json
Copy
Edit
{
  "pickups": [
    {
      "id": 1,
      "date": "2025-07-10",
      "timeSlot": "2:00 PM",
      "address": "123 Green Street",
      "status": "Pending"
    }
  ]
}
✅ Status transitions:

Customer creates → Pending

Partner accepts → In Queue

Partner completes → Pending for Approval

Customer approves → Completed

⚙️ Notes
Ensure your local IP is used in API URLs in both apps so devices on your network can connect to json-server.

If you use Expo Go, make sure your PC and phone are on the same Wi-Fi network.

For dark/light themes, both apps support toggling from their respective Dashboards.

📹 Video Walkthrough
Add your Google Drive or YouTube link here once recorded.

🤝 Contact
For questions about this project:

Mohit Kumawat

mohit.kumawat23b@iiitg.ac.in

yaml
Copy
Edit
