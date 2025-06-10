# دليل نشر موقع فرسان العقيدة على Vercel

## 🚀 خطوات النشر:

### 1. إعداد قاعدة البيانات MongoDB Atlas (مجاني)

1. اذهب إلى [MongoDB Atlas](https://www.mongodb.com/atlas)
2. أنشئ حساب جديد أو سجل دخول
3. أنشئ مشروع جديد باسم "foursan-al-aqida"
4. أنشئ cluster جديد (اختر الخطة المجانية M0)
5. في قسم "Database Access":
   - أنشئ مستخدم جديد
   - احفظ اسم المستخدم وكلمة المرور
6. في قسم "Network Access":
   - أضف `0.0.0.0/0` للسماح بالوصول من أي مكان
7. اضغط على "Connect" واختر "Connect your application"
8. انسخ connection string (سيبدو مثل):
   ```
   mongodb+srv://username:password@cluster0.xxxxx.mongodb.net/foursan_al_aqida?retryWrites=true&w=majority
   ```

### 2. نشر على Vercel

#### الطريقة الأولى: من خلال GitHub (الأسهل)

1. ارفع المشروع على GitHub:
   ```bash
   git init
   git add .
   git commit -m "Initial commit"
   git branch -M main
   git remote add origin https://github.com/your-username/foursan-al-aqida.git
   git push -u origin main
   ```

2. اذهب إلى [Vercel](https://vercel.com)
3. سجل دخول باستخدام GitHub
4. اضغط "New Project"
5. اختر repository "foursan-al-aqida"
6. في إعدادات المشروع:
   - **Framework Preset**: Create React App
   - **Root Directory**: `./`
   - **Build Command**: `yarn vercel-build`
   - **Output Directory**: `frontend/build`

#### الطريقة الثانية: Vercel CLI

1. ثبت Vercel CLI:
   ```bash
   npm i -g vercel
   ```

2. سجل دخول:
   ```bash
   vercel login
   ```

3. من مجلد المشروع:
   ```bash
   vercel
   ```

### 3. إعداد متغيرات البيئة في Vercel

1. في لوحة تحكم Vercel، اذهب إلى مشروعك
2. اذهب إلى Settings > Environment Variables
3. أضف المتغيرات التالية:

   ```
   MONGO_URL = mongodb+srv://username:password@cluster0.xxxxx.mongodb.net/foursan_al_aqida?retryWrites=true&w=majority
   DB_NAME = foursan_al_aqida
   SECRET_KEY = your-super-secret-jwt-key-here
   ```

4. احفظ الإعدادات

### 4. إعداد Frontend للإنتاج

تأكد من أن ملف `.env` في مجلد frontend يحتوي على:

```
REACT_APP_BACKEND_URL=https://your-vercel-url.vercel.app
```

### 5. نشر وتحديث

بعد إعداد كل شيء:

1. اضغط "Deploy" في Vercel
2. انتظر انتهاء عملية البناء
3. اختبر الموقع للتأكد من عمل كل شيء

## 🔧 ملاحظات مهمة:

### أمان قاعدة البيانات:
- غير اسم المستخدم وكلمة المرور الافتراضية
- استخدم كلمة مرور قوية
- قم بتفعيل IP Access List حسب الحاجة

### أمان التطبيق:
- غير `SECRET_KEY` إلى قيمة سرية قوية
- راجع إعدادات CORS في الإنتاج
- فعل HTTPS في جميع البيئات

### الأداء:
- Vercel يوفر CDN تلقائياً
- الصور محفوظة كـ base64 (مناسب للمشاريع الصغيرة)
- يمكن تحسين تحميل الصور لاحقاً إذا احتجت

## 🎯 بعد النشر:

1. اختبر جميع الوظائف:
   - تسجيل حساب جديد
   - تسجيل دخول
   - إنشاء قسم جديد (في لوحة الإدارة)
   - كتابة مقال
   - التعليق والإعجاب

2. كلمة مرور الإدارة: `admin2025`

3. رابط لوحة الإدارة: `your-domain.vercel.app/admin`

## 🐛 حل المشاكل الشائعة:

### مشكلة في الاتصال بقاعدة البيانات:
- تأكد من صحة connection string
- تأكد من إضافة IP address في Network Access
- تأكد من صحة اسم المستخدم وكلمة المرور

### مشكلة في Build:
- تأكد من أن جميع dependencies مثبتة
- راجع logs في Vercel لمعرفة الخطأ
- تأكد من إعدادات Build Command

### مشكلة في APIs:
- تأكد من إعداد متغيرات البيئة
- راجع Function Logs في Vercel
- تأكد من أن API paths صحيحة

## 📧 الدعم:

إذا واجهت أي مشاكل، تحقق من:
1. Vercel Function Logs
2. Browser Console للأخطاء
3. Network tab لطلبات API

---

بالتوفيق في نشر موقع فرسان العقيدة! 🕌✨