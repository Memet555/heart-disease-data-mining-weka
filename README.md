# 🫀 Heart Disease Risk Analysis & Data Mining with WEKA
## WEKA ile Kalp Hastalığı Risk Analizi ve Veri Madenciliği Çalışması

Bu proje, **UCI Machine Learning Repository** üzerinde yer alan dünyaca ünlü **Heart Disease (Kalp Hastalığı)** veri seti üzerinde, açık kaynaklı makine öğrenmesi ve veri madenciliği platformu olan **WEKA (Waikato Environment for Knowledge Analysis)** kullanılarak gerçekleştirilmiş uçtan uca bir Bilgi Keşfi ve Veri Madenciliği (Knowledge Discovery in Databases - KDD) çalışmasıdır.

---

## 📊 1. Veri Seti Açıklaması (heart.csv)
Veri seti, hastaların demografik ve klinik laboratuvar ölçümlerini içeren 14 temel öznitelikten (attribute) oluşmaktadır:
- ge: Hastanın yaşı
- sex: Cinsiyet (1: Erkek, 0: Kadın)
- cp: Göğüs ağrısı türü (Chest Pain Type: 0-3)
- 	restbps: Dinlenme kan basıncı (Resting Blood Pressure - mm Hg)
- chol: Serum kolesterol düzeyi (mg/dl)
- bs: Açlık kan şekeri (> 120 mg/dl: 1, aksi halde: 0)
- estecg: Dinlenme elektrokardiyografik sonuçları (0-2)
- 	halach: Ulaşılan maksimum kalp atış hızı
- exang: Egzersizle tetiklenen anjina (1: Evet, 0: Hayır)
- oldpeak: Dinlenmeye kıyasla egzersizle oluşan ST depresyonu
- slope: Tepe egzersiz ST segmentinin eğimi
- ca: Floroskopi ile renklendirilen ana damar sayısı (0-3)
- 	hal: Talasemi türü (Normal, Sabit kusur, Tersine çevrilebilir kusur)
- 	arget: Hedef değişken (0: Kalp hastalığı riski yok, 1: Kalp hastalığı teşhisi var)

---

## ⚙️ 2. Veri Ön İşleme (Data Preprocessing)
* **Eksik Değerlerin İncelenmesi:** Veri setindeki tutarsız veya kayıp kayıtlar elenmiş ve incelenmiştir.
* **Normalizasyon:** Farklı ölçeklerdeki sayısal değişkenlerin (örneğin kolesterol ile açlık kan şekeri) model kararlarını domine etmesini engellemek için WEKA'nın Normalize filtresi (Min-Max ölçekleme) uygulanmıştır.
* **Öznitelik Seçimi (Feature Selection):** Hedef değişkenle en yüksek korelasyona sahip belirleyici değişkenler tespit edilmiştir.

---

## 🌳 3. Sınıflandırma: J48 (C4.5) Karar Ağaçları
* **Algoritma:** WEKA'nın açık kaynaklı C4.5 karar ağacı uygulaması olan **J48** algoritması kullanılmıştır.
* **Özellik:** Entropi ve Bilgi Kazanımı (Information Gain) metrikleri kullanılarak ağaç dallandırılmış, aşırı öğrenmeyi (overfitting) engellemek için budama (pruning) parametreleri optimize edilmiştir.
* **Başarım Değerlendirmesi:** 10-Katlı Çapraz Doğrulama (10-Fold Cross-Validation) ile:
  * Karışıklık Matrisi (Confusion Matrix)
  * Precision, Recall ve F-Measure
  * ROC Eğrisi ve AUC (Area Under Curve) analizleri gerçekleştirilmiştir.

---

## 🔍 4. Kümeleme: K-Means & EM Clustering
* **Gözetimsiz Öğrenme:** Etiket bilgisinden bağımsız olarak hastaların klinik benzerliklerine göre doğal gruplara ayrılması incelenmiştir.
* **Analiz:** Hastalar risk ve semptom şiddetine göre kümelere ayrılarak her kümenin belirleyici öznitelik profilleri çıkarılmıştır.

---

## 📁 5. Proje Dizini
`	ext
heart-disease-data-mining-weka/
├── dataset/
│   └── heart.csv                       # Analiz edilen kalp hastalığı veri seti
├── presentations/
│   └── Heart_Disease_Weka_Analiz.pptx  # Akademik sunum ve sonuç slaytları
└── results/
    ├── clustering/                     # K-Means kümeleme ekran alıntıları ve analizleri
    ├── decision_trees_j48/             # J48 Karar ağacı görselleştirmeleri ve doğruluk matrisleri
    └── preprocessing/                  # WEKA filtreleme ve normalizasyon adımları
`

---

## 🛠️ Kullanılan Araçlar
* **WEKA 3.8+**
* **Microsoft PowerPoint** (Akademik Sunum)
