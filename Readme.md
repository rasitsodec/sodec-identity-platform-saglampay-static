# Sodec Identity Platform - Saglampay Static

Bu proje, Sodec Identity Platform'un Saglampay Static bileşenini içerir. iOS uygulamaları için geliştirilmiş statik bir kimlik doğrulama ve belge tarama framework'üdür.

## 📋 Proje Hakkında

### 🎯 Amaç
- iOS uygulamalarında statik kimlik doğrulama işlemlerini kolaylaştırmak
- Belge tarama ve OCR işlemlerini desteklemek
- Biyometrik doğrulama entegrasyonu sağlamak
- Güvenli kimlik doğrulama süreçleri sunmak

### 🏗️ Teknolojiler
- **Platform**: iOS (ARM64 + x86_64 Simulator)
- **Framework**: SAMobileCapture.xcframework
- **Dil**: Swift + Objective-C
- **AI/ML**: TensorFlow Lite modelleri
- **OCR**: Latin karakter desteği
- **Biyometrik**: Face detection ve recognition

## 📦 Kurulum

### CocoaPods ile Kurulum

```ruby
# Podfile
pod 'SAMobileCapture', :path => './SAMobileCapture.xcframework'
```

### Manuel Kurulum

1. `SAMobileCapture.xcframework` dosyasını projenize ekleyin
2. Framework'ü target'ınıza link edin
3. Gerekli izinleri `Info.plist`'e ekleyin:

```xml
<key>NSCameraUsageDescription</key>
<string>Kimlik doğrulama için kamera erişimi gereklidir</string>
<key>NSFaceIDUsageDescription</key>
<string>Biyometrik doğrulama için Face ID erişimi gereklidir</string>
```

## 🚀 Kullanım

### Temel Kullanım

```swift
import SAMobileCapture

// Framework'ü başlat
let config = SAConfig()
config.apiKey = "your-api-key"
config.baseURL = "https://api.sodec.com"

// Statik belge tarama
let documentCapture = SACaptureDocument()
documentCapture.delegate = self
documentCapture.startCapture()

// Selfie çekme
let selfieCapture = SACaptureSelfie()
selfieCapture.delegate = self
selfieCapture.startCapture()
```

### Desteklenen Belge Türleri

- 🇹🇷 **Türk Kimlik Kartı**
- 🇹🇷 **Türk Pasaportu**
- 🇹🇷 **Türk Ehliyeti**
- 🌍 **Uluslararası Pasaportlar**
- 📄 **Diğer Resmi Belgeler**

## 🔧 Özellikler

### ✅ Kimlik Doğrulama
- Statik belge tarama ve OCR
- Yüz tanıma ve karşılaştırma
- Biyometrik doğrulama
- Liveness detection

### ✅ Güvenlik
- Şifreli iletişim
- Güvenli veri saklama
- GDPR uyumluluğu
- Audit logging

### ✅ Kullanıcı Deneyimi
- Türkçe arayüz
- Kolay kullanım
- Hızlı işlem
- Offline çalışma

## 📁 Proje Yapısı

```
SAMobileCapture.xcframework/
├── ios-arm64/
│   └── SAMobileCapture.framework/
│       ├── Headers/           # API header dosyaları
│       ├── Resources/         # Kaynak dosyaları
│       └── SAMobileCapture    # Ana framework
├── ios-x86_64-simulator/
│   └── SAMobileCapture.framework/
│       ├── Headers/           # Simulator header'ları
│       ├── Resources/         # Simulator kaynakları
│       └── SAMobileCapture    # Simulator framework
└── Info.plist                 # Framework bilgileri
```

## 🔄 CI/CD Pipeline

Bu proje Bitbucket Pipeline ile GitHub'a otomatik sync edilir:

### Pipeline Özellikleri
- ✅ **Otomatik GitHub Sync**: Main branch'e push → GitHub'a sync
- ✅ **Tag Sync**: Yeni tag → GitHub'a otomatik push
- ✅ **Git LFS Desteği**: Büyük dosyalar verimli yönetim
- ✅ **Hata Kontrolü**: Güvenli push işlemleri

### Repository Mapping
- **Bitbucket**: `sodec/sodec-identity-platform-saglampay-static`
- **GitHub**: `rasitsodec/sodec-identity-platform-saglampay-static`

## 📊 Versiyonlar

| Versiyon | Tarih | Açıklama |
|----------|-------|----------|
| 1.0.0 | 2025-08-07 | İlk release |

## 🤝 Katkıda Bulunma

1. Fork yapın
2. Feature branch oluşturun (`git checkout -b feature/amazing-feature`)
3. Değişikliklerinizi commit edin (`git commit -m 'Add amazing feature'`)
4. Branch'inizi push edin (`git push origin feature/amazing-feature`)
5. Pull Request oluşturun

## 📞 Destek

- **Email**: rasit.ulcay@sodec.com
- **Dokümantasyon**: [Sodec Developer Portal](https://developer.sodec.com)
- **Issues**: GitHub Issues kullanın

## 📄 Lisans

Bu proje Sodec şirketi tarafından geliştirilmiştir. Tüm hakları saklıdır.

---

**Geliştirici**: Raşit ÜLCAY  
**Şirket**: Sodec  
**Tarih**: Ağustos 2025 