🎯 Optimizasyona Giriş - Tam Kapsamlı Eğitim ve Referans Reposu
https://img.shields.io/github/stars/username/optimization-repo?style=social
https://img.shields.io/github/forks/username/optimization-repo?style=social
https://img.shields.io/badge/License-MIT-yellow.svg
https://img.shields.io/badge/contributions-welcome-brightgreen.svg

📖 Hakkında
Bu repo, optimizasyon teorisinin temellerinden başlayarak ileri seviye modern optimizasyon tekniklerine kadar tüm konuları kapsayan kapsamlı bir eğitim ve referans kaynağıdır. Hem akademik hem de endüstriyel uygulamalar için hazırlanmıştır.

🎯 Hedef Kitle:

Üniversite öğrencileri (lisans/yüksek lisans)

Veri bilimcileri ve makine öğrenmesi mühendisleri

Operasyon araştırmacıları

Yazılım geliştiriciler

Araştırmacılar ve akademisyenler

🏗️ Repo Yapısı
text
optimization-repo/
├── 📚 01-Fundamentals/          # Temel kavramlar ve giriş
├── 🔢 02-Exact-Methods/         # Kesin çözüm yöntemleri
├── 🔍 03-Heuristics/           # Sezgisel algoritmalar
├── 👥 04-Population-Based/     # Popülasyon temelli yöntemler
├── 🧠 05-Learning-Based/       # Öğrenme temelli yöntemler
├── ⚙️ 06-Applications/        # Uygulama alanları
├── 📊 datasets/                # Örnek veri setleri
├── 📓 notebooks/               # Jupyter notebook'ları
├── 💻 src/                     # Kaynak kodları
├── 📝 exercises/               # Alıştırmalar ve çözümler
├── 📚 references/              # Kaynaklar ve makaleler
└── 📄 README.md                # Bu dosya
📑 İçindekiler
1. 📚 Temel Kavramlar - Dosyalara Git
1.1 Optimizasyona Giriş

1.2 Problem Formülasyonu

1.3 Optimallik Koşulları

2. 🔢 Kesin Çözüm Yöntemleri - Dosyalara Git
2.1 Doğrusal Programlama (LP)

Simpleks Algoritması

İç Nokta Metotları

Dualite Teorisi

Duyarlılık Analizi

2.2 Tamsayılı Programlama (IP)

Dal-Sınır Metodu

Kesme Düzlemi Metodu

0-1 Programlama

2.3 Dinamik Programlama (DP)

Bellman Optimalite Prensibi

Deterministik DP

Stokastik DP

2.4 Hedef Programlama (GP)

Ağırlıklı Hedef Programlama

Öncelikli Hedef Programlama

2.5 Doğrusal Olmayan Programlama (NLP)

KKT Koşulları

Gradyan Tabanlı Metotlar

Kısıtsız Optimizasyon

3. 🔍 Sezgisel Algoritmalar - Dosyalara Git
3.1 Basit Sezgiseller

Açgözlü Algoritmalar

Yerel Arama

Rastgele Arama

3.2 Sezgisel Üstü Algoritmalar

Tabu Arama

Tavlama Benzetimi

Değişken Komşuluk Arama

3.3 İleri Sezgisel Yöntemler

Hyper-Heuristics

Memetic Algoritmalar

4. 👥 Popülasyon Temelli Yöntemler - Dosyalara Git
4.1 Evrimsel Algoritmalar

Genetik Algoritmalar

Diferansiyel Gelişim

Evrimsel Stratejiler

4.2 Sürü Zekası Algoritmaları

Parçacık Sürü Optimizasyonu

Karınca Kolonisi Optimizasyonu

Yapay Arı Kolonisi

4.3 Biyolojik Esinli Algoritmalar

Kurt Sürüsü Optimizasyonu

Balina Optimizasyon Algoritması

5. 🧠 Öğrenme Temelli Yöntemler - Dosyalara Git
5.1 Optimizasyon için ML

Bayesian Optimizasyon

Hiperparametre Optimizasyonu

5.2 Derin Öğrenme ile Optimizasyon

Nöro-Evrimsel Algoritmalar

Derin RL Optimizasyonu

6. ⚙️ Uygulama Alanları - Dosyalara Git
6.1 Endüstriyel Uygulamalar

Üretim Planlama

Tedarik Zinciri Optimizasyonu

6.2 Mühendislik Uygulamaları

Yapısal Optimizasyon

Robot Yolu Planlama

6.3 Veri Bilimi Uygulamaları

Özellik Seçimi

Kümeleme Optimizasyonu

🚀 Hızlı Başlangıç
Ön Koşullar
bash
# Gerekli Python paketlerini yükleyin
pip install numpy scipy matplotlib pandas
pip install pulp ortools scikit-learn
pip install deap pyswarms
İlk Örnek: Doğrusal Programlama
python
from pulp import LpProblem, LpVariable, LpMaximize

# Problem tanımı
prob = LpProblem("Simple_LP_Problem", LpMaximize)

# Karar değişkenleri
x = LpVariable("x", lowBound=0)
y = LpVariable("y", lowBound=0)

# Amaç fonksiyonu
prob += 3*x + 5*y

# Kısıtlar
prob += x + 2*y <= 10
prob += 3*x + y <= 12

# Çöz
prob.solve()
print(f"Optimal değer: {prob.objective.value()}")
print(f"x = {x.value()}, y = {y.value()}")
📊 Öğrenme Yol Haritası
Seviye	Konular	Tahmini Süre
Başlangıç	Temel kavramlar, Doğrusal Programlama, Basit sezgiseller	2-4 hafta
Orta	Tamsayılı Programlama, Dinamik Programlama, Meta-sezgiseller	4-6 hafta
İleri	Popülasyon temelli yöntemler, Çok amaçlı optimizasyon	6-8 hafta
Uzman	Öğrenme temelli yöntemler, Hybrid algoritmalar	8+ hafta
💻 Kod Örnekleri ve Uygulamalar
Her bölümde aşağıdaki içerikler bulunur:

Teori ve Matematiksel Temeller

Algoritma Adımları

Python/MATLAB/R Implementasyonları

Örnek Problemler ve Çözümler

Görselleştirmeler

Performans Analizleri

Alıştırmalar ve Çözümler

🤝 Katkıda Bulunma
Bu proje açık kaynaklıdır ve katkılara açıktır. Katkıda bulunmak için:

Repoyu fork edin

Yeni bir branch oluşturun (git checkout -b feature/AmazingFeature)

Değişikliklerinizi commit edin (git commit -m 'Add some AmazingFeature')

Branch'inizi push edin (git push origin feature/AmazingFeature)

Pull Request oluşturun

Katkı Kuralları
Kod yazarken PEP 8 standartlarına uyun

Her yeni algoritma için testler yazın

Dokümantasyonu güncel tutun

Örneklerin çalıştığından emin olun

📚 Kaynaklar ve Referanslar
Temel Kitaplar
Hillier & Lieberman - "Introduction to Operations Research"

Luenberger & Ye - "Linear and Nonlinear Programming"

Talbi - "Metaheuristics: From Design to Implementation"

Online Kaynaklar
MIT OpenCourseWare - Optimization Methods

Coursera - Discrete Optimization

edX - Optimization: Models and Applications

Yararlı Kütüphaneler
python
# Optimizasyon için:
- PuLP, OR-Tools, CVXOPT, SciPy
- DEAP, pyswarms, scikit-opt
- scikit-learn, Optuna, Hyperopt

# Görselleştirme için:
- matplotlib, seaborn, plotly
- networkx (ağ problemleri için)
🏆 Proje Hedefleri
Tüm temel optimizasyon yöntemlerini kapsamak

Her algoritma için çalışan kod örnekleri sağlamak

Gerçek hayat problemleri için uygulamalar geliştirmek

Performans karşılaştırmaları yapmak

Türkçe dokümantasyon hazırlamak

Topluluk katılımını artırmak

📞 İletişim ve Destek
Sorularınız için: GitHub Issues sayfasını kullanın

Önerileriniz: Pull Request veya Issue olarak gönderin

E-posta: your-email@example.com

📄 Lisans
Bu proje MIT lisansı altında lisanslanmıştır. Detaylar için LICENSE dosyasına bakın.

🙏 Teşekkürler
Bu projeye katkıda bulunan tüm geliştiricilere ve optimizasyon alanında çalışan araştırmacılara teşekkür ederiz.

⭐ Bu repoyu beğendiyseniz yıldız vermeyi unutmayın!

"Optimizasyon, sınırlı kaynaklarla maksimum fayda sağlama sanatıdır."

Son Güncelleme: Kasım 2023
Versiyon: 1.0.0
