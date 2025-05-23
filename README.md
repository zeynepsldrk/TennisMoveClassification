# Tenis Hareketlerinin Sınıflandırılması Projesi

Bu proje, 2024 Güz Dönemi'nde Google Colab ortamında geliştirilmiş olup, tenis oyuncularının videolardaki hareketlerini iskelet verileri üzerinden analiz ederek öğrenme tabanlı sınıflandırma yapmayı amaçlamaktadır. Temel amacı, hareketlerin (Backhand, Forehand, Serve) otomatik olarak sınıflandırılmasıdır.

## Projenin Genel Amacı

Tenis oyuncularının çeşitli vuruş pozisyonlarını (backhand, forehand, serve) video verileri üzerinden analiz etmek

MediaPipe ile iskelet noktalarını (keypoints) çıkartmak

Derin öğrenme modelleriyle (3D CNN + LSTM) sınıflandırma yapmak

Öznitelik çıkarımı, veri dengesini sağlama, özellik indirgeme (PCA, LDA), veri artırma gibi işlemler uygulamak

Kullanılan Teknolojiler ve Kütüphaneler

Proje, Python dili ve Google Colab ortamında geliştirilmiştir. OpenCV video işleme için, MediaPipe iskelet çıkarımı için, NumPy ve Pandas veri işleme için kullanılmıştır. Modelleme aşamasında TensorFlow/Keras ile 3D CNN + LSTM mimarisi kurulmuş, scikit-learn ile çeşitli makine öğrenmesi teknikleri uygulanmış, imbalanced-learn ile veri dengesi sağlanmış ve Matplotlib/Seaborn ile görselleştirme yapılmıştır.

## Proje Aşamaları

 Veri Hazırlama: Videolar .avi formatındadır. Her 10. karede bir iskelet verileri çıkarılmıştır. MediaPipe kullanılarak 33 noktalık 3D koordinatlar elde edilmiştir. Veriler CSV ve NPY formatlarında kaydedilmiştir.

 Veri Ön İşleme: İskelet verileri vektörel hale getirilmiştir. Dosya adlarından etiketleme yapılmıştır. Veri artırma teknikleri uygulanmış, SMOTE ile veri dengelenmiş ve MinMaxScaler ile normalizasyon yapılmıştır.

 Öznitelik Çıkarımı ve Boyut Azaltma: PCA ve LDA yöntemleri kullanılmıştır. Tüm çerçeveler 33x33x3 tensör yapısına dönüştürülmüştür.

 Modelleme: 3D CNN, mekansal özellikleri çıkarmak için, LSTM ise zaman serisi ilişkileri için kullanılmıştır. Model 10-fold çapraz doğrulama ile test edilmiştir. Alternatif olarak SVM, Random Forest, KNN ve GBM gibi klasik algoritmalar da uygulanmıştır.

 Performans İstatistikleri

Modelin doğruluk oranı %90’ın üzerindedir. F1 skoru 0.88 ile 0.92 arasında değişmiştir. Precision, recall ve AUC ROC değerleri hesaplanmıştır. Karmaşıklık matrisi ile hareketlerin karışma düzeyi analiz edilmiştir.

## Kullanılan Veri Seti

Bu projede THETIS Dataset adlı açık kaynaklı veri seti kullanılmıştır. Bu veri seti, tenis oyuncularının yan ve üstten çekilmiş çeşitli vuruş hareketlerini içerir. Hareketler, backhand2h, foreflat ve serflat gibi kategorilere ayrılmıştır. Daha fazla bilgi için: https://github.com/THETIS-dataset/dataset

## Öğrenilenler

3D CNN + LSTM mimarisinin hareket sınıflandırmada etkinliği

MediaPipe ile iskelet çıkarımının faydaları

Veri artırmanın etkisi

PCA ve LDA’nın boyut indirgemedeki rolleri öğrenilmiştir

## Proje Dosya Yapısı

Veriler, modeller, sonuçlar ve not defterleri ilgili klasörlerde toplanmıştır. Kodlar makale.py dosyasında bulunmaktadır.
