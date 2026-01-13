# Kalıtım (Inheritance)

Kalıtım, programlama ortamında da gerçek hayattaki tanımına benzer bir işi gerçekleştirir. Bir sınıfın başka bir sınıftan kalıtım yapması demek, kalıtımı yapan sınıfın diğer sınıftaki nitelik ve davranışlarını kendisine alması demektir. Kalıtımı yapan sınıfa alt sınıf, kendisinden kalıtım yapılan sınıfa ata sınıf dersek, ata sınıfta tanımlı olan her şeyin alt sınıf için de tanımlı olduğunu söyleyebiliriz.

Eğer bir A sınıfın B sınıfından kalıtım yapması isteniyorsa, aşağıda ki şekilde tanımlanır.

```java
public class A extends B {
     // 
}
```
## Kalıtım Türleri
### Tek Yönlü Kalıtım (Single Inheritance)
Bir sınıfın başka bir sınıfı genişlettiği alt ve ata sınıf ilişkisini ifade eder.

<img width="260" height="320" alt="image" src="https://github.com/user-attachments/assets/ec9bd9e0-59bb-4b8e-a393-10296300a4c7" />

Bu örnekte B sınıfı A sınıfını miras alır.

### Çoklu Kalıtım (Multiple Inheritance)
Bir sınıfın birden fazla sınıfı miras almasını ifade eder; bu, bir alt sınıfın iki ata sınıfa sahip olduğu anlamına gelir.

Not : ⚠️Java çoklu kalıtımı desteklemez. (Bu olay icin Java da Interface kullanılır)

<img width="660" height="320" alt="image" src="https://github.com/user-attachments/assets/53c0f2fe-cec5-444e-a981-7d956d42c48e" />

### Çok Seviyeli Kalıtım (Multilevel Inheritance)
Bir sınıfa ait alt sınıfın başka sınıfları genişletmesine denir.

<img width="260" height="480" alt="image" src="https://github.com/user-attachments/assets/611dfb1f-e547-44df-8346-80360794cb33" />

Bu örnekte , C sınıfı B sınıfını miras alır, B sınıfı ise A sınıfını miras alır. C sınıfı dolaylı yoldan A sınıfını da miras almış olur.

### Hiyerarşik Kalıtım (Hierarchical Inheritance)
Birden fazla sınıfın aynı sınıfı genişlettiği bir alt ve üst sınıf ilişkisini ifade eder.

<img width="820" height="340" alt="image" src="https://github.com/user-attachments/assets/2d63a89b-5258-4d2f-aa55-94c9836e595b" />

Bu örnekte : B, C ve D sınıfları aynı A sınıfını genişletir.

### Hibrit Kalıtım (Hybrid Inheritance)
Programda birden fazla kalıtım türünün kombinasyonuna denir. Örneğin, A ve B sınıfı, C sınıfını genişletir ve başka bir D sınıfı, A sınıfını genişletir, bu bir hibrit kalıtım örneğidir, çünkü bu, tek yönlü ve hiyerarşik kalıtımın bir birleşimidir.

<img width="860" height="480" alt="image" src="https://github.com/user-attachments/assets/2a097653-7098-4df9-ba1c-38647c9844f7" />

Not : ⚠️Java hibrit kalıtımı desteklemez. coklu kalitimi multile inheritance desteklemediginden hybrit inheritance da desteklemez. 

## Inheritance (Mantığı)
Bir üniversite işlerinin yürütüldüğü bir program yazdığımızı varsayalım. Programda ki tüm olayları modelleyerek sınıflar haline getirelim ve bu sınıfların niteliklerini, davranışlarını belirleyelim.

<img width="936" height="281" alt="Screenshot 2026-01-12 160952" src="https://github.com/user-attachments/assets/95a5a5d8-f1e4-4a7f-904b-d96884cbc200" />

- **Yukardaki gorselin aciklamasi :**

**Ogretim gorevlisi** class inda nitelikler **private** verilmis burdan su anlam cikar, **Encapsulation** yapilmis getter setter yazilmasina methodlarda gerek yok.! 

**Not: OOP mantiginda don't repeat yourself vardir yukardaki gorselde tekrar eden nitelikler ve tekrar eden methodlar vardir mesela adSoyad niteligi tekrar eder, giris(), cikis() methodu tekrar eder bu yapi oop ye uygun olmaz bu sorunu cozmemiz icin `INHERITANCE` kullaniriz javada.**

- Assagida yukardkai gorseldeki sorunu cozmus olduk , calisan diye bir sinif olusturduk inheritance yapmis olduk Super Class altinda sub classlari olur ve okun Super Class tarafi ici bos ok olurdu.(inheritance yonteminde)


<img width="742" height="426" alt="image" src="https://github.com/user-attachments/assets/217f62c6-9d65-4001-88b1-a2141c8b8450" />

- Ama hala yine ortaklar var **OgretimGorevlisi** classinda **Asistan** ve **LabAsistani** classinda nitelikler ortak methodlar ortak 
- Hatta **BilgiIslem** ve **GuvenlikGorevlisi** classinda da ortaklar var onlarida Inheritance yaparak gruplandirmis oluruz. Boylelikle **Multilevel  Inheritance** yapmis oluruz. ⚠️ **Assagida bunu yaptik.**

<img width="618" height="518" alt="Screenshot 2026-01-12 165457" src="https://github.com/user-attachments/assets/dc69472f-c4cc-45ff-b2e3-7830a3e4890e" />



### Kalıtım'da Constructor Zinciri ve Super Anahtar Sözcüğü:
Bir sınıfa ait nesne oluşturulurken, o sınıfın bir constructor işletildiğini, constructor çalışması tamamlandıktan sonra bellekte artık bir nesnenin oluştuğunu biliyoruz. Constructor da nesneleri ilk oluşturuldukları anda anlamlı durumlara taşıyabilmek için kullanıyoruz. Bu durumda, eğer nesnesi oluşturulacak sınıf başka bir sınıfın Sub Class sınıfıysa, önce Super Class ait iç nesnesinin oluşturulması ve bu nesnenin niteliklerinin ilk değerlerinin verilmesi gerektiğini söyleyebiliriz.

İç içe nesnelerin oluşabilmesi için nesnelerin içten dışa doğru oluşması gerekir. İç-nesnenin oluşabilmesi için, nesnesi oluşturulacak sınıfa ait Cosntructor işletilmeye başladığı zaman ilk iş olarak Super Class a sınıfa ait kurucu çağrılır. Eğer Super Class da başka bir sınıfın Sub Class sınıfıysa, bu kez o sınıfın Constructor çağrılır. Constructor zinciri Sub Class sınıftan Super Class sınıfa doğru bu şekilde ilerler. En üstte, Inheritance ağacının tepesindeki sınıfın Constrcutor çalışması sonlandıktan sonra sırası ile alt sınıfların kurucularının çalışması sonlanacaktır. Böylece iç içe nesneler sıra ile oluşturularak en son en dıştaki nesne oluşturulmuş olur ve Constructor zinciri tamamlanır.

### Super Kullanımı: 
Eğer Super Class sınıfta varsayılan constructor yoksa ve programcı Sub Class sınıftaki constructor içinde Super Class sınıfın hangi constrcutor inin çağrılacağını belirtmezse derleme hatası alınacaktır. Çünkü derleyici aksi belirtilmedikçe Super Class sınıfın varsayılan constructor ini çağıran super() kodunu üretecektir. Super Class sınıfın hangi constructorinin  çağrılacağı, super anahtar sözcüğü ile birlikte verilen parametrelere göre belirlenir. Nasıl ki new işleci ile birlikte kullandığımız parametreler hangi constructor in çağrılacağını belirliyorsa, super anahtar sözcüğü ile birlikte kullanılan parametreler de aynı şekilde Super Class sınıfın hangi constructor inin işletileceğini belirler.
