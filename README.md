# Examination of Zipf’s Law of Abbreviation in Thai dialogue text 
## Information  
Thanaritt Kunajak  
Natural Language Processing  
Master’s in Theoretical and Applied Linguistics (8037)  
Universitat Pompeu Fabra  
Exercise 1



## 1 Introduction

Zipf’s law of abbreviation, or the brevity law, is a linguistic law that states that the higher the frequency a word is used, the shorter the length of that word, and vice versa. (Kingsley Zipf, 1932; Henmon & Zipf, 1936; Chao & Zipf, 1950) For English, this can be observed in grammatical words, e.g., a, an, the, and and, and in contrast, non-frequent content words, e.g., overintellectualization, uncharacteristically, unsatisfactoriness, and autobiographically.
Previously, there has been a study of Zipf’s Law of Abbreviation in 986 different languages, which included Thai.(Bentz & Ferrer-I-Cancho, 2016.) They demonstrated that Zipf’s Law of Abbreviation hold for all languages tested, and argued that it might be a universal property.

## 2 Material and methods

In Bentz & Ferrer-I-Cancho (2016), for Thai language, the study used parallel translations from the Parallel Bible Corpus (PBC) (Mayer & Cysouw, 2014). I’d like to examine whether Zipf's Law of Abbreviation still holds in the domain of conversational language for Thai, a different language register and also a different domain.

### 2.1 Data Sources

The data used in this study is from SCB-MT-EN-TH-2020 (Lowphansirikul et al., 2021), specifically Taskmaster-1 (Byrne et al., 2019). Taskmaster-1 is a dataset of 13,215 task-based dialogs in 6 domains: ordering pizza,making car repair appointments, scheduling rides, booking movie tickets, ordering drinks, and making restaurant reservations. The dialogues were written in both written and spoken English. Later, in Lowphansirikul (2021),  25 professional translators were hired to translate these dialogues. The data is available for public use and could be found at airesearch/scb_mt_enth_2020 · Datasets at Hugging Face.
This corpus selection is to ensure the naturalness of the text in the corpora, while ensuring similarity in their content and context.


### 2.2 Preprocessing steps

The English texts were tokenized based on whitespaces and punctuation marks, namely, periods, commas, and question marks were removed. Later, the texts were lowercased. This is to remove the effect of sentence boundaries found in every text.

For Thai, a CNN-based tokenizer (Chormai et al., 2019) was used for tokenization.To provide a background knowledge, Thai is a non-whitespace language, meaning words are written without whitespaces in-between, unlike English, which leads to syntactic ambiguities as word boundaries are not evident. Moreover, Thai doesn’t use punctuation marks to delimit phrases and sentences. This issue was circumvented by the selection of the aforementioned corpus, which has already been sentence tokenized. After that, question marks (the only punctuation mark I found that was left in the data) were removed.

After preprocessing the data, I created a table detailing each word frequency and their word length; these were used as data points to investigate the association between the frequency of a word and its length. For this purpose, the Kendall rank correlation (‌Conover, 1999; Ferrer-i-Cancho et al., 2016) was used to capture non-linear dependencies.

### 3 Results

It has been shown through Kendall rank correlation that there exists an inverse relationship between the word frequency and their length, which is present in both languages in this experiment. Hence, the Zipf’s Law of Abbreviation holds for both languages in this domain and register, which is not surprising considering that there were multiple studies done to test this law across many language families and writing systems, and so far there are no deviations from this universal tendency. (Bentz & Ferrer-I-Cancho, 2016.)
