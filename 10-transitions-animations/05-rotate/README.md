# 05. CSS Rotate (Aylantirish)

`rotate` funksiyasi yordamida har qanday HTML elementini ma'lum bir burchak ostida aylantirishingiz mumkin. O'lchov birligi sifatida doimo graduslar (`deg`) ishlatiladi.

### Aylantirish o'qlari:
1. **`rotate(angle)` yoki `rotateZ(angle)`:** Elementni qog'oz yuzasida turgandek aylantiradi (2D aylanish).
   - Misol: `transform: rotate(45deg);` (soat mili yo'nalishida 45 gradusga aylanadi).
   - Manfiy qiymat ishlatsa soat miliga qarshi aylanadi: `rotate(-90deg)`.

2. **`rotateX(angle)`:** Elementni gorizontal markaziy o'q atrofida aylantiradi (X o'qi). Bunda 3D effekt seziladi.
   - Misol: Element tepaga yoki pastga qarab aylanib orqa tomonini ko'rsatishi mumkin.

3. **`rotateY(angle)`:** Elementni vertikal markaziy o'q atrofida aylantiradi (Y o'qi).
   - Misol: Karta yoki eshikning yon tomonga ochilishi / yopilishi effekti.

### 3D Aylantirish haqida eslatma
`rotateX` va `rotateY` ni ishlatganda, ko'zni chalg'itadigan chiroyli 3D effekt hosil bo'lishi uchun ko'pincha elementning ota (parent) konteyneriga `perspective: 500px;` xususiyatini qo'shish tavsiya qilinadi. Bu aylanishning realistik chuqurlikda bo'lishini ta'minlaydi.
