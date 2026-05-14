# 02. CSS Transform

`transform` xususiyati elementning qolipiga (layout) ta'sir qilmagan holda uning joylashuvini, shaklini, burilishini va o'lchamini o'zgartirish imkonini beradi. Ushbu yondashuv brauzer uchun grafik kartadan foydalanganligi sababli ancha yuqori tezlikda (performance-friendly) ishlaydi.

### Asosiy tushunchalar:
- **Transform Turlari:** `translate` (siljitish), `scale` (masshtablash), `rotate` (aylantirish), `skew` (qiyshaytirish).
- **Transform Kombinatsiyasi:** Bitta elementda bir nechta transformlarni ishlatish uchun ularni faqatgina bo'shliq (probel) bilan ajratish kerak:
  ```css
  .element {
    transform: translateX(50px) rotate(45deg) scale(1.2);
  }
  ```
  *(Izoh: Transformlar ketma-ketlikda bajariladi, ya'ni oldin siljiydi, so'ng aylanadi va hokazo)*

### Transform Origin
Elementlarning o'zgarish (aylanish yoki kattalashish) markazini belgilaydi. Standart holatda u o'zgarishni markazdan (`50% 50%` yoki `center`) amalga oshiradi. 
Uni burchaklarga yopishgan qilib o'zgartirish mumkin:
```css
.element {
  transform-origin: top left; /* O'zgarish markazi yuqori chap burchak */
}
```
