---
name: triad-diff-debugger
description: Üçlü kırılım yöntemini (1. Ne değişti?, 2. Ne çalışıyor?, 3. Ne bozuldu?) kullanarak kök neden analizi ve arıza ayıklama yapar. Bozuk kodları onarırken, kesintileri incelerken, regresyonları çözerken veya sistem hatalarını teşhis ederken kullanın.
---
# Üçlü Kırılım Hata Ayıklayıcı (Triad Diff Debugger)

Hata ayıklama süreçlerinde tahmin yürütmeyi ve gereksiz kod değişikliklerini engelleyen; "1. Ne değişti?, 2. Ne çalışıyor?, 3. Ne bozuldu?" üçlü teşhis disiplinine dayanan kök neden analiz çerçevesi.

## Ne Zaman Kullanılır?

- Daha önce çalışan bir uygulama, servis veya özellik aniden bozulduğunda ya da kararsızlaştığında
- Git diff'leri, başarısız dağıtımlar (deploy) veya beklenmeyen regresyon test sonuçları incelenirken
- Karmaşık log kayıtları, yığın izleri (stack trace) veya sessiz çökmeler analiz edilirken
- Olay sonrası kök neden raporu (post-mortem) hazırlanırken

## Üç Teşhis Ayağı

### 1. Ayak: Ne Değişti? (What Changed?)
- Son kod değişiklikleri, birleştirilen PR'lar ve Git diff'leri incelenir.
- Yapılandırma dosyaları, ortam değişkenleri (env vars) ve gizli anahtarlar kontrol edilir.
- Bağımlılık güncellemeleri, derleyici/çalışma zamanı sürüm yükseltmeleri denetlenir.
- Altyapı değişiklikleri (DNS, TLS sertifikaları, güvenlik duvarı kuralları, bulut sağlayıcı olayları) taranır.
- Gelen veri şemalarındaki veya trafik hacmindeki değişimler tespit edilir.

### 2. Ayak: Ne Çalışıyor? (What is Still Working?)
- Sorundan etkilenmeyen sağlıklı modüller ve uç noktalar belirlenir.
- Başarıyla yanıt veren veritabanı bağlantıları ve sağlık kontrolleri (health check) doğrulanır.
- Girdinin hala doğru işlendiği son sınır çizgisi saptanır.
- Bu sınır, sorunun NEREDE OLMADIĞINI kesinleştirerek arama alanını daraltır.

### 3. Ayak: Ne Bozuldu? (What is Broken?)
- Kesin hata mesajı, yığın izi, HTTP durum kodu veya çökme günlüğü çıkarılır.
- Hatanın tetiklendiği tam kod satırı, sorgu veya ağ paketi belirlenir.
- Hatayı yeniden üreten en küçük senaryo (curl komutu, birim test veya yük verisi) oluşturulur.

## Çözüm Protokolü

1. "Ne Değişti" verisini "Ne Bozuldu" bulgusuyla çakıştırarak nedensellik bağı kur.
2. En güçlü tek bir kök neden hipotezi formüle et.
3. İlgisiz kodlara dokunmayan, minimal ve cerrahi bir düzeltme öner.
4. Düzeltmeyi doğrulayan bir regresyon testi sağla.

## Dikkat Edilecek Noktalar (Gotchas)

- Üç teşhis ayağı tamamlanmadan asla ezbere çözüm veya yama önerme.
- Görünen hata mesajını doğrudan kök neden sanma; mesajın bir üst akıştaki durum değişikliğinin belirtisi olup olmadığını doğrula.
