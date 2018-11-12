# BASH NOTLARIM

Linux komutlarına çalışırken aldığım notlar. Umarım sizede faydası olur.

## Shell

Kullanıcı ile çekirdek arasında yer alır ve kullancıdan gelen komutarı yorumlayarak çekirdeğe iletir. Günümüzde en yaygın kullanılan kabuk `bash` kabuğudur.

* `echo $SHELL` sistemde kullanılan kabuk programını gösterir.
* `echo $PATH` shell bu kendisine komut geldiği zaman bu dizinlerde arar. Dizinler : ile birbirinden ayrılır. Eğer komutu bulursa çalıştırır. Bulamazsa hata mesajı verir. Ayrıca çaşıtırılabilir dosyalar `/bin` ve `/sbin` dizinlerinin altında bulurnur.
* Linux komutları küçük büyük harf duyarlıdır. Yani `ping` ile `Ping` ayrı şey değildir.

### Yardım Alma

* `help` komutu linux komutları ile ilgili yardım almak için kullanılır.
* `[komut] --help` yada `[komut] -h` komutları ile bir komutla ilgili yardım alınabilir. `ls --help` gibi.
* `man [komut]` komutu ile bir komutla ilgili dökümana/klavuza ulaşılabilir. Klavuzdan çıkmak için `q` kullanılır.

### Sistem Bilgisi

* `lsb_release -a` ile kullandığınız dağıtımla ilgili bilgi alabilirsiniz.
* `dmidecode` sistemle ilgili bilgi veren bir komuttur. Sudo yetkisi gerekir. `--type` parametresi ile belli bir şey ile bilgi alırken kullanırız.
    * `--type system`
    * `--type baseboard`
    * `--type chassis`
    * `--type processor`
    * `--type memory`
    * `--type cache`
    * `--type connector`
    * `--type slot`
* `lshw` donanım ile ilgili geniş bilgi almak için kullanılır. Bazı dağıtımlarda kurulu gelmeyebilir. Mesela kali linux da kurulu gelmiyor.
* Bir paket yok ise `apt-cache search <paketAdi>` komutu ile depolarda arama yapılabilir. Eğer depolarda var ise listelenecektir.
* Kurmak isterseniz `apt-get install <paketadi>` ile kurabilirsiniz.
* `uname -a` ile kernel ile ilgili bilgi alınabilir.
* `fdisk` Disk ile ilgili belgi alma ve disk üzerinde değişiklik yapmak için kullanılan bir komuttur.
    * `-l` disk bölümleri ile ilgili bilgi verir.
* `uptime` komutu sistemiz ne zamandan beri açık olduğunu gösterir.
* `free` sistemde kullandığımız bellek (RAM) miktarını gösterir.
    * `-h` `--human` insan için daha okunabilir. bilgi verir.
    * `-m` çıktıyı MB cinsinden verir.
    * `-g` çıktıyı GB cinsinden verir.
    * `--help` bu komut ile ilgili yardım almak için.
* `cal` komutu takvimi gösterir.
    * `cal 1995` 1996 yılına ait takvimi gösterir.

## DİZİNLER

* `pwd` o an çalıştığımız dizini gösterir.
* `ls` Dizinleri ve dosyaları listelemek için kullanılır.
    * `-l` çıktığı daha ayrıntılı ve liste şeklinde verir.
    * `-a` '.' nokta İle başlayan gizli dosyaları ve dizinleride listeler.
    * `ls [dizin]` Belli bir dizini listelemek için dizinin yolu verilebilir.
    * `-F` Çalıştırılabilir dosyaları *, linkleri @ işareti ile gösterir.
    * `-h` Dosya boyutlarını daha okunabilir gösterir.
* `cd` dizin değiştirmek için kullanılır. parametresiz kullanılırsa ev(home) dizinine gider.
    * `cd [dizin]` belli bir dizine gitmek için.
    * `cd ..` bir üst dizine gitmek için. İki nokta `..` bir üst dizini gösterir. Tek nokta `.` şimdiki dizini gösterir.
    * `cd ../..` iki üst dizine gitmek için.
    * `-` son çalışılan iki dizin arasında geçiş yapmak için kullanılır.
* `more` Uzun çıktıları sayfaya sığacak şekilde boyutlandırır. Enter tuşu ile satır satır, space(boşluk) tuşu ile sayfa sayfa atlar. q tuşu ile çıkar.
* `less` more komutuna benzer. Fakat çalışma şekli farklıdır. Verinin tamamını aynı anda okumaz. Sadece göstermesi gereken kısmı okur. Bu yüzden daha performanslıdır.
    * `f` yada `space` bir sayfa aşağı.
    * `b` bir sayfa yukarı.
    * `k` bir satır yukarı.
    * `j` bir satır aşağı.
    * `q` çıkış için.
    * `-N` satır numarasını göster.

### Bazı Pratik Bilgiler

* `clear` komutu terminali temizler. Aynı işi `ctrl + L` kısayolu ile de yapabiliriz.
* `ctrl + U` satırı temizler. bazen yanlış bi şeyler yazdığımızda uzunca backspace ye basmaktan kurtarır.
* `ctrl + C` çalışan komutu kesmek durdurmak için kullanılır.
* `exit` terminalden çıkmak için kullanılır. Aynı şeyi `ctrl + D` kısayolu ile de yapabiliriz.
* `history` komutu daha önce kullanılan komutları listeler. Daha önce kullandığımız komutlar ".bash_history" dosyasına kaydedilir. Bu dosya gizli bir dosyadır. `history` lomutuda bu dosyayı okuyarak listeler. Eğer bu dosyanın içeriği silinirse `history` komutu da çalışmaz fakat biz komutlar kullandıkça buraya kaydedilecektir.
    * `history 20` son 20 komutu listeler.
    * `-c` terminalden komut geçmişini (.bash_history dosyasını) temizler.
* `![komutNo]` ünlem işareti ile `history`komutuyla listelenen bir komutun sırasını yazarak kullanabiliriz. mesela `!242` gibi.
* Eğer son kullandığımız komutu tekrar kullanmak istiyorsak iki ünlem `!!` kullanırız.
* `!k` k ile başlayan son kullandığımız komutu tekrar çalıştırır.
* `!ke` 'ke' ile başlayan son kullandığırmız komutu tekrar çalıştırır. Komutun başını biraz hatırlıyorsak iyi bir seçim.
* `echo $HISTSIZE` ile kaç komutun saklandığını görebiliriz. Eğer istersek '.bashrc' dosyasının içinden 'HISTSIZE' değerini değiştirerek bu sayıyı değiştirebiliriz.

## TERMİNALDE BİRDEN FAZLA KOMUT ÇALIŞTIRMA

Terminalde birden fazla komut çalıştırmak için `&&` yada `;` kullanılır. Mesela `cd /var/log; ls` komutu önce bizi '/var/log' dizinini götürür ardından dizini listeler. Aynı komut `cd /var/log && ls` şeklindede yazılabilirdi.

* `>` çıktıyı yönlendirmek için kullanılır. Çıktıyı bir dosyaya yazdırmak için idealdir. Dosyanın içeriğini siler sonra yazmaya başlar.
* `>>` Çıktıyı yönlendirir. Fakat var olan dosyanın içeriğini silmez. Devamına ekleme yapar.
* * `<` dosyanın içeriğini girdi olarak almak için kullanılır.

* `||` Eğer bir komut başarısız olursa diğer komut çalışır. `lll || ls` komutu için `lll` diye bir komut yok bu yüzden başarısız olacak ve `ls` komutu çalışacak.

## AÇ KAPA REBOOT

Sistem çalışma seviyeleri yani runlavels. Linux başlatıldığında kernel belleğe yüklenir ve başlatılır, donanımlar taranır sürücü yazılımları yüklenir, root dosya sistemi mount edilir ve init programı başlatılarak sistem çalışır hale getirilir. Bunlar yapılırken runlevel ayarlanır.

Linux sistemlerde 7 farklı çalışma seviyesi vardır:

0. Hiç bir servisin çalışmadığı ve kapatma işlemlerinin başladığı seviye (halt)
1. tek kullanıcı seviyesi. Ağ servisleri çalışmaz. Sistem bakımı için kullanılabilir.
2. çok kullanıcılı çalışma seviyesi. ağ desteği yok.
3. Ağ destekli çok amaçlı çalışma seviyesi.
4. kullanılmaz. fakat kullanıcı tarafından özel olarak tanımlanabilir.
5. GUI nin çalıştığı seviye. Birçok linux dağıtımı bu seviyede başlar.
6. sistemi yeniden başlatma (reboot) seviyesi.

* `init 0` sistemi 0. çalışma seviyesine getirir. yani sistemi kapatır.
* `init 6` sistemi 6. çalışma seviyesine getirir. yani sistem reboot olacak.
* `shutdown -h now` sistem beklemeden kapatma işlemine başlar.
* `shutdown -h now+10` sistemi 10 dakika sonra kapatır.
* `halt` bu komut sistemin kapanmasını başlatacaktır.
* `reboot` komutu sistemi kapatır.
* `shutdown` komutu parametresiz olarak kullanılırsa sistem 1. çalışma seviyesine geçer.

Hangi çalışma seviyesinde hangi servislerin çalıştırılacağı ile ilgili scriptler(betikler) /etc dizini altındaki rcX.d dizini içinde bulunur. Burada X yerine çalışma seviyesi ile ilgili rakamlar gelir. Örneğin rc5.d den kasıt 5. çalışma seviyesidir.

Bu dizinlerdeki dosyalar K veya S harfi ile başlar. K ile başlayanlar bu çalışma seviyesinde durdurulacak scriptleri, S ile başlayanlar çalıştırılacak servisleri belirtir. K ve S harfinden sonra gelen sayıya göre çalışma sırası belirlenir. Daha küçük değerli scriptler önce çalıştırılır. Bir çalışma seviyesine geçildiğinde ilk önce durdurma scriptleri daha sonra da başlatma scriptleri çalıştırılır.

###### Sanal konsollar

## SERVİSLERİN BAŞLATILMASI DURDURULMASI

Sistemdeki servislerle ilgili betikler /etc/init.d dizininin altındadır.

Servisleri başlatmak durdurmak için iki farklı yol var:

1. `/etc/init.d/<servis> start|stop|status|restart`
2. `service <servis_adı> start|stop|status|restart`

Debian tabanlı dağıtımlarda server programlarını kurmak için kullanılan `tasksel` isminde bi araç vardır. parametresiz girilirse konsol gui arayüzünü başlatır.

## PROCESS (SÜREÇLER)

* `ps` komutu çalışan process leri gösterir. Bilgileri /proc dizinin altındaki gerekli dosyalardan alır.
    * `-a` bütün processleri gösterir. Arka planda çalışanlar dahil.
    * `-e` bütün işlemleri gösterir. Oturum işlemleri ve arkaplan işlemleri dahil.
    * `-u` işlemin kullanıcısını görüntüle.
    * `--help` komutla ilgili parametreleri gösterir.
    * `aux` çalışan process leri ayrıntılı olarak gösterir.
    * `alx` processleri ayrıntılı gösterir. aux den biraz farklı çıktı verir.
* `top` komutu süreçleri canlı olarak görüntüler. konsola dönmek için q tuşunu kullanın.
* `pstree` processleri ağaç yapısında gösterir.
* `kill <pid>` komutu ile processleri sonlandırabiliriz
    * `-9` ile kullanılırsa süreci zorla durdurur.
* `killall` bir işleme yada servise ait bütün işlemleri durdurmak için kullanılır.

## KULLANICI İŞLEMLERİ

* /etc/passwd dosyasında kullanıcı bilgileri bulunur.
* /etc/shadow dosyasında kullanıcı şifreleri bulunur.

Bir kullanıcı sisteme giriş yapmak istediğinde __/etc/issue__ içinde bulunan mesaj ekrana yansıtılır. Login isteminden önce gösterilecek mesajlar burada tutulur.

kullanıcı adı girildikten sonra __login__ programı çalışır ve parola bekler. Eğer parola doğru girilirse giriş yapar ve kullanıcı için tanımlanmış kabuğu (shell) çalıştırır.

* `man login` login programı ile ilgili dökümana ulaşmak için.
* sisteme her başarılı girişten sonra görüntülenen mesaj __/etc/motd__ dosyasında tutulur.
* sisteme giriş yapmış ve hala sistemde bulunan kullanıcılar __/var/run/utmp__ dosyasında listelenir. Bu dosya binary bir dosyadır. Sistem yeniden başlatıldığında yada açıldığında içeriği silinir.

* `file <dosya>` dosyanın türünü gösterir.
* `strings` dosya içindeki stringleri gösterir.
* `last` komutu ile en gon giriş-çıkışlar listelenir. Bu komut __/var/log/wtmp__ dosyasını baz alır.

Sisteme yapılan bütün bağlantılar __/var/log/wtmp__ dosyasında bulunur. bu dosya binary bir dosyadır.

### kullanıcı ekleme silme

`adduser` ve `useradd` komutları ile sisteme kullanıcı eklenebilir.

Sisteme kullancı eklendiği zaman passwd shadow dosyalarına kullanıcı ile ilgili kayıt eklenir, kullanıcı için home dizini oluşturulur, kullanıcı için group oluşturulur ve bu grubun üyesi yapılır.

__/etc/passwd__ dosyadına ait bir kayır __AAA:x:1000:1000:,,,:/home/AAA:/bin/bash__ şeklindedir. İki nokta ile birbirinden ayrılır. AAA kullanıcının ismi, x eski sürüm linuxlarda kullanıcının parolasının hash hali (şimdi parolalar shadow dosyasında bulunur), 1000 kullanıcı numarasını, 2. 1000 ise kullanıcının grubunu, virgülle ayrılan yerlerde ise kullanıcıya ait diğer bilgiler, /home/AAA ise kullanıcının home dizinini, son kısım ise kullanıcının çalışacağı kabuğu belirtir.

shadow dosyasından bir kayıt: 
___AAA:$6$ttZw7OIi$LjmBdapfyNA6kKrXnAcF1xkjnmQCGcLN3hsNrwZmEZkNPAPmoRqD9KYF5TngV60FAlecJine.Qv5v28uO2p8z.:15944:0:99999:7:::__

Bu kaydı incelediğimizde AAA kullanıcının adı, 2. bölüm kullanıcının şifresinin hash+salt halidir. bu bölüm $ işareti ile ayrılır. 1. ile 2. $ arasındaki değer hangi hash algoritmasının kullanıldığını belirtir.

* 1 ise MD5
* 2 ise Blowfish
* 5 ise SHA256
* 6 ise SHA512

2\. ile 3. $ arasındaki değer salt değeridir. Sonraki ifade ise parolanın şifrelenmiş halidir.

* `groups <kullanıcıAdı>` kullanıcıya ait grupları gösterir
* `passwd` komutu parola eğiştirmek için kullanılır. Eğer parametresiz kullanılırsa o anki kullanıcının parolasını değiştirir.
    * `passwd <kullanıcıAdı>` belli bir kullanıcıya ait parolayı değiştirir.
* `usermod` kullanıcılar ile ilgili birçok işlem yapmaya yarayan bir komuttur.
    * `usermod -L <kullanıcı_adı>` kullanıcı hesabını kilitler.
    * `usermod -U <kullanıcı_adı>` kullanıcı hesabını aktif eder.
* `who` komutu sisteme bağlı kullanıcıları gösterir.
* `whoami` sisteme giriş ismi görünür.
* `chage` şifre parametrelerini gösterir.
* `su <kullanıcı>` bir kullacının kimliğine bürünmek için.
    * `su - <kullanıcı>` kullanıcının kimliğine bürünür ve o kullanıcının kabuğunda çalışır.
    * `su` `su -` şeklinde kullanılırsa root olarak çalışır.

* host adı yani bilgisayarın adı __/etc/hostname__ dosyasında bulunur. Bu dosyanın içeriği değiştirilerek bilgisayarın adı değiştirilerbilir.
* `exit` komutu ile kullanıcının kimliğinden çıkabiliriz.
* `userdel <user>` komutu ile kullanıcı silinebilir. yani passwd ve shadow dosyalarındaki kayıtlar silinir.
    * `userdel -r <user>` komutu ile kullanıcının home dizinide silinir.
* `deluser` userdel komutu ile aynı işi yapar.

## DOSYA VE DİZİNLERE ERİŞİM

dosyalar ve dizinler __drwxrwxrwx__ şeklinde izin yapısına sahiptir. 1. harf dizinmi yoksa dosyamı olduğunu belirtir.

* __d__ directory
* __-__ dosya
* __l__ link

Yetkiler is şöyle:

* __r__ read oluma.
* __w__ write yazma.
* __e__ execute çalıştırma.

rwx rwx rwx şeklinde ayırırsak 1. rwx dosyanın sahibinin yetkileri, 2. rwx aynı grupta olan kullanıcıların yetkileri 3. ise diğer kullanıcıların yetkileri.

* `chmod` dosya ve dizin yetkilerini değiştirmek için kullanılır.
    * `chmod <ugoa> <+=-><rwxst> <dosya/dizin>` temel yapısı bu şekilde.
    * __u__ dosya ya da dizinin sahibi
    * __g__ dosya ya da dizin sahibiyle aynı gruptaki kullanıcılar
    * __o__ diğer kullanıcılar
    * __a__ herkes
    * __+__ yetki ekleme
    * __–__ yetki çıkarma
    * __=__ yetki eşitleme
    * __r__ okuma yetkisi
    * __w__ yazma yetkisi
    * __x__ çalıştırma yetkisi
    * __s__ suid biti
    * __t__ sticky bit
    * `-R` recursive yani alt dizin ve dosyalarada uygular
* aynı şeyi sayısal olarakta yapabiliriz.
    * __r__ : 4
    * __w__ : 2
    * __x__ : 1
    * rwxrwxrwx = 777
    * rwx------ = 700
    * rwxr-xr-x = 755

* `chattr` dosyaya değişiklik yapmayı engelleyen bir komuttur. root kullanıcısı bile değiştiremez. Tekrar chattr komutu ile koruma kaldırılasıya kadar.
    * `+i` dosyayı değiştirilmez yapar
    * `-i` değiştirilemez dosyayı eski haline getirir.
* `lsattr` chattr ile değiştirilmiş dosya varmı kontrol eder.
    * `-R` recursive olarak tarama yapar.

Suit biti normalde yetkimiz olmayan bir işlem için geçici yetki almamızı sağlayan bir erişim bitidir.

## PROGRAM KURMA KALDIRMA

İki farıklı paket yönetim sistemi var (debian dağıtımlarda). dpkg ve apt.

* `dpkg` Debian tabanlı dağıtımlarda kullanılan paket yöneticisi.
    * `-i <paket>` paket yani program kurmak için
    * `-r <paket>` paket kaldırmak için.
    * `-i *.deb` dizindeki deb uzantılı bütün paketleri kurar.
    * `-s` `--status` paket ile ilgili bilgi verir.
    * `--info <paket>` deb paket ile ilgili bilgi verir
    * `--purge remove <paket>` paketi konfigürasyon sosyaları ile birlikte kaldırır.
    * `--purge <paket>`

* `apt` `apt-get` repolardan paket indirip kurmak için
    * `install <paket>`
    * `remove <paket>`
    * `update` paket repolarını günceller
    * `upgrade` paketleri günceller
    * `dist-upgrade` dağıtımı yeni versiyona yükseltir.
    * `autoremove` artık kullanılmayan paketleri kaldırır.
    * `autoclean` indirilen paket cache dosyalarını siler.

* `apt-cache search <paket>` belli pakedi repolarda arar.
* `apt-cache show <paket>` paket ile ilgili bilgi gösterir

Hangi repolardan paketlerin indirileceği __etc/apt/sourcest.list__ altında bulunur.

* main: debian ana paketleri.
* contrib : katkıcıların yardımıyla geliştirilen paketler.
* non-free : özgür olmayan paketler.
* deb-src : depodaki paketlerin kaynak kodunu ifade eder.

## DİZİN OLUŞTURMA SİLME

* `mkdir <dizin>` komutu ile dizin oluşturabiliriz. 
    * `-p` alt alta dizin oluştururken gerekli

* `rm` dosya yada dizin silmek için kullanılır.
    * `-r` recursive yani alt dizinleride sil demek
    * `-ir` silerken bana sor
    * `-rf` sorgusuz sualsiz sil hepsini sil
    * `rm -rf /` bilgisayardaki herşeyi silmek için kullanın. YANİ KULLANMAYIN :)

## DOSYA İŞLEMLERİ

* `cat` komutu dosyadaki metni konsola yazdırır.
    * `cat > metin.txt` bu kullanımda dosya oluşturur ve konsoldan girdiğimiz metni dosyaya yazar. Yazma işlemini `ctrl + D` tuşuyla bitiririz.
* `tac` komutu dosyayı konsola yazdırır. Ama tersten.

* `touch <dosyaAdi>` dosya oluşturmak için kullanılır.
* `echo` ekrana yada dosyaya metin yazdırmak için kullanılır.
    * `echo "metin metin" > dosya.txt`

* `tail` dosyanın son kısımlarını görüntülemek için kullanılır.
    * `tail -n 5 <dosya>` dosyanın son 5 satırını görüntüler.
* `head` dosyanın ilk 10 satırını gösterir.
    * `-n` parametresi ile gösterilecek satır sayısı belirlenir.

* `sort <dosya>` bir dosyanın içeriğini sıralayarak gösterir.
    * `-r <dosya>` ters sıralamak için
* `wc <dosya>` dosyadaki satır, karakter, kelime sayısını gösterir.
    * `-l` satır sayısı.
    * `-c` karakter sayısı.
    * `-w` kelime sayısı.

* `nl` dosyayı satır numaraları ile yazdırır.
* `pr` dosya içeriğini sayfalara bölmek için kullanılır.

* `od` dosya içeriğini 8 sayı sisteminde gösterir.
    * `-x` 16 lık sayı sisteminde gösterir.
* `tee <dosya>` komutu yazılan ifadeyi hem konsola hemde dosyaya yazar.
* `paste <dosya1> <dosya2>` 2 dosya alır. bu dosyalardaki satırları ardışık birbirine ekler ve konsola yazdırır.

`|` operatörü komutun çıktısını bir sonraki komuta girdi olarak verir.

`` yani ters tırnak işareti arasındaki ifadeler komut olarak değerlendirilir.

* `grep` komutu dosyada belli bir metni arar.
    * `-i` büyük küçük harf ayrımı yapmaz
    * `-n` bulunan ifadenin satır numarasınıda gösterir.
    * `-v` aranan ifadenin olmadığı satırları göster.
    * `-c` satır sayısı kaç.
    * `^` ve `\<` satır başı için kullanılır. Satır başında ifade geçiyorsa. `^root` gibi.
    * `$` ve `\>` satır sonu için kullanılır. satırın sonunda ifade geçiyırsa. `aaa$` gibi.
* `cut` dosyanın bazı satır yada alanlarını listelemek için kullanılır.
    * `-d` satırları hangi karaktere göre ayıracağımızı belirledik.
    * `-f` kaçıncı parçayı göstereceğimizi belirler.
* `tr` komutu dosyadaki belli karakterleri değiştirmek için kullanılır.
    * `cat dosya.txt | tr a-z A-Z` küçük harfleri büyük harf ile değiştirir.
    * `-d` çıktıya verirken belli karakterleri yok saymak için kullanılır.
* `stat <file>` dosyanın durumu hakkında bilgi verir.
* `find` Dosya ve dizin aramak için kullanılır.
    * `-name 'dosyaadı'` dosya adını belirtmek için kullanılır.
    * `-size` dosya boyutunu göstemek için.
        * `k` Kilobayt.
        * `M` Megabayt.
        * `G` Gigabayt.
    * `-type` Dosya tipini belirtmek için.
        * `f` dosya
        * `d` dizin
        * `l` link
    * `-perm` Dosya izinlerini filtreler.
    * `-user` soya sahibine göre filtreler.
* `locate` dosya aramak için kullanılır. Fakat arama işlemini kendi oluşturduğu veritabanı üzerinden yapar. Bu yüzden veritabanı düzenli olarak güncellenmelidir.

## XARGS

Kendisinden önceki komuttan gelen çıktıyı sonraki komuta sırayla (tek tek) argüman olarak verir. Pipeline den farkı ise sunduğu extra parametreler ile daha fazla seçenek sağlamasıdır.

`find / -name *.jpg -type f -print | xargs tar -cvzf fotolar.tar.gz` komutu find ile jpg uzantılı dosyaları bulur. Xargs burada find komutundan aldığı çıktıyı sırayla tar komutuna gönderir ve tar komutu bu dosyalardan arşiv dosyası oluşturur.

## DOSYA ARŞİVLEME İŞLEMLERİ

* `tar` komutu tar arşivleri oluşturmak için kullanılır.
    * `-c` create: tar dosyası oluşturulucağını belirtir.
    * `-x` extract: tar dosyasının açılacağını belirtir.
    * `-t` Tabel of contents: bir tar dosyasının iceriğinin listeleneceğini belirtir.
    * `-v` verbose: ayrıntılı çıktı almak için kullanılır.
    * `-f` tar dosyasının ismini belirlememize imkan sağlar.
    * `-z` arşiv dosyasını gzip ile sıkıştırır.
    * `-j` arşiv dosyasını bzip2 ile sıkıştırır.
* `gzip` gzip formatında dosyaları sılıştırır.
* `gunzip` gzip ile sıkıştırılmış dosyaları açar.
* `bzip2` bzip2 formatında dosyaları sılıştırır.
* `bunzip2` bzip2 ile sıkıştırılmış dosyaları açar.

## DOSYA KOPYALAMA TAŞIMA SİLME

* `cp <kaynak_dosyalar> <hedef/dizin/>` dosya dopyalamak için kullanılır.
    * `-i` kopyalarken sorması için. aynı isimde dosya varsa onay bekler.
    * `-r` recursive. Dizinleri kopyalarken gerekli.
    * `-b` backup dosyası oluşturur.
    * `-f` işlemi yapmaya zorlar. Yani zorla yapar.
* `mv <dosya> <hedef/dizin>` dosya taşıma işlemi yapar. Yada dosyanın ismini değiştirmek için kullanılır.
    * `-f` force: taşima işlemini zorla yapar.
    * `-n` aynı isimde dosya varsa, üstüne yazılmasını engeller.
* `rm` dosya silmek için kullanılır.
    * `-r` recursive. dizin kopyalarden gerekli.
    * `-f` işlemi yapmaya zorlar. Yani zorla yapar.
    * `-i` silinecek dosyalar için tek tek onay ister.

## LİNKLER

* `ln` komutu link oluşturmak için kullanılır. Kısayol bibi.
    * `-s` sembolink link oluşturmak için kullanılır. sembolink link dosyanın/dizinin yolubu referans olır. Bu yüzden dosyayı taşıdığınızda, ismini değiştirdiğinizde yada sildiğinizde sembolink link çalışmayacaktır.

`ln` komutunda `s` parametresi kullanılmazsa o zaman hardlink oluşturur. Bu dosyanın diskteki adresini taşır. Bu yüzden dosyayı sildiğinizde, ismini değiştirdiğinizde yada dosyayı taşıdığınızda hala dosyaya ulaşabilirsiniz.

## KONSOL EDİTÖRLERİ

### Nano

Terminal tabanlı basit bir editördür. Kullanımı kolaydır. Daha önce terminalden editör kullanmadıysanız `nano` ile başlayabilirsiniz.

`nano dosya_adi.txt` şeklinde dosya oluşturup hemen yazmaya başlayabilirsiniz. Dosya ismini vermedende çalıştırabilirsiniz fakat başta dosya ismini vermek daha pratiktir.

Bazı kısayollar:

* `ctrl + G` Yardım sayfasını görüntüler.
* `ctrl + X` Nano editöründen çıkar. Eğer kaydetmediğiniz değişiklikler varsa onay bekler.
* `ctrl + O` Doyaya değişiklikleri yazar.
* `alt + U` Geri al.
* `alt + E` İleri al.

### Vim

Oldukça gelişmiş terminal tabanlı fantastik özellikleri olan bir editördür. Daha çok profesyönel kullanıcılar tarafından tercih edilir. Kullanımı `nano` ya nazaran daha zordur.

`vim` komutunu başlangıçta komut modunda başlar. Yazma moduna geçmek için `i` (insert) harfine basmanız gerekiyor.

Bazı vim komutları:

* `:q` vi editöründen çıkmak için kullanılır.
* `:q!` belgeyi kaydetmeden çıkmak için kullanılır.
* `:w` belgeyi kaydetmek için kullanılır.
* `:wq` belgeyi kaydeden ardından belgeyi kapatır ve editörden çıkar.
* `:r` bir dosyanın içeriğini imlecin olduğu konumdan itibaren dosyaya ekler.
* `:!` işareti vim editöründen komut çalıştırmak için kullanılır.
* `:r !ls` gibi bir komutla `ls` komutunun çıktısını dosyaya ekleyebilirsiniz.
* `:n` birden fazla dosya açtıysanız aralarında geçiş yapmak için kullanılır.

Ayrıca vim regex ifadelerle metin düzenlemeyede izin verir. Mesela `:s/ben/sen/g` ifadesi metinde geçen tüm `ben` yazılarınıs `sen` ile değiştirir.

## NETWORK KOMUTLARI

* `ifconfig` Network yapılandırmasını gösterir.
  * `ifconfig eth0 <ipadresi> <subnetmask>` ip yi manual yapılandırma
  * `-a` Daha ayrıntılı çıktı verir. Bütün interface leri listeler.
  * `eth1 up|down` arayüz (interface) yi aktif yada pasif eder. Bu örnekte eth1.
* `iwconfig` kablosuz ağ bağlantısı bilgilerini gösterir.
* `ping` ping gönderme işlemi
  * `-c 4` gönderilecek paket sayısını belirler. bu örnekte 4.
  * `-f` çok hızlı sayıda ping gönderir. root yetkisi gereklidir.
* `traceroute` Hedefa ulaşana kadar yolu gösterir. Icmp paketlerini kullanır.
* `netstat` ağ bağlantısı yönlendirme tablosu ile ilgili bilgi verir. 
    * `-a` Tüm TCP ve UDP bağlantıları görüntüler.
    * `-e` Gelen ve giden paket sayısının istatistiklerini görüntüler.
    * `-p` Tüm bağlantıları PID numarası ve uygulama adına göre listeler.
    * `-r` ip yönlendirme tablosunu görüntüler.
    * `-i` interface tablosunu görüntüler.
    * `netstat -antp`
* `whois` whois sorgulaması yapar.
* `nslookup` domain ip sorgulaması yapar.
* `dig` domain ip ile ilgili ayrıntılı bilgi verir.
* `host` dns lookup işlemleri için basit bir komuttur.
* `route` yönlendirme tablosu ile ilgili bilgi verir.
* `arp` arp tablosunu görüntüler.
* `wget` terminal tabanlı bir indirme yöneticisidir.
    * `-o <isim>` dosyayı farklı bir isismle kaydeder.
    * `-c` yarım kalmış indirmeleri devam ettirir.
    * `––limit-rate` indirme işlemine hız sınırı koyar.
* `curl` bir çok protokolü destekleten bir network aracıdır. 
