# Stall Laboratuvarı

Hücum açısı, kaldırma, sürükleme ve stall hızı arasındaki ilişkiyi gösteren etkileşimli bir aerodinamik simülasyon. Tek dosyadan oluşur (`index.html`), kurulum veya derleme gerektirmez.

https://egemenyilmaz21.github.io/stall-lab/

## Neler var?

- **Canlı akış animasyonu:** Kanat profili etrafında akan hava çizgileri. Kritik hücum açısı aşılınca akış kanattan ayrılır ve türbülanslı hale gelir.
- **Kaldırma ve sürükleme vektörleri:** L ve D, güncel CL ve CD değerleriyle orantılı çizilir.
- **Gösterge paneli:** α, CL, CD, L/D, hız, stall hızı (Vs), stall payı (V/Vs), yük faktörü (n) ve kaldırma/gerekli oranı.
- **İki çalışma modu:**
  - *Hücum açısını ben ayarlayayım:* α doğrudan seçilir.
  - *Dengeli uçuş:* Hız seçilir, α düz uçuş için hesaplanır (L = n · W). Hız Vs'ye yaklaştıkça α'nın neden arttığını gösterir.
- **Parametreler:** Hız, yatış açısı, ağırlık, yoğunluk irtifası ve flap (0°, 10°, 20°, 30°).
- **Grafikler:** CL–α, CD–α, L/D–α, kutup (CL–CD) ve Vs–yatış açısı.
- **Senaryolar:** α taraması, yavaşlama, sert viraj (viraj stall'ı) ve stall ve kurtarma.
- Açık ve koyu tema, telefon uyumlu düzen, `prefers-reduced-motion` desteği.

## Temel formüller

```
L  = ½ · ρ · V² · S · CL
Vs = √( 2 · n · W / (ρ · S · CLmax) )
n  = 1 / cos φ          →  Vs,viraj = Vs · √n
CD = CD0 + k · CL²  (+ ayrılma bileşeni)
```

## Model hakkında

Bu proje **eğitim amaçlı, sadeleştirilmiş** bir modeldir.

- Genel bir hafif uçak varsayılır: kanat alanı S = 16,2 m², flap 0° için kritik açı 15°. Flap açıldıkça CL0 ve CLmax artar, kritik açı biraz küçülür.
- Hızlar gerçek hava hızı (TAS) olarak alınır. Yoğunluk, standart atmosferden (ISA) hesaplanır.
- Stall sonrası CL ve CD eğrileri, ayrılmış akışı temsil eden basit üstel bir modelle verilir. Gerçek davranış kanat profiline, Reynolds sayısına ve kanat planformuna göre değişir.
- Gösterilen sayılar belirli bir uçağın performans verisi değildir. Gerçek uçuş için uçağın uçuş el kitabı (POH/AFM) ve eğitmenin talimatı geçerlidir.
