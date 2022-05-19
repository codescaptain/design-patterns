# Yazılım Karmaşıklığı
**F.Books, No Silver Bullet'ta**, yazılımın asil(essential) olan dört özelliği olduğunu ifade eder.
- Yazılım diğer mühendislik ürünlerinden daha karmaşıktır (complexity),
- Yazılım çok sık değişir (changeability),
- Yazılım görülmez (invisible) ve
- Yazılım uyumludur, sahnedeki diğer oyunculara uyar (conformity)
Aslında, görülemez ve uyumlu olmasını, karmaşıklığının ve sık değişmesinin sebeplerinden olduğunu düşünebiliriz. Bu durumda yazılımın en temel iki özelliği, karmaşıklık (complexity) ve değişmedir (change) diyebiliriz.
## Karmaşıklık
Yazılımın, diğer mühendisliklere hatta pek çok bilime göre daha karmaşık olduğu idda edilmektedir, çünkü yazılım:
- Soyuttur, zihinseldir ve görünmez bu yüzden fiziksel kısıtları yoktur,
- Yazılım sisteminin durumlarının sayısı çok fazladır,
- Her yönüyle tanımlamak ve test etmek imkansızdır,
- Yazılım yaşam döngüsünde belki en kolayı, yazılımı kodlamaktır,
	- Çünkü en fazla görünür olan kısım kodlamadır
- Çoğunlukla örneği yoktur, her yazılımı diğerlerinden ayıran birçok temel özellik vardır,
- Yazılımların bileşenleri birbirinden farklıdır, birbirlerine benzeyen kısımlar birleştirilir,
	- Dolayısıyla yazılımların büyümesi var olan bileşenlerin büyümesi ile değil de yeni ve orjinal bileşenlerin eklenmesi ile gerçekleşir.
- Yazılımların bileşenleri arasındaki ilişkiler de doğrusal değil (linear) değildir.
## Karmaşıklık Nedir?
Literatürde farklı karmaşıklık kavramları ve tanımlamaları vardır. Yazılımın karmaşılığına bakıldığında şu iki tür karmaşıklıktan bahsedilir:
- Algoritmik (algorithmic), zaman ve CPU ile ilgili, Big-O notasyonu ile ifade edilir. O(n^2) yada O(n|gn) gibi,
- Yapısal (structural), organizasyonel yapı ile ilgili,

İfade ettiğimiz yapı 2 tane nesne birbiri ile nasıl konuşur veya nesne sayısı n tane olursa n! durum olur bunların hangi en iyi kümesini bulalım ki karmaşıklığı ve değişimi rahat yönetelim.
**Not: Koda bakarak design problemlerini anlamak iğne ile kuyu kazmaya benzer.**

### Yapısal Karmaşıklık
Robert E. Wood, 1986 yılında yayınladığı " **Task Complexity: Definition Of The Construct**" isimli makalesinde, bir işin teorik yapısında üç parça olduğunu ifade eder:
- İşin ürettiği çıktılar (products)
- İş için gerekli işlemler ya da davranışlar (required acts)
- İş için gerekli bilgi girdisi (information cues)

#### Wood'un yaklaşımını yazılıma uyarlarsak:
- Çıktılar, yazılımın ürettikleridir. Arayüzler, kullanıcılara, diğer sistemlere vs. sunulan bilgi öbekleri, raporlar vs. ,
- İşlemler davranışları, sınıf sınıf yada metot gibi yazılım birimleridir,
- Bilgi girdisi ise işlemlerde kullanılan bilgi öbekleridir.
##### Bileşen karmaşıklığı (Component Complexity)
f(ayrık işlemlerin karmaşıklığı, bilgi giderlerinin karmaşıklığı)
##### İlişkisel karmaşıklık (Coordinative Complexity)
f(işlemler arasındaki ilişkilerin karmaşıklığı)

## Yazılım Complexity Bizim için:
### Tek tek bileşenlerinin complexity si + o bileşenlerin birbiriyle run time da nasıl bir ilişki kuracaklarının complexity si 

