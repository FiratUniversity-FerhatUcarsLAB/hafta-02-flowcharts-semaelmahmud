Başlat

Tanımla: sepet = boş liste

Fonksiyon: ürünEkle(sepet, ürün)
    Eğer ürün zaten sepette varsa
        ürün.adet += 1
    Aksi halde
        sepete ürünü ekle (adet = 1)
    Son

Fonksiyon: ürünÇıkar(sepet, ürün)
    Eğer ürün sepette varsa
        Eğer ürün.adet > 1 ise
            ürün.adet -= 1
        Aksi halde
            ürünü sepetten kaldır
    Son

Fonksiyon: sepetiGörüntüle(sepet)
    Eğer sepet boşsa
        Yazdır "Sepetiniz boş."
    Aksi halde
        Her ürün için sepette:
            Yazdır ürün adı, fiyatı, adet
        Son

Fonksiyon: toplamTutar(sepet)
    toplam = 0
    Her ürün için sepette:
        toplam += ürün.fiyat * ürün.adet
    Son
    Dön toplam

Fonksiyon: ödemeYap(sepet)
    toplam = toplamTutar(sepet)
    Eğer toplam > 0 ise
        Yazdır "Toplam tutar:", toplam
        Yazdır "Ödeme başarılı!"
        sepeti temizle
    Aksi halde
        Yazdır "Sepetiniz boş. Ödeme yapılamaz."

--- Ana Program ---

Tekrarla:
    Yazdır "[1] Ürün Ekle"
    Yazdır "[2] Ürün Çıkar"
    Yazdır "[3] Sepeti Görüntüle"
    Yazdır "[4] Ödeme Yap"
    Yazdır "[5] Çıkış"
    
    Kullanıcıdan seçim al

    Seçim == 1 ise:
        Kullanıcıdan ürün bilgisi al
        ürünEkle(sepet, ürün)
    Seçim == 2 ise:
        Kullanıcıdan çıkarılacak ürünü al
        ürünÇıkar(sepet, ürün)
    Seçim == 3 ise:
        sepetiGörüntüle(sepet)
    Seçim == 4 ise:
        ödemeYap(sepet)
    Seçim == 5 ise:
        Döngüden çık

Son
