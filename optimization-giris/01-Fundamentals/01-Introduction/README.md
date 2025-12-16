# 🧩 Problem Formülasyonu

> *“Bir problemi doğru formüle edebilmek, çözümün yarısıdır.”*

Optimizasyon sadece algoritmalarla değil, **doğru modellemeyle** kazanılır. Bu bölümde, bir optimizasyon problemini oluşturan temel bileşenleri öğrenip, basit örnekler üzerinden **matematiksel modele** nasıl dönüştüreceğimizi adım adım inceleyeceğiz.

---

## 🧱 Temel Bileşenler

Her optimizasyon problemi üç temel öğeden oluşur:

### 1. **Karar Değişkenleri (Decision Variables)**
- Problemin çözümünü tanımlayan bilinmeyenlerdir.  
- Örnekler:  
  - `xᵢ`: `i`. ürünün üretilecek miktarı  
  - `yⱼ`: `j`. tedarikçinin seçili olup olmadığı (0/1)  
  - `tᵢⱼ`: `i`’den `j`’ye gitme süresi

> Karar değişkenleri, çözüm uzayını tanımlar.

---

### 2. **Amaç Fonksiyonu (Objective Function)**
- Optimize edilmek istenen niceliktir: **minimize** (maliyet, zaman) ya da **maksimize** (kar, verimlilik).  
- Örnekler:  
  - **Min:** ∑ cᵢ·xᵢ &nbsp;&nbsp; (i = 1…n) → Toplam üretim maliyeti  
  - **Max:** ∑ pⱼ·yⱼ &nbsp;&nbsp; (j = 1…m) → Toplam kar

> Amaç fonksiyonu, çözümün “kalitesini” ölçer.

---

### 3. **Kısıtlar (Constraints)**
- Karar değişkenlerine getirilen mantıksal, fiziksel veya kaynak sınırlarını ifade eder.  
- Türleri:  
  - **Eşitsizlik kısıtları**: ∑ aᵢ·xᵢ ≤ b &nbsp;&nbsp; (kaynak tüketimi ≤ mevcut)  
  - **Eşitlik kısıtları**: ∑ xᵢ = 1 &nbsp;&nbsp; (tam olarak bir seçenek seçilmeli)  
  - **Değişken sınırları**: xᵢ ≥ 0, &nbsp; yⱼ ∈ {0,1}

> Kısıtlar, çözümün **uygulanabilir (feasible)** olmasını sağlar.

---

## 📐 Matematiksel Model Örneği: Çanta (Knapsack) Problemi

**Senaryo**: Sınırlı kapasiteli bir çantaya, her birinin ağırlığı ve değeri bilinen eşyalar konulacak. Amacımız çantadaki **toplam değeri maksimize** etmek.

### Karar Değişkenleri
xᵢ = 1 → i. eşya çantaya konur
xᵢ = 0 → i. eşya konmaz

### Amaç Fonksiyonu
**Max:** ∑ vᵢ·xᵢ &nbsp;&nbsp; (i = 1…n)  
- `vᵢ`: `i`. eşyanın değeri

### Kısıtlar
∑ wᵢ·xᵢ ≤ W  
- `wᵢ`: `i`. eşyanın ağırlığı  
- `W`: Çantanın maksimum kapasitesi

### Değişken Türü
xᵢ ∈ {0,1}, &nbsp;&nbsp; ∀ i

> Bu bir **0-1 tamsayılı programlama** problemidir.

---

## 🏗️ Problem Formüle Etme Adımları

1. **Problemi anla**: Gerçek amacı ve sınırları belirle.  
2. **Karar değişkenlerini tanımla**: “Ne karar vereceğim?”  
3. **Amaç fonksiyonunu yaz**: “Ne optimize etmek istiyorum?”  
4. **Kısıtları listele**: “Neler yapılabilir, neler yapılamaz?”  
5. **Matematiksel modeli kur**: Yukarıdakileri sembolik olarak ifade et.  
6. **Doğrula**: Uç durumlar (extreme cases) için mantıklı mı?

---

## 🌐 Diğer Klasik Örnekler

| Problem | Karar Değişkeni | Amaç | Kısıt |
|--------|------------------|------|-------|
| **Ulaşım Problemi** | `xᵢⱼ`: Fabrikadan mağazaya gönderilen ürün | **Min:** ∑ cᵢⱼ·xᵢⱼ | ∑ⱼ xᵢⱼ ≤ arzᵢ, &nbsp; ∑ᵢ xᵢⱼ ≥ talepⱼ |
| **İş Çizelgeleme** | `xⱼₜ = 1`: İş `j`, zaman `t`’de başlasın | **Min:** toplam gecikme | Her iş tam 1 kez atanmalı |
| **Portföy Seçimi** | `wᵢ`: Varlık `i`’ye yatırılan oran | **Max:** getiri, **Min:** risk | ∑ wᵢ = 1, &nbsp; wᵢ ≥ 0 |

---

## 💡 Yaygın Hatalar

- **Amaçla kısıtı karıştırmak**: “Maliyet düşük olmalı” → kısıt mı, amaç mı?  
- **Gereksiz değişken tanımlamak**: Modeli gereksiz yere karmaşıklaştırır.  
- **Gerçekçi olmayan kısıtlar**: Örn. “üretim sonsuz hızlı” varsayımı.  
- **Birim uyumsuzluğu**: kg ile tonu aynı denklemde kullanmak.

---

## 📚 İleri Okuma

- Winston, *Operations Research: Applications and Algorithms* – Bölüm 3  
- Taha, *Operations Research: An Introduction* – Modelleme bölümü  
- OR-Tools Dokümantasyonu: [Google Optimization Tools](https://developers.google.com/optimization)

---

## ➡️ Sonraki Adım

Bir çözümün **ne zaman “en iyi” olduğunu** anlamak için:

→ **[Optimallik Koşulları](../03-Optimality-Conditions/README.md)**

veya doğrudan kesin çözüm yöntemlerine geçmek için:

→ **[Doğrusal Programlama](../../02-Exact-Methods/01-Linear-Programming/README.md)**
