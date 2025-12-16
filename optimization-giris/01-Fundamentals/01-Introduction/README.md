# 🌱 Optimizasyona Giriş

> *“En iyi çözüm, problemin doğasını anladıktan sonra ortaya çıkar.”*

Bu belge, **optimizasyonun temel felsefesini**, **tarihsel gelişimini**, **sınıflandırmasını** ve **gerçek dünya etkisini** aktarmayı amaçlar. Algoritmalara geçmeden önce, **neden optimizasyon yaptığımızı** ve **ne tür sorulara yanıt aradığımızı** bilmek esastır.

---

## 🔍 Optimizasyon Nedir?

**Optimizasyon**, belirli **kısıtlar** altında bir **amaç fonksiyonunu** mümkün olan en iyi şekilde gerçekleştiren **karar değişkenlerinin** seçilmesi sürecidir.

### Genel Form:
- **Amaç**: Min veya Max ∑ cᵢ·xᵢ &nbsp;&nbsp; (i = 1…n)  
- **Kısıtlar**: ∑ aᵢⱼ·xⱼ ≤ bᵢ &nbsp;&nbsp; (i = 1…m)  
- **Değişkenler**: xⱼ ∈ ℝ⁺, ℤ⁺ veya {0,1}

> Burada:
> - `xⱼ`: karar değişkenleri  
> - `cᵢ`: amaç katsayıları (maliyet, kar, vs.)  
> - `aᵢⱼ`, `bᵢ`: kısıt katsayıları (kaynak, talep, kapasite)

Optimizasyon, **“en iyi” kararın ne olduğunu sistematik olarak bulma sanatıdır**.

---

## 🕰️ Tarihsel Gelişimi

| Dönem | Gelişme | Öne Çıkan Kişi/Kuram |
|------|--------|---------------------|
| 17.–18. yy | Türev tabanlı optimizasyon | Newton, Leibniz |
| 1788 | Kısıtlı optimizasyon ilkeleri | Lagrange (Lagrange çarpanları) |
| 1939 | Doğrusal programlamanın doğuşu | Leonid Kantorovich |
| 1947 | Simpleks algoritması | George Dantzig |
| 1950’ler | Dinamik programlama | Richard Bellman |
| 1960–80’ler | NLP, KKT koşulları, iç-nokta | Kuhn, Tucker, Fiacco |
| 1990’lar–günümüz | Meta-sezgiseller, öğrenme tabanlı optimizasyon | Kennedy (PSO), Holland (GA), vb. |

> 📌 II. Dünya Savaşı sırasında kaynakların etkin dağıtımı ihtiyacı, **operasyon araştırmasının** ve modern optimizasyonun doğuşunu tetiklemiştir.

---

## 🧩 Optimizasyon Türleri (Sınıflandırma)

Optimizasyon problemleri birden fazla eksen boyunca sınıflandırılır:

| Sınıflandırma Ekseni | Türler |
|----------------------|--------|
| **Değişken Türü** | Sürekli (ℝ), tamsayı (ℤ), ikili ({0,1}), karışık |
| **Amaç Sayısı** | Tek amaçlı, çok amaçlı (Pareto optimallik) |
| **Doğrusallık** | Doğrusal (LP), doğrusal olmayan (NLP), ikinci derece (QP) |
| **Kısıt Durumu** | Kısıtsız, kısıtlı |
| **Belirsizlik** | Deterministik, stokastik, sağlam (robust) |
| **Zaman Yapısı** | Statik, dinamik, çok periyotlu |
| **Çözüm Yaklaşımı** | Kesin (exact), yaklaşık (heuristic), öğrenme tabanlı |

> Örnek: Bir üretim planı → **karışık tamsayılı, çok periyotlu, deterministik, kısıtlı, tek amaçlı LP** olabilir.

---

## 🌍 Gerçek Dünya Uygulamaları

| Sektör | Optimizasyon Problemi | Kullanılan Yöntem |
|--------|----------------------|------------------|
| **Lojistik** | Araç rotalama (VRP) | Meta-sezgiseller, LP |
| **Havacılık** | Uçuş ve mürettebat çizelgeleme | Tamsayılı programlama |
| **Finans** | Portföy optimizasyonu | Doğrusal olmayan programlama, çok amaçlı |
| **Enerji** | Güç üretim dağılımı | Dinamik programlama, NLP |
| **Sağlık** | Radyoterapi hedef yoğunluğu | NLP, konveks optimizasyon |
| **Yapay Zeka** | Sinir ağı eğitimi | Gradyan tabanlı optimizasyon (SGD, Adam) |
| **Perakende** | Stok yönetimi | Dinamik programlama, stokastik optimizasyon |

> Bugün neredeyse **her etkin kaynak kullanımı**, bir optimizasyon problemidir.

---

## 📊 Basit Bir Örnek: En Düşük Maliyetle Ulaşım

**Senaryo**: İki depo (D₁, D₂), üç mağaza (M₁, M₂, M₃).  
Depo kapasiteleri: D₁=100, D₂=150  
Mağaza talepleri: M₁=80, M₂=90, M₃=80  
Birim taşıma maliyetleri (₺):

|       | M₁ | M₂ | M₃ |
|-------|----|----|----|
| **D₁** | 2  | 3  | 1  |
| **D₂** | 5  | 4  | 2  |

### Model:
- **Değişkenler**: `xᵢⱼ` = Dᵢ’den Mⱼ’ye gönderilen ürün miktarı  
- **Amaç**: Min: 2·x₁₁ + 3·x₁₂ + 1·x₁₃ + 5·x₂₁ + 4·x₂₂ + 2·x₂₃  
- **Kısıtlar**:  
  - Arz: x₁₁ + x₁₂ + x₁₃ ≤ 100  
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;x₂₁ + x₂₂ + x₂₃ ≤ 150  
  - Talep: x₁₁ + x₂₁ = 80  
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;x₁₂ + x₂₂ = 90  
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;x₁₃ + x₂₃ = 80  
  - xᵢⱼ ≥ 0

> Bu klasik bir **ulaşım problemi**dir ve **doğrusal programlama** ile çözülür.

---

## 📚 Bu Bölümü Neden Öğrenmeli?

- Optimizasyonu "sihirli kutu" değil, **mantıklı bir karar verme süreci** olarak görürsün.  
- Hangi yöntemin (**kesin mi? sezgisel mi?**) uygun olduğunu anlarsın.  
- Modelleme hatalarını erkenden tespit edebilirsin.

---

## 📖 İleri Okuma

- Hillier & Lieberman, *Introduction to Operations Research* – Bölüm 1–2  
- Boyd & Vandenberghe, *Convex Optimization* – Giriş (ücretsiz PDF: [stanford.edu/~boyd/cvxbook](https://web.stanford.edu/~boyd/cvxbook/))  
- MIT OpenCourseWare: [15.053 Optimization Methods](https://ocw.mit.edu/courses/15-053-optimization-methods-in-management-science-spring-2013/)

---

## ➡️ Sonraki Adım

Gerçek problemleri **matematiksel modele** dönüştürmeyi öğrenmek için:

→ **[Problem Formülasyonu](../02-Problem-Formulation/README.md)**

veya bir çözümün **“en iyi” olmasının ne anlama geldiğini** incelemek için:

→ **[Optimallik Koşulları](../03-Optimality-Conditions/README.md)**
