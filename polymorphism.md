# Çok Biçimlilik(Polymorphism)

Polymorphism(çok biçimlilik) NYP'de programlama dilinin farklı tip verileri ve sınıfları farklı şekilde işleme yeteneğini belirten özelliğidir. Daha belirgin olmak gerekirse, metotları ve türetilmiş sınıfları yeniden tanımlama yeteneğidir.

Polimorfizm, Sub Class sınıfların Super Class sınıflardaki metotları geçersiz kılması **(method overriding)** sayesinde çok biçimli olarak davranmasına denir. Bu sayede Sub Class sınıf Super Class sınıfından gelen davranışı kendine göre şekillendirebilir.

Polimorphism olmasi icin inheritance olmasi gerekir.

**Method Overriding** **(Metotlarda "Geçersiz Kılma")** ise bir Sub Class sınıfın içine doğrudan ya da dolaylı Super Class sınıflarından gelen bir(ya da daha fazla) yöntemin aynısının **(aynı yöntem adı ve aynı parametre listesi)** kodlanmasına verilen addır.

Polimorfizm sayesinde uygulamaların genişletilebilirliğini sağlarız ve bir Super Class sınıfın sunduğu yöntemleri geçersiz kılan Sub Class sınıflar yardımı ile Super Class sınıfa göre kodlanmış tek bir kod kesimine farklı davranışlar yüklemek olanaklı olmaktadır. Öyleyse, elimizde **esnek** bir altyapı var demektir. Bu **esneklik** altyapıya yeni türlerin eklenmesi, **kalıtım ve geçersiz kılma ilişkileri** çerçevesinde oldukça kolaydır.

## Polimorfizm Örneği
1) 
<img width="1470" height="811" alt="image" src="https://github.com/user-attachments/assets/ade1d91b-edfa-40b5-a382-9aefa7ac9056" />

- ⚠️Yukardaki Gorselde Super Class taki(Animal) method olan `speak()` assagida Sub Class larda da var bu durum **Method Overriding** olarak adlandirilir. Method Overriding yaparak Polymorphism yapmis oluruz⚠️✅.

2)
<img width="2010" height="1624" alt="image" src="https://github.com/user-attachments/assets/aa2ab279-d83c-42e7-876f-b19728ea9a32" />

- Yukardaki 2. Gorselde Sub Class, Super Classdaki methodu almayip ayni isimde olarak yeniden olusturursak **Calisan** Super Class indaki giris(anaGiris) methodu **Memur** Sub Class indaki giris(kapiNo) ayni method isimleri ve boylelikle biz **Method Overriding** yapmis olduk bu durumda **Polymorpihsm** oldu. **Memur** sinifindan uretilmis diger siniflarda `giris() methodu cagrilidiginda` **Calisan sinifindaki giris() methodu** artik calismayacak ve **Memur sinifindaki giris() methodu** calisiyor olacak.
- Ama **Memur** Classindaki **giris() methodu** ile **GuvenlikGorevlisi** Class indaki **giris() methodu** **Overriding degildir⚠️** Cunku parametre sayilari ayni degildir kapiNo,kart olarak 2 parametredir bu durum bu yuzden **Over Loading** olur 
- **Calisan** Classinda **yemekhane() methdu** ile **Akademisyen** Classindaki **yemekhane(bolum) methodu** farkli parametre sayilarina sahiptir bu yuzden **Over Loading** olur.⚠️
- **Asistan** Classinda ki **derseGir() methodu** ile **LabAsistani** Classindaki **derseGir()** methodu ayni parametre sayisina sahip olup ayni method adi olup, parametre tipleri ayni olup **Overriding** olmus olurlar ve boylelikle **Polymorphism** yapmis oluruz burada.

`Ama **des=rseGir()** ayni davranis sergilerse assagidkai igtimal oratay cikar`

1. Problem Tanımı

UML diyagramında dersGir() metodunun:

- Akademisyen
- Asistan
- Lab Asistanı

sınıflarında ayrı ayrı gösterildiği görülür. Bu durum çoğu zaman şu soruyu doğurur:

> “Eğer bu metodun yaptığı işlemler üç sınıfta da aynıysa ne olacak?”

2. UML Perspektifi (Tasarım Niyeti)

UML diyagramları kod tekrarını değil, davranış sözleşmesini gösterir.

UML’de bir metodun alt sınıflarda da görünmesi şu anlama gelir:

- Bu sınıf, bu davranışı garanti eder
- Bu davranışa erişimi vardır

UML şunları söylemez:

- Metodun içi nasıl yazılacak
- Override zorunlu mu
- Kod tekrar edilmeli mi

Bunlar uygulama (implementation) kararlarıdır.

3. Java Perspektifi (Gerçek Kod Kuralı)
Temel OOP Kuralı

> Aynı davranış tekrar ediyorsa, tek bir yerde yazılır.

Bu yer:

- Davranışın tüm alt sınıflar için ortak olduğu
- En üst mantıklı sınıftır

Bu senaryoda bu sınıf Akademisyen’dir.

4. Davranışlar Aynıysa (Override YOK)

Eğer dersGir() metodu üç sınıfta da birebir aynı işlemleri yapıyorsa:

```java
class Akademisyen {
  void dersGir() {
    System.out.println("Derse giriliyor");
    yoklamaAl();
    dersAnlat();
  }
}

class Asistan extends Akademisyen {
  // dersGir() override edilmez
}

class LabAsistani extends Asistan {
  // dersGir() override edilmez
}
```

Sonuç:

- Kod tekrarı yok
- Temiz tasarım
- UML ile çelişmez
- Polymorphism doğal olarak çalışır

Alt sınıflar metodu yazmasa bile kullanabilir.

5. Davranışlar Farklıysa (Override VAR)

Davranış gerçekten farklıysa, override yapılır.

Asistan için ek davranış:
```java
class Asistan extends Akademisyen {
  @Override
  void dersGir() {
    super.dersGir();
    ogrenciSorulariniYanitla();
  }
}
```
Lab Asistanı için farklı akış:
```java
class LabAsistani extends Asistan {
  @Override
  void dersGir() {
    labHazirla();
    super.dersGir();
  }
}
```
Sonuç:

- Ortak davranış korunur
- Rol farkı eklenir
- Polymorphism aktif şekilde çalışır

6. Yanlış Tasarım Örneği (Kaçınılması Gereken)

Aşağıdaki durum ne override ne de doğru polymorphism üretir:
```java
class Akademisyen {
    void dersGir() {}
}

class Asistan extends Akademisyen {
    void dersGir(String dersAdi) {}
}
```
Neden yanlış?

- Metod imzası değişmiştir
- Override gerçekleşmez
- UML sözleşmesi bozulur
- Polymorphism çalışmaz

Bu genellikle gizli bug üretir.

7. Altın Kurallar (Özet)

- UML davranışı vaat eder, Java uygular
- Aynı davranış → tek implementasyon
- Davranış değişmiyorsa → override YOK
- Davranış değişiyorsa → override VAR

Parametre ekleyerek override yapılmaz

**Override sayılabilmesi için imzaların birebir aynı olması gerekir.⚠️:**

- Parametre tipi ✅

- Parametre sayısı ✅

- Method adı ✅

Eğer UML’de anaGiris ve kapiNo sadece isimsel fark ise
(yani ikisi de mesela int ise)

> → Bu override kabul edilir.
Parametre adı önemli değildir, tipi önemlidir. ⚠️

**Method overloading’in kuralı şudur:⚠️**

- Aynı method adı ✅

- Aynı sınıf ✅

- Farklı imza (signature) ✅

**İmza dediğimiz şey:**

- Parametre sayısı

- Parametre tipleri

- Parametrelerin sırası
