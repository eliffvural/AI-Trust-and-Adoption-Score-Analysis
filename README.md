🤖 Yapay Zekâ Araçlarına Duyulan Güvenin Benimseme Niyeti Üzerindeki Etkisi
Bu proje, bireylerin Üretken Yapay Zekâ (YZ) araçlarını benimseme süreçlerini etkileyen faktörleri Veri Madenciliği ve Makine Öğrenmesi teknikleriyle inceleyen akademik bir çalışmadır.

📌 Proje Özeti
Çalışma, kullanıcıların güven düzeyi, teknik becerileri, yaş ve etik kaygıları gibi parametreleri analiz ederek kullanıcıları segmentlere ayırır ve benimseme niyetlerini tahmin eder. Proje kapsamında hem Denetimsiz (K-Means) hem de Denetimli (Random Forest) öğrenme yöntemleri kullanılmıştır.

🛠️ Teknik Altyapı ve Metodoloji
1. Veri Ön İşleme (Data Preprocessing)
Ordinal Encoding: Sözel anket verileri (örn: "Günlük", "Haftalık") sayısal skorlara dönüştürüldü.

Feature Engineering: Kullanılan araç sayısı ve motivasyon hacmi gibi yeni değişkenler türetildi.

Standardization: Mesafe temelli algoritmaların başarısı için StandardScaler kullanıldı.

2. Kümeleme (Clustering - K-Means)
Dirsek Yöntemi (Elbow Method): WCSS değerleri analiz edilerek optimal küme sayısı K=3 olarak belirlendi.

Segmentasyon: Kullanıcılar; Mesafeli Gözlemciler, Genç Uygulayıcılar ve Deneyimli Öncüler olarak 3 ana gruba ayrıldı.

3. Sınıflandırma (Classification - Random Forest)
Data Augmentation (SMOTE): Sınıf dengesizliğini (imbalance) gidermek için sentetik veri üretimi yapıldı.

Tahmin Modeli: Kullanıcının niyet puanına göre yüksek/düşük benimseme potansiyeli tahmin edildi.

Özellik Önemi (Feature Importance): Benimseme kararında "Yaş" ve "Kullanım Sıklığı"nın en belirleyici faktörler olduğu saptandı.

4. Model Kaydı (Deployment)
Eğitilen modeller (.pkl), gelecekteki tahminler ve Karar Destek Sistemi prototipi için /models klasörüne kaydedilmiştir.

📂 Dosya Yapısı
Plaintext

├── models/
│   ├── yz_benimseme_rf_modeli.pkl      # Rastgele Orman Modeli
│   ├── yz_benimseme_kmeans_modeli.pkl  # K-Means Kümeleme Modeli
│   └── yz_benimseme_scaler.pkl         # Veri Ölçeklendirici
├── veriseti.csv                        # Ham anket verileri
├── artirilmis_veriseti.csv             # SMOTE sonrası dengelenmiş veri
├── analiz.py                           # Ana işlem ve modelleme kodu
└── README.md                           # Proje dökümantasyonu
🚀 Kurulum ve Çalıştırma
Projenin çalışması için gerekli kütüphaneler:

Bash

pip install pandas numpy scikit-learn matplotlib seaborn imbalanced-learn joblib
📊 Sonuçlar
Model, test verileri üzerinde davranışsal örüntüleri başarıyla saptamış ve kullanıcıların teknolojiye olan mesafesini belirleyen "Güven Bariyeri" matematiksel olarak modellenmiştir. Elde edilen bulgular, stratejik teknoloji yönetimi ve kullanıcı odaklı eğitim planlamaları için veri odaklı bir rehber sunmaktadır.

Yazar: Elif VURAL