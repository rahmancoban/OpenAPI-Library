# OpenAPI Tasarımı Ödevi Teslim Raporu

## 👤 Öğrenci Bilgileri

- **Ad Soyad**: Abdurrahman Coban
- **Öğrenci Numarası**: 170422851

---

## 📂 OpenAPI YAML Dosyası

- **openapi.yaml** dosyasını projenizin GitHub reposuna yükleyiniz.
- Swagger Editor ile test ettiğinizden emin olunuz.

### 🔗 GitHub Repo Linki

[https://github.com/kullanici-adi/kutuphane-api](https://github.com/kullanici-adi/kutuphane-api)

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
