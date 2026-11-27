# Rajasthan Solar Guide — शुरुआती वास्तविक प्रोजेक्ट

यह एक शुरुआती source-code package है: responsive वेबसाइट (React + Vite), Flutter मोबाइल ऐप का starter, और Firebase security/database configuration.

## कंपनी सेटिंग
- नाम: Rajasthan Solar Guide
- संपर्क: 8769115218
- ईमेल: surgyanmeena145@gmail.com
- सुझाया गया डोमेन: rajasthansolarguide.in (उपलब्धता/रजिस्ट्रेशन अभी सत्यापित नहीं)

## जरूरी बातें
1. यह source code है, अभी प्रकाशित वेबसाइट या Play Store ऐप नहीं।
2. Firebase project आपको अपने Google खाते से बनाना होगा।
3. Firebase config को `web/src/firebase.js` में भरें।
4. पहले Firebase Authentication में Email/Password चालू करें और अपना admin user बनाएं।
5. Firestore Rules को deploy करने से पहले Firebase UID को `firebase/firestore.rules` में `YOUR_ADMIN_UID` की जगह डालें।
6. कभी भी Gmail पासवर्ड, OTP, service-account private key या Firebase Admin SDK secret वेबसाइट में न डालें।
7. Subsidy की राशि/पात्रता समय के साथ बदलती है। लॉन्च से पहले सरकारी पोर्टल से सत्यापित करें।

## वेबसाइट चलाना
Node.js LTS इंस्टॉल करें। फिर:
```bash
cd web
npm install
npm run dev
```
ब्राउज़र में Vite द्वारा दिखाया गया local address खोलें।

## वेबसाइट build
```bash
npm run build
```
`web/dist` को Firebase Hosting या अन्य hosting पर deploy किया जा सकता है।

## Firebase setup
- Firebase Console में नया project बनाएं।
- Web App जोड़ें और config कॉपी करें।
- Authentication > Sign-in method > Email/Password enable करें।
- Authentication में अपना admin user बनाएं।
- Firestore Database बनाएं।
- अपना admin UID लेकर rules में `YOUR_ADMIN_UID` बदलें।
- Firebase CLI से rules deploy करें:
```bash
npm install -g firebase-tools
firebase login
firebase init
firebase deploy --only firestore:rules
```

## Android ऐप
`mobile/` में Flutter starter है। Flutter SDK और Android Studio सेटअप के बाद:
```bash
cd mobile
flutter pub get
flutter run
```
अभी मोबाइल starter में Firebase जोड़ना बाकी है; वेबसाइट के Firebase setup को मोबाइल में भी अलग से configure करना होगा।

## आगे के विकास चरण
- OTP/phone authentication और consent
- डीलर KYC व admin approval
- ग्राहक enquiry assignment
- district-wise verified dealer directory
- notifications
- privacy policy, terms, grievance/contact process
- testing, backup, monitoring और production deployment
