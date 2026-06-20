Bu proje, **STM32 (F303K8T6)** mikrodenetleyicisi kullanılarak geliştirilmiş akıllı bir araç projesidir. Araç, HC-05 modülü üzerinden gelen Bluetooth komutlarıyla manuel olarak kontrol edilebilirken, önündeki engelleri ultrasonik sensör ile algıladığında **otomatik olarak durur ve sesli uyarı (Buzzer)** verir.

Mikroişlemci Sistemleri dersi kapsamında gömülü sistem mimarisi, gerçek zamanlı sensör entegrasyonunu uygulamak amacıyla geliştirilmiştir.

## Özellikler

*   **Kablosuz Kontrol:** HC-05 Bluetooth modülü üzerinden akıllı telefon veya seri terminal ile tam kontrol (İleri, Geri, Sağ, Sol, Dur).
*   **Güvenli Fren Sistemi:** Ultrasonik sensör (HC-SR04) ile sürekli mesafe ölçümü; engel algılandığında aracı anında durdurma.
*   **Sesli Geri Bildirim:** Engel mesafesine girildiğinde aktif olan sesli uyarı sistemi (Buzzer).
*   **Zamanlayıcı Tabanlı Motor Yönetimi:** Hız ve yön kontrolü için donanımsal Timer PWM sinyalleri.

## Kullanılan Donanım Bileşenleri

*   **Mikrodenetleyici:** STM32F303K8T6
*   **Mesafe Sensörü:** HC-SR04 Ultrasonik Sensör
*   **Kablosuz Haberleşme:** HC-05 Bluetooth Modülü
*   **Ses Modülü:** Aktif/Pasif Buzzer (Sesli Uyarı için)
*   **Motor Sürücü:** L298N Çift Motor Sürücü Kartı
*   **Şasi:** 2 veya 4 Tekerlekli Robot Şasisi + DC Motorlar
*   **Güç Kaynağı:** Li-ion / Li-po Piller


## Çalışma Mantığı

1.  **Manuel Kontrol:** Kullanıcı Bluetooth üzerinden yön komutu gönderdiğinde araç o yönde hareket eder.
2.  **Mesafe Kontrolü:** Araç hareket halindeyken ultrasonik sensör sürekli olarak önündeki mesafeyi ölçer.
3.  **Güvenlik Protokolü:** Mesafe kritik eşiğin (Örn: 20 cm) altına düştüğü anda, Bluetooth'tan gelen hareket komutları bypass edilir; **araç otomatik olarak DURUR ve buzzer üzerinden sesli uyarı vermeye başlar.** Engel ortadan kalktığında sistem normal çalışmasına döner.
