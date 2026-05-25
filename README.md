# NLP (Natural Language Processing) — Çalışma Notları

Bu depo, **Doğal Dil İşleme (NLP)** konusunda öğrendiğim kavramları, formülleri ve Python uygulamalarını içeren **Jupyter Notebook çalışma notlarıdır**. Her notebook; teori (görsel/slayt notları) ile pratik kod örneklerini bir arada sunar.

> **Not:** Notebook'ların büyük kısmı gömülü görseller içerir. GitHub'a yüklerken dosya boyutları yüksek olabilir; gerekirse [Git LFS](https://git-lfs.github.com/) kullanmayı düşünebilirsiniz.

---

## İçerik Haritası

Aşağıdaki sıra, NLP öğrenim yolculuğunda mantıksal bir ilerleme sunar:

| Sıra | Notebook | Konu |
|:---:|---|---|
| 1 | `TextPreprocessing.ipynb` | Metin ön işleme |
| 2 | `TextRepresentation.ipynb` | Metin temsili |
| 3 | `ProbabilisticLanguageModels.ipynb` | Olasılıksal dil modelleri |
| 4 | `BasicNLP.ipynb` | Temel NLP uygulamaları |
| 5 | `ModernLanguageModelsBasedonDeepLearning.ipynb` | Derin öğrenme tabanlı dil modelleri |
| 6 | `AdvancedNLP.ipynb` | İleri düzey NLP (Transformers) |

---

## Notebook Özetleri

### 1. TextPreprocessing.ipynb
Ham metni modellemeye hazır hale getirme adımları:

- **Veri temizleme:** fazla boşluk, büyük/küçük harf, noktalama ve özel karakterler
- **Tokenizasyon:** NLTK `word_tokenize`, `sent_tokenize`, `punkt`
- **Kök ve gövde analizi:** Stemming (`PorterStemmer`) ve Lemmatization (`WordNetLemmatizer`)
- **Durdurma kelimeleri (Stop Words)**

### 2. TextRepresentation.ipynb
Metni sayısal vektörlere dönüştürme yöntemleri:

- **Bag of Words (BoW)** — `CountVectorizer`, IMDB veri seti örneği
- **TF-IDF**
- **N-Gram modelleri**
- **Word Embeddings:** Word2Vec, GloVe, FastText
- **Transformer tabanlı metin temsili**
- Yöntemlerin karşılaştırılması

### 3. ProbabilisticLanguageModels.ipynb
İstatistiksel dil modelleme:

- Olasılıksal dil modellerine giriş
- **N-Gram modelleri** (bigram, trigram, olasılık hesaplama)
- **Hidden Markov Models (HMM)**
- **Maximum Entropy Models (MaxEnt)**

### 4. BasicNLP.ipynb
Klasik ve kütüphane tabanlı NLP görevleri:

- **Metin sınıflandırma:** Spam tespiti (Spam Dataset, BoW + Decision Tree)
- **spaCy ile NER:** Adlandırılmış varlık tanıma
- **spaCy ile POS tagging:** Sözcük türü etiketleme
- **Kelime anlamı belirsizliği (WSD):** Lesk algoritması (`nltk`, `pywsd`)
- **Duygu analizi:** VADER ile Amazon yorumları

### 5. ModernLanguageModelsBasedonDeepLearning.ipynb
Derin öğrenme ile sıralı ve transformer modeller:

- **RNN** (Recurrent Neural Networks)
- **GRU** ve **LSTM** — IMDB veri seti ile duygu sınıflandırma
- **BERT vs GPT** karşılaştırması
- **Hugging Face Transformers:** GPT-2, otomatik dil modelleri

### 6. AdvancedNLP.ipynb
Transformer ekosistemi ve ileri uygulamalar:

- **BERT** — SQuAD üzerinde fine-tune edilmiş soru-cevap (QA)
- **GPT-2** — metin üretimi
- **BERT embedding + cosine similarity** — anlamsal arama
- **Öneri sistemleri** — kullanıcı-öğe embedding (TensorFlow/Keras)
- **MarianMT** — İngilizce → Fransızca çeviri
- **Hugging Face `pipeline`** — metin özetleme / üretim

---

## Gereksinimler

### Python paketleri

```bash
pip install jupyter pandas numpy scikit-learn nltk spacy gensim pywsd
pip install tensorflow torch transformers huggingface_hub keras
```

### spaCy dil modeli

```bash
python -m spacy download en_core_web_sm
```

### NLTK veri paketleri

Notebook'lar çalıştırılırken gerekli paketler indirilir (`nltk.download(...)`). Örnekler: `punkt`, `stopwords`, `wordnet`, `vader_lexicon`.

---

## Veri Setleri

Bazı notebook'lar harici CSV dosyalarına referans verir. Çalıştırmadan önce ilgili dosyaların notebook ile **aynı klasörde** olması gerekir:

| Dosya | Kullanıldığı notebook |
|---|---|
| `Spam Dataset.csv` | `BasicNLP.ipynb`, `TextRepresentation.ipynb` |
| `IMDB Dataset.csv` | `TextRepresentation.ipynb` |
| `amazon.csv` | `BasicNLP.ipynb` (duygu analizi) |

> Bu veri setleri repoda bulunmayabilir. Kaggle veya resmi kaynaklardan indirip klasöre eklemeniz gerekir.

---

## Kullanım

1. Depoyu klonlayın veya indirin.
2. Sanal ortam oluşturup bağımlılıkları kurun.
3. Jupyter'ı başlatın:

```bash
jupyter notebook
```

4. Önerilen sırayla notebook'ları açıp hücreleri sırayla çalıştırın.

---

## Proje Yapısı

```
NLP (Natural Language Process)/
├── README.md
├── TextPreprocessing.ipynb
├── TextRepresentation.ipynb
├── ProbabilisticLanguageModels.ipynb
├── BasicNLP.ipynb
├── ModernLanguageModelsBasedonDeepLearning.ipynb
└── AdvancedNLP.ipynb
```

---

## Amaç ve Kapsam

- **Amaç:** NLP ders notlarını, formülleri ve kod örneklerini tek bir yerde toplamak; tekrar çalışmak ve GitHub üzerinden erişilebilir kılmak.
- **Kapsam:** Eğitim amaçlıdır; production-ready bir kütüphane veya API değildir.
- **Dil:** Notlar ve kod yorumları ağırlıklı olarak Türkçe; örnek metinler ve veri setleri çoğunlukla İngilizce.

---