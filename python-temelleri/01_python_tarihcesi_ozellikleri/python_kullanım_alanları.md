# Python'un Kullanım Alanları

Python, çok yönlü ve güçlü bir programlama dilidir. Hem **web geliştirme**, hem **veri bilimi**, hem **yapay zekâ**, hem de **otomasyon** gibi pek çok alanda kullanılır. Bu dosyada Python’un başlıca kullanım alanları ve örnekleri açıklanmaktadır.

---

## 1. Web Geliştirme

Python, web uygulamaları geliştirmek için yaygın olarak kullanılır.  
Popüler frameworkler:

- **Django**: Büyük ve güvenli web uygulamaları için.
- **Flask**: Hafif ve hızlı web uygulamaları için.
- **FastAPI**: REST API geliştirme için modern framework.

**Örnek: Basit Flask uygulaması**

```
python
from flask import Flask

app = Flask(__name__)

@app.route("/")
def home():
    return "Merhaba, Dünya!"

if __name__ == "__main__":
    app.run(debug=True)
```

## 2. Veri Bilimi ve Analiz
Python, veri analizi ve istatistiksel çalışmalar için en popüler dillerden biridir.
Kullanılan kütüphaneler:

- NumPy → Sayısal hesaplamalar

- Pandas → Veri manipülasyonu ve analizi

- Matplotlib / Seaborn → Görselleştirme

- SciPy → Bilimsel hesaplamalar

Örnek: Veri analizi
```
Python
import pandas as pd

data = pd.DataFrame({
    "isim": ["Ali", "Ayşe", "Mehmet"],
    "yas": [25, 30, 22]
})
print(data.describe())
```

## 3. Yapay Zekâ ve Makine Öğrenmesi
Python, AI ve ML projelerinde standart bir dildir.
Popüler kütüphaneler:
- scikit-learn → Makine öğrenmesi algoritmaları
- TensorFlow / Keras / PyTorch → Derin öğrenme
- OpenCV → Görüntü işleme ve bilgisayarla görme
Örnek: Basit ML modeli (scikit-learn)
```
Python

from sklearn.linear_model import LinearRegression
import numpy as np

X = np.array([[1], [2], [3], [4]])
y = np.array([2, 4, 6, 8])

model = LinearRegression()
model.fit(X, y)
print(model.predict([[5]]))  # Tahmin: 10
```

## 4. Otomasyon ve Scripting
Python, günlük işleri otomatikleştirmek için çok uygundur:
- Dosya ve klasör işlemleri
- Web scraping (BeautifulSoup, Selenium)
- Excel ve PDF otomasyonu (openpyxl, PyPDF2)
Örnek: Dosya adı değiştirme
```
Python

import os

for filename in os.listdir("."):
    if filename.endswith(".txt"):
        new_name = filename.replace(".txt", "_yeni.txt")
        os.rename(filename, new_name)

```

## 5. Oyun Geliştirme
Python, oyun geliştirme ve prototip oluşturmak için kullanılır:
- Pygame → 2D oyun geliştirme
- Godot-Python → Godot motoru entegrasyonu
Örnek: Basit Pygame pencere
```
Python

import pygame

pygame.init()
screen = pygame.display.set_mode((400, 300))
pygame.display.set_caption("Python Oyun")
running = True

while running:
    for event in pygame.event.get():
        if event.type == pygame.QUIT:
            running = False

pygame.quit()
```

## 6. Bilimsel ve Mühendislik Uygulamaları
- SymPy → Sembolik matematik
- SciPy → Bilimsel hesaplamalar
- NumPy → Lineer cebir ve sayısal hesaplamalar
- Matplotlib / Mayavi → Veri görselleştirme
Örnek: Matris çarpımı
```
Python

import numpy as np

A = np.array([[1, 2], [3, 4]])
B = np.array([[5, 6], [7, 8]])

C = np.dot(A, B)
print(C)
```
## 7. Ağ Programlama ve İnternet Uygulamaları
- Socket programlama
- HTTP istekleri (requests kütüphanesi)
- REST API istemcileri ve sunucuları















