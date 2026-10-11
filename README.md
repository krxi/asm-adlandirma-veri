# asmsense-data

asmsense için eğitim verisi arşivleri (release). Satırlar kaynak projelerin lisansına tabidir; bkz. ana depo veri/LISANSLAR.md.

Kod, veri hattı ve sonuçlar: [krxi/asmsense](https://github.com/krxi/asmsense). Ham v4 fonksiyon tablosu Hugging Face'te: [krxi123/asmsense](https://huggingface.co/datasets/krxi123/asmsense).

## Release künyesi

Her satırdaki SHA-256, GitHub'ın asset digest'iyle eşleşen indirilmiş arşivden hesaplandı (2026-10-11). Satır sayıları arşivin içinden sayıldı.

| Release | Arşiv | Boyut | Arşiv SHA-256 |
|---|---|---:|---|
| [v4](https://github.com/krxi/asmsense-data/releases/tag/v4) | `veri-olcek-v4.zip` | 45.512.203 B | `39b440c5b9a02cfa287a2c6acf1a39ee0dd98c993570df795aded7eeac2d1609` |
| [v5](https://github.com/krxi/asmsense-data/releases/tag/v5) | `veri-v5.zip` | 52.009.068 B | `d907792492dff79523035d4825b21ea190424cea633f0c052d38a54a7f6effd3` |
| [v6](https://github.com/krxi/asmsense-data/releases/tag/v6) | `veri-v6.zip` | 80.312.558 B | `e1286104e59860a34fc18fe908ccadc3896b4db40fe1a5a75253aa9cc7a8c201` |

### v4: sohbet biçiminde ölçek verisi

| Dosya | Satır | SHA-256 |
|---|---:|---|
| `train.jsonl` | 138.486 | `6b2ff4f0d10c0fc2065e5190a4a99b03cc27f89f91e94cdae14771b3069f2950` |
| `valid.jsonl` | 18.030 | `1778c2c658be73827eb6b986360a4463f9c312e40a4d1f6dbba7fa05212fd374` |
| `test.jsonl` | 11.641 | `b2219613685b4bbd127ba08512d3e42f787d9fa34091ad770a1c5254c933b5ca` |
| `eval115.jsonl` | 115 | `33b778de4b3cbd803c41d87a55d92be9897b5e8dc2b116694e5db4c5a350280b` |

### v5: açıklama_en → ad → açıklama hedefi

| Dosya | Satır | SHA-256 |
|---|---:|---|
| `train.jsonl` | 95.000 | `d54cab265e131812d44b2cb86f3c50cb5f985d2ab5becaa81497b72e64eccc93` |
| `valid.jsonl` | 19.770 | `b13bf1fc95b8e531c23ba575b007bc862651824961e6429c09395a0a90787567` |
| `valid_300.jsonl` | 300 | `45ed0960b03453f6a2eb45a118cc68bff3ff50ae22afec1849d023633dea90ad` |
| `test.jsonl` | 12.290 | `273f1f27129f3c9b99eb86776ca281197b7487153f46c13130b691263c2cfeb4` |
| `test_sabit.jsonl` | 2.000 | `f49207ba89b0eb0f23058a65d40becad831230163a6f1d020119db336a627cc4` |
| `eval115.jsonl` | 115 | `8dac78d550613ea06bed01aa79a296ec96c62e74d47ad0be92d929f8e00987f8` |

### v6: v5 girdisi + Ghidra decompile

| Dosya | Satır | Decompile olan | SHA-256 |
|---|---:|---:|---|
| `train.jsonl` | 95.000 | 94.738 | `b4ce965f8977258c8408ca78bdbb0393c34cf53d909eb9c5e291629d64c42b35` |
| `valid.jsonl` | 19.770 | 19.738 | `c10c7574462bf8607c085ed1511b34340e413e63db3445f24c5e235bfcba77d7` |
| `valid_300.jsonl` | 300 | 299 | `1148a533d05b044624e99d5a74dc43f6b481523dda61e8fbfc4f93ff77010256` |
| `test.jsonl` | 12.290 | 12.278 | `079711c586d47ad8cdefe1102aed351aefe5cac0857fa8b3f90972dd2ab4cbf4` |
| `test_sabit.jsonl` | 2.000 | 1.999 | `4ad04cd5b904a91a77d417b2a427ccb053bffe502368ecb182d293be84fcc586` |
| `eval115.jsonl` | 115 | 115 | `e9fa2f5747eda8a2b78fb614548182da869e87a0b32508e6d26f6c9527922b12` |

v6 release notundaki "test_sabit 1.999, valid_300 299" decompile kapsamıdır; satır sayıları v5 ile aynıdır (2.000 ve 300). Decompile'ı olmayan satırlarda ana hat hedef ad sızıntısı bulduğu için decompile'ı girdiden çıkarmıştır.

v5 ve v6 satırları birebir hizalıdır: aynı kimlik, sıra, metaveri ve hedef; v6 kullanıcı metni decompile bölümünden önce v5 ile aynıdır (95.000 train + 300 valid satırında denetlendi).

## Bilinen sınır

Test projesi `snkv`, eğitimdeki `sqlite` projesini kendi dosya adlarıyla gömer: `test_sabit`'in 217 satırının (%10,85) adı bir SQLite eğitim fonksiyonuyla aynıdır. Ayrıntı ve etki: [rapor/arastirma/V6_VERI_DENETIMI.md](https://github.com/krxi/asmsense/blob/main/rapor/arastirma/V6_VERI_DENETIMI.md).

## Atıf ve DOI

`CITATION.cff` atıf bilgisini, `.zenodo.json` Zenodo–GitHub entegrasyonunun metaverisini taşır. Entegrasyon açıldığında (Zenodo → GitHub → bu depoyu etkinleştir) sonraki her release kalıcı bir DOI alır.

Lisans alanı bilerek boş bırakıldı: satırlar farklı izin verici lisanslara tabi. Zenodo kaydında lisansı "Other (Open)" seçin ve ana depodaki veri/LISANSLAR.md'ye bağlantı verin.
