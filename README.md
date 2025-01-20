# Yaşam Beklentisi Tahmini Makine Öğrenimi Projesi

Bu proje, yaşam beklentisi tahminini gerçekleştiren bir makine öğrenimi modelinin geliştirilmesi sürecini içermektedir. Proje boyunca veri temizleme, görselleştirme ve farklı makine öğrenimi modellerinin test edilmesi adımları izlenmiştir.

## Proje Adımları

### 1. Veri Temizleme
Veri seti üzerinde aşağıdaki işlemler gerçekleştirilmiştir:
- **Eksik Verilerin Doldurulması:** Boşluklar null değerlerle doldurulmuştur.
- **Outlier İşlemi:** Anormal veriler tespit edilip gerekli işlemler uygulanmıştır.
-  **Label Encoding İşlemi:** Kategorik verilerin sayısal verilere dönüştürülmesi.

### 2. Korelasyon Analizi ve Görselleştirme
Veri setindeki değişkenler arasındaki ilişkiler korelasyon analizi ile incelenmiş ve sonuçlar bir histogram grafiği ile görselleştirilmiştir.

### 3. Modellerin Eğitilmesi
Aşağıdaki beş farklı makine öğrenimi modeli kullanılmıştır:
- **Linear Regression Modeli**
- **Random Forest Modeli**
- **K-en yakın Komşu Modeli (KNN)**
- **Support Vector Regresyon Modeli (SVR)**
- **XGBoost Modeli**

## Model Grafiklerinin Açıklamaları:

**Linear Regression Modeli**

Linear Regression, bağımsız ve bağımlı değişkenler arasındaki doğrusal ilişkiyi analiz eder. Grafikte, gerçek ve tahmin edilen değerlerin ilişkisi gösterilir. Noktaların doğrusal bir çizgi etrafında yoğunlaşması, modelin iyi performans sergilediğini gösterir. Ancak doğrusal olmayan ilişkilerde performansı sınırlı olabilir.

**Random Forest Modeli**

Random Forest, birden fazla karar ağacı kullanarak tahmin yapar ve aşırı öğrenmeyi önler. Grafikte, gerçek ve tahmin edilen değerlerin yoğunlaşması modelin başarısını gösterir. Model dengeli tahminler sunsa da açıklanabilirliği düşüktür ve hiperparametre ayarları performansı etkiler.

**K-Nearest Neighbors (KNN) Modeli**

KNN, veri noktalarının komşularına göre tahmin yapar. Grafikte, noktaların yoğunlaşması modelin doğruluğunu gösterir. Performans, komşu sayısına ve veri setinin yapısına bağlıdır. Büyük veri kümelerinde hesaplama maliyeti yükselebilir.

**Support Vector Regression (SVR) Modeli**

SVR, veriyi en iyi temsil eden hiper düzlemi oluşturarak tahmin yapar. Grafikte, noktaların yoğunlaşması modelin başarısını gösterir. SVR, küçük veri kümelerinde iyi çalışsa da büyük veri setlerinde hesaplama süresi artabilir.

**XGBoost Modeli**

XGBoost, karar ağaçlarını optimize eden güçlü bir algoritmadır. Grafikte, noktaların doğrusal bir çizgi etrafında yoğunlaşması modelin başarısını gösterir. Büyük veri setlerinde yüksek doğruluk sağlar ancak hiperparametre ayarları dikkatli yapılmalıdır.


## Kullanılan Kütüphaneler
- Pandas
- Numpy
- Matplotlib
- Seaborn
- Scikit-learn
- XGBoost

## Sonuçlar
Projede kullanılan beş farklı makine öğrenimi modeli, yaşam beklentisi tahminini başarıyla gerçekleştirmiştir. Modellerin performansları, doğru parametrelerle optimize edilerek test edilmiştir. Sonuçlar görselleştirildiğinde:

- XGBoost Modeli en yüksek doğrulukla tahminler sağlamıştır.
- Random Forest Modeli de başarılı bir performans sergileyerek güvenilir tahminler üretmiştir.
- Diğer modeller de (Linear Regression, KNN, SVR) yaşam beklentisi tahmininde başarılı olmuş, ancak XGBoost ve Random Forest daha yüksek doğruluklar elde etmiştir.

Bu bulgular, yaşam beklentisi tahmini gibi karmaşık problemlerde güçlü ve esnek makine öğrenimi modellerinin kullanımının önemini vurgulamaktadır.


Youtube linki => https://youtu.be/Zk5A_Cml_gE
