# 🧮 Simpleks Yöntemi

> *“Simpleks, doğrusal programlamanın kalbidir: köşe noktaları arasında akıllıca gezinerek küresel optimumu bulur.”*

Simpleks yöntemi, George Dantzig tarafından 1947’de geliştirilen, **doğrusal programlama (DP) problemlerini cebirsel olarak çözen** bir algoritmadır. Yöntem, uygun bölgenin **köşe noktaları (temel uygun çözümler)** arasında, amaç fonksiyonunu iyileştiren yönde hareket ederek **küresel optimuma** ulaşır.

---

## 🧱 Temel Kavramlar

| Terim | Açıklama |
|------|--------|
| **Temel değişken** | Bir köşe noktasında sıfır olmayan değişken |
| **Temel olmayan değişken** | Değeri sıfır olan değişken |
| **Temel uygun çözüm (BFS)** | Tüm kısıtları sağlayan köşe noktası |
| **Slack değişkeni** | `≤` kısıtını eşitliğe çevirmek için eklenen değişken (`s ≥ 0`) |
| **İyileştirme** | Amaç fonksiyonunu artıran yönde hareket |

> 🔑 Simpleks, her iterasyonda **bir köşe noktasından komşusuna** geçer.

---

## 🔁 Algoritma Adımları (Maksimizasyon)

1. **Standart forma getir** (slack ekle)  
2. **Başlangıç tablosunu oluştur**  
3. **Giriş değişkeni**: En büyük pozitif `cⱼ − zⱼ`  
4. **Çıkış değişkeni**: Minimum oran testi (`çözüm / giriş sütunu > 0`)  
5. **Pivot işlemiyle yeni tablo oluştur**  
6. **Dur**: Tüm `cⱼ − zⱼ ≤ 0` → **küresel optimum**

---

## 📚 Örnek 1: Standart Üretim Problemi (Tekrar)

**Max:** `Z = 40·x₁ + 30·x₂`  
s.t.  
`2x₁ + x₂ ≤ 100`  
`x₁ + 3x₂ ≤ 90`  
`x₁, x₂ ≥ 0`

✅ **Küresel optimum**: `x₁ = 42`, `x₂ = 16`, `Z = 2160`  
→ Detaylı tablolar önceki bölümden biliniyor.

---

## 📚 Ek Örnek 2: Sınırsız Çözüm (Unbounded)

**Problem**:  
Max: `Z = 3·x₁ + 2·x₂`  
s.t.:  
`x₁ − x₂ ≤ 2`  
`x₁, x₂ ≥ 0`

### Başlangıç Tablosu:

| Temel | x₁ | x₂ | s₁ | Çözüm |
|-------|----|----|----|--------|
| s₁    | 1  | -1 | 1  | 2      |
| **Z** | -3 | -2 | 0  | 0      |

- **Giriş**: x₁ (`cⱼ−zⱼ = 3`)  
- **Çıkış**: `2 / 1 = 2` → s₁ çıkar

### 1. İterasyon:

| Temel | x₁ | x₂ | s₁ | Çözüm |
|-------|----|----|----|--------|
| x₁    | 1  | -1 | 1  | 2      |
| **Z** | 0  | -5 | 3  | 6      |

- **Giriş**: x₂ (`cⱼ−zⱼ = 5 > 0`)  
- **Çıkış testi**: x₂ sütunu = `[−1]` → **tüm elemanlar ≤ 0**

> 🚫 **Sonuç**: **Sınırsız çözüm** — amaç fonksiyonu sonsuza gider (`Z → ∞`).  
> Gerçekçi olmayan model; muhtemelen bir kaynak kısıtı eksik.

---

## 📚 Ek Örnek 3: Uygun Olmayan (Infeasible) Problem

**Problem**:  
Max: `Z = x₁ + x₂`  
s.t.:  
`x₁ + x₂ ≤ 4`  
`x₁ + x₂ ≥ 6`  
`x₁, x₂ ≥ 0`

### Analiz:
- İlk kısıt: toplam ≤ 4  
- İkinci kısıt: toplam ≥ 6  
→ **Kesişim yok!** → **Uygun bölge boş**

### Big-M ile Simpleks Tablosu (özet):

| Temel | x₁ | x₂ | s₁ | s₂ | a₁ | Çözüm |
|-------|----|----|----|----|----|--------|
| s₁    | 1  | 1  | 1  | 0  | 0  | 4      |
| a₁    | 1  | 1  | 0  | -1 | 1  | 6      |
| **Z** | -1−M | -1−M | 0 | M | 0 | -6M |

- İterasyonlar sonunda **yapay değişken `a₁` temelde kalır** ve `a₁ > 0`  
- Bu, **uygun çözüm olmadığını** gösterir.

> 🚫 **Sonuç**: **Uygun olmayan problem** — kısıtlar çelişiyor.

---

## 📚 Ek Örnek 4: Dejenere Çözüm (Degeneracy)

**Problem**:  
Max: `Z = 5·x₁ + 3·x₂`  
s.t.:  
`x₁ + x₂ ≤ 6`  
`2·x₁ + x₂ ≤ 12`  
`x₁ ≤ 6`  
`x₁, x₂ ≥ 0`

### Başlangıç Tablosu (slack: s₁, s₂, s₃):

| Temel | x₁ | x₂ | s₁ | s₂ | s₃ | Çözüm |
|-------|----|----|----|----|----|--------|
| s₁    | 1  | 1  | 1  | 0  | 0  | 6      |
| s₂    | 2  | 1  | 0  | 1  | 0  | 12     |
| s₃    | 1  | 0  | 0  | 0  | 1  | 6      |
| **Z** | -5 | -3 | 0  | 0  | 0  | 0      |

- **Giriş**: x₁  
- **Oran testi**:  
  - s₁: 6/1 = 6  
  - s₂: 12/2 = 6  
  - s₃: 6/1 = 6  
→ **Üç eşit oran!** → **Dejenere durum**

### Seçim (Bland kuralı): En küçük indise sahip temel → s₁ çıkar

### 1. İterasyon:

| Temel | x₁ | x₂ | s₁ | s₂ | s₃ | Çözüm |
|-------|----|----|----|----|----|--------|
| x₁    | 1  | 1  | 1  | 0  | 0  | 6      |
| s₂    | 0  | -1 | -2 | 1  | 0  | 0      |
| s₃    | 0  | -1 | -1 | 0  | 1  | 0      |
| **Z** | 0  | 2  | 5  | 0  | 0  | 30     |

- **Z = 30**, ama s₂ ve s₃ satırlarında çözüm = 0 → **dejenere BFS**  
- Algoritma **döngüye girebilir** (ama Bland kuralıyla engellenir)

> ⚠️ **Sonuç**: Küresel optimum vardır (`Z = 30`), ama bazı iterasyonlarda **amaç değişmeyebilir**.

---

## ❓ Sık Karşılaşılan Durumlar Özeti

| Durum | Simpleks Tablosunda Belirti | Anlamı |
|------|----------------------------|--------|
| **Küresel optimum** | Tüm `cⱼ − zⱼ ≤ 0` | En iyi çözüm bulundu |
| **Sınırsız** | Giriş sütununda tüm katsayılar ≤ 0 | Amaç sonsuza gider |
| **Uygun değil** | Yapay değişken > 0 olarak kalır | Kısıtlar çelişiyor |
| **Dejenere** | Bir veya daha fazla temel değişken = 0 | Amaç aynı kalabilir; döngü riski |

---

## 📌 Özet

- Simpleks **küresel optimumu garanti eder** (problem uygun ve sınırlıysa)  
- **Sınırsız**, **uygun olmayan** ve **dejenere** durumlar, modelin doğruluğunu test etmek için önemlidir  
- Gerçek uygulamalarda bu durumlar, **eksik/yanlış modelleme** işaretidir

---

## ➡️ Sonraki Adım

Kesikli kararlar (evet/hayır, makine sayısı) gerektiren problemler için:

→ [Tamsayılı Programlama](../02-Integer-Programming/README.md)
