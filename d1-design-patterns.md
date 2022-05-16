# Design Pattern
**İyi kod yazmak için sorunun bilinmesi önemlidir**
## Pattern Nedir?
Kodun örneği ve desenidir. Çözümden önce problemi ifade eder. **Christopher Alexander** design patterns i ortaya atan kişidir.
"*Her bir kalıp önce ortamımızda tekrar tekrar olusan bir problemi, sonra da o probleme çekirdek bir çözümü tanımlar. Öyle ki bu çözümü, hiç bir iki kullanımınız birbirinin aynısı olmadan milyon defa kullanırsınız.* " - **Christopher Alexander** 
- Tasarım kalıplarının amacı, nesne merkezli prensibleri kullanarak;

	 - doğru sorumlulukları bulmak (finding correct responsibilities)
	 - degisimi göz önüne alarak bu sorumlulukları nesnelere dağıtmak (highly-cohesive objects)
	 - nesneleri, aralarında az bağımlılık  oluşturacak şekilde kurgulamaktadır (lowly couple objects)
- Yüksek birliktelikli ve bağımlılıklı yapıları nasıl kurgulayacağımızı sürekli karşılaşılan problemler bağlamında, genel bir yapıda ve tekrar kullanılabilecek şekilde modeller.
### Tekrarlanan Problemler
-	Nesneleri nasıl yaratırız?
	- Karmaşık nesneleri nasıl yaratırız?
	- Nesne ailelerini nasıl yaratırız?
- Bir sınıfta sadece bir veya belirli sayıda nesne nasıl yaratırız?
- Nesnelere erişimi nasıl kontrol ederiz?
- Nesneler arasındaki bütün-parça ilişkisini nasıl tasarlarız?
- Bir işi yapmanın pek çok yolu varsa bunları nasıl ifade ederiz?
- Emir-komuta yada olay-bilgilendirme zinciri nasıl oluşturulur?
- Çok sayıda nesne arasındaki haberleşmeyi nasıl yürütürüz?
- Bir nesneye çalışma zamanında yetkinlik nasıl sağlanır?
- Karmaşık duruma sahip olan nesneleri nasıl yönetiriz?
- Nesnenin durumunu nasıl saklar ve sonra yine nasıl ulaşırız?
- Birden fazla nesneyi nasıl yönetiriz?
- Aynı işi birden fazla nesneye nasıl uygularız?
### Nesne Rolleri
- Bahsedilen bu problemlerin çözümlerinde, sık karşılaşılan sorumluluklar ile bunların yerine getiren nesne rolleri ortaya konur.
- Tasarım kalıpları ile elde edilen nesne rolleri, zihnimizde bir rol soyutlaması ve kategorizasyon oluşturur.
- Bu roller, tasarım kalıpları kullanılmasa bile genel tasarımın bir parçasını olusturur.

### Tasarım Kalıplarının Yapısı
Bir tasarım kalbının temelde 4 bileşeni vardır:

 1. İsim ki o kalıbı, problemi ve çözümüyle ayırt etmemizi sağlar.
 2. Problem ki hangi bağlamda nasıl ortaya çıktığını ifade eder.
 3. Çözüm kü parçaları ve aralarındaki ilişkileri ifade eder.
 4. Sonuçlar ki kazanılan ve kaybedilenleri ifade eder.
