İsim - Soy isim Sema Elmahmud 
Öğrenci No:250541618

BAŞLA

// 1. Kart ve PIN kontrolü
Kartı_tak()
PIN = PIN_kodu_gir()

EĞER PIN DOĞRUysa
    DEVAM ET
DEĞİLSE
    HATALI_PIN_MESAJI_VER()
    TEKRAR_DENEME_YA_DA_SONU()
    BİTİR

// 2. Ana menü
MENÜYÜ_GÖSTER()
SEÇİM = KULLANICI_SEÇİMİ_AL()

EĞER SEÇİM = "Para Çekme" İSE
    PARA_CEKME_ISLEMI()
EĞER SEÇİM = "Bakiye Sorgulama" İSE
    BAKIYEYI_GÖSTER()
EĞER SEÇİM = "Çıkış" İSE
    KARTI_IADE_ET()
    BİTİR

// 3. Para çekme işlemi
FONKSİYON PARA_CEKME_ISLEMI()
    TUTAR = PARA_TUTARINI_GİR()
    
    EĞER TUTAR > GÜNCEL_BAKİYE İSE
        YETERSİZ_BAKİYE_MESAJI_VER()
    DEĞİLSE
        BAKİYEYİ_GÜNCELLE(BAKİYE - TUTAR)
        PARA_VER(TUTAR)
        İŞLEM_ONAY_MESAJI_VER()

    DEVAM_ETMEK_İSTER_MİSİN_SOR()
    EĞER EVET İSE
        MENÜYÜ_GÖSTER()
    DEĞİLSE
        KARTI_IADE_ET()
        BİTİR
SON

BİTİR

Açıklamalar:

Kartı_tak(): Kullanıcının ATM’ye kartını takması.

PIN_kodu_gir(): PIN giriş ekranı.

MENÜYÜ_GÖSTER(): Ana menü seçeneklerinin kullanıcıya sunulması (para çekme, bakiye sorgulama, çıkış vb.).

BAKIYEYİ_GÜNCELLE(): Bakiyeden çekilen tutarın düşülmesi.

PARA_VER(): ATM’nin fiziki olarak parayı vermesi.

KARTI_IADE_ET(): İşlem sonunda kartın iade edilmesi.

BİTİR: Programın sonlandırılması.
