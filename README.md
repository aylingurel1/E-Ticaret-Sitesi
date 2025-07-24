# E-Ticaret Sitesi

Modern teknolojilerle tasarlanmış kapsamlı bir ASP.NET Core e-ticaret web uygulaması.

## Proje Hakkında Detaylı Bilgi

Bu proje, kullanıcıların çevrimiçi kitap alışverişi yapabildiği tam işlevli bir e-ticaret platformudur. Uygulama, modern web geliştirme standartlarına uygun olarak geliştirilmiş olup, ölçeklenebilir mimari yaklaşımı benimser. Proje, gerçek dünya e-ticaret gereksinimlerini karşılamak üzere tasarlanmış ve hem yönetici hem de müşteri perspektifinden kapsamlı işlevsellik sunar.

Uygulama, kullanıcı dostu arayüzü, güvenli ödeme sistemi altyapısı ve etkili ürün yönetimi özellikleriyle e-ticaret sektöründeki temel ihtiyaçları karşılamayı hedefler.

## Özellikler (Features)
E-Ticaret-Sitesi
### 🔐 Kimlik Doğrulama ve Yetkilendirme

- Kullanıcı kaydı ve güvenli giriş sistemi
- ASP.NET Core Identity entegrasyonu
- Rol tabanlı erişim kontrolü (Admin/Customer)
- Kullanıcı profil yönetimi

### 📚 Ürün Yönetimi

- Detaylı ürün katalogu (kitaplar)
- Kategori bazlı ürün sınıflandırması
- Çoklu fiyat seviyeleri (1-50, 50+, 100+ adet)
- Ürün resmi yükleme ve yönetimi
- TinyMCE ile zengin metin editörü

### 🛒 Alışveriş Deneyimi

- İnteraktif ürün detay sayfaları
- Sepete ürün ekleme sistemi
- Miktar kontrolü ve güncelleme
- Responsive tasarım

### 👨‍💼 Yönetici Paneli

- Kategori yönetimi (CRUD işlemleri)
- Ürün yönetimi (ekleme, düzenleme, silme)
- Şirket bilgileri yönetimi
- Kullanıcı yönetimi
- DataTables ile gelişmiş tablo görünümü

### 🎨 Kullanıcı Arayüzü

- Modern ve responsive Bootstrap tasarımı
- Bootstrap Icons entegrasyonu
- SweetAlert2 ile kullanıcı dostu bildirimler
- Toastr bildirimleri

## Kullanılan Teknolojiler (Tech Stack)

### **Backend Framework**

- **ASP.NET Core 9.0** - Modern web framework
- **Entity Framework Core 9.0** - ORM ve veritabanı işlemleri
- **ASP.NET Core Identity** - Kimlik doğrulama ve yetkilendirme

### **Frontend**

- **Razor Pages** - Server-side rendering
- **Bootstrap 5** - Responsive CSS framework
- **jQuery** - JavaScript kütüphanesi
- **Bootstrap Icons** - Icon kütüphanesi
- **TinyMCE** - Zengin metin editörü

### **Veritabanı**

- **Microsoft SQL Server** - İlişkisel veritabanı
- **Entity Framework Migrations** - Veritabanı sürüm kontrolü

### **Mimari Yaklaşım**

- **Repository Pattern** - Veri erişim katmanı soyutlaması
- **Unit of Work Pattern** - İş birimi yönetimi
- **Area-based Architecture** - Modüler yapı (Admin/Customer/Identity)
- **Layered Architecture** - DataAccess, Models, Utility katmanları

### **Diğer Araçlar ve Kütüphaneler**

- **SweetAlert2** - Modern alert ve onay kutuları
- **Toastr** - Bildirim sistemi
- **DataTables** - Gelişmiş tablo özellikleri
- **IFormFile** - Dosya yükleme

## Kurulum (Installation)

### Gereksinimler

- .NET 9.0 SDK
- Visual Studio 2022 (önerilen) veya Visual Studio Code
- SQL Server (LocalDB veya tam sürüm)

### Adım Adım Kurulum

1. **Projeyi klonlayın**

   ```bash
   git clone https://github.com/aylingurel1/E-Ticaret-Sitesi.git
   cd E-Ticaret-Sitesi
   ```

2. **Bağımlılıkları geri yükleyin**

   ```bash
   dotnet restore
   ```

3. **Veritabanı bağlantı dizesini yapılandırın**

   - `FinalProjesi/appsettings.json` dosyasını açın
   - `ConnectionStrings:DefaultConnection` değerini kendi SQL Server örneğinize göre güncelleyin:

   ```json
   {
     "ConnectionStrings": {
       "DefaultConnection": "Server=(localdb)\\mssqllocaldb;Database=FinalDb;Trusted_Connection=True;MultipleActiveResultSets=true;TrustServerCertificate=True"
     }
   }
   ```

4. **Veritabanını oluşturun ve migrasyonları uygulayın**

   ```bash
   cd FinalProjesi
   dotnet ef database update
   ```

5. **Uygulamayı çalıştırın**

   ```bash
   dotnet run
   ```



## Kullanım (Usage)

### Müşteri Arayüzü

- Ana sayfa: Tüm ürünleri görüntüleyebilir ve kategorilere göre filtreleyebilirsiniz
- Ürün detayları: `Details` butonuna tıklayarak ürün detaylarını görüntüleyebilirsiniz
- Sepete ekleme: Ürün detay sayfasında miktar seçip "Add to Cart" butonuna tıklayın
- Kullanıcı hesabı: Sağ üst köşedeki menüden kayıt olabilir veya giriş yapabilirsiniz

### Yönetici Paneli

- Yönetici girişi yapın
- **Kategori Yönetimi**: `/Admin/Category` - Kategori ekleme, düzenleme ve silme
- **Ürün Yönetimi**: `/Admin/Product` - Ürün ekleme, düzenleme, resim yükleme
- **Şirket Yönetimi**: `/Admin/Company` - Şirket bilgilerini yönetme

### API Endpoints

- `GET /Admin/Product/GetAll` - Tüm ürünleri JSON formatında listeler
- `DELETE /Admin/Product/Delete/{id}` - Belirtilen ID'ye sahip ürünü siler
- `GET /Admin/Company/GetAll` - Tüm şirketleri JSON formatında listeler
- `DELETE /Admin/Company/Delete/{id}` - Belirtilen ID'ye sahip şirketi siler

## Proje Yapısı

```
E-Ticaret-Sitesi/
├── Final.DataAccess/          # Veri erişim katmanı
│   ├── Data/                  # DbContext ve veritabanı yapılandırması
│   ├── Migrations/            # Entity Framework migrasyonları
│   └── Repository/            # Repository pattern implementasyonu
├── Final.Models/              # Domain modelleri ve ViewModels
├── Final.Utility/             # Yardımcı sınıflar ve sabitler
├── FinalProjesi/              # Ana web uygulaması
│   ├── Areas/
│   │   ├── Admin/            # Yönetici paneli
│   │   ├── Customer/         # Müşteri arayüzü
│   │   └── Identity/         # Kimlik doğrulama sayfaları
│   ├── Views/                # Shared görünümler
│   └── wwwroot/              # Statik dosyalar (CSS, JS, resimler)
└── README.md
```

## Katkıda Bulunma (Contributing)

Bu projeye katkıda bulunmak isterseniz:

1. Bu repository'yi fork edin
2. Yeni bir feature branch oluşturun (`git checkout -b feature/YeniOzellik`)
3. Değişikliklerinizi commit edin (`git commit -am 'Yeni özellik: açıklama'`)
4. Branch'inizi push edin (`git push origin feature/YeniOzellik`)
5. Pull Request oluşturun

### Geliştirme Kuralları

- Clean Code prensiplerine uyun
- Unit testler ekleyin (mümkünse)
- Commit mesajlarını açıklayıcı yazın
- Code review sürecine katılın

## Lisans (License)

Bu proje MIT Lisansı ile lisanslanmıştır. Detaylar için `LICENSE` dosyasına bakın.

## Gelecek Özellikler

- [ ] Ödeme sistemi entegrasyonu
- [ ] Sipariş takip sistemi
- [ ] E-posta bildirimleri
- [ ] Ürün yorumları ve değerlendirmeleri
- [ ] Wishlist (İstek listesi) özelliği
- [ ] Çoklu dil desteği
- [ ] Mobil uygulama API'si

---
