# Village Intelligence Network (VIN) 🛡️

A centralized Public Data Portal designed for comprehensive data collection, citizen registration, and local record management. This platform acts as a secure hub connecting the public to standard forms, while providing a secure login gateway for authorized administrators to access backend data and restricted administrative functions.

## ✨ Features

* **🌍 Public-First Access:** Standard portal views and form links are accessible to the public by default, improving community engagement and ease of reporting.
* **🔐 Secure Admin Gateway:** Firebase-powered email and password authentication to protect administrative functions (such as editing forms or viewing backend data sheets).
* **🛡️ Role-Based Access Control (RBAC):** Distinct UI states for public users and Administrators. Admins receive exclusive action buttons seamlessly integrated into the dashboard upon login.
* **🌗 Persistent Theme Engine:** Built-in Dark and Light mode toggle. User preferences are automatically saved in the browser's local storage.
* **🔍 Instant Search & Filtering:** Live search functionality to instantly filter through various intelligence and data forms.
* **📑 Categorized Intelligence Hub:** Forms are visually categorized into Standard, Monitored, and Restricted (Alert) items for quick situational awareness.
* **📱 Fully Responsive UI:** Modern, animated, grid-based design optimized for desktops, tablets, and mobile devices.

## 🏗️ Architecture & Tech Stack

* **Frontend:** Pure HTML5, CSS3 (Custom Properties & Animations), and Vanilla JavaScript (ES6 Modules).
* **Backend & Auth:** Firebase v10 (Authentication & Realtime Database).
* **Data Collection:** Google Forms & Google Sheets API integrations.
* **Typography & Icons:** Google Fonts (Rajdhani, DM Sans, Share Tech Mono) & FontAwesome 6.

## 🚀 Getting Started

### Prerequisites

To run this project, you only need a modern web browser and a local development server (like VS Code Live Server).

### Installation

1. **Clone the repository:**
   ```bash
   git clone [https://github.com/lovnishverma/Village-Intelligence-Network.git](https://github.com/lovnishverma/Village-Intelligence-Network.git)
   ```

2. **Navigate to the project directory:**
   ```bash
   cd Village-Intelligence-Network
   ```

3. **Open the project:**
   Open `index.html` via a local web server (e.g., using the "Live Server" extension in VS Code) to prevent CORS issues with ES6 modules.

## ⚙️ Firebase Configuration

By default, the application uses a pre-configured Firebase project. If you wish to use your own Firebase backend:

1. Go to the Firebase Console.
2. Create a new project and enable **Authentication (Email/Password)** and the **Realtime Database**.
3. Register a Web App and copy your Firebase config object.
4. Open `index.html` and replace the `firebaseConfig` object inside the `<script type="module">` tag:

```javascript
const firebaseConfig = {
    apiKey: "YOUR_API_KEY",
    authDomain: "YOUR_PROJECT_ID.firebaseapp.com",
    databaseURL: "https://YOUR_PROJECT_ID-default-rtdb.firebaseio.com",
    projectId: "YOUR_PROJECT_ID",
    storageBucket: "YOUR_PROJECT_ID.firebasestorage.app",
    messagingSenderId: "YOUR_SENDER_ID",
    appId: "YOUR_APP_ID"
};
```

## 👑 Setting up an Admin User

To grant a user Admin privileges (which allows them to access the protected login screen and see the "Edit Form" and "View Sheet" buttons):

1. Ensure the user has signed up/logged in at least once via Firebase Auth.
2. Go to your Firebase Realtime Database.
3. Create a node structure like this, replacing `USER_UID` with the actual Firebase User ID string:

```json
{
  "users": {
    "USER_UID": {
      "role": "admin"
    }
  }
}
```

## 📂 Forms Included

The portal integrates over 15+ specialized forms, including:

* **Standard:** Demographics, Village Infrastructure, Business Hubs, Trade Persons, Vehicle Tracking.
* **Monitored:** Personnel near International Border (IB) Fences.
* **Alert/Restricted:** Suspicious Persons, Criminal Records, Suspected Hideouts.

## 🤝 Contributing

Contributions, issues, and feature requests are welcome! 
Feel free to check the issues page if you want to contribute.

1. Fork the Project
2. Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3. Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the Branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request
