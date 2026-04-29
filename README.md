# StepCrew — Deployment Guide 👟

## What you'll need
- A free **Firebase** account (for real-time data sync)
- A free **Netlify** account (for hosting)
- About 15 minutes

---

## STEP 1 — Create a Firebase project (free database)

1. Go to **https://console.firebase.google.com**
2. Click **"Add project"**, name it `stepcrew`, click through the steps
3. Once created, click **"Firestore Database"** in the left menu
4. Click **"Create database"** → choose **"Start in test mode"** → pick any location → click **Enable**
5. Now go back to **Project Overview** (home icon, top left)
6. Click the **"</>"** web icon to add a web app
7. Give it a nickname like `stepcrew-web`, click **Register app**
8. You'll see a block of code like this — **copy these 6 values**:

```
apiKey: "AIza..."
authDomain: "stepcrew-xxx.firebaseapp.com"
projectId: "stepcrew-xxx"
storageBucket: "stepcrew-xxx.appspot.com"
messagingSenderId: "123456..."
appId: "1:123..."
```

---

## STEP 2 — Add your Firebase config to index.html

1. Open **index.html** in any text editor (Notepad, TextEdit, VS Code)
2. Find this section near the top:

```javascript
const firebaseConfig = {
  apiKey: "PASTE_YOUR_API_KEY_HERE",
  authDomain: "PASTE_YOUR_AUTH_DOMAIN_HERE",
  projectId: "PASTE_YOUR_PROJECT_ID_HERE",
  storageBucket: "PASTE_YOUR_STORAGE_BUCKET_HERE",
  messagingSenderId: "PASTE_YOUR_SENDER_ID_HERE",
  appId: "PASTE_YOUR_APP_ID_HERE"
};
```

3. Replace each `PASTE_YOUR_..._HERE` with the values you copied in Step 1
4. Save the file

---

## STEP 3 — Deploy to Netlify (free hosting)

1. Go to **https://app.netlify.com** and sign up (free)
2. From the dashboard, find the **"Deploy manually"** section
3. Drag and drop your **stepcrew folder** onto the page
4. Netlify will give you a URL like `https://amazing-name-123.netlify.app`
5. That's your app! Share this link with your whole family 🎉

### Optional: Give it a custom name
- In Netlify dashboard → Site settings → Change site name
- e.g. `familysteps.netlify.app`

---

## STEP 4 — Share with your family

Send everyone your Netlify URL. When they open it on their phone:
- **iPhone**: tap the Share button → "Add to Home Screen" → it installs like an app
- **Android**: tap the browser menu → "Add to Home Screen" or "Install app"

They each set up their own profile and join your crew with the code you share.

---

## How the crew sync works

| User type | How it works |
|-----------|-------------|
| **New Crew** | First person creates the crew and gets a 6-character code |
| **Join Crew** | Everyone else enters that code to sync |
| **Manual users** | Log steps anytime, tap Share to push to the crew |
| **Moderator** | Crew creator — can set daily/weekly goals for everyone |

---

## Troubleshooting

**"Crew not found" when joining**
→ Check you copied the Firebase config correctly in Step 2

**Data not syncing**
→ Make sure Firestore is in "test mode" (Step 1, point 4)
→ Test mode expires after 30 days — go back to Firebase console and extend rules if needed

**Firestore rules expiring (after 30 days)**
→ Go to Firebase Console → Firestore → Rules → change the date or set:
```
allow read, write: if true;
```

---

## Questions?
Come back to this Claude chat and ask — all the code lives here.
