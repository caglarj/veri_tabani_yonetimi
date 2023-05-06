# VERİ TABANI YÖNETİM SİSTEMLERİ

## Birlikte Düşünelim

Çok miktarda veriye sahip organizasyonlar, aradıkları veriyi kolayca
nasıl bulabiliyorlar?
>
İlişkisel veri modeli konsepti ilişkisel veri tabanı yönetim
sistemlerine dönüşürken ne tür süreçlerden geçmişlerdir?
>
Neden çok sayıda ilişkisel veri tabanı yönetim sistemi ihtiyacı
oluştu?
>
İlişkisel veri tabanı yönetiminde kullanılan dil olan SQL, neden bazı
veri tabanı yönetim sistemlerinde ek özellikler kazanmaktadır? Bunun
avantaj ve dezavantajları nelerdir?
>
Birden fazla tablo üzerinde aynı anda sorgu yapmak ve sonuçları
birleşik olarak göstermek için SQL yeterli midir?
>
Hangi durumlarda SQL, programlama dilinin gücünden faydalanmalıdır,
hangi durumlarda tek başına SQL sorgusu ile sonuca ulaşılabilir?
>
Yalnızca SQL kullanılarak bir bilgisayar programı yazılabilir mi?

## Başlamadan Önce

Veri tabanı kavramsal bir gerçekliktir. Bir veri tabanını işler hale
getiren uygulama örneklerine ise veri tabanı yönetim sistemi (VTYS)
adı verilir. VTYS, verinin toplanması, kaydedilmesi ve işlenmesiyle
ilgili yazılım bileşenlerini içerisinde bulunduran, SQL dilini
destekleyen yazılımlardır. Her bir VTYS genellikle bir yönüyle öne
çıkmaktadır. Hız, kapasite, ölçek, veri saklama yöntemi ve benzeri
birçok açı, farklı VTYS için tercih sebebi olabilir.
>
Bu bölümde en sık kullanılan VTYS'leri ve özelliklerini ele alacağız.
Beklentimiz, bir sistem inşaası sırasında hangi VTYS'nin daha
avantajlı olacağının belirlenmesi konusunda bilgi tabanı
oluşturmaktır. Geliştirilen sistemin altyapısı, özellikleri ve hayati
önem taşıyan tarafları belirlendiği takdirde en uygun VTYS kolayca
seçilebilir.
>
Bölüm içerisinde yer alan VTYS'ler, güncel istatistiklere göre en sık
kullanılan sistemler olmakla birlikte kullanım oranlarına göre
sıralanmışlardır. Bu sebeple bahsedilen tüm VTYS'ler hakkında genel
bilgiye sahip olmanız, profesyonel hayatta ihtiyaca yönelik tercih
yapabilmeniz konusunda sizi yönlendirebilecektir. Her bit VTYS için,
kullanım denemesi yapılabilecek grafik arayüz aracı önerisinde de
bulunulmuştur. Herhangi bir sistemi kendi web sitesinden indirerek
bilgisayarınızda denemeler yapabilirsiniz.

## Veri Tabanının Yönetimi

Codd tarafından 1969 yılında önerilen ilişkisel veri modeli ve 1970'te
ilişkisel veri tabanı idi. Bu önerinin üzerine yıllar boyunca çeşitli
çalışmalar gerçekleştirildi. Avantajlar ve dezavantajlar tartışıldı.
En nihayetinde yapılan tüm çalışmalar; ilişkisel veri tabanlarının
nasıl çalışacağı, hangi kurallara uygun geliştirileceğini, nasıl
dokümante edileceğini, farklı programlar ya da araçlar vasıtasıyla
nasıl kullanılacağı gibi sorunlara çözümler önerdiler. İlişkisel veri
modelinden önce yaygın olarak kullanılan CODASYL sistemi,
geliştiricileri pek de memnun etmiyordu. Karmaşık ve zordu. Codd bir
IBM çalışanı olduğu için önerisinin genel bir yaygınlığa ulaşması
biraz zaman aldı. 1974'te yeni bir sorgu dili olan QUEL ortaya
çıkarıldı. Kısa bir süre sonra da geliştirildi ve SQL adını aldı.
>
İlişkisel veri tabanlarının benimsenmesi yıllar boyunca sürdü. Ortada
bir konsept bulunmaktaydı ancak mantıksal olarak tartışmalar
yapılıyordu. Bunun pratiğe dökülmesi için eldeki verinin ilişkisel
veri tabanı kuramlarına bağlı olarak saklanması ve işlenmesini
sağlayan yazılımlara ihtiyaç duyulmaktaydı. Veri tabanı yönetim
sistemi (VTYS) kavramının ortaya çıkışı ve karşıladığı ihtiyaç da tam
olarak bu noktadadır. VTYS, verinin saklanması ve işlenmesiyle ilgili
etkili bir yol sunan yazılımlardır.
>
Zaman içerisinde çeşitli VTYS'lerin ortaya çıktığını gözlemlemekteyiz.
Bu çeşitlenmenin temelde iki sebebi var. Birincisi, veri tabanının
kullanılacağı platforma en uygun VTYS'yi geliştirmek; ikincisi ise
çeşitli ek özellikler ile diğer VTYS'lere göre daha performanslı
yazılımlar ortaya çıkartmak.
>
Bu noktada özgür yazılım felsefesinin katkısını da es geçmemek
gerekmektedir. Günümüzde son kullanıcılar özgür yazılım (free
software) ve açık kaynak kodunu (open source) ücretsiz dağıtılan
yazılımlar olarak algılamaktadırlar. Bu yazılımların ücretsiz olması,
özgür yazılım dünyasının çıktılarından yalnızca bir tanesidir.
Buradaki “free” kelimesinin ücretsiz değil özgür anlamıyla
yorumlanması gerektiğini unutmayalım. Özgür yazılım, geliştiricisinin
kullanıcısına çok geniş yetkiler tanıdığı bir yazılım türüdür.
>
Linux işletim sisteminin ortaya çıkması sürecinde tanımlanan GNU
lisansı, bugün birçok yazılım için kullanılmaktadır. Ayrıca başka
diğer özgür yazılım lisansları da ortaya çıkmıştır. GNU, temelde
kullanıcıya 4 özgürlük sunar:
>
Özgürlük 0: Herhangi bir amaç için yazılımı sınırsız kullanma Özgürlük
1: Yazılımın kodlarını inceleyebilme
>
Özgürlük 2: Yazılımı dağıtabilme
>
Özgürlük 3: Yazılımı değiştirerek, değiştirilmiş kopyayı dağıtabilme
>
Özgür yazılımlar, genellikle bir topluluk tarafından geliştirilen;
geliştirme aşaması dahil tüm aşama ve dosyalarının herkese açık olarak
paylaşıldığı yazılımlardır. En büyük avantajı, sayısız gönüllü
yazılımcının hatasız bir yazılım geliştirebilecek olmasıdır. İkinci en
büyük avantaj ise elbette özgür olarak geliştirilen bir yazılıma
herkesin ücretsiz olarak erişebiliyor olmasıdır. En büyük dezavantaj
ise bir şirketin olmaması sebebiyle yazılımın savunucusunun
bulunmaması; bu görevin kendi topluluğu tarafından üstlenilmiş
olmasıdır. Bir özgür yazılım, topluluğu tarafından terk edilirse
geliştirme süreci doğallıkla sona ermiş olacaktır. Bugün, tüm
ölçeklerde en çok kullanılan ikinci VTYS olan MySQL bu şekilde
geliştirilmiş, 2009 yılında Oracle firması tarafından satın alınmış
(MySQL'e sahip olan firma olan Sun'ı satın alarak) bir yazılımdır. En
çok kullanılan yazılımın da Oracle Database olduğu düşünülürse VTYS
dünyasında güncel olarak en büyük firmanın Oracle olduğu söylenebilir.
>
Bilgisayar programcılığı bölümü okuyan ve bu işi (umuyorum)
profesyonelleştirmek isteyen bireyler olarak özgür yazılımın
yazılımcıya nasıl bir getiri sağlayabildiği sorusu zihinlerinizde
canlanmıştır. Özgür yazılım felsefesini destekleyen ve gelir modeli
oluşturan iki temel unsur bulunmaktadır. Öncelikle bu tür yazılımları
geliştirmek bir sosyal proje olarak da görülebilir. Yalnızca firmalar
tarafından çözümlerin üretildiği bir dünyada fiyat rekabeti oluşturmak
ve yazılımcılara ihtiyaç duyulan yazılımı sunmak pek de kolay
olmamaktadır. Linux işletim sistemi Windows ve Unix işletim
sistemlerinin pazarı domine ediyor olmasına bir tepki olarak ortaya
çıkmıştır. Bugün gelinen noktaya baktığımızda bilgisayarlarda Linux
işletim sistemi kullanmak oldukça yaygın olarak tercih edilen bir
yöntemdir. Mobil cihazlara baktığımızda ise bu durumun çok daha göz
önünde olduğunu görmekteyiz. Piyasadaki en büyük payın sahibi olan iki
mobil işletim sistemi olan Android ve iOS'tan; Android, Linux tabanlı
bir özgür yazılımken iOS, Apple firmasına ait lisanslı ve özgür
olmayan bir işletim sistemidir. iOS işletim sistemi yalnızca Apple
cihazlarda kullanılabilirken Android, dileyen tüm firmalar tarafından
özelleştirilerek kullanılabilen bir yazılımdır. Gelir modeli konusuna
geldiğimizde ise, bu yazılımların geliştirilmesinden sonraki tüm
süreçlerin desteklenmesi örnek verilebilir.
>
Özgür yazılımı kolayca edinebilirsiniz. Ancak o yazılımı kurmak,
kullanmayı öğrenmek, problemsiz güncellemeler gerçekleştirmek uzmanlık
gerektiren süreçlerdir ve bu konularda genellikle ücretli
danışmanlıklar alınır. Özgür yazılım dünyasının gelir modeli büyük
ölçüde bu süreçlerin özel sektöre ücretli olarak sunulmasıyla
gerçekleşmektedir.
>
Bu bölümde çeşitli VTYS yazılımlarını inceleyecek ve öne çıkan
özelliklerini vurgulayacağız. Böylece tasarladığınız bir veri tabanını
yazılıma dönüştürürken hangi VTYS'den faydalanmanız gerektiği
konusunda daha bilinçli bir tercih gerçekleştirebilirsiniz.

## Oracle Database

Oracle, ağırlıklı olarak B2B (business-to-business, işletmeden
işletmeye) alanda hizmet gösteren bir firmadır. Veri tabanları üzerine
özelleşmiş, işletme ihtiyaçlarını karşılamak üzere çeşitlendirilmiş
yazılım ürünleri ve bu yazılımları sunan hizmetleri bulunmaktadır.
Firma, otonom ve yüksek performanslı veri tabanı çözümleri
sunmaktadır.

<img src="./media/image3.jpeg"
style="width:6.27083in;height:4.22917in" />

Oracle Database tarafından sunulan bazı avantajlar şu şekilde
listelenmektedir:

- Güvenli bir veri tabanı elde etmek için karşılaşılan karmaşıklık,
  Oracle Database sayesinde aşılmaktadır. Bir sistem, az sayıda
  kullanıcının az sayıda işlemine hizmet vermesi durumunda kullanılan
  altyapı hayati önem arz etmeyebilir. Ancak geliştirilen sistemin
  kullanıcı sayısının sürekli artacak olması öngörülüyorsa
  ölçeklenebilirlik kavramı da dikkate alınmalıdır. Oracle Database,
  özellikle ölçeklenebilirlik ve yüksek performansı aynı anda sunması,
  iyi bir seçenek olmasına olanak sağlamaktadır. Oracle Database altında
  otonom veri ambarı, otonom kayıt işleme ve otonom JSON veri tabanı
  ürünleri bulunmaktadır.

- Oracle Database'in, Exadata adı verilen bir platform üzerinde
  çalıştırıldığında rakiplerine göre 3 kat daha hızlı olduğu
  belirtilmektedir. Kayıtların işlenmesi, işletme analitiği ve diğer
  enformasyon teknolojileri işlemleri bu kapsamda
  hızlandırılabilmektedir. Exadata platformu, bu hizmetlerden
  faydalanacak olan sistem sahibinin kendi veri merkezinde
  çalıştırılabileceği gibi Oracle tarafından sunulan bulut altyapı
  (Oracle Cloud Infrastracture) üzerinde de çalıştırılabilir.

- Her sistemin, kullanıcılarına sunduğu özellikler farklılaşabilir ve
  bazı özelliklerin öne çıkması istenebilir. Örneğin bulut dosya saklama
  sisteminde kapasite oldukça önemlidir. Ancak çevrimiçi oyun ya da
  kişilerin anlık etkileşimde oldukları sistemlerde sistem gecikmesinin
  düşük olması öne çıkacaktır. Bir kullanıcının sisteme gönderdiği bir
  isteğe ne kadar sürede yanıt aldığı bazı projeler için proje
  başarısını doğrudan etkilemektedir. Sistem gecikmesi (latency), Oracle
  Database tarafından da dikkate alınan bir konudur. Daha önce anılan
  Exadata platformu, gecikmelerin en aza indirilmesi konusunda fayda
  sağlamaktadır.

- Güncellemeler, yazılım geliştiriciler için büyük önemdedir. Kullanılan
  bir servisin bir güncelleme alması ve bu güncellemeyle birlikte bazı
  değişiklikler gerçekleştirmesi neticesinde sistemin işleyişinde
  çeşitli aksaklıklarla karşılaşılabilir. Oracle Database,
  geliştiricinin bir sürümü tercih etmesi ve özellikle bir sürümü
  kullanarak geliştirme yapmasını mümkün kılar. Böylece yeni sürümler,
  özellikle uygulanmadığı sürece sistemin işleyişini tehlikeye
  atmayacaktır.

- İlişkisel veri tabanları, yapılandırılmış veriyi saklamak için en
  etkin yöntemdir. Ancak günümüzde sosyal medya ve web sitelerinden
  toplanan bilgiler belli bir şablona uymadığı için yapılandırılmamış
  kabul edilmekle birlikte miktar olarak büyük yer kaplamaktadır. Oracle
  Database, JSON biçimini destekleyen bir altyapıya sahiptir. Böylece
  doküman tabanlı, yapılandırılmamış büyük verinin saklanması için de
  Oracle Database'den faydalanılabilir.

- Oracle Database, Oracle firmasının sahibi olduğu MySQL veri tabanını
  bir bulut hizmet olarak sunabilmektedir. Ayrıca MySQL veri tabanının
  yeteneklerini, sunulan altyapı hızlandırma eklentileriyle birlikte
  daha performanslı hale getirdiklerini belirtmektedirler.

- Oracle Database; NoSQL, doküman tabanlı ve anahtar-değer veri
  modellerini destekleyebilmektedir.

## MySQL

MySQL veri tabanı, açık kaynak kodlu olarak geliştirilen, SUN
firmasına aitken Oracle'ın SUN firmasını satın almasıyla birlikte
Oracle bünyesine geçen bir VTYS'dir. İlişkisel veri tabanı oluşturmayı
ve yönetmeyi destekleyen MySQL, çoğunlukla Linux işletim sistemi
üzerinde, PHP diliyle yazılmış web uygulamaları ile birlikte
kullanılmaktadır. YouTube, Facebook, Twitter, Netflix, Uber gibi
birçok firma MySQL'den faydalanmaktadır.
>
MySQL, HeatWave adı verilen bir sürümü ile bulut hizmet olarak
sunulmaktadır. Bu sürüm; OLTP, OLAP ve makine öğrenmesi uygulamaları
için kullanılabilir bir yapı sunmaktadır. Resmî web sitesinde verilen
sayılara göre MySQL HeatWave, birçok rakibine göre çok daha hızlıdır.
>
MySQL veri tabanları, birçok veri tabanı yönetim aracıyla uyumlu olsa
da sıklıkla birlikte kullanılan yazılımlar bulunmaktadır. Bu
yazılımlardan, internet tabanlı çalışan phpMyAdmin, yazılım olarak
çalışan ise MySQL Workbench'tir.

<img src="./media/image4.jpeg"
style="width:5.29167in;height:3.35417in" />

phpMyAdmin PHP diliyle yazılmış, veri tabanını web üzerinden yönetmeyi
sağlayan özgür yazılımdır. MySQL ve MariaDB veri tabanlarını
desteklemektedir. phpMyAdmin sayesinde doğrudan SQL komutları
çalıştırılabilir ya da arayüz üzerinden birçok veri tabanı yönetim
işlemi gerçekleştirilebilir.
>
<img src="./media/image5.jpeg"
style="width:6.30208in;height:4.13542in" />
>
MySQL Workbench, veri tabanı mimarları, geliştiricileri ve
yöneticileri için hazırlanmış bütünleşik bir görsel araçtır. Veri
modellemeyi, SQL komutları yazmayı ve yönetimsel birçok eylemi
gerçekleştirmeyi sağlamaktadır.

## Microsoft SQL Server

Eski adıyla Sybase SQL Server, Microsoft firması tarafından satın
alındıktan sonra Microsoft SQL Server olarak hizmet vermeye
başlamıştır. Microsoft ekosistemiyle birlikte sıklıkla kullanıla
VTYS'dir. Microsoft Windows üzerinde C++ ve C# gibi programlama
dilleriyle sıklıkla kullanılmaktadır. Ancak son zamanlarda sunulan
yeni güncellemelerle Microsoft ürünlerinin Windows dışındaki işletim
sistemlerinde de kullanılabilmesi mümkün hale getirilmiştir. Microsoft
SQL Server, bulut hizmet olarak da sunuluyor olmakla birlikte, yapay
zekâ içeren bazı sürümleri sebebiyle geliştiricilerin bulut hizmetten
faydalanması motive edilmektedir. Microsoft, SQL Server'ın veri
üzerinde otomatik olarak makine öğrenmesi algoritmaları
çalıştırabiliyor olmasını ön plana çıkartmaktadır.

<img src="./media/image6.jpeg"
style="width:6.30208in;height:3.16667in" />

Microsoft SQL Server'ın birkaç özel sürümü bulunmaktadır. Datacenter
adıyla veri merkezlerinde yüksek işlemci sayısını ve hafızayı
destekleyen; Enterprise adıyla ihtiyaca göre özelleştirilmiş
bileşenleri içeren yüksek kapasiteli bir sürümü; Web adıyla
yazılımların web sürümleri için daha hafif ancak performanslı bir
seçeneği; Workgroup adıyla en temel özellikleri barındıran bir
sürümünü; Express adıyla kısıtlı donanım imkanları altında çalışan
ücretsiz bir seçeneği sunmaktadırlar. Ayrıca Standard adlı seçenek ile
bazı özelliklerin daha kısıtlı olarak sunulduğu ancak çoğu sistem için
yeterli özellikleri içerecek bir sürümü de mevcuttur.

## PostgreSQL

PostgreSQL, en gelişmiş açık kaynak kodlu ilişkisel veri tabanı olarak
lanse edilmektedir. 35 yıldır geliştirme süreci devam eden PostgreSQL,
sağlamlık ve yüksek performansı sebebiyle sıkça tercih edilmektedir.
VTYS, tüm önde gelen işletim sistemleri üzerinde
çalıştırılabilmektedir.

<img src="./media/image7.png"
style="width:6.30208in;height:3.55208in" />

pgAdmin, PostgreSQL için tasarlanmış açık kaynak kodlu veri tabanı
yönetimi ve geliştirme aracıdır. PostgreSQL, standart SQL komutlarına
uyumlu çalışmakla birlikte bu komutları zenginleştirmek üzere çeşitli
ek özellikler içermektedir. Ayrıca temel veri türlerinin yanı sıra
doküman, geometrik ve özel tipte verileri de saklayabilmektedir.

## MongoDB

MongoDB, doküman tabanlı bir VTYS'dir. Kullanım oranları
incelendiğinde ilişkisel veri tabanlarından sonra doküman tabanlı
VTYS'ler gelmekte ve MongoDB bu türdeki veri tabanları için en sık
kullanılan seçenektir. Büyük ve yapılandırılmamış veri kavramlarının
çok daha öne çıktığı günümüzde, doküman tabanlı veri tabanları, bu
türde verilerin saklanılması konusunda MongoDB etkin bir çözüm
sunmaktadır. MongoDB, çok sayıda programlama diliyle uygun
çalışabilmektedir. Ayrıca veri aktarımı açısından JSON türünde veri
işlemektedir.
>
<img src="./media/image8.jpeg"
style="width:3.40625in;height:2.71875in" />
>
MongoDB Compass, MongoDB veri tabanını yönetmek için hazırlanmış
özelleştirilmiş ve yetenekli bir araçtır. Bu dersin kapsamında
yalnızca ilişkisel veri tabanları olsa da doküman tabanlı veri
tabanları da bir bilgisayar programcısının mutlaka aşina olması
gereken konular arasındadır. Bu konuda kendinizi geliştirmek
isterseniz; büyük veri, yapılandırılmamış veri, doküman tabanlı veri
tabanları, NoSQL ve JSON kavramlarına hâkim olmanız fayda
sağlayacaktır.

## Redis

Redis; çok sayıda geliştirici tarafından veri tabanı, ön bellek, yayın
motoru ve mesajlaşma için kullanılan bellek içi ve açık kaynaklı bir
VTYS'dir. Redis'in en önemli farkı, bellek içi veri tabanı olmasıdır.
Bilgisayar RAM belleğinin, sabit diske göre çok daha hızlı olması
sebebiyle Redis, diğer veri tabanlarına göre yüksek hız avantajı
sağlamaktadır. Ancak çoğu avantaj beraberinde bir dezavantaj da
getirmektedir. RAM bellek, verinin elektronik olarak saklanmasını
sağlamaktadır. Bu da elektriğin yokluğunda verinin de kaybolacağı
anlamına gelmektedir. Sabit diskler ise veriyi fiziksel olarak
kaydettikleri için elektrik kaybı veri kaybına sebep olmaz.
>
Veri tabanlarının en önemli özelliklerinden biri veri bütünlüğünü
koruması ve veri üzerinde yapılan işlemlerin güvenliğinden sorumlu
olmasıdır. Redis, yüksek kız kazanabilmek uğruna bu noktada bir
dezavantaja katlanmaktadır. Redis üzerinde yapılan işlemler bellek
içerisinde gerçekleştirildiği için, bellekte yer alan verilerin sabit
diske kaydedilememesi ve bu esnada elektrik kaybı yaşanması; veri
tabanı üzerinde gerçekleştirilen bir grup işlemin yok olması anlamına
gelecektir.
>
Redis, sahip olduğu veri kaybı riski sebebiyle genellikle veri
kaybının mağduriyet yaşatmayacağı ve yüksek hız gerektiren alt sistem
ve bileşenler için kullanılırlar. Ön bellek, mesajlaşma ve anlık
aktarım gibi işlemler hız gerektiren ancak veri kaybından dolayı krize
sebep olmayacak projelerdir.
>
<img src="./media/image9.png"
style="width:6.30208in;height:3.86458in" />
>
Redis, çoğunlukla komut istemi (terminal) üzerinden çalıştırılıyor
olsa da arayüz ile yönetilmesini sağlayan projeler de bulunmaktadır.
Redis Desktop Manager, en çok kullanılan Redis yönetim aracıdır.

1. **IBM DB2**

DB2, diğer adı ile IBM Database 2, 1983'te IBM tarafından MVS
mainframe platformu üzerinde bir VTSY çözümü olarak piyasaya
sürülmüştür. Sistem, erken dönemlerinde sadece IBM'in platformlarında
çalışmak üzere geliştirilmiş, 90'ların başı ile platform bağımsız bir
hale getirilmiştir. Kullanıcılar DB2'yu Linux, Unix veya Windows
işletim sistemlerinden biri ile kolaylıkla kullanabilecekleri gibi
bütçeleri doğrultusunda IBM'in sunduğu bulut ortamlarından biri ile de
kullanabilmektedirler.

![](./media/image10.jpeg)

Veri tabanı işlemlerini optimize ederek yüksek performans sağlayan DB2
ölçeklenebilirlik, güvenilirlik ve stabilizasyon özellikleri ile ön
plana çıkmaktadır. Yönetim açısından kullanıcı dostu bir GUI'ye
(grafik arabirimi) sahip DB2'da GUI'nin yanında terminal için yerleşik
(embeded) dil desteği bulunmaktadır.
>
Terminal ortamında geliştirme süreçleri Cobol scriptleri ile
yürütülmektedir. Geliştirme ve işletme süreçlerinde karşılaşılabilecek
problemlere karşı IBM destek hizmeti sunmakta, bu hizmet ise
kullanıcıların bu VTYS'ni tercih etmelerinde etkili olmaktadır.
>
Sunduğu özelliklerin yanında DB2 için IBM tarafından talep edilen
yüksek lisans ücretleri DB2'nun genellikle büyük ölçekli yapılar
tarafından tercih edilmesine yol açmıştır. Ülkemizde bankalar ve
çeşitli kamu kurumları tarafından tercih edilen DB2'ya özellikleri
kırpılmış bir versiyon olan Community (Topluluk) versiyonu sayesinde
ücretsiz şekilde erişebilmek de mümkündür.

## Elasticsearch

Elasticsearch bir arama motoru örneği olup büyük hacimli veriler
üzerinde etkin çalışma performansı için geliştirilmiştir. Platform
bağımsız bir şekilde çalışabilen Elasticsearch yapısal olarak Apache
Lucene üzerine kurulu, açık kaynak ve ücretsiz bir arama/analiz
motorudur. Log (günlük) kayıtları gibi yüksek hacimli ve gerçek
zamanlı verilerin merkezi bir şekilde depolanması ve analizi için
kullanılıp verileri belge şeklinde depolamaktadır. Elasticsearch
verileri sorgulamak için SQL'den başka fakat SQL ile benzer işleri
yerine getirebilen KQL (Kibana Query Language) dilini kullanmaktadır.
KQL, JSON diline yapısal olarak oldukça benzerdir.

<img src="./media/image12.png"
style="width:4.82292in;height:3.30208in" />

Hem yapılandırılmış hem de yapılandırılmamış veriler ile çalışma
olanağı sunan Elasticsearch matris tabanlı çalışabilmesinin yanı sıra
jeo-uzamsal verilere dayalı da çalışabilecek kadar esnek bir veri
tabanı tasarımı imkânı sunar. Basit, hızlı, ölçeklenebilir ve dağıtık
çalışabilme yetenekleriyle donatılı Elasticsearch veri depolamanın
yanı sıra veri analizi, görselleştirme ve zenginleştirme araçları ile
de dikkat çekmektedir. Başta güvenlik analitiği olmak üzere pazarlama
(ürün öneri ve arama sistemleri), coğrafi bilgi sistemleri ve oto
tamamlama araçları gibi sistemlerde tercih edilmektedir

## Microsoft Access

Microsoft tarafından Kasım 1990'da piyasa sürülen Access gelişimine
Office 365 konsepti altında devam etmektedir. Access yapı olarak hızlı
ve kullanışlı bir VTYS olup genellikle küçük ve orta ölçekli
kullanıcılar tarafından tercih edilmektedir. Access başlı başına bir
yerel VTSY sistemi olarak kullanılabileceği gibi başka veri tabanları
ile de bağlantılı ve eş zamanlı bir şekilde çalışabilmektedir. Örneğin
işletmede depo için kullanılan bir Access veri tabanı şirketin başka
bir veri tabanı Oracle ile bağlanarak daha büyük bir VTYS'nin parçası
gibi kullanılabilmektedir.

<img src="./media/image13.png"
style="width:4.1875in;height:2.71875in" />

Lisans ücreti, sadece Windows sistemleri üzerinde çalışabilmesi ve
kendine özgü bir dosya sistemi kullanması Access'in bir Microsoft
ürünü olmasına rağmen geliştiriciler tarafından daha az tercih
edilmesiyle sonuçlanmıştır.

## SQLite

SQLite Ağustos 2000'de D.Richard Hipp tarafından geliştirilmiştir.
Kurulum ve kullanım için herhangi bir özel yapılandırma istemeyen
SQLite platform bağımsız çalışabilen açık kaynak ve ücretsiz bir
VTYS'dir. Boyutlarının aksine yüksek performans ve düşük kaynak
tüketimi ile bilinir. Native olarak SQLite Database Browser ile
yönetilebileceği gibi DBeaver benzeri bir editörle de
yönetilebilmektedir.
>
Basit yapısı sayesinde geliştiricilere pek çok kolaylık sağlayan
SQLite benzeri VTYS'lerine göre iş yükü tasarrufu da sağlamaktadır.
Örneğin veri tabanını tek bir dosya şeklinde saklayan SQLite,
istenildiği taktirde çalışılan veri tabanını basit bir dosya transferi
ile taşıma imkânı sunmaktadır.

<img src="./media/image14.png"
style="width:5.09375in;height:4.51042in" />

Genellikle az kaynak tüketimi istenilen, verilerin hızlı ve yüksek
performanslı işlenmesinin istendiği yerlerde tercih edilen SQLite
mobil uygulamalar başta olmak üzere irili ufaklı pek çok cihaz
altyapısında karşımıza çıkmaktadır.

## Cassandra

Cassandra ilk olarak 2008 yılında Facebook tarafından geliştirilmiş
bir NoSQL VTYS örneğidir. Google Big Table ve Amazon Dynamo'nun
kombinasyonu olarak “Gelen Kutusu Arama” özelliği için
geliştirilmiştir.
>
Facebook tarafından Temmuz 2008'de açık kaynak hale getirilen proje
Mart 2009'dan bu yana bir Apache projesidir.
>
<img src="./media/image15.jpeg"
style="width:5.09375in;height:2.83333in" />
>
Cassandra benzeri Elasticsearch gibi dağıtık veri tabanları şeklinde
çalışabilirken, yine Elasticsearch gibi yüksek hacimli veri kümelerini
hızlı ve etkili bir şekilde analiz edebilme beceresine sahiptir.
Cassandra verileri sorgulamak için SQL'den başka fakat SQL ile benzer
işleri yerine getirebilen CQL (Cassandra Query Language) dilini
kullanılır.
>
Günümüzde Amazon, Facebook, Netflix gibi büyük şirketlerin çeşitli
yapılarında kullanılmakta olan Cassandra, Jeo-uzamsal uygulamalar,
mesajlaşma uygulamaları ve arama sistemleri gibi pek çok alanda
kullanılmaktadır.

## MariaDB

MySQL'in Oracle tarafından satın alınmasının ardından, bir grup
yazılımcı MySQL bünyesinden ayrılarak MariaDB'yi kurmuşlardır.
Kültürel olarak pek çok özelliğini MySQL'den miras alan MariaDB SQL
tabanlı iş yürütmekte olup açık kaynak ve ücretsiz bir VTYS'dir.

<img src="./media/image16.jpeg"
style="width:4.96875in;height:3.17708in" />

Kullanımı oldukça kolay olan MariaDB'de MySQL tarafından bir migration
(bir VTYS'deki verilerin bir başka VTYS'ye aktarılması) işlemi
yapılmak istenirse bunu desteklemektedir. Ayrıca MySQL için
geliştirilmiş pek çok araç ve eklentiyi de destekleyen MariaDB,
MySQL'e nazaran daha yenilikçi yaklaşımı ile gün geçtikçe
geliştiriciler tarafından daha çok tercih edilmektedir.

## Snowflake

Snowflake büyük hacimli verileri hızlı ve etkin yönetmek için
tasarlanmış, SQL dilini kullanan, bulut tabanlı bir VTYS'dir. Benzeri
VTYS'lerinden farklı olarak bulut özelinde çalışmak için
tasarlanmıştır. Genellikle veri mühendisliği ve veri bilimi
uygulamalarında tercih edilen Snowflake gerçek zamanlı veriler ile
etkin bir şekilde çalışma kabiliyetine sahiptir.

<img src="./media/image17.jpeg"
style="width:5.63542in;height:3.17708in" />

## Splunk

Splunk yüksek hacimli ve genellikle gerçek zamanlı verileri depolamak,
hızlı bir şekilde işleyip analiz etmek ve veri görselleştirme amacıyla
kullanılan bir platformdur. Yüksek hacimli ve gerçek zamanlı veriler
ile ekin çalışma kabiliyetine sahip Splunk şirketlerin BT
ihtiyaçlarına göre yarı yapılandırılmış verileri ve log kayıtlarını
izler, depolar ve analiz eder.

<img src="./media/image18.png"
style="width:5.92708in;height:3.89583in" />

Splunk süreci ve analiz sonuçlarını program üzerinde çeşitli araçlar
ile monitör edilebilmektedir. Genellikle güvenlik sistemleri
uygulanmalarında kullanılan Splunk ihtiyaca göre yerel veya bulut
çözümleri ile kullanılabilmektedir.

## Bölüm Özeti

Veri tabanı kavramı, ilişkisel veri modeli ve ilişkisel veri tabanı
üzerine yazılan iki makaleyle bugün en sık kullandığımız veri tabanı
sistemleri haline gelmiştir. Başlarda bu bir fikir olsa da zamanla
yazılım haline getirilmiş ve sistemlerle birlikte kullanılır hale
gelmiştir. Veri tabanı üzerine ele aldığımız her şey bu kavramların
bir parçası olmakla birlikte, veri tabanı yönetim sistemleri (VTYS) bu
kavramın vücut bulmuş, yazılıma dönüştürülmüş halidir.
>
Çok sayıda VTYS bulunmaktadır. Neredeyse tüm VTYS'ler ortak bir dil
olarak SQL dilini benimsemiş ve süreçlerine katmışlardır. Ancak bazı
VTYS'ler, özel durumlarda avantaj sağlayabilmek için SQL ve yazılım
süreçlerine eklemeler yaparak yeni yeteneklere sahip olmuşlardır.
Bununla birlikte en yetenekli olmak VTYS'ler için her zaman birincil
hedef olmamaktadır. Bazı VTYS'ler minimum özellik sunarak minimum
kaynak tüketimi ile oldukça düşük kapasiteli cihazlarda bile
çalıştırılabilir hale gelmektedir. Bazı VTYS'ler ise çok daha hızlı
okuma ve yazma yapmaya odaklıdır. Bazı VTYS'ler ise özellikle belirli
platformlara yönelik geliştirilmişlerdir. Çoğu programlama dili, çoğu
VTYS'yi destekliyor olsa da her bir VTYS'nin en etkin çalıştığı bir
platform bulunmaktadır. Bu da VTYS seçiminde dikkat edilmesi gereken
durumlardan biridir.
>
Bu bölüm içerisinde çok sayıda VTYS, temel özellikleri gözetilerek ele
alınmıştır. Bununla birlikte hangi programlama dili, hangi platform,
hangi amaç, hangi veri türü ile işlem yapılacağına bağlı olarak VTYS
seçilebileceği konusunda da çeşitli bilgiler sunulmuştur. Her bir VTYS
için ekran görüntüleri sunulmuştur.
>
Sonuç olarak bir VTYS'nin seçiminde “en iyi VTYS” gibi bir yaklaşımın
mümkün olmadığı, geliştirilen projenin, geliştiricinin ve fiziki
olanakların durumuna bağlı bir tercih yapılması gerektiği
vurgulanmıştır.