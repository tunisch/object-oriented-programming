# Programlama Paradigmaları

- Paradigma, bir bilim dalında zihinsel bir resmin, gerçekliğin algılanması, kavramsallaştırılmasını sağlayan modele denir. Programlama aleminde ise problemlere üretilen çözümlerin nasıl formül haline getirileceği ile alakalı olan temel programlama stilidir.
- Programlama paradigmaları hangi yolla çözümlere ulaştıklarının yanında hangi yolları yasakladıklarıyla da bilinirler. Örneğin sadece fonksiyonel paradigmayı esas alan bir dil yan etkilerin kullanılmasını yasaklar.

> **Bu belgeyi nasıl okumalıyım? (Başlangıç Zihinsel Model)**
>
> Eğer şu an kafanda net bir şekil oluşmadıysa sorun sende değil. Paradigmalar genelde **çok erken anlatılır, çok soyut kalır**. Bu yüzden buraya ekstra bir "neden / ne zaman" katmanı ekliyoruz.
>
> Şunu bilerek oku:
>
> * Paradigma = "Bu problemi hangi bakış açısıyla çözeceğim?"
> * Dil = "Bu bakış açısını hangi kelimelerle anlatacağım?"

---

## 0. En Başta Şu Soruyu Sor

> **"Ben şu an ne yapıyorum?"**

* Hesap mı yapıyorum?
* Gerçek dünyadaki bir şeyi mi modelliyorum?
* Olaylara mı tepki veriyorum?
* Veriyi mi dönüştürüyorum?

Paradigma seçimi bu sorunun cevabından doğar.

---

## 0.1 Paradigmaları Tek Cümlelik Akılda Kalıcı Tanımlar

* **Procedural** → "Adım adım ne yapacağımı anlatırım"
* **OOP** → "Gerçek dünyadaki şeyleri nesne olarak düşünürüm"
* **Functional** → "Veriyi alırım, dönüştürürüm, geri veririm"
* **Event-driven** → "Bir şey olunca tepki veririm"
* **Logic** → "Kuralları söylerim, çözümü sistem bulur"

---

## 0.2 Aynı Problem, İki Farklı Düşünme (OOP’ye Geçiş Köprüsü)

Bu bölüm **özellikle OOP öncesi** kafada şekil oluşması için eklendi.

### Problem Tanımı

"Bir oyunda savaşçılar var. Her savaşçının canı ve saldırı gücü var. Birbirlerine vurabiliyorlar."

---

### Procedural (Yapısal) Düşünme

Burada zihnin şunu yapar:

> "Ben işlemleri anlatacağım. Kim vurdu, ne kadar can düştü, onu kontrol edeceğim."

Zihinsel akış:

```
can = 100
hasar = 20
can = can - hasar
if can <= 0 → öldü
```

Bu yaklaşım:

* algoritmayı öğretir
* kontrolü tamamen sende tutar
* küçük problemler için hızlıdır

Ama büyüdükçe şunu hissedersin:

> "Her şey birbirine girmeye başladı"

---

### OOP (Nesne Yönelimli) Düşünme

Burada zihinde **kritik kırılma** olur:

> "Aslında ben can ve hasarla değil, **Savaşçı** ile uğraşıyorum"

Zihinsel dönüşüm:

```
Savaşçı
 ├─ can
 ├─ hasar
 └─ vur()
```

Artık sen şunu söylersin:

* Can, savaşçının özelliği
* Vurmak, savaşçının davranışı

Yani:

> "Veri + davranış = aynı yerde"

Bu OOP’nin kalbidir.

---

### Ne Zaman Hangisi Mantıklı?

* Küçük hesaplar → Procedural
* Gerçek dünya varlıkları → OOP
* Sistem büyüyorsa → OOP kaçınılmaz olur

---

### Patika’daki OOP Dersini Okurken Şunu Düşün

> "Bu class, gerçek hayatta **neyin karşılığı**?"

Bu soruyu soruyorsan, OOP doğru yere oturmaya başlamıştır.

---

* **Procedural** → "Adım adım ne yapacağımı anlatırım"
* **OOP** → "Gerçek dünyadaki şeyleri nesne olarak düşünürüm"
* **Functional** → "Veriyi alırım, dönüştürürüm, geri veririm"
* **Event-driven** → "Bir şey olunca tepki veririm"
* **Logic** → "Kuralları söylerim, çözümü sistem bulur"

Bunları ezberleme. Bir süre sonra refleks haline gelir.

---

## 1. Paradigma Nedir?

Paradigma, bir problemi **nasıl düşündüğümüzü**, **nasıl parçalara ayırdığımızı** ve **nasıl çözdüğümüzü** belirleyen zihinsel çerçevedir. Programlama dünyasında paradigma, sadece “nasıl kod yazılır?” sorusuna değil, aynı zamanda:

* Ne yapılabilir?
* Ne yapılması **önerilmez** ya da **yasaklanır**?
* Programın kontrolü kimdedir (fonksiyon mu, nesne mi, veri mi)?

sorularına verilen cevaptır.

> Kısa metafor: Paradigma = Harita. Kod = O haritayla yürüdüğün yol.

---

## 2. Paradigmalar Neden Önemlidir?

* Aynı problem farklı paradigmalarla **farklı şekillerde** çözülür
* Kodun:

  * okunabilirliği
  * bakımı
  * test edilebilirliği
  * performansı
    doğrudan etkilenir
* Senior seviyeye giden yol, **birden fazla paradigmayı doğru yerde kullanabilmekten** geçer

---

## 3. Programlama Paradigmalarının Genel Sınıflandırması

```
Programlama Paradigmaları
│
├─ Imperative (Buyrukçu)
│   ├─ Procedural (Yapısal)
│   └─ Object-Oriented (Nesne Yönelimli)
│
├─ Declarative (Bildirimsel)
│   ├─ Functional (Fonksiyonel)
│   └─ Logic (Mantıksal)
│
└─ Diğer / Hibrit
    ├─ Event-Driven
    ├─ Concurrent / Parallel
    └─ Aspect-Oriented
```

---

## 4. Imperative (Buyrukçu) Paradigma

### Temel Fikir

"Bilgisayara **nasıl** yapacağını adım adım söyle."

* Değişkenler vardır
* State (durum) değişir
* Döngüler ve koşullar merkezde

### Basit Şema

```
Başla
  ↓
Değişken Tanımla
  ↓
Döngü
  ↓
Koşul Kontrolü
  ↓
Bitir
```

### Kullanılan Diller

* C
* Python
* Java
* C#

### Beginner Seviyesi

* for / while
* if / else
* değişkenler

### Mid Developer Seviyesi

* yan etkilerin (side effect) farkında olmak
* state yönetimini sadeleştirmek
* fonksiyonları küçük ve test edilebilir yazmak

---

## 5. Procedural (Yapısal) Paradigma

> Imperative paradigmanın alt kümesidir.

### Temel Fikir

"Program = Fonksiyonlar + Veri"

### Özellikler

* Kod fonksiyonlara bölünür
* Global state riski vardır
* Veri ve davranış ayrı tutulur

### Şema

```
main()
 ├─ fonksiyon1()
 ├─ fonksiyon2()
 └─ fonksiyon3()
```

### Kullanılan Diller

* C
* Pascal
* Python (procedural yazılabilir)

### Beginner için

* algoritma mantığını anlamak için idealdir

### Mid için

* modülerlik
* tekrar eden kodu soyutlama

---

## 6. Object-Oriented Programming (OOP)

### Temel Fikir

"Program = Nesnelerin etkileşimi"

### 4 Temel İlke

1. Encapsulation (Kapsülleme)
2. Abstraction (Soyutlama)
3. Inheritance (Kalıtım)
4. Polymorphism (Çok biçimlilik)

### Şema

```
Class Araba
 ├─ hiz
 ├─ renk
 ├─ calistir()
 └─ durdur()
```

### Kullanılan Diller

* Java
* C#
* C++
* Python

### Beginner için

* class / object
* constructor
* method

### Mid Developer için

* SOLID prensipleri
* composition > inheritance
* design patterns (Factory, Strategy, Observer)

---

## 7. Declarative (Bildirimsel) Paradigma

### Temel Fikir

"Ne istediğini söyle, **nasıl** yapılacağını sistem düşünsün"

### Şema

```
Ne istiyorum?
  ↓
Sistem nasıl yapacağını çözer
```

### Alt Türler

* Functional
* Logic
* SQL

---

## 8. Functional Programming (FP)

### Temel Fikir

* Fonksiyonlar saf olmalı
* State değişmemeli (immutability)
* Yan etki minimum

### Temel Kavramlar

* Pure Function
* Higher-Order Function
* Map / Filter / Reduce

### Şema

```
Input → Function → Output
(State değişmez)
```

### Kullanılan Diller

* Haskell
* Scala
* JavaScript
* Python

### Beginner için

* map, filter
* lambda

### Mid Developer için

* immutability
* side effect izolasyonu
* FP + OOP birlikte kullanma

---

## 9. Logic Programming

### Temel Fikir

"Kuralları yaz, sonuçları sistem bulsun"

### Şema

```
Gerçekler
Kurallar
  ↓
Sorgu
  ↓
Cevap
```

### Kullanılan Diller

* Prolog

### Kullanım Alanları

* yapay zeka
* expert systems

---

## 10. Event-Driven Paradigma

### Temel Fikir

"Bir olay olur, ona tepki verilir"

### Şema

```
Event
 ↓
Listener
 ↓
Handler
```

### Kullanılan Alanlar

* GUI
* Web
* IoT

### Diller

* JavaScript
* Java
* C#

---

## 11. Beginner vs Mid Developer Özet Tablosu

| Seviye   | Odak                               |
| -------- | ---------------------------------- |
| Beginner | Syntax, döngüler, class mantığı    |
| Mid      | Paradigma seçimi, clean code, test |
| Senior   | Hibrit yaklaşım, mimari kararlar   |

---

## 12. Gerçek Hayat Analojisi

* Procedural → Yemek tarifi
* OOP → Mutfak ekipmanları
* Functional → Matematik fonksiyonu
* Event-driven → Kapı zili

---

## 13. Sonuç

Paradigma öğrenmek, yeni bir dil öğrenmekten daha değerlidir. Çünkü diller değişir, **düşünme biçimi kalır**. İyi yazılımcı tek paradigma bilmez; doğru problemi doğru paradigma ile çözer.

> Paradigmalar rakip değil, araçtır.
