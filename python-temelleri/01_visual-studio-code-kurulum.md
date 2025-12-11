📘 Visual Studio Code Kurulum Rehberi (Windows)

Bu derste Windows işletim sisteminde Visual Studio Code (VS Code) kurulumunu sıfırdan yapıyoruz.

VS Code, Python, veri bilimi, makine öğrenmesi ve yapay zeka çalışmalarında en çok kullanılan kod editörlerinden biridir.

🟦 1. VS Code’u Neden Kullanıyoruz?

VS Code’un avantajları:

Ücretsiz

Çok hızlı

Python eklentileri mükemmel

Jupyter destekli

Git/GitHub ile kusursuz entegre

Kod yazmayı kolaylaştıran binlerce eklenti var

Bu nedenle tüm eğitim sürecinde VS Code kullanacağız.

🟦 2. VS Code’u İndir

Aşağıdaki bağlantıya git:

👉 https://code.visualstudio.com/

Sayfada Windows x64 Installer otomatik çıkacaktır.
Tıklayıp indir.

İndirilen dosya genelde şöyle olur:

VSCodeUserSetup-x64-<sürüm>.exe

🟦 3. Kurulum Adımları

“I accept the agreement” → işaretle

Aşağıdaki 3 kutuyu mutlaka işaretle:

✔ Add to PATH

✔ Register Code as editor

✔ Add "Open with Code" action

Install → Kurulum başlar.

Bu ayarlar sayesinde VS Code her yerde kullanılabilir.

🟦 4. İlk Açılış

Kurulum tamamlandığında VS Code açılır.
Aşağıdaki ekran görünür:

Sol tarafta menüler

Ortada boş çalışma alanı

Üstte komut paleti

Tema değiştirmek istersen:

Ayarlar → Color Theme

🟦 5. Gerekli Eklentilerin Kurulumu

Sol menü → Extensions (Ctrl + Shift + X)

Aşağıdaki eklentileri ara ve kur:

⭐ Python (Microsoft)

⭐ Pylance

⭐ Jupyter

⭐ GitLens

⭐ Material Icon Theme

Bu beş eklenti tüm eğitim için yeterli.

🟦 6. İlk Python Dosyasını Oluşturma

Masaüstüne klasör aç:

python-projelerim


VS Code → File → Open Folder → klasörü seç

Sol üst → New File → test.py

İçine yaz:

print("VS Code çalışıyor!")


Çalıştırmak için:

Üst menü → Terminal → New Terminal
Terminal'e yaz:

python test.py


Çıktı:

VS Code çalışıyor!

🟦 7. Python Terminali Ayarı

VS Code sağ alt köşede hangi Python’un seçili olduğunu gösterir:

Python 3.x (64-bit)

Bu, ileride conda ortamları bağlarken önemli olacak.

🟦 8. Bu Derste Öğrendiklerimiz

VS Code indirildi

Kurulum ayarları yapıldı

Gerekli eklentiler kuruldu

İlk Python dosyası yazıldı

Terminalde başarıyla çalıştırıldı
