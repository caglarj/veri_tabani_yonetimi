# Eğitim Programı İçerik Hazırlık


* Notları


---

# Dersler
* 01 - Herkes İçin Temel Dersler
* 02 - Visual Studio Code Kullanımı
* 03 - GIT
* 04 - Veri Yapılar ve Algoritmalar
* 05 - SQL 
* 06 - GOLAND
* 07 - REST API
* 08 - Microservices

**Notlar :**  *İlk dört konuya burada yer verilmemiştir.* 

---

## 05  - SQL 
### Giriş

    Bu bölümde konu başlıkları, temel kaynakları ve çalışma yönteminden bahsedeceğiz.

----
**SQL Tanımını Yapacağız, SQL Tanımıyla Birlikte;** 

* Veri, veri tabanı ve veri tabanı yönetimi sistemleri,
* Veritabanı yönetim sistemi olan POSTGRESQL kurulumu ve kullanımı,
* SQL Temelleri - I- II. içerisinde;    *
* PSQL ana "Terminal ara yüzü", "Karşılaştırma ve Mantıksal operatörleri", "SQL anahtar kelimeleri" ve "aggregate fonksiyonları"ndan bahsedeceğiz. 
---
SQL anahtar kelimeleri:
``` 
SELECT - COUNT - WHERE - BETWEEN - IN - LIKE - ILIKE -
DISTINCT- ORDER BY - LIMIT - OFFSET - GROUP BY - HAVING - ALIAS. 
```
---

**Tablolarla Çalışma :**

- Temel tablo yapısı, 
- Tabloların oluşturulması, biribiriyle ilişkilendirilmesi, 
- Primary / Foreing Key kavramları, 
- Kısıtlama kavramı üzerine örnek ve Temel veri tipleri konuları işlenmiştir. 

---

**JOIN (Birleştirme İşlemleri) :**

- Birden fazla tablo üzerinde sıklıkla kullanılan JOIN işlemleri,
- Temel JOIN işlerimeri **INNER, LEFT, RIGHT ve FULL JOIN** komutları, 
- SQL sorgularını birleştirmede kullanılan **UNION ve EXPECT** operatorleri işlenmiştir.
- Sub Queries (Alt sorgular) : SQL'de fazlaca kullanılan Matematik ve String fonksiyonları ele alınmıştır.

---


**TEMEL KAYNAKLAR**

[PostgreSQL Resmi Dökümantasyon](https://www.postgresql.org/download/)\
[PostgreSQL Tutorial](https://www.w3schools.com/sql/)\
[W3Schools SQL](https://www.tutorialspoint.com/postgresql/index.htm)\
[Tutorials Point](https://www.tutorialspoint.com/postgresql/index.htm)


---
##  Veri, Veritabanı ve SQL Nedir ? 

### Veri :  

Ölçüm, sayım, deney, gözlem veya araştırma sonucuyla elde edilen ham 
bilgilerdir.

### Veritabanı tanımı ve SQL :

Veritabanı genellikle bir bilgisayar sisteminde elektronik olarak 
depolanan yapılandırılmış bilgi veya veriden oluşan düzenli bir 
koleksiyondur. Veritabanı genellikle bir veritabanı yönetim sistemi 
(DBMS) ile kontrol edilir. Veri ve DBMS ve aynı zamanda bunlarla 
ilişkili uygulama yazılımları bir araya getirildiğinde sıklıkla 
yalnızca veritabanı olarak kısaltılan veritabanı sistemi olarak 
ifade edilir. 

![DBMS](https://i.hizliresim.com/f83k1s9.jpg)


Günümüzde operasyonda kullanılan en yaygın veritabanı türlerindeki 
veri genellikle işlemeyi ve veri sorgulamayı verimli hale getirmek 
üzere bir dizi tablodaki satırlarda ve sütunlarda modellenir. 
Böylece veri kolayca erişilebilir, yönetilebilir, değiştirilebilir, 
güncellenebilir, kontrol edilebilir ve organize edilebilir hale 
getirilir. Çoğu veritabanında veri yazma ve sorgulama için 
yapılandırılmış sorgu dili (SQL) kullanılır.

- Yapılandırılmış Sorgu Dili (SQL) nedir?
  
SQL verileri sorgulamak, değiştirmek ve tanımlamak ve aynı zamanda 
erişim kontrolü sağlamak üzere neredeyse tüm ilişkisel 
veritabanlarında kullanılan bir programlama dilidir. SQL ilk olarak 
1970'li yıllarda Oracle'ın büyük katkıları ile IBM'de geliştirilmiş 
ve daha sonra SQL ANSI standardı uygulanmış ve SQL IBM, Oracle ve 
Microsoft gibi şirketlerden pek çok uzantının temelini atmıştır. SQL 
günümüzde oldukça yaygın bir şekilde kullanılsa da yeni programlama 
dilleri geliştirilmeye başlandı. 

### Veritabanının evrimi

Veritabanları, 1960'lı yılların başlarında ortaya çıkmalarından bu 
yana radikal bir evrim sürecinden geçmiştir. Hiyerarşik veritabanı 
gibi navigasyonel veritabanları (ağaç benzeri bir modeli temel alır 
ve yalnızca bir kaynaktan çoklu alıcıya doğru ilişkiye olanak 
sağlar) ve ağ veritabanı (çoklu ilişkilere olanak sağlayan daha 
esnek bir model), verileri depolamak ve değiştirmek üzere kullanılan 
orijinal sistemlerdi. Bu ilk sistemler kolay olsa da esnekti. 
1980'li yıllarda ilişkisel veritabanları popüler oldu ve ardından 
1990'lı yıllarda nesne odaklı veritabanları ortaya çıktı. Daha yakın 
bir zamanda ise, internetin büyümesine ve yapılandırılmamış 
verilerin daha hızlı bir şekilde işlenmesine duyulan ihtiyaca yanıt 
olarak NoSQL veritabanları kullanılmaya başlandı. Günümüzde ise 
bulut veritabanları ve kendi kendini yöneten veritabanları veri 
toplama, depolama, yönetme ve kullanma konusunda çığır açıyor.

### Bir veritabanı ve elektronik tablo arasındaki fark nedir?

Hem veritabanları hem elektronik tablolar (ör. Microsoft Excel) 
bilgi depolamak için uygun yöntemlerdir. Aralarındaki temel farklar 
şu şekilde sıralanabilir

- Veri toplama ve değiştirme yöntemi
- Verilere erişebilen kişiler
- Depolanabilecek veri miktarı

Elektronik tablolar orijinal olarak tek kullanıcı için tasarlanmış 
olup özellikleri bu amacı yansıtmaktadır. Muazzam düzeyde karmaşık 
veri manipülasyonuna ihtiyaç duymayan tek veya az sayıda kullanıcı 
için harika bir seçenektir. Diğer yandan veritabanları ise çok daha 
yüksek miktarda, kimi zaman devasa miktarlarda bilgi 
koleksiyonlarını barındırmak üzere tasarlanmıştır. Veritabanları, 
oldukça karmaşık bir mantık ve dil kullanımıyla aynı anda birden 
fazla kullanıcının hızlı ve güvenli bir şekilde verilere erişmesine 
ve veri sorgulamasına olanak sağlar. 

### Veritabanı türleri

Çok sayıda farklı veritabanı türü bulunur. Belirli bir kurum için en 
iyi veritabanı, söz konusu kurumun verileri nasıl kullanmayı 
amaçladığına bağlı olarak değişiklik gösterir. 

### İlişkisel veritabanları

İlişkisel veritabanları 1980'li yılların sonlarında piyasada 
hakimiyet kazandı. İlişkisel veritabanındaki öğeler, sütunlar ve 
satırlardan oluşan bir tablo kümesi şeklinde organize edilir. 
İlişkisel veritabanı teknolojisi, yapılandırılmış bilgilere en 
verimli ve esnek şekilde erişme olanağını sağlar.

### Nesne odaklı veritabanları.

Nesne odaklı bir veritabanındaki bilgiler, tıpkı nesne odaklı 
programlamada olduğu gibi nesneler biçiminde temsil edilir.

### Dağıtılmış veritabanları

Dağıtılmış veritabanı, farklı yerlerde bulunan iki veya daha fazla 
dosyadan oluşur. Veritabanı, farklı ağlara yayılan ya da aynı 
fiziksel konumda yer alan birden fazla bilgisayarda depolanabilir.

### Veri ambarları

Merkezi bir veri havuzu olan veri ambarı, özel olarak hızlı 
sorgulama ve analiz amaçlarıyla tasarlanmış bir veritabanı türüdür.

### NoSQL veritabanları
Bir NoSQL veya ilişkisel olmayan veritabanı, yapılandırılmamış ve 
yarı yapılandırılmış verilerin depolanmasına ve değiştirilmesine 
olanak tanır (veritabanına girilen tüm verilerin nasıl 
düzenleneceğini tanımlayan ilişkisel veritabanının aksine). NoSQL 
veritabanları, web uygulama yazılımlarının daha yaygın ve daha 
karmaşık hâle gelmesi ile birlikte popülerlik kazandı.

### Grafik veritabanları
Grafik veritabanı, verileri birimler ve birimler arasındaki 
ilişkiler açısından depolar.

### OLTP veritabanları. 

OLTP veritabanı, birden fazla kullanıcı tarafından çok sayıda 
işlemin gerçekleştirilmesi için tasarlanmış hızlı ve analitik bir 
veritabanıdır.
Günümüzde onlarca veritabanı türü kullanılmaktadır. Daha az yaygın 
olan diğer veritabanları bilimsel, finansal ya da diğer işlevlere 
özel olarak tasarlanmıştır. Farklı veritabanı türlerine ek olarak, 
bulut ve otomasyon gibi radikal ilerlemeler ve teknoloji geliştirme 
yaklaşımlarındaki değişiklikler veritabanlarının rotasını yepyeni 
yerlere çeviriyor. En yeni veritabanlarından bazıları şu şekilde 
sıralanabilir:

### Açık kaynaklı veritabanları
Açık kaynaklı veritabanı sistemi, kaynak kodu açık olan bir 
sistemdir. Bu tür veritabanları SQL veya NoSQL veritabanları 
olabilir.

### Bulut veritabanları
Bir bulut veritabanı özel, genel veya hibrit bulut bilişim 
platformunda bulunan yapılandırılmış veya yapılandırılmamış bir veri 
koleksiyonudur. İki tür bulut veritabanı modeli bulunur: geleneksel 
ve servis olarak veritabanı (DBaaS). DBaaS sayesinde yönetim 
görevleri ve bakım işlemleri servis sağlayıcı tarafından 
gerçekleştirilir.

### Çoklu model veritabanı
Çoklu model veritabanları, farklı veritabanı türlerini tek bir 
entegre arka uçta buluşturur. Buna göre çeşitli veri türlerini 
içerebilirler.

### Belge/JSON veritabanı
Belge odaklı bilgilerin depolanması, alınması ve yönetilmesi için 
tasarlanan belge veritabanları, verileri satırlar ve sütunlar yerine 
JSON biçiminde depolamak için modern bir yöntem sunar.

### Kendi kendini yöneten veritabanları
En yeni ve en ezber bozan veritabanı türü, kendi kendini yöneten 
veritabanları (aynı zamanda otonom veritabanları olarak bilinir), 
geleneksel olarak veritabanı yöneticileri tarafından 
gerçekleştirilen ince ayar, güvenlik, yedekleme, güncelleme ve diğer 
rutin yönetim görevlerini otomatikleştirmek üzere makine 
öğreniminden yararlanan bulut tabanlı çözümlerdir.

## Veritabanı yazılımı nedir?
Veritabanı yazılımı dosya ve kayıt oluşturmayı, veri girişini, veri 
düzenlemeyi, güncellemeyi ve raporlamayı kolay hale getirerek 
veritabanı dosyalarını ve kayıtları oluşturmak, düzenlemek ve 
muhafaza etmek için kullanılır. Yazılım veri depolama, yedekleme ve 
raporlama, çok erişimli denetleme ve güvenlik de sağlar. Hırsızlık 
olayları artığından, güçlü veritabanı güvenliği günümüzde özellikle 
önem kazanmıştır. Veritabanı yazılımı bazen "veritabanı yönetim 
sistemi" (DBMS) olarak da adlandırılmaktadır.
Veritabanı yazılımı veri yönetimini daha kolay hale getirir ve 
kullanıcıların yapılandırılmış bir forma veri depolamalarına ve 
sonra buna erişmelerine olanak tanır. Genellikle veri oluşturmaya ve 
yönetmeye yardımcı olan bir grafiksel arayüzdür ve bazı durumlarda 
kullanıcılar veritabanı yazılımı kullanarak kendi veritabanlarını 
oluşturabilir.

## Veritabanı yönetim sistemi (DBMS) nedir?
Veritabanları tipik olarak veritabanı yönetim sistemi (DBMS) olarak 
bilinen kapsamlı bir veritabanı yazılım programını gerektirir. DBMS, 
veritabanı ve son kullanıcıları ya da programlar arasında bir arayüz 
işlevi görerek kullanıcıların bilgilerin nasıl organize ve optimize 
edildiğini yönetmesine, bilgileri almasına ve güncellemesine olanak 
sağlar. DBMS aynı zamanda veritabanlarına ilişkin gözetim ve kontrol 
faaliyetlerini kolaylaştırarak performans izleme, ince ayar ve 
yedekleme ve kurtarma gibi çeşitli yönetim operasyonlarının 
gerçekleştirilebilmesini sağlar.
Popüler veritabanı yazılımlarına ya da DBMS'lere MySQL, Microsoft 
Access, Microsoft SQL Server, FileMaker Pro, Oracle Database ve 
dBASE örnek olarak gösterilebilir.[kaynak 3](https://www.oracle.com/tr/database/what-is-database/)


Özetleyecek olursak;

Verilerin organize bir şekilde depolanmasını sağlayan sistemlerdir.

Düzenli verilere sahip olursak;

- İleriye yönelik geliştirici kararlar verebiliriz.
- Hatalarımızı daha kolay çözeriz.
- Geleceğe yönelik başarılı tahminlerde bulunabiliriz.

Neden Veritabanına ihtiyaç duyarız ? 

- Veritabanı sayesinde sütunlarda bulunacak verilerin aynı veri tipinde olmasını garanti ederiz.
- Veritabanları sayesinde çok büyük boyutlu veri kümeleriyle daha kolay çalışırız.
- Çoklu kullanıcı yönetimi için veri tabanları daha uygundur.
- Veritabanları başka yazılım ve uygulamalarla daha kolay çalışır.

## PostgreSQL Kurulumu :
Çalışmalarımız boyunca veritabanı yönetim sistemi olarak PostgreSQL kullanacağız. PostgreSQL açık kaynak kodlu ve popüler bir ilişkisel veritabanı yönetim sistemidir.

**Neden PostgreSQL?**

- Açık kaynak kodlu
- Çeşitli veri tipi desteği
- Güçlü dökümantasyon ve topluluk desteği
- Tüm işletim sistemlerine uygunluk
- ACID uyumluluk
- Güvenlidir
- Büyük verilerle kolay çalışma

**PostgreSQL**

[İndirme Linki](https://www.postgresql.org/download/)

Sisteminize uygun olan versionu seçiyoruz. Bu ders içeriğinde win. 64 için PostgreSQL V.13 kullanılmıştır. 
Kurulum aşamaları klasik win programlarının kurulum aşamalarıdır. 
Components seçimlerinde her 4 seçeneği işaretliyoruz.
Data Directorler mevcut hali ile kalabilir. 
bir sonraki alaşamada Password (superuser) belirliyoruz.
PATH işlemlerini gerçekleştiriyoruz. 

[Daha detaylı bilgi için tıklaynız](https://www.guru99.com/download-install-postgresql.html)


[Dvdrental Örnek Veritabanı](
https://www.postgresqltutorial.com/wp-content/uploads/2019/05/dvdrental.zip)











