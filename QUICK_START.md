# 🚀 Quick Start: Build APK and IPA

This guide will help you quickly generate APK (Android) and IPA (iOS) files for the Rafiki mobile app.

## ⚡ Super Quick Setup (5 minutes)

### Step 1: Install EAS CLI
```bash
npm install -g eas-cli
```

### Step 2: Login to Expo
```bash
eas login
```
*Don't have an account? Create one free at https://expo.dev*

### Step 3: Configure Project
```bash
cd /app/frontend
eas build:configure
```

## 📱 Build Your Apps

### Android APK (Recommended for testing)

**Development Build** (for testing):
```bash
cd /app/frontend
eas build --platform android --profile preview
```

**Production Build** (for distribution):
```bash
cd /app/frontend
eas build --platform android --profile production
```

⏱️ **Build time**: 10-20 minutes  
📥 **Result**: You'll get a download link for the APK file

### iOS IPA (Requires Apple Developer Account)

**Requirements**:
- Apple Developer Account ($99/year)
- Valid provisioning profile

**Build Command**:
```bash
cd /app/frontend
eas build --platform ios --profile production
```

⏱️ **Build time**: 15-25 minutes  
📥 **Result**: You'll get a download link for the IPA file

### Build Both Platforms at Once

```bash
cd /app/frontend
eas build --platform all --profile production
```

## 📦 What Happens During Build?

1. **Code Upload**: Your app code is uploaded to Expo servers
2. **Native Build**: Expo builds native Android/iOS apps
3. **App Generation**: APK/IPA files are generated
4. **Download Link**: You receive a link to download your app

## 💾 Download Your Apps

After the build completes:

1. Check your terminal for the download URL
2. Or visit https://expo.dev/accounts/[your-username]/projects/rafiki-app/builds
3. Download the APK/IPA file
4. Distribute to users!

## 📲 Installing the Apps

### Android APK
1. Download APK to Android device
2. Enable "Install from Unknown Sources" in Settings
3. Tap the APK file to install
4. Open Rafiki app

### iOS IPA
1. Upload to App Store Connect
2. Distribute via TestFlight (beta) or App Store (production)

## 🔄 How Auto-Updates Work

**The beauty of this approach:**

```
Your GitHub → Vercel → Mobile App Updates
```

1. Push code to GitHub
2. Vercel auto-deploys your changes
3. Mobile app shows new content immediately
4. **No new APK/IPA needed!**

## ⚙️ Build Profiles Explained

We have 4 build profiles in `/app/eas.json`:

| Profile | Platform | Use Case | Output |
|---------|----------|----------|--------|
| `development` | Both | Testing | APK with debugging |
| `preview` | Both | Internal testing | APK (smaller) |
| `production` | Both | Public release | APK (optimized) |
| `production-aab` | Android | Play Store | AAB file |

## 🎯 Choose the Right Build

- **First time building?** → Use `preview` profile
- **Testing internally?** → Use `preview` profile  
- **Releasing to public?** → Use `production` profile
- **Publishing to Play Store?** → Use `production-aab` profile

## 💡 Pro Tips

### 1. Check Build Status
```bash
eas build:list
```

### 2. View Build Logs
```bash
eas build:view [build-id]
```

### 3. Cancel a Build
```bash
eas build:cancel
```

### 4. Submit to App Stores
```bash
# Android
eas submit --platform android

# iOS
eas submit --platform ios
```

## ⚠️ Common Issues

### Issue: "Not logged in"
**Solution**:
```bash
eas whoami
eas login
```

### Issue: "Build failed"
**Solution**: Check build logs in Expo dashboard

### Issue: "No build credits"
**Solution**: Expo provides free credits. Upgrade plan if needed.

### Issue: "iOS build requires Apple Developer account"
**Solution**: 
- Purchase Apple Developer membership ($99/year)
- Or build Android only for now

## 🔐 iOS Specific Setup

### Required for iOS:
1. **Apple Developer Account**: https://developer.apple.com
2. **Bundle Identifier**: Already set as `com.rafiki.app`
3. **Provisioning Profile**: EAS will help generate

### First iOS Build:
```bash
cd /app/frontend
eas build --platform ios --profile production
```

EAS will guide you through certificate creation.

## 📊 Build Size Estimates

- **Android APK**: ~25-30 MB
- **iOS IPA**: ~30-35 MB

## 🎉 Success Checklist

After your first successful build:

- ✅ Received download link from EAS
- ✅ Downloaded APK/IPA file
- ✅ Installed on test device
- ✅ App opens and shows Rafiki from Vercel
- ✅ Can navigate through the app
- ✅ Pull to refresh works
- ✅ Back button works (Android)

## 🆘 Need Help?

- **Build Issues**: https://forums.expo.dev
- **Expo Documentation**: https://docs.expo.dev/build/introduction/
- **WebView Issues**: https://github.com/react-native-webview/react-native-webview/issues

## 📞 Quick Commands Reference

```bash
# Login
eas login

# Build Android
eas build -p android --profile production

# Build iOS  
eas build -p ios --profile production

# Build Both
eas build --platform all

# Check status
eas build:list

# Submit to stores
eas submit -p android
eas submit -p ios
```

## 🎨 Customization Before Building

Want to customize before building?

1. **Change app name**: Edit `/app/frontend/app.json`
2. **Change URL**: Edit `/app/frontend/app/index.tsx`
3. **Change icon**: Replace `/app/frontend/assets/images/icon.png`
4. **Change colors**: Edit styles in `/app/frontend/app/index.tsx`

## 🚀 Next Steps

After getting your APK/IPA:

1. **Test thoroughly** on real devices
2. **Share APK** with test users (Android)
3. **Upload to TestFlight** (iOS)
4. **Submit to app stores** when ready
5. **Update your Vercel app** - mobile app updates automatically!

---

**Ready to build? Run this now:**

```bash
cd /app/frontend && eas build -p android --profile production
```

Good luck! 🎉
