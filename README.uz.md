# 🌊 Chorvoq Suv Ombori To'g'oni Buzilishi Simulyatsiyasi

<p align="center">
  <strong>🌐 O'qish tili:</strong>
  <a href="README.uz.md"><strong>O'zbekcha</strong></a> |
  <a href="README.ru.md"><strong>Русский</strong></a> |
  <a href="README.md"><strong>English</strong></a>
</p>

[![Live Simulation](https://img.shields.io/badge/Live_Demo-Interaktiv_3D_Simulyatsiya-00d084?style=for-the-badge&logo=githubpages&logoColor=white)](https://charvak-simulation.github.io/)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg?style=for-the-badge)](LICENSE)
[![Physics: SERGHEI + LISFLOOD](https://img.shields.io/badge/Solvers-SERGHEI%202D%20SWE%20%26%20LISFLOOD--FP-orange?style=for-the-badge)](https://charvak-simulation.github.io/)

> 🌐 **Interaktiv 3D Simulyatsiyani ishga tushirish:**  
> 👉 **[https://charvak-simulation.github.io/](https://charvak-simulation.github.io/)**  
> 📊 **Barcha texnik va gidrologik ma'lumotlar:**  
> 👉 **[CHARVAK_DATA.md](CHARVAK_DATA.md)**

---

## Chorvoq suv ombori to'g'oni yorilib ketsa nima bo'ladi?
Ushbu ochiq ilmiy-tadqiqot loyihasi **Chorvoq suv ombori** (Toshkent viloyati, Bo'stonliq tumani) to'g'oni to'liq yorilishi oqibatida yuzaga keladigan gidrodinamik toshqin to'lqinini **2D Shallow Water Equations (Sayoz suv tenglamalari)** yordamida sonli modellashtirish natijalarini taqdim etadi.

Simulyatsiya hisob-kitoblari GPU (NVIDIA CUDA) tezlatgichlarida o'nlab soatlar davomida amalga oshirildi va to'g'ondan to Qozog'istondagi Shardara suv omborigacha bo'lgan masofada toshqin harakatini qamrab oladi.

---

## 🔬 Texnik va Gidrologik Parametrlar
* **Suv hajmi:** 2.0 km³ (2 milliard kub metr).
* **To'g'on balandligi:** 168 metr (tosh-tuproqli to'g'on), to'g'on tepasi mutlaq balandligi 900 metr.
* **Buzilish modeli:** Froehlich (2008) empirik to'g'on yorilishi tenglamasi.
* **Maksimal suv sarfi (Qp):** taxminan 182 013 m³/s.
* **Yorilish davomiyligi (tf):** 1.6 soat.
* **Gidrodinamik algoritmlar:** 
  * **SERGHEI** (Full 2D Shallow Water Equations, GPU Roe Riemann yechuvchisi) – 60 metr to'r qadami.
  * **LISFLOOD-FP 8.1** (Local-inertial acc solver) – 90 metr to'r qadami.
* **Relyef ma'lumotlari (DEM):** Copernicus DEM GLO-30 (DSM), FABDEM v1.2 (er yuzasi), ALOS World 3D (AW3D30), NASADEM, SRTM GL1.

---

## ⏱️ Toshqin to'lqinining yetib kelish xronologiyasi

| Vaqt | Hudud / Manzil | Kutiladigan holat va suv chuqurligi |
| :--- | :--- | :--- |
| **0 – 15 daqiqa** | **Bochka darasi** (Chorvoq quyisi) | Dastlabki halokatli to'lqin zarbasi. Suv chuqurligi 60–100+ metrga yetadi. Xo'jakent to'g'oni to'liq yuvib ketiladi. |
| **1 soat** | **G'azalkent shahri** | Suv to'lqini G'azalkentga yetib keladi. Maksimal chuqurlik: 17–23 metr. |
| **2 soat** | **Chirchiq shahri** | To'lqin Chirchiq sanoat hududi va shahar markaziga kiradi. Maksimal chuqurlik: 16–21 metr. Kimyoviy korxonalar xavf ostida qoladi. |
| **2:30 – 3 soat** | **Qibray va Yangibozor** | Chirchiq daryosi vodiysidan toshib, pasttekisliklarni suv bosadi. Yangibozor to'liq suv ostida qoladi. |
| **3:30 – 4 soat** | **Toshkent shahriga kirish (Qo'yliq)** | Suv poytaxtning janubi-sharqiy chekkasiga yetib keladi. Qo'yliq bozor atrofi va Chirchiq daryosi qayiri toshadi. |
| **4:30 – 5 soat** | **Sergeli va Mirobod (pastki qismlar)** | Sergeli, "Index" savdo majmuasi va Mirobodning janubiy pastqamliklari jiddiy zarar ko'radi. |
| **6 – 7 soat** | **Aeroportlar va Mirzo Ulug'bek** | Toshkent Janubiy va Shimoliy (mahalliy) aeroport hududlari suv ostida qoladi. Mirzo Ulug'bek tumanining pastqam qismlariga suv sizib kiradi. |
| **9 – 10 soat** | **Kichik halqa yo'li va Janubiy vokzal** | Suv daryo o'zanidan toshib Kichik halqa yo'ligacha kengayadi. Yakkasaroy tumani qisman suv ostida qoladi, to'lqin Janubiy vokzalga yaqinlashadi. |
| **10:30 – 13 soat**| **Sergeli metrosi va Zangiota** | Suv Sergeli yerusti metro liniyasi tayanchlariga yaqinlashadi. Zangiota hududining pastliklari katta talofat ko'radi. |
| **24 soat** | **Shardara suv ombori (Qozog'iston)** | Toshqin suvlari Chinoz orqali Sirdaryoga, so'ng Shardara suv omboriga borib quyiladi. Agar Shardara to'la bo'lsa, kaskadli yorilish xavfi paydo bo'ladi. |

---

## 🛡️ Nega Toshkent shahar markazi cho'kmaydi? (Mif va Haqiqat)
Ijtimoiy tarmoqlarda tarqalgan *"Chorvoq to'g'oni yorilsa, butun Toshkent 10 daqiqada suv ostida qoladi"* degan mish-mishlar ilmiy jihatdan mutlaqo asossizdir:
1. **Relyef balandligi (Geomorfologik terrassalar):** Toshkent shahri Chirchiq daryosi bo'ylab joylashgan tabiiy qiya terrassalarda barpo etilgan. Yunusobod, Mirzo Ulug'bek qirlari, Shayxontohur va Amir Temur xiyoboni (shahar markazi) Chirchiq daryosi sathidan **20 dan 50 metrgacha balandda** joylashgan.
2. **Gidrodinamik natija:** Simulyatsiya hisob-kitoblariga ko'ra, Toshkent shahar markazida hisoblangan suv sathi **0 metrni** tashkil qiladi (suv kirmaydi). 
3. **Zarar zonalari:** Toshqin asosan Chirchiq daryosi tabiiy o'zani va unga yondosh pastqam tumanlar (Bektemir, Qo'yliq, Sergeli, Yangihayot, Yakkasaroyning janubi) bilan cheklanadi.

---

## ❓ Ko'p beriladigan savollar (FAQ)

### Chorvoq to'g'oni yorilsa Toshkent shahrini butunlay suv bosadimi?
**Yo'q.** Shahar markazi (Amir Temur xiyoboni) va shimoliy tumanlar daryo o'zanidan **20–50 metr balandlikdagi** terrasalarda joylashgan. Toshkent shahar markazida hisoblangan suv chuqurligi **0 metr** (suv kirmaydi). Toshqin faqat Chirchiq daryosi qayiri va janubiy pastqam hududlar (Bektemir, Qo'yliq, Sergeli) bilan cheklanadi.

### To'lqin Toshkentga qancha vaqtda yetib keladi?
**3.5 – 4 soatda.** Daryo bo'ylab masofa 60 km dan ortiq, to'lqin tezligi 12–18 km/soat (3.5–5 m/s). 10–20 daqiqada Toshkentni yuvib ketishi haqidagi gaplar fizik jihatdan imkonsizdir.

### Aholi punktlariga to'lqin yetib kelish xronologiyasi qanday?
* **Bochka darasi:** 0–15 daqiqa (chuqurlik 60–100+ m)
* **G'azalkent:** 1 soat (17–23 m)
* **Chirchiq shahri:** 2 soat (16–21 m)
* **Yangibozor:** 2.5–3 soat
* **Toshkent chegarasi (Qo'yliq):** 3.5–4 soat
* **Sergeli:** 4.5–5 soat
* **Chinoz:** 18 soat
* **Shardara suv ombori (Qozog'iston):** 24 soat

### Qanday gidrodinamik modellar va hisob-kitob parametrlari ishlatilgan?
2D Shallow Water tenglamalari **SERGHEI** (60 m to'r, GPU Roe Riemann yechuvchisi) va **LISFLOOD-FP 8.1** (90 m to'r) orqali yechilgan. To'g'on buzilishi **Froehlich (2008)** empirik formulasi orqali modellashtirilgan: eng yuqori suv sarfi Qp ≈ 182 013 m³/s, o'pirilish vaqti tf = 1.6 soat, to'liq hajm 2.0 km³, to'g'on balandligi 168 m. Relyef ma'lumotlari: Copernicus DEM GLO-30 va FABDEM.

---

## 📜 Litsenziya
Kod va veb-vizualizator [MIT litsenziyasi](LICENSE) ostida tarqatiladi.  
Relyef ma'lumotlari: Copernicus DEM GLO-30 (© ESA/Airbus), FABDEM (© University of Bristol / Fathom), ALOS World 3D (© JAXA).
