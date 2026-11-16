Mars Kolonisi Yaşam Destek Simülatörü (C ile Metin Tabanlı Oyun)
Bu depo, Algoritma ve Programlama dersi kapsamında geliştirilen, C dilinin temel yapılarını (koşullu ifadeler, döngüler, aritmetik ve mantıksal operatörler) kullanarak tasarlanmış metin tabanlı bir Mars Kolonisi Yaşam Destek Simülatörüdür.
Proje, Mars'taki bir araştırma istasyonunda mahsur kalan bir mühendisin, kurtarma ekibi gelene kadar (15. günü tamamlayana kadar) kaynaklarını (sağlık, enerji, oksijen, su, yedek parça) yöneterek hayatta kalmasını hedefler.
🚀 Proje Özellikleri ve Teknik Yapısı
Kod mimarisi, proje dokümanında belirtilen kısıtlamalar ve algoritmik gereksinimler doğrultusunda modüler ve anlaşılır bir yapıda tasarlanmıştır:
Komut Sistemi (SWITCH-CASE & Fall-Through):
Oyuncu komutları büyük/küçük harf duyarsız olarak (g/G şeklinde) işlenir. Bu yapı, switch-case bloklarında fall-through (ardışık durum birleştirme) mekanizması kullanılarak sağlanmıştır.
Tanımsız girişlerde default bloğu tetiklenir, kullanıcı uyarılır ve bu durum tur/süre harcamaz.
Aritmetik ve Mantıksal İşlemler:
Keşif (G): Enerji ve oksijen tüketir; rand() % 100 ve mantıksal operatörler (&&, ||) yardımıyla su, yedek parça bulma veya yaralanma ihtimallerini hesaplar.
Oksijen Üretimi (O): Su ve enerji dönüşümünü aritmetik işlemlerle yapar. Mod operatörü (%) ile suyun çift/tek durumunu kontrol ederek artıkları depoda tutar.
Tamir (T): Modül hasarını IF-ELSE IF kademelerine (0-30, 31-70, 71-100) ayırarak yedek parça tüketimi karşılığında onarır.
Dinlenme (U): İç içe IF yapıları ile oksijen seviyesinin 20'nin altında olup olmadığını kontrol ederek sağlık ve enerji artışını düzenler.
Gelişmiş Döngü Kullanımları (FOR & DO-WHILE):
Kum Fırtınası Simülasyonu (FOR): Zorluk seviyesine göre (Kolay: 3, Normal: 5, Zor: 7 tur) çalışır. Çift numaralı turlarda mod operatörü (% 2 == 0) ile rüzgar şiddeti artırılarak hasar iki katına çıkarılır. break ile acil çıkış, continue ile hava kilidi mühürlüyse oksijen sızıntısının atlanması sağlanır.
Hava Kilidi Şifresi (DO-WHILE): Gün sayısından aritmetik olarak türetilen ('A' + (gun % 26)) büyük harf şifreyi çözmek için en fazla 3 deneme hakkı sunar. Yanlış denemelerde "ileri git" / "geri git" yönlendirmeleri yapılır.
Durum Yönetimi ve Zaman Akışı:
Sağlık, enerji, oksijen, su, yedek parça, modül hasarı ve kilit durumu 0-100 arasında sınırlandırılmıştır.
Her 3 turda bir (tur % 3 == 0) yeni gün başlar; oksijen azalması ve kritik hasar durumlarında ek sağlık kayıpları işlenir.
Oyun sonunda formüle dayalı kapsamlı bir başarı puanı hesaplanır (Puan = (gun × 100) + saglik + oksijen - modulHasari).
🛠️ Kullanılan Kütüphaneler
Kod içerisinde temel G/Ç, rastgele sayı üretimi ve zaman fonksiyonları için şu kütüphaneler yer almaktadır:
#include <stdio.h> -> Ekrana yazdırma ve klavyeden okuma işlemleri için.
#include <stdlib.h> -> Rastgele sayı üretimi (rand()) için.
#include <time.h> -> Zaman tabanlı tohumlama (srand(time(NULL))) için.
💻 Kurulum ve Çalıştırma
Projeyi yerel bilgisayarınıza klonlamak ve çalıştırmak için terminal veya komut satırında şu adımları takip edebilirsiniz:
