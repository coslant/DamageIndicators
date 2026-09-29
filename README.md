<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=soft&color=0:FCAF01,50:FE2C6B,100:FC05AC&height=160&section=header&text=DamageIndicators&fontSize=60&fontColor=FFFFFF&fontAlignY=42&desc=Spigot%20%2F%20Paper%20%E2%80%A2%201.8%20%E2%86%92%201.21.11&descSize=15&descAlignY=72&animation=fadeIn" alt="DamageIndicators" width="100%" />
</p>

<p align="center">
  <a href="https://github.com/coslant/DamageIndicators/releases/latest"><img src="https://img.shields.io/github/v/release/coslant/DamageIndicators?style=for-the-badge&label=%C4%B0ndir&color=FE2C6B&logo=github" alt="Download" /></a>
  <a href="https://discord.gg/forges"><img src="https://img.shields.io/badge/Discord-Forges%20Studio-5865F2?style=for-the-badge&logo=discord&logoColor=white" alt="Discord: Forges Studio" /></a>
</p>

<p align="center">
  <a href="https://github.com/coslant/DamageIndicators/actions/workflows/build.yml"><img src="https://img.shields.io/github/actions/workflow/status/coslant/DamageIndicators/build.yml?branch=main&style=flat-square&label=build" alt="Build" /></a>
  <img src="https://img.shields.io/badge/Minecraft-1.8%20%E2%86%92%201.21.11-FCAF01?style=flat-square" alt="Minecraft 1.8 - 1.21.11" />
  <img src="https://img.shields.io/badge/Spigot%20%7C%20Paper-FE9808?style=flat-square" alt="Spigot | Paper" />
  <img src="https://img.shields.io/badge/Java-8-FD6C29?style=flat-square&logo=openjdk&logoColor=white" alt="Java 8" />
  <a href="LICENSE"><img src="https://img.shields.io/github/license/coslant/DamageIndicators?style=flat-square&color=FB0C9E&label=lisans" alt="License" /></a>
</p>

<p align="center">
  <b>Hasar göstergesi, oyuncu canı ve mob can barı.</b>
  <br>
  <sub><kbd>EN</kbd> Floating damage indicators, below-name player health and mob health bars.</sub>
</p>

Vurduğun her darbede havada yükselen hasar sayısı, oyuncuların isminin altında can, mobların
üstünde can barı. Tek jar **1.8 – 1.21.11** arası çalışır.

## ✨ Özellikler

- 💥 Vuruşta havada yükselen **hasar göstergesi**
- ⚡ Kritik vuruş, ölüm darbesi ve iyileşme için ayrı biçimler
- ❤️ Oyuncuların **isminin altında can** (isteğe bağlı olarak TAB listesinde de)
- 👹 Mobların üstünde **can barı** — sayı (`20 ❤`) ya da bar (`❤❤❤❤❤`) olarak
- 🎨 Cana göre renk değişimi: yeşil → sarı → kırmızı
- 🛡️ Hasar sebebine göre özel biçim, istenmeyen sebepleri gizleme
- 🚦 **Spam koruması** — lav/ateş gibi sürekli hasarlarda gösterge yağmurunu engeller
- 🌍 Dünya ve varlık türü bazında kapatma
- ⚡ Hiçbir bağımlılığı yok, ProtocolLib gerektirmez

## 📥 Kurulum

1. [Releases](https://github.com/coslant/DamageIndicators/releases/latest) sayfasından `DamageIndicators.jar` dosyasını indir.
2. Sunucunun `plugins/` klasörüne at.
3. Sunucuyu yeniden başlat.
4. `plugins/DamageIndicators/config.yml` dosyasından biçimleri düzenle.

## 🎮 Komutlar

| Komut | Açıklama | Yetki |
|-------|----------|-------|
| `/dmgindicators reload` | Ayarları yeniden yükler | `dmgindicators.reload` |

**Alias:** `/di` · `/dmg`

## 🔑 Yetkiler

| Yetki | Açıklama | Varsayılan |
|-------|----------|------------|
| `dmgindicators.reload` | Configi yeniden yükler | op |

## ⚙️ Ayarlar (config.yml)

| Anahtar | Açıklama |
|---------|----------|
| `damage-indicator.format` | Normal hasar biçimi |
| `damage-indicator.crit-format` | Kritik vuruş biçimi |
| `damage-indicator.death-format` | Ölüm darbesi biçimi |
| `damage-indicator.decimals` | Ondalık basamak sayısı (0 = tam sayı) |
| `damage-indicator.duration-ticks` | Gösterge kaç tick durur |
| `damage-indicator.rise` | Yukarı süzülme miktarı (0 = sabit) |
| `damage-indicator.throttle-ms` | Aynı varlık için iki gösterge arası en az süre |
| `damage-indicator.ignored-causes` | Bu sebeplerde gösterge çıkmaz |
| `damage-indicator.causes` | Sebebe göre özel biçim |
| `player-health.enabled` / `symbol` | İsim altında can ve simgesi |
| `self-health.actionbar` | Kendi canını action bar'da göster |
| `health-bar.mode` | `NUMBER` ya da `BAR` |
| `health-bar.always` | Sürekli görünsün mü, yoksa vurunca mı |
| `health-bar.ignored` | Can barı gösterilmeyecek varlıklar |

### Yer tutucular

`%damage%` · `%current%` · `%max%` · `%percent%` · `%bar%`

## 📝 Notlar

- Göstergeler **ArmorStand** ile çizilir; hiçbir ek kütüphane gerekmez.
- 1.8'de yerçekimini kapatan API yoktur; bu yüzden göstergenin konumu her karede sabitlenir ve düşmez.
- ❤ gibi simgeler bazı 1.8 istemcilerinde kutu görünebilir. O durumda configden düz metinle değiştir.
- Mob can barı, mobun kendi ismini geçici olarak değiştirir ve süre dolunca **eski ismini geri yükler**.

## 🛠️ Derleme

```bash
mvn clean package
```

Çıktı: `target/DamageIndicators.jar`

> 1.8 uyumluluğu için Java 8 hedefiyle derlenir. En sorunsuz derleme **JDK 8, 11 veya 17** iledir.

Her push'ta [GitHub Actions](https://github.com/coslant/DamageIndicators/actions/workflows/build.yml) projeyi otomatik derler; etiketlenen sürümler (`v*`) jar'ıyla birlikte [Releases](https://github.com/coslant/DamageIndicators/releases) sayfasında yayınlanır.

## 💬 Destek

- 🐛 Hata bildirimi ve öneriler için [Issues](https://github.com/coslant/DamageIndicators/issues) sekmesini kullan.
- 💬 Sorular ve destek için [Forges Studio Discord](https://discord.gg/forges) sunucusuna katıl.

## 📄 Lisans

[MIT](LICENSE) — dilediğin gibi kullan, değiştir, dağıt.

<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=rect&color=0:FCAF01,50:FE2C6B,100:FC05AC&height=4&section=footer" width="100%" alt="" />
  <br>
  <sub>🔥 <a href="https://github.com/coslant">coslant</a> tarafından geliştirildi · <a href="https://discord.gg/forges">Forges Studio</a></sub>
</p>
