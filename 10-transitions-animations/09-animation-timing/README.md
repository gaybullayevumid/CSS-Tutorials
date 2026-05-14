# 09. Animation Timing (Vaqt Funksiyalari)

`animation-timing-function` xususiyati (xuddi transitiondagi kabi) animatsiyaning tezlashish va sekinlashish dinamikasini belgilaydi. Animatsiya davomida tezlik o'zgarmas qoladimi yoki boshida sekin keyin tezlashadimi - buni shu funksiya orqali nazorat qilasiz.

### Eng ko'p ishlatiladigan qiymatlar:
1. **`ease` (Default):** Animatsiya sekin boshlanadi, o'rtada tezlashadi va oxirida yana sekinlashadi. Eng tabiiy ko'rinadigan harakat turi.
2. **`linear`:** Boshidan oxirigacha bir xil doimiy tezlikda davom etadi. (Odatda yuklanuvchi aylanadigan spinnerlar uchun ishlatiladi).
3. **`ease-in`:** Animatsiya juda sekin boshlanadi va keyin tezlashib ketadi.
4. **`ease-out`:** Animatsiya tez boshlanadi va oxirida sekinlashadi.
5. **`ease-in-out`:** `ease` ga o'xshaydi, lekin sekinlashish/tezlashish yana ham yaqqolroq namoyon bo'ladi.
6. **`steps(n)`:** Silliq animatsiya o'rniga, kadrni `n` ta aniq bosqichlarga bo'lib sakratib o'tkazadi (Eski pikselli o'yinlardagi yoki soat milidek effektlarni qilish uchun qulay).
7. **`cubic-bezier(n,n,n,n)`:** Custom funksiya tuzish. Agar tayyorlari yoqmasa o'z tezlik grafigingizni tuzishingiz mumkin. Buni brauzerning inspect tool ida vizual tahrirlash juda oson.

### Qo'llanilishi
Ushbu papkadagi `index.html` faylini ochib, barcha funksiyalarning vizual poygasini va qanday farq qilishini o'z ko'zingiz bilan ko'rishingiz mumkin!
