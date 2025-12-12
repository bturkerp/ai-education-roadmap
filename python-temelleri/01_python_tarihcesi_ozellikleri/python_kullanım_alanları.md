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

```python
from flask import Flask

app = Flask(__name__)

@app.route("/")
def home():
    return "Merhaba, Dünya!"

if __name__ == "__main__":
    app.run(debug=True)
