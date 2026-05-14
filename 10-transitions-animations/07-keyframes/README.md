# 07. CSS @keyframes

Faqatgina qandaydir harakatga (masalan hover) javob qaytarish emas, balki elementni ma'lum bir ketma-ketlik bo'yicha avtomatik o'zgarishga majbur qilish uchun `@keyframes` qoidasidan foydalanamiz. Bu murakkab va bosqichma-bosqich animatsiyalarni yaratishning yagona yo'lidir.

### Sintaksis
Keyframelarni nomlash orqali yangi animatsiya qonuniyati yaratamiz. 

**1. `from` va `to` orqali (Boshlanish va Tugash):**
```css
@keyframes slideIn {
  from { transform: translateX(-100%); }
  to { transform: translateX(0); }
}
```

**2. Foizlar orqali (Murakkab animatsiyalar):**
Foizlar yordamida animatsiyaning qayerida nima sodir bo'lishini juda aniq nazorat qila olasiz. `0%` bu boshlanishi, `100%` bu oxiri.
```css
@keyframes pulse {
  0% { transform: scale(1); }
  50% { transform: scale(1.2); background-color: #e74c3c; }
  100% { transform: scale(1); }
}
```

Ushbu qoidani yaratgandan so'ng, u avtomatik ishlamaydi, uni keyingi darsdagi `animation` xususiyati yordamida elementga bog'lash kerak bo'ladi.
