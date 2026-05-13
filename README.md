# Uyku ve Bilişsel Performans Tahmin Sistemi

## Proje Hakkında

Bu proje, bireylerin uyku alışkanlıkları, yaşam tarzı, stres düzeyi ve biyometrik verileri kullanılarak bilişsel performans skorunun tahmin edilmesini amaçlayan gelişmiş bir makine öğrenmesi sistemidir.

Notebook içerisinde kapsamlı veri analizi, eksik veri yönetimi, feature engineering, model optimizasyonu ve ensemble öğrenme teknikleri kullanılmıştır.

Sistem; Random Forest, Extra Trees, HistGradientBoosting, XGBoost, LightGBM ve stacking ensemble yaklaşımlarını bir araya getirerek yüksek doğruluklu regresyon tahminleri üretmektedir.

---

# Kullanılan Teknolojiler

- Python
- Pandas
- NumPy
- Scikit-Learn
- XGBoost
- LightGBM
- Optuna
- Matplotlib
- Seaborn
- Joblib

---

# Veri Seti İçeriği

Model eğitiminde aşağıdaki türde veriler kullanılmaktadır:

- Yaş
- Cinsiyet
- Meslek
- Vücut Kitle İndeksi (BMI)
- REM Uyku Yüzdesi
- Derin Uyku Yüzdesi
- Uykuya Dalma Süresi
- Gecelik Uyanma Sayısı
- Stres Skoru
- Günlük Çalışma Saati
- Ruh Sağlığı Durumu
- Dinlenik Nabız
- Oda Sıcaklığı
- Hafta Sonu Uyku Farkı
- Kronotip
- Mevsim
- Gün Tipi

### Hedef Değişken

```python
bilissel_performans_skoru
```

---

# Proje Mimarisi

Notebook aşağıdaki temel aşamalardan oluşmaktadır:

## 1. Veri Yükleme

```python
train.csv
test_x.csv
```

dosyaları yüklenir ve veri seti temel istatistikleri analiz edilir.

---

## 2. Eksik Veri Analizi

Eksik değerler tespit edilir:

- BMI
- Kronotip
- Meslek
- Ruh Sağlığı Durumu
- Kafein Tüketimi
- Stres Skoru

gibi alanlar analiz edilerek uygun preprocessing işlemleri uygulanır.

---

## 3. Feature Engineering

Veri setindeki kategorik ve sayısal değişkenler optimize edilir.

Uygulanan işlemler:

- Encoding
- Normalizasyon
- Ölçeklendirme
- Yeni türetilmiş özellikler
- Outlier yönetimi

---

## 4. Model Eğitimi

Birden fazla regresyon modeli eğitilmiştir.

### Kullanılan Modeller

- RandomForestRegressor
- ExtraTreesRegressor
- HistGradientBoostingRegressor
- Ridge Regression
- Huber Regressor
- XGBoost Regressor
- LightGBM Regressor

---

## 5. Ensemble ve Stacking

Farklı modellerin güçlü yönlerini birleştirmek amacıyla:

- Voting Regressor
- Stacking Regressor

yaklaşımları kullanılmıştır.

Bu sayede modelin genelleme başarımı artırılmıştır.

---

## 6. Hyperparameter Optimization

Optuna kullanılarak:

- learning rate
- tree depth
- estimators
- subsampling
- regularization

gibi parametreler optimize edilmiştir.

---

# Model Değerlendirme Metrikleri

## R² Score

Modelin açıklayıcılık oranını ölçer.

```math
R^2 = 1 - \frac{\sum (y_i-\hat{y}_i)^2}{\sum (y_i-\bar{y})^2}
```

---

## Mean Squared Error (MSE)

Tahmin hatalarının karelerinin ortalamasıdır.

```math
MSE = \frac{1}{n}\sum_{i=1}^{n}(y_i-\hat{y}_i)^2
```

---

## Mean Absolute Error (MAE)

Gerçek değer ile tahmin arasındaki mutlak farkı ölçer.

```math
MAE = \frac{1}{n}\sum_{i=1}^{n}|y_i-\hat{y}_i|
```

---

# Cross Validation

Model güvenilirliği için:

```python
KFold Cross Validation
```

uygulanmıştır.

```python
N_FOLDS = 5
```

ile veri 5 parçaya bölünerek modelin farklı veri dağılımlarındaki performansı test edilmiştir.

---

# Görselleştirmeler

Notebook içerisinde:

- Korelasyon analizleri
- Feature importance grafikleri
- Hata dağılımları
- Tahmin karşılaştırmaları
- Eksik veri analizleri

gibi çok sayıda veri görselleştirmesi bulunmaktadır.

---

# Çalıştırma Adımları

## 1. Gerekli Kütüphaneleri Kur

```bash
pip install pandas numpy scikit-learn matplotlib seaborn xgboost lightgbm optuna joblib
```

---

## 2. Veri Dosyalarını Yerleştir

Aynı klasöre:

```bash
train.csv
test_x.csv
```

dosyalarını ekleyin.

---

## 3. Notebooku Çalıştır

```bash
jupyter notebook
```

veya

```bash
Google Colab
```

üzerinden notebooku açın.

---

# Notebook Hatası Hakkında

Bazı Jupyter/Colab sürümlerinde aşağıdaki hata oluşabilir:

```text
the 'state' key is missing from 'metadata.widgets'
```

Bu hata yalnızca notebook metadata yapısıyla ilgilidir ve model eğitimini etkilemez.

Çözüm olarak notebook içerisindeki:

```json
metadata.widgets
```

alanı temizlenmiştir.

---

# Projenin Amacı

Bu sistemin amacı:

- Uyku kalitesinin bilişsel performans üzerindeki etkisini analiz etmek
- Yaşam tarzı faktörlerini modellemek
- Yapay zeka destekli performans tahmini yapmak
- Sağlık ve nörobilim alanında veri odaklı karar destek sistemleri geliştirmektir.

---

# Gelecek Geliştirmeler

- Deep Learning tabanlı modeller
- Zaman serisi uyku analizi
- Gerçek zamanlı sağlık verisi entegrasyonu
- Mobil uygulama desteği
- Yapay zeka destekli öneri sistemi
- Explainable AI (XAI) entegrasyonu

---
