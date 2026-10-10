# makine-ogrenmesi-ve-segmentasyon
Scikit-Learn ile K-Means Kümeleme ve Müşteri Segmentasyonu Analitiği
# Müşteri Segmentasyonu ve Davranış Modellemesi (K-Means Clustering)

Bu proje; denetimsiz makine öğrenmesi (unsupervised learning) yöntemleri kullanılarak müşteri kitlelerinin yıllık gelir ve harcama dinamiklerine göre matematiksel olarak kümelenmesini, modelin metriklerle doğrulanmasını ve her segmente özel veri odaklı pazarlama stratejilerinin geliştirilmesini kapsayan uçtan uca bir veri bilimi çalışmasıdır.

---

## 🎯 Projenin Amacı ve İş Problemi
Pazarlama bütçelerinin tüm müşteri tabanına tek tip kampanya ile dağıtılması yüksek maliyet ve düşük dönüşüm oranı (conversion rate) üretir. Bu çalışmada amaç; müşterileri demografik ve finansal davranışlarına göre homojen alt gruplara ayırarak şirket kârlılığını maksimize edecek hedef odaklı kampanya ve kaynak tahsis stratejileri oluşturmaktır.

---

## 🛠️ Kullanılan Teknolojiler ve Kütüphaneler
* **Programlama Dili:** Python
* **Veri İşleme ve Agregasyon:** `pandas`, `numpy`
* **Görselleştirme:** `matplotlib`, `seaborn`
* **Makine Öğrenmesi & Doğrulama:** `scikit-learn` (`KMeans`, `silhouette_score`)

---

## 🔬 Metodoloji ve Analitik Adımlar

### 1. Keşifçi Veri Analizi ve Dağılım İncelemesi
* Müşterilerin yıllık gelirleri (`Yillik_Gelir_k$`) ve harcama skorları (`Harcama_Skoru_1_100`) üzerinden betimsel istatistikler ve sınır değerler analiz edildi.

### 2. Optimal Küme Sayısının Belirlenmesi (Elbow Method)
* 1'den 10'a kadar olan $k$ değerleri için küme içi kareler toplamı (WCSS - Within-Cluster Sum of Squares / Inertia) hesaplandı.
* Dirsek kırılma noktası analiz edilerek en yüksek varyans açıklayıcılığına sahip küme adedi **$k = 5$** olarak belirlendi.

### 3. K-Means Modellemesi ve Centroid Tespiti
* $k = 5$ parametresi ve `k-means++` başlangıç optimizasyonu ile model eğitildi.
* Her kümenin geometrik ağırlık merkezi (Centroids) hesaplanarak iki boyutlu saçılım grafiğinde görselleştirildi.

### 4. Matematiksel Model Doğrulama (Silhouette Score)
* Kümelerin birbirlerinden ayrışma kalitesini ve veri noktalarının kendi kümelerine olan yoğunluğunu test etmek için **Silhouette Skoru** hesaplandı.
* Elde edilen skor, kümeler arası sınırların net ve ayrımın istatistiksel olarak anlamlı olduğunu doğruladı.

### 5. Karar Destek ve Küme Profilleme (Cluster Profiling)
* Her segmentin müşteri hacmi, ortalama geliri ve harcama skoru çapraz tablolarla modellenerek karar vericiler için profil matrisi oluşturuldu.

---

## 📊 Segment Profili ve Stratejik Aksiyon Planı

| Segment Adı | Profil Tanımı | Önerilen Ticari Aksiyon |
| :--- | :--- | :--- |
| **Hedef Kitle (VIP)** | Yüksek Gelir / Yüksek Harcama | Lüks segment ürün lansmanları, özel sadakat programları ve kişisel portföy yöneticisi tahsisi. |
| **Potansiyel VIP** | Yüksek Gelir / Düşük Harcama | Yüksek satın alma gücünü harekete geçirecek kişiselleştirilmiş çapraz satış (cross-selling) ve özel davetler. |
| **Denge Grubu** | Orta Gelir / Orta Harcama | Sepet büyüklüğünü artırmaya yönelik hacim promosyonları (örn. 3 Al 2 Öde, ücretsiz kargo eşiği). |
| **Dürtüsel Tüketiciler** | Düşük Gelir / Yüksek Harcama | Flaş indirim bildirimleri, taksitli/esnek ödeme kurguları ve trend odaklı ürün önerileri. |
| **Düşük Öncelikli Grup** | Düşük Gelir / Düşük Harcama | Reklam bütçesinin optimize edilmesi; düşük maliyetli dijital bültenlerle pasif takip. |

---

## 🚀 Kurulum ve Çalıştırma

Projeyi yerel ortamınızda veya Google Colab üzerinde çalıştırmak için:

```bash
# Depoyu klonlayın
git clone [https://github.com/](https://github.com/)<kullanici-adiniz>/makine-ogrenmesi-ve-segmentasyon.git

# Gerekli kütüphaneleri yükleyin
pip install numpy pandas matplotlib seaborn scikit-learn
