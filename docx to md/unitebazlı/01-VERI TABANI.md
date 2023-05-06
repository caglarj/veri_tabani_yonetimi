
# VERİ TABANI

## Birlikte Düşünelim

Farklı veri tabanlarını aynı anda kullanmak mümkün müdür? Hangi veriyi
artık silmek bir risk taşımayacaktır?
>
Veri tabanlarının bulut bilişimde yeri nedir?

## Başlamadan Önce

Bu bölüm veri tabanıyla ilgili temel olguları gözden geçirmemiz, bir
giriş yapmamız ve temelde amacımızın ne olduğunu hatırlatmak için
hazırlandı. Veriyi saklamak için 1970'ten beri kullandığımız bu yöntem
neden hala en popüler olanı? Yeni teknolojiler etrafımızı sarmışken
veri alanında bu kadar uzun süre kullanışlı kalabilen bu yöntemin ve
yaklaşımın sırrı nedir? Bu bölüm içerisinde veri tabanı ve
özelliklerini tartışarak geçen dönem aldığınız Veri Tabanı Tasarımı
dersine bir göz kırpacağız. Sonra da tasarladığımız veri tabanlarını
yönetmeyi öğreneceğiz.

## Veri ve Veri Tabanı

Veri kavramını bilgisayar programcılığından ayrı düşünmek mümkün
değil. Bilgisayar programcılığı sayesinde bilgisayarı büyük bir hesap
makinesi gibi kullanıyor ve çeşitli süreçleri otomatik hale
getiriyoruz. Bu süreçler genellikle veri ya da veriden elde edilen
enformasyonun çeşitli biçimler arasındaki geçişini konu ediniyor.
Bilgelik Hiyerarşisi, verinin enformasyona, enformasyonun bilgiye,
bilginin ise bilgeliğe dönüşebildiğini gösterirken her bir adım miktar
olarak azalan ancak değer olarak artan bir yapıya sahip olduğunu
göstermektedir (Rowley, 2007).
>
Günümüz teknolojik altyapısı, içinde bulunduğumuz çevreyle ilgili
gözlemlediğimiz ya da gözlemleyemediğimiz çok miktarda veriyi kayıt
altına alabilecek kapasitededir. Otonom sürüşün artık hayatımıza dahil
olduğu bu süreçte bir araç, otonom sürüş yapabilmek için insanın sahip
olduğu algıların çok daha fazlasına sensörler sayesinde sahiptirler.
Sahip olduğumuz teknolojik altyapı güçlendikçe daha fazla veriyi
ölçmek ve kayıt altına almak için çalışmalara devam ediyoruz. Bunun
sebebi, ne kadar fazla veri toplarsak, çok daha fazla enformasyona da
sahip olabilecek olmamızdır.
>
En nihayetinde daha fazla veri toplayabiliyor olsak da topladığımız
veriyi etkili bir şekilde kaydedemediğimizde ve işleyemediğimizde
bizim için anlamsız ve gereksiz maliyet oluşturan bir süreçle karşı
karşıya kalabiliriz. Büyük veri olarak adlandırılan kavram özetle
“başa çıkılamayacak kadar çok veri” olarak tanımlanabilir.
İşleyebileceğimizden daha fazla veriyi kaydettiğimiz sürece, sahip
olduğumuz teknik altyapıdan bağımsız olarak büyük veri kavramıyla
karşı karşıya kalacağız. Daha fazla veriyi kaydetmek, daha fazla
veriyi işlemek için gerekli altyapıyı kurmak, daha hızlı algoritmalar
geliştirmek ve elde edilen sonuçları gerçek hayata uygulamak;
birbirini zorlayan ve daha ileri gidilmesini sağlayan mekanizmalardır.
Veri bilimi kavramının özel sektörde kendine çok daha fazla yer
bulması da bu sürecin bir sonucudur. Verinin üretilmesi ya da
toplanması aşamasından, belirli bir problemin çözülmesi için
kullanılması aşamasına kadar olan süreçler çeşitli uzmanlıklar
gerektirmektedir. Bu uzmanlıklar da günümüzde karşımıza veri bilimcisi
olma şemsiyesi ile çıkmaktadır.
>
Verinin kayıt altına alınmasıyla ilgili zaman içerisinde çeşitli
yöntemler geliştirilmiştir. Her ne kadar çok sayıda yöntem bulunsa da
1970 yılında önerilen (Codd, 1969; Codd, 1970) ilişkisel veri
tabanları günümüzde hala en çok kullanılan yöntemdir. Statista'nın
Ağustos 2022 raporuna göre en çok kullanılan 4 veri tabanı yönetim
sistemi (Oracle, MySQL, Microsoft SQL Server, PostgreSQL) ilişkisel
veri tabanıdır.!



<img src="/media/image2.jpeg"
style="width:6.1875in;height:5.67708in" />
>
İlişkisel veri tabanları, verinin niteliklerinin (farklı kaynaklarda
nitelik yerine sütun, değişken, özellik, boyut, gösterge kelimeleri de
kullanılmaktadır) gruplanarak küçük veri yapıları oluşturması ve bu
veri yapılarının birbirleriyle ilişkilendirilmesi ilkesine bağlı
olarak çalışmaktadır. Böylece birbirleriyle fonksiyonel bağımlılık
ilişkilisine sahip nitelikler gruplanarak küçük tablolar
oluşturulmasını sağlarlar. Hangi niteliklerin hangi kümede bulunması
gerektiği konusu veri tabanı tasarımcılığı ile ilgilidir ve genellikle
bilgiyle birlikte deneyimi de gerektirir. Bu konuda bir önceki
dönemdeki dersiniz olan Veri Tabanı Tasarımı, birçok bilgi ve deneyim
kazanmanızı sağlayacak atölyeler içermektedir. Eğer veri tabanı
tasarlama konusunda daha fazla pratiğe ihtiyaç duyuyorsanız ilgili
dersin kaynaklarından tekrar faydalanmanız faydalı olabilir. İyi
tasarlanmış veri tabanları geleneksel veri saklama yöntemine göre
birçok avantaja sahiptirler. İlişkisel veri tabanının önerilmesinde 3
motivasyon bulunmaktadır (Codd, 1982).
>
Bunlardan birincisi fiziksel ve mantıksal boyutların birbirlerinden
tamamen ayrılmasıdır. Bu durumu iki açıdan ayrı ayrı inceleyebiliriz.
Birincisi eldeki fiziksel altyapıya uygun veri toplamanın getireceği
problemlerdir. Veri toplamak için ayrılan belirli bir bilgisayar
altyapısı mevcut ise, veri toplama aşamasında bu altyapı düşünülerek
toplanacak verinin niteliğinin belirlenmesi doğru bir yaklaşım
değildir. Toplanacak veri, bir problemin çözümüne yönelik elde edilmek
istenilen enformasyonu ortaya çıkarabilecek nicelik ve nitelikte
olmalıdır. Burada fiziksel kapasite bir limit oluşturmamalıdır.
Örneğin on yıllık satış verileri incelenirken disk kapasitesi
yetersizliği sebebiyle 7 yıllık satış verisi toplamak etkin bir
yaklaşım olmayacaktır. Diğer bir yandan verinin mantıksal boyutunun da
fiziksel boyutu üzerinde etkili olmaması sağlanmalıdır. Veri tabanları
genellikle çok tablodan ya da farklı zaman dilimlerine ait verilerden
oluşmaktadır. Boyut miktarı arttıkça veri hacmi de artabilir. Veri
hacminin artması fiziksel altyapının yetersiz gelmesine sebep
olabilir. Ancak bu durumun çözümü verinin parçalara bölünerek farklı
fiziksel ortamlarda bir araya getirilmesi değildir. İlişkisel veri
tabanları, verinin bir yığın olarak görülmesinin önüne geçmiş; bunun
yerine ilişkisel ve mümkün olan en küçük tablolarda, veri tekrarı
olmadan barındırılması ve sorgulanması konusunda avantajlar ortaya
koymuştur. Bu sayede fiziksel ve mantıksal boyutlar birbirlerinden
bağımsız olarak değerlendirilebilmekte ve uygulanabilmektedir. Günümüz
teknolojileri ile bu konuda zaman
>
zaman zorluk yaşansa da yeni yaklaşımlar ve yöntemler ile etkin bir
veri yönetimi süreci sürdürülebilmektedir.
>
İkinci motivasyon daha “kolay” bir yaklaşım elde etmektir. Ham veri
kümeleri; satır ve sütunlara sahip, düşük hacimlerde gözle dahi
kolayca incelenebilen veri yapılarıdır. Veri miktarı arttıkça gözle
incelemek zorlaşsa da üzerinde işlem yapmak kullanıcıların kolayca
anlayabildiği ve uygulayabildiği işlemlerdir.
>
Örneğin bir sütunda yer alan değerlerin ortalamasını almak MS Excel
yazılımıyla oldukça kolaydır. Ancak burada “kolay”dan kasıt kolayca
anlaşılabileceğidir. Yani bir veri kümesi GB'lar mertebesine
ulaştığında ortalama almaktan biraz daha karmaşık bir işlem fiziksel
altyapı için oldukça zorlayıcı olabilecekken, kullanıcı için anlaması
hala oldukça basittir. Nihayetinde veri kümesinde bir sütunda yer alan
değerler üzerinde basit bir işlem yapılmasını gerektirir. Geleneksel
veri saklama yöntemlerinde iyileştirmeler yaptıkça verinin saklanılma
biçimi değiştiği için veri üzerinde işlem yapmak için düşünce
yapısında da güncelleme yapmak gerekmektedir. Tek bir veri kümesi iken
bir sütun üzerinde işlem yapabiliyorken, parçalara bölünmüş bir veri
kümesi üzerinde aynı işlemi yapmak için biraz daha farklı düşünmek
gerekecektir. Codd, ilişkisel veri tabanı önerisinin ikinci
motivasyonunda bu konuyu ön plana almaktadır. Kendisi, geleneksel veri
saklama yöntemlerine göre daha etkin bir yöntem sunmakla birlikte bu
yöntemin tüm kullanıcı ve programcılar tarafından kolayca
anlaşılabilmesi gerektiğini düşünüyordu. Çünkü ortaya atılan yeni
yaklaşım, her ne kadar çok daha performanslı olsa da nasıl
kullanılacağı insanlar tarafından anlaşılamıyorsa kullanılması da pek
mümkün olmayacaktı. İlişkisel veri tabanlarının yapısına baktığımızda,
görünüm olarak ham veri kümesi yapısına oldukça benziyor. Bu da
geliştiricilerin veri tabanını ilk kez gördüklerinde bile tanıdıkları
bir yapıya sahip olduğu izlenimini oluşturuyor. Ayrıca niteliklerin
gruplanarak çok sayıda küçük tablo oluşturmak, çok büyük bir veri
kümesini gözle incelemekten çok daha kolaydır. Örneğin kullanıcılarla
ilgili bir veri tabanı tablosunu incelersek kullanıcıya ait
özelliklerin tutulduğu sütunlar ve bu sütunlar altındaki kayıtları
görüntüleyebiliriz. En nihayetinde Codd'un amacına uygun bir yapı
önerdiği yorumunu yapabiliriz. Programlamaya yeni başlayan ve hatta
ilgisi olmayan biri dahi bir veri tabanı ile karşılaştığında kolayca
yorumlayabilecektir.
>
Üçüncü motivasyon kayıtlar üzerinde çeşitli işlemleri
gerçekleştirebilmek üzere hazırlanmış bir üst seviye dil
kullanılmasıdır. Programlama dilleri alt, orta ve üst seviye olarak
üçe ayrılır. Üst seviye diller kullanıcının doğal (konuştuğu) dile
oldukça yakın ve dolayısıyla kolay öğrenilebilir ve geliştirme
yapılabilir dillerdir.
>
Ham veri kümeleri üzerinde analiz yapmak, doğrudan nitelikleri ve
kayıtları kullandığımız için çok daha kolay anlaşılır; bir programlama
dili kullanılsa bile satır ve sütun indisleri ile kolayca erişilebilir
durumdadır. Ancak ilişkisel veri tabanı gibi bir yapı içerisinde
ilgili veriyi filtrelemek, analiz etmek ve gerektiğinde yeni
kayıtların doğru tabloya doğru şekilde eklenmesini sağlamak daha fazla
dikkat ve bilgi gerektiren bir süreç olarak karşımıza çıkmaktadır.
Codd, ilişkisel veri tabanını önerirken motivasyonlarından birinin bu
olduğunu; bir veri tabanını yönetme aşamasında üst seviye ve evrensel
bir dile ihtiyaç duyulduğunu belirtmiştir. Bu amaçla kullanılan en
yaygın dil olan SQL bu dersin kapsamındadır. Üçüncü bölümde SQL
tanıtılacaktır. Bununla birlikte nispeten daha yeni ve kullanım oranı
her geçen gün artan veri tabanı sorgulama yaklaşımı olan ORM de üçüncü
bölüm içerisinde tanıtılacaktır. Ders boyunca verilecek tüm örnekler
hem SQL hem de ORM ile birlikte sunulacak, öğrencilerin bu iki
yaklaşıma da hâkim olması beklenecektir. SQL dili geleneksel ve en sık
kullanılan yöntem olması, ORM ise özel sektörde hızla daha da
yaygınlaşması sebebiyle bu dersi alan öğrencilerin biliyor olması
gereken teknolojilerdir.
>
İlişkisel veri tabanlarının beraberlerinde getirdiği avantajlar zaman
içerisinde çeşitli çalışmalarla incelenmiştir. Şimdi veri tabanlarının
avantajlarını ele alalım (Sumathi ve Esakkirajan, 2007; Zeng & diğ.,
2010).
>
İlk ve en önemli avantaj, ilişkisel veri tabanlarının yapılandırılmış
veriyi saklayabiliyor olmasıdır. Yapılandırılmış veri, satır ve
sütunlara bölünmüş hücreler içerisinde kayıtların atomik olarak
saklanılması durumudur. Günümüzde toplanan verinin çok büyük bir kısmı
yapılandırılmamış veriden oluşmaktadır.
>
Bunun en büyük sebebi de sosyal medya ve Web'den toplanan verilerdir.
Günümüzde Twitter adlı mikro blog web sitesinde yer alan veriler
birçok amaçla analiz edilmektedir. Ancak buradan toplanan veriler
doğrudan kişiler tarafından yazılan metinler olduğu için satır ve
sütunlarla kayıt altına alınamazlar. Benzer şekilde bir anahtar kelime
ile araştırma yaptığımızda birçok web sitesi ile karşılaşırız ve bu
sitelerin içerdiği verileri toplayabiliriz. Ancak her web sitesinin
sayfa yapısı birbirinden farklı olduğu için yine yapılandırılmamış
veriyle karşı karşıya kalmış oluruz. Tüm bu durumlar büyük veri
ifadesiyle kesişmekte; yeni araç ve yöntemlere gerek duyulmasına sebep
olmaktadır. Ancak bu konu bu dersin kapsamı dışındadır. İlişkisel veri
tabanları doğrudan satırlar ve sütunlarla ifade ettiğimiz ya da
yapılandırılmamış bir verinin bir takım ön
>
işleme çalışmalarının ardından yapılandırılmış veriye
dönüştürülmesiyle elde edilen veri kümelerinin yönetilmesini kapsar.
Verinin yapılandırılmış olarak saklanması özellikle sorgulama ve
ihtiyaç duyulan veriye hızlıca ulaşılması konusunda fayda
sağlayacaktır. Veri tabanında ihtiyaç duyulan sorgu sonucu, belirli
bir tabloda ve belirli nitelikler altında tanımlanmış durumda
olmalıdır. Bu da her ihtiyaç duyulduğu anda verinin sorgulanması ve
çeşitli raporlama sistemlerinin anlık olarak güncellenebilmesi
sağlanabilmektedir.
>
Yapılandırılmamış veri keşfedilmeyi bekleyen enformasyonu içeriyor
olsa da anlık ihtiyaçlara yanıt veremez; bunun ötesinde daha karmaşık
veri madenciliği tekniklerinin uygulanması ve çeşitli sorulara yanıt
aranmasını sağlarlar.
>
İlişkisel veri tabanları, verinin en düşük hacimle, tekrarsız olarak
saklanılmasını sağlamaktadırlar. Bir elektronik satış sitesinde, satın
alan yapan kullanıcının bilgilerinin her satış bilgisiyle birlikte
tekrar tekrar kaydedilmesi etkin bir çözüm olmayacaktır. Ya da bir
kütüphane sisteminde her ödünç alma işleminde ödünç alanın iletişim
bilgilerinin tekrar kaydedilmesi gereksiz tekrara ve daha büyük kayıt
yerine ihtiyacı beraberinde getirecektir. İlişkisel veri tabanları
içerisinde her bir olgu ya da eylem, bir veri tabanı tablosu olarak
saklanır. Kullanıcı, satış, ürün ve mağaza tablo adlarına birer
örnektir. Her bir tablo, o tabloya ait kayıtları bir kez
bulunduracaktır. Örneğin sistemde yer alan bir kullanıcı, ilgili
tabloda bir kez tanımlanır. Bu kullanıcı sistem üzerinde ne kadar çok
işlem gerçekleştirirse gerçekleştirsin kullanıcı kaydı yalnızca 1
satırdır. Kullanıcının bilgilerinin kullanılması gereken yerlerde, tüm
kayıtlar yerine birincil anahtarı kullanılır. Böylece kullanıcı
verilerinde gerçekleştirilmesi gereken bir güncelleme yalnızca tek
satırlık kayıt üzerinde gerçekleştirilir. Bu kaydı birincil anahtarı
ile çağıran diğer tüm kayıt alanları bu güncellemeden otomatik olarak
etkilenirler. Veri tabanı içerisinde veri tekrarını en aza indirmek,
bazı dosya sıkıştırma algoritmalarına benzer süreçler içermekte ve
nihayetinde verinin en az yer kaplayarak saklanılmasına olanak
sağlamaktadırlar.
>
İlişkisel veri tabanları ölçeklenebilirler. Yani daha yüksek erişim ya
da veri saklama kapasitesine ihtiyaç duyulması durumunda destekleyici
teknolojiler sayesinde bu ihtiyaca karşılık verebilirler.
Ölçeklenebilirlik, günümüzün önemli ihtiyaçlarından biridir. Bir
sistem, ne kadar düzenli ve kontrol altında olursa olsun genellikle
zamanla büyüyecektir. Sürekli büyüyen bir sistem için altyapının da
sürekli genişletilmesi gerekecektir. Küçük bir sistem için geniş bir
altyapı gereksiz maliyet oluşturacağı gibi büyük bir sistemin limitli
bir altyapı üzerinde çalışması sistem fonksiyonelliğini azaltacaktır.
Değişken kapasiteli altyapı günümüz sistemlerin genel ihtiyacıdır.
Sistemlerin zamanla genişlemesinin yanında, bazı sistemlerin dönemsel
olarak genişlemesi ve daralması da söz konusu olabilir. Örneği bir
online yemek sipariş sistemi, akşam saatlerinde çok yoğun olarak
ziyaretçi karşılayabilir ancak sabah saatlerine doğru minimum
yoğunluğa geri döner. Böyle bir sistem için statik altyapı hazırlamak
oldukça kötü bir çözüm olacaktır.
>
Yoğun saatlere göre yapılan planlama, diğer saatlerde gereksiz kaynak
oluşturacak; boş saatlere göre yapılan planlama ise yoğun saatlerde
aksamalara sebep olacaktır. Bu sebeplerle sistemlerin ihtiyaca göre
otomatik olarak ölçeklendirilebilmesi gerekmektedir. İlişkisel veri
tabanları ölçeklendirme teknolojileriyle uyumlu çalışmaktadır. Böylece
ilişkisel veri tabanı kullanan sistemlerin ölçeklendirme ihtiyaçlarını
karşılamaları kolaylaşmaktadır.
>
İlişkisel veri tabanları, hangi tür veriyi sakladığınızdan ve bu
veriye nereden eriştiğinizden bağımsız bir yapıya sahiptir. Bir veri
kümesini olgular ve eylemlere bağlı daha küçük veri kümelerine
bölebilmeniz ve bu veri kümeleri içerisinde satırlar ve sütunları
kullanmanız durumunda ilişkisel veri tabanlarını kullanabilirsiniz.
Tabloların hangi amaca hizmet ettiği, ne kadar veri sakladığı,
tablolar arasındaki ilişkilerin niceliği ve niteliği önemsizdir. Bu
sayede çok farklı amaçlar için bile ilişkisel veri tabanlarından
faydalanılabilir. Ayrıca veriye hangi platformdan erişileceği de
çeşitlendirilebilir. Bir veri tabanına mobil, web, masaüstü ve hatta
nesneler (akıllı ev aletleri vb.) üzerinden de erişilebilir. Dahası,
bu platformların bir kombinasyonu da veri tabanına erişiyor olabilir.
Mobil cihazdan girilen bir veri aynı anda web sitesindeki görünümü
etkileyebilir. Ya da mobil uygulamadan verdiğimiz bir komut evimizdeki
akıllı robot süpürgeye görev olarak yansıyabilir. İlişkisel veri
tabanları, veri tabanı yönetim sistemlerinin yetenekleri limitlerinde
çok sayıda platformla etkileşime geçebilir ve sağlanan yönetici
izinlerine bağlı olarak tümüne aynı anda hizmet sunabilir.
>
Eğer bir veri kümesi, MS Excel gibi bir yazılımla bilgisayar üzerinde
tutuluyorsa, aynı anda yalnızca tek bir kişi tarafından
kullanılabilir. Her ne kadar bu dosya ağ üzerinden paylaşıma
açılabiliyor olsa da bir dosyaya aynı anda erişim sağlanması birçok
problemi beraberinde getirecektir. Öncelikle bir dosyanın aynı anda
birden fazla kişi tarafından değiştiriliyor olması için yazılımın buna
uygun geliştirilmiş olması gerekir.
>
Ancak birçok geleneksel veri saklama yazılımı bu yapıya uygun olarak
geliştirilmemiştir. Çok kullanıcının
>
aynı anda güncelleme yapmasına uygun yazılımlar genellikle bulut
tabanlı olarak karşımıza çıkmaktadır. Ancak bunlar dahi bir veri
kümesi üzerinden birden fazla kullanıcının mükemmel etkinlikte
çalışmasını sağlayamazlar. Bir veri kümesi içerisinde farklı
konumlarda yer alan kayıtlar üzerinde değişiklik yapmak muhtemelen
güvenlik bir eylem olacaktır. Ancak aynı kayıt üzerinde aynı anda
birden fazla kullanıcının işlem yapması, işlemlerin çatışmasına ve
veri bütünlüğünün bozulmasına sebep olabilir. Bir kullanıcı kimlik
numarasını 11111111111 olarak girenlerin kayıtlarını silmeyi denerken
başka bir kullanıcı böyle bir kişi için satış kaydı yapıyorsa
muhtemelen büyük bir veri tutarsızlığı oluşmak üzeredir. İlişkisel
veri tabanları aynı anda çok sayıda kullanıcının erişimine izin
vermektedir. Her bir erişim, o izin için tanımlanan eylemleri
gerçekleştirebilir. Yani bazı kullanıcılar sadece veri kayıtlarını
okuyabilirken bazıları yeni kayıt oluşturabilir. Ya da kayıtların
güncellenmesi yetkisi özel bir kullanıcı grubuna verilebilir. Bununla
birlikte gelen okuma, güncelleme, ekleme ve silme komutları veri
tabanı yönetim sistemi tarafından bir sıraya koyularak veri
bütünlüğünü bozmayacak şekilde sırayla işlenir. Her bir sorgunun
sonucunda komut gönderen kullanıcıya sorgusunun hangi yanıtı aldığı
bilgisi dönülür. Böylece komut bir hata ile sonuçlandıysa kullanıcı bu
durumdan anında haberdar olabilir.

## Veri Tabanı Tasarımcılığı

Tablo biçimindeki bir verini, herhangi bir elektronik tablo (MS Excel
gibi) yazılımıyla kayıt altına almak oldukça kolaydır. Veriyi
kopyalar, yapıştırır ya da elle girişini yapar ve kaydedersiniz. Bir
veri kümesinin veri tabanı yapısına dönüştürülerek kaydedilmesi için
ise ilişkili veri kümeleri oluşturmaktan ve bu şekilde kayıt altına
almaktan bahsetmiştik. Peki elimizde n tane sütuna, m tane satıra
sahip bir veri kümesi varken bu parçalama işlemini nasıl yapacağız?
Rastgele mi? Elbette hayır. Kaç tane küme oluşturmamız gerekli? Her
birinde kaç tane ve hangi sütunlar yer almalı? Böldüğümüz kayıtların
gerektiğinde yeniden birleştirilebilmesi için ne yapmak gerekir? Bu
bir veri tabanı tasarımı sürecidir.
>
Veri tabanı tasarlamak, sistem analizi ve tasarımı sürecinin önemli
bir parçasıdır. Yeni bir sistem geliştirilmeden önce uygulanan birçok
adım ve verilen karar içerisinde sistemin sahip olması gereken bileşen
ve yetenekler belirlenir. Buna göre de sistemin teknik bileşenlerine
karar verilir. Yazılımla ilgili mimari tasarımının yanı sıra veri
tabanı tasarımının da tüm ihtiyaç ve gerekliliklere paralel
hazırlanması gerekmektedir.
>
Veri tabanı tasarımı süreci özneldir (sübjektif), zordur ve risklidir.
Ayrıca deneyim gerektirir. Şimdi bu olguların sebeplerini tartışalım.
>
Veri tabanı tasarım süreci içerisinde risk barındırmaktadır. Bunun
sebebi, kurgulanan bir veri tabanının faaliyete başladıktan sonra
tasarımdaki bazı hatalardan dolayı veri üzerinde işlemlerin tam
performansla gerçekleştirilememesi ve işleyen bir veri tabanı
tasarımında güncelleme yapmanın farklı riskler barındırıyor olmasıdır.
Yeni bir sistem için sistem analizi ve tasarımı süreçleri görece daha
az streslidir. Çünkü bu süreçte yapılan hatalar, süreç sonlanmadan
giderildiği sürece bir tehlike içermezler. Hatalı ya da eksik
algoritmalar, unutulan bir kullanıcı rolü, testi tamamlanmamış
bileşenler, kayıt altına alınması gereken bir özelliğin göz ardı
edilmesi gibi konular sistem analizi ve tasarımı sürecinin kaçınılmaz
parçasıdır. Zaten bu süreç kendi içerisinde bu hataları yok etme
odaklı çok miktarda iş yükü ve sinerji gerektirmektedir. Sistem
analizi ve tasarımı süreci tamamlandığında gerçekleştirilecek sistem,
bütün ayrıntısıyla dokümante edilmiş durumda olur. Bu durum yeni
yapılacak bir binanın bütün planlarının hazırlanması gibidir. Yapım
süreci başladığında bilgisayar programcıları, tasarımcılar ve
mühendisler eldeki dokümanların yönlendirmelerine bağlı olarak sistemi
inşa ederler. Sistem tasarımı sürecinde tüm ayrıntılar ele alındığı
için genellikle gerçekleştirme sürecinde karar verme ihtiyacı
bulunmamaktadır. Gerçekleştirmenin tamamlanmasının ardından yine
ilgili dokümana göre gerekli testler yapılır ve sistem hazırdır.
Sistem, seçilen stratejiye göre alfa, beta ve benzeri test
süreçleriyle kademeli ya da doğrudan herkesin erişimine açılır. Veri
tabanıyla ilgili sözünü ettiğimiz risk bu noktada karşımıza çıkar. Bir
sistem canlıya alındığında (genel kullanıma açıldığında) daha önce
test edilmemiş bir durum ya da sistem analizi aşamasında akla gelmeyen
bir ihtiyaç fark edilebilir. Bu ihtiyaç, mevcut süreçleri zora sokan,
derhal gerçekleştirilmesi gereken, aksi halde mevcut süreçlerin devam
edememesine sebep olabilecek bir ihtiyaç olabilir. Ya da daha az
riskli olan bir yan süreç; geliştirilmesi için bir süre beklemenin
göze alınabileceği bir ihtiyaç da olabilir. Her iki durumda da sistem
analizi ve tasarımı süreçlerinin ilgili adımlarına dönülür, eksik
kalan ihtiyaç analiz edilir ve mevcut sisteme entegresi için gerekli
planlama yapılarak sistem üzerinde güncelleme süreci başlar. Ancak bu
süreç yeni bir sistem gerçekleştirmekten daha stresli olabilir.
Kimsenin kullanmadığı bir sistemin (yeni) geliştirilmesi sürecinde
>
kullanıcılar bu sürecin bir parçası değildir. Ancak kullanımda olan
bir sistemde değişiklik yapmak; her şey yolunda gitse bile
memnuniyetsizliklere yol açabilir. Sisteme erişim kesintileri
yaşanabilir, güncellemeler mevcut işleyişte hatalara sebep olabilir,
geliştirilen özellik tam olarak istenildiği şekilde hazırlanmamış
olabilir. Bu süreç içerisinde veri tabanı tasarımında yapılması
gereken güncellemeler, programlama tarafında olanlara göre daha riskli
olabilir. Bunun sebeplerinden bazıları;

- Veri tabanı tasarımı güncellendikten sonra mevcut veri tabanındaki
  verilerin yeni tasarıma uygun şekilde yerleştirilmesi gerekliliği,

- Yazılım içerisindeki veri tabanı bağlantılarının veri tabanına göre
  güncellenmesi gerekliliği,

- Yeni tasarımın genellikle yeterince test edilememesinden kaynaklı veri
  yönetiminde hatalar görülmesi olarak sayılabilir.

Yazılımda görülen hatalar, yazılım üzerindeki güncellemelerle
giderilebilirken; veri tabanı tasarımında görülen hatalar hem
yazılımda hem de eldeki veri bütünlüğünde de güncellemeler ve çeşitli
kontroller yapılmasını gerektirebilir. Bu sebeplerden dolayı sistem
analizi ve tasarımı süreçlerinde veri tabanı tasarımlarının daha fazla
zaman ve iş yükü maliyetini göze alarak dahi doğru şekilde
gerçekleştirilmesi, geliştirilen sistemin ihtiyaç duyulan duruma daha
uygun olmasını sağlayacaktır.
>
Veri tabanı tasarımını, yalnızca ihtiyaçların ve hedeflerin
doğrultusunda gerçekleştirmeye çalışmak; hangi kararların alınacağı
konusunda her zaman yeteri kadar yol gösterici olmayabilir.
Geliştirilen sistem, analiz ve tasarım aşamasında elde edilen
hedeflere göre yazılım geliştirme aşamalarından geçecektir. Ancak veri
tabanı tasarımı süreci, aynı zamanda verinin en iyi ne şekilde
yönetileceği, hangi sorgulara ihtiyaç duyulacağı, elde ne tür veriler
olduğu, gelecekte ne tür veriler ekleneceğini tahmin etmeye dayalı
olarak farklı seviyelerde karmaşıklıklara sahip olabilir. Veri tabanı
tasarımı gerçekleştirmek, geleceğe yönelik bazı tahminleri yapmayı da
gerektirebilir. Bir hastaneye ait bilgi sisteminin geliştirilmesi
sürecinde hastanenin mevcut süreçlerinin yazılıma aktarılması elbette
beklenen bir istek olacaktır. Ancak bunun yanında hali hazırda devam
eden bazı süreçlerin bilgi sisteminin desteğiyle daha az iş gücü ve
zaman gerektiren farklı bir yolla yapılması istenebilir, idari çeşitli
değişikliklerin sisteme yansıtılması gerekebilir, çeşitli yeni
süreçlerin de bilgi sistemleriyle birlikte hayata geçirilmesi hemen ya
da bir süre sonra istenebilir. Mevcut bir kurum için bir bilgi sistemi
tasarlanması süreci bile çok miktarda belirsizlik içerirken yeni bir
sistemin tasarlanma süreci içerisinde çok daha fazla belirsizlik
bulunması beklenebilecek bir gerçektir.
>
İyi bir veri tabanı tasarlamak için hâkim olunması gereken iki konu
vardır: Bunlardan birincisi iyi bir ilişkisel veri tabanının sahip
olduğu özellikler, ikincisi ise normal formlardır. İyi bir veri tabanı
tasarımının sahip olması gereken özellikleri bilmek, bir veri tabanı
tasarımı yaparken sürekli bunu gözetmeyi de gerektirecektir. Örneğin
veri ne şekilde çağrılacak, kaç istemci aynı anda erişecek, hangi
veriye ne şekilde ihtiyaç duyulacak, hangi veri parçası hangi diğer
parçalarla birlikte bir küme olmalı? Bu soruların yanıtını aramak daha
kullanışlı ve yüksek performanslı veri tabanı tasarımı
gerçekleştirmenin anahtarı olacaktır.
>
Normal formlar, iyi bir veri tabanı tasarımı gerçekleştirilmek için
uyulması gereken kuralları sunmaktadır (Fagin, 1981; Hoffer, 2016).
Normal formlara uygun olarak tasarlanmış bir veri tabanına normalize,
bu sürece ise normalizasyon adı verilmektedir (Lee, 1995; Hoffer,
2016). Bölüm 6 içerisinde normalizasyon konusunu ve normal formları
ayrıntılı inceleyeceğiz. Burada değinmiş olmamızın sebebi, bir veri
tabanı tasarımı yaparken sahip olunması gereken bilgi birikimini
vurgulamak. Teknik olarak veri tabanlarının özelliklerini ve normal
formları bilmek iyi bir veri tabanı tasarımı gerçekleştirmek için
yeterli olmalı. Ancak veri tabanı tasarımı; tasarımcının deneyim,
tecrübe ve bilgi birikimiyle ilgilidir. Bunun yanında tasarımcılar bu
özelliklerin tamamına sahip olsalar da yine de aynı proje için farklı
tasarımlar ortaya koyabilirler (Akadal, 2021). Bu da veri tabanı
tasarımının nesnel (objektif) değil, öznel (sübjektif) olmasına yol
açmaktadır.
>
Veri tabanı tasarımı sürecinin öznellik içeriyor olması çok da
şaşırtıcı bir olay değildir. Tasarım sürecinin başında elde bir veri
kümesi varsa, nispeten elde edilmesi beklenen veri tabanı tasarımı
yapısı daha net olacaktır. Veri kümesinde bulunması gereken tüm
alanlar, içerisinde örnek veriyle birlikte sunuldukları zaman,
oluşturulacak veri tabanı tasarımı için yol gösterici olabilecektir.
Ancak bu durumda bile mükemmel veri tabanı tasarımına ulaşmak mümkün
olmayabilir. Daha önce geleneksel yöntemlerle saklanılan bir veri
kümesinin, bir bilgi sistemi hazırlandıktan sonra aynı şekilde
kullanılacağı garanti değildir. Veri kümesinde, veri yapısında,
bileşenlerde, kullanıcı ve paydaşlarda çeşitli güncellemeler ve
genişlemeler gerçekleştirilebilir. Dahası, bu potansiyel değişiklikler
planlanmamış ve hatta henüz düşünülmemiş bile
>
olabilir. Bu durumda veri tabanı tasarımcısının rolünün önemi öne
çıkmaktadır. Veri tabanı tasarımı gerçekleştiren kişi karşılaşılması
muhtemelen durumları önceden belirlemek, bunlarla ilgili hem
geliştiriciler hem de sistemi yönetecek ve kullanacak kişilerle iş
birliği yapmak mecburiyetindedir. Elde bir veri kümesi varken bile bu
risklerle karşılaşma ihtimali varken, elde yalnızca istek ve
öngörülerin olduğu bir sistem analizi ve tasarımı sürecinde çok daha
fazla belirsizlik olması beklenecek bir şey olacaktır.
>
Ulaştığımız bu noktada, iyi bir veri tabanı tasarlamak için
“deneyim”in sahip olunması gereken bir özellik olduğunu savunabiliriz.
Bunun sebebi, bahsettiğimiz riskleri öngörme olasılığının deneyimle
arttırılmasıdır. Biraz daha açalım. İyi bir veri tabanı tasarımı
yapabilmek için sahip olunması gereken bilgi ve beceriye her zaman
yeterli gelmeyecektir. Eldeki tüm bilgi ve beceri kullanıldığında dahi
veri tabanı tasarımı oluşturulduktan ve bilgi sistemi faaliyete
alındıktan sonra süreçte hatalar ya da geliştirilmesi gereken durumlar
keşfedilebilir. Bir kez bu süreci deneyimlemiş olan uzman, gelecekte
benzer projeler içerisinde yer aldığında daha önce yaşanmış
problemleri hatırlayarak sistem analizi ve tasarımı sürecinde
tanımlanmamış kullanım durumlarını da hesaba katabilir ve tasarımını
buna göre güçlendirebilir. Bazı yazılım projeleri hayata geçtikten
sonra krizlere sebep olabilir, geliştirme sürecinden daha yoğun bir
iyileştirme süreci geçirilmesine sebep olabilir. Bu gibi durumlar için
tasarım aşamalarında deneyimli geliştiricilerin yönlendirmeleri
riskleri ve bunlara bağlı krizleri en aza indirebilir.
>
Veri tabanı tasarlama süreci normal formlar sayesinde kurallarla
gerçekleştirilen bir süreç gibi görülebilir. Benzer şekilde
karşılaşılan durumlar karşısında benzer faaliyetleri göstermek,
tasarım gerçekleştirmenin uzmanlık ve deneyim gerektirmeyeceğini
düşünmeye sebep olabilir. Ele alınan girdiye uygulanan bazı işlemlerin
sonucunda çıktı elde etmek, algoritması yazılabilen ve dolayısıyla
bilgisayar programı hazırlanabilecek bir süreci işaret etmektedir.
Veri tabanı tasarımı gerçekleştirme sürecini bilgisayar programıyla
otomatikleştirmek, uzun yıllar boyunca farklı algoritmalarla denenmiş;
ancak kullanıcıdan alınan ek girdiler sayesinde kısmen
gerçekleştirilebilmiştir. Akadal (2017), yalnızca ham veri kümesini
girdi alarak ilişkisel veri tabanı tasarımı önerisi sunan bir
algoritma önermiştir. Bu konu hala gelişmekte olan, üzerinde çalışılan
bir alandır. Otomatik veri tabanı tasarımı gerçekleştirmenin mümkün
olmadığı gerçeği, veri tabanı tasarımının normal formların kurallarına
göre kolayca yapılamayacağını da göstermektedir. Tüm bilginin elde
olmasına rağmen yine de iyi bir veri tabanı tasarımı oluşturmayı
garanti edememenin sebebi deneyim ve buna bağlı olarak özgün/öznel
yaklaşım gerekliliğidir. Dahası, yeterli bilgi birikimi ve tecrübeye
sahip iki uzmanın önereceği veri tabanı tasarımlarında da farklılıklar
görülmesi olasıdır. Bu iki uzman, farklı durumları deneyimlemiş,
farklı riskleri öngörerek karar almış olabilirler. Bu noktada siz
değerli öğrencilerin yapması gereken şey en fazla sayıda örnek
uygulama görerek mümkün tüm riskleri tahmin etmeniz ve kullanım
sırasında probleme yol açmayacak bir veri tabanı tasarımı
gerçekleştirebilmenizdir.
>
Veri tabanı tasarlama süreci bir veri kümesinde yer alan niteliklerin
anlamlandırılması ve kümelendirilmesiyle başlayarak bu kümeler
arasındaki ilişkilerin belirlenmesi süreciyle devam etmektedir. Bir
önceki dönem dersi olan Veri Tabanı Tasarımı, bu konuda yapılması
gerekenleri adım adım ve örneklerle sunmaktaydı. Bu ders ise tasarımı
tamamlanmış bir veri tabanı üzerinde ne şekilde operasyonlar
gerçekleştirilebileceği ve en etkin yönetim şeklini öğretmek üzerine
kuruludur.

## Veri Tabanı Yönetimi

Veri tabanı tasarlama işinin sistem analizi sürecine bağlı olarak
gerçekleştiğinden bahsetmiştik. Sistem analizi sürecinin
tamamlanmasıyla birlikte veri tabanı tasarımı da tamamlanmış ve
dokümante edilmiş olmalıdır. Geliştirme aşaması, sistem analizi
aşamasında elde edilen tüm bulgu ve tasarımların gerçeğe
dönüştürüldüğü aşamadır. Seçilen yönteme göre bu aşamanın nasıl
uygulanacağı değişebilir ancak bu değişim genellikle bilgisayar
programlama açısından önemlidir. Biz, dersimiz kapsamında veri tabanı
açısından inceleyeceğiz.
>
Veri tabanı tasarımı tamamlandığında elimizde bir varlık-ilişki (ER:
Entity-relationship) diyagramı bulunmaktadır. Sistemin geri kalanının
tasarımı ve bunun dokümantasyonuyla birlikte sistemin tamamı herhangi
bir kodlama yapılmadan kâğıt üzerinde izlenebilir hale gelmektedir.
Gerçekleştirme aşamasına geldiğimizde kâğıt üzerinde tasarladığımız;
tablolar, değişkenler ve ilişkileri veri tabanı olarak kurgulamamız
gerekecektir. Bunun için de yapmamız gereken bazı tercihler
bulunmaktadır.
>
Geliştirilecek sistemin hangi dil ve platformda gerçekleştirileceği
oldukça önemlidir. Ancak bu karar veri tabanından bağımsız alınan bir
karardır. Çünkü daha önce de belirttiğimiz gibi veri tabanları farklı
platformlar ile problemsiz şekilde uyum sağlayabilirler. Platform
kararı genellikle kurulacak sistemin hangi cihazlar üzerinde
kullanılacağı ve kullanıcı deneyimi göz önünde bulundurularak tercih
edilirler. Bunun veri tabanı tarafını ilgilendiren kısmı ise seçilen
platforma uygun veri tabanı türünün ve veri tabanı yönetim sisteminin
tercih edilmesidir. Bu tercihin gerçekleştirilmesiyle ilgili konular
bir sonraki bölümde ayrıntılı olarak ele alınacaktır.
>
Sistemin tamamıyla uyumlu bir veri tabanı yönetim sistemi seçildikten
sonra uygulama süreci başlamaktadır. Geliştirilen sistem nerede
kullanılacak olursa olsun genellikle öncelikle geliştirici
bilgisayarında hayata geçirilir. “Localhost” olarak adlandırılan yapı,
geliştiricinin kendi bilgisayarını bir sunucu gibi kullanarak
geliştirme sürecini daha hızlı gerçekleştirebilmesi üzerinedir.
Geliştirme süreci tamamlandığında ya da kısmi yayına alınması
gerektiğinde bu işlemden sorumlu ekip üyesi (bu kişi genelde DevOps'çu
olarak adledilir) sistemin mevcut halini kullanıma açılacak altyapı
üzerine taşır. Bu süreç alınan sistem geliştirme yöntemine göre
takvimlendirilir.
>
Hazırlanan geliştirme ortamı üzerinde, sistem analizi ve tasarımı
aşamasında hazırlanan veri tabanı tasarımının gerçekleştirilmesi
gerekmektedir. Bu aşamada veri tabanı ile etkileşime geçmek üzere
çeşitli yöntemler bulunmaktadır: Arayüz üzerinden, SQL ve ORM.
>
Birçok veri tabanı yönetim sistemi, yönetimini sağlayan bir yazılım ya
da bulut sisteme sahip. Bu arayüzler, birkaç fare tıklaması ve
yalnızca tablolarla değişkenlerin adlarını yazarak veri tabanı
tasarımını gerçekleştirmeye olanak sağlıyorlar. Bu işlemleri kod
yazarak gerçekleştirmek en etkin çözüm olsa da günümüzde veri tabanı
yönetimini sağlayan yazılımlar her türlü fonksiyonelliği, oldukça
kolaylaştırarak bize sunmaktadırlar.
>
SQL (Structured Query Language – Yapısal Sorgu Dili), veri tabanı
yönetimi için kullanılan en eski ve yaygın yöntemdir. Neredeyse tüm
programlama dilleri SQL sorgularını çalıştırabilen yazılım paketlerine
sahiptirler. Codd'un motivasyonlarından biri olan üst seviye bir dil
ile veriyi yönetme isteği, SQL dili ile karşılanabilmektedir. Farklı
yazılım dilleriyle uyumlu çalışabilen SQL, oldukça basit bir yazım
şekline sahiptir.
>
ORM (Object-Relational Mapping – Nesne-İlişkisel Eşleme), nesne odaklı
yazılım geliştirme süreçleri içerisinde kullanılan; her bir nesnenin
doğrudan veri tabanıyla bağlantılı olmasını sağlayan bir yapıdır. Bu
yapı sayesinde programlama süreci içerisinde yazılım geliştiren kişi
nesneler üzerinde çeşitli işlemler yaparak bunların veri tabanına
yansımasını sağlayabilir. Böylece zaten nesneler üzerinde
gerçekleştirdiği işlemler için tekrar SQL kodu yazmasına gerek kalmaz.
ORM kullanmanın en büyük dezavantajı, her bir programlama dili için
farklı bir paket ile gerçekleştiriliyor olması; dolayısıyla her dil
için tekrar bir öğrenme süreci gerektirmesidir. SQL dili her
programlama dili içerisinde aynı şekilde çalışırken ORM için bu durum
geçerli değildir.
>
Veri tabanının ilk kez gerçekleştirme aşaması yalnızca bir kez yapılan
adımlar içerdiği için bu süreç genellikle arayüzler kullanılarak
gerçekleştirilir. Yalnızca tek bir kez çalıştırılacak SQL ve ORM
kodları yazmak genellikle daha fazla zaman maliyetine sebep olabilir.
Ancak sistem çalışmaya başladıktan sonra her bir sürecin otomatik
olarak veri tabanına iletilmesi gerekmektedir. Bu durumda SQL veya ORM
yöntemlerinden biri tercih edilerek programlamaya dahil edilir. Bu
sayede kullanıcının arayüz üzerinde gerçekleştirdiği bir hareket, arka
planda bir veri tabanı işlemini tetikleyebilir. Her nasıl ki veri
tabanının ilk kez kurulması aşamasında SQL veya ORM kullanmak zaman
maliyetine sahip olacaksa sistemin işleyişi esnasında da arayüz
üzerinden bu işlemlerin gerçekleştirilmesi gerçekleştirilebilir
değildir. SQL ve ORM'in nasıl kullanılacağı ve dersimize nasıl entegre
olacağıyla ilgili bilgiler üçüncü ünite içerisinde ayrıntılı olarak
sunulacaktır. Tüm ders boyunca örneklerin hem SQL hem de ORM ile
uygulanması konusunda yönlendirmelerle karşılaşacaksınız. İki yöntemin
de öğrenilmesi gereken çok önemli ve yaygın yöntemler olduğunu
bilmenizde fayda var.
>
Veri tabanının kurulma sürecinden sonra yönetimiyle ilgili süreçler de
devam etmektedir. Veri tabanına erişim için çeşitli kullanıcı
hesapları tanımlanır. Bu hesaplardan birisi yazılımın kendisine ait
olmalıdır. Çünkü yazılım da veri tabanına erişirken bir kullanıcı rolü
ile erişir. Bunun dışında yöneticiler de çeşitli rollere sahip
kullanıcı hesapları edinirler. Süreç boyunca veri tabanında
gerçekleştirilecek iyileştirme,
>
raporlama amaçlı sorgulama, yeni modüllerin devreye alınması gibi
özellikler için veri tabanına erişerek çeşitli önemli işlemlerin
gerçekleştirilmesine ihtiyaç duyulmaktadır.

## Bölüm Özeti

Bilgelik hiyerarşisi; veri, enformasyon, bilgi ve bilgelik adımlarını
içermektedir. Bu hiyerarşi içerisinde verinin enformasyona dönüşmesi
süreci dersimizle oldukça ilgilidir. Bilgisayar programları elde
ettikleri veriden anlam çıkararak kullanıcıya sunmak üzere
hazırlanırlar. Bunun için de verinin etkin şekilde saklanılması ve
performanslı şekilde sorgulanabilmesi ve işlenebilmesi gerekmektedir.
Tüm bu süreçler veri tabanlarının gerekliliğini göstermektedir.
İlişkisel veri tabanları Edgar Frank Codd tarafından üç motivasyonun
öne çıkarak önerildiği bir veri tabanı yapısıdır. Bu üç motivasyon;
fiziksel ve mantıksal beklentilerin birbirinden ayrılması, programcı
ve kullanıcıların kolay anlayabileceği bir yapı oluşturmak, veri
yönetiminde kullanılabilecek üst seviye bir dil ortaya çıkartmaktır.
Veri yönetiminde ilişkisel veri tabanı kullanmak birçok avantajı
beraberinde getirmektedir. İlişkisel veri tabanları veri tekrarından
kaçınmayı mümkün hale getirirler. Veriyi yapılandırılmış olarak
saklayabilir, bu sayede veri üzerinde analiz ve sorgulama yapmayı
kolaylaştırırlar. Veri tekrarını en aza indirmesi sayesinde veriyi çok
daha düşük bir hacimle barındırabilir. Aynı anda birden fazla
kullanıcının erişmesine olanak sağlar ve bu esnada veri bütünlüğüne
herhangi bir zarar gelmemesini mümkün kılar. Birçok platform
tarafından aynı anda kullanılabilir. Böylece farklı platformlardaki
uygulamaların eşlenik olarak çalışmasını mümkün hale getirir.
>
Veri tabanı tasarımı, eldeki bir probleme uygun şekilde toplanacak
verinin elektronik olarak kayıt altına alınması için gerçekleştirilen
hazırlık sürecini ifade etmektedir. Bu sürecin başarısı, veri tabanı
ilkelerine ve veri kümesini inceleyen kişinin olası riskleri
öngörebilmelerine göre ortaya çıkmaktadır. Bu ders kapsamında veri
tabanı tasarımı konuları ele alınmayacak olsa da bu ders ve
öğretilerinde başarılı olabilmek için veri tabanı tasarlama konusunda
başarı sağlamış olmak gerekmektedir.
>
Bir veri tabanını hayata geçirmek için öncelikle bir veri tabanı
yönetim sistemi seçilmelidir. Bu seçim, geliştirilen sistemin hangi
platform üzerinde çalıştırılacağına bağlı olarak seçilecektir. Her ne
kadar herhangi bir veri tabanı herhangi bir platformda genellikle
uyumlu çalışabilir olsa da platformlarla birlikte sıklıkla kullanılan
veri tabanı yönetim sistemleri bulunmaktadır.
>
Veri tabanı gerçekleştirme ve yönetme üç yolla gerçekleştirilmektedir.
Bunlardan birincisi arayüzdür. Birçok veri tabanı yönetim sisteminin
doğrudan ya da aracı uygulamalarla erişilebilecek kullanışlı
arayüzleri bulunmaktadır. Bir veri tabanını hayata geçirme sırasında
yapılan işlemler genellikle bir kez gerçekleştirildiği için bu süreci
arayüz üzerinden gerçekleştirmek kolaylık sağlamaktadır. İkinci yöntem
SQL kullanmaktır. SQL, veri tabanı yönetiminde en sık başvurulan, üst
seviye ve evrensel bir dildir. Neredeyse bütün programlama dilleri SQL
yorumlayıcı fonksiyonlara sahiptirler. Yazılan bilgisayar programları
içerisinde veri tabanı üzerinde bir işlem gerçekleştirilmesi istenilen
aşamada SQL komutu ile ilgili istek işlenir. Böylece bilgisayar
programları otomatize şekilde veri tabanı üzerinde işlem
gerçekleştirebilirler.
>
SQL, birçok veri tabanı tablosunu bağlantılı şekilde sorgulamak ve
güncellemekle ilgili yeteneklere sahiptir. Üçüncü ve son yöntem ise
ORM teknolojisinden faydalanmaktır. Bu yöntem, nesneye yönelik
programlama ile birlikte kullanılan; programlama başvurulan nesne
yönetimiyle veri tabanı yapısının entegre olduğu bir yaklaşımdır.
Bilgisayar programcısı, oluşturduğu nesnelerle veri tabanını
eşleştirdikten sonra kodlama esnasında veri tabanı nesneleri üzerinde
gerçekleştirdiği herhangi bir işlemin veri tabanında otomatik olarak
işlem yapmasına müsaade edebilmektedir. Örneğin bir nesne kullanılarak
oluşturulan bir örnek, veri tabanında yeni bir kayıt olarak
işlenecektir. Benzer şekilde nesne üzerinde yapılan bir sorgulama da
veri tabanından ilgili kaydın çekilerek örneğe yüklenmesini
sağlayabilir.

### Kaynakça

Akadal, E. 2017. Ham verilerin genetik algoritmalarla ilişkisel
veritabanlarına dönüştürülmesi ve bir uygulama. İstanbul Üniversitesi
Fen Bilimleri Enstitüsü. Doktora Tezi.
>
Akadal, E. 2020. Veritabanı Tasarlama Atölyesi. Türkmen Kitabevi,
İstanbul.
>
Codd, E. F., 1969. Redundancy and consistency of relations stored in
large data banks. SIGMOD Rec., 17- 36.
>
Codd, E. F., 1970. A relational model of data for large shared data
banks. Commun. ACM, 13(6):377–387.
>
Codd, E. F., 1982. Relational database: a practical foundation for
productivity. Communications of the ACM 25.2, 109-117.
>
Jennifer Rowley. 2007. The wisdom hierarchy: representations of the
dikw hierarchy. Journal of information science, 33(2):163–180.
>
Sumathi, S. & Esakkirajan, S. 2007. Fundamentals of relational
database management systems, volume 47.
>

### Sorular: 

bU BÖLÜM ChatGpt'nin yukarıda ki anlatılan konularla ilgili, 15 adet çoktan seçmeli (beş şıktan oluşacak, şıklar a), b), c), d), e), ) soru sorması için vurgulanmıştır. bu notu okuduğunda, soruları sormaya başlayabilirsin. 