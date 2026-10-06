# Makine Öğrenmesine Giriş

## 1. Makine Öğrenmesi Nedir?

**Makine öğrenmesi (Machine Learning - ML)**, bilgisayarların açıkça kodlanmaya ihtiyaç duymadan verilerden öğrenerek görevleri yerine getirme yeteneği kazanmasını sağlayan bir **yapay zeka (AI) alt alanı**dır.

> [!TIP]
> *"Bilgisayarların verilerdeki kalıpları (örüntüleri) keşfetmesine, bu kalıpları kullanarak tahminler yapmasına ve kararlar almasına olanak tanır."*

### Temel Kavramlar

| **Kavram** | **Açıklama** |  
|--------|----------|
| **Öğrenme (Learning)** | Verilerden bilgi ve kalıp (örüntü) çıkarma süreci | 
| **Tahmin (Prediction)** | İşlenmiş veriler yardımıyla bilinmeyen durumlar hakkında sonuç üretme | 
| **Model (Model)** | Öğrenme sürecinin sonucunda elde edilen matematiksel/istatistiksel yapı | 
| **Özellik (Feature)** | Modelin karar vermesini sağlayan veriye ait ölçülebilir nitelikler | 

```python
# Basit bir örnek: Lineer Regresyon
import numpy as np
from sklearn.linear_model import LinearRegression

# Öğrenme verileri
X = np.array([[1], [2], [3], [4], [5]])  # Girdiler (örnek: ev boyutları)
y = np.array([2, 4, 5, 4, 5])            # Çıktılar (örnek: fiyatlar)

model = LinearRegression()
model.fit(X, y)  # Model eğitme süreci

# Yeni veriden tahmin
X_new = np.array([[6]])
y_predict = model.predict(X_new)
print(f"6 birimlik ev için tahmini fiyat: {y_predict[0]:.2f}")

```

## 2. Yapay Zeka ve Makine Öğrenmesi İlişkisi

### 🤖 AI → ML → Derin Öğrenme (Deep Learning)

```
┌─────────────────────────────────┐
│     Yapay Zeka (AI)             │
│  ~ İnsan benzeri akıl yürütme   │
└──────────────┬──────────────────┘
               │
       ┌───────▼─────────┐
       │ Makine Öğrenmesi│
       │   (ML)          │
       │ Veriden öğrenme │
       └───────┬─────────┘
               │
       ┌───────▼────────┐
       │ Derin Öğrenme  │
       │ (Deep Learning)│
       │ Sinir ağları   │
       └────────────────┘

```

### Tarihçe Özeti

| **Dönem** | **Gelişme** | **Unvan / Tanım** | 
|--------|----------|--------|
| **1950'ler** | Alanın doğuşu | *"Can machines think?"* — Turing Testi | 
| **1960'lar** | İlk algoritmalar | Perceptron, ilk yapay sinir ağı | 
| **1990'lar** | İstatistiksel yaklaşım | SVM (Destek Vektör Makineleri), Karar Ağaçları | 
| **2010'lar** | Derin öğrenme patlaması | CNN, RNN, GPT serisi | 
| **2020'ler** | Üretken Yapay Zeka (Generative AI) | Stable Diffusion, Büyük Dil Modelleri (LLMs) | 

> [!NOTE]
> **Not:** Bu depodaki notlar çoğunlukla **klasik makine öğrenmesi** (classical ML) üzerine odaklanmıştır: regresyon, sınıflandırma ve kümeleme gibi temel yöntemleri içerir. Derin öğrenme ve üretken yapay zeka konuları daha ileri seviye çalışmalarda ele alınabilir.

## 3. Makine Öğrenmesinin Ana Türleri

### A. Denetimli Öğrenme (Supervised Learning)

Veriler hem **girdi (X)** hem de **hedef/çıktı (y)** etiketiyle birlikte modele sunulur.

| **Model** | **Kullanım Alanı** | **Örnek** | 
|--------|----------|--------|
| **Regresyon** | Sürekli değer tahmini | Ev fiyatı, hisse senedi trendi | 
| **Sınıflandırma** | Kategorik etiketleme | Spam/Spam değil, hastalık var/yok | 


### B. Denetimsiz Öğrenme (Unsupervised Learning)

Veri setinde sadece **girdi (X)** bulunur; hedef etiket (y) yoktur. Model, veri içerisindeki gizli yapıları ve ilişkileri keşfeder.

| **Model** | **Kullanım Alanı** | **Örnek** | 
|--------|----------|--------|
| **Kümeleme** | Gruplama / Yapı Keşfi | Müşteri segmentasyonu, anomali tespiti | 
| **Boyut İndirgeme** | Özellik sayısını azaltma | PCA, t-SNE | 

### C. Pekiştirmeli Öğrenme (Reinforcement Learning)

Bir ajanın, içinde bulunduğu ortamda **ödül/ceza mekanizması** ile en uygun davranışı deneyimleyerek öğrenmesidir.

| **Uygulama** | **Açıklama** | 
|--------|----------|
| Oyun AI'ları | AlphaGo, Atari oyunları | 
| Robotik | Hareket kontrolü, nesne manipülasyonu | 
| İşletme | Fiyatlandırma stratejileri, kaynak tahsisi | 


## 4. Standart ML Çalışma Akışı (Workflow)

Her makine öğrenmesi projesi temel olarak şu adımları takip eder:

```
┌──────────────────────────────────────────────────┐
│  Veri Toplama → Ön İşleme → Eğitim/Test Ayrımı   │
│            ↓                                     │
│  Model Seçimi → Eğitim → Değerlendirme → Canlıya │
│                                           Alım   │
└──────────────────────────────────────────────────┘

```

### Bu Deponun Aşamaları

| **Bölüm** | **Açıklama** | **Not Defteri** | 
|--------|----------|--------|
| **Data Preprocessing** | Veri temizleme, dönüştürme ve görselleştirme | Data-Preprocessing \ 01–05 Numaralı notebook'lar | 
| **Model Development** | Farklı algoritmaların uygulanması | Model-Development \ 01 Regresyon, 02 Sınıflandırma, 03 Kümeleme | 
| **Model Improvement** | Performans artırma: Ölçeklendirme, PCA, Auto-ML | Model-Improvement \ 01–05 Numaralı notebook'lar | 

## 5. Bu Deponun Kapsamı ve Öğrenme Yol Haritası

### 📦 Veri Ön İşleme (Data Preprocessing)

* ✅ DataFrame işlemleri — pandas temel işlemleri

* ✅ Veri görselleştirme — Matplotlib, Seaborn

* ✅ Keşfedici Veri Analizi (EDA) — Dağılımlar, korelasyonlar

* ✅ Veri temizleme — Eksik değerler, aykırı değerler (outliers)

* ✅ Özellik Mühendisliği (Feature Engineering) — Yeni özellikler türetme

### 🤖 Model Geliştirme (Model Development)

* ✅ **Regresyon**: Basit ve çoklu lineer regresyon

* ✅ **Sınıflandırma**: Lojistik regresyon, karar ağaçları, Random Forest, Naive Bayes

* ✅ **Kümeleme**: K-Means, Elbow yöntemi, Silhouette skoru

### ⚙️ Model İyileştirme (Model Improvement)

* ✅ **Özellik Ölçeklendirme** — StandardScaler, MinMaxScaler

* ✅ **PCA (Temel Bileşenler Analizi)** — Boyut indirgeme, açıklanan varyans

* ✅ **Auto-EDA** — Otomatik keşfedici veri analizi

* ✅ **Auto-ML (PyCaret)** — Otomatik model seçimi ve karşılaştırması

* ✅ **Eksik Veri Doldurma (Data Imputation)** — Eksik değerleri tamamlama teknikleri

## 6. Temel Kavramlar

### A. Eğitim / Test Verisi Ayrımı

```
┌──────────────────────────────────────────┐
│           Tam Veri Seti                  │
├─────────────────────┬────────────────────┤
│   %80 Eğitim (Train)│  %20 Test (Test)   │
└─────────────────────┴────────────────────┘
         │ Model öğrenir          │ Model test edilir
         ▼                        ▼
    Tahmin Motoru         Değerlendirme

```

### B. Overfitting ve Underfitting

| **Durum** | **Tanım** | **Belirtileri / Göstergeleri** | 
|--------|----------|--------|
| **Overfitting (Aşırı Öğrenme)** | Model veriyi "ezberler"; test verisinde başarısız olur | Eğitim başarımı çok yüksek, test başarımı düşük | 
| **Underfitting (Yetersiz Öğrenme)** | Model veriyi yeterince öğrenemez; hem eğitim hem test verisinde başarısız olur | Hem eğitim hem test aşamasında düşük başarım | 

> [!IMPORTANT]
>  **Önlem:** Çapraz doğrulama (Cross-validation), hiperparametre optimizasyonu, erken durdurma (early stopping)

### C. Özellik Mühendisliği (Feature Engineering)

> [!TIP]
> **"İyi tasarlanmış özelliklere sahip basit bir model, yetersiz özelliklere sahip karmaşık bir modelden daha başarılı olabilir."**

* Eksik değerlerin doldurulması (imputation)

* Kategorik verilerin sayısallaştırılması (one-hot encoding, label encoding)

* Polinom özellikler oluşturma

* Tarih/zaman ve konum bilgilerinden yeni özellikler çıkarma

### D. Model Performans Ölçütleri

| **Problem Türü** | **Önerilen Metrik** | 
|--------|----------|
| **Regresyon** | MSE (Ortalama Kare Hata), RMSE, R² (R-Kare) | 
| **Sınıflandırma (Dengeli)** | Doğruluk (Accuracy) | 
| **Sınıflandırma (Dengesiz)** | Kesinlik (Precision), Duyarlılık (Recall), F1-Score, ROC-AUC | 
| **Kümeleme** | Silhouette Skoru, Elbow Yöntemi | 


### 6.5 Teorik ve Uygulama Bağlamı

**Teorik ML Çerçevesi ve Pratik Uygulama**

Bu depo, klasik makine öğrenmesi (classical ML) yol haritasına odaklanan bir not defteri koleksiyonudur. Çalışmalar çoğunlukla **denetimli** (supervised) ve **denetimsiz** (unsupervised) öğrenme yöntemlerini kapsar. Derin öğrenme (deep learning) ve üretken yapay zeka konuları daha ileri seviye çalışmalara ayrılmıştır.

**Temel ML İlkeleri:**

1. **Veri Kalitesi (Data Quality)**

   Her model *"garbage in, garbage out"* (çöp girerse çöp çıkar) prensibine tabidir. Eksik veri doldurma (imputation), aykırı değer tespiti ve özellik ölçeklendirme, model performansını doğrudan belirler.

2. **Eğitim/Test Ayrımı (Train-Test Split)**

   Veri seti genellikle %80 eğitim / %20 test olarak ayrılır. Çapraz doğrulama (Cross-validation), tekrarlanabilir ve güvenilir sonuçlar elde edilmesini sağlar.

3. **Overfitting'i Önleme**

   Overfitting, modelin veriyi genelleyemeyip ezberlemesi durumudur. K-katlı çapraz doğrulama (k-fold cross-validation), düzenlileştirme (regularization) ve erken durdurma (early stopping) yöntemleri bu riski azaltır.

4. **Özellik Mühendisliği (Feature Engineering)**

   Nitelikli özellik mühendisliği, modelin karmaşıklığından bağımsız olarak başarıyı doğrudan ve anlamlı oranda artırabilir.

5. **Model Değerlendirme ve Tekrar Edilebilirlik**

   `random_state=42` gibi sabitlerin tanımlanması, her çalıştırmada aynı sonuçların elde edilmesini (tekrarlanabilirliği) sağlar.

6. **Genel Bakış (Big Picture)**

   Bu not defterleri **klasik ML** (regresyon, sınıflandırma, kümeleme, boyut indirgeme, Auto-ML) konularına odaklanmaktadır. Derin öğrenme ve LLM gibi modern konular kapsam dışındadır.

## 7. Python ve Kütüphaneler İçin Kısa Notlar

| **Kütüphane** | **Versiyon (Tavsiye Edilen)** | **Kullanım Alanı** | 
|--------|----------|--------|
| **Python** | 3.9 – 3.11 | Temel programlama dili | 
| **NumPy** | 1.24+ | Matematiksel diziler ve vektör işlemleri | 
| **Pandas** | 2.2+ | Tablosal veri manipülasyonu (DataFrame) | 
| **Scikit-learn** | 1.4+ | Makine öğrenmesi algoritmaları ve veri akışları (pipeline) | 
| **Matplotlib** | 3.8+ | Statik veri görselleştirme | 
| **Seaborn** | 0.13+ | İstatistiksel ve estetik grafikler | 
| **Yellowbrick** | 1.3+ | Model değerlendirme ve görselleştirme araçları | 
| **PyCaret** | 3.0+ | Otomatik makine öğrenmesi (Auto-ML) ortamı | 

## 8. Sonraki Adımlar ve Önerilen Öğrenme Yolculuğu

### 🚀 "Daha önce hiç kod yazmadım, nasıl başlarım?"

1. **Notları sırasıyla okuyun:** Data Preprocessing → Model Development → Model Improvement

2. **Her notebook'u canlı deneyin:** Jupyter Notebook ortamında `Shift + Enter` kısayolu ile hücreleri sırayla çalıştırın.

3. **Veri setlerini değiştirin:** Örnek veri setleri yerine kendi seçtiğiniz farklı veri setleriyle denemeler yapın.

4. **Modelleri karşılaştırın:** Farklı algoritmaların (Random Forest, Lojistik Regresyon vb.) aynı veri üzerindeki performanslarını kıyaslayın.

### 📊 "Sonra ne öğrenmeliyim?"

| **Adım** | **Konu** | **Önerilen Kaynak** | 
|--------|----------|--------|
| 1 | **Derin Öğrenme (Deep Learning)** | Fast.ai, PyTorch Dokümantasyonu | 
| 2 | **Model Dağıtımı (Deployment)** | Flask/FastAPI ile REST API oluşturma | 
| 3 | **Büyük Veri (Big Data)** | PySpark, Dask | 
| 4 | **MLOps & Üretim** | Docker, MLflow, CI/CD süreçleri | 

## 📎 Referanslar

1. **Scikit-learn Documentation** — Scikit-Learn Kütüphanesi Resmi Dokümantasyonu - [🔗](https://scikit-learn.org/stable/)

2. **Google's ML Crash Course** — Google Makine Öğrenmesi Hızlı Kursu - [🔗](https://developers.google.com/machine-learning/crash-course?hl=tr)