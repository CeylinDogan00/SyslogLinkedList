# SyslogLinkedList
Veri Yapıları ve Algoritmalar Final Degerlendirme Ödevi-2

Proje Hakkinda
Sistem gunlukleri (syslog), bir isletim sisteminin saglik durumunu, guvenlik olaylarini ve hata kayitlarini tutan kritik bir mekanizmadir. Bu projede, /var/log/syslog formatindaki veriler ele alinmis ve bellek verimliligini optimize etmek adina bagli liste mimarisiyle islenmistir.

Temel Ozellikler
Dinamik Bellek Yonetimi: malloc ve free fonksiyonlari ile sistem kaynaklari sadece ihtiyac duyuldugunda kullanilir.
Veri Ayristirma (Parsing): Ham log satirlari sscanf ile anlamli parcalara (tarih, host, servis, mesaj) bolunur.
Kronolojik Siralama: Veriler, log akisina uygun olarak listenin sonuna eklenir.

Teknik Mimari
Syslog Veri Yapisi
Log verileri su formatta islenmektedir:
Ay | Gun | Saat | Makine Adi | Servis[PID] | Mesaj

Bagli Liste Yapisi
Projede Tek Yonlu Bagli Liste kullanilmasinin nedenleri:
Sira Uyumlulugu: Loglarin dogal zaman akisina uygun tek yonlu ilerleyis.
Hafiza Tasarrufu: Cift yonlu listelere gore %10-15 daha az pointer maliyeti.
Esneklik: Belirsiz veri boyutu karsisinda dizilerin aksine sabit maliyetle buyume.
