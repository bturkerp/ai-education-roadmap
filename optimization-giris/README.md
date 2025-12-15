# 🚀 Optimizasyona Giriş – Kapsamlı Eğitim ve Referans Reposu

Bu GitHub deposu, **optimizasyon literatüründe yer alan sezgisel, sezgisel‑üstü (metaheuristic), popülasyon temelli ve üst‑sezgisel (hyper‑heuristic) algoritmaların tamamını** sistematik, eğitsel ve uygulanabilir bir biçimde sunmak amacıyla hazırlanmıştır.

Bu repo bir *uygulama demosu* değil; **ders materyali, akademik referans ve endüstriyel prototip kaynağı** olarak tasarlanmış **yaşayan bir eğitim serisidir**.

> 🎯 **Ana hedef:**
> Optimizasyonu, *"hangi algoritma daha iyi?"* sorusundan önce
> *"hangi problemde, hangi koşulda, hangi algoritma neden çalışır?"* düzeyinde öğretmek.

---

## 📚 Temel Eğitim Felsefesi

Repo boyunca **tek ve değişmeyen bir öğretim şablonu** izlenir:

1. Algoritma ailesinin **literatürdeki konumu**
2. **Sezgisel / algoritmik mantık** (soyut ve sade)
3. **Basit matematiksel fonksiyon optimizasyonu**
4. **Kısıtların eklenmesi**
5. **Gerçek dünya problemleri**
6. **Paralel (CPU) ve GPU destekli uygulamalar**
7. **Fitness – süre – enerji tüketimi** karşılaştırmaları

Eğitim akışı **daima basitten karmaşığa** ilerler.

---

## 🧭 Algoritma Sınıflandırması (Literatür Tabanlı)

Aşağıda repo kapsamında ele alınacak **tüm ana algoritma sınıfları**, literatürde kabul gören biçimiyle sunulmuştur.

---

## 1️⃣ Basit Sezgisel Algoritmalar (Heuristics)

Bu algoritmalar, genellikle **problem‑özel**, **hızlı** ve **düşük hesaplama maliyetli** çözümler üretir. Optimal garanti yoktur; amaç *makul çözüm*dür.

### 1.1 Greedy Yaklaşımlar

* En iyi görünen adımı anlık olarak seçer
* Global optimum garanti edilmez
* Çok hızlıdır

**Örnekler:**

* Greedy knapsack
* Earliest Due Date (EDD)
* Shortest Processing Time (SPT)

🔗 Detaylar: `01_basic_heuristics/greedy/`

---

### 1.2 Kural Tabanlı Sezgiseller

* Önceden tanımlanmış karar kuralları
* İnsan uzman bilgisini yansıtır

**Örnekler:**

* IF–THEN çizelgeleme kuralları
* Öncelik kuralı tabanlı atamalar

🔗 Detaylar: `01_basic_heuristics/rule_based/`

---

### 1.3 Local Search Türevleri

* Tek çözüm üzerinden komşuluk araması
* Yerel iyileştirme odaklıdır

**Alt türler:**

* Hill Climbing
* Steepest Descent
* First Improvement

🔗 Detaylar: `01_basic_heuristics/local_search/`

---

### 1.4 Problem‑Özel Yapıcı Sezgiseller

* Belirli bir problem için tasarlanır
* Yüksek problem bilgisi içerir

**Örnekler:**

* VRP için yapıcı rotalama sezgiselleri
* Çizelgeleme için sıralama sezgiselleri

🔗 Detaylar: `01_basic_heuristics/constructive/`

---

## 2️⃣ Sezgisel‑Üstü Algoritmalar (Metaheuristics)

Metaheuristics, **genel amaçlı**, **problem‑bağımsız** arama stratejileridir. Temel hedef, **yerel minimumlardan kaçabilmektir**.

### 2.1 Trajectory‑Based Metaheuristics

> ❗ Hayır, sadece SA–TS–VNS değildir.

**Tanım:**

* Tek çözüm üzerinde ilerler
* Arama uzayında bir "yörünge" izler

**Alt Türler ve Örnekler:**

* Simulated Annealing (SA)
* Tabu Search (TS)
* Variable Neighborhood Search (VNS)
* Iterated Local Search (ILS)
* Guided Local Search (GLS)

🔗 Detaylar: `02_metaheuristics/trajectory_based/`

---

### 2.2 Memory‑Based Metaheuristics

* Geçmiş çözümleri kullanır
* Uzun / kısa dönem hafıza içerir

**Örnekler:**

* Tabu Search (ileri seviye varyantlar)
* Scatter Search

---

## 3️⃣ Popülasyon Temelli Sezgisel‑Üstü Algoritmalar

Bu algoritmalar **tek çözüm yerine çözüm popülasyonu** ile çalışır.

> ❗ Hayır, sadece GA ve PSO değildir.

---

### 3.1 Evrimsel Algoritmalar

**Alt Türler:**

* Genetic Algorithms (GA)
* Differential Evolution (DE)
* Evolution Strategies (ES)
* Genetic Programming (GP)

**Temel Bileşenler:**

* Seçilim
* Çaprazlama
* Mutasyon

🔗 Detaylar: `03_population_based/evolutionary/`

---

### 3.2 Sürü Zekâsı (Swarm Intelligence)

**Örnekler:**

* Particle Swarm Optimization (PSO)
* Ant Colony Optimization (ACO)
* Artificial Bee Colony (ABC)
* Firefly Algorithm (FA)
* Bat Algorithm

🔗 Detaylar: `03_population_based/swarm/`

---

### 3.3 Biyolojik, Fiziksel ve Sosyal Metafor Tabanlı Algoritmalar

Bu grup, doğa ve sosyal sistemlerden ilham alan geniş bir aileyi kapsar.

**Biyolojik:**

* Immune Algorithms
* Bacterial Foraging

**Fiziksel:**

* Gravitational Search Algorithm
* Simulated Annealing (fizik kökenli)

**Sosyal:**

* Teaching–Learning Based Optimization (TLBO)
* Social Spider Algorithm

🔗 Detaylar: `03_population_based/metaphor_based/`

---

## 4️⃣ Üst‑Sezgisel (Hyper‑Heuristic) Algoritmalar

Hyper‑heuristics, **"sezgiseller üzerinde çalışan sezgiseller"**dir.

### 4.1 Sezgisel Seçimi (Heuristic Selection)

* Hangi sezgisel ne zaman seçilmeli?
* Online / offline yaklaşımlar

**Örnekler:**

* Rule‑based hyper‑heuristics
* Learning‑based selection

---

### 4.2 Sezgisel Üretimi (Heuristic Generation)

* Yeni sezgiseller üretir

**Örnekler:**

* Genetic Programming tabanlı HH
* Grammar‑based HH

---

### 4.3 Öğrenme Tabanlı Hyper‑Heuristics

* Reinforcement Learning
* Multi‑armed bandit
* Neural hyper‑heuristics

🔗 Detaylar: `04_hyper_heuristics/`

---

## ⚙️ Paralel ve GPU Destekli Uygulamalar

Her algoritma için:

* Single‑thread (referans)
* Multi‑threading
* Multiprocessing
* GPU destekli sürümler

karşılaştırmalı olarak sunulur.

---

## 📊 Performans Ölçütleri

* Fitness
* Süre
* Enerji tüketimi
* Ölçeklenebilirlik

---

## 🎓 Nihai Amaç

Bu repo sonunda:

* Akademik derslerde kullanılabilir
* Q1 dergi deney altyapısı sunan
* Endüstriyel problemlere uyarlanabilir
* Literatürdeki algoritmaları **tek çatı altında toplayan**

**referans bir optimizasyon deposu** oluşturulması hedeflenmektedir.

---

> ✨ *"Algoritmayı yazmak değil, doğru yerde kullanmak ustalıktır."*
