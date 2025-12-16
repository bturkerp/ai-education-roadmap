# 🧩 Problem Formülasyonu

> *“Bir problemi doğru formüle edebilmek, çözümün yarısıdır.”*

Optimizasyon sadece algoritmalarla değil, **doğru modellemeyle** kazanılır. Bu bölümde, bir optimizasyon problemini oluşturan temel bileşenleri öğrenip, basit örnekler üzerinden **matematiksel modele** nasıl dönüştüreceğimizi adım adım inceleyeceğiz.

---

## 🧱 Temel Bileşenler

Her optimizasyon problemi üç temel öğeden oluşur:

### 1. **Karar Değişkenleri (Decision Variables)**
- Problemin çözümünü tanımlayan bilinmeyenlerdir.  
- Örnekler:  
  - \( x_i \): \( i \). ürünün üretilecek miktarı  
  - \( y_j \): \( j \). tedarikçinin seçili olup olmadığı (0/1)  
  - \( t_{ij} \): \( i \)’den \( j \)’ye gitme süresi

> Karar değişkenleri, çözüm uzayını tanımlar.

---

### 2. **Amaç Fonksiyonu (Objective Function)**
- Optimize edilmek istenen niceliktir: **minimize** (maliyet, zaman) ya da **maksimize** (kar, verimlilik).  
- Örnekler:  
  - **Min**: \( \sum_{i=1}^n c_i x_i \) → Toplam üretim maliyeti  
  - **Max**: \( \sum_{j=1}^m p_j y_j \) → Toplam kar

> Amaç fonksiyonu, çözümün “kalitesini” ölçer.

---

### 3. **Kısıtlar (Constraints)**
- Karar değişkenlerine getirilen mantıksal, fiziksel veya kaynak sınırlarını ifade eder.  
- Türleri:  
  - **Eşitsizlik kısıtları**: \( \sum a_i x_i \leq b \) (kaynak tüketimi ≤ mevcut)  
  - **Eşitlik kısıtları**: \( \sum x_i = 1 \) (tam olarak bir seçenek seçilmeli)  
  - **Değişken sınırları**: \( x_i \geq 0 \), \( y_j \in \{0,1\} \)

> Kısıtlar, çözümün **uygulanabilir (feasible)** olmasını sağlar.

---

## 📐 Matematiksel Model Örneği: Çanta (Knapsack) Problemi

**Senaryo**: Sınırlı kapasiteli bir çantaya, her birinin ağırlığı ve değeri bilinen eşyalar konulacak. Amacımız çantadaki **toplam değeri maksimize** etmek.

### Karar Değişkenleri
\[
x_i = 
\begin{cases}
1, & \text{eğer } i\text{. eşya çantaya konursa} \\
0, & \text{aksi takdirde}
\end{cases}
\]

### Amaç Fonksiyonu
\[
\max \sum_{i=1}^{n} v_i x_i
\]
- \( v_i \): \( i \). eşyanın değeri

### Kısıtlar
\[
\sum_{i=1}^{n} w_i x_i \leq W
\]
- \( w_i \): \( i \). eşyanın ağırlığı  
- \( W \): Çantanın maksimum kapasitesi

### Değişken Türü
\[
x_i \in \{0,1\}, \quad \forall i
\]

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
| **Ulaşım Problemi** | \( x_{ij} \): Fabrikadan mağazaya gönderilen ürün | Maliyeti min. et | Arz = Talep, miktar ≥ 0 |
| **İş Çizelgeleme** | \( x_{jt} = 1 \): İş \( j \), zaman \( t \)’de başlasın | Gecikmeyi min. et | Her iş bir kez çalışsın |
| **Portföy Seçimi** | \( w_i \): Varlık \( i \)’ye yatırılan oran | Getiriyi max., riski min. | \( \sum w_i = 1 \), \( w_i \geq 0 \) |

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
