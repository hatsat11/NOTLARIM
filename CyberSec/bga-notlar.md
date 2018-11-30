# NOTLAR

dns hijacking nedir
theharvester komutu

## 1. BİLGİ TOPLAMA

### PASİF BİLGİ TOPLAMA

hedef ile ilgili bilgi topla. bilgiyi önemini düşünmeden hepsini al.

__whois sorgusu__ bir internet sitesi ile ilgili değişik bilgiler elde edilebilen bir sorgudur. Sorgu yapabileceğiniz bazı site ve komutlar.

* ripe.net
* www.who.is
* `whois` komutu terminalden whois sorgusu yapabiliriz.
* `theharvester` komutu domain ile bilgi toplamak için kullanılabilir. arama motorları üzerinen bilgi toplar.
    * `-d` hedef site.
    * `-l` kaç sonuç içinde arama yapılacağını belirtir.
    * `-b` arama motoru {google, linkedin, ...}

### bir ipdeki domainleri keşif

* `robtex.com` sitesi domain ile ilgili çeşitli bilgiler verir. ip adresi, host ismi, routerlar vs...
* bing arama motorunda `ip:21.21.21.21` gibi bir sorgu ile o ipde barınan domainleri buluruz
* `dig` komutu

__subdomain tespiti__ nasıl yapılır

* `fierce` komutu dns zone transferi ve dns brute force ile subdomain tespit etmeyi sağlayan bir yazılımdır. kısaca subdomainleri tespit eder.
* __dnsmap__ bu araç ile ip adresi ve subdomainler hakkında bilgi alınabilir.
* __dnsmap__ whois bilgileri, reverse lookup, özel ip tanımlamaları, MX kaydı, NS kaydı, zone transfer, bind version vb.. birçok bilgi bulmaya ve bilgi olarak analiz etmenize olanak tanır.

__archive.org__ sitesi internetteki sitelerin düzenli olarak yedeklemesini alıp saklayan bir web sitesidir. sitede eskiden bulunan önemli bilgileri bulmak için idealdir.

__netcraft.com__ hedef sistemle ilgili bilgi verir. işletim sistemi uptime süresi gibi önemli bilgiler verir.

* kaynak kodu incele. yazılımcılar bi şeyler unutmuş olabilir.

__kişilere ait bilgi TOPLAMA__
www.shodan.io internette zaafiyetli cihazları tarayan bir servis.
pastebin.com önemli bilgile bulunabilir
pipl.com insanlar hakkında bilgi toplamak için kullanılan bir site.
tineye.com bir resim üzerinden arama yapmak için özelleştirilmiş bir site.

__google hacking__ google üzerinden özel parametreler ile arama yapmak
googlehacking: google üzerinden advanced arama yapmak
goolagscanner
google hacking database: googledorks
sitedigger aracı

__serversniff__ bilgi toplamak için başka bir site.
hackertarget.com
pentest-tools

__nikto.pl__ perl ile kodlanmış hedefte zaafiyet taraması yapan bir araçtır. Kendi veritabanında binlerce açık ve zaafiyet bulunur.

__alt dizinleri keşfetme__
`dirb` sitedeki dizinleri tespit eden bir araçtır.
`dirbuster` dizinleri tespit eder.

### AKTİF BİLGİ TOPLAMA

__ids__: saldırı tespit etme sistemi. Ağdaki anormallikleri tespit eder ve kayıt eder.
__ips__: saldırı önleme sistemi. saldırıyı tespit eder ve engeller.
__waf__: web app firewall sqlinjection xss session hijacking gibi saldırı ları tespit ederler ve önlemeye çalışırlar. yerel ağda işe yaramaz.

__traceroute__ komutu bir internete bağlı bir cihaza ulaşıncaya kadarki yolu gösterir. * işareti görülenler ise engellidir. sonuç dönmez. güvenlik önlemi olarak.
__tcptraceroute__ tpc kullanan traceroute
__intrace__ tracuroute komutuna benzer bir komut. yol boyunca hub ların sayısını numaralandırır.
__hping__ komutu bi tür ping komutudur. hedef sisteme istenilen sayıda tcp paketi gönderir. normal ping komutuna göre çok daha gelişmiştir. network keşif  ve bilgi toplama aracı olarak kullanılabilir. port taramasıda yapılabilir.

__ips keşfi__ 404 dönüyorsa ips yok, timeout alıyorsan ips var. yani bir cevap dönüyorsa ips yok. cevap dönmüyorsa ips var denilebilir.
__wafw00f__ komutu güvenlik duvarı ips tespiti için kullanılır. kullanımı oldukça basittir.

__dns__ bilgi toplama: kuruma ait ip adresileri ve servisler tespit edilebilir. nslookup dig gibi araçları kullanılabilir.
__nslookup__ hedef domaine ait dns kayıtlarını sorgular.
__dig__ dns kayıtlarını sorgular. nslookup a göre daha gelişmiştir.

__nmap scripting engine__ normal nmap komutları ile yapılamayacak veya zor yapılacak işlemler için kullanılır.
__zone transferi__  dns kayıtlarının başka bir dns sunucusuna aktarılmasıdır.
smtp ile bilgi toplama
eposta başlık bilgileri
__mxtoolbox.com__ bir ip adresinin email blacklist te düşüp düşmediğini kontrol edebilirsiniz.

__snmp açıklıkları__
snmpenum
snmpwalk
__metagoofil__ aracı hedef sistem hakkında döküman arayan bir araçtır. bu belgelerin metadataları ile bilgi toplar.
__foca__ metadata analizi: hedef web sitesi üzerindeki belgeleri toplayarak metadata analizi yapar. Office dosyaları ve birçok dosya türünü arama motorları aracılığı ile bulur, indirir ve analiz eder. Google, bing ve duckduckgo arama motorlarını kullanır.
__maltego__ yazılımı grafik arayüzüne sahip oldukça gelişmiş bir bilgi toplama aracı.

## BÖLÜM 2 AĞ KEŞİF ÇALIŞMALARI

port tarama
nmap komutu
nc komutu ve port tarama
scapy hping
angry ip scan
foundstone superscan
netcat telnet
fping
telnet komutu

__namp scan turleri__ nelerdir.

* -sP: herhangi bir port tarama yapmadan up down sistemleri listele
* -sS: syn scan
* -sT: connect scan
* -sF: fin scan
* -sA: ack scan
* -sU: udp scan
* -sV: version scan
* -sL: list scan host listesini oluşturur tarama yapmaz
* -O -A: os detection

NSE nmap script engine ile script çalıştırma

açık port: syn; syn+ack; rst
kapalı port:syn; rst+ack

syncookie
synproxy

## BÖLÜM 3

common vulnabilities and exposures
cve nedir
cvss risk seviyeleri
nessus yazılımı
openvas

## BÖLÜM 4

__exploit__ varolan bir güvenli zaafiyetini istismar ederek sisteme sızmaya yol açacak yazılım/script.

* local exploit
* remote exploit
* dos exploit: sistemi erişilemez kılan exploit dir. Diğerlerine nazaran daha az tehlikelidir.
* zero-day exploit

payload
shellcode

msfconsole temel komutlar:

* `?` yardım menüsü
* `back` bir adım geriye dön
* `banner` açılış bannerini göster
* `cd` dizin atlamak için kullanılır.
* `color` renk seçeneklerini ayarlar.
* `connect` uzak sunucu ile bağlantı kurar.
* `exit` çıkış yap
* `help` yardım menüsü
* `info` modül hakkında bilgi verir.

## BÖLÜM 5

__meterpreter__ metasploit deki payloadlardan bir tanesidir.
__pivoting__ bir sisteme sızmadan önce o sisteme doğrudan erişimi olan bir bilgisayarı ele geçirip o bilgisayar üzerinden sızmaktır.
__mimikatz__ windows sistemlerde kullanıcı şifre ve sarbaros biletlerini almak için kullanılan bir araçtır.
__ettercap__
hijacking
__openssh__ normal ssh ın açık kaynak hali.

## BÖLÜM 6

ssl sarmalayıcı
stunnel
pasif/aktif sniffing
snoop
snort
dsniff
TCPDUMP
hping taraması
ngrep

## BÖLÜM 7

sosyal mühendislik

emkei.cz üzerinden sahte email gönderilir.

## BÖLÜM 8

firewall
ids ips
waf
dos ddos engelleme
anti-vürüs anti-spam
dlp
log ve monitoring

packet filter
proxy filter
stateful firewall
application firewall

dmz firewall

fpsense m0n0wall endial firewall
linux iptables

## BÖLÜM 9

__waf tespiti__. `wafw00f` aracı ile yapılabilir.

güvenlik duvarı atlatma
encoding
tünelleme çeşitleri ssh icmp dns smpt http
dns tünelleme
web tunnel
ssh tünelleme
socks/http proxy
HTTP TÜNELLEME
DNS tünellme

__snort__ gpl lisanslı ids/ips programı
__kismet__ kablosuz ağ dinleme izleme yazılımı. 
__veil framework__ antivirüs atlatmak için framework. encoding yöntemleri kullanır.

## BÖLÜM 10

http türleri delete put post get
webdaw

## BÖLÜM 11

trace.axd
google hacking
owasp dirbuster
wfuzz
owasp zap
tamper data
paros, web scarap, firefox http tamper
firecat
sanitize nedir
XSS NEDİR
    reflected
    stored
    dom based
myscape worm
owasp zenotix xss test framework

## BÖLÜM 12

girdi yönetimi ve kontrolü
SQL injection
    kör blind
    zaman tabanlı
    union
    hata tabanlı
    out of band
html encoding
url encoding
sqlmap absinthe pangolin
remote file inclusion
local file inclusion
fmap
command injection
csrf saldırısı nedir
idor açıklığı
remote code execution
waf çalışma yapısı
    positive sec model
    negative sec model
    öğrenme tabanlı
rot 13