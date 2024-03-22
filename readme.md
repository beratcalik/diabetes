**Naive Bayes Sınıflandırıcıları ve Hiperparametre Optimizasyonu**

**1. Giriş**

Bu README dosyası, üç farklı Naive Bayes sınıflandırıcısı olan Bernoulli Naive Bayes, Multinomial Naive Bayes ve Gaussian Naive Bayes'in Python kodlarını içermektedir. Ayrıca, her bir sınıflandırıcı için hiperparametre optimizasyonu yapılır.

**2. Yöntemler**

**2.1 Bernoulli Naive Bayes Sınıflandırıcısı**

Bernoulli Naive Bayes, özelliklerin ikili olduğu (0 veya 1) kategorik veri setleri için uygundur. Özelliklerin binarize edilmiş olduğu veri setleri üzerinde iyi performans gösterir. Bernoulli Naive Bayes sınıflandırıcısı, veri setindeki her özelliğin bağımsız olduğunu ve özellikler arasındaki ilişkileri ihmal ettiğini varsayar.

Bernoulli Naive Bayes sınıflandırıcısı için hiperparametre optimizasyonu, BayesSearchCV algoritması kullanılarak gerçekleştirilir. Bu algoritma, belirlenen hiperparametre aralığında bir arama yapar ve en iyi hiperparametre kombinasyonunu bulmaya çalışır. En iyi hiperparametre kombinasyonu, belirli bir performans metriği (genellikle doğruluk) temel alınarak seçilir.

**2.2 Multinomial Naive Bayes Sınıflandırıcısı**

Multinomial Naive Bayes, kategorik veri setleri üzerinde çalışır ve özelliklerin belirli bir dağılımı ifade ettiği durumlarda kullanılır. Özelliklerin kümeler halinde sayıldığı (örneğin, kelime sayıları) metin sınıflandırma gibi durumlar için uygundur. Multinomial Naive Bayes sınıflandırıcısı, her özelliğin her sınıf için ayrı bir olasılık dağılımı olduğunu varsayar.

Multinomial Naive Bayes sınıflandırıcısı için hiperparametre optimizasyonu, GridSearchCV algoritması kullanılarak gerçekleştirilir. GridSearchCV, tüm hiperparametre kombinasyonlarını deneyerek en iyi performansı sağlayan hiperparametreleri bulmaya çalışır. En iyi hiperparametre kombinasyonu, belirli bir performans metriği (genellikle doğruluk) temel alınarak seçilir.

**2.3 Gaussian Naive Bayes Sınıflandırıcısı**

Gaussian Naive Bayes, sürekli özelliklerle çalışır ve özelliklerin normal dağıldığı durumlarda kullanılır. Özelliklerin normal dağılımı, özelliklerin ortalama ve varyansına dayanır. Gaussian Naive Bayes sınıflandırıcısı, her sınıf için özelliklerin normal dağılıma sahip olduğunu varsayar.

Gaussian Naive Bayes sınıflandırıcısı için hiperparametre optimizasyonu, RandomizedSearchCV algoritması kullanılarak gerçekleştirilir. RandomizedSearchCV, belirlenen hiperparametre aralığında rastgele bir arama yapar ve en iyi hiperparametre kombinasyonunu bulmaya çalışır. En iyi hiperparametre kombinasyonu, belirli bir performans metriği (genellikle doğruluk) temel alınarak seçilir.

**3. Bulgular**

**3.1 Bernoulli Naive Bayes Sınıflandırıcısı**

Bernoulli Naive Bayes sınıflandırıcısının en iyi hiperparametrelerini ve test doğruluğunu gösteren bir örnek çıktı aşağıda verilmiştir:

Best hyperparameters are: OrderedDict([('alpha', 7.828715508217367), ('binarize', 0.22310839509340455), ('fit\_prior', True)])

Best score is: 0.649920676890534

Best model is: BernoulliNB(alpha=7.828715508217367, binarize=0.22310839509340455)

Test accuracy is: 0.6558441558441559

Bu çıktıda, en iyi hiperparametreler, en iyi skor ve test doğruluğu bilgileri bulunmaktadır. Bernoulli Naive Bayes sınıflandırıcısının performansı, bu hiperparametrelerle elde edilen test doğruluğu üzerinden değerlendirilir.

**3.2 Multinomial Naive Bayes Sınıflandırıcısı**

Multinomial Naive Bayes sınıflandırıcısının en iyi hiperparametrelerini ve test doğruluğunu gösteren bir örnek çıktı aşağıda verilmiştir:

Best alpha: 0.1

Accuracy: 0.6623376623376623

Training set performance is:

`               `precision    recall  f1-score   support

`           `0       0.70      0.69      0.69       401

`           `1       0.43      0.45      0.44       213

`    `accuracy                           0.60       614

`   `macro avg       0.57      0.57      0.57       614

weighted avg       0.61      0.60      0.61       614

Test set performance is:

`               `precision    recall  f1-score   support

`           `0       0.73      0.75      0.74        99

`           `1       0.53      0.51      0.52        55

`    `accuracy                           0.66       154

`   `macro avg       0.63      0.63      0.63       154

weighted avg       0.66      0.66      0.66       154

Tables of confusion matrixes are tiered as training and test ones hereby:


Bu çıktıda, en iyi alpha değeri ve elde edilen test doğruluğu bilgileri bulunmaktadır. GridSearchCV kullanılarak elde edilen en iyi alpha değeri, modelin belirli bir düzenleme düzeyiyle en iyi performansı gösterdiği anlamına gelir. Test doğruluğu ise, bu en iyi hiperparametrelerle eğitilen modelin test veri seti üzerindeki başarısını ölçer.

**3.3 Gaussian Naive Bayes Sınıflandırıcısı**

Gaussian Naive Bayes sınıflandırıcısının en iyi hiperparametrelerini ve test doğruluğunu gösteren bir örnek çıktı aşağıda verilmiştir:


Test setinde doğruluk: 0.7662337662337663

En iyi hiperparametreler: {'var\_smoothing': 1e-07, 'priors': [0.8, 0.2]} 

Eğitim Seti Sınıflandırma Raporu:

`              `precision    recall  f1-score   support

`           `0       0.76      0.90      0.83       401

`           `1       0.72      0.47      0.57       213

`    `accuracy                           0.75       614

`   `macro avg       0.74      0.69      0.70       614

weighted avg       0.75      0.75      0.74       614


Test Seti Sınıflandırma Raporu:

`              `precision    recall  f1-score   support

`           `0       0.79      0.87      0.83        99

`           `1       0.71      0.58      0.64        55

`    `accuracy                           0.77       154

`   `macro avg       0.75      0.73      0.73       154

weighted avg       0.76      0.77      0.76       154

Bu çıktıda, en iyi hiperparametreler ve elde edilen test doğruluğu bilgileri bulunmaktadır. En iyi hiperparametreler, modelin en iyi performansı gösterdiği özellik kombinasyonunu temsil eder. Test doğruluğu, bu en iyi hiperparametrelerle eğitilen modelin test veri seti üzerindeki başarısını ölçer.

**4. Tartışma**

Gaussian Naive Bayes sınıflandırıcısının elde ettiği en yüksek test doğruluğu, diğer iki sınıflandırıcıya kıyasla daha iyi performans gösterdiğini göstermektedir. Bernoulli ve Multinomial Naive Bayes sınıflandırıcıları, test doğruluğu açısından biraz geride kalmıştır. Bu durum, veri setinin doğrusal ayrılabilir olmayan özelliklere sahip olabileceğini ve bu tür özelliklerin Gaussian Naive Bayes sınıflandırıcısı için daha uygun olduğunu düşündürmektedir.

Sonuç olarak, veri seti için en uygun sınıflandırıcı Gaussian Naive Bayes olarak belirlenmiştir. Bu sınıflandırıcı, en yüksek test doğruluğuna ve en iyi performansa sahiptir. Ancak, Bernoulli ve Multinomial Naive Bayes sınıflandırıcıları da belirli durumlarda kabul edilebilir performans sergilemektedir. Bu nedenle, veri seti ve problem bağlamı göz önünde bulundurularak en uygun sınıflandırıcı seçilmelidir.


