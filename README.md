# LLM ile Belediye Mesaj Yönlendirme

Bu proje, Büyük Dil Modelleri (LLM) kullanılarak vatandaşlardan gelen belediye mesajlarının ilgili birimlere otomatik olarak yönlendirilmesini amaçlamaktadır.

## Proje Özeti

- **Veri Seti**: 100 adet vatandaş mesajı (5 farklı departman, her birinden 20 mesaj)
- **Departmanlar**:
  - Su ve Kanalizasyon
  - Temizlik ve Çöp
  - Ulaşım ve Trafik
  - Park ve Bahçeler
  - Zabıta

## Yapılan İşlemler

1. **Tokenization**  
   GPT-2 tokenizer ile mesajların token sayılarının analizi ve bağlam penceresi kontrolü.

2. **Embedding & Benzerlik**  
   `paraphrase-multilingual-mpnet-base-v2` modeli ile mesajların vektör temsillerinin çıkarılması ve cosine similarity ile anlam benzerliklerinin incelenmesi.

3. **Sınıflandırıcı Eğitimi**  
   Embedding vektörleri üzerinde basit bir sinir ağı (Keras) eğitilerek mesajların departmanlara sınıflandırılması.

4. **Güven Eşiği ile Yönlendirme**  
   Modelin güven skoru %60’ın altında kalan mesajların “Temsilciye aktar” şeklinde yönlendirilmesi.

5. **Sohbet Modeli ile Karşılaştırma (İsteğe Bağlı)**  
   Qwen2.5-0.5B-Instruct modeli ile sıfır örnekli (zero-shot) yönlendirme yapılarak sonuçların sınıflandırıcı ile karşılaştırılması.

## Kullanılan Teknolojiler

- Python
- Google Colab
- Transformers (Hugging Face)
- Sentence-Transformers
- TensorFlow / Keras
- Scikit-learn

## Not

Bu çalışma ders kapsamında hazırlanmış bir ödev projesidir.
