# Realtor Mobil Uygulaması – İş Analizi Vaka Çalışması

Bu repository, emlak ofisi çalışanlarının kullanımına yönelik geliştirilen bir mobil uygulama için hazırlanmış uçtan uca bir İş Analizi (Business Analysis) vaka çalışmasını içermektedir.

Proje; müşteri, mülk, sözleşme, satış/kiralama işlemleri ve satıcı talebine bağlı kredi notu sorgulama ve kontroller süreçlerini kapsamakta olup kapsam tanımı, iş kuralları, süreç akışları, use case’ler, ekran eşleştirmeleri, veri modeli ve sistem entegrasyonları detaylı şekilde dokümante edilmiştir.

---

## Proje Amacı

Bu projenin amacı, emlak ofisi çalışanlarının müşterileri, mülkleri ve satış/kiralama süreçlerini kontrollü ve izlenebilir bir şekilde yönetebileceği bir mobil uygulamanın iş analizi sürecini uçtan uca tasarlamak ve dokümante etmektir.

Proje kapsamı ve üst seviye özet bilgiler 01_Project_Overview klasörü altında yer almaktadır.

---

## Kapsam Tanımı

### Kapsam Dahilinde
- Mobil uygulamanın yalnızca emlak ofisi çalışanları tarafından kullanılması
- Müşteri kayıtlarının oluşturulması, aranması ve güncellenmesi
- TC kimlik numarası ve GSM bilgisi ile müşteri tekilleştirme
- Satılık ve kiralık mülk kayıtlarının yönetilmesi
- Satıcı ile ofis arasında dijital sözleşme oluşturulması
- Kapora ile satış ve kiralama işlemlerinin başlatılması
- Satış ve kiralama süreçlerinin sözleşme, işlem ve komisyon adımlarıyla takip edilmesi
- Satıcı talebi halinde KKB kredi notu sorgulaması yapılması
- SMS OTP ile sözleşme onayı alınması
- Satış sonrası mülk sahibinin otomatik güncellenmesi

### Kapsam Dışında
- Müşterilerin uygulamaya doğrudan erişimi
- Web veya masaüstü uygulama geliştirilmesi
- Sözleşme içeriklerinin hukuki olarak hazırlanması veya yorumlanması
- Faturalandırma, ödeme ve muhasebe işlemleri
- Banka kredisi başvurusu ve finansman süreçleri
- Satış sonrası hizmetler (sigorta, taşınma vb.)
- Farklı emlak ofisleri veya şubeler arası veri paylaşımı

---

## İş Kuralları

- Her mülk aynı anda yalnızca bir aktif sözleşmeye sahip olabilir
- Sözleşmesi olmayan mülkler satışa veya kiralamaya açılamaz
- İşlem kaydı yalnızca kapora yatırıldıktan sonra başlatılabilir
- Kiralama işlemlerinde komisyon sadece kiracıdan alınır
- Satış işlemlerinde komisyon hem alıcıdan hem satıcıdan alınır
- Satış tamamlandığında mülkün yeni sahibi sistemde otomatik güncellenir
- Kredi notu sorgulamaları yalnızca KKB entegrasyonu üzerinden ve satıcı talebiyle yapılır
- Kredi notu sorguları 24 saat süreyle geçerlidir
- Bir mülke birden fazla müşteri ilgilenen olarak eklenebilir, ancak işlem yalnızca bir müşteriyle başlatılabilir
- Müşteri tekilleştirmesi TC kimlik numarası ve GSM bilgisiyle yapılır
- Sözleşme onayları SMS OTP yöntemi ile gerçekleştirilir
- Uygulama aktif internet bağlantısı gerektirir

---

## Fonksiyonel Kırılım

### F1 – Ofis ve Kullanıcı Yönetimi
- Ofis bilgileri kaydı
- Ofis çalışanı kullanıcı hesaplarının oluşturulması
- Kullanıcı girişi ve kimlik doğrulama
- Kullanıcı yetki ve rol yönetimi
- Şifre sıfırlama ve destek erişimi

### F2 – Müşteri Yönetimi
- Müşteri kaydı oluşturma
- TC ve GSM ile kimlik doğrulama ve tekilleştirme
- Müşteri tipi belirleme (alıcı, satıcı, kiracı, kiraya veren)
- Müşteri arama ve güncelleme işlemleri

### F3 – Mülk ve Sözleşme Yönetimi
- Mülk kaydı oluşturma ve güncelleme
- Mükerrer mülk kontrolü
- Satıcı–ofis sözleşmesi oluşturma
- Sözleşme belge yükleme ve yönetimi
- Tek aktif sözleşme kuralı kontrolü
- Sözleşme bitiş takibi ve yenileme uyarıları

### F4 – Arama ve Eşleştirme İşlemleri
- Müşteri taleplerine göre mülk arama
- Filtreleme ve mülk detay görüntüleme
- Mülk–müşteri eşleştirme
- İlgilenen müşteri kayıtlarının yönetimi

### F5 – Satış ve Kiralama İşlemleri
- Kapora yatırıldığında işlem başlatma
- Satış işlemi süreci (sözleşme → satış → komisyon)
- Kiralama işlemi süreci (sözleşme → kiralama → komisyon)
- Satış veya kiralama sonrası mülk durumunun güncellenmesi

### F6 – Kredi Notu ve Doğrulama İşlemleri
- KKB kredi notu sorgulama
- Minimum kredi notu belirleme ve kontrol
- Son 24 saat kredi sorgusu kontrolü
- Kredi sorgu maliyetinin komisyonda tahsili
- SMS OTP ile sözleşme onayı
- Kimlik ve yetki doğrulama servisleri

---

## Use Case Tasarımı

Sistem için tanımlanan use case’ler, kullanıcı ve sistem etkileşimlerini ele almaktadır.

Use case’ler; aktörler, ön koşullar, tetikleyici olay, ana akış, alternatif akışlar, istisna durumları ve son durum koşullarını içerecek şekilde yapılandırılmıştır.

Detaylı ana akış, alternatif ve istisna senaryolarını örneklemek amacıyla UC02 detaylandırılmıştır.


## Ekranlar ve Screen Flow

Uygulama içerisindeki tüm kullanıcı etkileşimleri ekran bazında tanımlanmıştır.

- Müşteri Kayıt Ekranı  
- Mülk Kayıt Ekranı  
- Sözleşme Oluşturma ve Belge Yükleme Ekranı  
- Kapora İşlem Ekranı  
- Satış / Kiralama Ekranı  
- Kredi Notu Sorgulama Ekranı  
- Kimlik Doğrulama Ekranı  
- SMS OTP Onay Ekranı  
- Uyarı ve Hata Mesajları Ekranı  

Ekranlar arası geçişler screen flow diyagramları ile gösterilmiştir.

---

## Veri Modeli ve Durum Yönetimi

Projede veri modeli ve durum geçişleri tanımlanmıştır.

- Temel varlıklar: Müşteri, Mülk, Sözleşme, Kredi Notu Sorgu, OTP Onay
- Sözleşme durumları: Taslak, OTP Bekleniyor, Aktif, Tamamlandı, İptal
- Mülk durumları: Satışa Açık, Sözleşmede, Satıldı, Kiralandı

---

## Sistem Mimarisi ve Entegrasyonlar

Mobil uygulama, harici sistemlerle gerçek zamanlı web servis entegrasyonları üzerinden çalışmaktadır.

- KKB Kredi Notu Sorgulama Sistemi
- SMS OTP Doğrulama Servisi
- Kimlik ve Yetki Doğrulama Servisi

---

## Rol ve Sorumluluk

Bu projedeki tüm iş analizi çalışmaları uçtan uca İş Analisti rolü kapsamında gerçekleştirilmiştir.

## Kullanılan Araçlar

- Microsoft Excel
- BPMN diyagramları
- Draw.io

