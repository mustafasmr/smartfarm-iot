# SmartFarm IoT — Otonom Akıllı Tarım İzleme ve Sulama Sistemi (6 Kişilik Bitirme Projesi)

Doğu Akdeniz Üniversitesi (DAÜ / EMU) **Bilişim Sistemleri ve Teknolojileri** lisans bitirme projesi (6 kişilik ekip / Capstone Project) kapsamında geliştirilen; **ESP32**, **MQTT**, **Firebase** ve **TOTP MFA (RFC 6238)** tabanlı otonom tarım izleme ve kontrol sistemidir.

- 📄 **Bitirme Projesi Sunumu (PDF):** [SmartFarm_Sunum.pdf](https://mustafasumer.com/assets/docs/SmartFarm_Sunum.pdf)

## Sistem Mimarisi

```text
[Toprak Nemi / Sıcaklık / Nem Sensörleri]
                  │
                  ▼
         [ESP32 Mikrodenetleyici]
                  │  (MQTT Pub/Sub)
                  ▼
          [MQTT Broker / Bulut]
                  │
        ┌─────────┴─────────┐
        ▼                   ▼
[Firebase Realtime DB]  [Otomatik Sulama Rölesi]
        │
        ▼
 [TOTP MFA Doğrulamalı Web İzleme Paneli]
```

## Temel Özellikler

- **Gerçek Zamanlı Sensör Telemetrisi:** ESP32 üzerinden toprak nemi, ortam sıcaklığı ve bağıl nem verilerinin MQTT protokolü ile düşük gecikmeli aktarımı.
- **Otonom Sulama Kontrolü:** Eşik değerlere göre otomatik pompa/röle tetikleme ve manuel uzaktan müdahale desteği.
- **Güvenli Erişim (TOTP MFA — RFC 6238):** Yönetim paneli erişiminde zaman tabanlı tek kullanımlık doğrulama desteği.
- **Bulut Kayıt (Firebase):** Tarihsel sensör kayıtlarının ve sistem durumlarının Firebase Realtime Database üzerinde tutulması.
