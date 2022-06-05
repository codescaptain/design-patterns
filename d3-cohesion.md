## Birliktelik (Cohesion)
Bileşen karmaşıklığı, alt parçacıkların ne kadar "birlikte" (togetherness) olduğunun bir ölçüsüdür ve **cohesion** olarak adlandırılır.
- Birliktelik tek bir amaca, sorumluluğa odaklıdır(single responsibility), sadece tek bir iş ile ilgili olmak, onu yapmaktır.
- Dolayısıyla farklı isler farklı yerlerde yapılacak sekilde ayrılmalıdır:
	- Separation of concerns
		- Mühendisliğinde aslında farklı bir çok başarılı disiplininde arka tarafindaki en temel şeylerden birisi; karmasik yapilari atomik alt parçaları böl, her birini kendi kendi içinde hallet.
- Birlikteliği yüksek bilesenlerin
	- karmaşıklığı düşüktür
	- bakım maliyeti düsüktür
	- tekrar kullanıma daha yatkındır
- Bir sınıfın tüm yapısı, tüm alanları ile fonksiyonları, methodları aynı ortak amaç ise bu durumda o sınıfın birlikteliği yüksektir.
- Bir fonksiyon/method ne kadar az iş yaparsa birlikteliği o kadar yüksek olur.
- Aksi hallerde sınıf ve fonksiyon/method birlikteliği düşüktür
	- **High-cohesion yada strong-cohesion**
	- **Low-cohesion yada weak-cohesion**
### En kötüsünden en iyisine doğru, farklı birliktelik türleri
----
#### Gelişigüzel/(Coincidental):
Bir araya getirilmiş iligili yapılardır. Nesne soyutlamasının eksik yada hiç olmadığı durumlarda sık görülür
#### Mantıksal/(Logical):
Gerçekte farklı tabiatta olmlarına rağmen tek bir şey ile ilgili olduğu  düşünülen bir araya getirilmiş yapılardır. Örneğin, tüm input yada sifreleme işlemlerini halleden bir sınıf.
Aşağıda gördüğümüz Kesme sınıfı ama her şeyi kesiyor. Arka tarafta birbirleri ile alakalı olmayan işler yapıyorlar
```java
public class Cutter{
public void cutHair();
public void cutTalk();
public void cutWood();
}
```
#### Zamansal/(Temporal):
Zamansal birliktelikten dolayı bir araya getirilmiş yapılardır. Ornegin, bir dosyayı acmaya calışan bir sınıfın, dosyayı açamadığında fırlatılan sıra dışı durumu yakalayıp, durumu loglayıp, gerekli uyarıları üretip, yeni bir dosya açıp işine devam etmesi.

#### Prosedürel/(Procedural):
Yordamsal paradigmanın birliktelik anlayışıdır. Bir konu ile ilgili işlerin yukarıdan aşağıya doğru fonksiyonel olarak ayrılması ve hepsinin bir sınıfta bir araya getirilmesidir.
#### İletişimsel/(Communicational/Informational):
Aynı veri üzerinde çalışan yapıların bir araya getirilmesidir. Veri işlemenin öne çıktığı hallerde sık görülür.
#### Ardaşıl/(Sequential):
Sınıf seviyesinde birinin çıktısının diğerini beslediği pipe seklinde çalışan fonksiyonları bir araya getiren sınıflardır. Daha kötüsü tek bir fonksiyonun ardışıl işeri hallettiği durumdur.
#### Fonksiyonel/(Functional): 
Tek, çok iyi tanımlanmış ve olabildiğince küçük bir işe yada sorumluluğa yönelik olarak bir araya getirilmiş yapılardır.
- En iyi birliktelik durumudur.
- Yazılım geliştirme sürecinde detaylar arttıkça diğer birliktelik türlerinde yapılar gittikçe büyüme eğiliminde olurken fonksiyonel birliktelikte bölüp parçalama yoluyla odağın korunmasına çalışılır.
- Çünkü detay arttıkça is yada sorumluluğun tanımı değişir, her iş farklı ve küçük işlere bölünür

