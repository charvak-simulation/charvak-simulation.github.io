# 🌊 Chorvoq Suv Ombori To'g'oni Buzilishi Simulyatsiyasi | Charvak Dam Break Simulation | Моделирование Прорыва Чарвакской Плотины

[![Live Simulation](https://img.shields.io/badge/Live_Demo-Interactive_3D_Simulation-00d084?style=for-the-badge&logo=githubpages&logoColor=white)](https://charvak-simulation.github.io/)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg?style=for-the-badge)](LICENSE)
[![Physics: SERGHEI + LISFLOOD](https://img.shields.io/badge/Solvers-SERGHEI%202D%20SWE%20%26%20LISFLOOD--FP-orange?style=for-the-badge)](https://charvak-simulation.github.io/)

> 🌐 **Interaktiv 3D Simulyatsiyani ko'rish / View Interactive 3D Simulation / Смотреть интерактивную 3D-модель:**  
> 👉 **[https://charvak-simulation.github.io/](https://charvak-simulation.github.io/)**  
> 🌐 **Alohida til sahifalari / Dedicated language pages / Выделенные языковые страницы:**  
> 🇺🇿 **[O'zbekcha 3D (uz.html)](https://charvak-simulation.github.io/uz.html)** | 🇷🇺 **[Русская версия (ru.html)](https://charvak-simulation.github.io/ru.html)** | 🇬🇧 **[English version (en.html)](https://charvak-simulation.github.io/en.html)**  
> 📊 **Barcha texnik va gidrologik ma'lumotlar / Full Technical & Hydrological Data / Полные техданные:**  
> 👉 **[CHARVAK_DATA.md](CHARVAK_DATA.md)**

---

## 📑 Mundarija / Table of Contents / Оглавление
1. [🇺🇿 O'zbekcha: To'liq hisobot va tahlil](#-ozbekcha)
2. [🇷🇺 Русский: Полный отчет и гидродинамический анализ](#-русский)
3. [🇬🇧 English: Full Hydrodynamic Report & Analysis](#-english)
4. [📊 Charvak Technical & Hydrological Reference Data (CHARVAK_DATA.md)](CHARVAK_DATA.md)

---

<a name="-ozbekcha"></a>
## 🇺🇿 O'zbekcha

### Chorvoq suv ombori to'g'oni yorilib ketsa nima bo'ladi?
Ushbu ochiq ilmiy-tadqiqot loyihasi **Chorvoq suv ombori** (Toshkent viloyati, Bo'stonliq tumani) to'g'oni to'liq yorilishi oqibatida yuzaga keladigan gidrodinamik toshqin to'lqinini **2D Shallow Water Equations (Sayoz suv tenglamalari)** yordamida sonli modellashtirish natijalarini taqdim etadi.

Simulyatsiya **Claude Code (Claude Fable 5.1)** yordamida ishlab chiqilgan bo'lib, hisob-kitoblar GPU (NVIDIA CUDA) yadrolarida o'nlab soatlar davomida amalga oshirildi. 

🌐 **Onlayn 3D xaritani ishga tushirish:** [O'zbekcha 3D Simulyatsiya (uz.html)](https://charvak-simulation.github.io/uz.html) yoki [Asosiy sahifa](https://charvak-simulation.github.io/)

---

### 🔬 Texnik va Gidrologik Parametrlar
* **Suv hajmi:** $2.0\text{ km}^3$ (2 milliard kub metr).
* **To'g'on balandligi:** $168\text{ metr}$ (tosh-tuproq to'g'on).
* **Buzilish modeli:** Froehlich (2008) empirik to'g'on yorilishi tenglamasi.
* **Maksimal suv sarfi ($Q_p$):** $\approx 182,013\text{ m}^3/\text{s}$.
* **Yorilish davomiyligi ($t_f$):** $1.6\text{ soat}$.
* **Gidrodinamik algoritmlar:** 
  * **SERGHEI** (Full 2D Shallow Water Equations, GPU-accelerated Roe Riemann upwind solver) – $60\text{ metr}$ qadamli to'r.
  * **LISFLOOD-FP 8.1** (Local-inertial acc solver) – $90\text{ metr}$ qadamli to'r.
* **Relyef ma'lumotlari (DEM):** Copernicus DEM GLO-30 (DSM), FABDEM v1.2 (bare-earth), ALOS World 3D (AW3D30), NASADEM, SRTM GL1.

---

### ⏱️ Toshqin to'lqinining yetib kelish xronologiyasi

| Vaqt | Hudud / Manzil | Kutiladigan holat va suv chuqurligi |
| :--- | :--- | :--- |
| **0 – 15 daqiqa** | **Bochka darasi** (Chorvoq quyisi) | Dastlabki halokatli to'lqin zarbasi. Suv chuqurligi $60\text{--}100+\text{ metr}$ga yetadi. Xo'jakent to'g'oni to'liq yuvib ketiladi. |
| **1 soat** | **G'azalkent shahri** | Suv to'lqini G'azalkentga yetib keladi. Maksimal chuqurlik: $17\text{--}23\text{ metr}$. |
| **2 soat** | **Chirchiq shahri** | To'lqin Chirchiq sanoat hududi va shahar markaziga kiradi. Maksimal chuqurlik: $16\text{--}21\text{ metr}$. Kimyoviy korxonalar xavf ostida qoladi. |
| **2:30 – 3 soat** | **Qibray va Yangibozor** | Chirchiq daryosi vodiysidan toshib, pasttekisliklarni suv bosadi. Yangibozor to'liq suv ostida qoladi. |
| **3:30 – 4 soat** | **Toshkent shahriga kirish (Qo'yliq)** | Suv poytaxtning janubi-sharqiy chekkasiga yetib keladi. Qo'yliq bozor atrofi va Chirchiq daryosi qayiri toshadi. |
| **4:30 – 5 soat** | **Sergeli va Mirobod (pastki qismlar)** | Sergeli, "Index" savdo majmuasi va Mirobodning janubiy pastqamliklari jiddiy zarar ko'radi. |
| **6 – 7 soat** | **Aeroportlar va Mirzo Ulug'bek** | Toshkent Janubiy va Shimoliy (mahalliy) aeroport hududlari suv ostida qoladi. Mirzo Ulug'bek tumanining pastqam qismlariga suv sizib kiradi. |
| **9 – 10 soat** | **Kichik halqa yo'li va Janubiy vokzal** | Suv daryo o'zanidan toshib Kichik halqa yo'ligacha kengayadi. Yakkasaroy tumani qisman suv ostida qoladi, to'lqin Janubiy vokzalga yaqinlashadi. |
| **10:30 – 13 soat**| **Sergeli metrosi va Zangiota** | Suv Sergeli yerusti metro liniyasi tayanchlariga yaqinlashadi. Zangiota hududining pastliklari katta talofat ko'radi. |
| **24 soat** | **Shardara suv ombori (Qozog'iston)** | Toshqin suvlari Chinoz orqali Sirdaryoga, so'ng Shardara suv omboriga borib quyiladi. Agar Shardara to'la bo'lsa, kaskadli yorilish xavfi paydo bo'ladi. |

---

### 🛡️ Nega Toshkent shahar markazi cho'kmaydi? (Mif va Haqiqat)
Ijtimoiy tarmoqlarda tarqalgan *"Chorvoq to'g'oni yorilsa, butun Toshkent 10 daqiqada suv ostida qoladi"* degan mish-mishlar ilmiy jihatdan mutlaqo asossizdir:
1. **Relyef balandligi (Geomorfologik terrassalar):** Toshkent shahri Chirchiq daryosi bo'ylab joylashgan tabiiy qiya terrassalarda barpo etilgan. Yunusobod, Mirzo Ulug'bek qirlari, Shayxontohur va Amir Temur xiyoboni (shahar markazi) Chirchiq daryosi sathidan **20 dan 50 metrgacha balandda** joylashgan.
2. **Gidrodinamik natija:** Simulyatsiya hisob-kitoblariga ko'ra, `Tashkent centre` (shahar markazi) nazorat nuqtasida suv sathi **$0.00\text{ metr}$ni** tashkil qiladi (suv kirmaydi). 
3. **Zarar zonalari:** Toshqin asosan Chirchiq daryosi tabiiy o'zani va unga yondosh pastqam tumanlar (Bektemir, Qo'yliq, Sergeli, Yangihayot, Yakkasaroyning janubi) bilan cheklanadi.

---

<a name="-русский"></a>
## 🇷🇺 Русский

### Что произойдет в случае прорыва плотины Чарвакского водохранилища?
Данный открытый научно-исследовательский проект представляет результаты численного 2D-гидродинамического моделирования катастрофического прорыва **Чарвакской плотины** на реке Чирчик (Бостанлыкский район Ташкентской области) на базе **уравнений мелкой воды (Shallow Water Equations)**.

Интерактивная трехмерная визуализация развернута на GitHub Pages:  
🌐 **Смотреть 3D-модель онлайн:** [Русская версия 3D-модели (ru.html)](https://charvak-simulation.github.io/ru.html) или [Главная страница](https://charvak-simulation.github.io/)

---

### 🔬 Гидрологические и вычислительные параметры
* **Объем водохранилища:** $2.0\text{ км}^3$ (2 миллиарда кубометров).
* **Тип и высота плотины:** Каменно-земляная плотина высотой $168\text{ м}$.
* **Модель образования прорана:** Эмпирическая методика Froehlich (2008), рекомендованная USACE/FEMA.
* **Пиковый расход прорыва ($Q_p$):** $\approx 182,013\text{ м}^3/\text{с}$.
* **Время формирования прорана ($t_f$):** $1.6\text{ часа}$.
* **Вычислительные солверы:**
  * **SERGHEI** (GPU-ускоренный гидродинамический солвер, схема Роэ для уравнений мелкой воды) на сетке $60\text{ м}$.
  * **LISFLOOD-FP 8.1** (Локально-инерционная модель) на сетке $90\text{ м}$.
* **Цифровые модели рельефа (ЦМР / DEM):** Copernicus DEM GLO-30 (DSM), FABDEM v1.2 (без растительности и застройки), AW3D30 (JAXA), NASADEM, SRTM.

---

### ⏱️ Хронология движения волны прорыва

| Время | Локация | Ожидаемые последствия и глубина |
| :--- | :--- | :--- |
| **0 – 15 мин** | **Ущелье Бочка** (ниже плотины) | Формирование мощного прорывного вала. Глубины достигают $60\text{--}100+\text{ м}$. Ходжикентский гидроузел полностью смывается. |
| **1 час** | **г. Газалкент** | Фронт волны достигает Газалкента. Максимальная глубина затопления: $17\text{--}23\text{ м}$. |
| **2 часа** | **г. Чирчик** | Волна накрывает город Чирчик. Глубина потока: $16\text{--}21\text{ м}$. В зоне затопления оказываются жилые кварталы и промышленные химические гиганты. |
| **2.5 – 3 часа** | **Кибрай и Янгибазар** | Выход реки Чирчик из берегов на широкую равнину. Янгибазар оказывается под водой практически полностью. |
| **3.5 – 4 часа** | **Окраины Ташкента (Куйлюк)** | Вода подходит к границе столицы. Затапливаются массивы Куйлюк, пойма Чирчика, мосты и транспортные развязки. |
| **4.5 – 5 часов** | **Сергели и Мирабадский район** | Затопление низменных районов Сергели (включая массив "Index") и южной части Мирабадского района. |
| **6 – 7 часов** | **Район аэропортов и Мирзо-Улугбек** | Подтопление территории международного и местного аэропортов. Частичный перелив в низины Мирзо-Улугбекского района. |
| **9 – 10 часов** | **Малая кольцевая и Южный вокзал** | Вода разливается до Малой кольцевой дороги. Частично подтоплен Яккасарайский район, угроза путям Южного вокзала. |
| **10.5 – 13 часов**| **Сергелийская ветка метро и Зангиата** | Подтопление опор Сергелийской линии надземного метро. Затопление низменностей Зангиатинского района. |
| **24 часа** | **Шардаринское водохранилище (Казахстан)** | Волна прорыва через Чиназ выходит в Сырдарью и доходит до Шардары. При заполненной Шардаре ($5\text{--}7\text{ км}^3$) возникает риск каскадного прорыва. |

---

### 💡 Научное опровержение мифа о «полном затоплении центра Ташкента»
Слухи о том, что *"Ташкент будет смыт за 10–20 минут"*, абсолютно не соответствуют законам гидродинамики:
1. **Время добегания:** Расстояние от Чарвака до Ташкента по руслу составляет более $60\text{ км}$. Волна прорыва движется со скоростью $12\text{--}18\text{ км/ч}$ ($3.5\text{--}5\text{ м/с}$), достигая границы города только через **$3.5\text{--}4\text{ часа}$**.
2. **Топографический барьер:** Ташкент расположен на ступенчатых речных террасах. Центр города (сквер Амира Темура), Юнусабад, Шайхантахур и возвышенности Мирзо-Улугбека находятся на **$20\text{--}50\text{ метров}$ выше уреза реки Чирчик**.
3. В створе `Tashkent centre` расчетная глубина затопления составляет **$0.00\text{ м}$** — центр города остается в полной безопасности от затопления.

---

<a name="-english"></a>
## 🇬🇧 English

### What happens if the Charvak Dam breaches?
This open scientific project provides high-resolution 2D hydrodynamic modeling of a hypothetical catastrophic dam break at the **Charvak Reservoir** (Bostanlyk district, Tashkent region, Uzbekistan) along the Chirchik River basin using **2D Shallow Water Equations (SWE)**.

🌐 **Launch the Interactive 3D WebGL Simulation:** [English 3D Simulation (en.html)](https://charvak-simulation.github.io/en.html) or [Main page](https://charvak-simulation.github.io/)

---

### 🔬 Technical Specification & Numerical Methods
* **Reservoir Volume:** $2.0\text{ km}^3$ ($2.0 \times 10^9\text{ m}^3$).
* **Dam Structure:** Rockfill dam with central earthen core, height $168\text{ m}$, crest elevation $900\text{ m}$.
* **Breach Hydrograph Formulation:** Froehlich (2008) embankment dam failure model.
* **Peak Outflow Discharge ($Q_p$):** $\approx 182,013\text{ m}^3/\text{s}$.
* **Breach Formation Time ($t_f$):** $1.6\text{ hours}$.
* **Numerical Engines:**
  * **SERGHEI** (GPU-accelerated, Roe Riemann upwind finite-volume SWE solver) on a $60\text{ m}$ grid with 5-minute frames.
  * **LISFLOOD-FP 8.1** (Local-inertial formulation) on a $90\text{ m}$ grid with 15-minute frames.
* **Elevation Datasets (DEM):** Copernicus DEM GLO-30 (DSM), Bristol/Fathom FABDEM v1.2 (bare-earth), JAXA ALOS World 3D (AW3D30), NASADEM, NASA SRTM GL1.

---

### ⏱️ Flood Wave Travel Times & Impact Matrix

| Elapsed Time | Location | Hydrodynamic Impact & Inundation Depth |
| :--- | :--- | :--- |
| **0 – 15 min** | **Bochka Gorge** (Immediate downstream) | Initial surge wave peak. Depths exceed $60\text{--}100+\text{ m}$. Khojikent dam is overwhelmed. |
| **1 hour** | **Gazalkent** | Wave front arrives. Maximum inundation depth: $17\text{--}23\text{ m}$. |
| **2 hours** | **Chirchik City** | Main industrial hub flooded. Flow depth: $16\text{--}21\text{ m}$. Severe hazard to chemical production plants. |
| **2.5 – 3 hours** | **Qibray & Yangibozor** | Flood leaves narrow mountain canyon into piedmont alluvial fan. Yangibozor is extensively submerged. |
| **3.5 – 4 hours** | **Tashkent Ingress (Kuyluk / Qo'yliq)** | Flood enters southeastern capital limits. Inundation of the Chirchik river floodplain and Kuyluk market perimeter. |
| **4.5 – 5 hours** | **Sergeli & Mirobod Lowlands** | Substantial inundation across Sergeli, the "Index" logistics park, and low-lying parts of Mirobod. |
| **6 – 7 hours** | **Airport Zones & Mirzo Ulugbek** | Both local and international airports suffer runway and terminal flooding. Fluvial backwater affects low-lying areas. |
| **9 – 10 hours** | **Small Ring Road & South Railway** | Flow expands up to the Small Ring Road boundary. Yakkasaroy district partially inundated; threat to South Railway Station. |
| **10.5 – 13 hours**| **Sergeli Elevated Metro & Zangiota** | Flood reaches elevated metro line pylons and spreads through agricultural lowlands of Zangiota. |
| **24 hours** | **Shardara Reservoir (Kazakhstan)** | Flood wave passes Chinaz into the Syr Darya and enters Shardara. If Shardara is at capacity ($5\text{--}7\text{ km}^3$), risk of catastrophic cascading failure. |

---

### 🧠 Debunking the Urban Legend (Why Central Tashkent Stays Dry)
Popular urban myths frequently claim that a Charvak dam failure would submerge the entirety of Tashkent within 10–20 minutes. The physics-based simulation refutes this:
1. **Wave Velocity Constraints:** Over the $60\text{ km}$ distance, average wave propagation velocity is $3.5\text{--}5\text{ m/s}$ ($12\text{--}18\text{ km/h}$), meaning water takes **$3.5\text{ to }4\text{ hours}$** to reach Tashkent.
2. **Terrace Geomorphology:** Tashkent is built on a succession of elevated Quaternary fluvial terraces. Yunusabad, Shaykhontohur, Mirzo Ulugbek highlands, and the city center (Amir Timur Square) are situated **$20\text{ to }50+\text{ meters}$ above the Chirchik riverbed**.
3. The computational gauge probe at `Tashkent centre` registers **$0.00\text{ m}$ flood depth**. Inundation is physically confined to the southern Chirchik floodplain.

---

## 🔍 Qidiruv Kalit So'zlari va SEO / Ключевые слова и SEO / Keywords
*Qidiruv tizimlari (Google Web Search, YouTube, Yandex) uchun asosiy kalit so'zlar / Основные поисковые запросы:*
* **Google Web Search (O'zbekiston / O'zbekcha):** `Chorvoq suv ombori`, `Chorvoq`, `Chorvoq to'g'oni`, `Chorvoq suv sathi`, `Chorvoq xaritasi`, `Chorvoq toshqini`, `Chorvoq to'g'oni yorilishi`, `Toshkent suv toshqini`, `Bo'stonliq tumani`, `чорвок сув омбори`, `чорвоқ тошқини`.
* **Google Web Search (Узбекистан / Русский):** `Чарвакское водохранилище` (топ-запрос Google Trends), `Чарвак`, `Чарвакская плотина`, `Чарвакская ГЭС`, `уровень воды в Чарваке`, `безопасность Чарвакского водохранилища`, `прорыв плотины Чарвак`, `затопление Ташкента`, `Бостанлыкский район`, `река Чирчик`.
* **English & Research Queries:** `Charvak Reservoir`, `Charvak Lake`, `Charvak Dam failure simulation`, `Charvak dam break`, `Chirchik river flood map`, `Tashkent flood risk`, `Central Asia dam safety`, `SERGHEI 2D shallow water equations`.

---

## 📜 License & Citation
The code and web visualizer are released under the [MIT License](LICENSE).  
Topographic datasets: Copernicus DEM GLO-30 (© ESA/Airbus), FABDEM (© University of Bristol / Fathom), ALOS World 3D (© JAXA).
