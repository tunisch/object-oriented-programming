# Sınıf Diyagram Örnekleri

## Sipariş İşlemleri Sınıf Tasarımı

<img width="1280" height="968" alt="image" src="https://github.com/user-attachments/assets/5ca86b61-424c-43c7-8275-3a43da17632c" />

- 0 veya 1 müşterinin (Customer) en az 1 veya daha fazla siparişi (Order) olabilir.
- Siparişin (Order) ürünü (Product) vardır.
- Stoğun (Stock) ürünü (Product) vardır.

## Banka Yönetim Sistemi Sınıf Tasarımı

<img width="1800" height="1440" alt="image" src="https://github.com/user-attachments/assets/177ed56b-2f8b-4c71-a1fd-109458063c7a" />

- Bankanın (Bank) ATM, Müşteri (Customer), Hesap (Account) sınıfları vardır.
- 1 müşterinin (Customer) en az 1 en çok 2 hesabı (Account) olabilir.
- 1 hesap (Account) 0 veya daha fazla ATM işlemi yapabilir.
- Hesap (Account) sınıfına ait iki tane alt sınıf vardır, Ana Hesap (Main Account) ve Birikim Hesabı (Saving Account).

## Şirket Yönetim Sistemi Sınıf Tasarımı

<img width="1280" height="968" alt="image" src="https://github.com/user-attachments/assets/6095b661-3c0e-413d-9554-da5abf300fbc" />

- Şirketin (Company) 0 veya daha fazla departman (Department) ve ofisi (Office) vardır.
- Şirket (Company) olmadan departman (Department) ve ofis (Office) olamaz.
- Bir departmanın (Department) en az bir çalışanı (Employee) olmalıdır.
- Bir departman (Department) bir çalışan (Employee) tarafından yönetilir.
- Ofise (Office) ait bir merkez ofis (Headquarter) olabilir.

## Okul Yönetim Sistemi Sınıf Tasarımı

<img width="1280" height="560" alt="image" src="https://github.com/user-attachments/assets/b7ea8247-ba0e-4f9f-88b4-e714c93e2fb7" />

- 1 okulun (School) en az bir veya daha fazla departmanı (Department) olabilir.
- En az 1 veya daha fazla okulun (School) birden fazla öğrencisi (Student) olabilir.
- 0 veya daha fazla öğrenci (Student) , en az 1 veya daha fazla ders (Subject) alabilir.
- En az 1 veya daha fazla dersin (Subject), en az 1 veya daha fazla öğretmeni (Instructor) olabilir.
- Bir departmanın (Department) en az 1 veya daha fazla dersi (Subject) olabilir.
- Bir veya daha fazla departmana (Department), 1 veya daha fazla öğretmen (Instructor) atanabilir.

## Sipariş Yönetim Sistemi Sınıf Tasarımı

<img width="1280" height="728" alt="image" src="https://github.com/user-attachments/assets/b8a728f0-8c02-4d63-b4fe-9480e0517c71" />

- Bir müşterinin 0 veya daha fazla siparişi olabilir.
- Bir siparişe ait sipariş detayı ve ürünleri olur.
- 1 siparişin birden fazla ödemesi olabilir.
- Nakit , Çek ve Kredi Kartı ödeme yöntemleridir.

