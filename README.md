# ⚡ EPİAŞ Gerçek Zamanlı Akış Simülasyonu ve Anomali Tespiti

Bu proje, **EPİAŞ Şeffaflık Platformu** üzerinden (`eptr2` kütüphanesi ile) gerçek zamanlı elektrik tüketimi ve yenilenebilir üretim verilerini çekerek, veriyi zaman serisi tabanlı bir **akış simülasyonu** (streaming simulation) ile işler ve **kayan pencere (rolling window)** yöntemiyle ani yük sıçramalarını (anomalileri) tespit eder. Sonuçlar CSV dosyasına, grafik görsellerine ve isteğe bağlı olarak veritabanına aktarılır.

---

## 🚀 Proje Akışı ve Mimari

1. **Veri Çekme:** EPİAŞ API'si kullanılarak son 2 haftalık (`14 gün` / `336 saat`) saatlik tüketim (`rt-cons`) ve üretim (`rt-gen`) verileri çekilir.
2. **Akış Simülasyonu:** Python (`pandas`) yardımıyla veri kronolojik sırayla satır satır okunarak canlı bir veri akış ortamı simüle edilir.
3. **Anomali Tespiti:** 24 saatlik kayan pencere (rolling window) hareketli ortalama ve standart sapma kullanılarak güven aralığı üst sınırları hesaplanır. Bu sınırları aşan ani tüketim sıçramaları anomali olarak işaretlenir.
4. **Dışa Aktarım:** Elde edilen sonuçlar raporlama için CSV dosyasına kaydedilir ve Matplotlib ile görselleştirilerek grafik olarak dışa aktarılır.

---

## 🛠️ Kullanılan Teknolojiler ve Kütüphaneler

* **Python 3.x**
* **Pandas & NumPy** (Veri manipülasyonu ve istatistiksel hesaplamalar)
* **EPTR2** (EPİAŞ Şeffaflık Platformu API İstemcisi)
* **Matplotlib** (Zaman serisi ve anomali görselleştirme)
* **Google Colab / Jupyter Notebook**

---

## 📂 Dosya Yapısı

* `epias_analiz.ipynb` : Veri çekme, simülasyon ve anomali tespiti adımlarını içeren ana Jupyter Notebook dosyası.
* `epias_temiz_anomaliler.csv` : Anomali etiketleri eklenmiş işlenmiş veri seti.
* `epias_anomali_grafigi.png` : Tüketim eğrisi, kayan ortalama ve anomalilerin gösterildiği görselleştirme.

---

## 📊 Örnek Görselleştirme

> Proje sonucunda üretilen anomali tespit grafiği:
> *Mavi Çizgi:* Gerçek Elektrik Tüketimi  
> *Turuncu Kesikli Çizgi:* 24 Saatlik Kayan Ortalama  
> *Kırmızı Noktalar:* Ani Yük Sıçramaları (Anomaliler)  

---
