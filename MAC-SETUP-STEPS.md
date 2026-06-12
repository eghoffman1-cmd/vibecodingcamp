# How to Submit Be Anything to the App Store
## Complete step-by-step guide for when you have Mac access

---

## BEFORE YOU START — Get These Ready
- [ ] Apple Developer account ($99/yr) → developer.apple.com
- [ ] Mac access (your own Mac or cloud Mac at macincloud.com)
- [ ] App icon: 1024×1024 PNG file (see appstore-metadata.md)
- [ ] Screenshots (see appstore-metadata.md)

---

## STEP 1 — Install tools on the Mac

Open Terminal and run these one at a time:

```bash
# Install Homebrew (Mac package manager)
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

# Install Node.js
brew install node

# Install Xcode from the App Store (free, ~7GB, takes 20 min)
# Just search "Xcode" in the Mac App Store and install it
```

---

## STEP 2 — Clone the game repo

```bash
git clone https://github.com/eghoffman1-cmd/vibecodingcamp.git
cd vibecodingcamp
```

---

## STEP 3 — Set up the web folder

```bash
mkdir www
cp index.html www/index.html
cp privacy-policy.html www/privacy-policy.html
```

---

## STEP 4 — Install Capacitor

```bash
npm install
npx cap add ios
npx cap sync
```

---

## STEP 5 — Open in Xcode

```bash
npx cap open ios
```

Xcode will open. Now in Xcode:

1. Click the project name in the left panel (should say "App")
2. Under "Signing & Capabilities":
   - Check "Automatically manage signing"
   - Select your Apple Developer Team
   - Change Bundle Identifier to: `com.beanything.game`
3. Set Display Name to: `Be Anything`
4. Set Version: `1.0.0`
5. Set Build: `1`

---

## STEP 6 — Add the App Icon

1. In Xcode left panel → App → Assets.xcassets → AppIcon
2. Drag your 1024×1024 PNG into the "App Store" slot
3. Xcode fills in all other sizes automatically

---

## STEP 7 — Test on a simulator

1. At top of Xcode, select "iPhone 15 Pro" from the device dropdown
2. Press the ▶ Play button
3. The game should open in the simulator — test it works

---

## STEP 8 — Archive for App Store

1. Top menu: **Product → Archive**
2. Wait for the build (2–5 minutes)
3. When done, the Organizer window opens
4. Click **"Distribute App"**
5. Choose **"App Store Connect"** → Next
6. Choose **"Upload"** → Next → Next → Upload

---

## STEP 9 — App Store Connect

Go to appstoreconnect.apple.com:

1. Click **"My Apps"** → **"+"** → **"New App"**
2. Fill in:
   - Name: `Be Anything`
   - Bundle ID: `com.beanything.game`
   - SKU: `beanything001`
3. Under **"App Information"**: paste description, keywords from `appstore-metadata.md`
4. Under **"Pricing"**: Free
5. Under **"App Privacy"**: No data collected
6. Upload screenshots
7. Select your build (the one you uploaded from Xcode)
8. Click **"Submit for Review"**

---

## STEP 10 — Wait

Apple reviews take **1–3 business days**.
You'll get an email when approved or if they need changes.

---

## You're done! 🎉
The game will go live on the App Store within 24 hours of approval.
