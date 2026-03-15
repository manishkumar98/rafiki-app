# 🦁 Rafiki Mobile App

A mobile wrapper for the Rafiki Migration Success Agent platform. This app provides a native mobile experience for https://rafiki-nine.vercel.app/ with automatic content updates.

## ✨ What Makes This Special

### Auto-Update Feature
**When you push to GitHub → Vercel deploys → Mobile app updates automatically!**

No need to rebuild or redistribute the app for content changes. Users always see the latest version of your web app.

## 📱 Features

- ✅ **WebView Wrapper**: Loads your Vercel app in a native container
- ✅ **Auto-Updates**: Content updates instantly without app store approval
- ✅ **Loading States**: Beautiful loading spinner while content loads
- ✅ **Error Handling**: Graceful offline detection and retry functionality
- ✅ **Pull to Refresh**: Swipe down to reload content
- ✅ **Native Navigation**: Back button support (Android) and gesture navigation (iOS)
- ✅ **Cross-Platform**: Single codebase for iOS and Android
- ✅ **Optimized Performance**: Efficient caching and state management

## 🏗️ Technical Stack

- **Framework**: Expo (React Native)
- **WebView**: react-native-webview
- **Source**: https://rafiki-nine.vercel.app/
- **Build System**: EAS Build

## 🚀 Quick Start

### For Users (Installing the App)

1. **Android**: Download and install the APK file
2. **iOS**: Install via TestFlight or App Store

### For Developers (Building the App)

#### Prerequisites
```bash
# Install EAS CLI
npm install -g eas-cli

# Login to Expo
eas login
```

#### Build APK (Android)
```bash
cd /app/frontend
eas build --platform android --profile production
```

#### Build IPA (iOS)  
```bash
cd /app/frontend
eas build --platform ios --profile production
```

**Note**: iOS builds require an Apple Developer account ($99/year)

## 🔄 How Auto-Updates Work

### The Magic Flow:
1. You make changes to your website code
2. Push to GitHub
3. Vercel automatically deploys your changes
4. Mobile app users see updates **immediately** on next launch
5. **No app store approval needed!**

### When You DO Need to Rebuild:
- Changing app name or icon
- Modifying permissions
- Adding native features (camera, GPS, etc.)
- Updating app version number

## 📲 Testing the App

### Test on Web (Limited WebView support)
```bash
cd /app/frontend
yarn start
```
Open https://rafiki-mobile-auto.preview.emergentagent.com in your browser

### Test on Physical Device (Recommended)
```bash
# Build development version
eas build --platform android --profile development

# Install the APK on your device
```

### Test with Expo Go (Quick but limited)
```bash
cd /app/frontend
yarn start
# Scan QR code with Expo Go app
```

## 🎨 Customization

### Change URL
Edit `/app/frontend/app/index.tsx`:
```typescript
const RAFIKI_URL = 'https://your-app.vercel.app/';
```

### Update App Info
Edit `/app/frontend/app.json`:
```json
{
  "expo": {
    "name": "Your App Name",
    "slug": "your-app-slug",
    "version": "1.0.0"
  }
}
```

### Change App Icon
Replace `/app/frontend/assets/images/icon.png` (1024x1024px)

### Change Splash Screen
Replace `/app/frontend/assets/images/splash-icon.png`

## 📦 Distribution

### Android
- **APK**: Direct distribution (share file directly)
- **AAB**: Google Play Store (use `production-aab` profile)

### iOS
- **IPA**: TestFlight → App Store

## 🔧 Troubleshooting

### App Not Loading
- Check internet connection
- Verify Vercel app is accessible at https://rafiki-nine.vercel.app/
- Try force closing and reopening the app
- Clear app data (Settings → Apps → Rafiki → Clear Data)

### Build Fails
```bash
# Check login status
eas whoami

# Verify configuration
cd /app/frontend
eas build:configure
```

### Content Not Updating
- Verify Vercel deployment succeeded
- Check if URL changed
- Force close and reopen app
- Pull down to refresh

## 📊 App Specifications

- **Minimum Android Version**: 5.0 (API 21)
- **Minimum iOS Version**: 13.0
- **App Size**: ~25-30 MB (varies by platform)
- **Permissions Required**: Internet access
- **Offline Mode**: Shows error message with retry option

## 🌐 URLs

- **Vercel App**: https://rafiki-nine.vercel.app/
- **GitHub Repo**: https://github.com/manishkumar98/Rafiki
- **Preview (Web)**: https://rafiki-mobile-auto.preview.emergentagent.com

## 📚 Documentation

- [Complete Build Instructions](./BUILD_INSTRUCTIONS.md) - Detailed step-by-step guide
- [EAS Build Docs](https://docs.expo.dev/build/introduction/)
- [React Native WebView](https://github.com/react-native-webview/react-native-webview)
- [Expo Documentation](https://docs.expo.dev/)

## 🎯 Project Structure

```
/app
├── frontend/
│   ├── app/
│   │   └── index.tsx          # Main WebView screen
│   ├── assets/
│   │   └── images/            # App icons and splash screens
│   ├── app.json               # Expo configuration
│   └── package.json           # Dependencies
├── eas.json                   # Build profiles
└── BUILD_INSTRUCTIONS.md      # Detailed build guide
```

## 🤝 Support

### Getting Help
- **Build Issues**: Check [Expo Forums](https://forums.expo.dev)
- **WebView Issues**: Check [react-native-webview GitHub](https://github.com/react-native-webview/react-native-webview/issues)
- **Vercel Deployment**: Check [Vercel Docs](https://vercel.com/docs)

### Common Questions

**Q: Do users need to download updates?**
A: No! Content updates automatically. Only native feature changes require new app versions.

**Q: Can I use this for any website?**
A: Yes! Just change the URL in `index.tsx`.

**Q: How much does it cost to build?**
A: Expo provides free build credits. iOS distribution requires Apple Developer account ($99/year).

**Q: Does this work offline?**
A: The app detects offline status and shows a retry button. You could enhance it with offline caching.

## 💡 Tips

1. **Test thoroughly** on real devices before distributing
2. **Version your builds** properly for tracking
3. **Use production profiles** for distribution
4. **Monitor Vercel deployments** to ensure they succeed
5. **Consider analytics** to track user engagement

## 🎉 Success Metrics

Once your app is live:
- ✅ Users can access Rafiki on mobile devices
- ✅ Content updates deploy automatically via Vercel
- ✅ No app store approval needed for content changes
- ✅ Native mobile experience with proper navigation
- ✅ Offline detection and error handling

---

**Built for migrant workers with ❤️**

*Empowering migration through technology*
