# بناء تطبيق «نور الهداية» للأندرويد (APK)

المشروع جاهز تمامًا: أيقونة التطبيق، الاسم العربي، ومشروع أندرويد مُنشأ مسبقًا داخل مجلد `android/`.

## المتطلبات
- Node.js 18+
- Android Studio (يتضمن Android SDK و Java)

## الخطوات
```bash
npm install
npm run build
npx cap sync android
npx cap open android      # يفتح المشروع في Android Studio
```
ثم من Android Studio: **Build → Build Bundle(s)/APK(s) → Build APK(s)**

أو من سطر الأوامر مباشرة:
```bash
cd android
./gradlew assembleDebug
```
سيكون الملف في: `android/app/build/outputs/apk/debug/app-debug.apk`

للنسخة النهائية للنشر على Google Play:
```bash
cd android
./gradlew assembleRelease     # أو bundleRelease لملف AAB
```

## العمل بدون إنترنت
- كل ملفات التطبيق (الواجهة، الخطوط، الأيقونات) مضمّنة داخل التطبيق نفسه ويعمل بدون إنترنت.
- محتوى القرآن، التفسير، الأحاديث، ومواقيت الصلاة يتم تخزينه تلقائيًا (Cache) بعد أول فتح، فيبقى متاحًا بدون إنترنت.
- التلاوات الصوتية تُحفظ بعد الاستماع إليها مرة واحدة.

## تثبيت مباشر بدون Android Studio (اختياري)
يمكن أيضًا تثبيت التطبيق من المتصفح على الهاتف: افتح رابط التطبيق ثم
«إضافة إلى الشاشة الرئيسية» — سيُثبَّت كتطبيق كامل يعمل بدون إنترنت.
