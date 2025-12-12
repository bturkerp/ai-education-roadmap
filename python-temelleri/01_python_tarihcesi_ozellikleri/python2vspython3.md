# Python 2 vs Python 3

Python 2 ve Python 3, Python dilinin iki ana sürümüdür.  
Python 2 artık resmi olarak **2020 yılında desteklenmemektedir**, bu nedenle yeni projelerde Python 3 kullanılması önerilir.  

Bu dosya Python 2 ve Python 3 arasındaki temel farkları, örnekleri ve geçiş ipuçlarını içerir.

---

## 1. Print Fonksiyonu

**Python 2:**

```
python

print "Merhaba, Dünya"
```
Not: Python 3’te print bir fonksiyondur ve parantez zorunludur.

## 2. Integer Bölme

**Python 2:**
```
python

print(5 / 2)   # 2
print(5 // 2)  # 2
print(5 / 2.0) # 2.5
```

**Python 3:**
```
python

print(5 / 2)   # 2.5
print(5 // 2)  # 2
```

Python 3’te / her zaman float döner, tam sayı bölme için // kullanılır.


