# ENIGMA2 TKGS (TURKSAT KANAL GÜNCELLEME SİSTEMİ) EKLENTİSİ

Enigma2 uydu alıcıları için TKGS eklentisi.
TKGS sisteminin aktif edildiği 2013 yılından beri Enigma2 için bir türlü yapılamayan ve çok büyük eksik olan bir eklentiydi. Nihayet TKGS mantığını birebir çözdüm ve ilki başarıp bu plugini geliştirdim. İlk olmak her zaman iyidir (-:

## DİPNOT:
15 yıldır yazılamayan eklentiyi ben yazınca bazı sırtlanlar kaynak koddan benim eklentimin kopyalarını yapmışlar (-: Sağdan soldan topladıkları piconları bile satan adamlar 15 senedir neredeydiniz? (-:

## Eklenti ne yapar?
Türksat 42.0E'nin yayınladığı TKGS listesini doğrudan uydudan okur ve kanal listenizi birkaç saniyede kurar. Tarama yapmaz, internet gerektirmez.

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/389beb79-00c3-4196-9160-ab95c99eb4c9" />
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/7aea7ddb-4628-43ec-b72d-1174bb39e241" />
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/7af8b85a-cd45-4d00-b910-cf50d2ec5e68" />
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/a64f9e67-6bcc-43af-adac-83120eb9e237" />
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/b72e0003-5ac7-41d6-95c4-4263d7562758" />
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/ca128d5a-871f-48b6-a04c-20a8563b9b17" />
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/32a8d384-aedc-47be-81a7-318e49fa9f93" />


<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/256400ea-1524-4567-b43a-00a2cc136fed" />

## Eklenti OpenATV Feed'e eklenti. Artık Feed'den de indirilebilir



## Özellikler

- **Taramasız kurulum:** Kanal listesi doğrudan Türksat'ın yayınladığı tablodan kurulur.
- **Türksat numaralandırması:** Kanal numaraları Türksat sıralamasıyla birebir aynıdır.
- **Önizleme:** Kurmadan önce kanalları görür, TV/radyo ve kategoriye göre filtreleyebilirsiniz. Yeni eklenecek ve şifreli kanallar işaretlidir.
- **Canlı kanal akışı:** Okunan kanallar ekranda alt alta listelenir.
- **Otomatik güncelleme:** Liste her gün, her hafta veya her ay kendiliğinden kontrol edilir.
- **Sinyal testi:** TKGS frekanslarında kalite, güç ve dB değerleri canlı gösterilir.
- **Yedekleme:** Her kurulumdan önce yedek alınır, tek tuşla eski listeye dönülür.
- **Güvenli:** Diğer buketlerinize ve mevcut kanallarınıza dokunmaz, yalnızca eksikleri ekler.

## 4.4.8 sürümü ile yapılan düzeltmeler

- **Broadcom işlemciler için fix:** Broadcom işlemci kullanan cihazlarda verilerin okunamama sorunu düzeltildi. Artık VU+ gibi cihazlarda da eklenti çalışıyor.
- **Hata loglama:** Detaylı hata loglama. Tüm hatalar yakalanıyor.
- **Performans iyileştirmeleri:** Eklentinin stabil çalışması için performans iyileştirmeleri.
- **Yedek çalışma:** Tarama esnasında bir işlem hata verirse, yedek sistem devreye girip işlemi tamamlıyor.
 
## Kurulum

Paketi [Releases](../../releases) sayfasından indirip kutunun `/tmp` klasörüne kopyalayın (FTP ile).

**OpenATV, OpenPLi ve benzeri imajlar:**

```sh
opkg install /tmp/enigma2-plugin-extensions-mstkgs_4.4.8_all.ipk
```

**DreamOS:**

```sh
dpkg -i /tmp/enigma2-plugin-extensions-mstkgs_4.4.8_all.deb
```

Kurulumdan sonra Enigma2'yi yeniden başlatın. Eklenti **Eklentiler** listesinde görünür.

## Kullanım

1. **Eklentiler** menüsünden **TURKSAT TKGS**'yi açın.
2. **Oku ve Önizle**'yi seçin. Eklenti TKGS frekansına kilitlenir ve listeyi okur.
3. Bulunan kanallar ekrana dökülür, ardından **Kanal Gezgini** açılır.
4. Listeyi kontrol edip **yeşil** tuşla kurun.

Önizleme istemiyorsanız **Tek Tuşla Kur** okuma biter bitmez listeyi kurar.

Ana ekranda yön tuşlarıyla kartlar arasında gezinebilir, **1–8** tuşlarıyla kartları doğrudan açabilirsiniz. İşlem sırasında izlediğiniz kanal durdurulursa, işlem bitince geri açılır.

## Otomatik güncelleme

**Otomatik Güncelleme** kartından açılır. Önerilen ayar:

> **Her gün 04:00 · Yalnızca bekleme modunda · Yalnızca liste değiştiyse kur**

- İzlediğiniz yayın hiç kesilmez.
- Liste değişmediyse hiçbir dosyaya dokunulmaz.
- Kutu o saatte kapalıysa, açıldığında ilk fırsatta kontrol yapılır.
- Kayıt sürüyorsa kontrol ertelenir.

## Ayarlar

En çok kullanılanlar:

- **TKGS transponderı:** Otomatik ya da tek bir frekans
- **Kanal listesi:** HD veya SD sıralaması
- **Buket adı:** Kanal listesinde görünecek isim
- **Radyo buketi / Kategori buketleri:** Ek buketler oluşturur
- **Şifreli kanalları dahil et:** Kapalıysa şifreli kanallar bukete eklenmez
- **Ana menüde göster:** Ana Menü'ye kısayol ekler

## TKGS frekansları

Eklenti bu frekansları sırayla dener (PID 8181):

| Frekans | Polarizasyon | Sembol oranı |
|:---:|:---:|:---:|
| 12380 | Dikey | 27500 |
| 12423 | Dikey | 27500 |
| 12423 | Yatay | 30000 |
| 12458 | Dikey | 30000 |

Çanağınız yalnızca birini alıyorsa Ayarlar'dan o frekansı sabitleyebilirsiniz.

## Gereksinimler

- Türksat 42.0E tanımlı bir uydu tuneri (DVB-S/S2)
- OpenATV, OpenPLi, DreamOS veya benzeri bir Enigma2 imajı
- Python 2.7 ve Python 3 desteklenir; ARM ve MIPS işlemcilerde çalışır

Test edilen cihaz: Tüm cihaz ve imajlarda test edildi. Tamamında çalışıyor.

## Sorun giderme

**Kilit alınamıyor:** **Sinyal Testi** ile frekansları kontrol edin. Sinyal zayıfsa Ayarlar'dan **En uzun okuma süresi**'ni artırın.

**Eski listeye dönmek istiyorum:** **Buket ve Yedekler → Yedekten geri yükle**.

**Hata bildirmek istiyorum:**

1. **Ayarlar → Tanı kaydı**'nı açın.
2. Sorunu yeniden oluşturun.
3. `/home/root/logs/mstkgs_tani.log` dosyasını issue'ya ekleyin.

## Kaldırma

```sh
opkg remove enigma2-plugin-extensions-mstkgs
```

Kanal listeniz olduğu gibi kalır. TKGS buketlerini de silmek isterseniz önce eklentide **Buket ve Yedekler → TKGS buketlerini kaldır**'ı kullanın.

## Geliştirici

**Murat SEVER** · @muratsevercom

https://muratsever.com
