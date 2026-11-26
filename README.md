# Canavar Yutan — web sitesi (GitHub Pages)

Derleme yok, düz HTML. Push et, Pages'i aç.

| Dosya | Adres | Nerede kullanılır |
|---|---|---|
| `index.html` / `tr/index.html` | `/` · `/tr/` | Mağaza "Web sitesi" alanı |
| `privacy.html` / `tr/gizlilik.html` | `/privacy.html` | Play Console + App Store "Gizlilik politikası URL'si" |
| `terms.html` / `tr/kosullar.html` | `/terms.html` | İsteğe bağlı (App Store EULA, Steam) |
| `app-ads.txt` | `/app-ads.txt` | AdMob doğrulaması (pub-3834148733890519) |

Piksel canavarlar `assets/*.svg`, oyundaki `scripts/Sprites.gd` haritalarından üretildi.

## Yayından önce doldur

Klasörde `{{` ara ve değiştir:

| Yer tutucu | Örnek |
|---|---|
| `{{DEVELOPER_NAME}}` | Mağazadaki geliştirici adın |
| `{{CONTACT_EMAIL}}` | Destek e-postan |
| `{{EFFECTIVE_DATE}}` | EN: December 1, 2026 · TR: 1 Aralık 2026 |
| `{{GOVERNING_LAW}}` | EN: the Republic of Türkiye · TR: Türkiye Cumhuriyeti |

## Dikkat

- **app-ads.txt alan adının kökünde olmalı.** `kullanici.github.io/repo/app-ads.txt` AdMob için geçmez.
  Çözüm: repo adını `kullanici.github.io` yap **veya** kendi alan adını bağla. Play Console'daki
  geliştirici web sitesi de aynı kök alan adı olmalı.
- Play Console'da hedef kitleye **13 yaş altı** eklersen gizlilik metnindeki "Children" bölümü ve
  `AdMobBackend.gd` içindeki `tag_for_under_age_of_consent` / child-directed ayarı değişmeli
  (Families politikası). Şu anki metin "13 yaş altına yönelik değil" diyor.
- Metin şunları varsayıyor: hesap yok, kayıt yalnızca cihazda, analitik/çökme raporlama yok, yalnızca
  AdMob ödüllü reklam, Steam'de reklam yok. Bunlardan biri değişirse (Firebase, Steam Cloud, satın alma
  eklenirse) metni güncelle.
- Lansmandan önce bir hukukçuya göz attırmak iyi olur.

## Yayınla

```bash
git init
git add .
git commit -m "Canavar Yutan web sitesi"
git branch -M main
git remote add origin https://github.com/<kullanici>/<repo>.git
git push -u origin main
```

GitHub → repo → **Settings → Pages** → *Deploy from a branch* → `main` / `(root)` → Save.
