# 🎓 Farewell Organizer Committee Website

A stunning, interactive farewell website designed for the Class of 2026 (Xaverians). This project features a cinematic entrance, an interactive memory wall, and a countdown to the big day.

![Farewell Preview](invitation.jpg)

## ✨ Features

### 1. 🎬 Cinematic Entrance
- **Welcome Page**: Plays a background video with a "Enter Experience" button.
- **Login System**: A "Memory Lock" that requires a name and secret code (`lencho`) to access.
- **Smooth Transitions**: Video-based transitions between sections for a premium feel.

### 2. 🏠 Main Dashboard
- **Countdown Timer**: Ticks down to the event date (10 Jan 2026).
- **Invitation Card**: Digital invitation with venue details and a "View Location" button.
- **Audio Experience**: Background music that fades in/out smoothly.
- **Confetti Effect**: Celebratory animation upon entry.

### 3. 📸 Memory Wall (New!)
- **Upload Memories**: Users can upload photos + captions directly to the wall.
- **No Database Required**: Uses **Cloudinary** for storage and smart persistence.
- **Dark Aesthetic**: Matches the site's dark theme with glassmorphism and animated backgrounds.
- **Instant Updates**: New uploads appear immediately for everyone (after configuring Cloudinary).

---

## 🛠️ Tech Stack
- **Frontend**: HTML5, CSS3 (Vanilla), JavaScript (ES6+)
- **Storage**: [Cloudinary](https://cloudinary.com/) (Image hosting & JSON List API)
- **Styling**: Custom CSS with Animations, Flexbox, Grid, and Glassmorphism.

---

## 🚀 How to Run

1.  **Clone or Download** this repository.
2.  Open the `index.html` file in any modern web browser.
3.  **Login Credentials**:
    *   **Username**: `shivam`, `ayush mehta`, `pranjal`, `shreyansh`, `kunj`, or `sahil` (case-insensitive).
    *   **Password/Code**: `lencho`

---

## ☁️ Cloudinary Configuration (Crucial!)

The **Memory Wall** relies on Cloudinary's "Resource List" feature to fetch and display photos without a backend server.

### 1. Credentials in `memory_wall.html`
Ensure your `CLOUD_NAME` and `UPLOAD_PRESET` are set in the script section of `memory_wall.html`.
```javascript
const CLOUD_NAME = 'dj8igz7kg'; 
const UPLOAD_PRESET = 'Upload'; 
```

### 2. ⚠️ Enable "Resource List" (Required)
For the wall to show images to other users, you **MUST** enable this setting in your Cloudinary Dashboard:

1.  Go to **Settings (Gear Icon)** > **Security**.
2.  Scroll to **Restricted media types**.
3.  **UNCHECK** the box for **"Resource list"**.
4.  Click **Save**.

*If this is checked (default), the website cannot fetch the list of memories, and users will only see their own uploads temporarily.*

---

## 📂 Project Structure

- **`index.html`**: The main entry point (Welcome, Login, Main Page).
- **`memory_wall.html`**: The photo gallery and upload page.
- **`2.0.html`**: (Legacy/Alternative version).
- **`video1.mp4` - `video4.mp4`**: Background assets for transitions.
- **`music1.mp3`**: Background ambient music.

---

## 📝 How the Memory Wall Works

1.  **Upload**: When a user uploads a photo, the JS creates a custom `public_id` containing their **Name** and **Caption** (encoded in Base64).
2.  **Tagging**: The image is tagged with `farewell_memory_v1`.
3.  **Fetching**: The page fetches `list/farewell_memory_v1.json` from Cloudinary.
4.  **Decoding**: The script decodes the Name/Caption from the filename and builds the gallery grid dynamically.

---

Made with ❤️ by the **Farewell Organizing Committee**.
