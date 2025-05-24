# 📘 OpenAPI Kütüphane Sistemi

Bu proje, bir üniversiteye ait çevrim içi kütüphane sisteminin RESTful API tanımını içermektedir. API tasarımı **OpenAPI 3.0** spesifikasyonuna uygun şekilde hazırlanmıştır.

## 🎯 Projenin Amacı

Bu API, aşağıdaki üç temel varlık (entity) üzerinden kitap ödünç alma sistemini tanımlar:

- **Books**: Kütüphanedeki kitapları temsil eder.
- **Students**: Sisteme kayıtlı öğrencileri temsil eder.
- **Loans**: Kitap ödünç alma işlemlerini temsil eder.

## 🔗 Endpoint Özeti

### Books

- `GET /books`: Tüm kitapları listeler (sayfalama destekli)
- `GET /books/{id}`: Belirli bir kitabın bilgisi
- `POST /books`: Yeni kitap ekleme
- `PUT /books/{id}`: Kitap güncelleme
- `DELETE /books/{id}`: Kitap silme

### Students

- `GET /students`
- `GET /students/{id}`
- `POST /students`
- `PUT /students/{id}`
- `DELETE /students/{id}`

### Loans

- `GET /loans`
- `GET /loans/{id}`
- `POST /loans`: Kitap ödünç alma
- `PATCH /loans/{id}/return`: Kitap iade etme

## 🧱 Teknik Detaylar

- **Spesifikasyon**: OpenAPI 3.0
- **Dosya Adı**: `openapi.yaml`
- **Yapılar**: `components/schemas`, `parameters`, `responses`, `requestBody`, `securitySchemes`
- **Sayfalama**: `GET /books` endpointinde `page` ve `size` query parametreleriyle
- **Validasyon**: UUID, email, ISBN-13, enum, date formatlarıyla veri doğrulama
- **Örnekler**: Örnek istek ve yanıtlar belirli endpointlerde tanımlanmıştır

## 🛠️ Test

Swagger Editor kullanılarak test edilmiştir. Aşağıdaki bağlantı ile test edebilirsiniz:

🔗 https://editor.swagger.io

1. `File > Import File` diyerek `openapi.yaml` dosyasını yükleyin.
2. Arayüzden tüm endpointleri deneyimleyebilirsiniz.

## 📁 Dosya Yapısı

- **/**
- **├── openapi.yaml # API tanımı (OpenAPI 3.0)**
- **├── README.md # Bu açıklama dosyası**
- **└── DELIVERY.md # Ödev teslim format dosyası**
