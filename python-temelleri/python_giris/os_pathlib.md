# 📁 Python OS ve Pathlib Modülleri Rehberi
## 🗂️ OS MODÜLÜ (Sistem İşlemleri)
### 🔍 Dosya ve Dizin Kontrolü
```
import os

# Dosya/dizin var mı?
print(os.path.exists("kisiler.xml"))  # True/False

# Dosya mı?
print(os.path.isfile("kisiler.xml"))  # True

# Dizin mi?
print(os.path.isdir("klasor"))  # True

# Boyut (byte)
print(os.path.getsize("kisiler.xml"))  # 1024

# Son erişim/değiştirme zamanı
print(os.path.getatime("kisiler.xml"))  # timestamp
print(os.path.getmtime("kisiler.xml"))
```
Çıktı:
```
True
True
False
169
1765556124.344498
1765555225.5427828
```

### 📂 Dizin İşlemleri
```
import os

# Çalışma dizinini değiştir
os.chdir("C:/Users")  # Windows

# Mevcut çalışma dizini
print(os.getcwd())

# Dizin içeriğini listele
print(os.listdir("."))  # Mevcut dizin
print(os.listdir(".."))  # Üst dizin

# Tüm dosyaları listele (alt dizinlerle)
for kok, dizinler, dosyalar in os.walk("."):
    print(f"Dizin: {kok}")
    print(f"Alt dizinler: {dizinler}")
    print(f"Dosyalar: {dosyalar}")
```


Çıktı:
```
D:\quantum NN
['Best Model.docx', 'DER_N___RENME_ARACILI_IYLA_G20__LKELER_NDE_ARGE_HA.pdf', 'DERİN ÖĞRENME ARACILIĞIYLA G20 ÜLKELERİNDE ARGE HARCAMALARININ ve İLİŞKİLİ DEĞİŞKENLERİN EKONOMİK BÜYÜME ÜZERİNE ETKİSİNİN İNCELENMESİ (Pınar Hoca).docx', 'DERİN ÖĞRENME ARACILIĞIYLA G20 ÜLKELERİNDE ARGE HARCAMALARININ ve İLİŞKİLİ DEĞİŞKENLERİN EKONOMİK BÜYÜME ÜZERİNE ETKİSİNİN İNCELENMESİ.docx', 'g20 ülkeleri için ar ge harcamalarının ekonomik büyüme üzerine etkisinin LSTM sinir ağı tahmini.docx', 'g20 ülkeleri için ar ge harcamalarının ekonomik büyüme üzerine etkisinin yapay zeka ile analizi.docx', 'iThenticate Document Viewer.pdf', 'netgöster', 'qga.py', 'quantum.py', 'quantum_cifar.py', 'quantum_cifar2.py', 'quantum_panel2.py', 'quantum_tekparametre.py', 'results_dense_initializer.csv', 'results_dense_layers.csv', 'results_dense_units.csv', 'results_learning_rate.csv', 'results_lstm_initializer.csv', 'results_lstm_layers.csv', 'results_lstm_units.csv', 'RMSE (version 1).xlsb.xlsx', 'RMSE.xlsx', 'Sunu1.pptx', 'tekparametre.py', 'yapay sinir ağı makale.pdf', '~$0 ülkeleri için ar ge harcamalarının ekonomik büyüme üzerine etkisinin yapay zeka ile analizi.docx', '~$st Model.docx', '~$Sunu1.pptx', '~WRD0122.tmp', '~WRL3927.tmp']
['$RECYCLE.BIN', '2661104_99.out', '2662014.err', '2662019.err', 'Adrasan', 'anaconda', 'AnyDesk.exe', 'Arzum elektrikli ev aletleri üreticisi.docx', 'Aynur Iphone0309-13112025', 'Aynur İphone', 'BenimVeriler.xlsx', 'Birim Ic Degerlendirme Raporu 2024 kula.pdf', 'bootTel.dat', 'bs.xlsx', 'Cdekiler', 'cifar10 results for vgg16.csv', 'cifar100 results for EfficientNetB0.csv', 'cifar100 results for inceptionv3.csv', 'cifar100 results for mobilenetv2.csv', 'cifar100 results for vgg16.csv', 'cindirilenler', 'COVID', 'COVIDCOVID_Model4(INSNext)1.json', 'COVIDCOVID_Model4(INSNext)1.keras', 'COVIDCOVID_Model4(INSNext)2.json', 'COVIDCOVID_Model4(INSNext)2.keras', 'Cudakaldır.ps1', 'cvrp_GA_MP.docx', 'data', 'Dataset', 'deeplearnin ortamı.docx', 'deeplearning.yml', 'deeplearning_quantum.yml', 'def main.docx', 'defmain.docx', 'dene', 'denegpu.py', 'Deney.xlsx', 'Drivers', 'DRV_BT_Intel_All_SZ-TSD_W11_64_V236001_20240923R.zip', 'DRV_VGA_Intel_SZ_TSD_W11_64_V3201015866_20240923R(1).zip', 'DRV_VGA_Intel_SZ_TSD_W11_64_V3201015866_20240923R.zip', 'eklenen_kod.docx', 'env.docx', 'environment.yml', 'Figure_1.png', 'GSF_PUKÖ', 'hyperparam', 'input(x).py', 'intro_to_kt', 'job.sh', 'job2.sh', 'kisiler.json', 'kisiler.xml', 'kisiler_silindi.xml', 'learning.docx', 'LS_prob', 'LUNG_Disase.py', 'Lung_Disases', 'Lung_Disaseslung_cnn_tuning', 'Lung_Disases\uf05cCOVID.h5', 'Lung_Disases\uf05cCOVID.keras', 'Lung_Disases\uf05cCOVID.wei', 'main.docx', 'Mal Bildirimi', 'mdoeller.xlsx', 'merge.py', 'miniconda.sh', 'mnist results for resnet20.csv', 'mnist results for resnet50.csv', 'mnist results for vgg16.csv', 'mnist results for vgg16.xlsx', 'mnist results for vgg16_1.csv', 'mnist results.csv', 'MobiMoverBackup', 'Model şekil.png', 'modelandtunedene.py', 'models and tune.py', 'models_and_tuner.py', 'model_structure.png', 'msdownld.tmp', 'Ortam Kurma', 'ortam.yml', 'ortam_cuda118.yml', 'output', 'pretrained', 'prog cpu', 'prog cpu.rar', 'quantum NN', 'queue -p akya-cuda', 'resnet50.docx', 'Resnet50.py', 'resnet50_best.h5', 'resnet50_finetuned_full.h5', 'results.csv', 'SW_WinRAR_W11_64_V6240_20231108R', 'SW_WinRAR_W11_64_V6240_20231108R.zip', 'System Volume Information', 'Tebligat.docx', 'Temp', 'tf215.yaml', 'tf217.yaml', 'tf218.yaml', 'tf_wsl.yaml', 'ThrottleStop_9.7.2', 'Truba.docx', 'truba_tuners.py', 'tuners.docx', 'tuners.py', 'tuners2.py', 'tuners3.py', 'Untitled-1.py', 'Untitled-2.py', 'urunler.xml', '__pycache__', '~$eplearnin ortamı.docx']
Dizin: .
Alt dizinler: []
Dosyalar: ['Best Model.docx', 'DER_N___RENME_ARACILI_IYLA_G20__LKELER_NDE_ARGE_HA.pdf', 'DERİN ÖĞRENME ARACILIĞIYLA G20 ÜLKELERİNDE ARGE HARCAMALARININ ve İLİŞKİLİ DEĞİŞKENLERİN EKONOMİK BÜYÜME ÜZERİNE ETKİSİNİN İNCELENMESİ (Pınar Hoca).docx', 'DERİN ÖĞRENME ARACILIĞIYLA G20 ÜLKELERİNDE ARGE HARCAMALARININ ve İLİŞKİLİ DEĞİŞKENLERİN EKONOMİK BÜYÜME ÜZERİNE ETKİSİNİN İNCELENMESİ.docx', 'g20 ülkeleri için ar ge harcamalarının ekonomik büyüme üzerine etkisinin LSTM sinir ağı tahmini.docx', 'g20 ülkeleri için ar ge harcamalarının ekonomik büyüme üzerine etkisinin yapay zeka ile analizi.docx', 'iThenticate Document Viewer.pdf', 'netgöster', 'qga.py', 'quantum.py', 'quantum_cifar.py', 'quantum_cifar2.py', 'quantum_panel2.py', 'quantum_tekparametre.py', 'results_dense_initializer.csv', 'results_dense_layers.csv', 'results_dense_units.csv', 'results_learning_rate.csv', 'results_lstm_initializer.csv', 'results_lstm_layers.csv', 'results_lstm_units.csv', 'RMSE (version 1).xlsb.xlsx', 'RMSE.xlsx', 'Sunu1.pptx', 'tekparametre.py', 'yapay sinir ağı makale.pdf', '~$0 ülkeleri için ar ge harcamalarının ekonomik büyüme üzerine etkisinin yapay zeka ile analizi.docx', '~$st Model.docx', '~$Sunu1.pptx', '~WRD0122.tmp', '~WRL3927.tmp']
```
