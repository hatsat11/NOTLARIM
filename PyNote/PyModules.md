# PYTHON MODÜLLERİ

## Standart Kütüphane

### os modülü

İşletim sistemi ile iletişim kurmamızı sağlayan onlarca fonksiyonu vardır.

* `os.name` İşletim siteminin ismini döndürür. Eğer windows is 'nt', linux ise 'posix' döner.
* `os.system("komut")` Sistem kabuğunda komut çalıştırır. Çok dikkatli kullanılması gerekir.
* `os.getcwd()` Mevcut çalışma dizinini döndürür.
* `os.chdir('/sunucu/günlükler')` Çalışma dizinini değiştirir.
* `os.listdir()` Çalışma dizinini listeler ve döndürür.
* `os.mkdir("dizin_ismi")` Klasör oluşturmak için kullanılır.
* `os.rename("eskiAd", "yeniAd")` Dosya ve dizinleri yeniden adlandırır.
* `os.rmdir("dizinAdi")` İçi boş dizini siler.
* `os.stat("dosyaismi")` Dosya ile ilgili bilgi döndürür.
* `os.walk("dizin")` Belirtilen dizinin altındaki dizin ve dosyaları listeleyen generator objesi döndürür. for döngüsü ile kullanılabilir.
* `os.path.exits("dosyaDizin")` Dosya yada dizinin var olup olmadığını kontrol eder.
* `os.path.isdir()` Verdiğimiz parametrenin dizinmi kontrol eder.
* `os.path.isfile()`Verdiğimiz parametre dosyamı kontrol eder.

### sys Modülü

### shutil Modülü

Dosya ve dizin işlemleri için kullanılır.

* `shutil.copyfile('veri.db', 'arsiv.db')` Dosya kopyalama fonk.
* `shutil.move('', '')`

### math modülü
### random modülü
### urllib Modülü
### time Modülü
### datatime Modülü
### sqlite3 Modülü
### threading Modülü
### logging modülü