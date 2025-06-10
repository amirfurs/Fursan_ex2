# فرسان العقيدة 🕌

منصة إسلامية باللغة العربية لنشر المقالات العقدية والفقهية والردود العلمية على الشبهات والمخالفات.

## ✨ المميزات

- 🌙 **تصميم عربي أصيل** مع دعم كامل للغة العربية وخط RTL
- 📚 **نظام إدارة المحتوى** لنشر وتصنيف المقالات  
- 👥 **نظام العضوية** مع ملفات شخصية وصور
- 💬 **نظام التعليقات** التفاعلي
- ❤️ **نظام الإعجابات** للمقالات
- 🎨 **لوحة إدارة شاملة** لإدارة المحتوى
- 📱 **تصميم متجاوب** يعمل على جميع الأجهزة
- 🔒 **نظام أمان متقدم** مع JWT authentication

## 🚀 التقنيات المستخدمة

### Frontend
- **React 19** - مكتبة الواجهة الأمامية
- **React Router** - للتنقل بين الصفحات
- **Tailwind CSS** - للتصميم والتخطيط
- **Axios** - للتواصل مع الخادم
- **Arabic Fonts** - خطوط عربية جميلة (Cairo, Amiri)

### Backend
- **FastAPI** - إطار عمل Python سريع وحديث
- **MongoDB** - قاعدة بيانات NoSQL
- **Motor** - تعامل غير متزامن مع MongoDB
- **JWT** - نظام المصادقة الآمن
- **BCrypt** - تشفير كلمات المرور

### الاستضافة
- **Vercel** - استضافة Frontend و Backend APIs
- **MongoDB Atlas** - قاعدة البيانات السحابية

## 📁 هيكل المشروع

```
foursan-al-aqida/
├── frontend/                 # تطبيق React
│   ├── src/
│   │   ├── App.js            # المكون الرئيسي
│   │   ├── App.css           # تصميم عربي مخصص
│   │   └── index.css         # تصميم عام
│   ├── package.json
│   └── build/                # ملفات الإنتاج
├── api/                      # Serverless Functions
│   ├── index.py              # FastAPI application
│   └── requirements.txt      # مكتبات Python
├── vercel.json               # إعدادات Vercel
└── DEPLOYMENT_GUIDE.md       # دليل النشر
```

## 🎯 الصفحات والوظائف

### الواجهة العامة
- **الصفحة الرئيسية** (`/`) - عرض أحدث المقالات والأقسام
- **صفحة المقال** (`/article/:id`) - قراءة المقال مع التعليقات
- **صفحة القسم** (`/section/:id`) - تصفح مقالات قسم معين
- **تسجيل الدخول** (`/login`) - للأعضاء
- **إنشاء حساب** (`/register`) - للأعضاء الجدد
- **الملف الشخصي** (`/profile`) - إدارة الحساب

### لوحة الإدارة (`/admin`)
- **إدارة الأقسام** - إضافة وحذف التصنيفات
- **إدارة المقالات** - كتابة وتعديل وحذف المقالات
- **رفع الصور** - إضافة صور للمقالات
- **إدارة الشعار** - تحديث شعار الموقع
- **الإحصائيات** - عرض إحصائيات المحتوى

## ⚙️ التثبيت والتشغيل المحلي

### المتطلبات
- Node.js 18+
- Python 3.8+
- MongoDB

### خطوات التثبيت

1. **استنساخ المشروع**
   ```bash
   git clone https://github.com/your-username/foursan-al-aqida.git
   cd foursan-al-aqida
   ```

2. **إعداد Frontend**
   ```bash
   cd frontend
   yarn install
   cp .env.example .env
   # قم بتحديث REACT_APP_BACKEND_URL في .env
   ```

3. **إعداد Backend**
   ```bash
   cd ../backend
   pip install -r requirements.txt
   cp .env.example .env
   # قم بتحديث MONGO_URL و DB_NAME في .env
   ```

4. **تشغيل المشروع**
   ```bash
   # تشغيل Backend
   cd backend
   uvicorn server:app --reload --port 8001

   # تشغيل Frontend (في terminal آخر)
   cd frontend
   yarn start
   ```

## 🌐 النشر على Vercel

راجع الدليل التفصيلي في [DEPLOYMENT_GUIDE.md](./DEPLOYMENT_GUIDE.md)

### خطوات سريعة:

1. **إعداد MongoDB Atlas**
   - إنشاء cluster مجاني
   - الحصول على connection string

2. **نشر على Vercel**
   ```bash
   # ربط مع GitHub ونشر أو استخدام CLI
   npm i -g vercel
   vercel
   ```

3. **إعداد متغيرات البيئة**
   ```
   MONGO_URL=mongodb+srv://...
   DB_NAME=foursan_al_aqida
   SECRET_KEY=your-secret-key
   ```

## 🔐 معلومات الإدارة

- **رابط لوحة الإدارة**: `/admin`
- **كلمة مرور الإدارة**: `admin2025`
- **لتغيير كلمة المرور**: عدل `ADMIN_PASSCODE` في `App.js`

## 🎨 التخصيص

### الألوان والتصميم
- **الألوان الأساسية**: أسود وأحمر مع لمسات ذهبية
- **الخطوط**: Cairo (للنصوص) و Amiri (للعناوين)
- **الاتجاه**: RTL مع دعم كامل للعربية

### إضافة أقسام جديدة
1. ادخل لوحة الإدارة
2. اضغط "إضافة قسم"
3. أدخل اسم ووصف القسم

### كتابة مقال جديد
1. ادخل لوحة الإدارة
2. اضغط "كتابة مقال"
3. اختر القسم واكتب المحتوى
4. أضف صورة (اختياري)

## 🛡️ الأمان

- **تشفير كلمات المرور**: BCrypt
- **مصادقة آمنة**: JWT tokens
- **حماية APIs**: Authentication middleware
- **تحقق من الصلاحيات**: User ownership validation

## 📱 التوافق

- ✅ جميع المتصفحات الحديثة
- ✅ الهواتف الذكية والتابلت
- ✅ دعم كامل للغة العربية
- ✅ تصميم متجاوب

## 🤝 المساهمة

نرحب بالمساهمات! يمكنك:

1. فتح Issue لطلب ميزة أو إبلاغ عن خطأ
2. إنشاء Pull Request لتحسين الكود
3. تحسين الترجمة أو التصميم
4. إضافة ميزات جديدة

## 📄 الرخصة

هذا المشروع مرخص تحت رخصة MIT - راجع ملف [LICENSE](LICENSE) للتفاصيل.

## 📞 التواصل

- **الموقع**: [foursan-al-aqida.vercel.app](https://foursan-al-aqida.vercel.app)
- **البريد الإلكتروني**: admin@foursan-al-aqida.com
- **GitHub**: [github.com/your-username/foursan-al-aqida](https://github.com/your-username/foursan-al-aqida)

---

**"وَقُلِ اعْمَلُوا فَسَيَرَى اللَّهُ عَمَلَكُمْ وَرَسُولُهُ وَالْمُؤْمِنُونَ"**

بُني هذا المشروع بحب لخدمة العلم الشرعي والدعوة الإسلامية 🕌✨