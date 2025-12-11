# 📘 Visual Studio Code Kurulum Rehberi (Windows)

Bu derste Windows işletim sisteminde Visual Studio Code (VS Code) kurulumunu sıfırdan yapıyoruz.  
VS Code, Python, veri bilimi, makine öğrenmesi ve yapay zekâ çalışmalarında en çok kullanılan kod editörlerinden biridir.

---

## 🟦 1. VS Code’u Neden Kullanıyoruz?

VS Code’un avantajları:

- Ücretsiz  
- Çok hızlı  
- Python eklentileri mükemmel  
- Jupyter destekli  
- Git/GitHub ile kusursuz entegre  
- Kod yazmayı kolaylaştıran binlerce eklenti var  

Bu nedenle tüm eğitim sürecinde VS Code kullanacağız.

---

## 🟦 2. VS Code’u İndir

Aşağıdaki bağlantıya git:

👉 https://code.visualstudio.com/

Sayfada *Windows x64 Installer* otomatik olarak görünür.  
Tıklayıp dosyayı indir.

İndirilen dosya genelde şu isimde olur:

VSCodeUserSetup-x64-<sürüm>.exe


---

## 🟦 3. Kurulum Adımları

1. **“I accept the agreement”** kutusunu işaretle.  
2. Aşağıdaki 3 kutuyu mutlaka işaretle:
   - ✔ Add to PATH  
   - ✔ Register Code as editor  
   - ✔ Add "Open with Code" action (context menu)  
3. **Install** → kurulum başlar.

Bu ayarlar sayesinde VS Code her yerde kullanılabilir.

---

## 🟦 4. İlk Açılış

Kurulum tamamlandığında VS Code açılır ve şu ekran görülür:

- Sol tarafta menüler  
- Ortada boş çalışma alanı  
- Üstte komut paleti  

Tema seçmek istersen:  
**Ayarlar → Color Theme**

---

## 🟦 5. Gerekli Eklentilerin Kurulumu

Sol taraftan **Extensions** bölümüne (veya `Ctrl + Shift + X`) gir.

Aşağıdaki eklentileri kur:

- ⭐ Python (Microsoft)  
- ⭐ Pylance  
- ⭐ Jupyter  
- ⭐ GitLens  
- ⭐ Material Icon Theme  

Bu beş eklenti tüm eğitim boyunca yeterli olacak.

---

## 🟦 6. VS Code’da İlk Python Dosyası Oluşturma

1. Masaüstüne yeni klasör oluştur:



python-projelerim


2. VS Code → **File → Open Folder** → bu klasörü seç  
3. Sol üstte **New File** → `test.py` oluştur  
4. İçine yaz:

```python 
print("VS Code çalışıyor!")
```
Çalıştırmak için:

Üst menü → Terminal → New Terminal

Terminal’e yaz:

```
python test.py
```
Eğer çıktı şu geliyorsa kurulum başarılıdır:

```
VS Code çalışıyor!
```

🟦 7. Python Terminali Ayarını Kontrol Et

VS Code sağ alt köşede kullandığı Python sürümünü gösterir:

```
Python 3.x (64-bit)
```
Bu kısım, ileride conda ortamları bağlarken önemli olacak.

🟦 8. Bu Derste Öğrendiklerimiz

✔ VS Code indirildi

✔ Kurulum ayarları yapıldı

✔ Gerekli eklentiler kuruldu

✔ İlk Python dosyası yazıldı

✔ Terminalde çalıştırma test edildi
