# 🇹🇷 Arch Linux DE & Uygulama Kurulum ve Yapılandırma Betiği (installarchde)

Bu betik, şahsi kişisel ihtiyaçlardan dolayı oluşturulmuş olup, masaüstü ortamlarını, sürücüleri, uygulamaları ve system yapılandırmalarını **interaktif** bir Terminal Kullanıcı Arayüzü (TUI) aracılığıyla kurmak ve yönetmek için tasarlanmıştır.

`dialog` aracı kullanılarak oluşturulan menüler, kurulum sürecini daha az karmaşık hale getirir.

---

## 🚨 Önemli Uyarı: Önyükleyici Desteği

Betik içerisindeki bazı kritik system yapılandırmaları, özellikle **Takas (Swap) Dosyası Ayarları** ve **Hazırda Bekleme (Hibernation)** işlemleri, **systemd-boot** önyükleyicisi için tasarlanmıştır.

> ⚠️ **GRUB KULLANICILARI İÇİN UYARI:** Betikte yer alan çekirdek parametresi ayarlamalarının (örneğin, `swap_file_config` fonksiyonu) GRUB önyükleyicisinde otomatik olarak uygulanması şimdilik **desteklenmemektedir**. GRUB kullanıyorsanız, bu ayarları **elle** yapılandırmanız gerekecektir.

---

## ✨ Özellikler

Betiğin ana menüsü (`mainmenu`) altında sunulan temel işlevler şunlardır:

* **Güncelleme:** System ve AUR paketlerini güncelleme, packet önbelleğini temizleme, gereksiz bağımlılıkları kaldırma ve Pacman yapılandırma dosyalarını düzenleme.
* **Kurulum:** Grafik sürücüleri (**AMD, NVIDIA**), **ASUS ROG/TUF** araçları, ses sistemi (**Pipewire**), uygulamalar, yazı tipleri, temalar ve **Masaüstü Ortamları/Pencere Yöneticileri** kurulumu.
* **Yapılandırma:** **Dotfile'ları** yönetme (kopyalama/sembolik bağlama), ağ, swap/hazırda bekleme (hibernation) ve DDCI gibi özel system ayarlarını uygulama.

---

## ⚙️ Gereksinimler

Betiğin doğru şekilde çalışması için aşağıdaki koşulların sağlanması gerekir:

1.  **Arch Linux:** Betik yalnızca Arch Linux veya Arch tabanlı dağıtımlarda (Pacman packet yöneticisi ve AUR kullanımı nedeniyle) çalışacak şekilde tasarlanmıştır.
2.  **Kullanıcı Yetkisi:** Betiğin **root olmayan bir kullanıcı** (`sudo` yetkisi olan) tarafından çalıştırılması gerekir. Betik, güvenliği sağlamak için root olarak çalıştırılmasını engeller.
3.  **Temel Araçlar:** `git`, `dialog`, `neovim`, `xdg-user-dirs` gibi temel bağımlılıklar betik tarafından otomatik olarak kontrol edilir ve eksik olanlar kurulur.

---

## 🚀 Kurulum ve Kullanım

Betiği kullanmak için öncelikle depoyu klonlayın ve çalıştırma izni verin:

```bash
# 1. Depoyu klonlayın
git clone https://github.com/drpars/installarchde
cd installarchde

# 2. Betiğe çalıştırma izni verin
chmod +x installarchde

# 3. Betiği başlatın (Ana Menü)
./installarchde
```

---

## 🧪 Fonksiyon Modunda Çalıştırma ve Test Edilebilirlik

Betiğin modüler yapısı sayesinde, betik içinde tanımlanmış her bir kurulum veya yapılandırma fonksiyonu (amddriver, swap_file_config, vb.) bağımsız olarak çalıştırılabilir ve test edilebilir.

## Betik içerisindeki tüm fonksiyonları görme ve Çalıştırma :

```bash
grep '() {' installarchde | grep -vE '^\s*#' | sed 's/().*//'
```

```bash
./installarchde [FONKSIYON_ADI]

```

