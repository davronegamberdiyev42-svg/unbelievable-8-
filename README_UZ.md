# IELTS Boost — Stage 40 Advanced Master Release

## Nimalar yaxshilandi
- Speaking Part 1/2/3 va daily challenge transcript maydonlari alohida. Web Speech API mavjud bo‘lsa, live recognition shu field’ga yozadi; internet, mikrofon ruxsati va Chrome/device qo‘llovi talab qilinishi mumkin.
- Pronunciation Lab uchun mustaqil audio recorder qo‘shildi. U Speaking Part audio fayllarini bosib ketmaydi; yozuv IndexedDB’da alohida saqlanadi va qayta tinglanadi.
- Fluency missiyasi 4 qismli argument rejasidan tashqari real spoken-response transcript ham talab qiladi.
- Collocations uchun 24 ta, grammar uchun 24 ta yangi original context question; har bir javobda qoidaga oid izoh va transfer sentence.
- Paraphrase’da claim, scope, certainty va time bo‘yicha to‘rtta alohida semantik nazorat. Bu avtomatik semantik ekvivalentlik isboti emas; learner self-check.
- Vocabulary builder: 19,000 index, 4,000 IPA cohort, 4,000 translation lookup target va 9,000 definition/IPA lookup target. Batch (10/20) bilan online so‘rovlar bajarilib, local cache’da saqlanadi. Machine translation sense-check talab qiladi.
- Adaptive performance board: modul bo‘yicha best/average/mastery va so‘nggi 7 curriculum day attempt trend. Internal formative score, IELTS band emas.
- PWA manifest identifikatori, start_url va scope aniq `/unbelievable-8-/`; 192/512 icons, maskable icons, apple-touch icon, versioned service worker.

## GitHub Pages deployment
1. `01_ROOT_FILES.zip` ni Extract qil; **ichidagi barcha fayl va papkalarni** repository root’ga yukla. `index.html`, `manifest.webmanifest`, `sw.js`, app-icon’lar va `.nojekyll` root’da bo‘lsin.
2. `audio` papkasini och. Uchta audio ZIP’ni bittadan Extract qil va ichidagi MP3’larni mavjud `audio/` papkasiga joyla (har bir 28 ta fayl alohida commit bo‘lishi mumkin).
3. Repository → Settings → Pages → Deploy from a branch → `main` → `/(root)` → Save.
4. To‘liq HTTPS URL’ni och: `https://davronegamberdiyev42-svg.github.io/unbelievable-8-/`. Sahifa yuklangach bir marta qayta yukla va Settings → PWA readiness check ni ishga tushir.
5. Chrome menyusida `Install app` yoki `Install and create shortcut` tanla; ikkinchi dialogda `Install`ni tanla. `Create shortcut`ni tanlasang faqat shortcut bo‘ladi.

## Muhim install eslatma
Sayt manifesti va ikonkalari PWA talablariga tayyorlangan, ammo Chrome native install taklifini majburlab chiqara olmaydi. Chrome install event ko‘rinishi uchun HTTPS, nom, 192/512 icon, start_url, standalone display va foydalanuvchi engagement shartlari mavjud. Android’da haqiqiy WebAPK uchun Google Mobile Services kerak; GMS bo‘lmasa, Chrome browser-badged shortcut yaratishi mumkin. Eski shortcut’ni olib tashlab, yangi versiya deployment bo‘lgach qayta urin.

## Speaking transcript izohi
Live transcript Web Speech API’ga bog‘liq; Samsung Android Chrome’da ishlashi uchun mikrofon ruxsati va ko‘pincha internet talab qilinadi. Bu offline Whisper model emas. API qo‘llanmasa, transcript field ichidagi Samsung Keyboard/Gboard voice typing orqali gapni matnga aylantirish mumkin. ASR confidence — IELTS pronunciation score emas.

## Vocabulary truth-in-labeling
19,000 ta qidiriladigan word index to‘liq offline dictionary degani emas. 4,000 IPA cohort va 9,000 lookup target mavjud; translation/definition batch orqali onlayn olinadi va shu browser/device’da cache qilinadi. MyMemory translation mashina tarjimasi; exact sense tekshirilmaguncha tasdiqlangan deb ishlatilmasin.

## Progress va privacy
Stage 1–39 progress key’lari saqlanadi. Stage 40 yangi pronunciation recording’lari uchun alohida IndexedDB key ishlatadi. ZIP/JSON backup oldidan va platformani almashtirishdan oldin eski progress backup ol. Audio blobs JSON backup ichiga kirmaydi.
