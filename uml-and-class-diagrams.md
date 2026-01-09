# UML ve Sınıf Diyagramları:
## Modelleme Nedir ?
- Gerçek hayattaki problemleri bilgisayarın sanal ortamında çözebilmek için, her şeyden önce problemin uygun şekilde bilgisayar ortamına aktarılması gerekmektedir. Bu işlem “soyutlama (abstraction)” ya da “modelleme (modeling)” olarak anılır.
- Modelleme, insanın problem çözmek üzere eskiden beri kullandığı bir yöntemdir. Büyükçe bir problemin tamamını zihinde canlandırıp çözmeye çalışmak yerine, oluşturulacak model ya da modeller üzerinde hedef sistemin görünüşü, davranışı ya da bazı durumlarda verdiği tepkiler gözlemlenebilir
## UML (Unified Modeling Language) Nedir ?
- UML’ in Türkçe deki karşılığı “Birleşik Modelleme Dili” olsa da aslında bir programlama dili değil yazılım mühendisliğinde nesne tabanlı modellemede kullanılan standart olmuş görsel modelleme dilidir. Bir yazılımın hayata geçirilmesinde farklı görev tanımlamaları bulunmaktadır (Tasarımcılar, programcılar, analistler, testçiler, kalite sorumluları, kullanıcılar) gibi. Bir yazılım için her kişinin farklı bakış açısı vardır. Müşteri açısından projeye baktığımızda müşteriyi işlerin sıralandırılması, sisteme artıları ve eksileri , işler arasındaki ilişkiler ilgilendirirken bir fonksiyonun detayları ilgilendirmemektedir. Analist açısından baktığımızda nesne özellikleri, fonksiyonlar ve alacakları parametreler yeterli iken tasarımcı açısından parametrelerin veri tipleri, fonksiyonun performansı, yaşam süresi gibi bilgiler de önemli olmaktadır.
- Bu nedenle UML bu ekip için gerekli farklı diyagramlar içermektedir. Yazılım geliştirme işinde yer alacak farklı ekiplerin farklı bakış açılarına uygun farklı UML diyagramları bulunmaktadır.
## Peki Neden UML ?
- Hataların kolaylıkla fark edilip en düşük seviyeye indirgenmesi.(Risk, zaman, maliyet)
- Kodlama kolaylığı sağlar.
- Kullanılan tekrar kod sayısı ayırt edilebilir bu sayede verim sağlanır.
- Mantıksal hataların minimum seviyeye düşürülmesini sağlar.
- Geliştirme maliyetinin düşmesini sağlar.
- Resmin tamamının görülmesini sağlar.
- UML diyagramları ile yazılım tamamını görebileceğimiz için verimli bellek kullanımı sağlanabilir.
- Karmaşık sistemlerde değişiklik yapmayı kolaylaştırır.
- UML ile dokümanlandırılmış kodları düzenlemek daha az zaman alacaktır
- UML diyagramlarını kullanan yazılımcılar aynı dili konuşacaklarından kolay iletişim sağlanır.
## UML Diyagram Türleri

<img width="848" height="417" alt="image" src="https://github.com/user-attachments/assets/7579e2a4-b948-438c-8106-dd9ae2677922" />

### Sınıf Diyagramları (Class Diagram)

- Nesne yönelimli programlamada her bir nesnenin konseptini belirten yapılara sınıf (class) adı verilmektedir. Sınıflar çok farklı yapılarda ve işlevlerde olabilirler. Bununla birlikte, genellikle programlamada bütün iş tek bir sınıfın üzerine yüklenmez. Kuracağınız sistem ile ilgili önce temel sınıflar belirlenip daha sonra bunlar arasındaki bağlantıların açıklanması gerekir. Bunu bir yazılım geliştirme sürecinin tasarım aşamasında yaparız. Burada sınıfların modellemesi için UML kullanırız ve Sınıf Diyagramları adı veririz.

- Programlamada sınıfların niteliklerini "değişkenler" , davranışlarını da "metotlar" tanımlar.

### Sınıf Tanımlama

<img width="244" height="210" alt="image" src="https://github.com/user-attachments/assets/cdc200cd-f087-4391-a670-984d056635d6" />

- Şekilde görüldüğü üzere bir dikdörtgen 3 parçaya bölünerek, ilk parçasına "Sınıf Adını", ikinci parçaya "Sınıfın Değişkenleri" , son parçaya da "Sınıf Metotları" yazılır.

## Nitelikler (Değişkenler,Variable)
<img width="347" height="333" alt="Screenshot 2026-01-08 221819" src="https://github.com/user-attachments/assets/861c4d5d-2936-437c-8dea-d77bf2928447" />


**Sınıfa ait niteliklerin sözdizimi (syntax):**

> <Görünürlük> <İsim>: <Tür> <Multiplicity> = <Varsayılan Değer>

- Görünürlük (Visibility): Niteliğin dışarıdan erişim ilkesinin ne olduğunu belirtir. Eğer bir sınıfın niteliği public ise buraya “+“, private ise buraya “–“, protected ise buraya “#” işareti konulur.
- İsim (Name): Niteliğe ait isimlendirme yapılır.
- Tür (Type): Bir niteliğin veri tipini belirtir.
- Varsayılan Değer (Default Value): Niteliğin, ilk değerini belirtir.

## Davranışlar (Metotlar,Behaviour)
<img width="364" height="282" alt="image" src="https://github.com/user-attachments/assets/74e83695-182b-4fe5-b426-c8ec43a6a4d0" />

**Sınıfa ait davranışlara ait sözdizimi (syntax):**

> <Görünürlük> <İsim>(<Parametreler>): <Geri Dönüş Tipi>

- Görünürlük (Visibility): Bu davranışın dışarıdan erişim ilkesinin ne olduğunu belirtir. Alabileceği değerler niteliklerde olduğu gibidir.
- İsim (Name): Metoda ait isimlendirme yapılır.
- Parametre Listesi (Parameter List): Programlamada metodun aldığı parametreler tür bilgileri ile birlikte buraya yazılır.
- Geri Dönüş Türü (Return Type): Metodun geri dönüş tipini belirtir.

## Sınıflar Arası İlişkiler
Yazılımlar çoğu zaman tek sınıftan oluşmazlar. Küçük programlar bile çoğu zaman birden fazla sınıfa ihtiyaç duymaktadır. Bir yazılımda sınıf sayısı arttıkça programın tasarlanması da karmaşıklaşır. Bu yüzden UML diyagramlar kullanılarak, bu karmaşıklığı daha olayın en başında minimuma indirip maliyeti azaltmaktır. Sınıflar birbirleriyle ilişki içerisinde olan yapılardır. Bu ilişkileri UML diyagramlarında da göstermek gerekir. Elbette ilişkinin türüne göre gösterim de değişiklik gösterecektir.

<img width="379" height="334" alt="image" src="https://github.com/user-attachments/assets/e2c8e44e-ba16-4f8d-b14c-4eae4d18fa3f" />

- Bağlantı İlişkisi (Association)
- Genelleme/Kalıtım İlişkisi (Generalization/Inheritance)
- Bağımlılık İlişkisi (Dependency) (Aggregation, Composition)
- Gerçekleştirim İlişkisi (Realization)

## Bağıntı İlişkisi (Association Class)
- Sınıflar arasındaki ilişkiler çizgi ile gösterilir ve çizginin üstüne ilişki şekli yazılır. Sınıflar arası ilişkiler bire bir, bire çok, bire n gibi olabilir. Örneğin aşağıdaki gösterimde e-ticaret sisteminde müşteri ve ürün ilişkisini görmektesiniz

<img width="609" height="309" alt="image" src="https://github.com/user-attachments/assets/6739f885-ec14-4036-8109-709932817662" />

Yukarıda ki diyagrama göre müşteri ve ürün arasında Satın Alma ilişkisi vardır ve bunun için de Sipariş oluşturması gerekir. Yukarıda ki diyagram da bire bir ilişkisi vardır.

Sınıf diyagramlarında sınıflar arasında bire n ilişki kurulabilir. Bir sınıf, n tane başka bir sınıf ile ilişkiliyse buna bire-çok (1-n) ilişki denir.

<img width="743" height="176" alt="image" src="https://github.com/user-attachments/assets/a677144f-12ef-468f-99bd-53b9e4a063a5" />

Yukardaki örnekte ise bir sepette n tane ürün olabileceği gösterilmiştir. İki sınıf arasında yalnızca tek bir bağıntı çizilmesi gibi bir kısıt yoktur. En temel bağıntı ilişki tipleri aşağıdaki gibi listelenebilir;

- Bire-bir (1-1)
- Bire-çok (1-*)
- Çoka bir (* - 1)
- Bire-sıfır (1-0)
- Bire-Beş yada Bire-sekiz (1-5 veya 1-8)

 Diğer bir ilişki türü ise bir sınıfın kendisiyle kurduğu ilişkidir. Bu tür ilişkiler genellikle bir sınıfın sistemde birden fazla rolü varsa ortaya çıkar. Bu tür ilişkilere `"reflexive associations"` denir.
 
 <img width="364" height="233" alt="image" src="https://github.com/user-attachments/assets/ef35caa1-b69c-4107-a5f9-4a90347dca15" />

## Sınıflar Arasında Türetme (Inheritance) ve Genelleme (Generalization) İlişkisi

Nesne yönelimli programlamanın en önemli parçası türetme (inheritance)'dir. Türetme yoluyla bir sınıf başka bir sınıfın var olan özelliklerini alarak, o sınıf türünden başka bir nesneymiş gibi kullanılabilir. Bir sınıfın işlevleri türetme yoluyla genişletilecekse, türetmenin yapılacağı sınıfa taban sınıf (super class), türetilmiş olan sınıfa da türemiş sınıf (sub class) denir. Şekilsel olarak türemiş sınıftan taban sınıfa bir ok olarak belirtilir.

<img width="748" height="407" alt="image" src="https://github.com/user-attachments/assets/57119f23-3ff4-41d5-ac87-da5553a1f862" />

Bu örnekte "Şekiller" sınıfına ait tüm özellikler altında üretilmiş olan, diğer sınıflara aktarılmıştır.

## Bağımlılık İlişkisi (Dependency) ve Birleştirme (Aggregation, Composition):

Birden fazla parçadan oluşan sınıflar arasındaki ilişkiye "Aggregation" denir. Aggregation ilişkisini 'bütün parça' yukarıda olacak şekilde ve bütün parçanın ucuna içi boş elmas yerleştirecek şekilde gösteririz. İçi boş elmas ile gösterilen ilişkilerde her bir parça ayrı bir sınıftır ve tek başlarına anlam ifade ederler.

Örneğin Araba sınıfını 1 Motor, 5 Koltuk ve 4 Lastik sınıflarının oluşturduğunu düşünürsek aralarındaki ilişki aşağıdaki gibi gösterilir.

<img width="748" height="407" alt="image" src="https://github.com/user-attachments/assets/e59ab6a6-951c-4087-bfe8-3619411799fb" />

## Olusma (Composition) iliskisi:

Asıl sınıf üretildiğinde parçaları da üretilecek ise bu ilişkiye **Composite** denir. Parça-bütün ilişkilerini modellemekte kullanılırlar. Bütün nesneler yaratıldığında parçaları da yaratılmalıdır. Bütün ve bütünü
oluşturan parçalar arasında sıkı bir ilişki vardır. Oluşma ilişkisi 'bütün parça' yukarıda olacak şekilde ve
bütün parçanın ucuna içi dolu bir elmas gelecek şekilde gösterilir.

<img width="568" height="319" alt="Screenshot 2026-01-09 174333" src="https://github.com/user-attachments/assets/c4c4ef24-6613-495e-b795-ff54f3f85304" />

Eğer Araba sınıfı oluşturulduğunda Motor, Koltuk ve Lastik sınıfları da oluşturulacak ise içi dolu dörtgen dolu olarak gösterilir.

## Gerçekleştirim (Realization) İlişkisi

<img width="492" height="315" alt="image" src="https://github.com/user-attachments/assets/46826b1c-107f-456a-9011-4e06ed9aa050" />

Gerçekleştirim ilişkisi en çok kullanıcı arayüzlerinin **(user interface)** modellenmesinde kullanılır. Arayüz yalnızca method adlarını ve bunların parametrelerini içermektedir. Program yazarken, yalnızca arayüzlerin kullanılması ve arayüzü gerçekleştiren sınıfın diğer sınıflardan ayrı tutulması, yazılımın geliştirilmesi ve bakımında önemli kolaylık sağlar.


### References:
1. [Uml-ve-modelleme-bolum-1](https://univera-ng.blogspot.com/2009/10/uml-ve-modelleme-bolum-1.html)
