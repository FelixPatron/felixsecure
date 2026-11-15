# FelixSecure

**FelixSecure** is a desktop file-encryption utility developed by **felixpatron**.  
**FelixSecure**, **felixpatron** tarafından geliştirilen masaüstü dosya şifreleme aracıdır.

---

## Türkçe

### Özellikler
- Fotoğraf, video, belge, ses, arşiv ve diğer dosyaları listeleme.
- Fotoğraflar için küçük resim, videolar için örnek kare önizlemesi.
- Dosyaları tek tek işaretleyerek şifreleme veya şifre çözme.
- Kategori üzerinden toplu seçim ve tek tek seçimden çıkarma.
- Türkçe ve İngilizce arayüz. Sistem dili Türkçe ise Türkçe, diğer dillerde İngilizce açılır.
- Büyük klasörlerin taranması ve önizlemelerin hazırlanması arka planda yapılır.
- AES-256-GCM ve PBKDF2-HMAC-SHA256 kullanılır.

### Gereksinimler
- Python 3.10 veya üzeri
- Windows 10/11 önerilir

### Kurulum
```bash
python -m pip install -r requirements.txt
python FelixSecure.py
```

`requirements.txt`:
```text
cryptography
Pillow
opencv-python
```

OpenCV yüklenmezse video küçük resimleri yerine video simgesi gösterilir.

### EXE oluşturma
```bash
python -m pip install pyinstaller
pyinstaller --noconfirm --clean --onefile --windowed --name FelixSecure FelixSecure.py
```

Oluşan uygulama:
```text
dist/FelixSecure.exe
```

İkon eklemek için `felixsecure.ico` dosyanız varsa:
```bash
pyinstaller --noconfirm --clean --onefile --windowed --icon felixsecure.ico --name FelixSecure FelixSecure.py
```

### Güvenlik uyarısı
- Parolanızı güvenli bir yerde saklayın. Parola kaybolursa dosyaların kurtarılması mümkün olmayabilir.
- Şifreleme başarılı olduğunda kaynak dosya silinir. Önemli dosyalarınızı önceden yedekleyin.
- Bu proje önemli veriler üzerinde kullanılmadan önce kopya dosyalarla test edilmelidir.
- Büyük dosyalar belleğe tamamen alınır; çok büyük video dosyaları için akış tabanlı şifreleme daha uygundur.

### Geliştirici
- GitHub: `felixpatron`
- Instagram: [@borantekin097](https://www.instagram.com/borantekin097)

---

## English

### Features
- Browse images, videos, documents, audio, archives and other files.
- Image thumbnails and video-frame previews.
- Select or deselect individual files before encryption or decryption.
- Bulk selection by category, with per-file overrides.
- Turkish and English interface. Turkish system locale starts in Turkish; other locales start in English.
- Folder scanning and thumbnail generation run in background threads.
- AES-256-GCM encryption with PBKDF2-HMAC-SHA256 key derivation.

### Requirements
- Python 3.10 or newer
- Windows 10/11 recommended

### Installation
```bash
python -m pip install -r requirements.txt
python FelixSecure.py
```

`requirements.txt`:
```text
cryptography
Pillow
opencv-python
```

If OpenCV is unavailable, video files display a generic video preview tile.

### Build an EXE
```bash
python -m pip install pyinstaller
pyinstaller --noconfirm --clean --onefile --windowed --name FelixSecure FelixSecure.py
```

The executable will be created at:
```text
dist/FelixSecure.exe
```

To include a custom icon, place `felixsecure.ico` beside the Python file and run:
```bash
pyinstaller --noconfirm --clean --onefile --windowed --icon felixsecure.ico --name FelixSecure FelixSecure.py
```

### Security notice
- Keep your password safe. Lost passwords cannot be recovered.
- Original files are deleted after successful encryption. Back up important data first.
- Test with copies of files before using the program on important data.
- Files are currently read into memory in full. Streaming encryption is recommended for very large files.

### Developer
- GitHub: `felixpatron`
- Instagram: [@borantekin097](https://www.instagram.com/borantekin097)
