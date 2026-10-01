# Makine Öğrenmesine Giriş

## 1. Makine Öğrenmesi Nedir?

**Makine öğrenmesi (Machine Learning)**, bilgisayarların verilerden öğrenerek, açık programlama ile tanımlanmadan görevleri yerine getirebilen yetkinliği geliştiren bir **yapay zeka (AI) alanı**dır.

> *"Bilgisayarların verilerden kalıpları bulmasına, bu kalıpları kullanarak tahmin yapmasına ve karar almasına olanak tanıması."*

### Temel Kavramlar

| Kavram | Açıklama |
|--------|----------|
| **Öğrenme (Learning)** | Verilerden bilgi/kalıp çıkarma süreci |
| **Tahmin (Prediction)** | Bilinmeyen verilerde sonuç tahmini |
| **Model (Model)** | Öğrenme sonucunda elde edilen matematiksel/istatistiksel yapı |
| **Özellik (Feature)** | Modelin karar vermesi için kullanılan verinin ölçütleri |

```python
# Basit bir örnek: lineer regresyon
import numpy as np
from sklearn.linear_model import LinearRegression

# Öğrenme verileri
X = np.array([[1], [2], [3], [4], [5]])  # Girdiler (örnek: ev boyutları)
y = np.array([2, 4, 5, 4, 5])            # Çıktılar (örnek: fiyatlar)

model = LinearRegression()
model.fit(X, y)  # Model öğrenme süreci

# Yeni veriden tahmin
y_predict = model.predict(np.array([[6]]))
print(f"6 birimlik ev için tahmini fiyat: {y_predict[0]:.2f}")
```

---

## 2. Yapay Zeka ve Makine Öğrenmesi İlişkisi

### 🤖 AI → ML → Derin Öğrenme (Deep Learning)

```
┌─────────────────────────────────┐
│     Yapay Zeka (AI)             │
│  ~ İnsan benzeri akıl yürütme   │
└──────────────┬──────────────────┘
               │
       ┌───────▼────────┐
       │ Makine Öğrenme │
       │   (ML)         │
       │ Veriden öğrenme│
       └───────┬────────┘
               │
       ┌───────▼────────┐
       │ Derin Öğrenme  │
       │ (Deep Learning)│
       │ Sinir ağları   │
       └────────────────┘
```

### Tarihçe Özeti

| Dönem | Gelişme | Ünvan |
|-------|---------|-------|
| **1950'ler** | Alanın doğuşu | *"Can machines think?"* — Turing Test |
| **1960'lar** | İlk algoritmalar | Perceptron, ilk sinir ağı |
| **1990'lar** | İstatistiksel yaklaşım | SVM, Decision Trees |
| **2010'lar** | Derin öğrenme patlaması | CNN, RNN, GPT serisi |
| **2020'ler** | Generatif AI | Stable Diffusion, Large Language Models |

> **Not:** Bu repo üzerindeki notlar çoğunlukla **classical ML** (klasik makine öğrenmesi) üzerine odaklıdır: regresyon, sınıflandırma, kümeleme gibi temel yöntemler. Derin öğrenme ve generatif AI konuları daha ileri seviyede ele alınabilir.

---

## 3. Makine Öğrenmenin Ana Türleri

### A. Denetimli Öğrenme (Supervised Learning)

Veriler hem **girdi (X)** hem de **hedef/çıktı (y)** olarak etiketlenmiştir.

| Model | Kullanım Alanı | Örnek |
|-------|---------------|-------|
| **Regresyon** | Sürekli değer tahmini | Ev fiyatı, fiyat trendi |
| **Sınıflandırma** | Kategorik atama | Spam/not spam, hastalık var/yok |

> **Repo'daki:** `Model-Development/02-Classification/` ve `01-Regression/` notları burayı kapsar.

### B. Denetimsiz Öğrenme (Unsupervised Learning)

Sadece **girdi (X)** vardır; hedef (y) belirtilmemiştir. Veri içinde gizli yapılar bulunur.

| Model | Kullanım Alanı | Örnek |
|-------|---------------|-------|
| **Kümeleme** | Gruplama/struktur | Müşteri segmentasyonu, anomal detection |
| **Boyut İndirme** | Özellik sayısını azaltma | PCA, t-SNE |

> **Repo'daki:** `Model-Development/03-Clustering/` ve `Model-Improvement/02-PCA/` notları burayı kapsar.

### C. Desteğe Öğrenme (Reinforcement Learning)

**Ödül/ceza mekanizması** ile ajanın ortamda öğrenmesi.

| Uygulama | Açıklama |
|----------|----------|
| Oyun AI'ları | AlphaGo, Atari oyunları |
| Robotik | Hareket kontrolü, manipülasyon |
| İşletme | Ödeme stratejileri, kaynak tahsisi |

> ⚠️ **Repo'da bu konuya dair bir giriş yer almamakla beraber, ileri seviye notlar eklenebilir.**

---

## 4. Standart ML Çalışma Akışı (Workflow)

Her ML projesi için standart bir akış vardır:

```
┌──────────────────────────────────────────────────┐
│  Veri Toplama → Ön İşleme → Eğitim/Test Ayırma   │
│            ↓                                     │
│  Model Seçimi → Eğitim → Değerlendirme → Dağıtım │
└──────────────────────────────────────────────────┘
```

### Bu Reponun Aşamaları

| Bölüm | Açıklama | Not Defteri |
|-------|----------|-------------|
| **Data Preprocessing** | Veri temizleme, dönüştürme, görselleştirme | 01–05 Numaralı notebooklar |
| **Model Development** | Farklı algoritmaların uygulanması | 01 Regresyon, 02 Sınıflandırma, 03 Kümeleme |
| **Model Improvement** | Performans artışı: ölçeklendirme, PCA, Auto-ML | 01–05 Numaralı notebooklar |

---

## 5. Bu Deponun Kapsamı ve Öğrenme Yol Haritası

### 📦 Veri Ön İşleme (Data Preprocessing)

- ✅ DataFrame işlemleri — pandas temel işlemleri
- ✅ Veri görselleştirme — Matplotlib, Seaborn
- ✅ Keşfedici veri analizi (EDA) — Dağılımlar, korelasyonlar
- ✅ Veri temizleme — Eksik değer, outliers
- ✅ Özellik mühendisliği — Yeni özellik oluşturma

### 🤖 Model Geliştirme (Model Development)

- ✅ **Regresyon**: Basit ve çoklu lineer regresyon
- ✅ **Sınıflandırma**: Lojistik regresyon, karar ağaçları, Random Forest, Naive Bayes
- ✅ **Kümeleme**: K-Means, Elbow yöntemi, Silhouette score

### ⚙️ Model Improvement (Model Improvement)

- ✅ **Özellik ölçeklendirme** — StandardScaler, MinMaxScaler
- ✅ **PCA (Bilekleme)** — Boyut azaltma, explained variance
- ✅ **Auto-EDA** — Otomatik keşif analizi
- ✅ **Auto-ML (PyCaret)** — Otomatik model seçme ve kıyaslama
- ✅ **Data Imputation** — Eksik değer doldurma teknikleri

---

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

| Durum | Tanım | Gösterisi |
|-------|-------|-----------|
| **Overfitting** | Model veriyi "ezberler"; test verisinde başarısız olur | Training accuracy çok yüksek, test accuracy düşük |
| **Underfitting** | Model veriyi yeterince öğrenemez; hem train hem test başarısız olur | Düşük accuracy her iki aşamada da |

> **Önlem:** Cross-validation, hyperparameter tuning, early stopping

### C. Öznitelik Mühendisliği (Feature Engineering)

> **"En iyi model, en iyi özelliğe sahip olmaktan daha iyi olabilir."**

- Eksik değerlerin doldurulması (imputation)
- Kategorik verinin sayısallaştırılması (one-hot encoding, label encoding)
- Polinom özellikler oluşturma
- Bölge/zaman özelliklerinin çıkarılması

### D. Model Performans Ölçütleri

| Problem Türü | Önerilen Metrik |
|-------------|-----------------|
| **Regresyon** | MSE (Mean Squared Error), RMSE, R² (R-kare) |
| **Sınıflandırma (dengeli)** | Accuracy |
| **Sınıflandırma (dengisiz)** | Precision, Recall, F1-Score, ROC-AUC |
| **Kümeleme** | Silhouette Score, Elbow yöntemi |

> **Repo'daki:** `classification.ipynb` ve `clustering.ipynb` notlarındaki tablolar bu metriği canlı gösterir.

---

### 6.5 Teori ve Uygulama Bağlamı

**Teorel ML Çerçevesi ve Pratik Uygulama**

Bu repo, klasik makine öğrenmesi (classical ML) yol haritasına odaklı bir not defteri koleksiyonudur. Çalışmalar çoğunlukla **denetimli** (supervised) ve **denetimsiz** (unsupervised) öğrenme yöntemlerini kapsar. Derin öğrenme (deep learning) ve generatif AI konuları ileri seviye çalışmalara ayrılmıştır.

**Temel ML İlkeleri:**

1. **Veri Kalitesi (Data Quality)**  
   Her model *"garbage in, garbage out"* prinsibine tabidir. Eksik veri doldurma (imputation), aykırı değer tespiti ve özellik ölçeklendirme, model performansının büyük kısmını belirler.

2. **Eğitim/Test Ayrımı (Train-Test Split)**  
   Veri seti genellikle %80 eğitim / %20 test olarak ayrılır. Cross-validation (çapraz doğrulama), tekrarlanabilir ve güvenilir sonuçlar sağlar.

3. **Overfitting Önleme**  
   Overfitting, modelin veriyi "ezberlemesi" durumudur. Cross-validation (k-katlı çapraz doğrulama), düzenlileştirme (regularization) ve erken durdurma (early stopping) bu riski azaltır.

4. **Özellik Mühendisliği (Feature Engineering)**  
   *"En iyi model, en iyi özelliğe sahip olmaktan daha iyi olabilir."* İyi özellik mühendisliği, model performansını anlamlı oranda artırabilir.

5. **Model Değerlendirme ve Tekrar Edilebilirlik**  
   `random_state=42` gibi sabitler, her çalışmada aynı sonuçların elde edilmesini sağlar. Cross-validation ile model güvenilirliği artırılır.

6. **Genel Bakış (Big Picture)**  
   Bu not defterleri, **klasik ML** (regresyon, sınıflandırma, kümeleme, boyut indirgeme, Auto-ML) üzerine odaklanmıştır. Modern derin öğrenme ve LLM konuları kapsam dışındadır.

---

## 7. Python ve Kütüphaneler için Kısa Not

| Kütüphane | Versiyon (Tavsiye) | Kullanım |
|-----------|-------------------|----------|
| **Python** | 3.9 – 3.11 | Temel çalışma dili |
| **NumPy** | 1.24+ | Matematiksel diziler, vektör işlemleri |
| **Pandas** | 2.2+ | Tablo verisi manipülasyonu, DataFrame |
| **Scikit-learn** | 1.4+ | Tüm ML algoritmaları, pipeline'lar |
| **Matplotlib** | 3.8+ | Statik görselleştirmeler |
| **Seaborn** | 0.13+ | Estetik grafikler, heatmap'lar |
| **Yellowbrick** | 1.3+ | Model değerlendirme görselleştirmeleri |
| **PyCaret** | 3.0+ | Auto-ML ortamı (Auto-EDA, Auto-ML) |

---

## 8. Sonraki Adımlar ve Önerilen Öğrenme Yolculuğu

### 🚀 "Daha önce hiç kod yazmadım, nasıl başlarım?"

1. **Bu notları sırasıyla oku:** Data Preprocessing → Model Development → Model Improvement
2. **Her notebook'u canlı deneyin:** Jupyter Notebook ortamında `Shift + Enter` ile hücreleri çalıştırın
3. **Verisetleri değiştirme:** Verilen örnek verisetleri yerine kendi verisetlerinizi deneyin
4. **Model'leri kıyaslayın:** Farklı algoritmaların (Random Forest, Lojistik Regresyon vb.) performansını aynı veride karşılaştırın

### 📊 "Sonra ne öğrenmeliyim?"

| Adım | Konu | Önerilen Kaynak |
|------|------|------------------|
| 1 | **Derin Öğrenme (Deep Learning)** | Fast.ai, PyTorch Tutorials |
| 2 | **Model Dağıtımı** | Flask/FastAPI ile API oluşturma |
| 3 | **Büyük Veri (Big Data)** | PySpark, Dask |
| 4 | **ML Production** | Docker, MLflow, CI/CD pipeline'lar |

---

## 📎 Referanslar

1. **Scikit-learn Documentation** — Scikit Kütüphanesi Dokümanları - [🔗](https://scikit-learn.org/stable/)
2. **Google's ML Crash Course** — Google'ın kendi iç eğitimi - [🔗](https://developers.google.com/machine-learning/crash-course?hl=tr)
