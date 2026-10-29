<div align="center">
  <img width="500" height="500" alt="logo" src="https://github.com/user-attachments/assets/40e65fa8-1d9d-423c-802d-cd23a67f56c3" />

  <h1>FETCHY! 🍔</h1>
  <p><b>An anonymous, encrypted, and incredibly beautiful messenger right in your browser.</b></p>

  <img src="https://img.shields.io/badge/version-1.0.0-blue?style=for-the-badge" alt="Version" />
  <img src="https://img.shields.io/badge/status-active-success?style=for-the-badge" alt="Status" />
  <img src="https://img.shields.io/badge/Firebase-FFCA28?style=for-the-badge&logo=firebase&logoColor=white" alt="Firebase" />
  <img src="https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black" alt="JavaScript" />
</div>

---

## 📖 About the Project and Concept

**FETCHY!** is an experiment in the world of anonymous communication. We are tired of messengers that require a phone number, collect metadata, and read your chats. 

**The Concept:** Create an application where every user can deploy their own "server" (Firebase database) and invite friends there without registering anywhere. All messages are encrypted on the sender's device (AES-GCM + PBKDF2) and decrypted only on the recipient's device. Even Firebase sees nothing but a jumble of random characters.

The application runs entirely on the client side. Download the file, open it in a browser — and you are online.

> [!CAUTION]
> **⚠️ Neural Network Disclaimer**
> Neural networks were actively used during the development of the interface, architecture, and code of this application. The code may contain suboptimal solutions or hidden bugs. Use at your own risk.

> [!WARNING]
> **⚠️ About Potential Bugs**
> This is an Open-Source project by enthusiasts, not a commercial product. The app may contain visual bugs, sync issues under poor internet conditions, or version conflicts. If you find an error, please open an Issue in the repository.

---

## ✨ Features

- 🔒 **End-to-End Encryption** — passwords are not written to the database; a key is derived from them instead.
- 🛡️ **Anonymous Authentication** — database access is restricted exclusively through the app (Firebase Auth).
- 🎨 **12 Themes and 2 Designs** (NeoBrutalism / Minimalistic) + light/dark mode.
- 🅰️ **10 Fonts** with customizable size and italic options.
- 🖼️ **Photo Sharing** with built-in compression and encryption.
- 📁 **File and Video Sharing** via Google Drive.
- 🗑️ **Bulk Selection** and deletion, chat clearing (owner only).
- 🎵 **Interface Sounds** with in-browser synthesis (no external files required).
- 📱 **Responsive Layout** + manual panel resizing on PC.
- 🥚 **Easter Eggs** (try typing `burger` in the secret menu).

---

## 📸 Screenshots


<p align="center">
  <img width="1852" height="992" alt="image" src="https://github.com/user-attachments/assets/4d18dafb-4bec-4bd5-8101-094ef3d5b78a" />

</p>
<p align="center">
  <i>Main Screen + Chat</i>
</p>

<br>

<p align="center">
  <img width="1856" height="992" alt="image" src="https://github.com/user-attachments/assets/afc7aab4-d99e-4102-82e5-4c24dc50bb4a" />

</p>
<p align="center">
  <i>Settings</i>
</p>

---

## 🚀 Quick Start

1. Download the HTML file from this repository.
2. Open it in any modern browser (Chrome, Firefox, Safari).
3. Create a chat by following the instructions below.

---

## 🛠 Firebase Setup Guide

To get the chat working, you need your own database. It's free.

### Step 1. Creating a Project
1. Go to the Firebase Console.
2. Click "Add project", enter a name, and create it.

### Step 2. Enabling Anonymous Authentication
1. Select **Authentication** from the left menu.
2. Click **Get Started**.
3. Go to the **Sign-in method** tab.
4. Find **Anonymous**, toggle the switch to **Enable**, and save.

### Step 3. Creating a Realtime Database
1. Select **Realtime Database** from the left menu.
2. Click **Create Database**.
3. Choose a location and click **Next**.
4. Select **Start in test mode** and click **Enable**.

### Step 4. Configuring Security Rules
> [!CAUTION]
> This is a critical step. If you skip it, anyone with the link will be able to read your messages.

1. Go to the **Rules** tab in your Realtime Database.
2. Delete everything there and paste the following code:

{"rules": { "fetchok_chats": { "$chatId": { ".read": "auth != null", ".write": "auth != null" } } }}

3. Click the **Publish** button.

### Step 5. Getting the Keys
1. Click the **gear icon** ⚙️ next to "Project Overview" -> **Project settings**.
2. Scroll down to the **Your apps** section.
3. If there is no web app, click the `</>` icon, enter a name, and register it.
4. Copy two lines from the `const firebaseConfig` block:
   - **`apiKey`** (starts with `AIzaSy...`)
   - **`databaseURL`** (starts with `https://...firebaseio.com`)

### Step 6. Creating a Chat
1. Click "+" inside the application.
2. Enter a name, a password (remember it!), the **API Key**, and the **Database URL**.
3. Click "Create". The application will generate a 10-digit chat code.

Share the **code, password, API Key, and Database URL** with your friend so they can connect to you.

---

## 🧠 Technologies

- **Frontend:** Vanilla JavaScript (ES6+), HTML5, CSS3.
- **Database:** Firebase Realtime Database.
- **Authentication:** Firebase Auth (Anonymous).
- **Encryption:** Web Crypto API (AES-GCM, PBKDF2).

---

## ⚠️ Security

Please remember that the application uses **local encryption**. This means:
- No one (not even Google) can read your messages without the password.
- If you forget the chat password, the chat history **cannot** be recovered.

---

<div align="center">
  <p>Made with 🍔 and a love for anonymity.</p>
  <p>2026 © FETCHY! Project</p>
</div>

