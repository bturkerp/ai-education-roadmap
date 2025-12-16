🚀 Optimizasyona Giriş – TAM KAPSAMLI Eğitim ve Referans Reposu
Bu repo, optimizasyon teorisinden uygulamalara, klasik kesin yöntemlerden öğrenme temelli modern yaklaşımlara kadar geniş bir spektrumu kapsayan, açık kaynaklı, uygulamaya dönük ve topluca geliştirilebilir bir eğitim ve başvuru kaynağıdır.

Hem akademik araştırmacılar hem de sektörde çalışan mühendisler/veri bilimciler için faydalı olacak şekilde tasarlanmıştır. Her konu, teoriden kodlamaya, örneklemden görselleştirmeye kadar tam döngülü bir şekilde ele alınır.

🗂️ Repo Yapısı
123456789101112131415
optimization-repo/
│
├── 01-Fundamentals/          # Temel kavramlar ve giriş
├── 02-Exact-Methods/         # Kesin çözüm yöntemleri
├── 03-Heuristics/            # Sezgiseller ve üst-sezgiseller
├── 04-Population-Based/      # Popülasyon temelli algoritmalar
├── 05-Learning-Based/        # Makine ve derin öğrenme ile optimizasyon
├── 06-Applications/          # Endüstri, mühendislik ve veri bilimi uygulamaları
│
├── datasets/                 # Test problemleri ve örnek veri setleri

📚 İçerik Kapsamı
🌐 01 – Temel Kavramlar
Optimizasyon nedir? Uygulama alanları
Problem formülasyonu: Amaç fonksiyonu, karar değişkenleri, kısıtlar
Yerel vs. global optimum, konvekslik, olurluluk bölgesi
Optimallik koşulları (1. ve 2. derece şartlar)
🔢 02 – Kesin Çözüm Yöntemleri
Doğrusal Programlama: Simpleks, iç-nokta, dualite, ulaşım/ata ma problemleri
Tamsayılı Programlama: Dal-Sınır, kesme düzlemleri, MIP, 0-1 modeller
Dinamik Programlama: Bellman ilkesi, deterministik/stokastik DP
Hedef Programlama: Ağırlıklı, öncelikli, Chebyshev, leksikografik
Doğrusal Olmayan Programlama: Lagrange, KKT, gradyan tabanlı metotlar
🔍 03 – Sezgisel Algoritmalar
Basit sezgiseller: Açgözlü arama, rastgele arama, yerel arama
Meta-sezgiseller:
Tabu Arama
Tavlama Benzetimi
Değişken Komşuluk Arama
İteratif Yerel Arama
Yönlü Rastgele Arama
👥 04 – Popülasyon Temelli Yöntemler
Evrimsel Algoritmalar:
Genetik Algoritma (GA), Diferansiyel Gelişim, Evrimsel Stratejiler
Sürü Zekası:
PSO, ACO, ABC, Ateşböceği, Kelebek Optimizasyonu
Doğa-esinli diğerleri:
Grey Wolf, Whale, Bat, Cat Swarm Optimizasyonu
🧠 05 – Öğrenme Temelli Yöntemler
Hiperparametre optimizasyonu (Bayes, Optuna, Hyperopt)
Takviyeli öğrenme (RL) ile optimizasyon
Derin öğrenme tabanlı optimizasyon modelleri
Nöro-evrimsel hibrit sistemler
Meta-öğrenme ve otomatik algoritma seçimi
⚙️ 06 – Uygulama Alanları
Endüstri: Üretim çizelgeleme, tedarik zinciri, portföy optimizasyonu
Mühendislik: Yapısal tasarım, robot yolu planlama, enerji sistemleri
Veri Bilimi: Özellik seçimi, kümeleme, anomali tespiti, öneri sistemleri
🛠️ Kullanılan Araçlar ve Kütüphaneler
Kategori
Kütüphaneler / Araçlar
Kesin Yöntemler
PuLP, OR-Tools, SciPy.optimize, CVXOPT, Gurobi*
Sezgiseller
DEAP, pyswarms, scikit-opt, metaheuristic
Makine Öğrenmesi
scikit-learn, Optuna, Hyperopt, BayesianOptimization
Görselleştirme
matplotlib, plotly, networkx, animatplot
Performans Ölçümü
cProfile, line_profiler, time, memory_profiler
* Ticari çözücüler (Gurobi, CPLEX) sadece örnek amaçlı kullanılır; açık alternatifler her zaman önceliklidir.

📖 Öğrenme Yol Haritası
mermaid
Başlangıç

Temel Kavramlar

Doğrusal Programlama

Tamsayılı & Dinamik Programlama

Basit Sezgiseller

Meta-sezgiseller

Popülasyon Temelli Yöntemler

Çok Amaçlı Optimizasyon

Öğrenme Temelli Yöntemler

Hibrit ve Araştırma Konuları

📌 Katkıda Bulunma
Bu repo toplu bilgi birikimine açıktır!

Yeni algoritmalar ekleyebilir,
Mevcut örnekleri geliştirebilir,
Görselleştirme veya performans analizi ekleyebilir,
Uygulama alanlarını genişletebilirsiniz.
Lütfen CONTRIBUTING.md dosyasını inceleyin (henüz yoksa oluşturulacak).

📚 Temel Kaynaklar
Kitaplar
Introduction to Operations Research – Hillier & Lieberman
Linear and Nonlinear Programming – Luenberger & Ye
Metaheuristics: From Design to Implementation – E.-G. Talbi
Evolutionary Computation – Michalewicz & Fogel
Swarm Intelligence – Kennedy & Eberhart
Online Eğitimler
MIT OpenCourseWare – Optimization Methods
Coursera – Discrete Optimization
edX – Optimization: Models and Applications
🎯 Hedef Kitle
Endüstri Mühendisliği, Bilgisayar Mühendisliği, Uygulamalı Matematik öğrencileri
Veri bilimciler ve araştırmacılar
Operasyonel araştırma uzmanları
Yapay zeka ve otomasyon mühendisleri
Akademik tez/ders/proje çalışanlar
📬 İletişim & Destek
Sorularınız, öneri veya hata bildirimleriniz için Issues sekmesini kullanabilirsiniz.
Repo sürekli güncellenmekte ve geliştirilmektedir. Takip etmek için Star ⭐️ vermeyi unutmayın!

🌱 "En iyi çözüm, problemin doğasını anladıktan sonra ortaya çıkar."
— Bu repo, o anlayışı inşa etmenize yardımcı olmak için var.

Hazırlayan: [Adınız / Takım]
Lisans: MIT (açık kaynak kullanımı serbest)

İstersen bu README.md dosyasının İngilizce versiyonunu da hazırlayabilirim veya her alt dizin için örnek README içerikleri üretebilirim. Başlangıç olarak hangi bölümü ilk sıraya almak istersin? (Örneğin: 02-Exact-Methods/01-Linear-Programming/)
