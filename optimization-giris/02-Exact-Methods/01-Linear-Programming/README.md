# 📈 Doğrusal Programlama (Linear Programming)

> *“Doğrusal programlama, optimizasyonun en güçlü ve en yaygın kullanılan silahıdır.”*

Doğrusal programlama (DP), **amaç fonksiyonu ve tüm kısıtların doğrusal** olduğu optimizasyon problemlerini çözmek için geliştirilmiş bir kesin yöntemdir. DP, hem teorik olarak sağlam hem de pratikte yüksek performanslı çözümler sunar.

En önemlisi: **Doğrusal programlama problemleri her zaman konvekstir** → bu da **her yerel optimumun küresel optimum olduğunu** garanti eder.

---

## 🧩 Temel Formülasyon

### Standart (Maksimizasyon) Form:
- **Amaç**: Max ∑ cⱼ·xⱼ &nbsp;&nbsp; (j = 1…n)  
- **Kısıtlar**: ∑ aᵢⱼ·xⱼ ≤ bᵢ &nbsp;&nbsp; (i = 1…m)  
- **Değişkenler**: xⱼ ≥ 0

### Genel Özellikler:
- **Değişkenler**: Sürekli (gerçel sayılar)  
- **Amaç**: Doğrusal → düz bir düzlem  
- **Kısıtlar**: Yarı-uzaylar → kesişimleri **konveks çokyüzlü** (polyhedron) oluşturur  
- **Optimum**: Her zaman bir **köşe noktasında** (extreme point) oluşur

> 💡 Bu yüzden **Simpleks algoritması**, köşe noktaları arasında gezinerek optimumu bulur.

---

## 📊 Geometrik Yorum

- **Uygun bölge (feasible region)**: Tüm kısıtların kesişimiyle oluşan kapalı alan  
- **Köşe noktası (vertex)**: İki veya daha fazla kısıtın kesiştiği nokta  
- **Küresel optimum**: Uygun bölgenin bir köşe noktasındadır (veya kenar/kenar üzerinde sonsuz çözüm)

### Örnek (2 Değişkenli):
Min: `2·x₁ + 3·x₂`  
s.t.:  
`x₁ + x₂ ≥ 4`  
`x₁ ≤ 3`  
`x₂ ≤ 3`  
`x₁, x₂ ≥ 0`

→ Uygun bölge bir çokgen; amaç fonksiyonu bu çokgen üzerinde kaydırılır.  
→ En düşük değeri **bir köşede** (örneğin: `x₁=1, x₂=3`) alır.

---

## ⚙️ Çözüm Yöntemleri

### 1. [Grafik Çözüm](graph-solution.md) 
### 2. [**Simpleks Algoritması** (George Dantzig, 1947)](simplex.md)
- Köşe noktaları arasında **iyileştirme yönünde** hareket eder  
- Pratikte çok hızlı; teoride en kötü durumda üssel zaman alabilir  
- Günümüzde LP çözücülerinin çekirdeğinde yer alır

### 3. [**İç-Nokta Yöntemleri** (Karmarkar, 1984)](icnokta.md)
- Uygun bölgenin **içinden** geçerek optimuma yaklaşır  
- Büyük ölçekli problemlerde Simpleks’ten daha iyi performans gösterebilir  
- Polinomsal zaman karmaşıklığına sahiptir

> 📌 Her iki yöntem de **kesin çözümü** (küresel optimum) garanti eder.

---

## 🔁 [Dualite Teorisi](Dualite.md) 

Her doğrusal programlama problemi (**primal**) için bir **dual** problem tanımlanabilir.

### Primal (Maksimizasyon):
Max: ∑ cⱼ·xⱼ  
s.t.: ∑ aᵢⱼ·xⱼ ≤ bᵢ, &nbsp; xⱼ ≥ 0

### Dual (Minimizasyon):
Min: ∑ bᵢ·yᵢ  
s.t.: ∑ aᵢⱼ·yᵢ ≥ cⱼ, &nbsp; yᵢ ≥ 0

### Ekonomik Yorum:
- `yᵢ`: `i`. kaynağın **gölge fiyatı** (shadow price)  
- Kaynak bir birim artırılırsa, toplam kar ne kadar artar?

> 💡 **Güçlü dualite teoremi**: Uygun çözümler varsa, primal ve dualin optimum değerleri **eşittir**.

---

## 📉 [Duyarlılık Analizi (Sensitivity Analysis)](duyarlilik.md)

DP modelleri, parametrelerdeki değişikliklere karşı ne kadar duyarlıdır?

- **Amaç katsayıları (`cⱼ`)** ne kadar değişirse çözüm değişmez?  
- **Kaynak miktarları (`bᵢ`)** artırılırsa kar ne kadar artar? (→ gölge fiyat)  
- Yeni bir değişken (ürün) eklemek karı artırır mı? (→ indirgenmiş maliyet)

> Bu analizler, **karar vericilere stratejik esneklik** sağlar.

---

## 📚 Gerçekçi Örnek: Üretim Planlama

**Senaryo**: Bir fabrika iki ürün üretiyor. Kaynaklar sınırlı.

| Kaynak | Ürün A | Ürün B | Mevcut |
|--------|--------|--------|--------|
| İşçilik (saat) | 2 | 1 | 100 |
| Malzeme (kg) | 1 | 3 | 90 |
| **Birim Kar (₺)** | **40** | **30** | — |

### Model:
- `x₁`: Ürün A miktarı  
- `x₂`: Ürün B miktarı

**Amaç**: Max: 40·x₁ + 30·x₂  
**Kısıtlar**:  
2·x₁ + 1·x₂ ≤ 100 &nbsp;&nbsp; (işçilik)  
1·x₁ + 3·x₂ ≤ 90 &nbsp;&nbsp;&nbsp;&nbsp; (malzeme)  
x₁, x₂ ≥ 0

### Çözüm (Simpleks/PuLP ile):
- Optimal üretim: `x₁ = 42`, `x₂ = 16`  
- Maksimum kar: **2160 ₺**  
- İşçilik tamamen kullanılır (gölge fiyat > 0)  
- Malzeme kısmen kullanılır (gölge fiyat = 0)

---

## 💻 Python ile Çözüm (PuLP)

```python
import pulp

# Problem tanımla
prob = pulp.LpProblem("Uretim_Planlama", pulp.LpMaximize)

# Karar değişkenleri
x1 = pulp.LpVariable('UrunA', lowBound=0, cat='Continuous')
x2 = pulp.LpVariable('UrunB', lowBound=0, cat='Continuous')

# Amaç fonksiyonu
prob += 40 * x1 + 30 * x2, "Toplam_Kar"

# Kısıtlar
prob += 2 * x1 + 1 * x2 <= 100, "Isçilik"
prob += 1 * x1 + 3 * x2 <= 90, "Malzeme"

# Çöz
prob.solve()

print(f"Ürün A: {x1.varValue}")
print(f"Ürün B: {x2.varValue}")
print(f"Maksimum Kar: {pulp.value(prob.objective)}")
