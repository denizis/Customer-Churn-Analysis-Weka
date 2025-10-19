### 🔹 J48 (Decision Tree) Sonuç Özeti

Model, Telco Customer Churn veri setinde %77.99 doğruluk oranı elde etti.

- **Precision:** 0.769  
- **Recall:** 0.780  
- **ROC Area:** 0.758  
- **Kappa:** 0.3988  

Confusion Matrix:
|  | Predicted No | Predicted Yes |
|--|---------------|----------------|
| **Actual No** | 4578 | 596 |
| **Actual Yes** | 954 | 915 |

Model, “müşteri kalır (No)” sınıfında daha yüksek doğruluk göstermiştir.


## 📊 Sonuçlar (10-Fold Cross Validation)

| Model | Accuracy | Precision | Recall | F-Measure | ROC Area |
|--------|-----------|-----------|---------|-------------|-----------|
| J48 (Decision Tree) | 77.99% | 0.769 | 0.780 | 0.772 | 0.758 |
| Naive Bayes | 74.66% | 0.734 | 0.747 | 0.738 | 0.787 |


J48 modeli doğruluk açısından daha başarılı olurken,
Naive Bayes modeli daha yüksek ROC alanına sahiptir ve olasılık tahminlerinde daha dengelidir



## 🔹 Customer Segmentation (K-Means Clustering)

### Amaç
Benzer özelliklere sahip müşterileri gruplandırmak için K-Means kümeleme algoritması kullanıldı.

### Uygulama Adımları
1. Veri seti Weka’da yüklendi.
2. "Churn" sütunu kaldırılarak denetimsiz öğrenme uygulandı.
3. SimpleKMeans algoritması 3 küme ile çalıştırıldı.

### Sonuçlar
| Küme | Müşteri Oranı | Özellikler |
|-------|----------------|------------|
| Cluster 0 | %48 | Uzun süreli, sadık müşteriler |
| Cluster 1 | %22 | Yeni, churn riski yüksek müşteriler |
| Cluster 2 | %30 | Yüksek ücretli, premium hizmet kullananlar |

### Görselleştirme
![K-Means Clusters](results/kmeans_visual.png)

### İçgörü
- **Cluster 1**, en yüksek churn riski taşıyan gruptur.  
- Bu müşterilere özel sadakat kampanyaları planlanabilir.
