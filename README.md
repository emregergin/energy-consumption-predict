# Enerji Tüketimi Tahmin Projesi ⚡

Merhabalar, bu repo binaların özelliklerine bakarak ne kadar enerji harcayacaklarını tahmin eden bir makine öğrenmesi projesi. Yani bir binanın tipi, büyüklüğü ya da içindeki insan sayısı elektrik faturasını ne kadar etkiliyor onu tahmin etmeye çalıştım.

## Veri Setimiz 📊

Elimizde iki tane CSV dosyası var:

* **`train_energy_data.csv`**: Eğitim için
* **`test_energy_data.csv`**: Test için

Veri setinin içinde ne tarz bilgiler var, göz atalım:

* **Building Type**: Binanın türü ne? (örneğin Residential, Commercial, Industrial)
* **Square Footage**: Bina ne kadar büyük? (Metrekaresi)
* **Number of Occupants**: Binada kaç kişi yaşıyor?
* **Appliances Used**: Binada ne kadar elektronik cihaz kullanılıyor?
* **Average Temperature**: Ortalama sıcaklık nasıl?
* **Day of Week**: Hafta içi mi, hafta sonu mu?
* **Energy Consumption**: Elektrik tüketimi (Hedef değişkenimiz)

## Kullandığım Araçlar 🛠️

* **numpy**
* **pandas**
* **matplotlib**
* **seaborn**
* **scikit-learn**
* **lazypredict**

## Neler Yaptım? 🚀

Proje boyunca şu şekilde ilerledim:

1.  **Veriyi Tanıma**: Önce `train_energy_data.csv` ve `test_energy_data.csv` veri setlerini yükleyip içinde ne var ne yok diye göz attım.
2.  **Görselleştirme**: Sonra değişkenler arasında ne tarz var onu anlamak için grafiklerden yararlandım.
3.  **Ön İşleme**: "Residential", "Commercial" gibi string ifadeleri, makine öğrenmesi modellerinin anlayacağı sayısal değerlere çevirdim.
4.  **Model Eğitimi**: `LinearRegression` modelini seçip eğitim verileriyle modeli eğittim. Ayrıca tüm verilerin birbiriyle tutarlı olması için `StandardScaler` ile verileri scale ettim.
5.  **Değerlendirme**: Son olarak modelimin ne kadar isabetli tahminler yaptığını farklı skorlarla (Mean Squared Error, R2 Score gibi) ölçtüm.

## Sonuçlar? 🎉

* **R2 Skoru**: 0.9999
* **Ortalama Kare Hata (MSE)**: 9.22
* **Ortalama Mutlak Hata (MAE)**: 3.03
* `LazyRegressor` ile yaptığım hızlı denemelerde de `LarsCV`, `Lars` ve `LassoLarsCV` gibi modellerin de harika sonuçlar verdiğini gördüm.

## Siz de Denemek İsterseniz 💻

1.  Önce bu repoyu bilgisayarınıza veya klonlayın.
2.  Gerekli kütüphaneleri kurun:
    ```bash
    pip install numpy pandas matplotlib seaborn scikit-learn lazypredict
    ```
3.  `energy_consumption.ipynb` dosyasını Jupyter Notebook ile açın ve hücreleri sırasıyla çalıştırın.
