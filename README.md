# Yaşam Beklentisi Tahmini Makine Öğrenimi Projesi

Bu proje, yaşam beklentisi tahminini gerçekleştiren bir makine öğrenimi modelinin geliştirilmesi sürecini içermektedir. Proje boyunca veri temizleme, görselleştirme ve farklı makine öğrenimi modellerinin test edilmesi adımları izlenmiştir.

## Proje Adımları

### 1. Veri Temizleme
Veri seti üzerinde aşağıdaki işlemler gerçekleştirilmiştir:
-  **Eksik Verilerin Doldurulması:** Boşluklar null değerlerle doldurulmuştur.
-  **Label Encoding İşlemi:** Kategorik verilerin sayısal verilere dönüştürülmesi.
-  **Outlier İşlemi:** Anormal veriler tespit edilip gerekli işlemler uygulanmıştır.

Outlier işlemi bir veri setindeki aykırı (uç) değerleri tespit etmek ve belirlenen sınırlar içinde düzelterek temizlemek amacıyla kullanılır. İşlem adımları şu şekildedir:

###1. Veri Setinin Bölünmesi
Kodun başında veri seti, eğitim (df_train) ve test (df_test) olarak ikiye ayrılır. train_test_split fonksiyonu, veriyi %80 eğitim ve %20 test oranında böler. random_state=42 parametresi, aynı sonuçların tekrar üretilebilmesi için rastgelelik kontrolünü sağlar. Böylece modelin farklı çalıştırmalarda tutarlı sonuçlar vermesi sağlanır.

**2. Aykırı Değer Sınırlarının Hesaplanması**
Aykırı değerleri belirlemek için her sütunun birinci (Q1, %25) ve üçüncü (Q3, %75) çeyrek dilimleri hesaplanır. Bu çeyrekler arası fark (IQR) kullanılarak aykırı değer sınırları belirlenir. Aykırı değerler, aşağıdaki formüllerle bulunur:

Alt sınır: Q1 - 1.5 * IQR
Üst sınır: Q3 + 1.5 * IQR
Bu hesaplamalar, verinin dağılımına bağlı olarak aşırı düşük veya yüksek değerleri tespit etmek için kullanılır.

**3. Aykırı Değerleri Düzenleme**
Tespit edilen alt ve üst sınırlar kullanılarak, aykırı değerler sınırlar içine çekilir. Eğer bir değer alt sınırdan küçükse alt sınıra, üst sınırdan büyükse üst sınıra eşitlenir. Bu işlem, hem eğitim (df_train) hem de test (df_test) veri setlerine uygulanır. Böylece modelin tutarlı verilere dayanarak öğrenmesi sağlanır.

**4. Aykırı Değerlerin Yüzdesinin Hesaplanması**
Her bir sütun için aykırı değer yüzdesi hesaplanır. İlk olarak sütunun aykırı değer sınırları belirlenir, ardından bu sınırların dışına çıkan değerler sayılır. Tespit edilen aykırı değerlerin veri kümesindeki toplam gözlem sayısına oranı yüzdelik olarak hesaplanır. Bu işlem, veri temizleme sürecinin etkinliğini değerlendirmek için yapılır.

**5. Sayısal Sütunların Seçilmesi**
Aykırı değer işlemi yalnızca sayısal sütunlara uygulanmaktadır. Bu nedenle select_dtypes fonksiyonu kullanılarak sayısal veriler seçilir. Ayrıca, analiz açısından uygun olmadığı için "Year" sütunu listeden çıkarılır.

**6. Aykırı Değer Analizi Öncesi ve Sonrası Karşılaştırma**
Kod, her sütun için aykırı değer yüzdesini aykırı değerlerin düzeltilmesinden önce ve sonra hesaplayarak ekrana yazdırır. Böylece uygulanan düzeltme işleminin etkisi gözlemlenir.

**Sonuç:**
Kod çalıştırıldığında önce mevcut aykırı değer yüzdesi hesaplanır ve ekrana yazdırılır. Daha sonra aykırı değerler alt ve üst sınırlarla düzeltilir. Son olarak, tekrar aykırı değer yüzdesi hesaplanarak düzenleme işleminin ne kadar etkili olduğu analiz edilir.

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
