# Mişkat — Kur'an mushaf sayfası aynası

[Mişkat](https://github.com/hasantarla/mishkat) uygulamasının mushaf sayfası
**aynayı**. Sayfalar burada üretilmedi; kaynak depolardan **değişmez bir commit**ten
kopyalandı. Amaç: sayfa dağıtımı üçüncü taraf depoların ayakta kalmasına bağlı
kalmasın.

Ayrıntılı atıf ve lisans bilgisi: [`NOTICE.md`](NOTICE.md), [`LICENSE`](LICENSE).

## İçerik

| Dizin | Dosyalar | Boyut | Biçim |
| --- | --- | --- | --- |
| `png/` | `1.png` … `604.png` (604) | ~34 MB | opak, aydınlatmalı, indeksli PNG |
| `webp/` | `000.webp` … `604.webp` (605) | ~182 MB | saydam mürekkep, 1080×1440 |

`webp/000.webp` besmele levhasıdır, mushaf sayfası değildir. Her iki sette de sayfa
numarası aynıdır (`png/2.png` ve `webp/002.webp` aynı sayfadır).

## Uygulama bunu nasıl kullanıyor

Sayfa dağıtımı iki yollu:

1. **Paket (tercih edilen):** her set için bir zip, **Releases** altında
   (`png-v1.zip`, `webp-v1.zip`). Uygulama tek istekte indirip cihaza açar.
2. **Tek tek sayfa:** zip alınamazsa dosyalar bu depodan tek tek indirilir.

Adresler **etiket**e sabitlenir (`v1`), `main`'e değil: depo içeriği sonradan
değişse bile uygulamanın gördüğü sayfalar değişmez. Güncelleme bilinçli yapılır:
yeni bir etiket (`v2`) açılır ve uygulamada adres ona çevrilir.

## Bütünlük

`MANIFEST.sha256` her dosyanın SHA-256 özetini taşır (1209 kayıt):

```bash
sha256sum -c MANIFEST.sha256
```

## Zip'leri yeniden üretmek

```bash
node data/scripts/mirror-mushaf-pages.mjs --target <bu-dizin> --zip
```

`dist/` altındaki iki zip Releases'e yüklenir; depoya **commit edilmez**
(`.gitignore`).
