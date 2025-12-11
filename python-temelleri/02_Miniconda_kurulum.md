#📘 Miniconda Kurulum Rehberi (Windows)

Bu derste Windows üzerinde Miniconda kurulumunu sıfırdan yapıyoruz. Miniconda, Python ortamlarınızı (environment) yönetmek için en hafif, en temiz çözümdür.

Tüm eğitim boyunca model eğitimi, yapay zekâ, veri bilimi projelerinde Conda ortamları kullanacağız.

🟦 1. Miniconda Nedir?

Miniconda, Anaconda'nın hafif sürümüdür:

- Gereksiz paket yok

- Daha hızlı

- Ortam yönetimi mükemmel

- CUDA, PyTorch, TensorFlow ortamlarını izole kurabilirsiniz
  
- GPU destekli ortamlar sorunsuz çalışır

Bu nedenle Python’u direkt sisteme kurmak yerine Conda ortamına kurmak her zaman daha iyidir.

🟦 2. Miniconda’yı İndir

Resmî indirme sayfası: https://docs.anaconda.com/miniconda/

İndirilecek sürüm:
```
Windows • Miniconda3 • 64-bit • Installer (.exe)
```

Genelde isim şöyle olur:

```
Miniconda3-latest-Windows-x86_64.exe
```

🟦 3. Kurulum Adımları

Kurulum dosyasını açınca:

1) ✔ "Just Me" seçin (önerilir)
2) ✔ Lisans sözleşmesini kabul edin
3) ✔ Aşağıdaki iki kutuyu mutlaka DOĞRU şekilde ayarlayın:

```
☐ Add Miniconda3 to PATH            (BUNU İŞARETLEME!)
☑ Register Miniconda3 as the default Python
```
PATH'e eklemiyoruz çünkü sorun çıkarır. Conda zaten kendi terminaliyle PATH'i yönetiyor.

Install → Kurulum 1 dakika sürer.

🟦 4. Kurulum Sonrası Test

Başlat → Anaconda Prompt (Miniconda3) açın.

Aşağıdaki komutu yazın:

```
conda --version
```

Beklenen çıktı:
```
conda 24.x.x
```

Python sürümünü test edin:
```
python --version
```

🟦 5. Pip & Conda Paketleri Kurma

🟦 A) CPU Kullanacaklar İçin Ortam (Önerilen)

TensorFlow ≥ 2.11 Windows’da GPU çalışmaz, bu yüzden CPU tercih edenler için en sorunsuz yol:

✔ Python 3.10 CPU ortamı oluştur
```
conda create -n tfcpu python=3.10 -y
conda activate tfcpu
```
✔ CPU sürümleri:
1. TensorFlow CPU
```
pip install tensorflow==2.15
```

3. PyTorch CPU
```
pip install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cpu
```

5. Bilimsel paketler
```
pip install numpy pandas matplotlib seaborn scikit-learn jupyterlab
```

Çalışıyor mu?

```
python -c "import tensorflow as tf; print(tf.__version__); print(tf.config.list_physical_devices())"
```

🟦 B) GPU Kullanacaklar İçin Ortam (Windows – NVIDIA)

Bu bölüm yalnızca TensorFlow 2.10 ve altı için geçerlidir.
Resmî TensorFlow belgesi:
✔ “Windows native GPU only works up to TensorFlow 2.10”

👉 https://www.tensorflow.org/install/pip?hl=tr#windows-native

✔ 1. Ortamı Oluştur (Python 3.10)
```
conda create -n tfgpu python=3.10 -y
conda activate tfgpu
```
✔ 2. CUDA 11.2 + cuDNN 8.1 (Conda’dan temiz kurulum)
```
conda install -c conda-forge cudatoolkit=11.2 cudnn=8.1.0 -y
```

Bu kurulum yalnızca TensorFlow 2.10 için uygundur.

✔ 3. TensorFlow GPU (2.10 ve altı)
```
pip install "tensorflow<2.11"
```

Bu otomatik olarak doğru GPU sürümünü kurar.

✔ 4. PyTorch GPU (CUDA 12 destekli)

PyTorch, Windows’ta CUDA 12 ile sorunsuz çalışıyor.
```
pip install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu121
```

✔ 5. Bilimsel paketler
```
pip install numpy pandas matplotlib seaborn scikit-learn jupyterlab
```
✔ Test – TensorFlow GPU
```
python -c "import tensorflow as tf; print(tf.config.list_physical_devices('GPU'))"
```

Beklenen çıktı:
```
[PhysicalDevice(name='/physical_device:GPU:0', device_type='GPU')]
```

🟦 6. Ortamları Listelemek
```
conda env list
```

🟦 7. Ortam Silmek
```
conda remove -n tfgpu --all
```

🟦 8. Doğru Kurulum Stratejisi (En Temizi)

✔ ML/AI çalışacaksan: CPU ortamı
✔ XAI, CV, DL çalışacaksan: PyTorch GPU ortamı
✔ Sadece TF GPU gerekirse: tfgpu ortamı (TF 2.10)
