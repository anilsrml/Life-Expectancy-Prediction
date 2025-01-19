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
Linear Regression Modeli, bağımsız değişkenler ile bağımlı değişken arasındaki doğrusal ilişkiyi analiz eder. Grafikte, gerçek değerler ile tahmin edilen değerler arasındaki ilişkiyi görselleştiririz. Grafikteki noktaların doğrusal bir çizgi etrafında yoğunlaşması modelin iyi bir performans sergilediğini gösterir.

**Random Forest Modeli**  
Random Forest Modeli, birden fazla karar ağacı kullanarak daha güvenilir tahminler yapar. Grafikte, gerçek değerler ile tahmin edilen değerler arasındaki ilişkiyi görselleştiririz. Grafik, modelin karmaşıklığını ve genel performansını gösterir. Noktaların doğrusal bir çizgi etrafında yoğunlaşması modelin iyi bir performans sergilediğini gösterir.

**K-Nearest Neighbors Modeli**  
K-Nearest Neighbors Modeli, veri noktalarının komşularına dayanarak tahmin yapar. Grafikte, gerçek değerler ile tahmin edilen değerler arasındaki ilişkiyi görselleştiririz. Noktaların doğrusal bir çizgi etrafında yoğunlaşması modelin iyi bir performans sergilediğini gösterir. Ancak, bu modelin performansı genellikle veri setinin yapısına ve seçilen komşu sayısına bağlıdır.

**Support Vector Regression Modeli**  
Support Vector Regression Modeli, hedef değişkeni en iyi temsil eden bir hiper düzlem bulmayı amaçlar. Grafikte, gerçek değerler ile tahmin edilen değerler arasındaki ilişkiyi görselleştiririz. Noktaların doğrusal bir çizgi etrafında yoğunlaşması modelin iyi bir performans sergilediğini gösterir. Model, marj içindeki hatayı minimize etmeye çalışır.

**XGBoost Modeli**  
XGBoost Modeli, gradient boosting algoritmasını optimize ederek daha iyi performans sergiler. Grafikte, gerçek değerler ile tahmin edilen değerler arasındaki ilişkiyi görselleştiririz. Noktaların doğrusal bir çizgi etrafında yoğunlaşması modelin iyi bir performans sergilediğini gösterir. XGBoost, genellikle diğer modellerden daha yüksek doğruluk sağlar.

## Kullanılan Kütüphaneler
- Pandas
- Numpy
- Matplotlib
- Seaborn
- Scikit-learn
- XGBoost

## Sonuçlar
Projede kullanılan beş farklı makine öğrenimi modeli, yaşam beklentisi tahminini başarıyla gerçekleştirmiştir. Modellerin performansları, doğru parametrelerle optimize edilerek test edilmiştir. Sonuçlar görselleştirildiğinde:

-XGBoost Modeli en yüksek doğrulukla tahminler sağlamıştır.
-Random Forest Modeli de başarılı bir performans sergileyerek güvenilir tahminler üretmiştir.
-Diğer modeller de (Linear Regression, KNN, SVR) yaşam beklentisi tahmininde başarılı olmuş, ancak XGBoost ve Random Forest daha yüksek doğruluklar elde etmiştir.
Bu bulgular, yaşam beklentisi tahmini gibi karmaşık problemlerde güçlü ve esnek makine öğrenimi modellerinin kullanımının önemini vurgulamaktadır.
