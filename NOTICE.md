# NOTICE — kaynak ve atıf

Bu depo, Mişkat uygulamasının mushaf sayfası **aynayı**dır. Sayfalar burada
üretilmedi; aşağıdaki kaynaklardan, değişmez bir commit'ten kopyalandı.

## Kaynak

- Ayna kaynağı: [Miftah-Fentaw/Quran-Images](https://github.com/Miftah-Fentaw/Quran-Images) — commit
  `cca352724b9f29e326e077ce142172ddd9006368`, MIT lisansı (`LICENSE` dosyası bu commit'ten kopyadır).
- Sayfaların aslı: [GovarJabbar/Quran-PNG](https://github.com/GovarJabbar/Quran-PNG)
  — quran.com'un Kral Fahd (KFQC) fontlarından üretilmiştir. Bu depoda **lisans
  dosyası yok**; MIT kapsamı aynadaki derlemeye aittir.
- Sayfa numaralandırması: standart 604 sayfalık Madani mushaf.

## İçerik

| Dizin | Dosya sayısı | Boyut | Biçim |
| --- | --- | --- | --- |
| `png/` | 604 (`1.png` … `604.png`) | ~32 MB | opak, aydınlatmalı, indeksli PNG |
| `webp/` | 605 (`000.webp` … `604.webp`) | ~180 MB | saydam mürekkep, 1080×1440 |

`webp/000.webp` besmele levhasıdır, 605. mushaf sayfası değildir.

## Bütünlük

`MANIFEST.sha256` her dosyanın SHA-256 özetini taşır:

```bash
cd <depo> && sha256sum -c MANIFEST.sha256
```

## Zip'ler

`dist/` altındaki iki zip, GitHub Releases'e yüklenir. Uygulama paketi tek
istekte indirmek için bunları kullanır; dosyalar zip **kökündedir**.

```bash
node data/scripts/mirror-mushaf-pages.mjs --target <bu-dizin> --zip
```
