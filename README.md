# 🐧 WSL (Windows Subsystem for Linux) Kurulum Rehberi

Bu depo, Windows işletim sistemi üzerinde **WSL (Windows Subsystem for Linux)** kurulumunu adım adım, en güncel ve kolay haliyle anlatmaktadır. WSL sayesinde bilgisayarınızı dual-boot (çift işletim sistemi) yapmadan veya ağır sanal makineler kullanmadan doğrudan Windows üzerinde gerçek bir Linux ortamı çalıştırabilirsiniz.

---

## 📌 Sistem Gereksinimleri

Başlamadan önce sisteminizin aşağıdaki gereksinimleri karşıladığından emin olun:
* **Windows 10** (Sürüm 2004 ve üzeri, Yapı 19041 ve üzeri) veya **Windows 11** kullanıyor olmak.
* BIOS/UEFI üzerinden **Sanallaştırma (Virtualization - Intel VT-x / AMD-V)** özelliğinin açık olması.

## 🚀 Hızlı Kurulum (Önerilen)

Eğer Windows 10'un güncel bir sürümünü veya Windows 11 kullanıyorsanız, kurulum artık tek bir komutla yapılabiliyor:

1. Başlat menüsüne sağ tıklayın ve **PowerShell**'i (veya Windows Terminal'i) **Yönetici olarak** çalıştırın.
2. Aşağıdaki komutu kopyalayıp yapıştırın ve `Enter`'a basın:

   ```bash
   wsl --install


Kurulum işlemleri tamamlandığında bilgisayarınızı yeniden başlatın.

Bilgisayarınız açıldığında terminal otomatik olarak devam edecek ve varsayılan dağıtım olan Ubuntu'yu kuracaktır. Sizden bir UNIX kullanıcı adı ve şifre belirlemeniz istenecektir. (Şifre yazarken ekranda karakterler görünmez, bu normaldir)


Mevcut internet bağlantısı kısıtlamaları nedeniyle doğrudan paylaştığınız GitHub linkindeki spesifik içeriği okuyamıyorum. Ancak kendi GitHub hesabınızda yayınlayabileceğiniz, hem görsel olarak daha düzenli hem de teknik olarak eksiksiz bir WSL (Windows Subsystem for Linux) Kurulum Rehberi (README.md) şablonunu sizin için hazırladım.

Bu şablonu kopyalayıp deponuzdaki README.md dosyasının içine doğrudan yapıştırabilirsiniz.

Markdown
# 🐧 WSL (Windows Subsystem for Linux) Kurulum Rehberi

Bu depo, Windows işletim sistemi üzerinde **WSL (Windows Subsystem for Linux)** kurulumunu adım adım, en güncel ve kolay haliyle anlatmaktadır. WSL sayesinde bilgisayarınızı dual-boot (çift işletim sistemi) yapmadan veya ağır sanal makineler kullanmadan doğrudan Windows üzerinde gerçek bir Linux ortamı çalıştırabilirsiniz.

---

## 📌 Sistem Gereksinimleri

Başlamadan önce sisteminizin aşağıdaki gereksinimleri karşıladığından emin olun:
* **Windows 10** (Sürüm 2004 ve üzeri, Yapı 19041 ve üzeri) veya **Windows 11** kullanıyor olmak.
* BIOS/UEFI üzerinden **Sanallaştırma (Virtualization - Intel VT-x / AMD-V)** özelliğinin açık olması.

## 🚀 Hızlı Kurulum (Önerilen)

Eğer Windows 10'un güncel bir sürümünü veya Windows 11 kullanıyorsanız, kurulum artık tek bir komutla yapılabiliyor:

1. Başlat menüsüne sağ tıklayın ve **PowerShell**'i (veya Windows Terminal'i) **Yönetici olarak** çalıştırın.
2. Aşağıdaki komutu kopyalayıp yapıştırın ve `Enter`'a basın:

   ```bash
   wsl --install
Kurulum işlemleri tamamlandığında bilgisayarınızı yeniden başlatın.

Bilgisayarınız açıldığında terminal otomatik olarak devam edecek ve varsayılan dağıtım olan Ubuntu'yu kuracaktır. Sizden bir UNIX kullanıcı adı ve şifre belirlemeniz istenecektir. (Şifre yazarken ekranda karakterler görünmez, bu normaldir).

🔀 Farklı Bir Linux Dağıtımı Kurmak
Varsayılan olan Ubuntu yerine Debian, Kali Linux veya openSUSE gibi başka bir dağıtım kurmak isterseniz:

Kurulabilir durumdaki resmi dağıtımları listelemek için:

Bash
wsl --list --online
İstediğiniz dağıtımı kurmak için (Örn: Debian):

Bash
wsl --install -d Debian
🛠️ Kurulum Sonrası İlk Adımlar
Linux ortamınızı başarıyla kurduktan sonra, paket listelerini ve mevcut programları güncellemek en iyi pratiktir. Terminali açın ve şu komutları çalıştırın:

Bash
sudo apt update && sudo apt upgrade -y
⚙️ Faydalı WSL Komutları
Geliştirme sürecinizde en çok ihtiyaç duyacağınız temel WSL komutları:

Komut	Ne İşe Yarar?
wsl -l -v	Yüklü olan tüm dağıtımları ve hangi WSL sürümünde (1 veya 2) çalıştıklarını listeler.
wsl --set-version <Dağıtım> 2	Belirli bir dağıtımı (Örn: Ubuntu) WSL 2 mimarisine yükseltir.
wsl --shutdown	Arka planda çalışan tüm WSL süreçlerini anında durdurur ve RAM'i serbest bırakır.
wsl --unregister <Dağıtım>	Yüklü bir dağıtımı tamamen siler. (DİKKAT: İçindeki tüm dosyalar silinir!)
⚠️ Sık Karşılaşılan Sorunlar ve Çözümleri
Hata: 0x80370102 (Sanal Makine Platformu Hatası)

Çözüm: Bilgisayarınızı yeniden başlatıp BIOS ayarlarına girin ve "Virtualization Technology" ayarını "Enabled" yapın. Ayrıca Windows arama çubuğuna Windows özelliklerini aç veya kapat yazıp, listedeki Sanal Makine Platformu (Virtual Machine Platform) seçeneğinin işaretli olduğundan emin olun.

Ağ Bağlantısı veya DNS Sorunları (İnternete çıkamama)

Çözüm: WSL içindeki /etc/resolv.conf dosyasını düzenleyerek nameserver adresini 8.8.8.8 olarak güncelleyebilirsiniz.
