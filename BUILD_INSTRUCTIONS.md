# Rafiki Mobile App - Build Instructions

This is a WebView wrapper app for the Rafiki Migration Success Agent platform. The app loads https://rafiki-nine.vercel.app/ and automatically reflects any updates you make to the Vercel deployment.

## 🎯 Key Features

- **Auto-Updates**: Content updates from Vercel instantly without rebuilding
- **Native Feel**: Loading states, error handling, pull-to-refresh
- **Cross-Platform**: Works on both iOS and Android
- **Offline Handling**: Graceful error messages when offline
- **Navigation**: Back button support for Android, gesture navigation for iOS

## 📱 Building APK and IPA Files

### Prerequisites

1. **Install EAS CLI globally:**
   ```bash
   npm install -g eas-cli
   ```

2. **Login to Expo:**
   ```bash
   eas login
   ```
   (Create a free account at https://expo.dev if you don't have one)

3. **Configure the project:**
   ```bash
   cd /app/frontend
   eas build:configure
   ```

### Building Android APK

**For Development/Testing:**
```bash
cd /app/frontend
eas build --platform android --profile preview
```

**For Production:**
```bash
cd /app/frontend
eas build --platform android --profile production
```

The build will take 10-20 minutes. Once complete, you'll get a download link for the APK file.

### Building iOS IPA

**Requirements:**
- Apple Developer Account ($99/year)
- Proper provisioning profiles and certificates

**For Development:**
```bash
cd /app/frontend
eas build --platform ios --profile development
```

**For Production:**
```bash
cd /app/frontend
eas build --platform ios --profile production
```

### Building Both Platforms

```bash
cd /app/frontend
eas build --platform all --profile production
```

## 🔄 Update Strategy

### Content Updates (No Rebuild Needed)
When you push changes to your GitHub repo that update the Vercel app:
1. Your changes deploy to Vercel automatically
2. Mobile app users see the updates immediately on next launch
3. No new APK/IPA needed

### Native Feature Updates (Rebuild Required)
Only rebuild the app when you need to:
- Change app name, icon, or splash screen
- Modify native permissions
- Update app version
- Add new native functionality

## 📲 Testing the App

### Option 1: Expo Go (Quick Testing)
```bash
cd /app/frontend
npm start
```
Scan the QR code with Expo Go app.

**Note:** WebView may have limitations in Expo Go. For full testing, use development builds.

### Option 2: Development Build (Recommended)
```bash
eas build --platform android --profile development
```
Install the generated APK on your device for full native testing.

## 🎨 Customization

### Change the Loaded URL
Edit `/app/frontend/app/index.tsx`:
```typescript
const RAFIKI_URL = 'https://your-new-url.vercel.app/';
```

### Update App Name
Edit `/app/frontend/app.json`:
```json
{
  "expo": {
    "name": "Your App Name",
    "slug": "your-app-slug"
  }
}
```

### Change App Icon
Replace these files in `/app/frontend/assets/images/`:
- `icon.png` (1024x1024px)
- `adaptive-icon.png` (1024x1024px for Android)
- `splash-icon.png` (splash screen logo)

## 🚀 Distribution

### Android
1. **Direct Distribution**: Share the APK file directly with users
2. **Google Play Store**: Use the `production-aab` profile for Play Store submission
   ```bash
   eas build --platform android --profile production-aab
   ```

### iOS
1. **TestFlight**: Upload IPA to App Store Connect for beta testing
2. **App Store**: Submit for review after testing

## 🔧 Troubleshooting

### Build Fails
- Ensure you're logged in: `eas whoami`
- Check your Expo account has build credits
- Verify app.json configuration is valid

### WebView Not Loading
- Check internet connection
- Verify the URL is accessible
- Check if Vercel app is deployed and running

### App Updates Not Showing
- Force close and reopen the app
- Check if Vercel deployment succeeded
- Verify the URL hasn't changed

## 📚 Additional Resources

- [EAS Build Documentation](https://docs.expo.dev/build/introduction/)
- [React Native WebView](https://github.com/react-native-webview/react-native-webview)
- [Expo App Store Deployment](https://docs.expo.dev/distribution/introduction/)

## 🤝 Support

For issues or questions:
1. Check the Expo forums: https://forums.expo.dev
2. React Native WebView issues: https://github.com/react-native-webview/react-native-webview/issues
3. Vercel deployment: https://vercel.com/docs

---

**Built with ❤️ for migrant workers**
