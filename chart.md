``` mermaid
flowchart TD
Start([Başla])-->SU[Serbest Uçuş]
SU-->Tespit{İHA konumları alındı mı?}
Tespit-- evet -->uygun{Yakınlarda takibe uygun İHA var mı?}
Tespit-- hayır --> SU
uygun-- evet --> yaklaş[Rakip araca yakınlaş]
uygun-- hayır -->SU
yaklaş-->kilit{Araç kilitlenebilir mi?}
kilit-- hayır -->uygun
kilit-- evet -->ilk{Rakip araca daha önce 4 saniye kilitlenildi mi?}
ilk-- evet -->Tespit
ilk-- hayır -->kilit1[Hedefe 4 saniye boyunca kilitlen]
kilit1-->sonuç{Kilitlenme başarılı mı?}
sonuç-- evet -->feedback[Bilgileri yer istasyonuna gönder]
sonuç-- hayır -->sorgu{bu işlem 4 kere gerçekleştirildi mi?}
sorgu-- hayır -->kilit1
sorgu-- evet -->uygun
feedback-->SU
```