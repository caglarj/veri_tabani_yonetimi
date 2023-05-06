# SQL VE ORM


## Kazanımlar

1. Veri tabanıyla ilgili temel kavramlara hakim olur.

2. Veri tabanıyla ilgili gösterim yöntemlerini bilir.

3. Kaz Ayağı gösterim yöntemine hakim olur.

4. Fonksiyonel bağımlılık gösterimine hakim olur.

5. Veri kümesi, veri ambarı, tablo, nitelik, kayıt ve benzeri
    kavramlarını bilir.

## Birlikte Düşünelim

Bilgisayar programlama sürecinin tamamı bilgisayar ortamında mı
gerçekleştirilir?
>
Veri tabanı tasarımı dersi için “tasarım” kelimesi özellikle
seçilmiştir. Tasarım kelimesini kullanınca ne hayal ediyorsunuz?
Tasarım süreci doğası gereği hangi faaliyetleri barındırır?
>
Bir veri tabanı tasarımı gerçekleştirmekle sanat eseri tasarlamak
arasında nasıl benzerlikler bulabiliriz? Veri tabanı tasarımında
“bilgelik” yeterli midir?
>
Bir veri tabanının performansı nasıl ölçülebilir?

## Başlamadan Önce

Yazılım geliştirme -eğer hobi projesi değilse- bir ekip işidir. Aynı
zamanda genellikle kısa bir süreç de değildir. Yazılım geliştirme
süreci boyunca ekibin hangi amaç ve motivasyonla yazılım geliştirdiği
ve önceliklerin neler olduğunu; yol haritasının ne şekilde
tanımlandığının bilinmesi oldukça önemlidir. Bunun için de yazılım
projelerinde sistem analizi ve tasarımı ile buna bağlı olarak
dokümantasyon süreçleri oldukça önemlidir. Bir yazılımcı için
dokümantasyon oluşturma ve inceleme zaman zaman sıkıcı olabilse de
projenin sağlıklı yürütülmesi açısından gereklidir.
>
Veri tabanı tasarımı da sistem analizi ve tasarımı sürecinin bir
parçasıdır. Bu sebeple henüz bilgisayar ortamında geliştirmeye
başlanmadan önce yapılan çeşitli faaliyetler içerir. Bu faaliyetler
neticesinde de bir dokümantasyon elde edilir. Elde edilen çıktının tüm
proje ekibi ve potansiyel diğer ekip üyeleri tarafından rahatlıkla
anlaşılabilir ve uygulanabilir olması gerekmektedir. Bunu sağlamak
için ortak kullanılan çeşitli kavram ve diyagramlar bulunmaktadır. Bu
bölüm içerisinde temel kavramların anlamları ve gösterim şekilleriyle
ilgili temel bilgileri edinebilecek; bu tür teknik dokümanları
oluşturmak ve incelemek için gerekli altyapıyı edinmiş olacaksınız.

## Veri Yönetimi

İlk iki ünitede veri tabanına dair hem birçok konuyu tekrar gözden
geçirdik, hem de veri yönetimi konusunda bolca ayrıntıya değindik. Bu
ders boyunca amaç, kavramsal olarak sunulan başlıklar da dahil olmak
üzere sizlere tanımsal öğretiler sunmak değil; bir kavramın pratik
anlamda sağlayacağı katkılar konusunda çeşitli bilgiler sunmak ve
yorum gücünüzü arttırmaktır. Veri tabanıyla ilgili çalışırken bir veri
tabanının öne çıkan özelliklerine hâkim olmak, veri tabanı tasarlama
ve yönetme süreçlerinde fayda sağlayacaktır. Nihayetinde veri tabanı
konusuna eğilme sebebimiz, zaten elimizde bulunan ya da
toplayabileceğimiz bir veriyi daha etkin şekilde saklayabilmek ve
sorgulayabilmektir.
>
Veri tabanları, doğrudan grafik arayüze sahip bir yazılım ile
yönetilebilirler. Herhangi bir veri tabanı seçilip oluşturulduktan
sonra, bir veri tabanı yönetim aracı ile bu veri tabanına
bağlanılabilir; tüm içerikler görüntülenebilir, klavye ve mouse
hareketleriyle kontrol edilebilir. Ayrıca komut istemi ve SQL erişimi
de yine bu yazılımlarla mümkündür. Bunun nasıl yapılacağına geri
döneceğiz. Ancak şu an bilgisayar programcılığı üzerine çalıştığımızı
hatırlatıp, veri tabanı yönetimini bu perspektiften incelemeye devam
etmeliyiz.
>
Bilgisayar programları, sistematik bir şekilde tekrar edilen işlerin
bilgisayara yaptırılabilmesi için hazırlanan, bilgisayar tarafından
yorumlanabilen komutlar bütünüdür. Bir bilgisayar programının
işlettiği süreçlerde, veri işleme de bu süreçlerin bir parçası
olabilmektedir. Bir bilgisayar programı, yapacağı işlem için girdi
(input) veriye ihtiyaç duyabilir, çalışma süreci içerisinde bir veri
üretimi ya da toplanması işlemi gerçekleştirebilir, çalışma sürecinin
sonucu olarak bir çıktı (output) veri üretebilir. Ayrıca bunların bir
kombinasyonu da mümkündür.
>
Örnek olarak veri analizi gerçekleştiren bir bilgisayar programı,
girdi veri kümesine ihtiyaç duyacak, iç süreçlerinde bu veri kümesi
üzerinde çeşitli işlemler gerçekleştirecektir. Ancak çıktı bir rapor
formatında olabilir. Bir diğer örnek olarak, bilgisayar programı
çalıştırılması esnasında bir veri kümesi oluşturabilir. Örneğin bir
optimizasyon yönteminin performansının ölçülmesi esnasında rastgele
parametreler kullanılarak aramalar yapılabilir ve bu aramaların
sonuçları kayıt altına alınır. Ardından bu kayıtlar üzerinde bir veri
analizi gerçekleştirilerek rapor elde edilir. Böylece girdi ya da
çıktı veri kümesi mevcut olmasa da program, çalıştırılması sürecinde
bir veri kümesi üretmiş ve kullanmıştır. Son bir örnek olarak ise bir
bilgisayar programının veri kümesi üretmesi mümkündür. Örneğin Twitter
üzerinde İstanbul Üniversitesi araması yapıldığında karşılaşılan
Tweet'lerin toplanıp bir veri kümesi olarak kayıt altına alınması
mümkündür. Bu amaçla yazılan bir bilgisayar programı, girdi olarak
sadece parametrelere ihtiyaç duyarken bir veri kümesi çıktısı üretmiş
olacaktır.
>
Bilgisayar programları ile sıklıkla veri kümelerini kullanarak
işlemler gerçekleştirilmektedir. Bu noktada şu teknik bilgiyi aktarmak
da önemli olacaktır. Bir bilgisayarın hızını en çok etkileyen ölçü
genellikle sabit diske yazma işlemidir. Güncel teknolojiler
gözetildiğinde genellikle bilgisayar üzerinde en yavaş süreç diske
yazma sürecidir. Bu da yapılan işlemler sırasında diske yazmak için
diğer süreçlerin bekletilmesi gerekliliğini ortaya çıkarır. İşlemler
ve diske yazma paralel hale getirilebilir ama bu sefer de işlemlerin
hızlı olması sebebiyle diske yazma sürecinde bozukluklar, kayıtların
birbirine karışması veya bazı kayıtların atlanması gibi problemler
görülebilir.
>
Bir bilgisayar programı vasıtasıyla veri üzerinde işlem yapılması,
beraberinde genellikle ufak tefek çok sayıda dezavantaj getirmektedir.
Bu dezavantajların birçoğu zaman maliyeti arttırılarak çözülebilir.
Yapılacak işlemin basit olması durumunda yani bir işlemin bilgisayar
programı tarafından 1 saniye yerine 3 saniyede gerçekleştirilmesi
kullanıcı açısından önemli bir kayıp olmayacaktır. Ancak halihazırda
uzun sürecek bir işlemin bir de diske yazma süreci sebebiyle uzaması,
ciddi bir performans düşüşü olarak değerlendirilebilir.
>
Tüm bu tartışma konuları, tartışmaya katılanların teknik bilgiye sahip
olması durumunda anlamlıdır ancak bilgisayar programcısının diğer
uzmanlıklara ve yetkilere sahip kişilerle tartışması esnasında açıklık
getirilmesi zor süreçlerdir. Bu sebeple genellikle bir bilgisayar
programcısı ya da programlama ekibi, bu probleme çözüm üretmekten
sorumludur.
>
İster girdi, ister süreç içerisinde, ister çıktı olsun; veri kümesi
ile ilgili işlemler, hangi platform ya da dil kullanılırsa
kullanılsın, sürecin dikkatli karar alınmasını gerektiren önemli bir
parçasıdır. Veri yönetim sürecinde en güvenilir yapı,
karşılaşılabilecek olumsuzluklar için alınmış önlemler ve güçlü
altyapı sebebiyle veri tabanları, dolayısıyla veri tabanı yönetim
sistemleridir. Bir verinin doğrudan diske kaydedilmesi, CSV ya da JSON
gibi hafif bir dosya formatıyla kayıt altında tutulması mümkündür
ancak veri bütünlüğü ve hız
>
konusunda çeşitli problemlere yol açabilirler. Bu sebeple veri tabanı
yönetim sistemi kullanmak süreci daha sağlıklı hale getirecektir.
>
Veri tabanı yönetim sistemleri (VTYS) oldukça çeşitlilik
göstermektedir. Bir önceki ünite altında en sık kullanılan VTYS'ler
hakkında özet bilgiler edindiniz. Birçok VTYS'yi listeleyerek size bu
yazılımlar hakkında bilgi verme amacımız, hem bu alanda öncü
yazılımların hangileri olduğuna dair bilgi sahibi olmanız hem de
ihtiyaç halinde hangisini seçmenin daha faydalı olacağının kararını
verebilmeniz içindir. Yazılım geliştirme süreci yalnızca kodlamadan
ibaret değildir. Bir programın kodlanmasından önce verilmesi gereken
çokça karar, yapılması gereken tasarım ve dokümantasyon işleri, görev
paylaşımı ve ekip yönetimi gibi süreçler bulunmaktadır. Tüm bu
süreçlerin nihayetinde kodlama gerçekleştirilerek yazılım ortaya
çıkartılır. Ancak bu süreçte yapılan hatalar, mükemmel bir kodlama
süreciyle dahi aşılamayacak problemler olarak karşımıza çıkabilir. Bu
esnada verilmesi gereken kararlardan biri elbette ki yazılımın hangi
platform üzerinde geliştirileceğidir. Veri tabanı seçimi, yapılacak
kodlama ortamının ne olduğuna zorunlu olarak bağımlı olmasa da en
uygun veri tabanı seçimi için hâkim olunması gereken bir konudur. Eğer
web tabanlı bir geliştirme yapılıyor ve Linux işletim sistemi üzerinde
PHP dili kullanılıyorsa en uygun veri tabanı seçimi MySQL olacaktır.
Dolayısıyla VTYS'ler için en iyi ya da en uygun tercihi, değişkenlere
bağlı olarak yanıtlanabilecek bir durumdur. Programlama dili ve
platform seçimi de benzer bileşenlere sahip olsa da bu konu bu dersin
kapsamı dışındadır.
>
Bir önceki ünitede çok sayıda VTYS inceledik. Ancak elbette ki
yalnızca özet içerik sunulduğu için, bir VTYS hakkında ayrıntılı ve en
güncel bilgi kendi dokümantasyonundan elde edilebilir. Buradaki
yönlendirme, eldeki platform ve programlama diline uygun olarak VTYS
alternatiflerini belirlemektir. Bu alternatiflerden en uygununun
seçimi, seçilen VTYS'lerin karşılaştırılması, performanslarının
incelenmesi ve topluluk yorumlarının araştırılmasıdır. Bazı konularda
internet aramaları en kesin bilgiyi vermeyebilir. Ancak topluluk
yorumları, bu yorumların önemli bir kısmının incelenmesi ve
yorumlanması neticesinde ciddi bir yol gösterici olacaktır. Ben bu
ders için kullanacağım VTYS seçimini yaparken, öğrenme süreci en kolay
olan örnekleri ve yazılımları tercih etmeye çalıştım ve bunun için
topluluk yorumlarından faydalandım.
>
Yapılacak bir iş için en iyi bilinen araçları kullanmak da bir
yöntemdir. Ancak her zaman en iyi yöntem olmayabilir. Bir programlama
dili, platform, işletim sistemi, veri tabanı ve benzeri yazılım
tercihi yapılırken en iyi bilinenden öte çalışma için en uygununun
tercih edilmesi çok daha performans sağlayacaktır. Benim bu ders için
amacım, kurulum bağımlılığı en az, en kolay öğrenilebilecek ve
üzerinde kolayca örnek uygulamalar gerçekleştirilebilecek bir altyapı
kurmaktı. Tercihim bu doğrultuda oldu. Her ne kadar kişisel olarak
farklı yazılımlara daha aşina olsam da dersin amacına en uygun
yazılımı seçmek ve bunun üzerinde süreci devam ettirmek en doğru
tercih olacaktı. Aynı tutumu sizler de projelerinizde göstermelisiniz.
Bir programlama dilini ya da aracı öğrendikten sonra tüm problemleri
onlarla çözmeye çalışmamalısınız.

## Yapısal Sorgu Dili (SQL – Structured Query Language)

SQL (Structured Query Language), veri tabanıyla ilgili çalışma yapmaya
başlayınca en sık karşılaşılan teknik terimdir. Hatırlayacağınız üzere
Codd'un ilişkisel veri tabanını önerme motivasyonlarından biri, tüm
kullanıcı ve programcılar tarafından kolayca anlaşılabilecek ve
uygulanabilecek üst seviye bir dil ortaya koymaktı. SQL bunu
sağlamaktadır. Uzunca zamandır kullanılan SQL, oldukça basit bir
sorgulama dilidir.
>
Zaman içerisinde çeşitli VTYS'ler ortaya çıkaran firma ve topluluklar,
SQL'in daha yetenekli sürümlerini sunsalar da temelde hepsi SQL'in
yapısı üzerine inşa edilmiştir. Basit sorgular ve ayrıntılarına
gelecek ünitelerde değinecek olsak da basit bir SQL sorgusu görerek
üzerine konuşmaya devam edebiliriz.

<img src="./media/image19.jpeg"
style="width:6.15625in;height:1.0625in" />

Herhangi bir SQL eğitimi almasanız dahi yukarıdaki SQL komutunun ne
anlama geldiğini anlayabileceğinizi düşünüyorum. Okumaya devam etmeden
önce lütfen bir fikir oluşturun.
>
Bu komut, veri tabanı üzerinde bir sorgulama yapan, herhangi bir veri
değişikliğine yol açmayan bir sorgudur. Tam olarak görevi;
Kullanicilar adlı tabloda, maas sütununda yer alan değerler 10000'den
fazla olan kayıtların tüm sütunları görünür şekilde listelenmesidir.
>
Farklı VTYS'ler, SQL içerisinde çok daha karmaşık işlemler
yapılabilmesi için çeşitli yaklaşımlar içermektedir. Bunlardan en
bilinenleri PL/SQL ve T-SQL'dir. Bu SQL çeşitleri farklı yeteneklere
sahip olsalar da temelde SQL'in yaptığı her şeyi yapabilmektedirler.
En basit haliyle SQL hem çok kolay öğrenilebilir hem de uygulanabilir
olduğu için hiçbir VTYS, SQL'in yerine bir dil önermeyi denememiştir
(denediyse bile başarılı olamamıştır).
>
Hangi programlama dilini ya da VTYS'yi kullanıyor olursanız olun,
yukarıda örneği verilen SQL problemsiz çalıştırılacaktır. Bu
evrensellik, ihtiyaca uygun veri tabanının ve programlama dilinin
seçilmesi konusunda ek bir kolaylık sağlamaktadır. Bir veri tabanı
yöneticisi olarak kullanılan altyapıdaki değişim, temel sorgularda
hiçbir zorluk yaratmayacak; karmaşık sorgularda ise kullanılan VTYS'ye
göre bazı kolaylıklar sunabilecektir.
>
Bilgisayar programı ile veri tabanı birbirinden bağımsız çalışan iki
yazılımdır. Bu iki yapıyı bir araya getiren bir sürücü yazılım
(genellikle programlama dili içerisinde kütüphane olarak mevcuttur)
bir de bu sürücü yazılım ile aktarılan komutlar dizisi olmalıdır. Bir
programlama dili ve veri tabanı seçimi yapıldıktan sonra öncelikle
ilgili veri tabanı ile bağlantı kurmayı sağlayan kütüphanelerin
yüklenmesi ve çağrılması gerekmektedir. Bu yapıldığı anda programlama
dili, veri tabanına komut gönderebilir hale gelecektir.
>
Ardından yapılması gereken istenilen komutu göndermektir. Seçilen
programlama dili her ne olursa olsun, veri tabanı güncellemeleri SQL
komutlarıyla gerçekleştirilir. Bilgisayar programı içerisinde bir SQL
komutu karakter katarı (String) olarak hazırlanır ve kütüphanenin
ilgili fonksiyonu kullanılarak veri tabanına gönderilir. Eğer veri
tabanı bu komuta karşılık bir sonuç üretiyorsa, aynı fonksiyon bu
sonucu geri döndürecektir.
>
Şimdi kullandığınız herhangi bir programı düşünün. Mesela Twitter.
Twitter'ın ana sayfasına ulaştığınızda arayüz, SQL sorgulaması yaparak
bir grup Tweet'i çeker ve ekrana basar. Siz bir Tweet yazdığınızda ve
gönder butonuna bastığınızda yine bir SQL sorgusu, girdiğiniz metni
veri tabanına sizin kullanıcı hesabınızla ilişkili olarak kaydeder.
Bir kullanıcının profiline girdiğinizde adres satırında o kullanıcıya
ait bir ibare (id ya da kullanıcı adı) görürsünüz. Bu sayfaya
eriştiğinizde bir SQL komutu, kullanıcıyla ilgili ibareyi de içerecek
şekilde veri tabanını sorgular ve ilgili kullanıcının profiliyle
ilgili detayları veri tabanından alır. Veri tabanından dönen veriler
arayüzde ilgili alanlara doldurulur.
>
Veri tabanı üzerinde işlem yapmanın bir diğer yolu bir veri tabanı
yönetim aracı kullanmaktır. Birçok VTYS geliştirici ekibi, aynı
zamanda veri tabanı yönetimi için de bir yazılım üretmiştir. Ayrıca
veri tabanı yönetimi için evrensel yazılımlar da mevcuttur. Grafik
arayüzlü bu yazılımlar, sürücüsünü barındırdıkları veri tabanlarının
tümüne bağlanabilirler. Bu ders kapsamında bu türde olan DBeaver
yazılımını kullanacağız. Bu türdeki bir yazılım için bir veri tabanına
bağlantı kurmak, üzerinde herhangi bir işlem yapmak için yeterlidir.
Tabloları görüntülemek, kayıtlar girmek ya da güncellemek, çeşitli
sorgulamalar gerçekleştirmek ve bunların çıktılarını veri kümesi
olarak alabilmek en sık kullanılan fonksiyonlardır.

## Nesne-İlişkisel Eşleme (ORM - Object-Relational Mapping)

Oldukça uzun zamandır SQL, veri tabanı yönetimi için yeterli bir
arayüz olmuştur. Programcı, kodlamanın yanı sıra hangi durumun
tetiklenmesiyle veri tabanında hangi değişikliğin yapılacağını kodlama
içerisinde belirleyebilir. Böylece program dahilindeki bir fonksiyonun
çağrılması; istenilen işin gerçekleştirilmesinin yanında bunun veri
tabanına yansımasını da halletmektedir. Halen, programlamada veri
tabanı yönetimi için SQL'in en güçlü yöntem olduğunu söyleyebiliriz
ancak bilgisayar programlamanın SQL kullanma ihtiyacının genellikle
kodlama içerisindeki süreçlerle paralellik gösterdiği fark edilmiştir.
Basit bir program üzerinden örneklendirelim. Bir telefon rehberinde
karşılaşılan ilk ekranda tüm kayıtların listelenmesi beklenir. Bununla
birlikte eğer rehbere yeni bir kişi kaydedecekseniz, bir kayıt formu
açılır ve doldurulan bilgiler kaydet butonuyla birlikte veri tabanına
yazılır. Rehberde yer alan bir kişi seçildiğinde o kişiyle ilgili
kayıtların tümü veri tabanından çekilerek ekrana bastırılır. Sayılan
örneklerin tümü, basit SQL sorgularıyla gerçekleştirilebilir. Bununla
birlikte eğer nesne yönelimli programlama yapıyorsanız muhtemelen kişi
adında bir sınıfınız olacaktır. Rehberde bir kişi seçildiğinde veri
tabanı ilgili ID ile sorgulanır ve sonuç kişi sınıfının
>
bir örneği olarak ele alınır. Yani sınıf ve SQL sorgusu sonucu ayrı
ayrı ele alınır ve kodlama esnasında eşleştirilir. Eşleştirmeden sonra
kişi sınıfının ilgili örneği arayüzün işlenmesi için kullanılabilir.
ORM burada bir çözüm önerisi sunmaktadır.
>
ORM sayesinde kodlamada kurulan bir sınıf yapısı aynı zamanda veri
tabanında yer alan bir tablo ile eşleştirilir. Örneğin kişi sınıfı
veri tabanındaki kişiler tablosuyla eşleştirilmiş olsun. Kodlama
esnasında kişi sınıfından bir örnek üretme esnasında bir koşul vererek
bu örneğin içeriğinin veri tabanından çekilmesi sağlanabilir. Daha
açık olabilmek için iki örnek sunacağım.

<img src="./media/image20.jpeg"
style="width:6.15625in;height:0.72917in" />

Verilen örnekte birinci satırda yer alan SQL sorgusu, users tablosunda
id değeri 7'ye eşit kayıtları elde eder. İkinci satırda da aynı veri
talep edilmektedir. Fark şudur; birinci satırdaki SQL sorgusu, veri
tabanından bir tablo döndürür. Bir satır kayıt ekli olması beklenen bu
veri, kodlama ile işlenerek gerekli şekilde kullanılır. İkinci örnek
ise doğrudan Users sınıfına ait bir örnek üretir ve bu örnek veri
tabanında bulunan, ID değeri 7 olan kullanıcının bilgilerini içerir.
Böylece veri tabanı erişimi, kodlamanın bir parçası gibi görülebilir.
Bu sayede hem mantıksal hem de pratiklik açısından programcıya büyük
kolaylık sağlanır.
>
Şunu unutmamak gerekir; ORM, programlama dilleri içerisinde bir
kütüphane olarak bulunmaktadır ve arka planda SQL sorgularını otomatik
olarak oluşturmaktadır. Yani ORM kullanmayı tercih ederek SQL'i terk
etmiş olmuyoruz; programın SQL sorgularını kendiliğinden oluşturmasını
sağlıyoruz.
>
Akademisyen olmanın yanında uzun zamandır kod yazan bir programcı
olarak şunu itiraf etmeliyim ki ORM tekniği, kod yazma sürecimi çok
hızlandırdı. Yazılımın içerisinde bir akış hazırlarken bu akışın hangi
tablo ve sütunlarla ilgili olduğunu kontrol etmek, SQL hazırlamak,
sorguyu göndermek ve sonucunu işlemek zor olmasa da uğraştırıcı ve
dikkat dağıtıcı bir süreçtir. Bu sebeple ORM tekniğinin kullanımının
gittikçe arttığını gözlemliyoruz.
>
Ancak elbette bu demek değildir ki SQL artık eskidi ve
kullanılmayacak. Şu an üzerinde çalıştığımız programlama dillerinin
arka planda bilgisayarın yorumlayabileceği alt seviye dillere
dönüştürülmesi gibi ORM de SQL'e dönüştürülerek veri tabanı bağlantısı
sağlamaya devam edecektir. SQL'in özellikle tüm VTYS'leri kapsayan
evrenselliği, onu kullanmayı terk etmemizi zorlaştıracaktır. Ancak
kodlama sürecimizi hızlandıran yenilikçi yöntemlere de açık olmak,
bilgisayar programcılığının bir parçasıdır.

## Öğrenme Ortamı

Bu ders kapsamında tasarımı gerçekleştirilmiş bir veri tabanını hayata
geçirmek ve üzerinde çeşitli işlemler yapmayı konu edineceğiz. Dersin
hazırlanması sürecinde iki motivasyon etkili olmuştur:

1. Basit. Dersin amacı, veri tabanı yönetimine odaklanmaktır. Ancak
    bunu izole olarak gerçekleştirmek pek mümkün değildir. Bir VTYS
    seçmek, bir programlama dili belirlemek ve bir grafik arayüzlü veri
    tabanı aracı kullanmak gerekmektedir. Bu sebeple kullanımı en kolay
    olan araçlar tercih edilmiştir. Böylece veri tabanı dışındaki
    konularda takılma olasılığınız en aza indirilmiştir.

2. Modern. Veri tabanı yönetimi içinde bulunduğumuz süreçte özel
    sektörde oldukça rağbet gören becerilerden birisidir. Bu beceriye
    dair akademik bilgiyle birlikte teknik olarak en sık uygulanan
    yöntemleri göstermek de gerekmektedir.

Dersin bundan sonraki kısımlarında çok sayıda örnek yer almaktadır. Bu
örneklerin mümkünse tamamını ve daha fazlasını kendi bilgisayarınızda
uygulamalısınız. Bu sayede tekniğe hakimiyetiniz artacaktır. Dersin
altyapısıyla ilgili ayrıntılar ve kendi bilgisayarınızda nasıl
uygulayacağınıza dair ayrıntılar bu başlık altında verilecektir.
Lütfen aynı altyapıyı kendi bilgisayarınızda da hazır hale getiriniz.
>
<img src="./media/image21.jpeg"
style="width:3.54167in;height:1.8125in" />
>
Veri tabanı yönetim sürecini deneyimleyebilmemiz için bir veri
tabanına ihtiyacımız olduğu aşikardır. Elbette veri tabanını yönetecek
bir yazılıma yani VTYS'ye de ihtiyaç duymaktayız.
>
VTYS'ler, çok sayıda istemcinin anlık erişimine hizmet sunabilen
yapılar oldukları için genellikle bir sunucu üzerinde
yapılandırılırlar. Bir önceki ünitede adı geçen VTYS'lerin çoğunluğu
bir sunucu yapılandırmasıyla birlikte çalıştırılmaktadır. İhtiyacın
genellikle bu paralelde olması sebebiyle de bu durum normaldir. Ancak
ders kapsamında her bir öğrencinin bir sunucu yapılandırmasını ve
üzerine VTYS kurmasını beklemek dersin maksadını aşacaktır. Bu sebeple
bu ders kapsamında VTYS olarak SQLite tercih edilmiştir. SQLite,
bilgisayarda bir dosya oluşturarak tüm veri tabanı yapısının
içerisinde saklanmasını mümkün kılan, ek bir yapılandırmaya ihtiyaç
duyulmayan, son derece basit ve hızlı bir VTYS'dir. Hem kurulum hem de
kullanım sürecinde ek ayrıntılar SQLite ile en aza indirilebilir ve
doğrudan veri tabanı yönetim sürecine odaklanılabilir.
>
Veri tabanına erişim için 3 yöntemden faydalanacağız. Her bir yöntemin
temelde SQL komutları ile işlem yaptığını tekrar hatırlatalım. Biz,
veri tabanı yönetimi için bir aracı yazılım ya da yöntem tercih
ediyoruz ancak bu yöntem veri tabanına erişmek için yine SQL'den
faydalanıyor.
>
İlk yöntemimiz bir grafik arayüz kullanmak. Bunun için, özgür bir
yazılım olan DBeaver kullanacağız. Bu yazılım, sadece SQLite değil,
birçok VTYS'ye bağlanma konusunda oldukça beceriklidir. Dolayısıyla
farklı bir VTYS ile işleme yaparken ihtiyaç duymanız halinde yine
DBeaver kullanabilirsiniz.
>
DBeaver'in güncel sürümüne dbeaver.io web sitesi üzerinden
erişebilirsiniz. Web sitesinden yazılımın son sürümünü indirdiğinizde
aşağıdaki pencere ile karşılaşacaksınız.

<img src="./media/image22.jpeg"
style="width:6.30208in;height:3.94792in" />

Yazılımı çalıştırdığımızda, henüz hiçbir veri tabanı ile bağlantısı
olmadığı için karşılaşacağımız görüntü görseldeki gibi olacaktır.
Şimdi ilk bağlantıyı sağlamaya çalışalım. Lütfen siz de
gerçekleştirin.

<img src="./media/image23.jpeg" style="width:6.30208in;height:5.75in" />

Görselde 1 olarak numaralandırılmış yuvarlak içerisinde bir fiş ikonu
görmektesiniz. Bu yazılım, genellikle mevcut bir veri tabanına
bağlanmak ve onu yönetmek amacıyla kullanıldığı için, buradaki ikon da
bağlantıyı sağlama anlamına gelmektedir. İkona tıkladığınızda bağlantı
sağlanabilecek VTYS'ler listelenmektedir.
>
Listede öncelikli olarak sık kullanılanlar görüntülenmektedir. Other
(diğer) seçeneği ile bağlanılabilecek tüm VTYS'leri
görüntüleyebilirsiniz. Ekran görüntüsünün en altında bu listenin aşağı
doğru devam edeceğini gösteren bir ok ikonu var. DBeaver, onlarca VTYS
ile bağlantı kurmak üzere destek sağlamaktadır. Bu dersin kapsamında
öğrenilmesi en kolay ve ücretsiz araçlar tercih edilmiştir. Ancak
bununla birlikte çok daha gelişmiş ve karmaşık projelerde de aynı
adımları izleyebilirsiniz. Örneğin şu anda bağlantı için SQLite veri
tabanını seçeceğiz ancak bunun yerine MySQL seçerek internet üzerinde
hizmet sağlayan bir veri tabanına da bağlanarak aynı işlemleri
gerçekleştirebilirdiniz. Ölçeğin farklılığı, daha basit bir iş
gerçekleştirdiğiniz yanılgısı oluşturmasın. Büyük projeler de benzer
küçük adımlarla başlar.
>
<img src="./media/image24.jpeg"
style="width:6.29167in;height:5.13542in" />
>
Bağlantı kurulacak VTYS olarak SQLite seçtiğimizde görseldeki ekranla
karşılaşmaktayız. Eğer bunu ilk kez yapıyorsak yazılım SQLite
bağlantısını sağlayabileceği bir sürücü (driver) kurulumu
gerçekleştirecektir.
>
Bunu sizden izin alarak otomatik olarak gerçekleştirir. Ayrıca bir
işlem yapmanıza gerek kalmaz.
>
İlk kez veri tabanı kurulumu yaptığınızı varsayarak 1 numaralı adım
olan Create (oluştur) seçeneği üzerinden ilerleyebiliriz. Veri
tabanları, çok kullanıcıya aynı anda hizmet verebilmesi için
genellikle internet sunucuları üzerinde konumlandırılırlar. Ancak
SQLite daha çok yerel olarak veri saklama ve işleme için kullanılmakta
olduğu için bilgisayarda bir dosya açarak işlemleri bu dosya üzerinde
gerçekleştirir. Oluştur butonu size bu dosyanın kaydedileceği yeri ve
adını soracaktır.
>
Burada önerim; her türlü geliştirme projelerinizi barındıracağınız
temel bir dizin oluşturmaktır. Ben bunu ayrı bir disk altında “work”
adında klasörüm ile yapıyorum. Bu ders çalışmalarımızı gerçekleştirmek
üzere db klasörü açtım ve veri tabanını myfirstdb adıyla kaydettim. 2
numaralı alanda bu bilgiyi ayrıntılı görebilirsiniz.
>
Bu noktada işlem aslında sona eriyor ancak bir kontrol etmekte fayda
var. SQLite için pek problemle karşılaşılmaz ancak diğer VTYS'lerde
izin problemleri yaşanabilir. Bunu test etmek için 3 numaralı Test
Connection (Bağlantıyı test et) butonuyla bir test gerçekleştirelim.
>
Bunu yaptığımızda 4 numara ile işaretlediğim iletişim kutusu ile
karşılaşacaksınız. İşaretli alanda Connected (Bağlantı sağlandı)
ibaresini görüyorsanız herhangi bir problem kalmadı demektir. Bu
iletişim kutusunu kapattıktan sonra bir önceki ekranı da Finish
(Bitir) butonuyla kapatabilirsiniz.
>
<img src="./media/image25.jpeg"
style="width:6.30208in;height:4.05208in" />
>
Yeni veri tabanı oluşturduğunuzda DBeaver'in sol menüsüne myfirstdb
adlı veri tabanının gelmiş olduğunu görebilirsiniz. Elbette bu veri
tabanı tamamen boş olduğu için herhangi bir tablo ya da içerik
görmemiz mümkün değildir.
>
DBeaver'i kapatıp açtığımızda artık doğrudan bu görüntü ile
karşılaşacağız. Başka bir veri tabanı açmak istediğimizde ya da farklı
bir yazılım kullanmak istediğimizde Create (oluştur) yerine Open (aç)
menüsü üzerinden SQLite veri tabanı dosyamızın adresini göstermemiz
yeterli olacaktır. Unutmayın; verimiz DBeaver içerisinde değil, dosya
olarak kaydettiğimiz SQLite dosyası içerisinde saklanmaktadır. DBeaver
sadece bu veri tabanına erişmek ve üzerinde işlem gerçekleştirmek için
kullanılan bir aracı yazılımdır ve alternatifleri oldukça fazladır.

<img src="./media/image26.jpeg"
style="width:6.30208in;height:3.48958in" />

Veri tabanı yönetimindeki en yaygın aracın SQL kullanmak olduğundan
bahsetmiştik. Hazırlamış olduğumuz veri tabanı üzerinde DBeaver
kullanarak SQL ile işlem yapmak için görselde yuvarlak içerisine
alınmış SQL butonuna tıklamamız gerekmektedir. Bunu yaptığımızda
ekranın sağ tarafına metin girişi yapabileceğimiz bir alan gelecektir.
Bu alana SQL komutunu yazdıktan sonra sol tarafında yer alan üçgen
(çalıştırma) butonuna basarak SQL komutunun veri tabanı üzerinde
çalıştırılmasını sağlayabiliriz.
>
Hatırlayacağınız üzere diğer iki yöntem; bir programlama diliyle
doğrudan SQL komutları çağırmak ve ORM yöntemiyle veri tabanı yönetimi
sağlamak idi. Bu iki yöntemde de bir programlama dilini kullanmak
gerekmektedir. Bu yeteneklere sahip olan, seçilebilecek çok sayıda
programlama dili mevcut. Ancak bu ders kapsamında amacımız bir
programlama dilini öğretmek olmadığı için kurulumu ve kullanımı en
kolay, aynı zamanda en yaygın dili seçme motivasyonuyla Python dili
tercih edilmiştir. Daha önce Python ile bir deneyiminiz olmadıysa
moraliniz bozulmasın. Yapacağımız işlemler için yeteri kadar
programlama bu ders içerisinde göreceğiz. Ancak şunu da unutmamanız
gerekir. Bu ders kapsamında bir veri tabanı yönetimi için gereken
miktarda Python dilini göreceğiz. Dolayısıyla bu ders kapsamında
gösterilen işlevleri kullanabiliyor olmanız bu dile tam hakimiyet
kurduğunuz anlamına gelmeyecektir. Elbette güzel bir başlangıç olacağı
da aşikardır.
>
Bilgisayarınızın Python dilini yorumlayabilme ve Python betiklerini
çalıştırabilmesi için birkaç kurulum yöntemi bulunmaktadır ve bu
yöntemler işletim sistemine göre farklılık gösterebilir. Başlangıç
seviyesi için kullanılan yöntem Anaconda yazılım paketini kurmaktır.
Anaconda, Python ile birlikte faydalı olabilecek birçok aracı
bilgisayarınıza tek bir kurulumla yüklemenizi sağlayacaktır.
Anaconda'yı, anaconda.com web sitesinden ücretsiz olarak indirerek
bilgisayarınıza kurulumunu gerçekleştirin.

<img src="./media/image27.jpeg"
style="width:6.29167in;height:2.83333in" />

Anaconda, birçok aracı beraberinde getirir ancak bizim temelde 2 şeye
ihtiyacımız var. Birincisi bilgisayarın Python dilini çalıştırabilir
hale gelmesi, ikincisi ise Python kodlarımızı yazıp
çalıştırabileceğimiz bir ortam. Anaconda'yı yükleyerek birinci
amacımıza ulaşmış olmaktayız. Artık bilgisayarımız Python dilini
tanıyor.
>
İkinci amaç için ise Anaconda içerisine bir göz atmak lazım.
Anaconda'yı çalıştırdığımızda, bu yazılım paketiyle birlikte gelen tüm
yazılımları görmekteyiz. Python ekosistemiyle ilgili faydalı çok
sayıda yazılımı bu sayfada görebilir ve kolayca kullanabiliriz. Kendi
Python kodlarımızı, diğer dillerde olduğu gibi yeni bir Not Defteri
dosyasına yazabilir, “py” uzantılı olarak kaydedebilir ve terminalde
çalıştırabiliriz. Ancak programlamaya yeni giriş yapan arkadaşlar için
bu yöntem biraz karmaşık gelebilir. Bu sebeple biz Anaconda içerisinde
de gelen Jupyter Notebook yazılımından faydalanacağız. Bu yazılım,
Python kodları yazarak anında çalıştırıp yanıtını görebildiğimiz,
üzerine notlar alabildiğimiz, bir nevi kodlama ile not tutma
fonksiyonlarını birleştirmiş bir araçtır. İnternet tarayıcısı
(browser) üzerinden çalışması, en yazılım ve terminal kullanımına
ihtiyaç duyulmamasını sağlamaktadır. Bu da öğrenme sürecini
hızlandırır ve kolaylaştırır.
>
Notebook'u çalıştırmak için Anaconda'yı açın, panelde Notebook yazan
kutuyu bulun ve Launch (Çalıştır) butonu ile yazılımı çalıştırın. Eğer
Launch yerine Install (Yükle) butonu görüyorsanız buna bir kere
tıklayarak kurulumu tamamlayabilir ve Launch butonuna ulaşabilirsiniz.
Notebook'u çalıştırdığınızda bir terminal (komut istemi) penceresi
açılacak ve Notebook açık olduğu sürece açık kalacaktır. Bu pencereyi
kapatmayın. Notebook'u çalıştırdığınız anda internet tarayıcınız
açılacak ve aşağıdaki görseldeki sayfa ile karşılaşacaksınız.
>
<img src="./media/image28.png"
style="width:6.30208in;height:1.4375in" />
>
Gördüğünüz üzere karşılaştığınız ilk arayüz klasör ve dosyaları içeren
bir navigasyon arayüzü. Öncelikle burada, çalışmaları
gerçekleştirdiğiniz klasöre ulaşın. Biraz önce DBeaver kullanarak bir
SQLite veri tabanı dosyası oluşturmuştuk. İlgili veri tabanının
bulunduğu klasöre erişmenizi ve o klasör içerisinde çalışmanızı
öneririm. Sayfa üzerinde 1 ile işaretli yer bulunduğunuz konumu, 2
numara bulunduğunuz klasörün içeriğini, 3 numara ise yeni bir dosya
oluşturma seçeneklerini gösterir. 2 numara ile daha önce
oluşturduğumuz veri tabanını görmekteyiz. Dolayısıyla veri tabanı ile
aynı klasör içerisinde işlem yaptığımıza emin olabiliriz.
>
Şimdi 3 numaralı seçeneklerden biri ile kodlama ekranına geçeceğiz.
Eğer mevcut bir dosya üzerinden devam edeceksek Upload (Yükle)
seçeneği ile devam edebiliriz. Ancak ilk kez oluşturuyorsak New (Yeni)
seçeneğini seçerek ilk dosyamızı oluşturabiliriz.

<img src="./media/image29.jpeg"
style="width:5.10417in;height:2.48958in" />

Ben yeni bir dosya oluşturdum ve yukarıdaki ekran ile karşılaştım.
Notebook'umuz açıldıktan sonra 1 yazılı alanı kullanarak dosya adını
güncelleyebiliriz. 2 numaralı alana bakarsanız hem dosyamızın konumunu
hem de hangi dosya üzerinde çalıştığımızı görebilirsiniz. Şimdi ilk
kodumuzu yazarak testimizi gerçekleştirelim. 3 numaralı alana;
>
print(“Merhaba Bilgisayar Programcısı!”)
>
yazalım ve 4 numaralı butona tıklayarak bu kutu içerisindeki kodun
çalıştırılmasını sağlayalım. Bunu yaptığımızda 5 ile işaretli yanıtı
göreceğiz. Bu yanıt, bizim kodumuz çalıştırıldığında Python dilinin
ürettiği yanıttır. Kodlamaya devam etmek için 6 numaralı + butonuna
tıklayarak yeni kodlama kutuları açabiliriz.
>
İlgili butona tıkladığımızda 7'de görüldüğü gibi yeni bir alan
karşımıza çıkacaktır.
>
Böylelikle tüm kodlamamızı parçalara bölerek kutularda yapabilir ve
adım adım yanıtlarının ne olduğunu inceleyerek devam edebiliriz.
Ayrıca notlar alarak hangi kutuda hangi işlemi yaptığımızı da kayıt
altına alabiliriz. Tebrikler, Python kodu yazdınız!
>
Python kodlaması yapabileceğimiz altyapıyı da hazırladığımıza göre
sırada ORM tekniğini nasıl kullanacağımız var. Bunun için yine
öğrenmesi ve kodlaması en basit olan paket SQLAlchemy tercih
edilmiştir. Bu paketin bilgisayarınıza kurulumu oldukça basittir.
>
<img src="./media/image30.jpeg"
style="width:6.30208in;height:2.01042in" />
>
Notebook üzerinde bir kutuya; pip install sqlalchemy
>
yazarsanız, Python sizin için ilgili paketin kurulumunu tamamlayacak
ve kullanılabilir hale getirecektir.

## Veri Tabanını Oluşturmak

Karşılaştığınız bir olay için nasıl veri tabanı tasarımı
gerçekleştirmeniz gerektiği, bir önceki dönem dersi olan Veri Tabanı
Tasarımı'nda sunulmuştu. Bu ders, veri tabanının nasıl yönetileceğiyle
ilgili tasarlanmıştır. Bu sebeple veri tabanının hazırlanmış olduğu
durum başlangıç noktası kabul edilerek anlatım gerçekleştirilecektir.
>
Bu ders boyunca tüm örneklerde kullanacağımız bir veri tabanının bu
aşamada tanımlayacağız. Seçtiğimiz veri tabanı MySQL VTYS'nin
dokümantasyonunda örneklendirme için bulunan ve ayrıntılı tarif edilen
“Employee” veri tabanıdır\[1\].
>
Bu veri tabanındaki tablo ve değişken adları hem Türkçeleştirme hem de
bizim notasyonumuza göre tekrar oluşturulduğunda veri tabanı
tasarımımızın son hali aşağıdaki diyagramda verildiği gibi olmaktadır.

<img src="./media/image31.png"
style="width:6.29167in;height:3.78125in" />

Bu veri tabanında bir iş yerindeki bölümler, çalışanlar, çalışanların
pozisyonları, çalışanların bölümde yer alma durumları ve
yöneticilikleriyle birlikte maaşları da kayıt altına alınmaktadır.
Calisan ve Pozisyon tabloları bire çok, Calisan ve Maas tabloları bire
çok, Calisan ve Bolum tabloları çoğa çok bağlantılıdır. Kurulan çoğa
çok bağlantı hem görev alma hem de yöneticilik faaliyetleri için bilgi
saklamak amacıyla 2 bağlantı tablosu kullanılarak
gerçekleştirilmiştir.
>
Bu veri tabanı tasarımını bizim gerçekleştirdiğimizi ve yeni açtığımız
boş veri tabanı içerisine bu veri tabanının girişini yapmak
istediğimizi varsayalım. Bildiğiniz üzere veri tabanı yönetimi için
kullanacağımız üç yöntem bulunmaktaydı. Yapacağımız her bir sorgulama
için üç yöntemi de kullanarak yanıtları üç yöntemle de ele alabiliriz.
Ancak şu aşamada veri tabanı tasarımını gerçekleştirmek üzere tablo
tanımlamaları yapacağımız için bir komutun üç yolla tekrar tekrar
girilmesi uygun bir davranış değildir.
>
Şöyle açıklayalım: İlk yapacağımız iş Calisan tablosunu tanımlamak
olsun. Bu tabloyu DBeaver üzerinden SQL komutu ile tanımlarsak SQLite
içerisinde bu tablo hazır olacaktır. Daha sonra aynı SQL komutunu
başka bir yöntemle tekrar veri tabanına gönderirsek hata ile
karşılaşacağız. Çünkü veri tabanı içerisinde zaten bu tablo
tanımlanmış olacaktır. Bu sebeple veri tabanımızı gerçekleştirirken
farklı görevleri farklı yöntemlerle gerçekleştireceğiz. Böylece hem
tüm yöntemleri kullanmış olacağız hem de sonuç olarak veri tabanını
bir bütün olarak gerçekleştirmiş olacağız. Haydi başlayalım.
>
Toplamda tanımlanması gereken 6 tablo mevcut. Bunlar; Calisan, Bolum,
Maas, BolumCalisan, Pozisyon ve Yoneticilik tabloları. Üç
yöntemimizden her biriyle ikişer tablo tanımlayalım. İlk olarak
Calisan ve Bolum tablolarını DBeaver kullanarak SQL komutu ile
tanımlayalım. Öncelikle verilen veri tabanı tasarımı diyagramına uygun
olarak Calisan tablosunu oluşturacak SQL komutunu inceleyelim:

<img src="./media/image32.jpeg"
style="width:6.16667in;height:1.51042in" />

Yukarıda verilen SQL komutunu inceleyelim. CREATE TABLE komutu, veri
tabanında yeni bir tablo oluşturmak için kullanılır. Ardından gelen
Calisan kelimesi, tanımlanacak tablonun adının belirtildiği kısımdır.
Sonraki bileşen ise bir komutlar grubu olduğu için parantez ()
kullanılarak belirtiliyorlar. Parantez içerisinde gruplanmış komutlar,
bu tabloda yer alacak nitelikleri belirtmektedir. Her bir nitelik,
virgül (,) ile birbirinden ayrılmaktadır. Her bir nitelik; nitelik
adı, veri tipi ve varsa ek özellikleri kullanılarak tanımlanır.
Örneğin ilk nitelik id'dir, Integer tipindedir ve birincil anahtardır.
dogumTarihi ise Integer tipinde olarak ek bir özellik olmadan
tanımlanmıştır. adi niteliği Varchar yani alfanümerik değişkendir.
Parantez içerisindeki 255 değeri en fazla 255 karakter uzunluğunda
değer alabileceğini gösterir. Varchar veri türü yapısı gereği en fazla
255 karakter alabilmektedir. Bu sayıyı arttıramayız ancak
azaltabiliriz. Örneğin cinsiyet niteliği için yine Varchar tipi
kullanılmış ancak en fazla 10 karakter alan kullanılmıştır. Eğer 255
karakterden fazlasına ihtiyaç duyuyorsak Text veri tipini kullanmamız
gerekmektedir. Her bir SQL sorgusu noktalı virgül (;) ile
ayrılmalıdır. Eğer çalıştırılacak SQL tek bir komutsa noktalı virgül
kullanmasak da hata almayız. Ancak birden fazla SQL komutunu aynı anda
çalıştıracaksak her bir SQL komutunun sonunda noktalı virgül kullanmak
gerekmektedir.
>
<img src="./media/image33.jpeg"
style="width:4.57292in;height:3.625in" />
>
Tanımladığımız SQL komutunu çalıştırmak için DBeaver yazılımını açalım
ve sol taraftan ilgili veri tabanını seçelim (adına tıklayalım).
Sonrasında sağ tarafta SQL bölmesini açarak hazırladığımız SQL
komutunu 1 olarak işaretli bu alana yazıyoruz. Sonrasında 2 numara ile
işaretli buton ile komutumuzu çalıştırabiliriz.
>
Çalıştırma sonucunu 3 numaralı alandan izleyebiliriz. Eğer komut bir
veri döndürüyorsa 3 numaralı alan bize sonucu gösterir. Ancak bu komut
yeni bir tablo oluşturan ancak herhangi bir veri döndürmeyen bir
komuttur. Tanımlama işlemi sonucunda 4 numaralı alanda yeni tablomuzun
adını görmeliyiz. Eğer göremiyorsak bu alanın yenilenmesi gerekebilir.
Bu durumda 5 numaralı veri tabanı adına tıklayarak F5 kısayolu ile
yenileyebilir ya da sağ tıklayarak Refresh butonu ile yenileme
yapabiliriz. Böylece veri tabanımız içerisinde ilk tablomuzu
tanımlamış olduk. Sıra ikincisinde.

<img src="./media/image34.jpeg"
style="width:6.11458in;height:0.76042in" />

İkinci tablomuz Bolum tablosu. Gördüğünüz gibi aynı SQL yapısı ile
tablomuzu tanımlayacağız. CREATE TABLE zorunlu bir komut, Bolum tablo
adı, nitelikler parantez içerisinde virgülle ayrılmış şekilde
görülmektedir. Bir önceki yöntemi uygulayarak SQL komutumuzu DBeaver
üzerinde çalıştıralım ve ikinci tablomuzu da oluşturmuş olalım.

<img src="./media/image35.jpeg"
style="width:3.59375in;height:2.66667in" />

Veri tabanı tasarımımızdaki 6 tablodan 2 tanesini tanımladık. Şimdi
Python kodu yazarak yani bir programlama dili kullanarak veri tabanı
üzerinde SQL komutu çalıştırmayı; bu sayede veri tabanı tablosu
oluşturmayı deneyimleyelim. Veri tabanı tasarımımızdaki Pozisyon ve
Maas tablolarını tanımlayacağız.
>
Jupyter Notebook üzerinde CreateTables adında yeni bir dosya
oluşturdum. Oluşturduğum dosyamın SQLite veri tabanımla aynı dizinde
bulunması oldukça önemli. Şimdi çalıştırılması gereken kodları birer
birer inceleyelim.

<img src="./media/image36.jpeg"
style="width:5.65625in;height:0.67708in" />

Python kodunda \# işaretiyle başlayan satırlar yorum satırıdır. Bu
satıra istediğiniz metni yazabilirsiniz. Kod çalışırken \# işaretiyle
başlayan satırlar dikkate alınmazlar. Böylece yazdığınız kod
içerisinde çeşitli notlar alabilirsiniz.
>
“import sqlite3” komutu, programımız içerisinde SQLite işlemleri
yapabilmemizi sağlayan paketi yükler. Bu paketi yükleyerek veri tabanı
üzerinde tüm işlemleri gerçekleştirebiliriz.

<img src="./media/image37.jpeg"
style="width:6.125in;height:0.41667in" />

İkinci kod bölümünde yine bir yorum satırının ardından veri tabanı
bağlantısı komutunu görüyorsunuz. conn ifadesi bir değişkendir,
istediğimiz adı verebiliriz. Gerçekleştirdiğimiz bağlantıyı bu
değişkene yüklüyoruz. Böylece gelecekte, kurduğumuz bağlantı üzerinden
bir işlem yapmak istediğimizde bu değişkeni kullanarak basitçe
gerçekleştirebiliriz. Veri tabanı bağlantısı için connect fonksiyonunu
kullanacağız. Ancak bu fonksiyon sqlite3 paketi içerisinde yer aldığı
için çağırırken paket adını da belirtmeliyiz. Böylece
sqlite3.connect() fonksiyonu bizim için bağlantı sağlar. Fonksiyon
içerisinde yer alan değer, bağlantı sağlanacak veri tabanı yolunu
gösterir. Aynı dizinde olduğu için doğrudan dosya adını verebiliyoruz.
Eğer veri tabanımız ve Python kodumuz farklı dizinlerde yer alsaydı
veri tabanının tam yolunu vermek zorunda kalacaktık. Bu sebeple aynı
dizin içerisinde çalışmak kolaylık açısından önemlidir.

<img src="./media/image38.jpeg"
style="width:6.20833in;height:0.59375in" />

Bir sonraki kod bloğunda öncelikle veri tabanı ile iletişimizi
sağlayacak bir araç oluşturacağız. Bu araca Cursor adı veriliyor.
Ayrıca oluşturduğumuz bu aracı bir değişkene yüklemeliyiz. Bu sayede
gelecekte değişkeni kullanarak Cursor aracını çağırabiliriz.
>
Kodda yer alan cursor bir değişkendir. Bu değişkene veri tabanı
bağlantısını simgeleyen conn değişkeni altındaki cursor() fonksiyonunu
çağırıyoruz. Böylece veri tabanı bağlantısına ait bir cursor aracı,
cursor adlı değişkene yüklenmiş oluyor.
>
Bir sonraki satırda cursor aracının bir SQL sorgusunu veri tabanına
götürmesini istiyoruz. Bu da cursor aracına ait execute() fonksiyonu
ile sağlanabiliyor. cursor.execute() fonksiyonu, parametre olarak
aldığı SQL komutunu veri tabanı üzerinde çalıştıracaktır. Ekran
görüntüsünde SQL komutunun tamamı gözükmediği için aşağıda tekrar
belirtiyorum. Kod içerisinde bu komutu lütfen tek satırda yazınız.
>
<img src="./media/image39.jpeg"
style="width:6.13542in;height:1.46875in" />
>
Veri tabanıyla işlemlerimizi sonlandıralım:

<img src="./media/image40.jpeg"
style="width:6.26042in;height:1.11458in" />

commit() fonksiyonu, yaptığımız değişiklikeri veri tabanına kaydeder.
Bir bağlantı üzerinden gönderilmesi gerektiği için conn değişkenine
bağlı olarak çağrılır. Bununla birlikte veri tabanına ihtiyacımız
kalmadığı için bağlantıyı kapatmalıyız. Bağlantı kapatma, bağlantı
değişkeni olan conn üzerindeki close() fonksiyonuyla gerçekleştirilir.
>
Veri tabanı bağlantısı kapatmak önemlidir. İlgili kod betiği
tamamlandığında veri tabanı bağlantısı kapatılmazsa açık kalır. Aynı
ya da farklı kod tekrar çalıştırıldığında yeni bir bağlantı
oluşturulur. Bir önceki açık bağlantı artık ulaşılamaz durumdadır
ancak aynı zamanda açık kalmıştır. Bu da tutarsızlık ve gereksiz
kaynak tüketimine sebep olabilir. Bu sebeple kodlamanın bitiminde veri
tabanı bağlantısını kapatmamız gerekmektedir.
>
Bu kod bloklarını çalıştırdığımızda veri tabanı tablosu tanımlanmış
olacaktır. Ancak herhangi bir yanıt ya da ekran görüntüsü edinmemiz
için ek bir işlem yapmamız gerekir. Bu kod bloğunu çalıştırdıktan
sonra DBeaver açarak ve ilgili veri tabanı alanını F5 ya da Refresh
seçeneği ile yenileyerek tablonun tanımlandığını görebiliriz. Ancak
bunu da kodla yapmak istiyorsak en son incelediğimiz veri tabanı
bağlantısını kapatma işleminden önce yazacağımız bir sorgu kodu ile
veri tabanında yer alan tabloları öğrenebiliriz.

<img src="./media/image41.jpeg"
style="width:6.21875in;height:1.57292in" />

Kod bölümünde ilk komut SQL komutu çalıştırmayı sağlar. Bu komuna
aşinayız artık. Bir sonraki komut, cursor üzerinde yer alan veriyi
yakalamak ve bir değişkene (tables) yüklemek içindir. Artık
çalıştırdığımız SQL komutunun yanıtının tables değişkeni üzerinde
olduğunu biliyoruz. print fonksiyonunu kullanarak bu değişkenin
içeriğini görüntüleyebiliriz.
>
Kod bloğunun hemen altındaki kısma dikkat edin lütfen. İlk kez veri
tabanından bir yanıt alıyoruz. Veri tabanı bize Calisan, Bolum ve
Pozisyon adlı 3 tablomuz olduğu bilgisini döndürdü.
>
Şimdi tüm bu kodlamayı bir arada inceleyelim:
>
<img src="./media/image42.jpeg"
style="width:6.08333in;height:4.8125in" />
>
Şimdi Maas tablosunu tanımlayarak devam edelim. Yine Python dilini
kullanarak tanımlama gerçekleştireceğiz. İhtiyaç duyduğumuz SQL kodu
şu şekilde olacaktır:

<img src="./media/image43.jpeg"
style="width:6.15625in;height:1.47917in" />

Bu SQL komutunu çalıştırabileceğimiz Python kodu şu şekilde olacaktır:
>
<img src="./media/image44.jpeg"
style="width:6.30208in;height:4.79167in" />
>
Dördüncü kod bloğunun yanıtını incelediğinizde sonuç olarak artık 4
tablo adının dönüş yaptığını görebilirsiniz. Veri tabanımızda artık 4
tablo mevcut. Dilerseniz DBeaver üzerinden de 4 tablo olduğunu
görüntüleyebilirsiniz.
>
Böylece tanımlamamız gereken 2 tablo kaldı. Kalan tablolarımızı da
Python dilinin bir ORM kütüphanesi olan SQLAlchemy kullanarak
tanımlayacağız. BolumCalisan ve Yoneticilik tablolarımızı ORM
kullanarak tanımlayacağız.
>
DBeaver ve Python dili ile doğrudan SQL komutu göndermek ile ORM
kullanmak bir noktada önemli bir farklılık içermektedir. DBeaver ve
Python ile doğrudan veri tabanına erişilebilir ve komut gönderilerek
uygulanabilir. Ancak ORM, nesne yönelimli bir programın veri tabanı
tasarımıyla eşleştirilmesi ile oluşturulur ve ilgili programlamada
yapılan güncellemeler veri tabanına yansıtılır. Bu sebeple bir veri
tabanı güncellemesi yapmak için halihazırda Python dilinde bir program
yazılmalı ve bu program üzerinde yapılacak güncellemeler ile veri
tabanı güncellemeleri gerçekleştirilmelidir.

<img src="./media/image45.jpeg"
style="width:6.21875in;height:0.69792in" />

Yukarıdaki kod parçası, Python içerisinde kullanılan ORM paketi olan
SQLAlchemy'i, ilgili alt paketleriyle birlikte çağırmak için
kullanılan komutlardır.

<img src="./media/image46.jpeg"
style="width:4.63542in;height:0.65625in" />

İkinci kısım, veri tabanı bağlantısı sağlamak için gerekli kodları
içermektedir.
>
<img src="./media/image47.jpeg" style="width:4.625in;height:1.375in" />
>
ORM yapısında veri tabanındaki bir tablo, nesne yönelimli
programlamada bir Class (sınıf) ile eşleşmektedir. Bu sebeple veri
tabanı üzerinde herhangi bir işlem gerçekleştirmeden önce bu işlemin
yapılacağı sınıfın tanımlanmış olması gerekmektedir. Şu an
gerçekleştirmek istediğimiz şey, Yoneticilik adlı tabloyu
tanımlamaktır. Bunu yapabilmek için Yoneticilik adlı sınıfı
oluşturmalı ve bu sınıfın veri tabanı ile eşlenmesini sağlamalıyız.
Yukarıdaki kod bloğu yeni bir sınıf tanımlanmasını sağlar. Bu
tanımlama Base değişkenini alır, bu da SQLAlchemy'nin veri tabanı
bağlantısı kurmasını sağlar. Sınıf içerisinde
>
tablename değişkeni, bu sınıfın hangi tablo ile birlikte çalıştığını
tanımlar. Ardından gelen değişkenler ise yine bu sınıf içerisinde yer
alan değişkenlerdir. Elbette, eşleştirme yapıldığı anda sınıf
içerisinde yer alan değişkenler veri tabanında ilgili tablonun da
içerisinde yer alacaktır.

<img src="./media/image48.jpeg"
style="width:4.13542in;height:0.375in" />

Yukarıdaki kod bloğu çalıştırıldığında tanımlanan sınıflar veri tabanı
üzerinde de oluşturulur ve eşleştirmeler tamamlanır. Bundan sonra
sınıflar ve veri tabanı tabloları hazır olacağı için veri tabanı
işlemleri yapmak için sınıfları kullanmak yeterli olacaktır.
>
Şimdi, BolumCalisan tablosunu oluşturmak için gerekli kodlamayı da
gerçekleştirelim.

<img src="./media/image49.jpeg"
style="width:6.30208in;height:2.90625in" />

Böylece veri tabanı tasarımımızı, SQLite veri tabanı üzerinde
gerçekleştirmiş olduk. Toplamda 6 tablomuzun tamamı veri tabanımız
içerisinde tanımlı durumda. DBeaver kullanarak veri tabanı
tablolarımızı kontrol edebiliriz:
>
<img src="./media/image50.jpeg"
style="width:2.32292in;height:2.70833in" />
>
Aslında bu noktada veri tabanı tanımlama işlemlerimizin tamamını
sonuca ulaştırdık. Ancak daha önce de üzerinde durduğumuz gibi, ORM
kullanımında veri tabanına direkt erişim yerine öncelikle sınıf
tanımlamaları yapmak gerekiyor. Biz yalnızca 2 tabloyu ORM ile
oluşturduğumuz için iki tablonun tanımlanmasını gördük. Gelecek
bölümde ORM ile sorgulama işlemleri yapacağımız için tüm
sınıflarımızın tanımlamalarının yapılmış olması gerekiyor. Bu sebeple
son olarak Python SQLAlchemy ile sınıf tanımlamalarımızı tamamlayarak
bu bölümü sonlandıralım.
>
Gerekli paketleri çağıralım:

<img src="./media/image51.jpeg"
style="width:6.1875in;height:0.67708in" />

SQLite bağlantısı kuralım:

<img src="./media/image52.jpeg"
style="width:4.35417in;height:0.44792in" />

Calisan sınıfını tanımlayalım:

<img src="./media/image53.jpeg"
style="width:4.21875in;height:1.875in" />

Bolum sınıfını tanımlayalım:

<img src="./media/image54.jpeg"
style="width:4.28125in;height:0.78125in" />

Pozisyon sınıfını tanımlayalım:
>
<img src="./media/image55.jpeg"
style="width:5.89583in;height:1.54167in" />
>
Maas sınıfını tanımlayalım:

<img src="./media/image56.jpeg"
style="width:5.125in;height:1.39583in" />

Yoneticilik sınıfını tanımlayalım:

<img src="./media/image57.jpeg"
style="width:5.36458in;height:1.48958in" />

BolumCalisan sınıfını tanımlayalım:

<img src="./media/image58.jpeg"
style="width:5.51042in;height:1.45833in" />

Eğer tanımlanan sınıflar için veri tabanı tablolarının da
oluşturulmasını istiyorsak aşağıdaki kodu çalıştırabiliriz:

<img src="./media/image59.jpeg"
style="width:3.86458in;height:0.33333in" />

Ancak bizim örneğimizde zaten tüm tablolar tanımlanmış olduğu için bu
komutu çalıştırsanız bile veri tabanı üzerinde bir değişiklik
olmayacaktır. DBeaver kullanarak tüm tabloları sildikten sonra bu
komutları çalıştırarak tüm tabloların ORM ile tanımlanmasını da
sağlayabilirsiniz. Bu örnek ve kombinasyonları, sizin için faydalı
egzersizler olacaktır.
>
DBeaver veya Python ile doğrudan SQL komutları ile yapacağınız
işlemler için herhangi bir ön hazırlığa gerek bulunmamaktadır. Veri
tabanı bağlantısı kurulduğu anda SQL komutunuzu sisteme
gönderebilirsiniz. Ancak ORM ile bir güncelleme yapmak için sınıfı
çağırmanız gerekeceği için sınıfın tanımlanmış olması
>
gerekmektedir. Bu sebeple gelecek bölümlerde yapılacak örnek
sorgulamalarda ORM tanımlamalarının ardından sorgulamaların yapılması
önemlidir.

## Bölüm Özeti

Bilgisayar programcısı olarak veri, yazılım geliştirme sürecimizin en
önemli bileşenlerinden biri olacaktır. Programlamanın herhangi bir
aşamasında veri saklama, sorgulama ya da veri üzerinde işlem yapma
ihtiyacı duyabiliriz. Veri yönetimiyle ilgili bilinen en iyi yöntem,
bir veri tabanından faydalanmaktır. Daha küçük ölçekli projeler için
geleneksel dosyaya kaydetme yöntemleri, CSV türü dosyalarla veri
işlenmesi mümkün olsa da orta ve büyük ölçekli projeler genellikle bir
veri tabanı ile güçlendirilirler.
>
Bu ders kapsamında bir veri tabanını nasıl yöneteceğimizi öğreniyoruz.
Veri tabanı yönetimi için sıklıkla kullanılan 3 yaklaşımı ele
alacağız. Ayrıca ders boyunca bu 3 yaklaşımı kullanarak veri tabanı
yönetimi sağlayacağız.
>
Bunlardan birincisi SQL (Structured Query Language) kullanmaktır. Codd
tarafından ilişkisel veri tabanı önerisinde bulunmanın
motivasyonlarından biri üst seviye bir dil önerisinde bulunmaktı. SQL,
ilişkisel veri tabanlarının ortaya çıkmasından birkaç sene sonra
önerildi, bazı iyileştirmeler yapıldı ve bugün halini alarak yıllardır
kullanımımızda. Çeşitli firmalar özelleştirilmiş bazı SQL türevleri
üretmiş olsa da klasik SQL yapısı neredeyse tüm veri tabanı yönetim
sistemleri (VTYS) tarafından kullanılabilmektedir. Anlatacağımız tüm
yaklaşımlar, temelde SQL kullanarak veri tabanı üzerinde işlem
gerçekleştirmektedir.
>
Veri tabanına doğrudan bir yazılım kullanarak bağlanabiliriz. Birçok
veri tabanı yönetim aracı mevcuttur. Biz, dersimiz kapsamında hem
ücretsiz hem kolay hem de birçok VTYS ile kullanılabilir olması
sebebiyle DBeaver kullanacağız. Bu yazılım sayesinde neredeyse tüm
VTYS'lere bağlanabiliriz. Ders kapsamında VTYS olarak, yine basit
kullanımı ve bir sunucu kurulumu gerektirmemesi sebebiyle SQLite
kullanacağız. DBeaver, SQLite bağlantısı konusunda oldukça
başarılıdır. Hatta yeni bir SQLite veri tabanı oluşturma işlemini
DBeaver kullanarak gerçekleştirebiliyoruz. Ayrıntılar için lütfen
bölümün tamamını okuyunuz ve uygulayınız.
>
İkinci yaklaşım bir programlama dili kullanmaktır. Bir bilgisayar
programcısı olarak veri tabanına hazırladığımız yazılım içerisinden
bağlanmak isteyeceğiz. Bazı sorgulama, raporlama, kontrol ve özel
durumlarda DBeaver tarzı yazılımlarla veri tabanına erişmek
isteyebiliriz ancak asıl ihtiyacımız, hazırladığımız yazılımın bazı
tetikleyici durumlarda veri tabanında otomatik güncellemeler
gerçekleştirmesidir. Örneğin bir telefon rehberi uygulamasında yeni
kayıt formu doldurulduğunda yazılım uygun SQL kodunu yazarak veri
tabanına giriş yapabilmelidir. Bu yöntemi uygulamak için yaygın olarak
kullanılan ve öğrenmesi kolay olan Python dilini kullanacağız.
>
Üçüncü ve son yaklaşımımız ise ORM yöntemini kullanmaktır. Bu yöntem
nesne yönelimli programlama esnasında her bir sınıfın bir veri tabanı
tablosuyla eşlenik olarak çalışması üzerine kuruludur. Bir dil
üzerinde ilgili sınıflar oluşturulur, ORM kütüphanesi sınıfların
karşılığında veri tabanı oluşturulmasını sağlar.
>
Kodlama içerisinde sınıf üzerinde yapılacak bir işlem, aynı anda veri
tabanında da güncelleme yapılmasını sağlar. Böylece programcı yalnızca
kodlama aşamasına odaklanabilir. Kodlama esnasında ayrıca yapılan
işlemlerin veri tabanını güncellemesi için hazırlanması gereken SQL
komutlarının ayrıca düşünülmesine gerek kalmaz.
>
Bölüm içerisinde Python dili için geliştirilen SQLAlchemy ORM
kütüphanesinden faydalanacağız.
>
Bölüm içerisinde tüm bu yöntemlerin kurulumları ve örnek uygulamaları
ele alınmıştır. Lütfen tüm bölümü inceleyerek uygulamaları kendi
bilgisayarınızda gerçekleştiriniz.

### Kaynakça

Akadal, E. 2020. Veritabanı Tasarlama Atölyesi. Türkmen Kitabevi,
İstanbul.
>
Anaconda Documentation. Anaconda.com. Erişim: 25.12.2022,
[<u>htt</u>p<u>s://docs.anaconda.com/</u>](https://docs.anaconda.com/)
Beaulieu, A. 2020. Learning SQL: Generate, manipulate, and retrieve
data (3rd ed.). O'Reilly Media.
>
DBeaver documentation. 16 Eylül 2020. DBeaver. Erişim: 25.12.2022,
[<u>htt</u>p<u>s://dbeaver.com/docs/wiki/</u>](https://dbeaver.com/docs/wiki/)
>
MySQL, Employees Sample Database. Mysql.com. Erişim: 25.12.2022,
[<u>htt</u>p<u>s://dev.mysql.com/doc/employee/en/</u>](https://dev.mysql.com/doc/employee/en/)
>
SQLAlchemy Documentation — SQLAlchemy 1.4 documentation.
Sqlalchemy.org. Erişim: 25.12.2022,
[<u>htt</u>p<u>s://docs.sqlalchemy.org/en/14/</u>](https://docs.sqlalchemy.org/en/14/)
>
\[1\] URL:
[<u>htt</u>p<u>s://dev.mysql.com/doc/employee/en/sakila-structure.html</u>](https://dev.mysql.com/doc/employee/en/sakila-structure.html)
>