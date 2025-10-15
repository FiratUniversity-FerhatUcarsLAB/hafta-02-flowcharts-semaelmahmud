Başla

// Sistem durumları
Durum = "Pasif"
AlarmDurumu = "Kapalı"

// Sensörlerden gelen veriler
HareketAlgilandi = false
KapiPencereAcildi = false

// Fonksiyonlar
Fonksiyon HareketAlgilama()
    Eğer hareket sensörü aktif ise
        HareketAlgilandi = true
    Aksi halde
        HareketAlgilandi = false
    Bitir

Fonksiyon KapiPencereKontrol()
    Eğer kapı/pencere sensörü açık ise
        KapiPencereAcildi = true
    Aksi halde
        KapiPencereAcildi = false
    Bitir

Fonksiyon AlarmCalistir()
    AlarmDurumu = "Açık"
    BildirimGonder("Alarm Çaldı! Olası izinsiz giriş.")
    // Diğer güvenlik önlemleri burada (örneğin siren, kamera kaydı başlatma)
    Bitir

Fonksiyon BildirimGonder(mesaj)
    // Kullanıcıya SMS, e-posta veya mobil uygulama bildirimi gönder
    Yazdır(mesaj)
    Bitir

// Ana döngü
Sürekli olarak
    HareketAlgilama()
    KapiPencereKontrol()

    Eğer Durum == "Aktif" ise
        Eğer HareketAlgilandi veya KapiPencereAcildi ise
            AlarmCalistir()
        Sonuç

    Bekle(1 saniye)
Bitir
