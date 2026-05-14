# 08. CSS Animation Xususiyatlari

Oldingi darsda o'rganilgan `@keyframes` orqali yaratilgan animatsiya stsenariysini elementga qanday qo'llashni va uning xatti-harakatini to'liq nazorat qilishni ushbu qismda ko'rib chiqamiz.

### Animatsiyani ulash (`animation-name` & `animation-duration`)
Animatsiya elementda ishlashi uchun kamida 2 narsa kerak: Qaysi animatsiya ishlasin va qancha vaqt davom etsin.
```css
.box {
  animation-name: pulse;      /* Yaratilgan @keyframes nomi */
  animation-duration: 2s;     /* 2 soniya davom etsin */
}
```

### Boshqa asosiy xususiyatlar:
1. **`animation-iteration-count` (Qaytadan ishlashi):** Animatsiya necha marta ishlashi kerak.
   - Qiymatlar: raqam (masalan, `3`) yoki `infinite` (cheksiz aylanadi).
2. **`animation-direction` (Yo'nalish):** Animatsiya qaysi tomonga o'qilishi kerak.
   - `normal` (default: `0%` dan `100%` ga).
   - `reverse` (teskari: `100%` dan `0%` ga).
   - `alternate` (bir safar oldinga, keyingi safar orqaga qaytadi. Masalan yurak urishi uchun mukammal).
3. **`animation-fill-mode` (Tugash holati):** Animatsiya tugagandan so'ng nima bo'lishi.
   - `forwards` (animatsiyaning so'nggi `100%` dagi holatida qoladi, asliga qaytmaydi).
   - `backwards` (boshlang'ich holatga qaytadi).

### Shorthand (Qisqa) Sintaksis
Barcha xususiyatlarni bir qatorda yozish eng keng tarqalgan usuldir:
```css
.box {
  /* name | duration | timing-function | delay | iteration-count | direction | fill-mode */
  animation: pulse 2s ease-in-out 0s infinite alternate;
}
```
