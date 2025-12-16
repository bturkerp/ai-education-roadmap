# 🔢 Kesin Çözüm Yöntemleri (Exact Methods)

> *“Bazen en iyi yaklaşım, kesin cevabı bulmaktır.”*

Bu bölüm, **optimal çözümü garanti eden** matematiksel yöntemleri kapsar. “Kesin” (exact) ifadesi, bu yöntemlerin **her zaman küresel optimumu** bulduğunu — tahmini veya yaklaşık sonuç olmadığını — vurgular.

Kesin yöntemler, problem boyutu küçük veya orta ölçekliyse tercih edilir. Büyük ve karmaşık problemlerde ise **hesaplama maliyeti** artabilir; bu durumda sezgisellere yönelinir.

---

## 📂 İçerikler

### [1. Doğrusal Programlama (Linear Programming)](01-Linear-Programming/README.md)
- Amaç ve kısıtlar doğrusal olduğunda kullanılan en güçlü araç  
- Simpleks algoritması ve iç-nokta yöntemleri  
- Dualite teorisi ve duyarlılık analizi  
- Uygulamalar: üretim planlama, ulaştırma, finans

### [2. Tamsayılı Programlama (Integer Programming)](02-Integer-Programming/README.md)
- Karar değişkenlerinin tamsayı olması gerektiği durumlar  
- Dal-Sınır (Branch and Bound)  
- Kesme düzlemi (Cutting Plane)  
- Karışık Tamsayılı Programlama (MIP)  
- 0-1 programlama ve modelleme püf noktaları

### [3. Dinamik Programlama (Dynamic Programming)](03-Dynamic-Programming/README.md)
- Çok aşamalı karar problemleri için  
- Bellman optimalite ilkesi  
- İleriye ve geriye dönük hesaplama  
- Deterministik ve stokastik DP örnekleri

### [4. Hedef Programlama (Goal Programming)](04-Goal-Programming/README.md)
- Birden fazla hedefin aynı anda karşılanması  
- Ağırlıklı, öncelikli ve Chebyshev yaklaşımları  
- Lexicographic (hiyerarşik) hedef optimizasyonu

### [5. Doğrusal Olmayan Programlama (Nonlinear Programming)](05-Nonlinear-Programming/README.md)
- Amaç veya kısıtlardan en az biri doğrusal değilse  
- Kısıtsız optimizasyon: gradyan tabanlı yöntemler  
- Kısıtlı optimizasyon: Lagrange çarpanları, KKT koşulları  
- Konveks optimizasyon ve karesel programlama (QP)

---

## 🧠 Ne Zaman Kesin Yöntem Kullanılır?

| Kriter | Kesin Yöntem Uygun mudur? |
|-------|----------------------------|
| Problem boyutu | Küçük/orta (değişken sayısı < 10⁴–10⁵) |
| Optimal çözüm gerekli mi? | Evet (örneğin: finansal kararlar, güvenlik sistemleri) |
| Problem konveks mi? | Evet → kesin çözüm hızlı ve güvenilir |
| Gerçek zamanlı mı? | Hayır → çözüm süresi kritik değilse |
| Veri kesin mi? | Evet → stokastiklik yoksa |

> ⚠️ Büyük ölçekli, yüksek boyutlu veya gerçek zamanlı sistemlerde kesin yöntemler **hesaplamalı olarak pahalı** olabilir.

---

## 🛠️ Yaygın Kullanılan Araçlar

| Kütüphane | Açıklama |
|----------|--------|
| **PuLP** | Python tabanlı, doğrusal ve tamsayılı programlama için |
| **OR-Tools** | Google tarafından geliştirilen güçlü açık kaynak optimizasyon kiti |
| **SciPy.optimize** | Basit LP ve NLP problemleri için |
| **CVXPY** | Konveks optimizasyon modelleri için yüksek seviye arayüz |
| **Gurobi / CPLEX** | Ticari çözücüler (akademik kullanım ücretsiz) — yüksek performans |

> 💡 Bu repo, **açık kaynak araçlarla** (`PuLP`, `OR-Tools`) örnekler sunar.

---

## 📚 Bu Bölümü Neden Öğrenmeli?

- Gerçek dünya problemlerinin çoğu **ilk olarak kesin modellerle** incelenir.  
- Sezgisel algoritmaların başarısı, **kesin çözümlerle karşılaştırılarak** ölçülür.  
- Modelleme yeteneğiniz, doğrusal ve tamsayılı programlama ile gelişir.

---

## 📖 Öğrenme Önerisi

1. Önce **Doğrusal Programlama** → temel dil ve sezgiyi inşa eder  
2. Sonra **Tamsayılı Programlama** → gerçekçi karar modelleri  
3. Ardından **Dinamik Programlama** → çok aşamalı karar süreçleri  
4. En son **Doğrusal Olmayan Programlama** → karmaşık, gerçekçi ama zorlu modeller

---

## ➡️ Sonraki Adım

En temel ve yaygın kullanılan kesin yöntemi öğrenmek için:

→ **[Doğrusal Programlama](01-Linear-Programming/README.md)**

veya doğrudan ilgi alanına göre:

→ **[Tamsayılı Programlama](02-Integer-Programming/README.md)**
