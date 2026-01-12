# Encapsulation (Kapsülleme)
## 4 Temel İlke
Nesne yonelimli programlama 4 temel ilke üzerine kuruludur. Bir programlama dilinin nesne yönelimli programlamayı uyguladığını anlamak için bu 4 temel ilkeyi sağlıyor olması gereklidir. Bu temel ilkeler kodların değiştirilebilirlik, yeniden kullanım ve esneklik gibi kriterlerin sağlanmasına ön ayak olurlar.

Bu İlkeler ;

- Encapsulation (Kapsülleme)
- Inheritance (Kalıtım)
- Polymorphism (Çok Biçimlilik)
- Abstraction. (Soyutlama)

<img width="407" height="381" alt="Screenshot 2026-01-11 153007" src="https://github.com/user-attachments/assets/77a42b01-5b23-4550-b716-e402be817001" />

**Encapsualtion ilkesi**, bir sınıfa ait değişkenlerin veya niteliklerin ancak o sınıfa ait metotlar tarafından değiştirilebilmesi ve okunabilmesi ilkesidir. Bu ilke sayesinde nesnelerde oluşacak anlamsızlıkların önüne geçilebilir.

<img width="575" height="235" alt="image" src="https://github.com/user-attachments/assets/553f9c67-2ba8-472b-a6c2-4774165723d0" />

Ayrıca değişkenlere sınıfların dışından erişim olmaması ve bir sınıf içindeki değişkenlerin nasıl ve ne kadar olacağının da başka kodlardan saklanmış olması anlamına gelir. Böylelikle biz değişkenlerimizi sarmalayarak istenmeyen durumlardan korunacak bir filtre haline dönüştürebiliriz. Bunu bir örnek ile anlamaya çalışalım.

**Ozetle**

- Istenmeyen durumlardan korumayi saglar, siniflarin disindan erisim olmamasini saglayarak.

## Erişim Belirleyiciler

Bir sınıfa ait nitelik ve davranışlara ulaşabilmek için Erişim Belirleyiciler (Access Modifier) kullanılır. **Erişim belirleyiciler (Access Modifiers)**, değişken ,metot ve sınıfların önüne yazılır ve yazıldıkları konuların erişebilecekleri alanları belirlerler.

**Private :** `-` Yazıldığı öğenin sadece ait olduğu sınıftan doğrudan erişilebilir olduğunu ve o sınıfın dışındaki kod parçacıklarından doğrudan erişim izni olmadığını tanımlar.

**Public :** `+` Yazıldığı öğenin sadece ait olduğu sınıf için değil, diğer sınıflar tarafından doğrudan erişilebilir olmasını sağlar. Sınıflara ait nesnelerin ve diğer nesneler tarafından kullanılması istenilen metotlar için kullanılır.

**Protected :** `#` public ve private arasında kalan bir erişim düzenleyicidir. Protected ile tanımlanan öğeler,
kendisi ile aynı pakette (package) bulunan sınıflar tarafından doğrudan erişilebilir.


## Encapsuliaton Örneği

- Kitap adında bir sınıfımız olsun ve bu sınıfımıza ait 3 adet değişkenimiz olsun bunlar ; **kitapAdi**, **sayfaSayisi** ve **yazar**. Bu değişkenlerin erişim belirleyicileri **public** olsun ve her sınıftan erişilsin. Kitap sınıfından oluşturacağımız bir nesne bu niteliklerin hepsini taşısın. Bu yüzden oluşturacağımız Constructor (kurucu) metodunu bu şekilde oluşturalım.

<img width="408" height="265" alt="image" src="https://github.com/user-attachments/assets/46156277-6b45-433b-aa10-3fc571427b6e" />

- **NOTE: ⚠️ Hic bir sey konulmazsa protected olur !**

 ```java
public class Kitap {
    public int sayfaSayisi;
    public String kitapAdi, yazar;
    Kitap(String kitapAdi, int sayfaSayisi, String yazar) {
        this.kitapAdi = kitapAdi;
        this.sayfaSayisi = sayfaSayisi;
        this.yazar = yazar;
    }
}
```

- Görüldüğü üzere normal bir sınıfımız ve kurucu metodumuz var. Kitap sınıfından bir nesne oluşturalım.

```java
Kitap book = new Kitap("Harry Potter", 500, "JK Rowling");
```

<img width="338" height="271" alt="image" src="https://github.com/user-attachments/assets/296e631e-d40a-4b6c-8536-73fc8fe7af6e" />

- Kitap sınıfından `book` adlı bir nesne oluşturduk ve bu nesnemizin niteliklerini belirttik. **Peki biz bu kurucu metotta sayfa sayısını negatif bir değer girseydik ne olurdu ?** Hiç bir kitabın sayfa sayısı negatif bir değer olamayacağı için, nesnemizde bir `anlamsızlık` olacaktı. Biz bu sorunu `constructor (kurucu)` metotumuza yazacağımız bir `if` kontrolü ile çözebiliriz.

<img width="445" height="271" alt="image" src="https://github.com/user-attachments/assets/58d4661f-036f-4f20-bf3c-aca6b3d1e46e" />

```java
public class Kitap {
    public int sayfaSayisi;
    public String kitapAdi, yazar;
    Kitap(String kitapAdi, int sayfaSayisi, String yazar) {
        this.kitapAdi = kitapAdi;
        this.yazar = yazar;
        if (sayfaSayisi < 1) {
            this.sayfaSayisi = 10;
        } else {
            this.sayfaSayisi = sayfaSayisi;
        }
    }
}
```
- `Constructor` metodu görüldüğü gibi modifiye ettik ve nesne oluşturulurken anlamız verilerin olmasını engelledik. **Ama sorunlarımız hala bitmedi , biz nesneye ait niteliklere hala dışarıdan erişebiliyoruz ve book.sayfaSayisi = -10 dersek , nesneye ait sayfa sayısını yine anlamsızlaştırmış oluruz.** Bu sorunu çözmek için sınıfa ait değişkenlere dışarıdan erişimi kapatmamız gerekir ve oluşturduğumuz değişkenlerin **erişim belirleyicilerini `(Access Modifiers)` değiştirmemiz gerekli**. Tüm `public'leri private` olarak değiştiriyoruz.
- Sınıfımızın son hali

```java
public class Kitap {
    private int sayfaSayisi;
    private String kitapAdi, yazar;
    Kitap(String kitapAdi, int sayfaSayisi, String yazar) {
        this.kitapAdi = kitapAdi;
        this.yazar = yazar;
        if (sayfaSayisi < 1) {
            this.sayfaSayisi = 10;
        } else {
            this.sayfaSayisi = sayfaSayisi;
        }
    }
}
```
Sınıfa ait değişkenlerimin izinlerini **private** yaparak bu sorunu çözdük ama, biz book nesnesine ait değişkenlere erişimi tamamen kısıtladık. Yani biz oluşturduğumuz nesneye ait sayfa sayısını ekrana bastıramayız çünkü değişken **private** olarak tanımlandı. Ya da sayfa sayısı yanlış girilmiş bir nesneyi daha sonrasında **düzenleyemeyiz.** Bu sorunu çözmek için sınıfa ait değişkenlerimizi **sarmalayarak(encapsulation)**, sınıf içerisinde ki metotlar yardımı ile değişkenlerimizi koruma altına alıyoruz ve kullanıma sunuyoruz. Bu metotlara sonrasında ismini çok duyacağımız Getter ve Setter metotları diyoruz.

<img width="367" height="318" alt="image" src="https://github.com/user-attachments/assets/d54113be-d67a-4772-8a76-4553820790f1" />

## Getter ve Setter Metotları
CamelCase ile adlandirmaliyiz `getSayfaSayisi() : int` gibi.
### Getter
Sınıfımıza ait **private** değişkenler mevcut. Bu değişkenlere `dışarıdan erişebilmek için` **her bir değişkenimiz** için **Getter** metodu yazmalıyız. Nesneye ait bu metot çağrıldığında geriye bir değer döndürmeli ve bu değer bizim istediğimiz **private** değişken olmalı. **sayfaSayisi** değişkeni için **getter metodu** tanımlayalım,

                                       getSayfaSayisi() : int
                                       
- **getter** methodu ile private olan degiskenimize(sayfaSayisi) na ulastik, Degiskeni degistirmek istersek **(private olan bir degiskenin degerini degisitirmek)** `setter` metodunu yazmaliyiz.                                       

```java
public class Kitap {
	private int sayfaSayisi;
	private String kitapAdi, yazar;


	Kitap(String kitapAdi, int sayfaSayisi, String yazar) {
		this.kitapAdi = kitapAdi;
		this.yazar = yazar;
		if (sayfaSayisi < 1) {
			this.sayfaSayisi = 10;
		} else {
			this.sayfaSayisi = sayfaSayisi;
		}
	}
	
	public int getSayfaSayisi() {
		return this.sayfaSayisi;
	}
}
```

Görüldüğü gibi basit bir metot yardımı ile sınıfa ait **private** değişkenimize ulaşabildik. Burada dikkat edilmesi gereken noktalar **getter** metotları **geri dönüşü** olan metot tipindedir ve isimlendirilmesi ise **get** ile başlayıp sonra değişken ismi yazılmalıdır. İsimlendirmeyi bu şekilde yapmasak da çalışacaktır lakin kodun okunabilirliği adına bu kurala uyulması **gerekir.**

### Setter
Biz **getter** metodu ile **private** olan değişkenimize ulaştık.Peki bu değişkenin değerini değiştirmek istediğimizde ne yapmalıyız ? Bir sınıfa ait **private** bir değişkenin değerini değiştirmek için, setter metodu yazılmalıdır. sayfaSayisi değişkeni için setter metodu yazalım.

                              setSayfaSayisi(int sayfaSayisi) : void

```java
public class Kitap {
	private int sayfaSayisi;
	private String kitapAdi, yazar;


	Kitap(String kitapAdi, int sayfaSayisi, String yazar) {
		this.kitapAdi = kitapAdi;
		this.yazar = yazar;
		if (sayfaSayisi < 1) {
			this.sayfaSayisi = 10;
		} else {
			this.sayfaSayisi = sayfaSayisi;
		}
	}
	
	public int getSayfaSayisi() {
		return this.sayfaSayisi;
	}
	
	public void setSayfaSayisi(int sayfaSayisi) {
		this.sayfaSayisi = sayfaSayisi;
	}
}
```
Görüldüğü üzere **setter** metodu sadece değiştirme işlemi yapacağı için **void** olarak tanımlandı ve bir adet parametre aldı. Bu parametre bizim yeni değerimi taşıyor olup, sınıfa ait değişkene aktarılmıştır. Ama burada hala bir sorun söz konusudur, bizler **setter** metodunu kullanarak sayfa sayısını negatif girebiliriz. Bu sorunu aşmak için **constructor (kurucu)** metotta yaptığımız gibi bir **if** koşulu ile bu sorunu çözebiliriz.**Setter** metodunu modifiye ederek nesnemiz için anlamsız olan durumu ortadan kaldırmış olduk. 

```java
public class Kitap {
	private int sayfaSayisi;
	private String kitapAdi, yazar;


	Kitap(String kitapAdi, int sayfaSayisi, String yazar) {
		this.kitapAdi = kitapAdi;
		this.yazar = yazar;
		if (sayfaSayisi < 1) {
			this.sayfaSayisi = 10;
		} else {
			this.sayfaSayisi = sayfaSayisi;
		}
	}


	public int getSayfaSayisi() {
		return this.sayfaSayisi;
	}


	public void setSayfaSayisi(int sayfaSayisi) {
		if (sayfaSayisi < 1) {
			this.sayfaSayisi = 10;
		} else {
			this.sayfaSayisi = sayfaSayisi;
		}
	}
}
```
**Setter** metodunun genel özellikleri ise , geriye bir değer döndürmeyen metot olması ve isimlendirme yaparken başlangıç olarak set yazıp sonrasında değişken ismini yazmaktır.

Bu örnekteki **sayfaSayisi** değişkenini koruma ve anlamsızlaşmasını önlemek için **Nesne Yönelimli Programlamanın** ilkesi olan **Encapsulation** (Sarmalama) ilkesinden yararlandık. Bir sınıfa ait değişkenlerimizi **Getter** ve **Setter** metotları yardımı ile sarmaladık ve istenilen şartlara göre oluşmasını sağladık.

### Examples:

Aşağıdakilerden hangisi Encapsulation (Kapsülleme) ilkesini en iyi şekilde tanımlar ?

a) Çeşitli nitelikleri tek bir birimde birleştirmenin bir yoludur.
b) Çeşitli metot parametrelerini tek bir birimde birleştirmenin bir yoludur.
c) Sınıflara ait metotların farklı parametreler ile yazılmasını sağlar.
d) Sınıfa ait niteliklerin anlamsızlaşmasını engelleyen bir yoldur.

**Cevap: d**

Sınıfa ait değişken private (özel) olarak tanımlanış ise, niteliklere sınıf nesnesinden erişmek için ne yapabiliriz?

a) Sınıf içerisine, ilgili sınıf değişkenini geri döndüren public (herkese açık) bir metot ekleriz.
b) Sınıf içerisine, ilgili sınıf değişkenini geri döndüren prive (özel) bir metot ekleriz.
c) Private tanımlanmış değişkene hiç bir şekilde ulaşamayız.
d) Sınıf içerisine, ilgili sınıf değişkenini ekrana yazdıran bir metot ekleriz.

**Cevap: a**

> Encapsulation, abstraction’ı gerçekleştirmek için kullanılan bir araçtır.
