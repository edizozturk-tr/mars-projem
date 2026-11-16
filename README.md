# Mars Kolonisi Yaşam Destek Simülatörü 🚀

> Algoritma ve Programlama dersi kapsamında C programlama dili ile geliştirilmiş, metin tabanlı ve karakter kontrollü hayatta kalma simülasyonu.

---

## 📋 Proje Hakkında
Bu proje, Mars'taki bir araştırma istasyonunda mahsur kalan bir mühendisin hikayesini konu alır[span_0](start_span)[span_0](end_span). Oyuncu, kurtarma ekibi gelene kadar (**15. günü tamamlayana kadar**) sınırlı kaynaklarını (`sağlık`, `enerji`, `oksijen`, `su`, `yedek parça`) yöneterek hayatta kalmaya çalışır[span_1](start_span)[span_1](end_span). Tüm akış C dilinin temel kontrol yapıları, döngüleri ve operatörleri kullanılarak konsol ortamında simüle edilmiştir[span_2](start_span)[span_2](end_span).

---

## ⚙️ Oyun Mekanikleri ve Komut Sistemi
Oyun sırasında her tur oyuncudan tek karakterlik bir komut alınır ve `switch-case` yapısı ile işlenir[span_3](start_span)[span_3](end_span). Komutlar büyük/küçük harf duyarsızdır (örn. `g` veya `G`)[span_4](start_span)[span_4](end_span).

| Komut | İşlev Açıklaması |
| :---: | :--- |
| **G** | **Keşif Görevi:** Enerji ve oksijen tüketir; mantıksal operatörler ve rastgele sayılarla su, yedek parça bulma veya yaralanma durumlarını hesaplar[span_5](start_span)[span_5](end_span). |
| **O** | **Oksijen Üretimi:** Su ve enerji harcayarak oksijen üretir (2 birim su = 3 birim oksijen). Mod operatörü ile artık kontrolü yapılır[span_6](start_span)[span_6](end_span). |
| **T** | **Tamir:** Yedek parça kullanarak modül hasarını kademeli (`if-else if`) olarak azaltır[span_7](start_span)[span_7](end_span). |
| **D** | **Durum Raporu:** Tüm değişkenleri, kritik uyarıları veya güvenli sistem durumunu ekrana yazdırır (tur harcamaz)[span_8](start_span)[span_8](end_span)[span_9](start_span)[span_9](end_span). |
| **U** | **Uyu / Dinlen:** Enerji ve sağlık değerlerini artırır; oksijen tüketimi devam eder (iç içe `if` kontrolleri içerir)[span_10](start_span)[span_10](end_span). |
| **K** | **Kum Fırtınası (`for` döngüsü):** Zorluk derecesine göre tur sayısı belirlenen fırtınayı simüle eder[span_11](start_span)[span_11](end_span). Çift turlarda hasar katlanır[span_12](start_span)[span_12](end_span). |
| **H** | **Hava Kilidi Şifresi (`do-while` döngüsü):** Gün sayısından türetilen şifreyi 3 denemede çözme mekanizmasıdır[span_13](start_span)[span_13](end_span)[span_14](start_span)[span_14](end_span). |
| **Q** | **Çıkış:** Oyunu sonlandırır ve detaylı sonuç raporunu görüntüler[span_15](start_span)[span_15](end_span). |

---

## 🛠️ Teknik Altyapı ve Kullanılan C Yapıları

* **Kontrol Yapıları:** Zorluk seçimi ve komut yönlendirmeleri için `switch-case` (fall-through destekli) ve `if-else if-else` kademeleri[span_16](start_span)[span_16](end_span)[span_17](start_span)[span_17](end_span).
* **Döngüler:** 
  * `do-while` döngüsü ile ana oyun akışı ve sınırlı hak içeren şifre doğrulama mekanizmaları[span_18](start_span)[span_18](end_span)[span_19](start_span)[span_19](end_span)[span_20](start_span)[span_20](end_span).
  * `for` döngüsü ile kum fırtınası turlarının yönetimi (`break` ve `continue` komutları ile)[span_21](start_span)[span_21](end_span).
* **Rastgelelik:** `srand(time(NULL))` ve `rand() % 100` fonksiyonları ile her kritik kararda zar atılması ve ekrana eşik değerlerin yansıtılması[span_22](start_span)[span_22](end_span)[span_23](start_span)[span_23](end_span).
* **Aritmetik ve Mantıksal Operatörler:** Mod (`%`) operatörü ile su artıkları, çift tur kontrolü ve karmaşık mantıksal bağlaçlar (`&&`, `||`)[span_24](start_span)[span_24](end_span)[span_25](start_span)[span_25](end_span).

---

## 🚀 Kurulum ve Çalıştırma

Projeyi derlemek ve çalıştırmak için bilgisayarınızda bir C derleyicisi (GCC vb.) kurulu olmalıdır.

1. Depoyu klonlayın:
   ```bash
   git clone [https://github.com/KULLANICI_ADI/mars-kolonisi-simulatoru.git](https://github.com/KULLANICI_ADI/mars-kolonisi-simulatoru.git)
