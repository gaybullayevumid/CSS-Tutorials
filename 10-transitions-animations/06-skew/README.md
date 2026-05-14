# 06. CSS Skew (Qiyshaytirish)

`skew` xususiyati 2D tekislikda elementlarni qiyshaytirish (og'dirish) uchun ishlatiladi. U dizaynga dinamiklik yoki qandaydir 3D ga o'xshash qiyalik qo'shishda yordam beradi. 

### Turlari:
1. **`skewX(angle)`:** Elementni X (gorizontal) o'qi bo'ylab qiyshaytiradi.
   - Misol: `transform: skewX(20deg);` (Yon tomonga og'diradi).
2. **`skewY(angle)`:** Elementni Y (vertikal) o'qi bo'ylab qiyshaytiradi.
   - Misol: `transform: skewY(15deg);` (Yuqoriga yoki pastga qarab og'diradi).
3. **`skew(x-angle, y-angle)`:** Ikkala yo'nalish bo'yicha bir vaqtda og'diradi.
   - Agar ikkinchi qiymat berilmasa, default `0deg` bo'ladi.

### Nima uchun kerak?
Bu ko'pincha parallelograms (romb) shakllar yasashda yoki fondagi qiziqarli geometrik bloklarni shakllantirishda juda keng qo'llaniladi.
