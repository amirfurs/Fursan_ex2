# 🚀 البدء السريع - نشر موقع فرسان العقيدة

## خطوات النشر السريع (15 دقيقة)

### 1️⃣ إعداد قاعدة البيانات (5 دقائق)

1. اذهب إلى [MongoDB Atlas](https://www.mongodb.com/atlas) → سجل حساب جديد
2. أنشئ Cluster جديد (اختر المجاني M0)
3. في "Database Access" → أنشئ مستخدم جديد
4. في "Network Access" → أضف `0.0.0.0/0`
5. "Connect" → "Connect your application" → انسخ الرابط

### 2️⃣ نشر على Vercel (5 دقائق)

#### خيار أ: من GitHub
1. ارفع الكود على GitHub
2. اذهب إلى [Vercel](https://vercel.com) → "New Project"
3. اختر repository → Deploy

#### خيار ب: Vercel CLI  
```bash
npm i -g vercel
vercel
```

### 3️⃣ إعداد المتغيرات (2 دقيقة)

في Vercel Dashboard → Settings → Environment Variables:

```
MONGO_URL = mongodb+srv://username:password@cluster0.xxx.mongodb.net/foursan_al_aqida?retryWrites=true&w=majority
DB_NAME = foursan_al_aqida  
SECRET_KEY = your-super-secret-key-123456789
```

### 4️⃣ اختبار الموقع (3 دقائق)

1. انتظر انتهاء Build
2. ادخل على الرابط → اختبر التسجيل
3. `/admin` → كلمة المرور: `admin2025`
4. أنشئ قسم وأول مقال

---

## ✅ تم! موقعك جاهز

- **الموقع**: `your-project.vercel.app`
- **الإدارة**: `your-project.vercel.app/admin`
- **كلمة مرور الإدارة**: `admin2025`

---

## 🔧 تخصيص سريع

### تغيير اسم الموقع:
```javascript
// في api/index.py
site_name: str = "اسم موقعك الجديد"
```

### تغيير كلمة مرور الإدارة:
```javascript  
// في frontend/src/App.js
const ADMIN_PASSCODE = "كلمة_المرور_الجديدة";
```

### إضافة أول محتوى:
1. `/admin` → "إضافة قسم" → مثلاً "العقيدة"
2. "كتابة مقال" → اختر القسم واكتب
3. انشر وشارك! 

---

**🎉 مبروك! موقعك الإسلامي جاهز للعالم**