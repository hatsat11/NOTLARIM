# PYTHON NOTLARIM

## TEMELLER

### Veri Tipleri

Pythondaki temel veri tipleri:

1. __Tamsayılar (int)__: Sınır yoktur. Yani istediğimiz uzunlukta tamsayı yazabiliriz.
2. __Reel sayılar (float)__: Sınır var. Yani belli bir uzunluktan daha fazla uzun olamaz. Eğer bu uzunluğu aşarsa overflow hatası verir.
3. __Karmaşık sayılar (x+yj)__: (a+bj) şeklindeki sayılardır.
4. __Dizeler (string)__. "string" gibi. İndis numaraları ile erişilebilir. Değiştirilemezler.
5. __tupple__: Parantezler ile tanımlanır. İndis ile erişilebilir. Farklı tip verileri barındırabilir. Değiştirilemezler.
6. __Listeler__: Tupple benzer. Köşeli parantez ile tanımlanır. Farklı tip değişkenleri barındırabilir, indis ile erişilebilirler. Tupple dan farkı ise değiştirilebilirler. Yani tekrar atama yapılabilir.
7. __Sözlükler__: Süslü parantezler ile tanımlanır. Anahtar değer şeklinde verileri saklarlar.
8. __bool__: True yada False den biri. Yani doğru yada yanlıştan biri.

* Farklı sayı tipleri kullanıldığında sonuç genel tipe çevrilir. (int+float) float tipine, (float+karmaşık) karmaşık sayıya çevrilir.

### print() ve input() fonksiyonları

python da ekrana bir şey yazdırmak için `print()` fonksiyonu kullanılır.

```python
# hello yazdırdık
print("hello world!")

# birden fazla yazıyı aralarında boşluk bırakarak yazdırdık.
print("hello", "world", "!")
```

`input()` fonksiyonu klavyeden veri girişi almak için kullanılır. Eğer input içine parametre verilerek kullanılırsa önce onu yazdırır. sonra veri girişini alır.

```python
input("Bir değer girin: ")
```

bu kod ekrana "bir değer girin: " yazdırır. sonra veri girişi için bekler.

### Yorum Satırları

python da yorum satırları # ile başlar. Bu satırlar açıklama amaçlıdır. pogramın işleyişine etki etmezler. # ile tek yorum satırı, ''' ''' ve """ """ ile çok sayıda yorum satırı oluşturulabilir.

```python
# yorum satırı
# başka bi yorum

"""
Birden fazla satıra uzayacak yorumlar bu şekilde yazılır.
başka bi satır daha

ayrıca bu yontem python da dökümantasyon içinde kullanılır.
"""
```

### Matematiksel işlemler

* `=` Atama operatörü.
* `==` Eşittir operatörü. Eğer iki değer eşitse `True`, aksi taktirde `False` döndürür.
* `+` Toplama işlemi için kullanılır.
* `-` Çıkarma işlemi.
* `*` Çarpma işlemi.
* `/` Bölme işlemi.
* `%` Kalan bulma. Yani mod.
* `**` Üs alma için kullanılır.
* `//` Bölme işlemi yapar fakat oluşan kesirli kısmı atar.

Pythonda işlem öncelikleri şu şekilde (genellikle matematikteki ile aynı):

1. `()`: Parantezler
2. `**`: Üs alma
3. `*`: Çarpma `/`: Bölme `%`: Mod `//`: Bölme(kesirsiz)
4. `+`: Toplama `-`: Çıkarma
5. `=`: Atama

Eğer öncelik eşit ise soldan işlemler soldan sağa doğru yapılır.

Pythonda aynı satırda birden fazla atama yapılabilir. `x, y = y, x` gibi. Bu sayede 3. bir değişken olmadan sayıların yerleri değiştirilebilir.

## KOŞULLAR

Python girintilere dayanan bir dildir yani girintiler blokları oluşturur. Bu yüzden girintiler önemlidir. girintiler iki nokta ':' ile oluşturulur.

* `if` eğer doğru ise bu blok çalışır.
* `elif` eğer if yada önceki elif blokları yanlış ise ve koşul doğru ise çalışır.
* `else` eğer if ve elif bloklarının tamamamı yanlış ise çalışır.

```python
if kosul1:  # : ile kod blogu oluşturduk
    print("doğru")
elif kosul2:  # yeni blok
    print("hello")
elif kosul3:
    print("elif 2")
else:
    print("else blogu")
```

Karşılaştırma operatörleri:

1. `==`: Eşitlik kontrolü yapar.
2. `!=`: Eşit değildir.
3. `>`: Büyüktür.
4. `<`: Küçüktür.
5. `>=`: Büyükeşit.
6. `<=`: Küçükeşit.
7. `in`: İçinde mi kontrolü yapar.
8. `and`: Mantıksal and işlemi.
9. `or`: Mantıksal or işlemi.
10. `not`: Tersine çeverir.

Ayrıca  0 False, 0 haricindeki bütün sayılar True dir. Aynı şekilde uzunluğu 0 olan değişkenlerde False dir. `[]  {}  '' None  0  0.0  False` gibi.

Bir kaç farklı kullanım:

```python
# eğer koşul True ise y, aksi taktirde z atanır.
a = y if kosul else z

# eğer kosul doğru ise Doğru, yanlış ise Yanlış yazdırır.
print("Doğru!" if kosul else "Yanlış")

# abartmamakta fayda var :)
SONUC = "A" if kosul1 else "B" if kosul2 else "C"
```

## DÖNGÜLER

### While Döngüsü

Döngünün şartı doğru olduğu sürece çalışan bir döngüdür. Eğer koşulu oluşturan ifadenin `False` durumuna geçmesini ayarlamazsak sonsuz döngüye girer.

```python
a = 0
while a < 10:  # 10 a kadar gidecek
    print(a)
    a += 1  # döngüyü kırmak için değişkenin değerini arttır.
```

* `break` deyimi döngüyü istediğimiz herhangi bir noktada kırmak için kullanılır.
* `continue` deyimi döngünün kalan kısmını atlayıp başa dönmesini sağlar.

### While-Else

while-else de döngü şartı yanşış olduğu taktirde else `bloğu` çalıştırılır. Eğer döngü `break` ile kırılırsa `else` bloğuda atlanır.

```python
while kosul:
    islemler
else:  # kosul yanlış olduğu zaman çalışır, else ile kırılırsa atlanır.
    islemler
```

### For Döngüsü

```python
for x in iterable_nesne:
    islemler
```

İterable nesne üzerinde yürünebilen bir nesnedir. Diziler, tupplelar, dizeler gibi. Bu nesnelerin elemanları üzerinde dolaşılabilir yani sırayla okunabilir. Dögü ilk elemandan başlayarak son elemana kadar gider. Daha fazla eleman kalmadığı zaman döngü kırılır. O andaki elemanı `x` değişkeni turar.

`range()` ve `reversed()` fonksiyonları dögülerde oldukça faydalıdır. `range()` fonksiyonu istediğimiz bi aralıkta sayı üretmek için idealdir.

* `range(baslangic, bitis, artis_miktari)`
* `range(10)` 0 dan 9 a kadar sayı üretir. 10 dahil değil.
* `range(5, 10)` 5 den 9 a kadar sayı üretir. 2. sayı dahil değil.
* `range(5, 10, 2)` 2 şer atlayarak üretir. 5 7 9 gibi.
* `range(len(A))` bir dizi yada liste üzerinde indis numaralarına göre döngü kurarken kullanılabilir. A bir liste, tupple olabilir.
* `reversed()` tersini almak için kullanılır. Listeleri tupple ları ve range ile ürettiğimiz sayıları tersten dolaşırken iyi.

## FONKSİYONLAR

fonksiyon tamınlamaları `def` ile yapılır. Sonrasında fonksiyon adı ve parametreler gelir. Geriye değer döndürmek istersek `return` deyimini kullanırız. Eğer geriye değer döndermezsek varsayılan olarak `None` döndürülür. Ayrıca birden fazde değişken döndürmekte mümkündür.

```python
def fonksiyonAdi(parametreler):
    # islemler
    return  d1, d2  # geriye değer döndürdük
```

```python
# parametrelerin varsayılan degerleri olabilir.
# varsayılan degerler sonda olmalı.
def fonksiyon2(param, param1='deger1', param2=0):
    pass  # hiç bir şey yapma
```

`pass` deyimi hiç bir şey yapma anlamına gelir. Sonra tamamlamak istediğimiz yada bi şey yapmamız gerekmediği yerlerde kullanılır.

Fonksiyonlar çağrılırken parametreler çağrılan fonksiyondaki sıraya göre verilmeli. Ama parametre isimleri ile atara yapılarak verilirse sırasız olarakta verilebilir. Parametreler sırayla verilirse buna konumla eşleştirme, eğer parametre ismiyle verilirse isimle eşleştirme denir.

Fonksiyonlar çağrılırken önce varsayılan değeri olmayan parametreler sonra varsayılan değeri olan parametreler şeklinde sırayla verilmeli. Aksi taktirde program hata verir.

```python
def fonk(p1, p2, p3="den", p4=10):
    # islemler
    return p1, p2

# konuma göre atama yaptık.
# burada sıra önemli ve karıştırılmamalı.
fonk(1, 2, 3, 4)  # dönen değeri kullanmak zorunda değiliz.

# isimle atama yapılırsa sıra önemli değil.
# p3 p4 varsayılan değerinde
x, y = fonk(p2=2, p1=1)  # geri dönen değeri kullandık
```

Değişken sayıda argüman alan fonksiyonlar tanımlanabilir. `*args` ile verilen bütün parametreler bir tupple da toplanır. Aynı şekilde `**kwargs` verilen isimli parametreler sözlükte toplanır. Bu sayede fonksiyonlar değişken sayıda argüman alabilir.

```python
def fonk1(*args):
    pass

def fonk2(**kwargs):
    pass

def fonk3(*args, **kwargs):
    pass

# verelen bütün parametreler bir tuppleda toplanır. ('asd', 3, 4, 5) gibi.
fonk1('asd', 3, 4, 5)

# verilen bütün parametreler bir sözlükte toplanır. {a:1, b:2, c:'aaa'} gibi.
fonk2(a=1, b=2, c='aaa')

# ikisini bi arada kullanmakta mümkün. (2, 'aa') {x:2, y:'bb'} gibi.
fonk3(2, 'aa', x=2, y='bb')

# doğrudan list tupple sözlüklerde * ** ile parametre olarak verilebilir.
# buna parametre çözme denir.
fonk1(*(2, 3, 'a'))
fonk1(*[2, 3, 'a'])
fonk2(**{a:2, b:'aa'})
fonk3(*(), **{})
```

### Labmda Fonksiyonları

Lambda fonksiyonları isimsiz fonksiyondur. Normal fonksiyonlara göre daha kısa ve kısıtlıdır. Ama bazı durumlarda fonksiyon nesnesi gereken durumlarda kolaylık sağlar. Temel yapısı `fonksiyon = lambda degiskenler: donusDegeri` şeklindedir. `lambda` deyimi geriye bir fonksiyon nesnesi döndürür.

Fonksiyon tanımlamasının mümkün olmadığı yada tek kullanımlık fonksiyonların gerektiği noktalarda kolaylık sağlarlar.

```python
kare = lambda x: x**2
# basit bir lambda fonksiyonu

# normal fonksiyon gibi kullanılabilir.
kare(2)

# isim verilmeden çalıştırılabilir.
# Bu kod çalışma anında fonksiyon nesnesi oluşturur.
(lambda x: x*2)(2)
```

Pythonda her şey nesnedir. Fonksiyonlar sınıflar dahil herşey. Bu sayede bir fonksiyona argüman olarak başka bir fonksiyon verilebilir. Bir fonksiyon başka bir isme atanabilir.

```python
def f():
    pass

def ff(f):
    pass

# foksiyon başka bir değişkene atandı.
a = f

# Bir fonksiyon başka bir fonksiyona parametre olarak verildi.
ff(f)

# fonksiyona lambda fonksiyonu argüman olarak verildi.
ff(lambda x: x*2)
```

### `global` Deyimi yerel ve global değişkenler

`global` deyimi ile global alanda tanımlanmış değişkenlere sınıf yada fonksiyon içinden ulaşabiliriz.

```python
a = 10

def fonk():
    global a
    a += 10
    print(a)

fonk()
print(a)
```

Python bir değişkene ulaşmaya çalıştığında önce yerel değişkenlere bakar. Sonra global değişkenlere ve en son olarak build-in değişkenlere bakar. Biz global bir değişkene doğrudan ulaşabiliriz fakat değiştirmek istediğimizde global deyimi ile belirtmemiz gerekir. Aksi taktirde python yeni bir yerel değişken oluşturur.

### Belgelendirme dizinleri

```python
def fonk():
    """Bu bir belgelendirmedir.

    fonksiyon hakkında bilgi verir.
    parametreler, dönüş değerleri, tipleri, ek açıklamalar ...
    Fonksiyon ve sınıftan hemen sonra  3 er tane tek tırnak yada 3 er tane çift tırnak ile oluşturulur.
    """
    pass

# fonksiyon nesnesinin __doc__ değişkeni ile ulaşılır.
print(fonk.__doc__)
```

### Bazı Önemli Fonksiyonlar

__map()__ Bir fonksiyon paramatre olarak bir fonksiyon ve bir liste alır. Aldığı listenin her elemanını sırayla fonksiyona parametre olarak göndererek fonksiyonu çalıştırır. Geriye bir `map` objesi döndürür. Bu obje iterabledir. Yani for döngüsünde rahatlıkla kullanılabilir.

```python
a = map(kare, [1,2,3,4,5])

print(a) # <map object at 0x7fb3e6301828>
type(a) # <class 'map'>

for i in a:
    print(i) # 1 4 9 16 25
```

---

__filter()__ fonksiyonu parametre olarak bir fonksiyon ve liste alır. Bu fonksiyon `True` yada `False` dönen bir fonksiyon olmalı. filter fonksiyonuda bu fonksiyona göre filtreleme yapar. Eğer parametredeki fonksiyon `True` dönerse listedeki elemanı kabul eder. Aksi taktirde kabul etmez. Geriye filter nesnesi döndürür. Bu nesne iterabledir.

```python
def tek_mi(sayi):
    return sayi % 2 == 1

liste = list(range(10)) # 1 den 10 a kadar liste oluşturduk.
fil = filter(tek_mi, liste)
for i in fil:
    print(i) # 1 3 5 7 9
```

---

__dir()__ fonksiyonu parametresiz kullanılırsa mevcut isim alanındaki öğeleri liste olarak döndürür. Parametre verilirse verilen parametre nesnesinin isim alanını görüntüler. Bu sayede nesne ile ilgili bilgi edinebilirsiniz. Değişkenler fonksiyonlar vs...

```python
>>> dir() # mevcut isim alanını görüntüler.
['__builtins__', 'a', 'fil', 'i', 'kare', 'liste', 'sys', 'tekmi']

>>> dir(str) # str sınıfı hakkında bilgi edindik.
['__add__', '__class__', '__contains__', '__delattr__', '__dir__', '__doc__', '__eq__', '__format__', '__ge__', '__getattribute__', '__getitem__', '__getnewargs__', '__gt__', '__hash__', '__init__', '__init_subclass__', '__iter__', '__le__', '__len__', '__lt__', '__mod__', '__mul__', '__ne__', '__new__', '__reduce__', '__reduce_ex__', '__repr__', '__rmod__', '__rmul__', '__setattr__', '__sizeof__', '__str__', '__subclasshook__', 'capitalize', 'casefold', 'center', 'count', 'encode', 'endswith', 'expandtabs', 'find', 'format', 'format_map', 'index', 'isalnum', 'isalpha', 'isdecimal', 'isdigit', 'isidentifier', 'islower', 'isnumeric', 'isprintable', 'isspace', 'istitle', 'isupper', 'join', 'ljust', 'lower', 'lstrip', 'maketrans', 'partition', 'replace', 'rfind', 'rindex', 'rjust', 'rpartition', 'rsplit', 'rstrip', 'split', 'splitlines', 'startswith', 'strip', 'swapcase', 'title', 'translate', 'upper', 'zfill']

```

---

__help()__ fonsiyonu yardım almak için kullanılır. Sınıfın amacı nedir, fonksiyonlarına ait bilgiler vs...

```python
>>> help(str) # str sınıfı ile ilgili yardım aldık.
Help on class str in module builtins:
class str(object)
 |  str(object='') -> str
 |  str(bytes_or_buffer[, encoding[, errors]]) -> str
 |  
 |  Create a new string object from the given object. If encoding or
 |  errors is specified, then the object must expose a data buffer
 |  that will be decoded using the given encoding and error handler.
 |  Otherwise, returns the result of object.__str__() (if defined)
 |  or repr(object).
 |  encoding defaults to sys.getdefaultencoding().
 |  errors defaults to 'strict'.
 |  
 |  Methods defined here:
 |  
 |  __add__(self, value, /)
 |      Return self+value.
 |  
 |  __contains__(self, key, /)
 |      Return key in self.
# bu çıktı çok uzundu. kısaltmak zorunda kaldım.
```

## VERİ YAPILARI

### Listeler

Listeler köşeli parantezler ile tanımlanır. Listeler sıralı, içinde değişik tipte veriler tutabilen veri yapısıdır.

* İterable dir
* Değiştirilebilir.
* Elemanları sayı, dize, liste, tupple, sözlük yada başka bir nesne/obje olabilir.
* İndis numaraları ile elemanlarına erişilebilir.
* Listeler dilimlenebilir. Mesela `liste[2:5]` 2. indisten 4. indise kadar olan elemanların listesini döndürür. 5 dahil değil.
* `liste[:]` listenin kopyasını döner.
* `liste[-1]` eksi indisler sondan başlar. Yani -1. indir listenin son elemanıdır.

```python
liste = [1, "qqq", 2.12, (), {}, []]
```

* `list.append()` listenin sonuna eleman ekler.
* `list.clear()` Listeyi siler bütün elemanları kaldırır. Aynısını del ilede yapabiliriz `del list[:]`.
* `list.copy()` Listeyi kopyalar.
* `list.count()` bir elemanın listede kaç kez tekrar ettiğini sayar.
* `list.extend()` bir listeyi diğer liste ile birleştirir.
* `list.index()` belli bir elemanı arar ilk bulunduğu indexi döndürür.
* `list.insert()` belirtilen konuma eleman ekler.
* `list.pop()` belirtilen elemanın verir ve listeden siler. parametresiz son elemanı verir ve siler.
* `list.remove()` belirtilen elemanı listeden siler.
* `list.reverse()` listenin sırasını ters çevirir. Doğrudan listeyi değiştirir değer döndürmez.
* `list.sort()` Listeyi sıralar. Osjinal listeyi değiştirir.
    * `list.sort(reverse=True)` Listeyi tersten sıralar.
    * `list.sort(key=abs)` key parametresine fonksiyon vererek bu fonksiyona göre sıralama yapar.

### Sözlükler

Sözlükler anahtar:değer çiftlerinden oluşan sırasız veri tipidir.

* Anahtar benzersiz olmalıdır (uniq).
* `{}` boş bir sözlük oluşturur.
* `del` deyimi kullanılarak anahtar:değer çifti silinebilir.
* `sozluk["anahter"] = "deger"` şeklinde ekleme yapılabilir.

```python
# sozkuk oluşturduk.
sozluk = {"isim":"suleyman", "soyisim":"ergen", "yas": 22}

sozluk["isim"] # 'suleyman'
del sozluk["isim"] # ismi sildi
print(sozluk) # {'soyisim': 'ergen', 'yas': 22}
```

Bazı sözlük metodları.

* `dict.clear()` Sözlüğü temizler. yani siler.
* `dict.copy()` sözlüğü kopyalar.
* `dict.update()` iki sözlüğü birleştirir.
* `dict.items()` sözlüğü iterasyona uygun hale getirir. Dögülerde sık kullanılır.
* `dict.keys()` sözlüğün anahtarlarını döndürür.
* `dict.values()` sözlüğün değerlerini döndürür.
* `dict.get("anahtar", "varsayilandeger")` Eğer eleman sözlükte yoksa varsayılan bir değer döndürmesi için kullanılır.

### Dizeler

Dize bir yada birden fazla karakterin bir araya gelmiş halidir. Değiştirilemezler. İndex numarası ile elemanlarına erişilebilir. Değiştirilemeyen string gibi düşünebilirsiniz.

```python
dize = "dize ornegi"

print(dize[2]) # z
dize[2] = f # hata verir.
```

* `in` Dizenin içinde geçiyormu kontrolü.
* `not in` dizenin içinde geçiyor ise `True` döndürür.
* `len(dize)` dizenin uzunluğunu döndürür.
* `+` Dizelerde toplama işlemi tanımlıdır. İki dizeyi birleştirir.
* `*` Çarpma işlemi tanımlı. Dizeyi çarpılan sayı kadar tekrarlar.
* `str()` diğer veri tiplerini dizeye dönüştürür. Sayı gibi.
* `dize.startswith("biseyler")` verilen dize başlangıçta geçiyor ise `True` döner
* `dize.endswith("biseyler")` verilen dize sonda geçiyorsa `False` döner.
* `dize.upper()` bütün harfleri büyük harfe çevirir.
* `dize.lower()` bütün harfleri küçük harfe çevirir.
* `dize.capitalize()` Cümlenin ilk harfini büyük harf yapar.
* `dize.swapcase()` küçük harfleri büyüğe, büyük harfleri küçüğe çevirir.
* `dize.title()` her kelimenin ilk harfini büyük harfe çevirir.
* `dize.count("biseyler")` dize içinde verilen dizenin kaç defa geçtiğini döndürür.
* `dize.find("biseyler")` dize içinde verilen dizenin ilk göçtiği yerin indexini döndürür. Eğer bulamazsa -1 döndürür.
* `dize.rfind()` ise `find()` metodu gibi. Fakat aramaya sondan başlar.
* `dize.join()` sıralı veri yapılarını dize olarak birleştirir.
* `dize.lstrip()` dizenin başındaki boşlukları kaldırır.
* `dize.rstrip()` dizenin sonundaki boşkukları kaldırır.
* `dize.strip()` dizenin baş ve sondaki boşlukları kaldırır.
* `dize.replace("bul", "degitir")` 2 argüman alır. Dizede 1. argümanı 2. argüman ile değiştirir. İsteğe bağlı olarakta 3. bi argümanla kaç öğenin değiştirileceği belirlenebilir. `replace('', '-', 5)` gibi.
* `dize.split(',')` verilen dizeye göre dizeyi ayırır. Parçalar. Bu örnekte , işaretine göre ayırır.
* `dize.splitlines()` dizeyi satır satır böler. Yani her satır bir eleman.

### Kümeler

İçinde tekrar eden eleman bulunmayan veri tipidir. Sırasızdır. Değiştirilebilen (liste, sözlük gibi) eleman içermezler.

* `set()` boş küme döndürür. `{}` boş sözlük tanımlar küme değil.
* `{1, 2, 'a', 'b'}` ile küme tanımı yapılabilir.
* `len(kume)` kümenin eleman sayısını verir.
* `eleman in kume`  gibi `in` ile kümede belirtilen eleman varmı kontrol edilebilir.
* `<=` alt küme testi.
* `<` öz alt küme testi.
* `>` ve `=>` kapsama testi.
* `|` birleşim.
* `&` kesişim.
* `-` fark işlemi.
* `^` ortak olmayan elemanlar.
* `frozenset()` Donut küme oluşturmak için kullanılır. Normal kümelerden farkı değiştirilemez olmalarıdır.
* ``kume.add()` kümeye eleman ekler.
* `kume.remove()` kumeden eleman siler. Eğer eleman belirtilen eleman yoksa hata verir.
* `kume.discard()` elemanı kümeden kaldırır. Hata mesajı vermez.
* `kume.clear()` kümedeki bütün elemanları siler.
* `kume.pop()` kumeden rasgele bir eleman döndürür ve o elemanı kümeden siler. Eğer eleman yoksa hata verir.

## ÇIKTI BİÇİMLENDİRME

`"{}".format()` ile dizeyi istediğimiz biçimlendirmeyi yapabiliriz. `{}` süslü parantezler arasına biçimlendirme ile ilgili kuralı belirterek istediğimiz biçimlendirmeyi yapabiliriz.

* `"{} {} {}".format(deger1, deger2, deger3)` Dizedeki her süslü parantez format fonksiyonundaki argümanlar ile değiştirilir. İstenirse `{2}` gibi süslü parantezler arasına sıra numarası verilebilir. Eğer verilmezse format fonksiyonu sırayla değiştirme yapar.
* `"{param1} {param2}".format(param1="", param2=23)` parametreye göre eşleştirme yapılabilir.
* `"{}".format(*liste)` * ile format fonksiyonuna liste verilebilir.
* `"{dictKey1} {dictKey2}".format(**sozluk)` ** ile format fonksiyonuna sözlük verilebilir.
* `"{0[1]} {0[2]}".format(liste)` listenin index numarasına göre eşleştirme yapılabilir.
* `{:10}` dizeyi yerleştirmek için 10 karakterlik alan ayrılır.
* `{:<10}` sola yastamak için.
* `{:>10}` sağa yastamak için.
* `{:^10}` ortaya yastamak için.
* `{:+>10}` boş kalan karakterleri + ile doldurur. Yani boş kalan alanı istediğimiz karakterle doldurabiliyoruz.
* `{0:10}` `{param:10}` iki noktadan önce index yada isimle eşleştirme yapabiliriz.
* `{:d}` `{:f}` sayılarda `d`:tamsayı `f`:float sayı olarak biçinlendirme yapabiliriz.
* `{:5d}` gibi sayı için alan ayırabiliriz.
* `{:05d}` sayının başını 0 ile doldurabiliriz.
* `{:5.2f}` virgülden sonra gelecek sayı sınırını ayarlayabiliriz.
* `{:+d}` negatif sayıların başına - gelir. Eğer pozitif sayıların başına + gelmesini istersek `d` den önce + koymamız gerekir.
* `{:b}` sayıyı 2 tabanında gösterir.
* `{:o}` sayıyı 8 tabanında gösterir.
* `{:x}` sayıyı 16 tabanında gösterir.

## DOSYA İŞLEMLERİ

* `open("dosyaismi","mod")` dosya açmak için kullanılır. Bir dosya nesnesi döndürür.
    * `r` okuma. varsayılandır.
    * `w` yazma. dosyayı siler sonra yazma işlemine başlar.
    * `a` sonuna ekleme. Dosyanın sonuna ekleme yapar.
    * ``
* `f.read()` dosyanın tamamını okur.
* `f.readlines()` dosyadaki bütün satırları okur ve listeye kaydedip listeyi döndürür.
* `f.readline()` dosyadan bir satır okur.
* `f.close` dosyayı kapatır.

```python
with open("dosya") as f:
    # bu blok boyunca dosya açık
# bloktan çıktıktan sonra dosya kapalıdır.
```

## HATA AYIKLAMA

`try: except: finally:` blokları ile hata kontrolü yapabiliriz. `try` bloğuna hata çıkması muhtemel kod yazılır. Eğer hata çıkarsa `except` bloğuna atlanır, `try` bloğunun geri kalanı atlanır. Hata çıktığında yapmak istediklerimizi `except` bloğunda yazarız. `finally` bloğuna ise hata çıksada çıkmasada çalıştırılacak kodlar yazılır.

`try except` blokları ile programda hata çıkması durumunda program aniden kapanmaz. `except` bloğuna düşer ve çalışmaya devam eder.

```python
try:
    # hata çıkması muhtemel kodlar.
except:
    # hata çıktığında yapmak istediklerimiz.
finally:
    # hata çıksada çıkmasada yapmak istediklerimiz.
```

`except` bloğunu belli bir hata için özelleştirmek mümkündür. `except <hata>:` gibi. Eğer çıkan hatayı yakalamak istersek `except <hata> as <degisken>` gibi bir kodlar hatayı değişkene atayabiliriz.

```python
try:
    # kodlar
except ValueError:
    # ValueError hatası
except ZeroDivisionError as err:
    # err degiskenine hatayı atadık. print() fonksiyonu ile yazdırabiliriz.
except:
    # hata özel except bloklarından biriyle eşleşmezse buraya düşey
```

Hatalarda birer sınıftır. Bu sebeple kendi hatalarımızı oluşturabiliriz. Bunun için `Exception` sınıfını miras almamız gerekir. Ayrıca `raise` deyimi ile hata olmasa dahi hata tetikleyebiliriz.

```python
class KendiHatam(Exception):
    pass

try:
    # raise deyimi ile bir hata çıkmasa bile hata tetikleyebiliriz.
    raise KendiHatam("kendi hatamı tetikledim")

    # başka bir hata
    raise ZeroDivisionError
except:
    pass
```

## NESNEYE YÖNELİK PROGRAMLAMA

### Sınıf Tanımlama

Sınıf tanımlamaları `class` deyimi ile yapılır. Diğer programlama dillerinde olduğu gibi sınıf nesne oluşturmak için bir taslaktır.

```python
# sınıf tanımlaması yaptık
class sinif:
    pass

# sinif'tan bir nesne oluşturduk.
nesne = sinif()
```

### `self` ve `__init__()`

* `self` deyimi bir sınıftan üretilen her nesneye ait öğeleri ifade eder.
* `__init__()` fonksiyonu sınıftan bir nesne oluşturulduğu zaman çağrılan bir fonksiyondur. Nesnenin değişkenlerine ilk değerlerini vermek için idealdir.

```python
class sinif_ismi:
    """
    Sınıflar 'class' anahlat kelimesi ile tanımlanır.
    Bu bir sınıfa ait docstring dir.
    """

    def __init__(self, x=0, y=''):
        """__init__ fonksiyonu

        nesne oluşturulduğunda çağrılan fonksiyondur.
        nesne değişkenlerine ilk değerleri atamak için idealdir.
        """
        pass

    def metod(self):
        """
        sınıfa ait bir metod.
        """
        pass

# sınıftan nesne üretmek.
# varsayılan değerler atandı
nesne = sinif_ismi()

# ilk değerler ile nesne üretmek
nesne2 = sinif_ismi(12, "deneme")
```

* Sınıfa ait fonksiyonlara metod denir. Ve nesne nesne kullanılarak çağrılırlar. İlk parametreleri sınıfa ait bir nesnedir.
* `nesne.metod()` aslında `sinif_ismi.metod(nesne)` a denktir, tamamen aynıdır. Sınıf metodlarına atanan ilk değişken nesnenin kendisidir. `nesne.metod()` kullanımında bu işlem otomatik olarak yapılır.
* Örnek değişkenleri, her bir örneğe özgü veriler içinken; sınıf değişkenleri ise sınıfın bütün örnekleri tarafından paylaşılan nitelikler ve metotlar içindir.

### Miras Alma (inheritance)

Miras alma nesneye tönelik programlamanın olmazsa olmazıdır. Python da ise bu işlemi şu şekilde yaparız.

```python
class ust_sinif:
    x = 12
    def y(self):
        print("hello")

class alt_sinif(ust_sinif):
    pass

u = ust_sinif()
a = alt_sinif()

print(a.x) # 12
a.y # hello
```

Python da mitas alma sınıf tanımlamasından sonra gelen parantezler ile yapılır. Ayrıca python çoklu miras almayı destekler.

```python
class a:
    pass
class b:
    pass
class c(a, b): # çoklu miras alma
    pass
```

### Nesne ve Sınıf Değişkenleri

Nesne değişkenleri sınıftan üretilen her nesneye özgü değişkenlerdir. Sınıf değişkenleri ise sınıfa ait değişkenlerdir ve bütün nesneler tarafından paylaşılır.

```python
class sinif:

    # sınıf değişkenleri bütün nesneler tarafından paylaşılır.
    s_d = 0

    def __init__(self):
        # nesne değişkenleri her nesneye özgü değişkenlerlerdir.
        self.n_d = 0

# 2 tane nesne oluşturduk.
a1 = sinif()
a2 = sinif()

# nesnelerin nesne değişkenlerini yazdırdık.
print(a1.n_d)
print(a2.n_d)

# sinif değişkenini değiştirdik.
# doğal olarak bütün nesneler bundan etkilenecek
sinif.s_d = 10
print(a1.s_d)  # 10
print(a2.s_d)  # 10

# a1 nesnesinin nesne değişkenini değiştirdik.
# bu işlem a2 nesnesini etkilemez.
a1.n_d = 20
print(a1.n_d)  # 20

# a2 nesnesine yeni bir nesne değişkeni tanımladık.
# bu işlem sadece a2 nesnesini etkiler.
a2.s_d = 25
print(a2.s_d)  # 25
```

Eğer sınıf değişkenleri ile nesne değişkenleri aynı isimde olursa o zaman nesne üzerinden doğrudan sınıf değişkenlerine erişmek problem olabilir. Bunu önlemek için `sinif.sinif_degiskeni` gibi sınıf üzerinden sınıf değişkenlerine ulaşılabilir. Yada isimler farklı tutulursa böyle bir problem olmayacaktır.

### `@classmethod` ve `@staticmethod`

`@classmethod` sınıfla ilişkili ve sınıf değişkenlerini kullanan metodlardır. Sınıf yada nesne değişkenleri üzerinde işlem yapan methodur.

`@staticmethod` sınıf ile ilişkili ve sınıf değişkenlerini kullanmayan metodlardır. Sınıf ile ilişkili olduğu için sınıftan ayrılması istenmediği için bu şekilde tanımlanırlar.

```python
class sinif:
    @classmethod
    def motod1(cls):
        pass

    @staticmethod
    def metod2():
        pass
```

### `isinstance()` ve `issubclass()` Fonksiyonları

`isinstance()` ve `issubclass()` fonksiyonları miras almayı kontrol eder. `isinstance()` fonksiyonu verilen nesnenin verilen sınıftan üretilmesi durumunda `True` döner; aksi taktirfa `False` döner.

```python
isinstance(12, int)
# 12 int sınıfının bir nesnesi olduğu için True döner

isinstance('12', int)
# '12' int değil str sınıfının bir nesnesi olduğu için False döner.
```

`issubclass()` verilen 1. sınıf 2. sınıfın altsınıfı ise `True` aksi taktirde `False` döner.

```python
issubclass(bool,int)
# bool sınıfı int sınıfının alt sınıfı olduğu için True döner.

issubclass(object, int)
# object sınıfı int sınıfının bir alt sııfı değildir. False döner.
```

`object` sınıfı pythonda en üst sınıftır. Bütün sınıflar object sınıfını miras alır ve her nesne object sınıfının bir örneği/nesnesi dir.

### Gizli ve Yarı gizli değişkenler

#### Açık (Public) Değişkenler

Açık değişkenler sınıf içinden ve sınıf dışından normal yollarla ulaşılabilen ve değiştirilebilen değişkenlerdir.

#### Gizli (Private) Değişkenler

`__degisken` veya `__degisken_`. Bir Değişkenin gizli olabilmesi için başında en az iki adet, ucunda da en fazla bir adet alt çizgi bulunmalıdır. Gizli üyeler yalnızca sınıf dışına kapalıdır. Yani sını dışından ulaşılamaz ve değiştirilemez. Bu değişkenlere sınıf içinden rahatlıkla erişebiliriz. Ayrıca bu fonksiyonlarda da geçerlidir.

Aslında gizli değişkenlere ulaşmanın bir yolu vardır. `_sinifAdi__degisken` şeklinde ulaşılabilir. Altçizgi+sınıfismi+`__gizlidegisken` kalıbı ile değişkene ulaşılabilir. Çünkü python gizli değişkenleri bu formata getirir. Her ne kadar gizli değişkenlere ulaşabiliyor olsakta bunu yapmamak gerekir çünkü bu değişken gizli yapıldıyda bunun bir nedeni vardır.

#### Yarı Gizli (Semi Private) Değişkenler

_yarıgizli yarıgizli değişkenler python topluluğu tarafından konmuş bir gelenektir. Değiştirilmesini engelleyen bir mekanizma yoktur fakat sınıf dışından değiştirmeye kalkışmamamız gerekir.

### `@property` Tagı

Bir sınıf öğesi gizli yapılsa dahi onu değiştirmek mümkündür. Bu durum bazen problemlere neden olabilir. Bu problemi `@property` ile çözeriz.

```python
class Celsius:
    def __init__(self, temperature = 0):
        self._temperature = temperature

    def to_fahrenheit(self):
        return (self.temperature * 1.8) + 32

    def get_temperature(self):
        print("Sıcaklık alınıyor")
        return self._temperature

    def set_temperature(self, value):
        if value < -273:
            raise ValueError("-273 derecenin altında sıcaklık mümkün değil.")
        print("Sıcaklık değiştiriliyor.")
        self._temperature = value

    # temperature değişkenini property haline getirdik.
    temperature = property(get_temperature,set_temperature)
```

Biz her ne zaman `nesne.temperature` değişkenine ulaşmaya çalışsak arkaplanda `get_temperature()` fonksiyonu çalışır. Aynı şekilde her ne zaman değer atamaya çalışsak ta `set_temperature()` fonksiyonu çalışır. Bu sayede değişkene dışarıdan doğrudan ulaşamayız.

`property()` fonksiyonunun prototipi şu şekildedir.

```python
property(fget=None, fset=None, fdel=None, doc=None)
```

* `fget` : değişkenin değerini döndüren fonksiyon.
* `fset` : değişkene değer ataması yapan fonksiyon.
* `fdel` : Değişkeni silen fonksiyon.
* `doc` : Değişkeni tanımlayan docstring.

Aynı işlemi şu şekilde daha pratik olarak yapabiliriz.

```python
class Celsius:
    def __init__(self, temperature = 0):
        self._temperature = temperature

    def to_fahrenheit(self):
        return (self.temperature * 1.8) + 32

    # property getter fonksiyonu
    @property
    def temperature(self):
        print("Derece alınıyor.")
        return self._temperature

    # property setter fonksiyonu
    @temperature.setter
    def temperature(self, value):
        if value < -273:
            raise ValueError("-273 derecenin altı mümkün değil.")
        print("Derece değiştiriliyor.")
        self._temperature = value
```

## DOCSTRING OLUŞTURMA

Docstring oluşturmak dökümantasyon için önemlidir. Çünkü yazdığınız kodları sadece siz kullanmayacaksınız. Başka insanların sizin yazdığınız kokları, modülleri, kütüphaneleri daha rahat kullanabilmesi için docstring oluşturmak şarttır.

Dünyada standartlaşmış birkaç docstring stili vardır. Bunlardan bazıları Epydoc, sphinx reStructuredText, google style, Numpydoc ... Ben kısaca sphins den bahsedeceğim.

Parametreleri belirtirken iki tane ikinakta arasına 'param' yazdıktan sonra parametre ismini girerek parametre ile ilgili açıklama yapılabilir.

* `:param parametre:` bir parametre için açıklama.
* `:type parametre: int` gibi bir ifade ile parametrenin türünü belirtebilirsiniz.
* `:param int parametre:` Parametre ve türünü daha kısa olarak bu şekilde yazılabilir.
* `:param int param1: açıklamalar` Şeklinde açıklamada eklenebilir.
* `:return:` Dönüş değeri ile ilgili açıklama
* `:rtype:` Dönüş değerinin tipi.
* `:raises ValueError:` 'raises' kelimesinden sonra fonksiyonda ortaya çıkabilecek hata türünü yazabilirsiniz.

```python
class sinif:
    def __init__(self):
        pass
    def fonk1(self, param1, param2, param3):
        """
        Fonksiyon için açıklama

        :param param1: açıklamalar
        :type param1: str
        :param param2: param2 için açıklama
        :type param2: int
        :param param3: param3 için açıklama
        :type param3: bool
        :return: None
        :rtype: None
        :raises TypeError: Foksiyonda çıkabilecek bir hata türü.
        """
        pass

    # daha kısa olarak yazılabilir.
    def fonk1(self, param1, param2, param3):
        """
        Fonksiyon için açıklama

        :param str param1: açıklamalar
        :param int param2: param2 için açıklama
        :param bool param3: param3 için açıklama
        :return: None
        :rtype: None
        :raises TypeError: Foksiyonda çıkabilecek bir hata türü.
        """
        pass

    # bu şekilde docstring e eklemeden parametrelerin türü belirtilebilir.
    # aynı şekilde dönüş değeride belirtilebilir.
    # def fonk(self, param: tip) -> donustipi:
    def fonk2(self, param1: str, param2: int, param3: float) -> bool:
        """Açıklamalar

        :param param1: açıklama1
        :param param2:  aciklama2
        :param param3: aciklama4
        """
        pass
```

Daha ayrıntılı bilgi için [www.sphinx-doc.org](http://www.sphinx-doc.org/en/master/usage/restructuredtext/) adresini ziyaret edebilirsiniz. Ayrıca [google style](https://github.com/google/styleguide/blob/gh-pages/pyguide.md#38-comments-and-docstrings) docstringi de incelemenizi tavsiye ederim. Diğer standant docstring stillerinide inceleyip size en güzel gelen tipi kullanabilirsiniz.

## MODÜLLER VE PAKETLER

Python da modüller py uzantılı herhangi bir dosyadır. Paketler ise py uzantılı dosyaların oluşturduğu birbiriyle ilişkili bir dizindir. İçlerinde çeşitli işlemler için çeşitli fonksiyolar yada modüller barındırırlar.

`import modul_adi` deyimi ile herhangi bir modülü programınızda kullanabilirsiniz. Bu modül ismi ile yeni bir isim alanı oluşturur ve modüldeki isimleri bu alana taşır. Modüldeki nesnelere nokta ile ulaşılır. `modul.f()` gibi.

```python
# modülü import ettik
import modul_ismi

# modüldeki fonksiyon ve değişkenlere ulaştık.
modul_ismi.f()
modul_ismi.x
```

`from modul import pydosya` şeklinde doğrudan programın ana isim alanına aktarılır. Nokta kullanmadan doğrudan erişilebilir.

```python
from modul_ismi import f, x

# from import kalıbı ile kendi isim alanımıza aktarıldığı için
# modul_ismi.f() diye yazmamıza gerek kalmadı.
f()
print(x)

# ama belirtmediğimiz isimleri hala modülismi ile kullanmalıyız.
g() # hata verir.
modul_ismi.g() # çalışır.
```

`from modul import *` şeklinde kullanımda modüldeki bütün nesneleri kendi isim alanımıza taşımış oluruz. Fakat bu kullanım tavsiye edilmez çünkü bizim tanımladığımız isimler ile çalışma imkanı oluşur. Şöyle ki iki tane modüu import ettik. modul1 ve modul2. İkisindede 'fonk' isminde bir fonksiyon olsaydı o zaman python hangi modüldeki fonksiyonu kullanmak istediğimizi nasıl anlayacaktı. Yada biz 'fonk' isminde bir fonksiyon tanımlasaydık? Bu tarz karışıklıkları engellemek için bu tarz kullanımdan kaçınmak gerekir.

```python
from modul1 import *
from modul2 import *

def f():
    pass

# şimdi hangi f fonksiyonu çağrılacak?
# modul1 deki mi modul2 deki mi bizim tanımladığımız mı ???
f()
```

`import paket.modul as md` kullanımında ise `as` deyimi ile modül ismini dm olarak kısaltmış olduk. Program boyunda bu ismi kullanarak modüle erişebiliriz. İsmi uzun olan modüllerde oldukça kullanışlı olabilir.

```python
# modulü r ismi ile aktardık.
import urllib.request as r

# bundan sonda modülü bu isimle kullanacağız.
r.urlopen('url')
```

## ÖNEMSİZ ŞEYLER

### Modül Metadata Değişkenleri

Yazdığınız modüllere metadata eklemek isteyebilirsiniz.

* `__author__` Modülü kodlayan kişinin ismi.
* `__copyright__` Copyright bilgisi.
* `__license__` Lisans bilgisi.
* `__version__` Modülün versiyon bilgisi.
* `__email__` Modülü kodlayan kişinin mail adresi.

```python
#!/usr/bin/env python

"""
Modül ile ilgili açıklamalar.
"""

# import işlemleri.
import os

# metadata bilgileri
__autor__ = "isim soyisim"
__copyright__ = "Copyright 2018, İsim Soyisim"
__license__ = "MIT"
__version__ = "1.2.1"
__email__ = "mail@mail.com"

# programın devamı....
if __name__ == "__main__":
    pass
```

### Awesome Python

Python kütüphaneleri, yazılımları, kaynaklarını barındıran bir github reposu. Kesinlikle incelenmesi gereken bir kaynak.

[Awesome Python Link](https://github.com/vinta/awesome-python)

## KAYNAKLAR

* [Stackoverflow Docstring](https://stackoverflow.com/questions/3898572/what-is-the-standard-python-docstring-format)
* [veridefteri python](http://www.veridefteri.com/category/python-giris/)
* [Yazbel python belgeleri](https://belgeler.yazbel.com/python-istihza/)
* [İstihza Python 3 klavuz çevirisi](https://www.python.tc/wp-content/uploads/2017/06/python-kitap.pdf)
* [www.python.tc blog postları](https://www.python.tc/)