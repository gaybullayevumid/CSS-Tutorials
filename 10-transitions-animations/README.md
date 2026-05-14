# CSS Transitions va Animations (O'tishlar va Animatsiyalar)

Ushbu bo'lim CSS yordamida veb-sahifalarga qanday qilib hayot bag'ishlash, interaktiv o'tishlar (transitions) va murakkab animatsiyalar yaratishni o'rganishga bag'ishlangan. Barcha misollar amaliy kodlar (`index.html`) bilan keltirilgan bo'lib, har bir papka ichida ushbu mavzuni chuqurroq o'rganishingiz mumkin.

## 📂 Darslar Mundarijasi

### [1. Transition (O'tishlar)](./01-transition)
`transition` xususiyati element holati o'zgarganda (masalan, hover qilinganda) o'zgarishlarning qanchalik tez yoki sekin, qaysi usulda amalga oshishini boshqaradi.
- **Asosiy xususiyatlar:** `transition-property`, `transition-duration`, `transition-timing-function`, `transition-delay`.
- *Misol:* Tugmaning rangi o'zgarishi, elementning kattalashishi yoki soyasi paydo bo'lishining silliq o'tishi.

### [2. Transform (Shakl o'zgarishi)](./02-transform)
`transform` elementi joylashuvi, o'lchami yoki shaklini o'zgartirishga xizmat qiladi. Ushbu qismda bir nechta transform xususiyatlarini qanday qilib birgalikda ishlatish (kombinatsiya) hamda `transform-origin` (o'zgarish markazi) haqida o'rganasiz.

### [3. Translate (Siljitish)](./03-translate)
Elementlarni o'z joyidan surish / siljitish uchun ishlatiladi. Bu pozitsiyalashning (position) eng zamonaviy va samarali (performance-friendly) usulidir.
- **Turlari:** `translateX()`, `translateY()`, `translate()`, `translate3d()`.

### [4. Scale (Masshtablash)](./04-scale)
Elementning o'lchamini kattalashtirish yoki kichraytirish imkonini beradi. Hover effektlarida eng ko'p ishlatiladigan xususiyatlardan biri.
- **Turlari:** `scaleX()`, `scaleY()`, `scale()`.

### [5. Rotate (Aylantirish)](./05-rotate)
Elementlarni 2D va 3D o'qlar bo'ylab aylantirish imkonini beradi.
- **Turlari:** `rotate()` (Z o'qi bo'ylab), `rotateX()` (vertikal o'q), `rotateY()` (gorizontal o'q).

### [6. Skew (Qiyshaytirish)](./06-skew)
Elementlarni berilgan burchak bo'yicha qiyshaytirish uchun ishlatiladi. Rombsimon yoki nostandart shakllar yaratishda foydali.
- **Turlari:** `skewX()`, `skewY()`, `skew()`.

### [7. Keyframes (Kadrlar)](./07-keyframes)
Faqat hover kabi holatlardagina emas, balki sahifa yuklanganda yoki doimiy ravishda ishlab turadigan murakkab animatsiyalar yaratish uchun `@keyframes` qoidasidan foydalaniladi.
- `from` / `to` sintaksisi yoki foizlar (`0%`, `50%`, `100%`) orqali har bir kadr holatini belgilash.

### [8. Animation (Animatsiya xususiyatlari)](./08-animation)
Yaratilgan `@keyframes` animatsiyalarini qanday boshqarishni o'rgatadi.
- **Asosiy xususiyatlar:** 
  - `animation-iteration-count`: Necha marta ishlashi (masalan: `infinite`).
  - `animation-direction`: Qaysi yo'nalishda harakatlanishi (`normal`, `reverse`, `alternate`).
  - `animation-fill-mode`: Animatsiya tugagandan so'ng qanday holatda qolishi (`forwards`, `backwards`).

### [9. Animation Timing (Animatsiya vaqti funksiyalari)](./09-animation-timing)
Animatsiyaning tezlashish va sekinlashish dinamikasini belgilaydi.
- **Turlari:** `ease`, `linear` (bir xil tezlikda), `ease-in`, `ease-out`, `ease-in-out` hamda `steps()` qadamli animatsiyalar.

---

## 🚀 Qanday Foydalaniladi?
Ushbu darslarni amaliy ko'rish uchun, o'zingizni qiziqtirgan mavzu papkasiga kiring (masalan: `01-transition`) va u yerdagi `index.html` faylini brauzerda oching. O'zgarishlarni va xususiyatlarni kodda o'zgartirib tajriba o'tkazishingiz tavsiya etiladi!
