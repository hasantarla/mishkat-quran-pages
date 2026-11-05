# Mişkat — Kur'an mushaf sayfası aynası

[Mişkat](https://github.com/hasantarla/mishkat) uygulamasının mushaf sayfası
**aynayı**. Sayfalar burada üretilmedi; kaynak depolardan **değişmez bir commit**ten
kopyalandı. Amaç: sayfa dağıtımı üçüncü taraf depoların ayakta kalmasına bağlı
kalmasın.

Ayrıntılı atıf ve lisans bilgisi: [`NOTICE.md`](NOTICE.md). Lisans dosyaları:
[`LICENSE`](LICENSE) (Miftah-Fentaw, MIT) ve [`LICENSE-quranhub`](LICENSE-quranhub)
(Unlicense — kamu malı; kaynak sahibi kapalı kaynak/ticari kullanıma izin verdi).

## İçerik

| Dizin | Dosyalar | Boyut | Biçim |
| --- | --- | --- | --- |
| `png/` | `1.png` … `604.png` (604) | ~34 MB | opak, aydınlatmalı, indeksli PNG |
| `webp/` | `000.webp` … `604.webp` (605) | ~182 MB | saydam mürekkep, 1080×1440 |
| `wasat/` | `1.jpg` … `604.jpg` (604) | ~177 MB | süslü çerçeveli JPEG, ~807×1205 |

`webp/000.webp` besmele levhasıdır, mushaf sayfası değildir. Sayfa numarası her
sette aynıdır (`png/2.png`, `webp/002.webp`, `wasat/2.jpg` aynı sayfadır).

## Uygulama bunu nasıl kullanıyor

1. **Paket (tercih edilen):** her set için bir zip, **Releases** altında. Uygulama
   tek istekte indirip cihaza açar.
2. **Tek tek sayfa:** zip alınamazsa dosyalar bu depodan tek tek indirilir.

Adresler **etiket**e sabitlenir (`v1`, `v2`), `main`'e değil: depo içeriği sonradan
değişse bile uygulamanın gördüğü sayfalar değişmez. Güncelleme bilinçli yapılır:
yeni bir etiket açılır ve uygulamada adres ona çevrilir.

| Etiket | İçerik | Zip adları |
| --- | --- | --- |
| `v1` | `png/`, `webp/` | `png-v1.zip`, `webp-v1.zip` |
| `v2` | + `wasat/` | `wasat.zip` |

## Bütünlük

`MANIFEST.sha256` her dosyanın SHA-256 özetini taşır (1813 kayıt):

```bash
sha256sum -c MANIFEST.sha256
```

## Zip'leri yeniden üretmek

```bash
node data/scripts/mirror-mushaf-pages.mjs --target <bu-dizin> --zip
```

`dist/` altındaki zip'ler Releases'e yüklenir; depoya **commit edilmez**
(`.gitignore`).
