# 📱 Step-by-Step: Build Android APK on Expo.dev

## Complete Visual Guide to Build Your Rafiki APK

### Step 1: Login to Expo
1. Go to: **https://expo.dev**
2. Click **"Sign In"** (top right)
3. Login with your credentials (you're already logged in as **manishkumarnia**)

---

### Step 2: Navigate to Your Project
1. After login, you'll see your dashboard
2. Look for your project: **"rafiki-app"**
3. Click on **"rafiki-app"** to open it

**Direct Link:** https://expo.dev/accounts/manishkumarnia/projects/rafiki-app

---

### Step 3: Go to Builds Section
1. In your project page, look at the left sidebar
2. Click on **"Builds"** tab
   - It might also show as a tab at the top
3. You'll see your builds page (currently empty or with previous builds)

**Direct Link:** https://expo.dev/accounts/manishkumarnia/projects/rafiki-app/builds

---

### Step 4: Create New Build
1. Click the **"Create a build"** button
   - It's usually a blue/purple button
   - Located at the top right of the builds page
   - Might say "New Build" or "Create Build"

---

### Step 5: Configure Build Settings

You'll see a form with several options:

#### A. Platform Selection
- **Select:** Android
- Click on the Android icon/button

#### B. Build Profile
- **Select:** production
- From the dropdown menu, choose "production"
- (Other options might be: development, preview)

#### C. Additional Settings (Usually Auto-Filled)
- **App Version:** 1.0.0 (should be auto-filled)
- **Build Number:** 1 (should be auto-filled)
- **SDK Version:** Will be detected automatically

#### D. Credentials
When you see credentials section:
- **Select:** "Let Expo handle credentials"
- Or: "Expo managed credentials"
- This will auto-generate your Android keystore

---

### Step 6: Start the Build
1. Review your settings:
   - Platform: ✓ Android
   - Profile: ✓ production
   - Credentials: ✓ Expo managed
2. Click **"Build"** or **"Start Build"** button (usually blue)

---

### Step 7: Confirm Keystore Generation

You might see a popup or message:
- **Message:** "Generate a new Android Keystore?"
- **Action:** Click **"Yes"** or **"Generate"**

This is important - it creates the signing certificate for your app.

---

### Step 8: Build in Progress

After starting:
1. You'll see a build page with:
   - **Status:** "In Queue" or "Building"
   - **Progress bar** or spinner
   - **Build logs** (expanding as build progresses)

2. **Build phases you'll see:**
   ```
   ⏳ Queued (1-2 min)
   📦 Provisioning (2-3 min)
   🔨 Building (10-12 min)
   ✅ Completed
   ```

---

### Step 9: Monitor Build Progress

While building, you can:
- **Watch the logs** scroll by (optional)
- **Leave the page** - you'll get email notification
- **Check back** in 15-20 minutes

The page shows:
- Time elapsed
- Current phase
- Detailed logs
- Estimated time remaining

---

### Step 10: Download Your APK

When build completes:

1. **You'll see:**
   - ✅ Green checkmark
   - "Build successful" message
   - Build details

2. **Download button appears:**
   - Look for **"Download"** button
   - Or **"Download APK"**
   - Usually on the right side

3. **Click Download:**
   - APK file will download to your computer
   - File name: Something like `build-<id>.apk`
   - Size: ~25-30 MB

---

## Alternative Path (If Above UI Differs)

### Quick Build Path:
1. Go to: https://expo.dev/accounts/manishkumarnia/projects/rafiki-app
2. Find **"Builds"** section
3. Click **"+" or "New Build"**
4. Select: **Android** → **production**
5. Click **"Build"**
6. Wait 15 minutes
7. Download APK

---

## What Each Build Profile Means

| Profile | Purpose | Size | Use Case |
|---------|---------|------|----------|
| **production** | Final release | Smallest | Distribution to users |
| preview | Internal testing | Small | Team testing |
| development | Debugging | Largest | Development only |

**✅ You want: production**

---

## Build Settings Explained

### Platform: Android
- Builds APK file for Android devices
- Compatible with Android 5.0+ (API 21+)

### Profile: production
- Optimized and minified code
- Smallest file size
- Ready for distribution
- Signed with production keystore

### Credentials: Expo Managed
- Expo generates and stores your keystore
- Secure and automatic
- No manual certificate management needed

---

## Troubleshooting

### "No project found"
- Make sure you're logged in as **manishkumarnia**
- Use direct link: https://expo.dev/accounts/manishkumarnia/projects/rafiki-app

### "Build failed"
- Click on the failed build
- Check the error logs
- Common fix: Just retry the build

### "Insufficient credits"
- Free tier includes build credits
- Check: https://expo.dev/accounts/manishkumarnia/settings/billing
- You should have free credits available

### "Can't find download button"
- Wait until build shows "Completed" status
- Refresh the page
- Look for "Artifacts" section
- Download button is next to the APK artifact

---

## After Download

### Install on Android Device:

1. **Transfer APK to your phone:**
   - Via USB cable
   - Via email
   - Via cloud storage (Google Drive, Dropbox)

2. **Enable Unknown Sources:**
   - Go to: Settings → Security
   - Enable "Install from Unknown Sources"
   - Or: Settings → Apps → Special Access → Install Unknown Apps

3. **Install:**
   - Tap the APK file
   - Click "Install"
   - Wait for installation
   - Click "Open"

4. **Test:**
   - App should open
   - Show "Loading Rafiki..." spinner
   - Load your Vercel app
   - Test navigation and features

---

## Build Information to Note

Once build completes, save these details:

- **Build ID**: (shows on build page)
- **Download Link**: (valid for 30 days)
- **Build Date**: (for your records)
- **App Version**: 1.0.0
- **Build Number**: 1

---

## Next Time You Build

For future updates:

1. Increment version in `/app/frontend/app.json`
2. Go to same builds page
3. Click "Create Build"
4. Select Android → production
5. Build will reuse existing keystore (no prompt)
6. Download new APK

---

## Quick Reference URLs

| Purpose | URL |
|---------|-----|
| Project Dashboard | https://expo.dev/accounts/manishkumarnia/projects/rafiki-app |
| Builds Page | https://expo.dev/accounts/manishkumarnia/projects/rafiki-app/builds |
| Account Settings | https://expo.dev/accounts/manishkumarnia/settings |
| Build Credits | https://expo.dev/accounts/manishkumarnia/settings/billing |

---

## Visual Checklist

Before you start, verify:
- ✅ Logged in to expo.dev
- ✅ Project "rafiki-app" visible
- ✅ Can access builds section
- ✅ "Create Build" button available

During build:
- ✅ Selected Android platform
- ✅ Selected production profile
- ✅ Chose Expo managed credentials
- ✅ Clicked "Build" button
- ✅ Build is in progress

After build:
- ✅ Status shows "Completed"
- ✅ Download button visible
- ✅ APK downloaded to computer
- ✅ File size ~25-30 MB

---

## Expected Timeline

```
0:00  - Start build
0:02  - In queue
0:05  - Provisioning
0:15  - Building
0:25  - Finalizing
0:27  - Complete ✅
```

**Total: ~15-20 minutes**

---

## Need Help During Build?

If stuck at any step:
1. Take a screenshot of what you see
2. Check build logs for errors
3. Try refreshing the page
4. Contact Expo support: https://expo.dev/support

---

## Success!

When you download your APK:
🎉 **Congratulations!** 

You now have a mobile app that:
- Loads your Rafiki Vercel app
- Auto-updates when you push to GitHub
- Works on any Android device
- Ready for distribution

---

**Ready to start? Go to:** https://expo.dev/accounts/manishkumarnia/projects/rafiki-app/builds

Click "Create Build" and follow the steps above! 🚀
