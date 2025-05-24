# OpenAPI Tasarımı Ödevi Teslim Raporu

## 👤 Öğrenci Bilgileri

- **Ad Soyad**: Abdurrahman Coban
- **Öğrenci Numarası**: 170422851

---

## 📂 OpenAPI YAML Dosyası

- **openapi.yaml** dosyasını projenizin GitHub reposuna yükleyiniz.
- Swagger Editor ile test ettiğinizden emin olunuz.

### 🔗 GitHub Repo Linki

https://github.com/rahmancoban/OpenAPI-Library

---

## 📝 API Açıklaması

- **Varlıklar**: `books`, `students`, `loans`
- Her varlık için `GET`, `POST`, `PUT`, `DELETE` gibi CRUD işlemleri endpoint olarak tanımlandı.
- `components/schemas` ile tüm veri modelleri belirtildi.
- `parameters` içinde `path` ve `query` parametreleri kullanıldı (`page`, `size`, `id`).
- `responses` içinde `200`, `201`, `400`, `404` yanıtları tanımlandı.
- `GET /books` için sayfalama parametreleri kullanıldı.
- `POST /books` için örnek `example` eklendi.
- `description` ve `tags` alanları ile açıklamalar sağlandı.

----------- ACIKLAMA ------------
Bu API, bir üniversiteye ait çevrim içi kütüphane sistemini modellemek amacıyla tasarlanmıştır. Üç ana varlık bulunmaktadır:

Books: Kütüphanedeki kitapların bilgilerini içerir. Her kitap, başlık, yazar, ISBN, yayıncı, sayfa sayısı ve stok bilgisine sahiptir.

Students: Kütüphane sistemine kayıtlı öğrencileri tanımlar. Her öğrenciye ait ad, öğrenci numarası, e-posta ve aktiflik durumu bilgisi tutulur.

Loans: Kitap ödünç alma süreçlerini temsil eder. Öğrencinin hangi kitabı, ne zaman aldığını ve ne zaman iade ettiğini gösterir. Durum alanı ongoing, returned veya late olabilir.

CRUD Endpoint’leri:
Tüm varlıklar için GET, POST, PUT, DELETE işlemleri desteklenmektedir.

loans için PATCH /loans/{id}/return ile iade işlemi yapılabilmektedir.

Kullanılan OpenAPI Bileşenleri:
components/schemas: Tüm varlıkların veri modelleri tanımlanmıştır.

parameters: path ve query parametreleri kullanılmıştır (örneğin: id, page, size).

requestBody: POST ve PUT işlemlerinde zorunlu, uygun format, enum ve required alanlarla birlikte kullanılmıştır.

responses: 200, 201, 400, 404 ve 500 durum kodlarına ait örnek yanıtlar tanımlanmıştır.

example: Bazı endpointlerde örnek istek ve yanıtlar gösterilmiştir.

description ve tags: API genelinde açıklayıcı alanlar ve kategoriler eklenmiştir.

sayfalama: GET /books endpointinde page ve size query parametreleri ile desteklenmektedir.

---

## 🧪 Test Notları (Opsiyonel)

- `GET /books` çağrısı, örnek kitap listesi döner.
- `POST /students`:

  ```json
  {
    "id": "e123e4567-e89b-12d3-a456-426614174001",
    "name": "Ali Yılmaz",
    "studentNumber": "20211234",
    "email": "ali.yilmaz@example.com",
    "isActive": true
  }
  ```

  --------- TEST NOTLARI -----------
  Swagger Editor (https://editor.swagger.io) üzerinde testler gerçekleştirilmiştir. Test senaryoları aşağıdaki gibidir:

GET /books: Sayfalama parametreleriyle (page=1&size=10) test edildi. Dönüş değeri, kitap listesi ve toplam sonuç sayısını içermektedir.

POST /students: Geçerli veriyle öğrenci kaydı başarıyla oluşturuldu. Örnek requestBody:

json
Kopyala
Düzenle
{
"id": "b15cf46b-2d39-4f4c-9a14-58b13c41f014",
"name": "Ayşe Yılmaz",
"studentNumber": "20231234",
"email": "ayse@example.com",
"isActive": true
}
PATCH /loans/{id}/return: Bir kitap iade edildiğinde, status alanı "returned" olarak güncellendi.

POST /books: Eksik title alanı gönderildiğinde 400 Bad Request hatası doğru şekilde döndü.

GET /students/{id}: Geçersiz UUID formatı ile istek yapıldığında 400 hatası alındı.
