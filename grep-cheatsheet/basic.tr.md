Grep Cheatsheeti Linux Konfigürasyonu, Kodlama ve Saldırı Testleri için

## Temel Syntax
```
grep [options] pattern [dosya...]
```

## Genel Seçenekler
- `-i`: Büyük/küçük harf duyarsız arama
- `-r` veya `-R`: Dizin içerisinde arama (alt dizinler dahil)
- `-n`: Satır numaraları göster
- `-w`: Tam kelime ile eşleşme
- `-v`: Eşleşmeyen satırları göster
- `-l`: Eşleşen dosyaların isimleri göster
- `-c`: Eşleşen sayısını göster
- `-A n`: Arananın ardından n satır göster
- `-B n`: Aranan önce n satır göster
- `-C n`: Aranan önce ve sonra n satır göster

## Linux Konfigürasyon İşlemleri

1. Belirli bir ayarı tüm config dosyalarında arayın:
   ```
   grep -r "PasswordAuthentication" /etc/
   ```

2. Aktif olan servisleri bulun:
   ```
   grep -r "enabled=1" /etc/
   ```

3. Config dosyalarında IP adreslerini arayın:
   ```
   grep -E -r "\b([0-9]{1,3}\.){3}[0-9]{1,3}\b" /etc/
   ```

4. Kullanıcıların shell erişimi olup olmadığını bulun:
   ```
   grep -E "/bin/(bash|sh)$" /etc/passwd
   ```

## Kodlama İşlemleri

1. Fonksiyon tanımlamalarını arayın:
   ```
   grep -n "def " *.py
   ```

2. TODO yorumlarını bulun:
   ```
   grep -r -n "TODO:" .
   ```

3. Belirli bir modülü import eden dosyaları bulun:
   ```
   grep -r "import numpy" .
   ```

4. Belirli bir sınıfı içeren dosyaları bulun:
   ```
   grep -l "class MyClass" *.py
   ```

## Saldırı Testleri İşlemleri

1. Potansiyel parolaları arayın:
   ```
   grep -r -i "password" /path/to/search
   ```

2. Potansiyel API key'lerini bulun:
   ```
   grep -r -E "[a-zA-Z0-9]{32}" /path/to/search
   ```

3. SQL injection saldırılarına karşı arayın:
   ```
   grep -r -i "SELECT.*FROM.*WHERE" /var/www/html/
   ```

4. Komuta injection saldırılarına karşı arayın:
   ```
   grep -r -E "system\(|exec\(|passthru\(" /var/www/html/
   ```

5. Zayıf izinlere sahip dosyaları bulun:
   ```
   grep -r "777" /etc/
   ```

## İleri Seviye Kullanım

1. OR mantığını kullanın:
   ```
   grep -E "pattern1|pattern2" dosya
   ```

2. AND mantığını kullanın:
   ```
   grep "pattern1" dosya | grep "pattern2"
   ```

3. Belirli dosyaları veya dizinleri hariç tutun:
   ```
   grep -r "pattern" --exclude=*.log --exclude-dir=node_modules .
   ```

4. Düzenli ifadeleri kullanın:
   ```
   grep -E "[A-Za-z0-9._%+-]+@[A-Za-z0-9.-]+\.[A-Za-z]{2,4}" dosya
   ```

Grep komutunu sorumlulukla ve etik kurallara uygun bir şekilde kullanın, özellikle de saldırı testleri için. Sistemlere erişimi olmayan sistemlerde güvenlik değerlendirmesi yapmadan önce yetki almayı unutmayın.