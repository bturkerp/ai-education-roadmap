📘 Python Kurulum Rehberi (Windows)

Bu derste Windows işletim sisteminde Python’un temiz, sorunsuz ve yapay zekâ projelerine uygun şekilde nasıl kurulacağını öğreneceksin.

Bu rehber tamamen sıfırdan öğrenenler için hazırlandı.

🟦 1. Python Neden Gereklidir?

Python, yapay zekâ ve makine öğrenmesi alanında en çok kullanılan programlama dilidir.

Kullanım alanları:

- Makine Öğrenmesi

- Derin Öğrenme (TensorFlow, PyTorch)

- Veri Bilimi (NumPy, Pandas, Matplotlib)

- Yapay Zekâ projeleri

- Otomasyon, API, web uygulamaları

Bu eğitim boyunca tüm örnekleri Python ile yazacağız.

🟦 2. Python’un Doğru Sürümü Hangisidir?

Windows için önerilen sürüm:

✔ Python 3.10.x

TensorFlow, PyTorch, Jupyter ve diğer kütüphanelerle en sorunsuz sürüm budur.

⚠ Python 3.12+ kullanmayın

Birçok AI kütüphanesi hâlâ tam destek vermiyor.

🟦 3. Python’u Resmi Siteden İndir

Aşağıdaki bağlantıya git:

👉 https://www.python.org/downloads/windows/

Karşına “Latest Python 3.10” benzeri bir link çıkacaktır.

İndir:

Windows Installer (64-bit)

🟦 4. Kurulum Adımları (En Önemli Bölüm)

Kurulum penceresi açıldığında en kritik adım:

✅ Mutlaka işaretle:
```
☑ Add Python 3.10 to PATH
```

Bu kutuyu işaretlemezsen Python çalışmaz.

Sonra:

1. Customize installation → tıkla

2. Tüm seçenekler işaretli kalsın

3. “Install” butonuna bas

Kurulum birkaç dakika sürecek.

🟦 5. Python Kurulumunu Test Etme

Windows arama kısmına:

```
cmd
```

Komut satırı açıldıktan sonra:

```
python --version
```

Beklenen çıktı:

```
Python 3.10.x
```

Ardından pip’i test et:

```
pip --version
```

🟦 6. İlk Python Kodunu Çalıştıralım

Masaüstünde bir dosya oluştur:

test.py

İçine yaz:

```
print("Python çalışıyor!")
```

Komut satırında dosyanın olduğu klasöre gidip çalıştır:

```
python test.py
```

Beklenen çıktı:

```
Python çalışıyor!
```

🟦 7. Python İçin Gerekli Ek Kütüphaneleri Kurma

İlk etapta temel veri bilimi paketlerini kuralım:

```
pip install numpy pandas matplotlib
```

Yapay zeka kütüphanelerini sonraki derslerde conda ortamıyla kuracağız.

🟦 8. Bu Derste Öğrendiklerimiz

✔ Python neden AI için önemli?
✔ Python 3.10 sürümü neden kritik?
✔ Doğru installer nasıl indirilir?
✔ PATH ayarı nasıl yapılır?
✔ İlk Python dosyası nasıl çalıştırılır?
✔ pip test edildi
✔ Temel kütüphaneler kuruldu
