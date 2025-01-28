# Ankara Çankaya İlçesi Hedonik Konut Fiyat Modeli

## Giriş

Hedonik fiyat modeli heterojen malların sahip olduğu karakteristiklerin her birinin tüketiciye farklı bir fayda veya tatmin düzeyi sağladığını gösteren ve Lancaster’ın Tüketici Teorisini temel alan bir modeldir. İlk olarak 1939’da Amerikan otomobil endüstri uzmanı Andrew T. Court oluşturduğu modelde otomobil endüstrisine ilişkin bir fiyat endeksi oluşturma gayesi ile otomobilin fiyatını, otomobilin çeşitli özelliklerinin bir fonksiyonu olarak incelemiş ve böylece heterojen malların hedonik fiyatlarını analiz etmiştir (Goodman, 1998: 292). Sonrasında Hedonik fiyat modeli diğer tüketim mallarına uygulanarak genişletilmiştir.

Hedonik fiyat modeli Lancaster (1966)’ın tüketici tercih teorisine dayanmaktadır. Hedonik fiyat modeli ile öncelikle bir malın sahip olduğu özellikleri ile ilgili malın fiyatı arasında ilişki kurulmakta daha sonra, ilave her bir özelliğin malın fiyatı üzerindeki etkisi ayrıştırılarak ilave özellikler ile malların farklılaştırılması sağlanmaktadır (Özkan ve Yalpır, 2005). Bir başka ifade ile hedonik fiyat modeli, belirli bir malın fiyatını, malın sahip olduğu özelliklerin değer toplamları olarak değerlendiren ve her bir özelliğin değerini regresyon analizi kullanarak tahmin eden bir yöntem olmaktadır (Shimizu ve diğerleri, 2010).

Hedonik fiyat fonksiyonunda, bağımlı değişken logaritmik formda, bağımsız değişkenlerin ise doğrusal formda yer aldığı hedonik fiyat fonksiyonu kalıbına logaritmik doğrusal (log-lin) veya yarı logaritmik model denilmektedir.

lnF=α + β1X1 + β2X2 + β3X3 + ϵ
 
Bu model ile bağımsız değişkenlerde meydana gelen mutlak değişimlerin, bağımlı değişkende meydana getirdiği yüzde değişimler hesaplanmaktadır. Regresyon katsayılarının yorumlanmasını da kolaylaştıran logaritmik dönüşüm bağımsız
değişkendeki bir birimlik artışa karşılık bağımlı değişkendeki yüzdesel artışı göstermektedir (Day vd., 2003: 20).

Logaritmik doğrusal modelin bu denli tercih edilen bir kalıp olmasının bir diğer nedeni ise modele dummy (kukla) değişkenlerin eklenmesinde herhangi bir sorunla karşılaşılmamasıdır. Bir konut için düşünürsek bazı değişkenlerin ölçülemediği, etkileri sadece var veya yok gibi ifadelerle model dahil edilebildiği bilinmektedir. Bu tür konut özellikleri modele ancak dummy değişkenlerle eklenebilmektedir. Örneğin konutun özelliklerinden biri olarak belirlenebilecek asansör özelliğinin varlığı dummy değişken ile modele eklenmekte, konuta ait asansörün olması durumunda dummy değişken değeri 1, olmaması durumunda 0 olarak analize dahil edilmektedir. Dummy değişkenlerin yer aldığı logaritmik doğrusal model ise;

lnF=α + i∑βiXi + j∑cjDj + ϵ

Dj: Dummy değişkenleri temsil etmektedir.

Birçok çalışma yarı logaritmik fonksiyonel formun diğer doğrusal fonksiyonel formlara göre avantajlarını vurgulamaktadır (Owusu-Ansah, 2013: 22). Yarı logaritmik fonksiyonun en temel avantajı, belirli bir özelliğin değerinin diğer özelliklerin değeri ile orantılı olarak değişmesine izin vermesidir (Sopranzetti, 2015: 2126). Ayrıca logaritmik dönüşüm değişen varyans sorununu daha önemsiz hale getirmektedir (Gujarati, 2015: 105).

Kukla değişkenlerin yorumlanmasında ise tahmin edilen katsayıların ters logaritmaları alınarak bulunan değerlerden 1 çıkarılmalı ve sonuç 100 ile çarpılmalıdır (Gujarati, 2015: 105-106).

## Ön Analiz

Çalışmamızda ham veriler “Hepsi Emlak” internet sitesinden Ankara Çankaya ilçesi için toplanmıştır. Ancak Web Scraping zorluklarından dolayı gözlem ve özellik sayılarımız az sayıdadır. Zaten amacımız akademik bir çalışmadan ziyade öncü ve temel bir çalışmadır. Daha derinlemesine araştırmak adına literatürde bulunan akademik çalışmaları inceleyiniz.

Not: Veri kazıma işlemimiz Python, veri düzenleme ve analiz işlemlerimiz ise Excel ve IBM SPSS 27 ile gerçekleştirilmiştir.

Veri setimiz 108 mahallede 2139 gözlem değeri ile birlikte toplam 13 özellikten oluşmaktadır.

1-Konut Tipi

2-Oda Sayısı

3-Banyo Sayısı

4-Brüt ve Net Metre Kare

5-Yapı Toplam Kat Sayısı

6-Yapının Bulunduğu Kat

7-Yapının Yaşı

8-Isınma Tipi

9-Krediye Uygunluk

10-Eşya Durumu

11-Kullanım Durumu

12-Bulunduğu Mahalle

13-Fiyat

Öncelikle analizin tutarlı olması açısından mahalle bazlı frekansları incelediğimizde gözlem değeri çok düşük veriler bulunmaktadır.

![1](https://github.com/user-attachments/assets/6e42b0b9-d960-4bbb-b930-09bd8102eda8)


![fff](https://github.com/user-attachments/assets/76c62e1c-fc40-48e0-9169-1f14777632aa)

Bu nedenden dolayı 10 gözlem altında kalan mahallelerdeki verileri analizimizin dışında bırakıyoruz. 108 mahalle ve 2139 gözlem sayımız 76 mahalle ve 2001 gözleme inmektedir.

Ayrıca veri setlerinde hatalı veriler göz önüne alındığında her bir değişkenin kendi içerisindeki veri noktaları incelenmelidir. Mesela bizim veri setimizde ise “Oda Sayısı” değişkeninde hatalı giriş olan “41+1 oda” verisi gözlemlenmektedir.


![Resim5](https://github.com/user-attachments/assets/f4cafadf-0039-40a7-915b-bffdcbfe457c)

Bu gözlem değerini de veri setimizden kaldırıyoruz ve sonuç olarak 76 mahallede toplam 2000 gözlem noktası ve 13 özellik kalmaktadır.

Bu süreçten sonra ilk yapmamız gerekenler sayısal ve kategorik değişkenlerimizi ayırıp, kategorik olanları kukla değişken haline getirmek. Ancak bunu yaparken de “Kukla Değişken Tuzağı” problemine düşmememiz gerekir.

Not: Kukla Değişken Tuzağı (https://tr.wikipedia.org/wiki/Kukla_de%C4%9Fi%C5%9Fken_tuza%C4%9F%C4%B1)

## Özelliklerin İncelenmesi

## 1-Konut Tipi

3 temel konut tipimiz vardır. 

![1](https://github.com/user-attachments/assets/5255fbe4-c0de-408e-b4d8-b99c819f1e1a)

Kukla değişkenlerimiz 3 adet ancak tuzağa düşmemek adına “Daire” özelliğimizi dışlayacağız. Villa ve residence değişkenlerimiz için 2 kukla değişkeni oluşturulacak, var olanlar 1 olmayanlar 0 değeri ile kodlanacak.

Konut_Tipi_Villa (1,0)

Konut_Tipi_Residence (1,0)

Diğer (Daire) durumu (0,0)

## 2-Oda Sayısı

Oda sayısı ister kukla istersek de sayısal değişken olarak kullanılabilir. Bizler bu değişkeni sayısal değişken olarak bırakacağız. Ancak ham verimizde bu değişken “2+1”, “3+1” şeklinde gelmiştir. Burada ister sadece oda sayısını ister oda+salon sayısını istersek de oda ve salon ayrı değişkenler olarak tutulabilir. Biz sadece oda sayısını alacağız. Bu yüzden “2+1” şeklinde olan verimiz “2”, “3+1” olan verimiz “3” şeklinde sayısal değişken olacaktır.


![2](https://github.com/user-attachments/assets/d39f2c15-1a55-4175-82ae-657c12565ea3)

Hem verilerimizden hem de dağılım grafiğinden gördüğümüz üzere ortalama 3,12 oda sayısı bizlere 3 odalı evlerin daha fazla ilanda olduğunu göstermektedir. Ayrıca oda sayısı ekstrem olanlar muhtemelen villa tarzı evlerdir. Bununda aykırı veya hatalı gözlem olmaması adına teyit edilmesi önemlidir.

![3](https://github.com/user-attachments/assets/401f465f-db2a-4969-8d1e-f45f3c815661)

Minimum 8 odası olan tüm evler villa yapı tarzında. Yani hatalı bir gözlem olarak ele alamıyoruz.

## 3-Banyo Sayısı

Banyo sayımızı oda sayısı gibi sayısal bir değişken olarak ele alacağız. Ham veride de sayısal olarak geldiği için üzerinde oynama yapmamıza gerek yok.

![1](https://github.com/user-attachments/assets/bfdc5b0c-04d3-49e8-b411-f14b3e566d7c)

Yine gözlemlere ve dağılım grafiğine baktığımızda ortalama 1,55 olarak görüyoruz. Bu da ilandaki evlerin çoğunlukla 1 veya 2 banyolu olduğunu gösteriyor. Yine ekstrem banyo sayıları gözükmekte ve bunlarında incelenmesi gerekmektedir.

![1](https://github.com/user-attachments/assets/ef7db4e1-f732-4510-8d80-495f8a963100)

![2](https://github.com/user-attachments/assets/598430e1-64e4-410a-a7f6-5c0143c72797)

Minimum banyo sayısı 4 olarak baktığımızda rezidans grubunun tamamı 0 yani hiçbiri rezidansa ait değil. Villaya baktığımızda ise yine 0 değerleri görüyoruz. Bu da bize bazı yüksek sayıda banyo sayısının ne rezidans da ne de villa da olduğunu gösteriyor. Yani dairelerde mevcut. Bu durum ise hatalı veriler veya başka durumlar olduğunu gösterir.


--İlk olarak 11 banyosu olan 3 odalı bir daire. Muhtemelen 1 yerine 11 değeri girilmiş ve hata olarak gözüküyor. Onu "1" değeri ile veri setimizde değiştirdik.

--Yine hem rezidansı hem de villa kukla değişkenlerimizi “0” ile filtre uygulayarak minimum 4 banyosu olan daireleri tespit ettik. 

![3](https://github.com/user-attachments/assets/f5135576-6279-4b3c-9989-38d1dd10e068)

Özellikle m2 durumuna baktığımızda 84m2 lik bir dairede 6 banyo olmaz. Bu büyük ihtimal hatadır ve bunu 1 olarak değiştiriyoruz. Yine 300 m2 ye kadar olan dairelere 2 daha yüksek olanlara 3 değerini vereceğiz. Bu veri kaybı için verimizi silmek yerine genel ortalamaya uygun değer vermemiz anlamına gelir.

## 4-Brüt ve Net Metrekare

Ham verilerimizi yukarıdaki Excel üzerinden gördüğümüz gibi brüt ve net karışık gelmiştir. Öncelikle bunları ayırıp sayısal değerlere çevireceğiz. Burada ister brüt ve net olarak 2 ayrı değişken kullanabiliriz, istersek de birini tercih edebiliriz. Biz ikisini ayrı değişkenler olarak alacağız.

![1](https://github.com/user-attachments/assets/02e57279-4fd9-4681-8942-210102ded09a)

![2](https://github.com/user-attachments/assets/ce8dbf58-64b2-4ab1-9c41-a444765ae06b)

Ortalamalara baktığımız da brüt 155,75 m2 iken net ortalama 139,19 m2 dir.

Uç değerler histogramımızda gözükmektedir. Bu değerlerin daireden ziyade villa olmasını bekleriz. Bunu kontrol etmemiz gerekir.

Öncelikle m2 si sıfıra yakın gözlemlerimiz var. Bunları kontrol edelim.

![1](https://github.com/user-attachments/assets/1561c2da-6d01-4282-bd3f-e5b02a480dc3)

Dikkat ederseniz 3 adet villa verimiz var ve brüt m2 2,1,1 şeklinde ve netlere uygun değil. Bu yüzden bunlar da birer hatadır ve yine silmek yerine net üzerine brüte ortalama bir değer eklememiz gerekir. Bunun için villaların diğer gözlemleri incelenerek brüt-net farkının ortalaması kullanılabilir. O da yaklaşık 70 m2 civarında. Biz düz olması açısından bu 3 gözlem değerini düzeltmek adına net m2 lere 100 m2 daha ekleme yapıp brüt m2 leri düzelteceğiz.

Aynı şekilde net m2 de de düşük gözlemler var. Bunu incelediğimizde ise 1 gözlem değeri tespit ediyoruz.

![2](https://github.com/user-attachments/assets/9a89be46-c2ac-4299-abcb-20c499c9691b)

Bu gözlem değerinde de 130 m2 brüte karşılık 12 m2 net yazıyor ama bu büyük ihtimal yine bir hata ve 120 yerine 12 yazılmış. Biz de bunu 120 olarak düzeltiyoruz.

Yüksek gözlemleri incelediğimizde ise bunların villa olduğunu görüyoruz. Yani beklenilen bir durum olmasından dolayı bir hata gözükmemektedir.

![1](https://github.com/user-attachments/assets/c11ea513-4f2e-498c-ba38-36c48a6b6f90)

## 5-Yapı Toplam Kat Sayısı

Bu verimiz de yapının kaç kattan oluştuğu bilgisini verir. Ham verimiz sayısal değildir ancak biz sayısal olarak değerlendireceğiz ve buna göre düzenleme yapacağız.

![2](https://github.com/user-attachments/assets/71171a58-0689-4b7b-a070-a2a464637fa9)

Verilerimizde toplam kat sayısı ortalama 5,31 standart sapma 5,56 olup bu da yoğunlukla 5-10 katlı yapıların daha çok ilanda olduğunu gösteriyor.

## 6-Yapının Bulunduğu Kat

![1](https://github.com/user-attachments/assets/39ca313d-3ba7-489f-bd26-0544270821b7)

Yapının bulunduğu kat verilerine baktığımızda oldukça karışık veriler karşımıza çıkmaktadır. Normal sayısal katların dışında kot katları, teras katlar, yüksek giriş vs gibi veriler karşımıza çıkmaktadır. Öncelikle bu verileri düzenlememiz ve buna göre kukla değişkenler üretmemiz gerekmektedir.

İlk olarak sayısal veri barındıran (örneğin 3.kat) gibi verilerin hepsine “Ara Kat” adını vereceğiz. Kot verisi olanların tamamına “Kot” adını vereceğiz. Yani kaçıncı kotta olduğunun önemini göz ardı edeceğiz. Bahçe katı, zemin kat, giriş kat gibi verilere “Zemin” adını vereceğiz. Çatı katı ve terasa ise “Teras” adını vereceğiz. Bu ayırımı kendinize göre değiştirebilirsiniz. Kırılımın hangi noktadan kaynaklanacağını bilemeyiz. 

![2](https://github.com/user-attachments/assets/990aa088-ecfc-4990-bfbe-4a2c27601930)

Güncel olarak bu şekilde düzenlemiş olduk.

Bu değişkenimizde ise 3 kukla değişkeni uygulayacağız. Ara kat değişkenini almayıp Kot, Teras ve Zemin üzerinden kukla değişkenler üretmemiz gerekir.

Bulunduğu_Kat_Kot (1,0)

Bulunduğu_Kat_Zemin (1,0)

Bulunduğu_Kat_Teras (1,0)

Diğer (Ara kat) durumu (0,0,0)

## 7-Yapının Yaşı

Veri setimizde bu sayısal olarak gelmemiştir ve biz de bu değişkeni sayılsa hale çevirip kullanacağız.

![3](https://github.com/user-attachments/assets/c12c1fa9-62f4-4722-8015-3ede55342349)


Değişkenimizi incelediğimizde ağırlıklı olarak sıfır yapıların olduğunu görüyoruz. Ortalama 17,72 bina yaşımız var ancak standart sapmamız biraz yüksek. Yani bina yaşı dağılımı geniş aralıkta değişebilmektedir. 

Uç değerlere baktığımızda ekstrem bina yaşı olanlar var gibi. 

![4](https://github.com/user-attachments/assets/09d29ca6-92eb-42e7-a881-61962a726852)

İncelediğimizde bir daire olduğu ve bina yaşının 131 olduğu verisi var. Ancak büyük ihtimal hatalı bir veri. İlanı da kontrol ettiğimde binanın 131 değil ortalama 31 yıllık olduğunu görebildim. Bu yüzden hatalı bir veri girişi olduğu için veriyi “31” olarak düzeltiyoruz.

## 8-Isınma Tipi

Veri setimizde ısınma tipini incelediğimizde sayısal olmayan bir değişken yapısı olduğunu görebiliyoruz.

![1](https://github.com/user-attachments/assets/af1c9620-c5c4-454c-ba5d-c74a83243f8a)

Doğalgaz sobası, Fancoil Ünitesi, Kat Kaloriferi ve Klima sayımız diğer kategorilere göre çok düşüktür. Bu yüzden bunlara “Diğer” adını vereceğiz ve tek kategori olarak alacağız.

![2](https://github.com/user-attachments/assets/2d20751a-3c98-4d9f-af53-f210adaa27c1)

Şimdi bu verilerimiz için kukla değişkenler oluşturacağız.

Isınma_Tipi_Kombi (1,0)

Isınma_Tipi_Merkezi (1,0)

Isınma_Tipi_Payölcer (1,0)

Isınma_Tipi_Yerden (1,0)

Diğer durum (0,0,0,0)

## 9-Krediye Uygunluk

Kategorik bir değişken o yüzden krediye uygunluk değişkenimizi de kukla değişkene çevireceğiz. Eğer hem krediye uygunluğu hem de uygun olmama durumunu incelemek istiyorsak iki durum için iki ayrı kukla değişken üretmemiz gerekir

Krediye_Uygunluk_Uygun (1,0)

Krediye_Uygunluk_UygunDegil (1,0)

## 10-Eşya Durumu

Yapı içerisinde eşya olup olmaması ile ilgili bir veridir. Kategoriktir ve kukla değişken durumuna çevireceğiz. Burada eşyalı olması fiyata artı bir değer katıyor mu ona bakacağız. O yüzden tek bir kukla yeter.

Eşya_Durumu_Eşyalı (1,0)

Diğer durum (0,1)

## 11-Kullanım Durumu

Yapılar satın alınırken son olarak içerisinde 3 durum gerçekleşebilir. Kiracı olabilir, mülk sahibi olabilir veya boş olabilir.

![3](https://github.com/user-attachments/assets/b38e27ea-affe-4efb-9c77-80173bcbe7ee)

Burada da kiracılı ve mülk sahibi olma durumu eksi veya artı yansıması var mı buna bakacağız. Kukla değişkenlere çevirelim.

Kullanım_Durumu_MülkSahibi (1,0)

Kullanım_Durumu_Kiracılı (1,0)

Diğer (Boş) durum (0,0)

## 12-Bulunduğu Mahalle

En başta zaten mahalle ile ilgili küçük bir frekans analizi yapmıştık ve sayısı az olanları silmiştik. Burada yapmamız gereken nokta tüm mahalleri kukla değişken olarak tanımlamak. Var olan mahallede ise 1 değilse 0 değeri ile kodlama yaptık.

## 13-Fiyat

Fiyat verimiz zaten modelimizde kullanacağımız bağımlı değişken. 

![4](https://github.com/user-attachments/assets/7fa323a9-633d-4c51-a129-abadbc081ac4)

Genel olarak baktığımızda 7.899.038 ortalama fiyat, 5.500.000 medyan fiyata sahip bir bölge verisine sahibiz. Ancak özellikle daire dışında villa gibi yapılarımızın yüzünden yüksek de bir standart sağmaya sahibiz. 

![5](https://github.com/user-attachments/assets/61be088e-b21c-4b3d-9935-7ab36a671657)

Görmüş olduğumuz gibi konut tipi 1 olan verilerimizde ortalama fiyat konut tipi 0 olana göre çok yüksek.

## Model

Modelimizi en başta söylediğimiz gibi Log-Lin model olarak kuracağız, o yüzden fiyat bağımlı değişkenimiz girdi olarak log değeri ile girer.

![1](https://github.com/user-attachments/assets/793ab3c4-a8b3-44aa-959c-abfd83025e08)

Modeli yorumlamaya geçmeden önce yüksek VIF (Variance Inflation Factor) (>5) olan değerler bizlere multicollinearity sorunu olduğunu gösterir. Bu yüzden tek tek modelden çıkartıp güvenli sınıra gelene kadar düzenlememiz lazım.

Sırası ile Net M2 ve Isıtma_Tipi_Kombi değişkenlerini çıkarttığımızda tüm VIF değerleri güvenli sınırın içine (<5) girmiştir.

Bunun dışında ise bazı değişkenler istatistiksel olarak anlamlı değildir. Sig > 0,01, 0,05, 0,10

Bizler genel literatüre uyup %5 ile çalışacağız. Bu yüzden 0,05'den büyük olan değişkenleri modelden dışlıyoruz.

Dışlanan değişkenler: "Eşya_Durumu_Eşyalı", "Krediye_Uygunluk_Uygun", "Yukarı_Bahcelievler_Mah", "Bahçelievler_Mah", "Yıldızevler_Mah", "Mebusevler_Mah", "Güzeltepe_Mah", "Güvenevler_Mah", "Üniversiteler_Mah", "Mutlukent_Mah", "Büyükesat_Mah", "Gaziosmanpaşa Mah",
"Barbaros_Mah", "Kazım_Özalp_Mah", "Çukurambar_Mah".

Güncel model bilgileri;

![1](https://github.com/user-attachments/assets/07b3ec50-2d37-456f-8173-7e3ad153028e)

![2](https://github.com/user-attachments/assets/f8aced3c-7c55-4869-8b47-51ef856f3976)


Öncelikle modelimiz %87’lik bir düzeltilmiş R kare değerine sahiptir. Ayrıca F testi sonucuna göre modelimiz anlamlıdır. (Sig<0,05)

![fff](https://github.com/user-attachments/assets/c12a4d9a-cf48-4bf9-95f9-db824573a66e)

Katsayı tablomuzun tamamı güvenli VIF değeri içerisinde ve istatistiksel olarak anlamlıdır.

Özeliiklerimizi incelediğimizde konut tipinin villa veya rezidans olması fiyata pozitif etki etmektedir. Yine aynı şekilde oda sayımız, banyo sayımız, brüt m2 alanımız ve yapının toplam katı birim başına arttığında fiyata pozitif etki etmektedir. Konutun kot, zemin ve teras katında olması fiyata negatif ederken, yine binanın yaşı birim bazlı arttığında fiyata negatif etki etmektedir. Isınma tiplerimiz merkezi, payölçer ve yerden olması fiyata pozitif etki ederken krediye uygun olmaması fiyata negatif etki etmektedir. Ayrıca konutun içersinde mülk sahibi olması fiyata pozitif etki ederken, kiracının bulunması negatif etki etmektedir. Mahalleler genel olarak fiyata negatif etki ederken, konutun Oran Mahallesinde olması pozitif etki etmektedir. Ayrıca fiyatlarımız mahallelere göre standart sapması yüksek olduğu için mahalle bazlı analizler daha derinlemesine incelenmelidir (Örneğin medyan modeller gibi).

Sonuçlarımız literatürle benzerdir. Ayrıca çok daha fazla özellikle de tekrar incelenmelidir. 

Aşağıdaki veriler bazı özelliklerin literatür çalışmalarıdır. 

Kaynak: Konutlarda Hedonik Fiyat Modeli Üzerine Bir Literatür İncelemesi (Ekonomik Yaklaşım 2019, 30(112): 1-18)


![1](https://github.com/user-attachments/assets/20c28d8e-b010-4ef8-850c-376794b33944)

![2](https://github.com/user-attachments/assets/2274358d-e008-4ad1-b4f1-35ed59236cf8)

Tüm eğitimler için;

https://www.youtube.com/@AnlasEkonomi
