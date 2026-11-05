# NOTICE — kaynak ve atıf

Bu depo, Mişkat uygulamasının mushaf sayfası **aynayı**dır. Sayfalar burada
üretilmedi; aşağıdaki kaynaklardan, değişmez commit'lerden kopyalandı.

| Dizin | Dosya | Kaynak | Lisans |
| --- | --- | --- | --- |
| `png/` | 604 | Miftah-Fentaw/Quran-Images | MIT |
| `webp/` | 605 | Miftah-Fentaw/Quran-Images | MIT |
| `wasat/` | 604 | QuranHub/quran-pages-images | Unlicense (kamu malı) — kapalı kaynak/ticari kullanım serbest |

## Kaynaklar

- [Miftah-Fentaw/Quran-Images](https://github.com/Miftah-Fentaw/Quran-Images) — commit `cca352724b9f29e326e077ce142172ddd9006368`; lisans dosyası `LICENSE`.
- [QuranHub/quran-pages-images](https://github.com/QuranHub/quran-pages-images) — commit `95823e5c5788e150a3f3e89a8536f1bd0c34f2c2`; lisans dosyası `LICENSE-quranhub`.

- `png/` ve `webp/` sayfalarının aslı
  [GovarJabbar/Quran-PNG](https://github.com/GovarJabbar/Quran-PNG) — quran.com'un
  Kral Fahd (KFQC) fontlarından üretilmiştir. O depoda lisans dosyası yok; MIT
  kapsamı Miftah-Fentaw derlemesine aittir.
- `wasat/` sayfaları: kaynak depo [QuranHub/quran-pages-images](https://github.com/QuranHub/quran-pages-images)
  lisansı **Unlicense** (kamu malı). README eskiden GPL-3.0 diyordu; kaynak sahibi
  `LICENSE` dosyasının esas olduğunu ve kapalı kaynak uygulamada copyleft
  yükümlülüğü olmadığını doğruladı:
  https://github.com/QuranHub/quran-pages-images/issues/2
- Sayfa numaralandırması: standart 604 sayfalık Madani mushaf.

## Bütünlük

`MANIFEST.sha256` her dosyanın SHA-256 özetini taşır:

```bash
cd <depo> && sha256sum -c MANIFEST.sha256
```

## Zip'ler

`dist/<set>.zip` dosyaları GitHub Releases'e yüklenir; dosyalar zip **kökündedir**.
Uygulama paketi tek istekte indirmek için bunları kullanır.

```bash
node data/scripts/mirror-mushaf-pages.mjs --target <bu-dizin> --zip
```
