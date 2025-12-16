# 🌐 Temel Kavramlar (Fundamentals)

Bu bölüm, optimizasyonun **temel taşlarını** tanıtmayı amaçlar. Herhangi bir optimizasyon tekniğini anlamlı şekilde kullanabilmek için öncelikle:

- Optimizasyonun ne olduğu ve hangi alanlarda kullanıldığı,  
- Bir problemin nasıl **matematiksel olarak formüle edildiği**,  
- ve bir çözümün **"iyi" olmasının ne anlama geldiği** (optimallik koşulları)

kavranmalıdır.

Bu bölümdeki içerikler, ileri düzey tüm yöntemlerin ortak dili niteliğindedir.

---

## 📂 İçerikler

### [1. Optimizasyona Giriş (Introduction)](01-Optimization-Introduction/README.md)
- Optimizasyon nedir?  
- Tarihsel gelişimi (Newton’dan Simpleks’e)  
- Uygulama alanlarına genel bakış:  
  - Lojistik & üretim  
  - Finans & portföy yönetimi  
  - Yapay zeka & veri bilimi  
- Optimizasyon tiplerine genel sınıflandırma:  
  - Sürekli vs. ayrık  
  - Tek amaçlı vs. çok amaçlı  
  - Deterministik vs. stokastik

---

### [2. Problem Formülasyonu (Problem Formulation)](02-Problem-Formulation/README.md)
- Karar değişkenleri (decision variables)  
- Amaç fonksiyonu (objective function)  
- Kısıtlar (constraints): eşitlik ve eşitsizlik  
- Olurlu bölge (feasible region)  
- Örnek problem formülasyonları:  
  - Beslenme problemi  
  - Çanta (knapsack) problemi  
  - En kısa yol problemi

> 💡 *“Doğru problemi çözmek, problemi doğru çözmekten daha önemlidir.”*

---

### [3. Optimallik Koşulları (Optimality Conditions)](03-Optimality-Conditions/README.md)
- Yerel optimum vs. global optimum  
- Konvekslik ve optimallik ilişkisi  
- Gerekli ve yeterli optimallik koşulları  
  - Tek değişkenli: \( f'(x) = 0 \), \( f''(x) > 0 \)  
  - Çok değişkenli: gradyan, Hessian  
- Kısıtsız optimallik  
- Kısıtlı optimallik: Lagrange çarpanları (önsel giriş)

---

## 📚 Bu Bölümü Neden Öğrenmeli?

- Optimizasyon algoritmalarını **anlamsız sihirli kutular** olarak değil, **mantıklı araçlar** olarak kullanabilirsiniz.  
- Modelleme hatalarını erkenden tespit edebilir,  
- Uygun yöntemi (kesin mi? sezgisel mi?) doğru seçebilirsiniz.

---

## 📖 Sonraki Adım

Temel kavramlar net olduğunda, ilk teknik derinliğe inmeye başlayabilirsiniz:

➡️ **[02 – Kesin Çözüm Yöntemleri](../02-Exact-Methods/README.md)**

veya doğrudan ilgi alanınıza göre:

➡️ **[03 – Sezgisel Algoritmalar](../03-Heuristics/README.md)**

---

> 🧭 *Her büyük çözüm, küçük bir karar değişkeniyle başlar.*
