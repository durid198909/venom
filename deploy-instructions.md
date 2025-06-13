# دليل النشر على منصات الاستضافة المختلفة

## 1. Vercel (مجاني ومدفوع)

### الخطوات:
1. قم بإنشاء حساب على [Vercel](https://vercel.com)
2. اربط حسابك بـ GitHub
3. ارفع الكود إلى GitHub repository
4. في Vercel، اضغط "New Project"
5. اختر المستودع واضغط "Deploy"

### أو باستخدام CLI:
```bash
npm i -g vercel
vercel login
vercel --prod
```

---

## 2. Firebase Hosting (مجاني حتى 10GB)

### الخطوات:
1. قم بإنشاء مشروع على [Firebase Console](https://console.firebase.google.com)
2. فعّل Firebase Hosting
3. ثبت Firebase CLI:
```bash
npm install -g firebase-tools
firebase login
firebase init hosting
```
4. اختر المشروع الذي أنشأته
5. اختر `dist` كمجلد النشر
6. اختر "Yes" لـ single-page app
7. انشر المشروع:
```bash
npm run build
firebase deploy
```

---

## 3. GitHub Pages (مجاني)

### الخطوات:
1. ارفع الكود إلى GitHub repository
2. في إعدادات المستودع، اذهب إلى "Pages"
3. اختر "GitHub Actions" كمصدر
4. أنشئ ملف `.github/workflows/deploy.yml`:

```yaml
name: Deploy to GitHub Pages

on:
  push:
    branches: [ main ]

jobs:
  build-and-deploy:
    runs-on: ubuntu-latest
    steps:
    - uses: actions/checkout@v2
    
    - name: Setup Node.js
      uses: actions/setup-node@v2
      with:
        node-version: '18'
        
    - name: Install dependencies
      run: npm install
      
    - name: Build
      run: npm run build
      
    - name: Deploy
      uses: peaceiris/actions-gh-pages@v3
      with:
        github_token: ${{ secrets.GITHUB_TOKEN }}
        publish_dir: ./dist
```

---

## 4. Surge.sh (مجاني)

### الخطوات:
```bash
npm install -g surge
npm run build
cd dist
surge
```

---

## 5. استضافة مشتركة (cPanel/Hostinger/GoDaddy)

### الخطوات:
1. قم ببناء المشروع محلياً:
```bash
npm run build
```

2. ارفع محتويات مجلد `dist` إلى:
   - `public_html` (للدومين الرئيسي)
   - `public_html/subdomain` (للدومين الفرعي)

3. تأكد من رفع ملف `.htaccess` للتوجيه الصحيح

### ملاحظات مهمة للاستضافة المشتركة:
- تأكد من دعم HTTPS
- فعّل ضغط Gzip
- تأكد من دعم Service Workers

---

## 6. DigitalOcean App Platform

### الخطوات:
1. قم بإنشاء حساب على [DigitalOcean](https://digitalocean.com)
2. اذهب إلى "App Platform"
3. اربط GitHub repository
4. اختر "Static Site"
5. اضبط Build Command: `npm run build`
6. اضبط Output Directory: `dist`

---

## 7. Cloudflare Pages (مجاني)

### الخطوات:
1. قم بإنشاء حساب على [Cloudflare](https://cloudflare.com)
2. اذهب إلى "Pages"
3. اربط GitHub repository
4. اضبط Build Command: `npm run build`
5. اضبط Build Output Directory: `dist`

---

## نصائح عامة:

### 1. متغيرات البيئة:
تأكد من إضافة متغيرات البيئة المطلوبة في كل منصة:
- `VITE_APP_NAME=Venom USDT`
- `VITE_APP_URL=https://yourdomain.com`

### 2. الدومين المخصص:
- معظم المنصات تدعم ربط دومين مخصص
- تأكد من إعداد DNS records بشكل صحيح
- فعّل HTTPS دائماً

### 3. الأداء:
- فعّل ضغط Gzip/Brotli
- استخدم CDN إذا كان متاحاً
- اضبط Cache headers بشكل صحيح

### 4. المراقبة:
- اضبط Google Analytics
- راقب الأخطاء باستخدام Sentry أو مشابه
- اضبط uptime monitoring

---

## الدعم الفني:

إذا واجهت أي مشاكل في النشر، تأكد من:
1. بناء المشروع محلياً بنجاح
2. فحص console للأخطاء
3. التأكد من صحة ملفات التكوين
4. مراجعة logs المنصة المستخدمة