# 🚀 Optimizasyona Giriş – TAM KAPSAMLI Eğitim ve Referans Reposu

Bu GitHub deposu, **optimizasyon literatüründe yer alan tüm temel ve ileri yöntemleri** tek bir çatı altında toplayan **kapsamlı, sistematik ve eğitsel** bir referans reposudur.

Bu repo bir "örnek kod deposu" değildir. Amaç;

* 📚 öğrencilerin **tek bir README üzerinden tüm optimizasyon evrenine ulaşabilmesi**,
* 🎓 lisans–YL–Doktora seviyesinde **ders materyali** olarak kullanılabilmesi,
* 📊 akademik çalışmalar için **standart deney altyapısı** sunması,
* ⚙️ endüstriyel optimizasyon problemleri için **karar rehberi** olmasıdır.

---

## 🧠 Eğitim ve Tasarım İlkeleri

* **Tek README → tüm yöntemlere erişim**
* Literatüre dayalı **doğru sınıflandırma**
* Basitten karmaşığa pedagojik akış
* Her yöntem için:

  * matematiksel model
  * sezgisel açıklama
  * algoritmik iskelet
  * gerçek problem örneği
  * performans (fitness–süre–enerji)

---

# 🧭 OPTİMİZASYON YÖNTEMLERİ – LİTERATÜR TABANLI TAM TAKSONOMİ

Aşağıdaki yapı, **Operasyon Araştırması (OR)**, **Yapay Zekâ (AI)** ve **Bilgisayar Bilimi** literatürünün ortak kabulüne dayanmaktadır.

---

## 0️⃣ Matematiksel (Kesin / Exact) Optimizasyon Yöntemleri

Bu yöntemler, uygun varsayımlar altında **optimal çözüm garantisi** sunar.

### 0.1 Doğrusal Programlama (LP)

* Simplex Algoritması
* İç Nokta (Interior Point) Algoritması

### 0.2 Tamsayılı Programlama (IP)

* Dal-Sınır (Branch and Bound) Algoritması
* Kesme Düzlemleri (Cutting Planes Algoritmaı

### 0.3 Karma Tamsayılı Programlama (MIP)

* Dal ve kesme (Branch and Cut) Algoritması
* Dal ve Fiyat (Branch and Price) Algoritması

### 0.4 Hedef Programlama (Goal Programming)

* Ağırlıklı hedef programlama
* Öncelikli hedef programlama

### 0.5 Doğrusal Olmayan Programlama (NLP)

* Dışbükey Optimizasyon (Convex optimization)
* Dışbükey olmayan optimizasyon (Non-convex optimization)
* Gradyan / Newton yöntemleri (Gradient / Newton methods)
* KKT koşulları

### 0.6 Dinamik Programlama (DP)

* Bellman prensibi
* Stage-based optimization

**Problemler:** knapsack, shortest path, inventory

---

## 1️⃣ Mantıksal ve Kısıt Tabanlı Yöntemler

### 1.1 Kısıt Programlama (CP)

* Constraint Satisfaction Problems (CSP)
* Global constraints

### 1.2 Mantıksal Programlama

* SAT / Max-SAT
* SMT

### 1.3 Arama ve Greedy-Adaptive Algoritmalar

> Metaheuristic değildir.

* BFS / DFS
* Dijkstra
* A*
* IDA*
* Greedy Best-First Search

---

## 2️⃣ Basit Sezgisel Algoritmalar (Heuristics)

Problem-özel, hızlı, düşük maliyetli yöntemler.

### 2.1 Greedy Yaklaşımlar

* EDD, SPT, LPT

### 2.2 Kural Tabanlı Sezgiseller

* IF–THEN rules
* Priority rules

### 2.3 Local Search

* Hill Climbing
* First / Best Improvement

### 2.4 Yapıcı (Constructive) Sezgiseller

* Problem-özel inşa algoritmaları

---

## 3️⃣ Sezgisel-Üstü (Metaheuristic) Algoritmalar

Genel amaçlı, problem-bağımsız arama çerçeveleri.

### 3.1 Trajectory-Based Metaheuristics

* Simulated Annealing (SA)
* Tabu Search (TS)
* Variable Neighborhood Search (VNS)
* Iterated Local Search (ILS)
* Guided Local Search (GLS)

### 3.2 Memory-Based Metaheuristics

* Tabu Search (advanced)
* Scatter Search

---

## 4️⃣ Popülasyon Temelli Sezgisel-Üstü Algoritmalar

### 4.1 Evrimsel Algoritmalar

* Genetic Algorithms (GA)
* Differential Evolution (DE)
* Evolution Strategies (ES)
* Genetic Programming (GP)

### 4.2 Sürü Zekâsı (Swarm Intelligence)

* Particle Swarm Optimization (PSO)
* Ant Colony Optimization (ACO)
* Artificial Bee Colony (ABC)
* Firefly Algorithm (FA)
* Bat Algorithm

### 4.3 Biyolojik / Fiziksel / Sosyal Metaforlar

**Biyolojik:**

* Immune Algorithms
* Bacterial Foraging

**Fiziksel:**

* Gravitational Search Algorithm
* Harmony Search

**Sosyal:**

* Teaching–Learning Based Optimization (TLBO)
* Social Spider Algorithm

---

## 5️⃣ Üst-Sezgisel (Hyper-Heuristic) Algoritmalar

> Sezgiselleri yöneten üst seviye yöntemler

### 5.1 Heuristic Selection

* Rule-based
* Learning-based

### 5.2 Heuristic Generation

* Genetic Programming HH
* Grammar-based HH

### 5.3 Öğrenme Tabanlı Hyper-Heuristics

* Reinforcement Learning
* Multi-Armed Bandit
* Neural Hyper-Heuristics

---

## ⚙️ Paralel, Dağıtık ve GPU Destekli Optimizasyon

Her algoritma ailesi için:

* Single-thread
* Multi-threading
* Multiprocessing
* GPU (CUDA / OpenCL)

karşılaştırmalı örnekler sunulur.

---

## 📊 Performans ve Deney Standartları

* Fitness
* Süre
* Enerji tüketimi
* Ölçeklenebilirlik

---

## 🎓 Nihai Vizyon

Bu repo:

* Öğrenciler için **tek durak optimizasyon rehberi**
* Akademisyenler için **deney altyapısı**
* Endüstri için **algoritma seçim kılavuzu**

olmayı hedefler.

---

> ✨ *"Optimizasyonu öğrenmek algoritma ezberlemek değil, doğru problemi doğru araçla çözmeyi bilmektir."*
