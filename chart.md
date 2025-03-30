``` mermaid
flowchart TD
Start([Başla])-->SU[Serbest Uçuş]
SU-->Tespit[Eğitilen yapay zeka modeline uygun bir iha ara]
Tespit-->bul{iha bulundu mu?}
bul-- evet --> konum[konumları al]
bul-- hayır -->Tespit
konum-->motor[Konum verilerini motora gönder]
motor-->hareket[Motoru hareket ettirerek hedef İHA'ya yakınlaş]
hareket-->uygun{Araç takibi yapay zeka modeli kriterlerine uygun mu?}
uygun-- hayır -->Tespit
uygun-- evet -->ilk{Rakip araca daha önce 4 saniye kilitlenildi mi?}
ilk-- evet -->Tespit
ilk-- hayır -->kilit1[Hedefe 4 saniye boyunca kilitlen]
kilit1-->sonuç{Kilitlenme başarılı mı?}
sonuç-- evet -->feedback[Bilgileri yer istasyonuna gönder]
sonuç-- hayır -->sorgu{bu işlem 4 kere gerçekleştirildi mi?}
sorgu-- hayır -->kilit1
sorgu-- evet -->Tespit
feedback-->SU
```