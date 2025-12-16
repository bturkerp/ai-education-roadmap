# 🎯 Optimallik Koşulları

> *“Bir çözümün iyi olduğunu iddia edebilmek için, ‘iyi’nin ne anlama geldiğini bilmek gerekir.”*

Bu belge, bir çözümün **yerel optimum**, **global optimum** veya **uygunsuz (infeasible)** olup olmadığını nasıl anlayacağınızı öğretir. Optimizasyon algoritmaları bu koşulları hedefler; modelleyiciler ise bu kavramları kullanarak çözüm kalitesini değerlendirir.

---

## 🔍 Temel Kavramlar

### 1. **Uygun (Feasible) Çözüm**
- Tüm **kısıtları** sağlayan çözüm.  
- Örnek: `x₁ = 10`, `x₂ = 5` → Eğer `2·x₁ + x₂ ≤ 25` ise **uygun**tur.

### 2. **Yerel (Local) Optimum**
- Çözümün **komşuluğunda** daha iyi bir çözüm yoktur.  
- Ancak **global en iyi** olmayabilir.

### 3. **Global Optimum**
- **Tüm uygun çözümler arasında** en iyi olanıdır.  
- Kesin çözüm yöntemleri bunu garanti eder; sezgiseller yakınsamayı hedefler.

### 4. **Konvekslik ve Optimallik**
- Eğer **amaç fonksiyonu konveks** ve **kısıt bölgesi konveks** ise:  
  → **Her yerel optimum, global optimumdur.**  
- Bu, doğrusal programlamanın gücüdür.

---

## 📉 Kısıtsız Optimallik Koşulları

Kısıt olmayan durumlarda, optimallik **türevlerle** belirlenir.

### Tek Değişkenli Fonksiyon: `f(x)`
- **Gerekli Koşul**:  
  `f′(x*) = 0` → Durağan (stationary) nokta  
- **Yeterli Koşul**:  
  `f″(x*) > 0` → Yerel minimum  
  `f″(x*) < 0` → Yerel maksimum

### Çok Değişkenli Fonksiyon: `f(x₁, x₂, …, xₙ)`
- **Gradyan (∇f)**: Tüm kısmi türevlerden oluşan vektör  
  `∇f(x) = [∂f/∂x₁, ∂f/∂x₂, …, ∂f/∂xₙ]ᵀ`
- **Gerekli Koşul**:  
  `∇f(x*) = 0`
- **Yeterli Koşul**:  
  Hessian matrisi `H(x*)` **pozitif tanımlı** ise → yerel minimum  
  (`H ≽ 0` yeterli değil; `H ≻ 0` gerekli)

> 💡 **Hessian**: İkinci türevlerin oluşturduğu kare matris. Konveksliği test eder.

---

## ⚖️ Kısıtlı Optimallik: Lagrange ve KKT

### 1. **Eşitlik Kısıtlı Durum** – Lagrange Çarpanları

Problem:  
Min `f(x)`  
s.t. `hⱼ(x) = 0`, &nbsp; j = 1…p

**Lagrangian**:  
`ℒ(x, λ) = f(x) + ∑ λⱼ·hⱼ(x)`

**Optimallik Koşulu**:  
`∇ₓℒ = 0` ve `hⱼ(x) = 0`

> λⱼ: Lagrange çarpanı — “kısıtın gölge fiyatı” olarak yorumlanabilir.

#### Örnek:  
Min `f(x₁,x₂) = x₁² + x₂²`  
s.t. `x₁ + x₂ = 4`

→ Lagrangian: `ℒ = x₁² + x₂² + λ·(4 − x₁ − x₂)`  
→ Türevler alınır, çözülür → `x₁ = x₂ = 2`

---

### 2. **Eşitsizlik Kısıtlı Durum** – Karush-Kuhn-Tucker (KKT) Koşulları

Problem:  
Min `f(x)`  
s.t.  
`gᵢ(x) ≤ 0`, &nbsp; i = 1…m  
`hⱼ(x) = 0`, &nbsp; j = 1…p

**KKT Koşulları** (düzgünlik sağlanırsa gerekli ve yeterlidir):

1. **Durağanlık**:  
   `∇f(x*) + ∑ μᵢ·∇gᵢ(x*) + ∑ λⱼ·∇hⱼ(x*) = 0`
2. **Primal Uygunluk**:  
   `gᵢ(x*) ≤ 0`, &nbsp; `hⱼ(x*) = 0`
3. **Dual Uygunluk**:  
   `μᵢ ≥ 0`
4. **Tamamlayıcı Gevşeklik (Complementary Slackness)**:  
   `μᵢ·gᵢ(x*) = 0` &nbsp; → Her kısıt ya **aktif** (`gᵢ = 0`, μᵢ > 0) ya da **pasif** (`gᵢ < 0`, μᵢ = 0)

> 🔑 Tamamlayıcı gevşeklik, **aktif kısıtların** çözümü nasıl şekillendirdiğini açıklar.

---

## 🌐 Basit Sayısal Örnek: Kısıtlı Minimizasyon

**Problem**:  
Min: `f(x) = (x₁ − 1)² + (x₂ − 1)²`  
s.t.: `x₁ + x₂ ≤ 1`  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`x₁ ≥ 0`, `x₂ ≥ 0`

- Amaç: (1,1) noktasına en yakın uygun noktayı bul.
- Uygun bölge: `x₁ + x₂ ≤ 1` üçgeni.

**Çözüm**:  
En yakın nokta, sınırda → `x₁ + x₂ = 1`  
Simetriye göre: `x₁ = x₂ = 0.5`

**KKT Doğrulaması**:  
- `g(x) = x₁ + x₂ − 1 ≤ 0` → aktif (`g = 0`)  
- `μ ≥ 0`, `μ·g = 0` → μ serbest  
- Gradyan: `∇f = [2(x₁−1), 2(x₂−1)] = [−1, −1]`  
- `∇g = [1, 1]`  
- Durağanlık: `[−1, −1] + μ·[1, 1] = 0` → μ = 1 ≥ 0 ✅

→ KKT sağlanır → **optimal çözüm**.

---

## 📊 Konvekslik: Neden Bu Kadar Önemli?

| Özellik | Konveks Problem | Genel (Non-konveks) Problem |
|--------|------------------|----------------------------|
| **Yerel optimum** | Her zaman global optimumdur | Yerel optimumlar yanıltıcı olabilir |
| **Çözüm garantisi** | Evet (Simpleks, iç-nokta) | Hayır (algoritmalar lokal minimumda takılabilir) |
| **KKT koşulları** | Gerekli ve yeterli | Sadece gerekli (bazen yetersiz) |

> 📌 **Doğrusal programlama (LP)** her zaman konvekstir → bu yüzden güçlü ve güvenilirdir.

---

## ❌ Yaygın Yanılgılar

- **“Türev sıfır = en iyi çözüm”** → Hayır, eyer noktası da olabilir.  
- **“Kısıt sağlanıyor = çözüm iyi”** → Uygun olabilir, ama optimal değil.  
- **“Sezgisel iyi sonuç verdi = global optimum”** → Yanıltıcı olabilir; çoklu başlangıç gerekli.

---

## 📚 İleri Okuma

- Boyd & Vandenberghe, *Convex Optimization* – Bölüm 4 ve 5  
- Luenberger & Ye, *Linear and Nonlinear Programming* – KKT bölümü  
- MIT OCW: [Nonlinear Programming](https://ocw.mit.edu/courses/15-084j-nonlinear-programming-spring-2004/)

---

## ➡️ Sonraki Adım

Artık temel kavramlara hakimsiniz. Şimdi ilk **kesin çözüm yöntemini** öğrenme zamanı:

→ **[Doğrusal Programlama](../../02-Exact-Methods/01-Linear-Programming/README.md)**

veya sezgisellere atlamak isterseniz:

→ **[Basit Sezgiseller](../../03-Heuristics/01-Simple-Heuristics/README.md)**
