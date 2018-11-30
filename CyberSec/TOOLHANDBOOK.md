# tool lar

__steghideCracker__ steghide ile ŞİFRELİ olarak verilen resme bruteforce yöntemi ile şifreyi bulmaya çalışır.

__binwalk__ dosya içinde gizli dosyaları bulmaya yarar. resim için zip dosyası gibi.

__exiftool__ dosyalardan metadata okur yada yazar. Ayrıca dosyadaki metadata bilgilerini değiştirebiliriz.

__apktook__ apk dosyalarını incelemek için ideal bir araç. ctf mobile sorularında oldukça faydalıdır.

__APK EASY TOOL__ apk dosyalarını yönetmenizi decompile etmenizi derlemenizi ve imzalamanızı sağlar. apktool un gui hali gibi düşünülebilir.

__foremost__ Dosyanın header footer ve veri yapısını kullanarak dosyayı kurtar, yani geri yükler. resim dosyalarında çalışabilir. yada doğrudan disk üzerinde çalışabilir. ayrıca exe, pdf, doc, rar, mov gibi dosyalardada çalışabilir. Silinen dosyalar üzerinde.

__www.hybrid-analysis.com__ malvare analizi yapmak için online bir site. zararlı yazılımları burada test edebiliriz. sanal makineye gerek kalmadan.

__shodan.io__ google gibi arama motorudur. farkı ise sisteminde açıklık bulunan sistemleri aramasıdır. bu arama motoru ile belli bir bölgedeki ip adreslerine nmap tarama sonuçlarına, açık portlara ve buna benzer birçok bilgiye ulaşıbalilir. ve bundan çok daha fazlasınıa yapan özel bir arama motorudur.

__ida pro__ çalıştırılabilir programları assembly haline dönüştüren ve incelenmesine yarayan bir programdır.

__https://29a.ch/photo-forensics/__ stenografi ile üzerinde oynanmış resimler üzerinde inceleme yapmak için bir site. dkhost da bi soruda kullanıldı.

__http://fotoforensics.com__ stenografi resim için başka bir site

__crunch__
__aircrack__
__rsa ctf tool__
__rsa tool__

__scp__ secure copy manasına gelir. güvenli dosya transferi. 
```text
scp [-12346BCpqrv] [-c cipher] [-F ssh_config] [-i identity_file] 
    [-l limit] [-o ssh_option] [-P port] [-S program]
    [[user@]host1:]file1 ... [[user@]host2:]file2
```

__cewl__ bir web sitesindeki kelimeler ile wordlist oluşturur.
```text
root@kali:~# cewl -d 2 -m 5 -w docswords.txt http://docs.kali.org

-d: derinlik
-m: minimum kelime uzunluğu
-w: kelimelerin kaydedileceği dosya
```

__hydra__  yada __xhydra__ gui. bir network login şifresi kırma aracıdır. çok hızlıdır ve birçok protokolü destekler.