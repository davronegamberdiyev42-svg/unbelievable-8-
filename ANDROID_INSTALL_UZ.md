# Samsung Galaxy / Chrome — haqiqiy ilova sifatida o‘rnatish

## 1. Avval saytning yangi versiyasini och

Quyidagi to‘liq manzilni Chrome’ning o‘zida och:

`https://davronegamberdiyev42-svg.github.io/unbelievable-8-/`

GitHub repository sahifasi yoki `index.html` faylining preview manzilini emas, aynan yuqoridagi Pages manzilini ishlat. Sahifa to‘liq yuklangach bir necha marta ichida harakat qil va bir marta refresh qil. Settings → PWA readiness check ichida manifest, 192/512 ikonka va service worker qatorlari PASS bo‘lishi kerak.

## 2. Eski shortcut’ni olib tashla

Bosh ekrandagi oldingi IELTS Boost shortcut’ni uzoq bosib, Remove from Home screen / Remove ni tanla. Hozircha Chrome’dagi site data yoki ilova ma’lumotlarini tozalama — bu progressni ham o‘chirishi mumkin.

## 3. Chrome orqali o‘rnat

1. Sayt ochiq turgan paytda Chrome’dagi `⋮` menyuni bos.
2. `Install app` bo‘lsa, shuni tanla.
3. Agar `Install and create shortcut` chiqsa, uni tanlaganingdan keyingi oynada albatta `Install`ni bos.
4. `Create shortcut` yoki faqat `Add to Home screen` tanlansa, bu oddiy browser shortcut bo‘lishi mumkin.

## 4. Chrome faqat shortcut bersa

Android’da Chrome haqiqiy WebAPK yaratishi uchun qurilmada Google Mobile Services (GMS) mavjud bo‘lishi kerak. Chrome GMS’siz muhitda saytni brauzer belgisi bilan shortcut sifatida qo‘shishi mumkin. Samsung qurilmalarida Samsung Internet ham PWA’ni WebAPK ko‘rinishida o‘rnatishi mumkin.

Shuning uchun:
- Settings → Apps ichida Google Play services bor va enabled ekanini tekshir.
- Chrome’ni Play Store’dan yangila.
- Hali ham Chrome shortcut bersa, Samsung Internet’da ayni HTTPS Pages manzilini ochib, browser menyusidagi Add to / Install app variantini tekshir.

## 5. Nima uchun sayt o‘rnatishni majburlay olmaydi?

Sayt manifest, ikonka, HTTPS va service worker kabi install shartlarini ta’minlaydi. Yakuniy `Install app` taklifini Chrome va Android belgilaydi. Sayt kodidan OS darajasidagi native app install’ni majburlash mumkin emas.

Rasmiy yordam:
- Chrome Android: https://support.google.com/chrome/answer/9658361
- PWA installability / Android WebAPK: https://developer.mozilla.org/en-US/docs/Web/Progressive_web_apps/Guides/Making_PWAs_installable
