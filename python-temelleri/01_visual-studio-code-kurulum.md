📘 Visual Studio Code Kurulum Rehberi (Windows)

Bu derste Windows işletim sisteminde Visual Studio Code (VS Code) kurulumunu sıfırdan yapıyoruz.

VS Code, Python, veri bilimi, makine öğrenmesi ve yapay zeka çalışmalarında en çok kullanılan kod editörlerinden biridir.

🟦 1. VS Code’u Neden Kullanıyoruz?

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

Sayfada Windows x64 Installer otomatik olarak gelir.
Tıklayıp dosyayı indir.

İndirilen dosya:

VSCodeUserSetup-x64-<sürüm>.exe

🟦 3. Kurulum Adımları
➊ “I accept the agreement” → işaretle
➋ Aşağıdaki 3 kutuyu işaretle (çok önemli):

✔ Add to PATH
✔ Register Code as editor
✔ Add "Open with Code" action (context menu)

Bu ayarlar VS Code'u her yerde kullanmanı kolaylaştırır.

➌ Install → Kurulum başlar.
🟦 4. İlk Açılış

Kurulum bittiğinde VS Code açılır ve aşağıdaki gibi bir ekran görürsün:

Sol tarafta menüler

Orta alan boş

Üstte komut paleti

İstersen tema seçebilirsin.
(Tema: Ayarlar → Color Theme)

🟦 5. Gerekli Eklentilerin Kurulumu

Sol tarafta Extensions kısmına (Ctrl + Shift + X) tıkla.

Şunları ara ve kur:

⭐ Python (Microsoft) → Ana Python uzantısı
⭐ Pylance → Akıllı kod tamamlama
⭐ Jupyter → .ipynb dosyaları için
⭐ GitLens → Git/GitHub için
⭐ Material Icon Theme → Klasör/kod ikonlarını güzelleştirir

Bu 5 eklenti tüm eğitim boyunca işimizi görecek.

🟦 6. VS Code’da İlk Python Dosyası Oluşturma

Masaüstüne bir klasör aç:

python-projelerim


VS Code → File → Open Folder → bu klasörü seç

Sol üstte New File →

test.py


İçine yaz:

print("VS Code çalışıyor!")


Çalıştırmak için terminal aç:

Üst menü → Terminal → New Terminal

Terminal’e yaz:

python test.py


📌 Eğer çıktı şöyle geldiyse kurulum başarılıdır:

VS Code çalışıyor!

🟦 7. VS Code’un Python Terminali Ayarını Kontrol Etme

VS Code yeni terminali açtığında hangi Python ortamını kullanacağını gösterir.

Görev çubuğunun sağ alt kısmında “Python 3.x (64-bit)” gibi bir metin görürsün.

Bu ileride conda ortamlarını bağlarken çok işimize yarayacak.

🟦 8. Derste Öğrendiklerimiz

✔ VS Code indirildi
✔ Kurulum ayarları doğru yapıldı
✔ Gerekli eklentiler kuruldu
✔ İlk Python dosyası çalıştırıldı
