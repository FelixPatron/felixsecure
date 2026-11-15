# FelixSecure

**FelixSecure** is a desktop file-encryption utility developed by **felixpatron**.

## Kullanıcılar için / For users

### Türkçe

Uygulamayı kullanmak için **yalnızca `FelixSecure.exe` dosyasını indirip çalıştırmanız yeterlidir.**

- Python kurmanız gerekmez.
- `cryptography`, Pillow veya OpenCV kurmanız gerekmez.
- `requirements.txt` dosyasına ihtiyacınız yoktur.
- Uygulama Türkçe Windows arayüz dilinde Türkçe, diğer dillerde İngilizce açılır.
- Windows SmartScreen uyarısı gösterirse, dosyayı yalnızca resmi/güvendiğiniz dağıtım kaynağından indirdiğinizden emin olun. Tanımadığınız EXE dosyalarını çalıştırmayın.

### English

To use the app, **download and run only `FelixSecure.exe`.**

- Python is not required.
- You do not need to install `cryptography`, Pillow, or OpenCV.
- You do not need `requirements.txt`.
- The app starts in Turkish when the Windows user interface language is Turkish; otherwise it starts in English.
- If Windows SmartScreen displays a warning, make sure the executable came from the official/trusted distribution source. Do not run EXE files from unknown sources.

---

## Özellikler / Features

- Fotoğraf, video, belge, ses, arşiv ve diğer dosyaları listeleme. / Browse images, videos, documents, audio, archives and other files.
- Fotoğraf küçük resimleri ve videolardan örnek kare önizlemesi. / Image thumbnails and video-frame previews.
- Şifreleme/şifre çözme öncesinde dosyaları tek tek seçme. / Select individual files before encryption or decryption.
- Kategori üzerinden toplu seçim ve dosya bazında seçim değiştirme. / Bulk category selection with per-file overrides.
- Sistem diline göre otomatik Türkçe/İngilizce başlangıç dili. / Automatic Turkish/English startup language based on the system UI language.
- Klasör taraması ve önizleme hazırlama işlemlerinin arka planda yapılması. / Background folder scanning and thumbnail generation.
- AES-256-GCM and PBKDF2-HMAC-SHA256.

---

## Geliştiriciler için / For developers

Aşağıdaki adımlar yalnızca Python kaynak kodundan uygulamayı kendiniz derlemek istiyorsanız gereklidir. Normal kullanıcıların bunları yapmasına gerek yoktur.

These steps are only needed if you want to build the application from source. Regular users do not need to follow them.

### Gereksinimler / Requirements

- Python 3.10 or newer
- Windows 10/11 (64-bit) recommended
- `FelixSecure.py`, `icon.ico`, and `requirements.txt` in the project folder

### Kurulum / Install build dependencies

```bash
python -m pip install --upgrade pip
python -m pip install -r requirements.txt
python -m pip install --upgrade pyinstaller
```

`requirements.txt`:

```text
cryptography
Pillow
opencv-python
```

OpenCV is used for video-frame previews. If it is not bundled correctly, video files can still be listed, but their preview may be unavailable.

### EXE oluşturma / Build the EXE

Run this command from the folder containing `FelixSecure.py` and `icon.ico`:

```bash
python -m PyInstaller --noconfirm --clean --onefile --windowed --icon=icon.ico --name FelixSecure --collect-all cv2 FelixSecure.py
```

The distributable file is:

```text
dist/FelixSecure.exe
```

**Dağıtım / Distribution:** Share only `dist/FelixSecure.exe` with end users. Do not ask users to install Python packages or provide the source folder for normal use.

### Windows "Ordinal 380" / "Sıra sayısı 380" error

If the EXE shows an error saying that ordinal 380 cannot be found, do not assume that users need to install Python packages. This is a Windows loader/dependency compatibility issue. Rebuild on Windows 10/11 (64-bit) using a current 64-bit Python installation and an updated PyInstaller. Also test the build on a separate Windows 10/11 computer.

For diagnosis, first create a folder-based build with a console so a startup traceback can be seen:

```bash
python -m PyInstaller --noconfirm --clean --onedir --console --name FelixSecure --collect-all cv2 FelixSecure.py
```

Run `dist\\FelixSecure\\FelixSecure.exe`. If this works but the one-file build does not, the issue is likely related to one-file bundling or a packaged dependency. If it still fails, note the Windows version, Python version (`python --version`), and whether Python is 64-bit before changing dependencies.

---

## Güvenlik uyarısı / Security notice

- Parolanızı güvenli bir yerde saklayın. Parola kaybolursa dosyalarınızı kurtaramazsınız. / Keep your password safe; lost passwords cannot be recovered.
- Şifreleme başarılı olduğunda kaynak dosya silinir. Önce yedek alın. / Original files are deleted after successful encryption. Back up files first.
- Önemli dosyalarınızda kullanmadan önce kopyalar üzerinde test edin. / Test with copies before using it on important files.
- Büyük dosyalar belleğe tamamen alınır. / Large files are currently read into memory in full.

## Geliştirici / Developer

- GitHub: `felixpatron`
- Instagram: [@borantekin097](https://www.instagram.com/borantekin097)
