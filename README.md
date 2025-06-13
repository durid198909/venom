# Venom USDT - منصة التعدين والاستثمار الرقمي

منصة التعدين والاستثمار الرقمي الأكثر تطوراً في العالم العربي

## المميزات

- 🚀 عوائد يومية مضمونة
- 🔒 أمان متقدم
- ⚡ سحب فوري
- 📱 تطبيق ويب تقدمي (PWA)
- 🌐 دعم كامل للغة العربية

## التقنيات المستخدمة

- React 18 + TypeScript
- Tailwind CSS
- Vite
- PWA Support
- Service Workers

## التثبيت والتشغيل

```bash
# تثبيت المتطلبات
npm install

# تشغيل الخادم المحلي
npm run dev

# بناء المشروع للإنتاج
npm run build

# معاينة البناء
npm run preview
```

## النشر على منصات مختلفة

### 1. Vercel
```bash
# تثبيت Vercel CLI
npm i -g vercel

# نشر المشروع
vercel --prod
```

### 2. Firebase Hosting
```bash
# تثبيت Firebase CLI
npm install -g firebase-tools

# تسجيل الدخول
firebase login

# تهيئة المشروع
firebase init hosting

# بناء ونشر المشروع
npm run build
firebase deploy
```

### 3. GitHub Pages
```bash
# بناء المشروع
npm run build

# رفع مجلد dist إلى فرع gh-pages
```

### 4. استضافة مشتركة (cPanel)
1. قم ببناء المشروع: `npm run build`
2. ارفع محتويات مجلد `dist` إلى مجلد `public_html`
3. تأكد من رفع ملف `.htaccess` للتوجيه الصحيح

## ملفات التكوين

- `vercel.json` - تكوين Vercel
- `firebase.json` - تكوين Firebase
- `_redirects` - تكوين Netlify
- `.htaccess` - تكوين Apache/cPanel

## الأمان

- تشفير SSL مطلوب
- حماية CSRF
- تنظيف المدخلات
- حماية XSS

## الدعم

للدعم الفني، يرجى التواصل معنا عبر:
- البريد الإلكتروني: support@venomusdt.com
- الموقع الإلكتروني: https://venomusdt.com

## الترخيص

جميع الحقوق محفوظة © 2025 Venom USDT