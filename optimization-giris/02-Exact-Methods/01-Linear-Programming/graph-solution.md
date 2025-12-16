# 📊 Grafik Çözüm Yöntemi

Grafik çözüm, **iki karar değişkenli** doğrusal programlama problemlerini **geometrik olarak** çözmek için kullanılan sezgisel ve öğretici bir yöntemdir. Üç veya daha fazla değişkenli problemlerde görselleştirme mümkün olmadığı için bu yöntem yalnızca **eğitim ve anlama amacıyla** kullanılır.

---

## 🧠 Yöntem Adımları

1. **Kısıtları eşitsizlikten eşitliğe çevirerek doğruları çiz**  
2. **Her kısıtın uygun tarafını belirle** (deneme noktası: genelde (0,0))  
3. **Tüm kısıtların kesişimiyle uygun bölgeyi (feasible region) oluştur**  
4. **Amaç fonksiyonunu sabit bir değerle çiz (izoprofit/izocost doğrusu)**  
5. **Bu doğrusunu kaydırarak uygun bölge üzerinde en iyi değeri bul**  
6. **Optimum genellikle bir köşe noktasındadır**

> 🔑 Teorem: Eğer bir DP probleminin **küresel optimumu varsa**, o optimum **uygun bölgenin en az bir köşe noktasında** bulunur.

---

## 📚 Örnek 1: Üretim Karı Maksimizasyonu

**Problem**:  
Max: `Z = 40·x₁ + 30·x₂`  
s.t.:  
`2·x₁ + x₂ ≤ 100` &nbsp;&nbsp; (işçilik)  
`x₁ + 3·x₂ ≤ 90` &nbsp;&nbsp;&nbsp;&nbsp; (malzeme)  
`x₁, x₂ ≥ 0`

### Adım 1: Kısıt doğrularını çiz
- `2x₁ + x₂ = 100` → (0,100) ve (50,0) noktalarından geçer  
- `x₁ + 3x₂ = 90` → (0,30) ve (90,0) noktalarından geçer

### Adım 2: Uygun bölgeyi belirle
- Her iki kısıt da “≤” olduğundan, orijine (0,0) doğru olan taraf alınır  
- Eksenlerde `x₁ ≥ 0`, `x₂ ≥ 0` → 1. çeyrek düzlem

### Adım 3: Köşe noktalarını bul
Kesişim noktaları:
1. `(0, 0)`  
2. `(0, 30)` → Malzeme kısıtı ile y ekseni  
3. `(50, 0)` → İşçilik kısıtı ile x ekseni  
4. **Kesişim noktası**:  
   `2x₁ + x₂ = 100`  
   `x₁ + 3x₂ = 90`  
   → Çözüm: `x₁ = 42`, `x₂ = 16`

### Adım 4: Amaç fonksiyonunu köşelerde değerlendir
| Nokta | Z = 40·x₁ + 30·x₂ |
|-------|-------------------|
| (0, 0) | 0 |
| (0, 30) | 900 |
| (50, 0) | 2000 |
| **(42, 16)** | **40·42 + 30·16 = 1680 + 480 = 2160** ✅

### Sonuç:
- **Küresel optimum**: `(x₁, x₂) = (42, 16)`  
- **Maksimum kar**: **2160 ₺**

> 📌 Bu nokta, iki kısıtın **kesiştiği yerde** → her iki kaynak tamamen kullanılır.

---

## 📚 Örnek 2: Minimizasyon – Diyet Problemi

**Problem**:  
Min: `Z = 2·x₁ + 5·x₂`  
s.t.:  
`200·x₁ + 150·x₂ ≥ 2000` &nbsp;&nbsp; (kalori)  
`5·x₁ + 12·x₂ ≥ 50` &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; (protein)  
`x₁, x₂ ≥ 0`

### Adım 1: Doğrular
- `200x₁ + 150x₂ = 2000` → (0, 13.33), (10, 0)  
- `5x₁ + 12x₂ = 50` → (0, 4.17), (10, 0)

### Adım 2: Uygun bölge
- “≥” kısıtları → orijinden **uzak** taraf  
- Uygun bölge: iki doğrunun **üst kesişimi**

### Adım 3: Köşe noktaları
1. `(10, 0)` → Kalori sınırı  
2. `(0, 13.33)` → Protein sınırı  
3. **Kesişim**:  
   `200x₁ + 150x₂ = 2000`  
   `5x₁ + 12x₂ = 50`  
   → Çözüm: `x₁ ≈ 6.06`, `x₂ ≈ 1.01`

### Adım 4: Amaç değerlendirmesi
| Nokta | Z = 2·x₁ + 5·x₂ |
|-------|------------------|
| (10, 0) | 20 |
| (0, 13.33) | 66.65 |
| **(6.06, 1.01)** | **2·6.06 + 5·1.01 ≈ 12.12 + 5.05 = 17.17** ✅

### Sonuç:
- **Küresel minimum**: `(6.06, 1.01)`  
- **Minimum maliyet**: **≈17.17 ₺**

---

## 📚 Örnek 3: Sonsuz Sayıda Optimal Çözüm

**Problem**:  
Max: `Z = 2·x₁ + 2·x₂`  
s.t.:  
`x₁ + x₂ ≤ 10`  
`x₁ ≤ 6`  
`x₂ ≤ 6`  
`x₁, x₂ ≥ 0`

### Gözlem:
- Amaç fonksiyonu: `Z = 2(x₁ + x₂)`  
- En büyük `x₁ + x₂ = 10` (ilk kısıt)  
- Bu doğrunun uygun bölgeyle kesişimi: `(4,6)` ile `(6,4)` arası **doğru parçası**

### Sonuç:
- **Sonsuz sayıda optimal çözüm** var  
- Tüm `(x₁, x₂)` çiftleri: `x₁ + x₂ = 10`, `4 ≤ x₁ ≤ 6`  
- **Küresel optimum değeri**: `Z = 20`

> 💡 Bu, **dejenere olmayan alternatif çözümler** örneğidir.

---

## 📌 Özet

- Grafik çözüm **yalnızca 2 değişkenli** DP’ler için uygundur  
- Uygun bölge her zaman **konveks çokgen**  
- Optimum **mutlaka bir köşededir** (ya da kenar üzerinde sonsuz çözüm)  
- Hem maksimizasyon hem minimizasyon için geçerlidir

---

## ➡️ Sonraki Adım

Daha yüksek boyutlu problemler için cebirsel çözüm yöntemi:

→ [Simpleks Yöntemi](simplex-method.md)
