# 04. CSS Scale (Masshtablash)

`scale` funksiyasi elementning proportsiyalarini kattalashtirish yoki kichraytirish uchun ishlatiladi. `1` qiymati elementning asliga tengligini bildiradi (100%). Undan katta qiymatlar kattalashtiradi, kichik qiymatlar (masalan, `0.5`) kichraytiradi.

### Turlari:
- **`scaleX(n)`:** Faqat gorizontal o'q bo'yicha kattalashtiradi / kichraytiradi.
- **`scaleY(n)`:** Faqat vertikal o'q bo'yicha.
- **`scale(n)` yoki `scale(x, y)`:** Umumiy masshtab. Agar bitta raqam berilsa, ikkala tomon ham bir xil o'zgaradi.

### Misollar:
```css
transform: scale(1.5); /* Asl o'lchamidan 50% ga kattalashadi (1.5 marta) */
transform: scale(0.8); /* Asl o'lchamining 80% gacha kichrayadi */
transform: scale(2, 0.5); /* Kengligi 2 marta kattalashadi, balandligi 2 marta kichrayadi */
```

### Foydalanish
Rasmlarni (image gallery) hover qilinganda chiroyli tarzda kattalashtirish yoki chertilganda pulsatsiya effektlarini berish uchun eng qulay vosita hisoblanadi.
