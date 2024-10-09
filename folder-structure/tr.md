Aşağıdaki markdown formatında, farklı dağıtımlarda kullanılan klasörlerin kullanım örnekleri ve resimleri bulunmaktadır:

# Unix Tabanlı İşletim Sistemi Klasör Yapısı

```markdown
![Unix klasör yapısı](/api/placeholder/800/600 "Unix klasör yapısı")

```

## Genel Klasörler

- `/` (root): Sistem hiyerarşisinin en üst düzey klasörü.
- `/bin`: Esansiyel komut dosyaları (örneğin, `ls`, `cp`, `mv`).
  - Ubuntu ve Debian'de `/bin` `/usr/bin` klasörüyle bir bağlantıdır.
- `/sbin`: Esansiyel sistem dosyaları (örneğin, `init`, `ifconfig`, `route`).
  - Ubuntu ve Debian'de `/sbin` `/usr/sbin` klasörüyle bir bağlantıdır.
- `/etc`: Sistem-wide konfigürasyon dosyaları.
  - Red Hat ve CentOS'ta ağ ayarları `/etc/sysconfig/network-scripts/` klasöründe depolanır.
- `/dev`: Cihaz dosyaları (örneğin, `/dev/null`, `/dev/sda`).
- `/proc`: İşlem ve çekirdek bilgisi sağlayan sanal dosya sistemi.
- `/var`: Değişken dosyalar (örneğin, günlükler, spool dosyaları ve geçici dosyalar).
  - Ubuntu'da varsayılan Apache belge dizini `/var/www/html/`dır.
- `/tmp`: Geçici dosyalar. Sistem yeniden başlatıldığında genellikle korunmaz.
- `/usr`: Kullanıcı uygulamaları ve araçları.
  - Arch Linux'te paket kümeleri `/var/cache/pacman/pkg/` klasöründe depolanır.
- `/home`: Kullanıcı ev dizinleri.
  - Ubuntu ve Debian'da her kullanıcıya bir dizin vardır: `/home/username/`.
- `/boot`: Boot loader dosyaları, çekirdek ve initrd.
  - Fedora'da GRUB konfigürasyon dosyası `/boot/grub2/grub.cfg`dir.
- `/lib`: Esansiyel paylaşımlı kütüphaneler ve çekirdek modülleri.
  - Ubuntu ve Debian'de `/lib` `/usr/lib` klasörüyle bir bağlantıdır.
- `/opt`: Seçmeli uygulama yazılım paketleri.
- `/mnt`: Geçici olarak monte edilen dosya sistemleri.
- `/media`: Kaldırılabilir medya için montaj noktaları (örneğin, USB sürücüler, CD'ler).
  - Ubuntu'da bir USB sürücü `/media/username/USBDRIVE/` klasöründe monte edilebilir.

## Dağıtıma Özellikli Klasörler

### Ubuntu ve Debian
- `/snap`: Snap paketleri (Ubuntu için)
- `/usr/share/doc`: Kurulan paketlere ait belgeler.

### Red Hat, Fedora ve CentOS
- `/usr/local`: Yerel olarak kurulum yapılan yazılım.
- `/usr/libexec`: Sistem değişkenleri ve sistem araçları.

### Arch Linux
- `/srv`: Sistem tarafından sağlanan hizmetler için veri.
- `/run`: Son başlatma anından itibaren çalışan sistemin ilgili bilgileri.