NEDJMA — حزمة مصدر Android وتجهيز البناء

المحتويات:
- واجهة NEDJMA الحالية داخل app/src/main/assets/index.html.
- تطبيق Android WebView بالحزمة com.nedjma.app.
- أيقونة تشغيل سوداء وذهبية.
- إعداد GitHub Actions لبناء APK تجريبي، وبناء APK + AAB موقّعين عند توفير أسرار التوقيع.

حالة التحقق في بيئة إعداد هذه الحزمة:
- أرشيف المصدر الأصلي سليم.
- ملفات JavaScript المضمنة اجتازت فحص node --check.
- لا توجد معرفات HTML مكررة.
- لم يتم بناء APK هنا لعدم توفر Android SDK وGradle.
- لم يتم اختبار التطبيق على هاتف فعلي.

بناء Debug:
- افتح المستودع في Android Studio ثم نفّذ Sync وBuild APK.
- أو راجع GitHub Actions؛ ينشأ Debug APK تلقائياً عند اكتمال رفع ملفات المصدر.

بناء Release للنشر:
- يلزم مفتاح توقيع Android خاص بالتطبيق، مع الاحتفاظ بنسختين احتياطيتين مشفرتين.
- أضف أسرار المستودع: ANDROID_KEYSTORE_BASE64 وANDROID_KEYSTORE_PASSWORD وANDROID_KEY_ALIAS وANDROID_KEY_PASSWORD.
- شغّل Workflow يدوياً واختر build_release=true.
- سيُنشئ APK موقّعاً وAAB مناسباً لرفع Google Play.
- لا تضع ملف keystore أو كلمات المرور داخل المستودع أو التطبيق.

قبل النشر العام يجب اختبار التسجيل والدخول والرسائل ورفع الصور والفيديو والقصص والإشعارات وسياسات Supabase على أجهزة حقيقية وحسابات اختبار.
هذه الحزمة مصدر وتجهيز CI وليست APK جاهزاً للنشر.
