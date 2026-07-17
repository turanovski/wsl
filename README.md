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
