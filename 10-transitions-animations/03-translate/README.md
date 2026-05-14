# 03. CSS Translate (Siljitish)

`translate` funksiyasi elementni o'zining joriy joylashgan o'rnidan X (gorizontal) yoki Y (vertikal) o'qlari bo'yicha siljitadi. `position: relative` yoki `absolute` orqali siljitishdan farqli ravishda, `translate` bilan siljitish animatsiyalarda silliqroq ishlaydi.

### Turlari va Qo'llanilishi:
1. **`translateX(qiymat)`:** Elementni faqat o'ngga yoki chapga siljitadi.
   - O'ngga: `translateX(50px)`
   - Chapga: `translateX(-50px)`

2. **`translateY(qiymat)`:** Elementni faqat yuqoriga yoki pastga siljitadi.
   - Pastga: `translateY(50px)`
   - Yuqoriga: `translateY(-50px)`

3. **`translate(x, y)`:** Gorizontal va vertikal bo'yicha bir vaqtda siljitish.
   - Misol: `translate(20px, -20px)`

### Amaliy Qo'llanilishi
Eng ko'p qo'llaniladigan holat - foydalanuvchi kartochka yoki tugma ustiga kursor olib borganda uni bir oz yuqoriga ko'tarish:
```css
.card {
  transition: transform 0.3s;
}
.card:hover {
  transform: translateY(-10px); /* 10px yuqoriga siljitish */
}
```
