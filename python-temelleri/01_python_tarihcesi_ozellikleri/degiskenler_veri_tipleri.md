🐍 Python Eğitimi: Değişkenler ve Veri Tipleri

Bu bölümde, Python'da değişkenlerin nasıl tanımlandığını ve temel veri tiplerini öğreneceksiniz. Python, dinamik olarak yazılan (dynamically typed) bir dildir — yani bir değişkenin türünü açıkça belirtmenize gerek yoktur; Python bunu otomatik olarak algılar.
📌 İçindekiler

    Değişken Nedir?
    Değişken Tanımlama Kuralları
    Python’da Temel Veri Tipleri
        1. Sayısal Tipler
            a) int – Tam Sayılar
            b) float – Ondalıklı Sayılar
            c) complex – Karmaşık Sayılar
        2. Metin Tipleri
            str – Dizgeler (Strings)
        3. Mantıksal Tipler
            bool – Boolean
        4. Sıralı (Sequence) Tipler
            list – Liste
            tuple – Demet
            range – Aralık
        5. Eşleme (Mapping) Tipi
            dict – Sözlük
        6. Küme (Set) Tipleri
            set – Küme
            frozenset – Sabit Küme
        7. İkili (Binary) Tipler
            bytes
            bytearray
            memoryview
    Veri Tipini Nasıl Öğreniriz?
    Değişken Türünü Dönüştürme (Type Casting)
    Önemli Hatırlatmalar

Değişken Nedir?

Bir değişken, bir veriyi (sayı, metin, liste vb.) bellekte saklamak için kullanılan bir isimdir.
Python’da bir değişken oluşturmak için yalnızca değişken_adı = değer yazmanız yeterlidir.

python
1
2

Bu örnekte:

    isim adlı bir değişkene "Ahmet" metni,
    yas adlı bir değişkene 25 sayısı atanmıştır.

Değişken Tanımlama Kuralları

    Harf veya alt çizgi (_) ile başlamalıdır.
    ✅ Geçerli: ad, _puan
    ❌ Geçersiz: 2ad, @puan
    Sadece harf, rakam ve alt çizgi içerebilir.
    ✅ Geçerli: toplam_puan1
    ❌ Geçersiz: toplam-puan, toplam puan
    Python anahtar kelimeleri (örn. if, else, for) kullanılamaz.
    Büyük/küçük harf duyarlıdır.
    Ad ile ad farklı değişkenlerdir.
    Türkçe karakterler teknik olarak kullanılabilir, ancak önerilmez.
    ✅ not_ortalaması → tercih edilen
    ❌ not_ortalamasııı → okunabilirlik düşer

Python’da Temel Veri Tipleri

Python, çeşitli veri tiplerini yerleşik olarak destekler. Ana kategoriler şunlardır:
1. Sayısal Tipler
a) int – Tam Sayılar

Pozitif, negatif veya sıfır olabilen tam sayılardır. Sınırsız sayıda basamak içerebilir.

python
1
2
3
4

b) float – Ondalıklı Sayılar

Ondalık nokta içeren sayılardır.

python
1
2
3

    ⚠️ Not: 3. veya 5.0 gibi yazım da float tipindedir.

c) complex – Karmaşık Sayılar

Gerçek ve sanal kısımdan oluşan sayılardır. j sanal birimi temsil eder.

python
1
2
3
4

2. Metin Tipleri
str – Dizgeler (Strings)

Tek tırnak (' '), çift tırnak (" ") veya üçlü tırnak (''' ''' / """ """) ile tanımlanır.

python
1
2
3
4
5
6
7

Dizgeler değiştirilemezdir (immutable). Yani üzerinde doğrudan değişiklik yapılamaz.
3. Mantıksal Tipler
bool – Boolean

Sadece iki değere sahiptir: True veya False.

python
1
2
3

    Mantıksal veriler genellikle karşılaştırma işlemlerinden elde edilir:

    python
    1
    2

4. Sıralı (Sequence) Tipler
list – Liste

    Değiştirilebilir (mutable)
    Aynı veya farklı veri tiplerini barındırabilir.
    Köşeli parantez ([]) ile tanımlanır.

python
1
2
3

tuple – Demet

    Değiştirilemez (immutable)
    Aynı veya farklı veri tiplerini barındırabilir.
    Normal parantez (()) ile tanımlanır.

python
1
2
3

range – Aralık

    Sayı dizileri oluşturmak için kullanılır.
    Genellikle döngülerde (for) kullanılır.

python
1
2
3

5. Eşleme (Mapping) Tipi
dict – Sözlük

    Anahtar-değer (key-value) çiftleriyle çalışan bir veri yapısıdır.
    Süslü parantez ({}) ile tanımlanır.
    Anahtarlar benzersiz ve değiştirilemez olmalıdır.

python
1
2
3
4
5
6
7

6. Küme (Set) Tipleri
set – Küme

    Sırasız, benzersiz elemanlardan oluşur.
    Değiştirilebilir.
    Süslü parantez ({}) veya set() fonksiyonu ile tanımlanır.

python
1
2

    Aynı elemandan iki defa olmaz:

    python
    1

frozenset – Sabit Küme

    Değiştirilemez kümelerdir.
    frozenset() fonksiyonu ile oluşturulur.

python
1
2

7. İkili (Binary) Tipler

Bu tipler genellikle düşük seviyeli işlemlerde veya dosya okuma/yazma işlemlerinde kullanılır.
bytes

    Değiştirilemez bayt dizisidir.
    b öneki ile tanımlanır.

python
1
2

bytearray

    Değiştirilebilir bayt dizisidir.

python
1
2
3

memoryview

    Bellek üzerinde veriye erişimi optimize eder (özellikle büyük verilerde).

python
1
2
3

Veri Tipini Nasıl Öğreniriz?

type() fonksiyonu ile herhangi bir değişkenin veri tipini öğrenebilirsiniz.

python
1
2
3
4
5

Alternatif olarak isinstance() ile belirli bir türe sahip olup olmadığını kontrol edebilirsiniz:

python
1
2

Değişken Türünü Dönüştürme (Type Casting)

Python, veri türlerini dönüştürmek için bazı yerleşik fonksiyonlar sağlar:
Fonksiyon
	
Açıklama
	
Örnek
int()
	
Sayıya çevirir
	
int("10") → 10
float()
	
Ondalıklı sayıya çevirir
	
float("3.14") → 3.14
str()
	
Metne çevirir
	
str(42) → "42"
bool()
	
Mantıksal değere çevirir
	
bool(1) → True
list()
	
Listeye çevirir
	
list("abc") → ['a','b','c']
tuple()
	
Tuple’a çevirir
	
tuple([1,2]) → (1, 2)

    ⚠️ Dönüştürme her zaman mümkün değildir:

    python
    1

Önemli Hatırlatmalar

    Python’da her şey nesnedir → her veri tipi bir sınıf (class) olarak tanımlıdır.
    Değişkenler bellekte referanslar olarak saklanır.
    id() fonksiyonu ile bir değişkenin bellek adresini öğrenebilirsiniz.
    None özel bir değerdir ve “hiçbir şey” anlamına gelir (NoneType tipindedir).

python
1
2

📚 Özet Tablosu
Veri Tipi
	
Değiştirilebilir?
	
Sıralı mı?
	
Benzersiz mi?
int
	
Hayır
	
—
	
—
float
	
Hayır
	
—
	
—
str
	
Hayır
	
Evet
	
—
bool
	
Hayır
	
—
	
—
list
	
Evet
	
Evet
	
Hayır
tuple
	
Hayır
	
Evet
	
Hayır
set
	
Evet
	
Hayır
	
Evet
frozenset
	
Hayır
	
Hayır
	
Evet
dict
	
Evet
	
Hayır*
	
Anahtarlar benzersiz
bytes
	
Hayır
	
Evet
	
—
bytearray
	
Evet
	
Evet
	
—

    * Python 3.7+’da dict sıralıdır (ekleme sırasını korur), ancak mantıksal olarak "sıralı veri tipi" olarak sınıflandırılmaz.

🔄 Sonraki Adım

Bir sonraki bölümde, operatörler ve ifadeler konusunu ele alacağız:
→ Aritmetik, karşılaştırma, mantıksal ve üyelik operatörleri!

    ✨ İpucu: Kodlarınızı denemek için Python REPL
     veya Google Colab
     gibi çevrimiçi ortamları kullanabilirsiniz.

Yazar: [Senin Adın]
Lisans: MIT
Son Güncelleme: 📅 12 Aralık 2025
