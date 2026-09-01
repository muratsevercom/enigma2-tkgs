

# Enigma2 Turksat Kanal Güncelleme Sistemi (TKGS) Eklentisi



<img width="1920" height="1080" alt="screenshot_20260901112427" src="https://github.com/user-attachments/assets/1515ee06-8f9d-4592-a5e1-4266b1ee77e7" />



Türksat Kanal Güncelleme Sistemi (TKGS) verisini canlı yayından okuyup Enigma2 kanal listenizi ve LCN sırasını otomatik olarak günceller.

## Özellikler

- Türksat uydusundan TKGS verisini doğrudan demux üzerinden okur, harici bir sunucuya ihtiyaç duymaz
- Okunan kanalları LCN sırasına göre otomatik bir buket (`userbouquet.tkgs_auto.tv`) olarak yazar
- Tarama sırasında mevcut kanaldan TKGS frekansına otomatik geçiş yapar, işlem bitince izlediğiniz kanala geri döner
- İlerleme durumu, bulunan kanallar ve LCN eşleşme sayısı ekranda canlı olarak gösterilir
- Frekans, polarizasyon ve sembol oranı ayarlanabilir

## Gereksinimler

- Enigma2 tabanlı bir alıcı (OpenATV, OpenPLi, VTi, PurE2, DreamOS vb.)
- **Python 3** (Python 2 desteklenmiyor — güncel imajların hepsinde zaten varsayılan)
- Türksat uydusunu görebilen bir DVB-S2 tuner

> [!CAUTION]
> ## Önemli NOT
> Eklentiyi çalıştırmadan önce mutlaka aşağıdaki frekanslardan **"Şebeke Arama (NIT)"** açık şekilde tarama yapın.
>
> * Frekans: 12380 MHz
> * Polarizasyon: V - Dikey (Vertical)
> * Sembol Oranı (SR): 27500
> * FEC: 3/4
>
> Alternatif olarak Orta Asya ve Türkiye bölgesi için şu değerler de kullanılabilir:
>
> * Frekans: 12423 MHz
> * Polarizasyon: H - Yatay (Horizontal)
> * Sembol Oranı (SR): 30000
> * FEC: 3/4

## Kurulum

**OpenATV / OpenPLi / VTi / PurE2 ve diğer opkg tabanlı imajlar:**

```sh
opkg install tkgsautolcn_1.0_all.ipk
```

**DreamOS:**

```sh
dpkg -i tkgsautolcn_1.0_all.deb
```

Kurulumdan sonra eklenti **Eklentiler (Extensions)** menüsünde görünür.

## Kullanım

1. Eklentiler menüsünden **TKGS Otomatik Kanal Güncelleme**'yi açın.
2. Frekans, polarizasyon ve sembol oranını (varsayılan: `12380 V 27500`)yazın ya da default frekansta bırakın, TKGS frekans değişirse, güncel frekansla değiştirin.
3. **YEŞİL** tuşuna veya **OK**'a basarak taramayı başlatın.
4. Tarama ~20 saniye sürer; bulunan kanallar LCN sırasıyla listede görünür.
5. Tarama bitince kanal listeniz otomatik güncellenmiş olur.

## Kaldırma

```sh
# opkg tabanlı imajlar
opkg remove enigma2-plugin-extensions-tkgsautolcn

# DreamOS
dpkg -r enigma2-plugin-extensions-tkgsautolcn
```

## Sorun Giderme

**"Refusing to load file... it matches the installed version" hatası:**

```sh
opkg remove enigma2-plugin-extensions-tkgsautolcn
opkg install tkgsautolcn_1.0_all.ipk
```

veya doğrudan zorla üzerine kurun:

```sh
opkg install --force-reinstall tkgsautolcn_1.0_all.ipk
```

**TKGS frekansı bulunamadı uyarısı:** Cihazınızda o transponder'a ait bir kanal kayıtlı olmayabilir; ayarlar ekranından doğru frekans/polarizasyon/sembol oranını girin.

## Destek

Sorun ve önerileriniz için: **muratsevercom@gmail.com**

## Lisans

Tüm hakları saklıdır. Bu eklenti ücretsiz kullanım için sunulmuştur. 

## Geliştirici

Murat SEVER
https://muratsever.com
