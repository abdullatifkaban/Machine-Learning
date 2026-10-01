# Machine Learning

Bu depo, Python ile klasik makine öğrenmesi uygulamalarını içeren eğitimsel bir kütüphanedir. Veri ön işleme, model geliştirme ve model iyileştirme aşamalarını kapsayan örnek Jupyter not defterleri, veri setleri ve referans kaynaklar sunar.

## 📚 Giriş

- [Makine Öğrenmesine Giriş](00-Introduction.md)
  *Teorik temeller ve kapsamı*

## 📊 Veri Ön İşleme

> Veri temizleme, keşif ve dönüştürme işlemleri

- [DataFrame İşlemleri](Data-Preprocessing/01-DataFrame-Operations/DataFrame-Operations.ipynb)
  *Pandas ile veri manipulasyonu, temel işlemler*
- [Veri Görselleştirme](Data-Preprocessing/02-Data-Visualization/Data-Visualization.ipynb)
  *Matplotlib ve Seaborn ile görselleştirme örnekleri*
- [Keşfedici Veri Analizi (EDA)](Data-Preprocessing/03-Exploratory-Data-Analysis/Exploratory-Data-Analysis.ipynb)
  *Veri dağılımları, korelasyon ve özet istatistikler*
- [Veri Temizleme](Data-Preprocessing/04-Cleaning-Data/Cleaning-Data.ipynb)
  *Eksik veri, aykırı değer ve veri dönüşüm teknikleri*
- [Özellik Mühendisliği](Data-Preprocessing/05-Feature-Engineering/Feature-Engineering.ipynb)
  *Özellik seçimi, dönüşümü ve yeni özellik oluşturma*

## 🤖 Model Geliştirme

> Denetimli ve denetimsiz öğrenme algoritmaları

### Denetimli Öğrenme

- [Regresyon Modeli](Model-Development/01-Regression/Regression.ipynb)
  *Lineer ve polinom regresyon teknikleri*
- [Sınıflandırma Modeli](Model-Development/02-Classification/Classification.ipynb)
  *Lojistik regresyon, karar ağaçları ve ensemble yöntemleri*
  - [Dengesiz Verilerle Başa Çıkma](Model-Development/02-Classification/Imbalanced-Data.ipynb)
    *SMOTE, sınıf ağırlıkları ve dengesiz veri stratejileri*

### Denetimsiz Öğrenme

- [Kümeleme Modeli](Model-Development/03-Clustering/Clustering.ipynb)
  *K-Means, hiyerarşik kümeleme ve değerlendirme metrikleri*

## ⚙️ Model İyileştirme

> Performans artırma ve otomasyon araçları

### Veri Boyutunu Azaltma

- [Özellik Ölçeklendirme](Model-Improvement/01-Scaling/Scaling.ipynb)
  *StandardScaler, MinMaxScaler gibi tekniklerle özelliklerin aynı ölçeğe getirilmesi*
- [Temel Bileşen Analizi](Model-Improvement/02-Principal-Component-Analysis/Principal-Component-Analysis.ipynb)
  *PCA ile veri boyutunun azaltılması ve varyans analizi*

### Otomatik İşlemler

- [Oto‑Keşfedici Veri Analizi](Model-Improvement/03-Auto-EDA/Auto-EDA.ipynb)
  *PyCaret ile otomatik EDA raporları ve görselleştirmeler*
- [Oto‑Makine Öğrenmesi](Model-Improvement/04-Auto-ML/Auto-ML.ipynb)
  *PyCaret ile model karşılaştırma ve en iyi model seçimi*
- [Oto‑Boş Verileri Doldurma](Model-Improvement/05-Data-Imputation/Data-Imputation.ipynb)
  *Eksik verilerin doldurulması için çeşitli imputation teknikleri*