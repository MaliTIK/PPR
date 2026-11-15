# P.P.R. Website with Live Admin Panel

This version lets you update texts, contacts, services and the showroom **directly from the website**.

## 1. Create a free Firebase project (5 minutes)

1. Go to [https://console.firebase.google.com](https://console.firebase.google.com)
2. Click **Add project** → name it `ppr-pavimenti` (or anything) → continue
3. Disable Google Analytics if asked → Create project
4. Once ready, click the **Web** icon (`</>`) to add a web app
5. Register app (nickname: `ppr-web`) → copy the `firebaseConfig` object

## 2. Enable the services

In the Firebase console:

- **Authentication** → Get started → Sign-in method → **Email/Password** → Enable
- **Firestore Database** → Create database → Start in **test mode** (for now) → choose a region close to you
- **Storage** → Get started → Start in **test mode**

## 3. Create your admin user

- Authentication → Users → **Add user**
- Enter your email and a password (this is what you will use to log into the admin page)

## 4. Put the config in the files

Open `admin.html` and `index.html` and replace the placeholder:

```js
const firebaseConfig = {
  apiKey: "YOUR_API_KEY",
  authDomain: "YOUR_PROJECT.firebaseapp.com",
  projectId: "YOUR_PROJECT",
  storageBucket: "YOUR_PROJECT.appspot.com",
  messagingSenderId: "123456789",
  appId: "1:123456789:web:abcdef"
};
```

with the real values from step 1.

## 5. Upload to hosting

Upload these files to your hosting (GitHub Pages, Netlify, Vercel, or any static host):

- `index.html`
- `admin.html`
- `logo.jpg` / `logo.png` (optional)
- the `showroom/` folder (initial photos)

## 6. Use the admin panel

Go to `https://yourdomain.com/admin.html`

- Log in with the email/password you created
- Edit company info, about text, services
- Add or remove photos from the showroom (uploads go to Firebase Storage)
- Click **Save** — the public site updates immediately

---

**Security note (later):** After testing, change the Firestore and Storage rules from “test mode” to more secure rules that only allow writes when the user is authenticated. I can give you the exact rules when you are ready.
