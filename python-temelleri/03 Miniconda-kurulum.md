📘 Miniconda Kurulum Rehberi (Windows)

Bu derste Windows üzerinde Miniconda kurulumunu sıfırdan yapıyoruz. Miniconda, Python ortamlarınızı (environment) yönetmek için en hafif, en temiz çözümdür.

Tüm eğitim boyunca model eğitimi, yapay zekâ, veri bilimi projelerinde Conda ortamları kullanacağız.

🟦 1. Miniconda Nedir?

Miniconda, Anaconda'nın hafif sürümüdür:

- Gereksiz paket yok

- Daha hızlı

- Ortam yönetimi mükemmel

- CUDA, PyTorch, TensorFlow ortamlarını izole kurabilirsiniz

Bu nedenle Python’u direkt sisteme kurmak yerine Conda ortamına kurmak her zaman daha iyidir.

🟦 2. Miniconda’yı İndir

Resmî indirme sayfası: https://docs.anaconda.com/miniconda/

İndirilecek sürüm:

Windows • Miniconda3 • 64-bit • Installer (.exe)

Genelde isim şöyle olur:

Miniconda3-latest-Windows-x86_64.exe
🟦 3. Kurulum Adımları

Kurulum dosyasını açınca:

✔ 1) "Just Me" seçin (önerilir)
✔ 2) Lisans sözleşmesini kabul edin
✔ 3) Aşağıdaki iki kutuyu mutlaka DOĞRU şekilde ayarlayın:
☐ Add Miniconda3 to PATH            (BUNU İŞARETLEME!)
☑ Register Miniconda3 as the default Python

PATH'e eklemiyoruz çünkü sorun çıkarır. Conda zaten kendi terminaliyle PATH'i yönetiyor.

Install → Kurulum 1 dakika sürer.
🟦 4. Kurulum Sonrası Test

Başlat → Anaconda Prompt (Miniconda3) açın.

Aşağıdaki komutu yazın:

conda --version

Beklenen çıktı:

conda 24.x.x

Python sürümünü test edin:

python --version
🟦 5. Conda Ortamı Oluşturma (ÖNEMLİ)

Her projede ayrı ortam kullanılır.

Örnek: Python 3.12 ortamı oluşturma:

conda create -n tf python=3.12 -y

Ortamı aktifleştir:

conda activate tf

Doğru çalıştığını kontrol edin:

python --version
🟦 6. Pip & Conda Paketleri Kurma

Conda ortamı aktifken istediğiniz paketleri kurabilirsiniz:

pip ile:
pip install numpy pandas matplotlib
conda ile:
conda install numpy pandas -y

CUDA destekli PyTorch veya TensorFlow kurmayı da ileride işleyeceğiz.

🟦 7. Ortamları Listeleme & Silme

Mevcut ortamları listele:

conda env list

Ortam silme:

conda remove -n tf --all
🟦 8. VS Code ile Conda Bağlantısı

VS Code → sol alt köşedeki Python sürümüne tıklayın.

Açılan listeden conda ortamını seçin:

tf (Python 3.12)

VS Code artık o projeyi bu ortamla çalıştırır.

🟦 9. Bu Derste Öğrendikleriniz

✔ Miniconda indirildi
✔ PATH ayarları doğru şekilde yapıldı
✔ Conda ortamı oluşturuldu
✔ Ortam aktif edildi
✔ Pip/Conda paket yönetimi öğrenildi
✔ VS Code ile entegrasyon ayarlandı
