# epias-anomaly-detection
Bu proje, açık şebeke verileri (EPİAŞ) üzerinde **akış simülasyonu (Streaming Simulation)** mantığıyla çalışan ve **kayan pencere (Rolling Window)** istatistiksel yöntemini kullanarak elektrik yükündeki ani sıçramaları / düşüşleri anomali olarak tespit eden bir zaman serisi analiz aracıdır.
## 📊 Proje Mimarisi ve Akışı
1. **Veri Akışı Simülasyonu:** Zaman serisi verileri, gerçek dünya akış sensörlerini simüle edecek şekilde satır satır işlenir.
2. **Dinamik Kayan Pencere:** 24 saatlik hareketli ortalama (`Rolling Mean`) ve standart sapma (`Rolling Std`) kullanılarak normal çalışma bandı (`±2.5 Std`) hesaplanır.
3. **Z-Score Tabanlı Anomali Tespiti:** Beklenen bandın dışına çıkan ani yük değişimleri istatistiksel olarak yakalanır.
4. **Çok Katmanlı Görselleştirme:** Tüketim bantları ve anomali şiddet trendleri profesyonel bir gösterge paneli (dashboard) halinde raporlanır.

---

## 📈 Analitik Görselleştirme (Örnek Çıktı)

> Aşağıdaki grafik, 672 saatlik (4 haftalık) simülasyon verisi üzerinde tespit edilen yük anomalilerini ve sapma şiddetlerini (Z-Score) göstermektedir.

![Gelişmiş Anomali Analizi](gelismis_anomali_analizi.png)

---

## 🛠️ Kullanılan Teknolojiler ve Kütüphaneler
- **Python** (Core Logic)
- **Pandas** (Zaman serisi manipülasyonu ve kayan pencere hesaplamaları)
- **NumPy** (Matematiksel ve istatistiksel işlemler)
- **Matplotlib** (Çok panelli gelişmiş veri görselleştirme)

---

## 🚀 Projeyi Çalıştırma Adımları

1. Depoyu klonlayın veya Google Colab ortamında açın.
2. Gerekli kütüphaneleri yükleyin:
   ```bash
