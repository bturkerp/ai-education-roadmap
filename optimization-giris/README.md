# 🚀 Optimizasyona Giriş – Eğitim Serisi

Bu GitHub deposu, **optimizasyon alanına sistematik, katmanlı ve uygulamalı bir giriş**
sunmak amacıyla hazırlanmış bir **eğitim serisidir**.

Amaç; kullanıcıyı **matematiksel optimizasyondan** başlayarak  
**sezgisel**, **sezgisel-üstü (metaheuristic)**,  
**popülasyon temelli sezgisel-üstü** ve  
**üst-sezgisel (hyper-heuristic)** algoritmalara kadar  
**basitten karmaşığa** doğru ilerleyen bir öğrenme yolculuğuna çıkarmaktır.

> 🎯 **Temel ilke:**  
> Her yöntem önce *en sade haliyle* öğretilir, ardından gerçek dünya problemleri,
> paralel hesaplama, GPU hızlandırma ve performans analizi ile derinleştirilir.

---

## 📚 Eğitim Felsefesi

Bu repo bir kod arşivi değil, **öğreten bir yapı**dır.

- 🔹 Teori + sezgisel açıklama + kod birlikte verilir
- 🔹 Eğitim akışı **basitten karmaşığa** ilerler
- 🔹 Aynı problem farklı algoritmalarla çözülerek **karşılaştırmalı öğrenme** sağlanır
- 🔹 Performans sadece çözüm kalitesiyle değil:
  - **Fitness (amaç fonksiyonu değeri)**
  - **Çalışma süresi (CPU / GPU)**
  - **Enerji tüketimi (Joule / mWh)**
  metrikleriyle değerlendirilir

---

## 🧭 Repo Kapsamı ve Yol Haritası

### 1️⃣ Matematiksel Optimizasyon Yöntemleri

Optimizasyonun **teorik ve matematiksel temeli**.

**Kapsam**
- Doğrusal Programlama (LP)
- Tamsayılı Programlama (IP)
- Karma Tamsayılı Programlama (MIP)
- Kısıtlı / kısıtsız optimizasyon

**Yaklaşım**
1. Basit matematiksel fonksiyonların optimizasyonu
2. Lineer ve lineer olmayan kısıtlar
3. Gerçek problemler:
   - Üretim planlama
   - Temel çizelgeleme örnekleri

---

### 2️⃣ Basit Sezgisel (Heuristic) Yöntemler

\"Optimal\" yerine **hızlı ve kabul edilebilir** çözümler.

**Örnekler**
- Greedy algoritmalar
- Local Search
- Hill Climbing
- Nearest Neighbor

**Problemler**
- Fonksiyon optimizasyonu
- Basit araç rotalama
- Kural tabanlı çizelgeleme

---

### 3️⃣ Sezgisel-Üstü (Metaheuristic) Algoritmalar

Yerel minimumlardan kaçabilen **gelişmiş arama stratejileri**.

**Algoritmalar**
- Simulated Annealing (SA)
- Tabu Search (TS)
- Variable Neighborhood Search (VNS)

**Eğitim Akışı**
1. Soyut algoritmik model
2. Basit fonksiyon optimizasyonu
3. Gerçek problemler:
   - Job / Flow Shop Scheduling
   - Hemşire çizelgeleme

---

### 4️⃣ Popülasyon Temelli Sezgisel-Üstü Algoritmalar

**Tek çözüm yerine çözüm popülasyonu** yaklaşımı.

**Algoritmalar**
- Genetik Algoritmalar (GA)
- Parçacık Sürü Optimizasyonu (PSO)
- Diferansiyel Evrim (DE)
- Karınca Kolonisi Optimizasyonu (ACO)

**Problemler**
- Araç Rotalama Problemi (VRP)
- Üretim ve bakım çizelgeleme
- Kombinatoryal optimizasyon

---

### 5️⃣ Üst-Sezgisel (Hyper-Heuristic) Algoritmalar

> “Hangi sezgiseli, ne zaman, nasıl kullanmalıyım?”

**Kapsam**
- Sezgisel seçimi
- Sezgisel üretimi
- Online / Offline hyper-heuristic yaklaşımlar

**Amaç**
- Algoritma tasarım yükünü azaltmak
- Genelleştirilebilir optimizasyon çerçeveleri geliştirmek

---

## ⚙️ Paralel Hesaplama ve Hızlandırma

Sezgisel-üstü ve üst-sezgisel yöntemler için:

### 🔹 CPU
- Single-thread (referans)
- Multi-threading
- Multiprocessing

### 🔹 GPU
- GPU destekli temel modeller
- GPU + multiprocessing
- CPU vs GPU karşılaştırmaları

Her yapı için:
- Fitness
- Süre
- Enerji tüketimi
ölçülür ve raporlanır.

---

## 📊 Performans Değerlendirme Kriterleri

- 📈 En iyi / ortalama fitness
- ⏱️ Toplam süre & iterasyon süresi
- 🔋 Enerji tüketimi
- ⚖️ Algoritmalar arası karşılaştırma tabloları

---

## 🗂️ Önerilen Klasör Yapısı

```text
optimization-series/
│
├── 01_mathematical_optimization/
├── 02_basic_heuristics/
├── 03_metaheuristics/
├── 04_population_based/
├── 05_hyper_heuristics/
│
├── benchmarks/
├── experiments/
├── utils/
└── README.md

