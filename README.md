<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1" />
<title>وكالة إيهران ترافل - إدارة الموقع</title>
<style>
  body {font-family: Arial, sans-serif; direction: rtl; background: var(--bg-color, #fff5f5); margin: 0; padding: 0;}
  header {background-color: var(--header-color, #b30000); color: white; padding: 20px; text-align: center;}
  nav {background-color: var(--nav-color, #cc0000); padding: 10px; text-align: center;}
  nav a {color: white; margin: 0 10px; text-decoration: none; font-weight: bold;}
  section {padding: 20px; max-width: 800px; margin: auto;}
  .package {background: white; padding: 15px; margin-bottom: 15px; border-radius: 5px; box-shadow: 0 0 8px rgba(0,0,0,0.1);}
  footer {background: var(--footer-color, #ffe6e6); text-align: center; padding: 15px; margin-top: 40px;}
  label {display: block; margin-top: 10px; font-weight: bold;}
  input, textarea, select {width: 100%; padding: 8px; margin-top: 5px; border-radius: 4px; border: 1px solid #ccc;}
  button {margin-top: 10px; padding: 10px 20px; background: var(--nav-color, #cc0000); color: white; border: none; border-radius: 4px; cursor: pointer;}
  #admin-panel {background: #fff; padding: 20px; margin: 20px auto; max-width: 800px; border-radius: 8px; box-shadow: 0 0 10px rgba(0,0,0,0.2);}
</style>
</head>
<body>

<header>
  <h1 id="agency-name">وكالة إيهران ترافل</h1>
  <p id="agency-desc">رحلات العمرة المميزة من الجزائر إلى الحرمين الشريفين</p>
</header>

<nav>
  <a href="#packages">باقات العمرة</a>
  <a href="#booking">الحجز</a>
  <a href="#contact">تواصل معنا</a>
</nav>

<section id="packages">
  <h2>باقات العمرة</h2>
  <div id="packages-list"></div>
</section>

<section id="booking">
  <h2>احجز الآن</h2>
  <form id="booking-form">
    <input type="text" id="booking-name" placeholder="الاسم الكامل" required />
    <input type="tel" id="booking-phone" placeholder="رقم الهاتف" required />
    <input type="email" id="booking-email" placeholder="البريد الإلكتروني" />
    <textarea id="booking-notes" rows="4" placeholder="ملاحظات أو استفسار..."></textarea>
    <button type="submit">إرسال الطلب</button>
  </form>
</section>

<section id="contact">
  <h2>معلومات التواصل</h2>
  <p><strong>العنوان:</strong> <span id="agency-address">POS 50, Tour C4, Résidence Mira Belle, Bir El Djir, Oran</span></p>
  <p><strong>الهاتف 1:</strong> <span id="phone1">0540000478</span></p>
  <p><strong>الهاتف 2:</strong> <span id="phone2">0772370228</span></p>
  <p><strong>البريد الإلكتروني:</strong> <span id="agency-email">ihranetravel26@yahoo.com</span></p>
  <p><strong>واتساب:</strong> <a id="whatsapp-link" href="https://wa.me/213540000478" target="_blank">تواصل معنا على واتساب</a></p>
  <p><strong>فيسبوك:</strong> <a id="facebook-link" href="https://facebook.com/ihranetravel" target="_blank">صفحتنا على فيسبوك</a></p>
</section>

<footer>
  &copy; 2025 وكالة إيهران ترافل. جميع الحقوق محفوظة.
</footer>

<!-- لوحة التحكم -->
<section id="admin-panel">
  <h2>لوحة التحكم</h2>
  <label>اسم الوكالة:
    <input type="text" id="input-agency-name" />
  </label>
  <label>وصف الوكالة:
    <input type="text" id="input-agency-desc" />
  </label>
  <label>العنوان:
    <input type="text" id="input-address" />
  </label>
  <label>رقم الهاتف 1:
    <input type="text" id="input-phone1" />
  </label>
  <label>رقم الهاتف 2:
    <input type="text" id="input-phone2" />
  </label>
  <label>البريد الإلكتروني:
    <input type="email" id="input-email" />
  </label>
  <label>رابط واتساب:
    <input type="text" id="input-whatsapp" placeholder="مثلاً https://wa.me/213540000478" />
  </label>
  <label>رابط فيسبوك:
    <input type="text" id="input-facebook" placeholder="مثلاً https://facebook.com/ihranetravel" />
  </label>

  <h3>تعديل العروض</h3>
  <div id="admin-packages"></div>
  <button id="add-package">إضافة عرض جديد</button>
  
  <h3>تغيير ألوان الموقع</h3>
  <label>لون الخلفية:
    <input type="color" id="color-bg" value="#fff5f5" />
  </label>
  <label>لون الترويسة:
    <input type="color" id="color-header" value="#b30000" />
  </label>
  <label>لون الشريط العلوي:
    <input type="color" id="color-nav" value="#cc0000" />
  </label>
  <label>لون الفوتر:
    <input type="color" id="color-footer" value="#ffe6e6" />
  </label>

  <button id="save-settings">حفظ التغييرات</button>
</section>

<script>
  // بيانات الموقع الافتراضية
  let siteData = {
    agencyName: "وكالة إيهران ترافل",
    agencyDesc: "رحلات العمرة المميزة من الجزائر إلى الحرمين الشريفين",
    address: "POS 50, Tour C4, Résidence Mira Belle, Bir El Djir, Oran",
    phone1: "0540000478",
    phone2: "0772370228",
    email: "ihranetravel26@yahoo.com",
    whatsapp: "https://wa.me/213540000478",
    facebook: "https://facebook.com/ihranetravel",
    packages: [
      { title: "باقة اقتصادية", desc: "10 أيام | فندق 3 نجوم | طيران مباشر | حافلات مكيفة", price: "185,000 دج" },
      { title: "باقة راحة", desc: "12 يوم | فندق 4 نجوم | طيران مباشر | تنقل VIP", price: "250,000 دج" },
      { title: "باقة VIP", desc: "14 يوم | فندق 5 نجوم قريب من الحرم | طيران درجة رجال الأعمال", price: "350,000 دج" },
    ],
    colors: {
      bg: "#fff5f5",
      header: "#b30000",
      nav: "#cc0000",
      footer: "#ffe6e6"
    }
  };

  // تحميل البيانات من localStorage أو تعيين الافتراضي
  function loadData() {
    const saved = localStorage.getItem("siteData");
    if (saved) {
      siteData = JSON.parse(saved);
    }
  }

  // حفظ البيانات في localStorage
  function saveData() {
    localStorage.setItem("siteData", JSON.stringify(siteData));
  }

  // عرض البيانات في الصفحة
  function renderSite() {
    document.getElementById("agency-name").textContent = siteData.agencyName;
    document.getElementById("agency-desc").textContent = siteData.agencyDesc;
    document.getElementById("agency-address").textContent = siteData.address;
    document.getElementById("phone1").textContent = siteData.phone1;
    document.getElementById("phone2").textContent = siteData.phone2;
    document.getElementById("agency-email").textContent = siteData.email;
    document.getElementById("whatsapp-link").href = siteData.whatsapp;
    document.getElementById("facebook-link").href = siteData.facebook;

    // تطبيق الألوان
    document.body.style.setProperty('--bg-color', siteData.colors.bg);
    document.querySelector('header').style.backgroundColor = siteData.colors.header;
    document.querySelector('nav').style.backgroundColor = siteData.colors.nav;
    document.querySelector('footer').style.backgroundColor = siteData.colors.footer;

    // عرض العروض
    const packagesList = document.getElementById("packages-list");
    packagesList.innerHTML = "";
    siteData.packages.forEach((p, i) => {
      const div = document.createElement("div");
      div.className = "package";
      div.innerHTML = `<h3>${p.title}</h3><p>${p.desc}</p><p><strong>السعر
