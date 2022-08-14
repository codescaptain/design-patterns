# Nesne Kategorizasyonu
## Temel nesne tipleri
- Yazılım sistemleri farklı rollerde iş gören nesneler bulunur.
- Nesneler, bazı rollere göre sınıflandırılabilir.
- Rollere uygun sorumluluk ve veriyi bir araya getirmek, farklı rollere ait olanları ayırmak birlikteliği artıran en temel etkendir
- Dolayısıyla nesne rolleri, daha yüksek birlikteliğe sahip nesneler el etmeye yardımcı olabilir.
## Jacopson'ın Sınıflandırması - I
- Ivor Jacopson'ın nesne sınıflandırması şöyledir:
	- **Boundary**: Sistemin aktörleriyle olan iletişimini yöneten nesnelerdir, interface nesleri de denir.
	- **Control**: İş süreçlerini yöneten ve ilgili kuralları bilen nesnelerdir. Çoğunlukla service olarak bilinirler.
	- **Entity**: İş alanı (business domain) nesneleridir.
## Jacopson'ın Sınıflandırması - II
**Boundary**: Pencereler ya da düğmeler gibi UI/GUI bileşenleri, socket bağlantısı yapan nesneler, web servisler bu tipten nesnelerdir.
**Control**: İş süreçlerini yöneten ve ilgili kuralları bilen nesnelerdir. Çoğunlukla servis(service) olarak bilinir.
**Entity**: İş ile ilgili bilgiyi bilen ve en temel davranışları modelleyen nesnelerdir. JPA, EntityFramework vb. frameworklerin ürettiği ve sadece veri tabanı tablolarına karşı gelen nesneler bu anlamda entity değildir çünkü davranışa sahip değilleridir.
 ## Jacopson'ın Sınıflandırması - III
 - B-C-E (Boundary-Control-Entity) modelinde davranışlar nesnelere dağılmış durumdadır.
 - Veri ile veriyi işleyen davranış entity, veri sunumu boundary, koordinasyon vb. use case ve uygulama davranışı ise controller nesneleridir.
 ### Model-View-Controller
 Model-View-Controller (MVC) kalıbını, Jacopson'ın sınıflandırmasıyla ifade edersek, aşağıdaki eşleştirmelere vararız.
 - Boundary => View
 - Entity => Model
 - Controller => Controller

## Jacopson'ın Sınıflandırması - IV
- B-C-E nesneleri arasındaki bağımlılıklar temelde dıştan içe doğrudur.
	- Aynı roldeki nesneler birbirlerini kullanabilirler.
	- Boundary nesneleri controller nesnelerini, control nesneleri de entityleri kullanır
- Bunun tersine ya da boundary nesnelerinin controller nesnelerini atlayarak entity nesnelerini kullanması tavsiye edilmez.
## Jacopson'ın Sınıflandırması - V
- Bu durumda entity nesnelerinin durumunu temsil eden veriyi uygulama içinde gezdirmek için **Data Trasnfer Objects (DTO)** vb. kalıplar kullanılabilir.
- Ya da davranışa değil sadece veriye ulaşım amaçlı erişime izin verilebilir.
## Hexogonal Architecture - I
![enter image description here](https://i.im.ge/2022/08/14/Orq1ix.CleanArchitecture.jpg)
- Bir başka nesne kategorizasyonu **Altıgen Mimaride (Hexogonal Architecture)** vardır.
	- Alternatif isimleri onion/soğan mimarisi yada Ports & Adapters'dır
- İlk defa 2006 yılında A.Cockburn tarafından teklif edilmiştir.
- Teklif edildiğinden bu yana katmanlı bir yapıya bürünmüştür.

***
### Ekstra Notlar
Bizim farklı cinsten objelerimiz vardır ve biz soğan gibi katmanlı bir yapı olarak düşünürsek merkezde business rule ları yöneten entityler vardır.
Business üzerinde application logic vardır (use cases).
#### Aplication Logic'ten kasıt nedir?
En dışarıdan data yı alıp entitylerin durumlarını manipüle edecek daha sonra kalıcı hale getirecek, loglayacak şekilde, security checkleri yapılacak şekilde business tan bağımsız ama uygulamanın mantığı olacak şekilleri kim üretecek ? Use cases dediğimiz şeyde tam budur (Application Rules).

Uses cases da bulunan objeler entity leri yönetebilmeli ama tam tersi olmamalıdır.

Dışarıda Presenter lar ve Contoller lar vardır. Bunlarda soğanın daha dış katmanında farklı device, clientler, UI arayüzleri, external interface ler, DB ve farklı sistemlerle bizi iletişimde tutar  ve aradada bular ile alakalı adaptor lerimiz var. 

En dışarıda da Frameworkleri, driver ve device ları kullanıyoruz. En core dan yani business tan dışarıya doğru yani daha teknolojik olana doğru gidiyoruz.
 ***
 ## Hexogonal Architecture - II
 ![enter image description here](https://i.im.ge/2022/08/14/Orq1ix.CleanArchitecture.jpg)

 - Hexogonal mimaridei dışarıdaki yapılar mekanizmalar, içeridekiler ise kurallardır.
 - **Entity** kurumal kuralları, Use Caseler ise uygulama kurallarını temsil eder.
 - **Interface Adapter (Controller, Presenter ve Gateway)**: En dıştaki yapılarla Use Caseler arasındaki iletişimi sağlayan adaptorlerdir. Gerekli veri formatı dönüşümlerini de yönetir.
	 - Bu yapılar Web yada DB için geçiş sağlar ve örneğin MVC yada DAO kalıpları burada uygulanır.
 ## Hexogonal Architecture - III
 ![enter image description here](https://i.im.ge/2022/08/15/OrI5yJ.Graph-7.png)
-	**Frameworks ve Drivers** ise en az kod yazılan ve daha çok araç(tool) cinsinden yapılardır.
-	Akış Controller dan başlar ve Use Case ile ilerleyip Presenter da son bulur
-	Bağımlılıklar da dışarıdan içeriye doğru ilerler, dışarıdakiler içtekileri bilir ama tam tersi olmaz.

 ## Birliktelik Karşı-Kalıpları
 - Birliktelik karşı-kalıpları (cohesion anti-pattern) genelde nesnelerin mimarideki ve fonksiyonel yapıdaki rollerini karıştırmaktan, aralarındaki farkları gözetmekten kaynaklanır.
 - **Meilir Page-Jones**'a göre 3 yaygın çeşidi vardır:
	 - Mixed-instance cohesion
	 - Mixed-domain cohesion
	 - Mixed-role cohesion
### Mixed - Instance Cohesion
- Bu durumda bir sınıfın bazı özellikleri bazı nesneleri için geçerli bazı nesneleri için geçerli değildir.
- Bu durum aslında iyi tanımlanmamış bir sınıf hiyerarşisine işaret eder.
- OCP(The Open/Closed Principle)'ne doğrudan aykırıdır.
- Nesne kavramının oturmadığı ve nesne-merkezli tekniklerin iyi uygulanmadığı, daha çok veri modellerinin ağır bastığı ortamlarda sık görülür.
- Çözümü, her sınıfın sadece kendisi ile ilgili özelliklere sahip olduğu bir miras hiyerarşisi kurmaktır.
- Bu durumda tip bilgisinden nesneleri ayırt etme görevi çok şekillilik (polymorphism) sayesinde çalışmamıza kalır.
	- Bu durumda ne bu sınıfın kodlarına ne de istemci kodlarına tipe bağlı ayrımlara gerek kalır.
### Mixed - Domain Cohesion
- Bu durumda bir sınıf, farklı yazılım alanlarının (domain) nesnelerinin özelliklerini bir araya getirir.
	- Yazılım alanıyla kastedilen ise bir yazılımı oluşturan farklı nesne kategorileridir. Sırası ile:
	- Uygulama alanı (application domain)
	-  İş alanı (Business domain)
	- Mimari Alan (Architecture domain)
	- Temel Alan (Foundation domain)
	- Yukarı doğru çıktıkça Reuseability (tekrar kullanılabilirlik) azalır, aşağı doğru indikçe artar.
#### Uygulama Alanı
- Uygulamaya has nesneleri içeriri:
	- **Service nesneleri**: Use caseleri gerçekleştirecek şekilde entity lerin koordinasyonundan sorumlu nesneler,
	- Events ve event handler nesneleri,
	- Workflow vb. nesneler,
- Tekrar kullanımları düşük olan nesnelerdir. Ancak birbirleriyle benzer uygulamalarda uygulamalarda tekrar kullanılabilirler.

#### İş Alanı
- İşi temsil eden nesneler, entity, enum ve interface nesneleridir.
	- Entity lerin alanları olarak kullanılacak ama kendisi entity olmayan diğer nesneler: Adress, PhoneNumber vb. nesneler ile DTO
	- Sıra dışı durumlar
	- Entity için validator, converter, comprator, sorter, formatter vb. nesneler
- Tekrar kullanımı bener iş alanlarında yüksek nesnelerdir.
 #### Mimari Alan
- Mimari stil-kalıp, tasarım kalıbı, boundary, teknoloji vb. nesneler,
	- MVC, DAO vb mimari stil, kalıp ve altyapı neseneler,
	- Ön bellek (cache), thread pool, transaction vb.
	- IU/GUI mekanizmaları, web servis vb. iletişim nesneleri
	- Spring, EJB, JPA, EntityFramework, Django vb. teknolojik nesneler
- Tekrar kullanımı iş alanlarından ve uygulamadan bağımsızdır ve yüksektir. 
#### Temel Alan
- En temel nesneleri içerir:
	- Programlama dili tipleri: Primitives ve wrapper nesneleri, String, Date, Time, Thread, koduna müdahele edilmeyecek sınıflar.
	- Sık kullanılan kütüphane nesneleri,
	- Oluşturulan diğer temel nesneler: Better String, Complex Number, HttpWrapper, vs.
- Tekrar kullanımı en yüksek olan nesnelerdir.
### Yazılım Alanları İlişkileri 
- Nesneler, alanlarına has olmalıdırlar, birden dazla olan tek bir nesne temsil edilmemeli
- Her alanın nesneleri, aynı alandaki diğer nesneleri kullanabilir
- Farklı alanlardan olan nesneler, birbirlerini ancak bağımlılık yönünde kullanabilirler, bağımlılık yönüne ters kullanımdan kaçınmalıdır. 
### Mixed - Role Cohesion
- Aynı alan içerisinde olduğu halde farklı rollere sahip nesnelerin özelliklerinin tek bir nesnede toplandığı durumdur.
- Örnekleri çok sık görülür çünkü diğer ikisi kadar açık değildir
- Örnekleri çok sık, özellikle entity nesnelerinde görülür
- Problemi tarif etmek diğer ikisine göre daha zordur. Çünkü sınıf tek bir domainde ve o domainin içindeki farklı rolleri bir araya getirmiş. Burada role kavramı bize daha fazla detay veriyor.
#### Ornek
	

    public class Person{
    String name
    ...
    int numberOfDogs;
    int numberOfCC;
    }
    
  - Örneğin erişim kolaylığı olsun diye Person nesnesi üzerinde *numberOfDogs* vb. alanlar tanımlamak
	  - Tekrar kullanımı önler
  - Farklı durumlara(state) sahip bir nesnenin durumlarının hepsi aynı nesnede yönetmek
	  - Bu mixed-instance içinde bir örnektir
    

	

