# Güç Kartı Tersine Mühendislik Projesi

Şebeke girişli, yüksek gerilim çıkışlı ticari bir güç kartının tersine mühendisliği: blok analizi, şema çıkarma, trafo ve komponent ölçümleri, sürekli arızalanan yüksek gerilim çarpıcı katının yeniden üretilmesi.

## Kartın yapısı

1. **Giriş katı:** sigorta, varistör, ortak mod bobinleri, köprü diyot, ana kondansatör
2. **Flyback konvertör:** şebekeden lojik devre gerilimini üretir
3. **Kontrol devresi:** kontrolcü ve akım ayar devresi
4. **Sürücü trafosu**
5. **Forward konvertör:** yüksek gerilim katını besler
6. **6 katlı gerilim çarpıcı:** kartın sürekli arızalanan bölümü

```
Şebeke → EMI filtre → Doğrultucu → Flyback → Lojik besleme → Kontrol
                                  → Forward → 6x çarpıcı → Yüksek gerilim çıkışı
```

## Yöntem

- Sistemi işlevsel bloklara ayırdım.
- PCB'nin X-ray görüntülerini alıp her bloğun şemasını çıkardım.
- Komponentleri LCR metre ve multimetre ile ölçtüm.
- Flyback, forward ve sürücü trafolarının sarım yönlerini ve sarım oranlarını çıkardım (fonksiyon jeneratörü ile sinüs uygulayıp osiloskopla ölçerek).
- Forward ile beslenen çarpıcı devresinin sürekli arızalandığını tespit ettim, 20 adet yeniden üretip kartları kurtardım.
- Üretilebilir Altium projesini oluşturdum (şirket bilgisayarında kaldığı için repoda yok).

## Kullanılan ekipman

Osiloskop (Rigol DS1054Z), fonksiyon jeneratörü (Rigol DG2102), LCR metre (GW Instek LCR-6100), DC güç kaynağı (Owon ODP3063), multimetre (Metrel MD9020), Altium Designer

## Ölçüm örnekleri

- **Trafo oranı:** sinüs uyarımı ile primer/sekonder tepeden tepeye gerilim oranı (50 kHz ve 1 MHz)
- **Kondansatör:** 1 kHz'de Cp/Cs, D ve Rs ölçümü
- **Zener:** 12 V ve seri direnç ile zener gerilimi tespiti

Fotoğraflar `images/` klasöründe.

## Güvenlik

Kart şebeke gerilimi ve yüksek gerilim içerir. İzolasyon trafosu olmadan canlı ölçüm yapılmamalı, kondansatörler boşaltılmadan karta dokunulmamalıdır.

## Not

Bu proje bağımsız bir inceleme ve belgeleme çalışmasıdır. Üretici firma ile bağlantısı yoktur.
