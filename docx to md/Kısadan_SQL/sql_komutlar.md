## CRUD YAPISI

CRUD, Create (Oluşturma), Read (Okuma), Update (Güncelleme) ve Delete (Silme) kelimelerinin baş harflerinden oluşan bir kısaltmadır ve geleneksel veritabanı sistemlerinde gerçekleştirilebilen dört temel işlemi temsil eder. SQL’de, bir tabloya yeni kayıtlar eklemek için INSERT ifadesi kullanılır.

Veri tabanı süreçleri içeren bir yazılımda neredeyse her zaman bu 4 işlem gerçekleştirilir. 

ilk kavram olan Create kullanımı : 

Örneğin, Müşteriler adında `müşteri_id, müşteri_kodu, iletişim_adı ve aktif` sütunları olan bir tablomuz olduğunu varsayalım. Bu tabloya tüm sütunlar için değerlerle yeni bir satır eklemek için aşağıdaki sözdizimini kullanabiliriz:

`INSERT INTO Müşteriler (müşteri_id, müşteri_kodu, iletişim_adı, aktif)

VALUES (değer1, değer2, değer3, değer4);
`

Burada değer1, değer2, değer3 ve değer4, ilgili sütunlara eklemek istediğiniz değerlerdir.

Örnekler : 


```sql
INSERT INTO Calisan (id, adi, soyadi, cinsiyeti, iseGirisTarihi)
VALUES (1, 'Ahmet', 'Yilmaz', 'Erkek', '2022-01-01'),
	   (2, 'Mehmet', 'Öztürk', 'Erkek', '2022-02-12'),
	   (3, 'Ayşe', 'Yilmaz', 'Kadın', '2022-03-01'),
	   (4, 'Ahu', 'Geldik', 'Kadın', '2022-04-04'),
	   (5, 'Dursun', 'Kalgeldi', 'Erkek', '2022-04-10'),
	   (6, 'Çiçek', 'Tutuldu', 'Kadın', '2022-05-11'),
	   (7, 'Mustafa', 'Çetin', 'Erkek', '2022-04-12'),
	   (8, 'Hatice', 'Kuş', 'Kadın', '2022-06-01'),
	   (9, 'Aşşe', 'Sen', 'Kadın', '2022-07-04'),
	   (10, 'Hamit', 'Minnoş', 'Erkek', '2022-08-10');


```

```sql
INSERT INTO Bolum (id,adi)
VALUES (1,'Bilim'),
       (2,'Fizik'),
       (3,'Kimya'),


```

Şimdi 20 kayıt daha ekleyeceğiz ama bunu bu sefer Python Kullanarak Yapıyoruz : 


```python
#SQLite için gerekli olan paketi çağırıyoruz.
import sqlite3
#veri tabanına bağlanalım ve bağlantıyı bir değişkene yükleyelim (conn)
conn = sqlite3.connect('myfirst')

#Şimdi SQL Kodunu çalıştırılım.
# veri tabanı ile iletişim kuracak bir Cursor elemanı oluşturalım:
cursor = conn.cursor()

#SQL komutumuzu cursor kullanarak çalıştıralım :

cursor.execute("""
INSERT INFO BolumCalisan(id, calisan_id, bolum_id, baslangicTarihi, bitisTarihi) VALUES
(1,1,1, '2022-01-01', '2022-06-30'),
(2,2,1, '2022-02-01', '2022-06-30'),
(3,3,1, '2022-03-01', '2022-09-30'),
(4,4,1, '2022-04-01', '2022-12-30'),
(5,5,1, '2022-05-01', '2022-12-30'),
(6,6,1, '2022-06-01', '2022-12-30'),
(7,7,7, '2022-07-01', '2022-12-30'),
(8,8,7, '2022-08-01', '2022-12-30'),
(9,9,1, '2022-09-01', '2022-12-30'),
(10,10,1, '2022-10-01', '2022-12-12'),
(11,1,1, '2022-11-01', '2022-12-28'),
(12,4,3, '2022-12-01', '2022-09-25'),
(13,2,4, '2022-01-01', '2023-08-30'),
(14,4,3, '2022-02-01', '2022-12-30'),
(15,5,2, '2022-03-01', '2022-12-03'),
(16,16,1, '2022-04-01', '2022-12-30'),
(17,3,7, '2022-05-01', '2022-12-30'),
(18,8,1, '2022-06-01', '2023-12-30'),
(19,9,1, '2022-07-01', '2023-12-30'),
(20,7,1, '2022-08-01', '2023-12-30');
""")
#Veri tabanında yer alan tabloları listeleyen SQL kodunu çalıştıralım
cursor.execute("SELECT * FROM BolumCalisan")

#SQL sonucunda oluşan yanıtı alalım ve tables değiştenine atayalım
tables = cursor.fetchall()
print(tables)

#Yapilan değişiklikleri veri tabanına kaydedelim:
conn.commit()
#Veritabanı tabanı bağlantısını kapatalım
conn.close()


```

Yukarıdaki kod bloğu, yeni bir SQL kodunun çalıştırılması, bunun yanıtını almayı ve veri tabanı bağlantısını kapatmayı içeriyor.


```python

# Maas Bolumu İçinde bir Giriş Yapalım
# Veri tabani ile saglayacak bir Cursor elemani olusturalim:
cursormaas = conn.cursormaas()

# SQL komutumuzu Cursor kullanarak calistiralzm:
cursormaas.execute("""INSERT INTO Maas(id, calisan_id, unvan, baslangicTarihi, bitisTarihi) VALUES
(1, 1, 'Yönetici', '2022-01-01', '2022-12-31'),
(3, 5,'Muhasebe Müdüru*, '2022-01-01', '2022-12-31'),
(2, 2,'Yönetim Kurulu', '2022-01-01', '2022-12-31'),
(6, 6,'Satis Muduru', '2022-01-01', '2022-12-31'),
(7, 7,'Müsteri Tensilcis', '2022-01-01', '2022-12-31'),
(8, 8,'Müduru', '2022-01-01', '2022-12-31'),
(9, 9,'Insan Kaynaklar1 Müduru', '2022-01-01', '2022-12-31'),
(11, 11,'Yazilim Gelistirici', '2022-01-01', '2022-12-31'),
(12, 12,'Kameraman', '2022-01-01', '2022-12-31'),
(13, 13,'Starrrr', '2022-01-01', '2022-12-31'),
(14, 14,'Tellak', '2022-01-01', '2022-12-31'),
(15, 15,'Yalama', '2022-01-01', '2022-12-31');
""")

# Veri tabanında yer alan tabloları listeleyen SQL kodunu çalıştıralım
cursormaas.execute("SELECT * FROM Maas")

tables = cursormaas.fetchall()

print(tables)

conn.commit()

conn.close()






```