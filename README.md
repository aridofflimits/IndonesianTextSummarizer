# Bert2GPT Indonesian Text Summarizer
This repository hosts a sequence-to-sequence model that employs BERT for encoding and GPT for decoding, crafted specifically for the task of text summarization. The model is optimized for the Indonesian language, having been fine-tuned on the 'id_liputan6' dataset. This dataset is comprised of text summarization data derived from Liputan6, a prominent Indonesian news website. The ultimate goal of this project is to deliver succinct and accurate summaries of Indonesian news articles.

---

## Table of Contents
- [Introduction](#introduction)
- [Dataset](#dataset)
- [Methodology](#methodology)
- [Results](#results)
- [Room For Improvement](#room-for-improvement)
- [Attachment](#attachment)

---
# Introduction

The Bert2GPT Indonesian Text Summarizer is a sequence-to-sequence model that combines the encoding capabilities of BERT with the decoding prowess of GPT, specifically designed for the task of text summarization within the Indonesian context. This model addresses the growing need for efficient information processing in the face of increasing digital content, particularly in news media.

Indonesia's diverse linguistic landscape and the proliferation of digital news platforms necessitate advanced tools for content comprehension. The Bert2GPT Indonesian Text Summarizer caters to this need by providing a mechanism to distill lengthy news articles into their essential summaries, thus aiding in rapid information assimilation.

Housed in this repository is a model meticulously fine-tuned on the 'id_liputan6' dataset, which comprises text summarization pairs sourced from Liputan6, one of Indonesia's prominent news websites. This choice of dataset ensures that the model is well-adapted to the Indonesian language's syntactic and semantic nuances, as well as the stylistic characteristics typical of local news reporting.

The primary objective of the Bert2GPT Indonesian Text Summarizer is to enhance the accessibility of news content by generating concise and coherent summaries. This endeavor aligns with the broader goal of leveraging AI to bridge the gap between vast information streams and the end-user's need for quick and reliable insights. Through this project, I aim to contribute to the domain of natural language processing by offering a tool that not only streamlines content consumption but also fosters a better-informed and engaged audience in the Indonesian digital ecosystem.

---
# Dataset

## Finetuning Corpus

For the Bert2GPT Indonesian Text Summarizer, the canonical subset of the id_liputan6 dataset, accessible via the [Hugging Face](https://huggingface.co/datasets/id_liputan6) platform, serves as the foundation for the model's finetuning. This dataset, specifically curated from Liputan6 — a prominent Indonesian news website — offers a rich collection of text summarization pairs that are pivotal for training models in the Indonesian language context.

The id_liputan6 dataset is structured into two distinct parts:

- Xtreme Set: Designed for more challenging summarization scenarios, the Xtreme set features a diverse range of text lengths and complexities. It is intended to push the boundaries of summarization models in terms of understanding and generating concise summaries from more intricate articles.

- Canonical Set: This portion of the dataset provides a standard benchmark for summarization tasks, with a larger set of examples for training, development, and testing. It is characterized by its balanced representation of various news categories, making it ideal for general summarization models.

The canonical set is characterized by its comprehensive coverage, including a balanced mix of topics and writing styles reflective of mainstream Indonesian news reporting. This aspect of the dataset ensures that the finetuning process incorporates a wide array of linguistic nuances and information structures typical of Indonesian news articles.

By utilizing the canonical subset, the Bert2GPT model is exposed to a vast and varied corpus during finetuning, enabling it to learn and adapt to the complexities of summarizing news content accurately. The choice of this subset is strategic, aiming to equip the model with the ability to generate summaries that are not only concise and coherent but also faithful to the original articles in terms of content and tone.

The decision to employ the canonical subset underscores the project's commitment to creating a summarization tool that is highly attuned to the specifics of the Indonesian news landscape, ensuring relevance and applicability across a broad spectrum of news content.

---

# Methodology

## Exploratory Data Analysis

The Exploratory Data Analysis (EDA) section provides comprehensive insights into the dataset used for training the Bert2GPT Indonesian Text Summarizer. This section outlines various analytical steps taken to understand the dataset's characteristics, which inform the model's development and fine-tuning process.

### 1. Distribution of Article Lengths
This step involves analyzing the lengths of the articles in the dataset to understand the distribution and identify any potential outliers or biases. The analysis is visualized using a histogram, offering a clear view of how article lengths vary.

![image](https://github.com/aridofflimits/IndonesianTextSummarizer/assets/147245715/115a8328-2a5a-4f4e-b887-d31aac9b4eb0)

### 2. Distribution of Summary Lengths
Similar to the analysis of article lengths, this step focuses on the lengths of the summaries. Understanding the summary lengths is crucial for modeling the summarization process, ensuring that the generated summaries are concise yet informative.

![image](https://github.com/aridofflimits/IndonesianTextSummarizer/assets/147245715/67fb604e-5576-45c5-9b30-f820f0068aa3)

### 3. Most Frequent Terms in Articles
Identifying the most frequent terms in the articles helps in understanding the common themes and topics covered. This analysis is visualized through a bar plot, showcasing the top terms and their frequencies.

![image](https://github.com/aridofflimits/IndonesianTextSummarizer/assets/147245715/50ab42d3-ce77-4435-aa35-6cee216cbb83)

### 4. Most Frequent Terms in Summaries
This step parallels the analysis of articles, focusing instead on the summaries. By identifying the most frequent terms in summaries, insights into the core information retained in the summarized content are gained.

![image](https://github.com/aridofflimits/IndonesianTextSummarizer/assets/147245715/dff1ff2f-9b49-4857-b37e-702f79e087f3)

### 5. Scatter Plot for Article vs. Summary Length
A scatter plot comparing the lengths of articles and their corresponding summaries provides a visual representation of the summarization process, highlighting the compression ratio and the relationship between the original articles and the summaries.

![image](https://github.com/aridofflimits/IndonesianTextSummarizer/assets/147245715/c71a9c10-00dc-43e0-b28b-dfb2099c903e)

### 6. Box Plot for Distribution of Text Lengths
A box plot offers a comparative view of the distribution of text lengths between articles and summaries. This visualization helps in understanding the variance and central tendency of lengths.

![image](https://github.com/aridofflimits/IndonesianTextSummarizer/assets/147245715/2b87f8c3-a937-449c-b1d0-1f8f6396ccc9)

### 7. Plotting Bi-grams in Articles
Analyzing bi-grams (pairs of consecutive words) in articles reveals common phrase patterns, providing further insights into the linguistic characteristics of the dataset.

![image](https://github.com/aridofflimits/IndonesianTextSummarizer/assets/147245715/a8ebc195-7e72-4ba0-ad32-ad9a899913ac)

### 8. Plotting Bi-grams in Summaries
This analysis extends the bi-gram analysis to summaries, helping to understand the phrase patterns prevalent in summarized content.

![image](https://github.com/aridofflimits/IndonesianTextSummarizer/assets/147245715/07321033-14a3-4980-a855-d5dbfa3a032f)

### 9. Plotting Tri-grams in Articles
Tri-gram analysis in articles uncovers frequent three-word sequences, offering deeper insights into the contextual relationships within the text.

![image](https://github.com/aridofflimits/IndonesianTextSummarizer/assets/147245715/0fc1dcb3-1525-436d-8595-b14837072b91)

### 10. Plotting Tri-grams in Summaries
Similar to articles, tri-gram analysis in summaries helps identify common three-word phrases, crucial for understanding the summarization style and content focus.

![image](https://github.com/aridofflimits/IndonesianTextSummarizer/assets/147245715/3b7f3877-9d3c-435d-816f-43a99890c4c5)

### 11. Sentiment Analysis for Articles
Sentiment analysis of articles provides an overview of the emotional tone and sentiment polarity within the original content, essential for ensuring that the summaries accurately reflect the articles' intended sentiments.

![image](https://github.com/aridofflimits/IndonesianTextSummarizer/assets/147245715/73e3a8f4-728a-46bd-891d-a431b4a5d16a)

### 12. Sentiment Analysis for Summaries
Extending sentiment analysis to summaries ensures that the emotional tone and sentiment polarity are preserved in the summarized content, maintaining the integrity of the original articles.

![image](https://github.com/aridofflimits/IndonesianTextSummarizer/assets/147245715/890ceacc-828d-4867-a1a8-34b33d9eb585)

### 13. Top Words in Topics
Topic modeling, such as Latent Dirichlet Allocation (LDA), applied to the articles, helps identify the major themes and topics present in the dataset. This analysis is crucial for ensuring the model is well-tuned to the content diversity.

```
Topic 1:
yang dan ini dari itu dengan untuk aceh dalam ke
Topic 2:
yang dan dengan dari untuk itu ini tidak ke akan
Topic 3:
yang dan ini warga dari untuk itu com liputan6 dengan
Topic 4:
yang dan itu ini jakarta dalam akan untuk dengan dari
Topic 5:
yang dan ini itu polisi dengan dari tak jakarta mereka
```
Each step in the EDA process contributes to a holistic understanding of the dataset, guiding the development and fine-tuning of the Bert2GPT Indonesian Text Summarizer to achieve optimal performance.

---

## Preprocessing

The preprocessing phase is a critical step in preparing the dataset for training the Bert2GPT Indonesian Text Summarizer. This section outlines the steps taken to preprocess the data, ensuring it is in the optimal format for model training and validation.

### 1. Splitting the Dataset
The dataset is initially split into training and validation sets to facilitate the model's training and evaluation phases. This split helps in assessing the model's performance on unseen data, ensuring its generalizability.

### 2. Loading the Tokenizer from a Pretrained Model
The tokenizer from the pretrained model "cahya/bert2gpt-indonesian-summarization" is utilized for tokenizing the text. Special tokens for the beginning and end of sequences are set to ensure the model recognizes sequence boundaries.

### 3. Defining the Maximum Length of the Input and Target Sequences
The maximum lengths for both input articles and target summaries are defined, ensuring uniformity in sequence lengths and facilitating efficient batching during model training.
```
max_input_length = 256
max_target_length = 256
```

### 4. Tokenizing and Encoding Articles and Summaries
A preprocessing function is designed to tokenize and encode the articles and summaries. This function ensures that all texts are truncated or padded to the defined maximum lengths, maintaining consistency across the dataset.

### 5. Mapping Train and Validation Dataset
The preprocessing function is applied to both the training and validation datasets, transforming the raw texts into a format suitable for model input. This step ensures that the data is tokenized, encoded, and structured appropriately for training the summarization model.

### 6. Print Processed Examples
To verify the preprocessing, the first few processed examples from both the training and validation datasets are printed, showcasing the input_ids, attention masks, labels, and decoder input ids generated by the preprocessing function.

#### Processed Examples from Training Dataset
```
Example 1:
input_ids: [3, 17715, 1050, 17, 3036, 15, 15668, 17368, 29, 7721, 4510, 7558, 1495, 4602, 1849, 1495, 2168, 9952, 2182, 15, 15668, 17368, 15, 3596, 2086, 15, 1966, 12915, 11, 2842, 18, 20, 12, 15, 2172, 4367, 1495, 2177, 1695, 17, 3167, 10442, 7508, 3971, 1695, 1653, 5280, 2649, 8955, 17, 2248, 1675, 15, 3167, 2277, 19502, 4367, 1570, 3693, 7558, 17, 9123, 15, 1570, 1568, 4187, 1542, 15, 2054, 3144, 26352, 6608, 2177, 1695, 17, 1849, 8800, 1014, 15, 5469, 5283, 15, 22748, 23005, 15, 1509, 1849, 24200, 8869, 1510, 2343, 6970, 29072, 7558, 17, 4382, 2054, 1495, 3974, 2766, 2221, 3496, 17, 6569, 15, 1783, 3167, 2396, 1935, 1748, 2673, 1993, 1531, 6278, 28508, 17, 3920, 1533, 2236, 3085, 1609, 2148, 21147, 17, 1789, 15296, 1012, 9245, 12369, 2575, 3920, 4819, 1737, 15, 3416, 2948, 4370, 2111, 15, 4418, 16, 10021, 15, 7065, 15, 19235, 6099, 15, 6705, 15, 28347, 15, 1509, 4300, 11573, 17, 3920, 1542, 4799, 4585, 15668, 17368, 8864, 4111, 2133, 17, 2113, 4430, 1533, 2618, 6784, 1766, 5494, 25824, 4022, 17477, 1609, 2575, 3920, 17, 6989, 3651, 2601, 20079, 17315, 8863, 1730, 1542, 6674, 2962, 4370, 2111, 15, 2653, 14383, 4300, 2443, 1510, 8099, 2847, 1592, 8740, 15, 3884, 1487, 19296, 15, 1495, 3564, 2168, 9952, 2182, 17, 7558, 1495, 2647, 21142, 16, 24142, 13419, 17, 3244, 2757, 3212, 3766, 1510, 5489, 4895, 7695, 17, 1848, 3167, 1510, 22619, 1507, 3745, 1510, 25140, 1695, 6798, 2943, 3359, 1008, 17, 3745, 1734, 6359, 14414, 15, 3745, 4192, 15, 1509, 6218, 5516, 1]
attention_mask: [1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1]
labels: [3, 2248, 10442, 7508, 3971, 1653, 5280, 2649, 8955, 15, 3167, 2277, 19502, 4367, 1570, 3693, 7558, 17, 3920, 1720, 6737, 1519, 3974, 1885, 1716, 1533, 15296, 1012, 9245, 12369, 1509, 25824, 4022, 17477, 17, 1, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2]
decoder_input_ids: [3, 3, 2248, 10442, 7508, 3971, 1653, 5280, 2649, 8955, 15, 3167, 2277, 19502, 4367, 1570, 3693, 7558, 17, 3920, 1720, 6737, 1519, 3974, 1885, 1716, 1533, 15296, 1012, 9245, 12369, 1509, 25824, 4022, 17477, 17, 1, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2]


Example 2:
input_ids: [3, 1753, 21930, 15967, 1007, 15, 5203, 16269, 5973, 2957, 4845, 7317, 14726, 17, 1956, 15, 1935, 7591, 3093, 9703, 2242, 3645, 10737, 1542, 17, 5203, 16033, 2172, 1725, 2565, 1510, 2059, 25972, 1509, 3654, 6546, 3212, 1510, 13339, 17, 2165, 23641, 2008, 2236, 30660, 1822, 19018, 1028, 3331, 8198, 1542, 17, 6, 2242, 3245, 7508, 2343, 9693, 1675, 1714, 3466, 15, 6, 27011, 5203, 17, 1734, 3494, 15, 4640, 5203, 1495, 5315, 9255, 4655, 3331, 1533, 2236, 2246, 17, 2921, 2878, 4625, 2230, 2461, 2042, 12656, 1822, 10796, 5203, 17, 5222, 24263, 1992, 30214, 1542, 3598, 11665, 3331, 17, 1956, 15, 8198, 5203, 3354, 23274, 1500, 8377, 5107, 1510, 9456, 3315, 16, 15080, 1012, 1533, 2236, 3085, 17, 3475, 15, 5203, 3270, 15, 1831, 1786, 1757, 4006, 16, 4006, 1793, 3672, 1495, 3358, 1978, 17, 1634, 1609, 1653, 16967, 4347, 10341, 16890, 1653, 3516, 7344, 17, 5203, 2550, 8711, 15, 1572, 1519, 3358, 1831, 1637, 3354, 4008, 1570, 4927, 4686, 3212, 17, 6, 3947, 16, 3947, 1672, 4686, 3020, 1538, 2695, 1637, 7746, 12625, 1783, 3924, 15, 6, 27011, 5203, 17, 1495, 2517, 5187, 1600, 3645, 15, 5203, 1725, 25941, 1716, 1495, 2177, 15, 1971, 11740, 11496, 3492, 15215, 15, 1942, 11133, 12371, 7953, 17, 3645, 4814, 2178, 2753, 5774, 1542, 11740, 2148, 1533, 5444, 19572, 15, 7737, 2494, 1608, 15, 1509, 1716, 7071, 1998, 17, 7591, 2957, 1542, 1653, 2340, 2403, 1994, 17, 1793, 5981, 15, 5203, 6674, 4686, 8454, 1509, 4608, 1967, 20332, 6099, 17, 5154, 6068, 15, 5203, 6123, 6614, 1792, 1]
attention_mask: [1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1]
labels: [3, 1753, 21930, 15967, 1007, 15, 5203, 16269, 5973, 2957, 4845, 7317, 14726, 17, 1956, 15, 1935, 7591, 3093, 9703, 2242, 3645, 10737, 1542, 17, 5203, 16033, 2172, 1725, 2565, 1510, 2059, 25972, 1509, 3654, 6546, 3212, 1510, 13339, 17, 2165, 23641, 2008, 2236, 30660, 1822, 19018, 1028, 3331, 8198, 17, 17, 17, 1, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2]
decoder_input_ids: [3, 3, 1753, 21930, 15967, 1007, 15, 5203, 16269, 5973, 2957, 4845, 7317, 14726, 17, 1956, 15, 1935, 7591, 3093, 9703, 2242, 3645, 10737, 1542, 17, 5203, 16033, 2172, 1725, 2565, 1510, 2059, 25972, 1509, 3654, 6546, 3212, 1510, 13339, 17, 2165, 23641, 2008, 2236, 30660, 1822, 19018, 1028, 3331, 8198, 17, 17, 17, 1, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2]


Example 3:
input_ids: [3, 17715, 1050, 17, 3036, 15, 2647, 29, 7797, 14944, 3573, 17668, 1495, 2384, 5245, 15, 21274, 15, 2647, 2480, 15, 9252, 11, 2349, 18, 2178, 12, 17, 17848, 1510, 2023, 1609, 14944, 3573, 16169, 3410, 2684, 1495, 2647, 2086, 17, 1966, 4432, 1542, 7108, 15, 2935, 1495, 2076, 3573, 1675, 3093, 2223, 29329, 17, 2935, 1495, 3573, 17668, 3494, 2148, 1833, 16942, 1495, 5731, 1590, 1535, 4550, 7733, 17, 2784, 7427, 17, 8166, 17035, 7797, 1510, 7881, 2270, 3029, 3137, 17035, 7797, 3093, 2498, 1607, 2007, 1028, 1507, 2139, 20637, 3410, 17, 2173, 1675, 15, 1783, 16340, 2884, 1510, 2970, 12825, 20902, 1487, 9531, 4865, 9484, 1793, 7777, 1851, 5727, 2935, 1495, 2384, 6654, 24543, 1913, 4125, 15, 2647, 2480, 17, 23324, 2945, 1556, 1574, 1510, 2871, 11032, 2955, 2165, 2223, 5986, 2436, 1748, 2935, 1555, 3661, 6831, 24543, 1490, 1975, 6745, 16340, 4940, 4602, 1582, 1542, 17, 8722, 1942, 4178, 1533, 3979, 52, 17, 13631, 1537, 1509, 4351, 24886, 2053, 2847, 5254, 1519, 2177, 3541, 7479, 2019, 21643, 31594, 1016, 17, 7797, 1510, 14944, 8354, 7142, 2245, 1675, 1570, 2220, 5831, 1708, 29329, 1592, 3167, 1510, 2871, 7916, 2220, 18809, 1007, 14033, 17, 1966, 1793, 1542, 7683, 7301, 5386, 6792, 2443, 17569, 1014, 2172, 11676, 6488, 1509, 2755, 2935, 2150, 17, 1956, 3572, 10976, 15, 2935, 2150, 1533, 2861, 3154, 6421, 4107, 1533, 2955, 1510, 2186, 1495, 6242, 1930, 2177, 3353, 52, 17, 13631, 1537, 17, 11, 8351, 18, 1789, 17715, 25, 12369, 12, 17, 1, 2, 2, 2, 2, 2, 2, 2, 2]
attention_mask: [1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 0, 0, 0, 0, 0, 0, 0, 0]
labels: [3, 7797, 1570, 2220, 3223, 5300, 14944, 3573, 17668, 1509, 3564, 16169, 3410, 2684, 1495, 2647, 17, 1783, 1942, 4865, 9484, 2008, 2871, 11032, 2955, 1793, 7777, 4403, 1549, 2139, 20637, 3410, 17, 1, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2]
decoder_input_ids: [3, 3, 7797, 1570, 2220, 3223, 5300, 14944, 3573, 17668, 1509, 3564, 16169, 3410, 2684, 1495, 2647, 17, 1783, 1942, 4865, 9484, 2008, 2871, 11032, 2955, 1793, 7777, 4403, 1549, 2139, 20637, 3410, 17, 1, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2]
```

#### Processed Examples from Validation Dataset
```
Example 1:
input_ids: [3, 17715, 1050, 17, 3036, 15, 2647, 29, 2601, 2618, 9023, 13371, 11016, 5598, 15301, 7812, 1653, 1786, 6509, 13338, 1538, 1570, 9117, 21320, 2601, 17, 18155, 15, 11793, 2881, 18361, 2577, 3501, 1978, 3160, 9074, 1653, 5974, 17, 1572, 4989, 4444, 2229, 4879, 3523, 1509, 4695, 3487, 2601, 15, 18361, 1786, 9800, 7463, 5201, 2584, 11986, 17, 6, 2870, 8039, 2557, 2815, 1535, 2855, 10338, 2605, 6874, 6196, 15, 6, 2463, 11016, 15, 8126, 4517, 1555, 3162, 1978, 2618, 11389, 2309, 11, 2196, 12, 14991, 1489, 22215, 1495, 2647, 15, 12915, 11, 1587, 18, 23, 12, 17, 1570, 4916, 5598, 15301, 15, 1793, 1542, 15, 1766, 2341, 4660, 4819, 12048, 1572, 5986, 2667, 17, 2577, 12552, 8389, 3955, 1572, 3654, 4879, 3523, 1509, 31514, 1541, 3523, 1533, 11608, 20564, 2667, 1510, 1886, 25955, 18361, 1509, 2196, 17, 6, 2246, 1786, 10502, 12155, 2557, 15, 6, 27011, 1831, 17, 2173, 14991, 1489, 6123, 3093, 1708, 4279, 31514, 1541, 3523, 1533, 2196, 34, 12287, 29, 14991, 1489, 22215, 2277, 7750, 20387, 2221, 1769, 31514, 1541, 3523, 36, 17, 3803, 2196, 1944, 1786, 5450, 1535, 2842, 2778, 3160, 17, 6, 20629, 2957, 17, 5052, 1538, 34, 31514, 1541, 3523, 36, 2230, 1509, 4266, 1541, 15, 6, 27011, 14991, 1489, 17, 11, 3047, 18, 9876, 19018, 2133, 1509, 4224, 6201, 12290, 12, 17, 1, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2]
attention_mask: [1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0]
labels: [3, 7463, 5201, 2584, 11986, 4726, 1572, 6446, 2605, 6874, 6196, 1570, 2575, 4444, 2229, 4879, 3523, 17, 2618, 11389, 2309, 1786, 4279, 4695, 3487, 2601, 1535, 2842, 2778, 3160, 17, 1, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2]
decoder_input_ids: [3, 3, 7463, 5201, 2584, 11986, 4726, 1572, 6446, 2605, 6874, 6196, 1570, 2575, 4444, 2229, 4879, 3523, 17, 2618, 11389, 2309, 1786, 4279, 4695, 3487, 2601, 1535, 2842, 2778, 3160, 17, 1, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2]


Example 2:
input_ids: [3, 5307, 1753, 2227, 20244, 1495, 3357, 6991, 1570, 3896, 12003, 3771, 5447, 2947, 2579, 15, 5031, 15147, 4642, 3664, 1572, 28440, 3880, 5590, 6108, 10144, 1510, 1720, 26027, 1538, 2079, 3620, 17, 15147, 4642, 8711, 19285, 1675, 1653, 2129, 10516, 10289, 16479, 1822, 16810, 1538, 1533, 3217, 13116, 1503, 17, 1956, 15, 6995, 2618, 3485, 10289, 16479, 2910, 3199, 15, 2349, 2759, 2947, 15, 7080, 15147, 4642, 8880, 1521, 29, 3843, 2165, 11933, 1570, 3217, 13116, 1503, 17, 2079, 1793, 1675, 15, 15147, 4642, 1817, 2347, 7428, 1008, 1507, 17, 10289, 16479, 1998, 3598, 2793, 1634, 1653, 8387, 4784, 2242, 15147, 4642, 1572, 2092, 1519, 1570, 12788, 11, 12287, 29, 6063, 1533, 10289, 16479, 12, 17, 1734, 1510, 1851, 2118, 1537, 19220, 26220, 15, 4144, 2577, 5576, 1510, 10783, 10144, 2227, 1570, 2221, 3025, 12568, 15, 1887, 1495, 3896, 6719, 10451, 2876, 1509, 2618, 8615, 2910, 3542, 15, 26, 2964, 2888, 2579, 15, 1509, 2092, 7039, 1538, 5031, 15147, 4642, 1592, 5905, 6447, 8663, 15, 7219, 3525, 16290, 1011, 2976, 1509, 7092, 3255, 4924, 3130, 12656, 10289, 16479, 2148, 2695, 7744, 17, 3651, 5905, 19011, 1018, 15312, 5002, 1675, 2871, 24169, 9563, 1572, 7911, 2092, 15147, 4642, 15, 3663, 1582, 15, 1570, 13116, 1503, 1538, 1510, 1786, 1626, 20016, 1012, 2618, 17170, 1495, 6719, 3405, 2522, 2876, 2910, 3706, 1495, 2128, 20507, 15, 3066, 2753, 11956, 17, 2379, 2755, 19220, 26220, 1510, 2059, 2569, 1555, 1783, 2627, 5234, 1510, 1653, 5130, 3843, 1675, 15, 10289, 16479, 4240, 3941, 5621, 1533, 2878, 2627, 6829, 2227, 1]
attention_mask: [1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1]
labels: [3, 31182, 4962, 5905, 10144, 2227, 15, 10516, 10289, 16479, 3941, 5621, 1967, 2878, 2627, 5234, 4144, 4024, 14474, 7039, 1538, 5031, 15147, 4642, 1519, 1570, 13116, 1503, 17, 3602, 16383, 14484, 17390, 1684, 17, 1, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2]
decoder_input_ids: [3, 3, 31182, 4962, 5905, 10144, 2227, 15, 10516, 10289, 16479, 3941, 5621, 1967, 2878, 2627, 5234, 4144, 4024, 14474, 7039, 1538, 5031, 15147, 4642, 1519, 1570, 13116, 1503, 17, 3602, 16383, 14484, 17390, 1684, 17, 1, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2]


Example 3:
input_ids: [3, 17715, 1050, 17, 3036, 15, 4399, 29, 1789, 6299, 5402, 15791, 5137, 2602, 3030, 2102, 15, 11553, 11, 24, 18, 21, 12, 15, 23127, 2878, 15791, 1495, 9490, 5600, 4399, 2102, 15, 2326, 2102, 15, 2961, 1510, 2186, 1495, 3030, 3128, 4892, 26697, 5805, 17, 15791, 4941, 2183, 1935, 2287, 1675, 1977, 1542, 2186, 2044, 2221, 2016, 2653, 3496, 1495, 2274, 8320, 2781, 2291, 34, 12287, 29, 9523, 15791, 1495, 5600, 4399, 2102, 5375, 3691, 1028, 1507, 36, 17, 1495, 4203, 15, 7599, 4955, 2618, 6865, 11473, 29024, 1555, 4476, 1793, 1520, 4454, 4010, 1495, 3564, 5055, 3501, 1978, 4868, 17, 4798, 1542, 1572, 18580, 4164, 16919, 4203, 1510, 28192, 2740, 4695, 7568, 3054, 1723, 1748, 1653, 1708, 11935, 9200, 5399, 17, 2722, 1495, 8888, 15, 1789, 11896, 1510, 1720, 3851, 1747, 30831, 1007, 8888, 1509, 2356, 1834, 11832, 4417, 5496, 1994, 1542, 2334, 2599, 18646, 2229, 16417, 16, 16417, 2618, 1510, 2172, 7518, 1495, 2517, 13372, 1510, 5000, 17, 1535, 5010, 1675, 2878, 1834, 11832, 3037, 5010, 1572, 7855, 16, 28939, 27837, 1012, 1967, 9065, 23531, 17, 1533, 10749, 15, 3793, 6704, 15, 7721, 5192, 1533, 2878, 2316, 18847, 1509, 9977, 1520, 4454, 4010, 1495, 3358, 3564, 4666, 1750, 10749, 17, 1695, 3941, 2357, 2826, 1653, 8091, 22908, 2182, 5895, 23111, 3312, 11, 6297, 1010, 12, 1509, 5895, 23111, 3312, 3668, 9780, 11, 6297, 1010, 28594, 12, 17, 2248, 1675, 1695, 1609, 11780, 2357, 2826, 3991, 16879, 7049, 3163, 16, 3163, 6037, 3990, 4212, 1495, 3030, 1675, 17, 11, 64, 1025, 1009, 18, 1]
attention_mask: [1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1]
labels: [3, 2878, 15791, 2291, 1495, 5600, 4399, 2102, 15, 20565, 15, 4264, 1495, 3030, 3128, 4892, 26697, 5805, 5375, 3691, 1028, 1507, 1789, 6299, 5402, 15791, 3514, 1702, 1017, 17, 15791, 16, 15791, 1684, 1566, 4941, 2183, 1935, 2076, 17, 1, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2]
decoder_input_ids: [3, 3, 2878, 15791, 2291, 1495, 5600, 4399, 2102, 15, 20565, 15, 4264, 1495, 3030, 3128, 4892, 26697, 5805, 5375, 3691, 1028, 1507, 1789, 6299, 5402, 15791, 3514, 1702, 1017, 17, 15791, 16, 15791, 1684, 1566, 4941, 2183, 1935, 2076, 17, 1, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2]
```

### 7. Print Dataset Lengths
The lengths of the training and validation datasets are printed, providing an overview of the dataset size and the number of examples available for model training and validation.
```
Length of Training Dataset: 99267
Length of Validation Dataset: 24817
```

### 8. Inspecting The First Element
Inspecting the first element of both the training and validation datasets offers a detailed view of the data structure post-preprocessing, including the tokenized inputs and the structured format ready for model consumption.
```
First Element of Training Dataset: {'id': '94442', 'url': 'https://www.liputan6.com/news/read/94442/ribuan-korban-banjir-di-ogan-ilir-enggan-mengungsi', 'clean_article': 'Liputan6.com, Ogan Ilir: Ribuan korban banjir di delapan desa di Kecamatan Pemulutan, Ogan Ilir, Sumatra Selatan, hingga Selasa (25/1), masih bertahan di rumah mereka. Warga khawatir harta benda mereka tidak aman jika ditinggalkan. Selain itu, warga sudah terbiasa bertahan dalam kondisi banjir. Padahal, dalam sepekan ini, air terus merendam rumah mereka. Desa Tembakang, Maju Jaya, Pematang Bangsal, dan Desa Segayam yang paling parah terendam banjir. Ketinggian air di sana mencapai tiga meter. Dilaporkan, seorang warga meninggal dunia karena digigit ular berbisa. Bantuan dari berbagai pihak juga mulai berdatangan. Tim Pundi Amal SCTV memberikan bantuan tahap pertama, berupa lima ton beras, obat-obatan, susu, bubur bayi, roti, biskuit, dan minyak sayur. Bantuan ini diterima Bupati Ogan Ilir Indra Rusdi. Anggota DPR dari Partai Demokrasi Indonesia Perjuangan Taufik Kiemas juga memberikan bantuan. Suami mantan Presiden Megawati Sukarnoputri ini menyerahkan 21 ton beras, empat tangki minyak tanah yang diserahkan langsung oleh putrinya, Puan Maharani, di Kantor Kecamatan Pemulutan. Banjir di Jakarta berangsur-angsur surut. Kini tinggal masalah kesehatan yang membutuhkan perhatian serius. Banyak warga yang mengeluhkan penyakit yang diderita mereka pascabanjir. Penyakit seperti gangguan pernapasan, penyakit kulit, dan luka ringan dirasakan mereka sejauh ini. Namun, ancaman demam berdarah dan diare juga tak bisa disepelekan mengingat lingkungan sekitar lokasi banjir yang masih kotor. Untuk mengantisipasi penyebaran penyakit, Pusat Kesehatan Masyarakat Jatinegara dan pos koordinasi kesehatan di lokasi banjir di Kampung Melayu, Jakarta Timur, bersiaga. Mereka menangani penyakit yang diderita warga. Bagi warga yang membutuhkan penanganan lebih serius, mereka akan dirujuk ke Rumah Sakit Umum Daerah Budhi Asih dan Rumah Sakit Persahabatan, Jaktim. Namun, sejauh ini, persediaan obat-obatan untuk warga korban banjir di Kampung Melayu masih memadai. Badan Meteorologi dan Geofisika memperkirakan hujan masih akan mengguyur wilayah Jakarta, Bogor dan sekitarnya dalam beberapa hari. Bahkan, Rabu ini, hujan diperkirakan turun mulai siang hingga malam hari. Warga Jakarta diminta mewaspadai banjir kiriman akibat hujan yang cukup lebat mengguyur Bogor. Beberapa wilayah seperti Banda Aceh, Bengkulu, Lampung, dan sebagian Kalimantan dan Sulawesi juga diperkirakan hujan pada hari ini. Peluang hujan lebat disertai angin kencang akan melanda Kalimantan Tengah dan Bengkulu. Menurut Kepala Bagian Bidang Gempa Bumi BMG Suhardjono, gempa yang mengguncang Palu, Sulawesi Tengah, Senin dini hari silam, disebabkan gesekan patahan Palu Koro yang berada melintang di Utara Sulawesi. Gesekan ini terjadi akibat dorongan antara lempeng Indo Australia dan Pasifik yang berada di bagian Selatan dan Timur Indonesia. Setiap tahun, Indonesia diguncang gempa sekitar 70 kali. Ini karena terdapat tiga patahan gempa di wilayah Indonesia. (AWD/Tim Liputan 6 SCTV).', 'clean_summary': 'Selain khawatir harta benda tidak aman jika ditinggalkan, warga sudah terbiasa bertahan dalam kondisi banjir. Bantuan telah mengalir ke sana antara lain dari Pundi Amal SCTV dan Taufik Kiemas.', 'extractive_summary': 'Warga khawatir harta benda mereka tidak aman jika ditinggalkan. Selain itu, warga sudah terbiasa bertahan dalam kondisi banjir.', 'input_ids': [3, 17715, 1050, 17, 3036, 15, 15668, 17368, 29, 7721, 4510, 7558, 1495, 4602, 1849, 1495, 2168, 9952, 2182, 15, 15668, 17368, 15, 3596, 2086, 15, 1966, 12915, 11, 2842, 18, 20, 12, 15, 2172, 4367, 1495, 2177, 1695, 17, 3167, 10442, 7508, 3971, 1695, 1653, 5280, 2649, 8955, 17, 2248, 1675, 15, 3167, 2277, 19502, 4367, 1570, 3693, 7558, 17, 9123, 15, 1570, 1568, 4187, 1542, 15, 2054, 3144, 26352, 6608, 2177, 1695, 17, 1849, 8800, 1014, 15, 5469, 5283, 15, 22748, 23005, 15, 1509, 1849, 24200, 8869, 1510, 2343, 6970, 29072, 7558, 17, 4382, 2054, 1495, 3974, 2766, 2221, 3496, 17, 6569, 15, 1783, 3167, 2396, 1935, 1748, 2673, 1993, 1531, 6278, 28508, 17, 3920, 1533, 2236, 3085, 1609, 2148, 21147, 17, 1789, 15296, 1012, 9245, 12369, 2575, 3920, 4819, 1737, 15, 3416, 2948, 4370, 2111, 15, 4418, 16, 10021, 15, 7065, 15, 19235, 6099, 15, 6705, 15, 28347, 15, 1509, 4300, 11573, 17, 3920, 1542, 4799, 4585, 15668, 17368, 8864, 4111, 2133, 17, 2113, 4430, 1533, 2618, 6784, 1766, 5494, 25824, 4022, 17477, 1609, 2575, 3920, 17, 6989, 3651, 2601, 20079, 17315, 8863, 1730, 1542, 6674, 2962, 4370, 2111, 15, 2653, 14383, 4300, 2443, 1510, 8099, 2847, 1592, 8740, 15, 3884, 1487, 19296, 15, 1495, 3564, 2168, 9952, 2182, 17, 7558, 1495, 2647, 21142, 16, 24142, 13419, 17, 3244, 2757, 3212, 3766, 1510, 5489, 4895, 7695, 17, 1848, 3167, 1510, 22619, 1507, 3745, 1510, 25140, 1695, 6798, 2943, 3359, 1008, 17, 3745, 1734, 6359, 14414, 15, 3745, 4192, 15, 1509, 6218, 5516, 1], 'attention_mask': [1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1], 'labels': [3, 2248, 10442, 7508, 3971, 1653, 5280, 2649, 8955, 15, 3167, 2277, 19502, 4367, 1570, 3693, 7558, 17, 3920, 1720, 6737, 1519, 3974, 1885, 1716, 1533, 15296, 1012, 9245, 12369, 1509, 25824, 4022, 17477, 17, 1, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2], 'decoder_input_ids': [3, 3, 2248, 10442, 7508, 3971, 1653, 5280, 2649, 8955, 15, 3167, 2277, 19502, 4367, 1570, 3693, 7558, 17, 3920, 1720, 6737, 1519, 3974, 1885, 1716, 1533, 15296, 1012, 9245, 12369, 1509, 25824, 4022, 17477, 17, 1, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2]}

First Element of Validation Dataset: {'id': '76484', 'url': 'https://www.liputan6.com/news/read/76484/hari-ini-pks-menggelar-sidang-majelis-syuro', 'clean_article': 'Liputan6.com, Jakarta: Presiden Partai Keadilan Sejahtera Hidayat Nur Wahid memastikan tidak akan menempatkan kadernya dalam bursa pencalonan presiden. Alasannya, perolehan suara PKS hasil Pemilihan Umum 2004 dinilai tidak signifikan. Untuk menentukan dukungan terhadap capres dan calon wakil presiden, PKS akan menggelar Sidang Majelis Syuro. "Cara pandang kita bukan pada tingkat sekadar politik dagang sapi," kata Hidayat, usai pertemuan dengan Ketua Umum Partai Amanat Nasional (PAN) Amien Rais di Jakarta, Selasa (20/4). Dalam pandangan Nur Wahid, saat ini, Indonesia tengah memasuki tahap penentuan untuk menyelamatkan bangsa. Hasil musyawarah nantinya sekaligus untuk mendukung capres dan cawapres dari Poros Penyelamat Bangsa yang dimotori PKS dan PAN. "Masyarakat akan menilai komitmen kita," ujar dia. Sementara Amien mengaku belum dapat mengumumkan cawapres dari PAN [baca: Amien Rais Sudah Mengantongi Tiga Nama Cawapres]. Keputusan PAN baru akan diumumkan pada 25 April 2004. "Tunggu saja. Cirinya [cawapres] tinggi dan tegap," ujar Amien. (KEN/Fransambudi dan Henky Rahman).', 'clean_summary': 'Sidang Majelis Syuro dilaksanakan untuk menghindari politik dagang sapi dalam memberikan dukungan terhadap capres. Partai Amanat Nasional akan mengumumkan calon wakil presiden pada 25 April 2004.', 'extractive_summary': 'Untuk menentukan dukungan terhadap capres dan calon wakil presiden, PKS akan menggelar Sidang Majelis Syuro. Keputusan PAN baru akan diumumkan pada 25 April 2004.', 'input_ids': [3, 17715, 1050, 17, 3036, 15, 2647, 29, 2601, 2618, 9023, 13371, 11016, 5598, 15301, 7812, 1653, 1786, 6509, 13338, 1538, 1570, 9117, 21320, 2601, 17, 18155, 15, 11793, 2881, 18361, 2577, 3501, 1978, 3160, 9074, 1653, 5974, 17, 1572, 4989, 4444, 2229, 4879, 3523, 1509, 4695, 3487, 2601, 15, 18361, 1786, 9800, 7463, 5201, 2584, 11986, 17, 6, 2870, 8039, 2557, 2815, 1535, 2855, 10338, 2605, 6874, 6196, 15, 6, 2463, 11016, 15, 8126, 4517, 1555, 3162, 1978, 2618, 11389, 2309, 11, 2196, 12, 14991, 1489, 22215, 1495, 2647, 15, 12915, 11, 1587, 18, 23, 12, 17, 1570, 4916, 5598, 15301, 15, 1793, 1542, 15, 1766, 2341, 4660, 4819, 12048, 1572, 5986, 2667, 17, 2577, 12552, 8389, 3955, 1572, 3654, 4879, 3523, 1509, 31514, 1541, 3523, 1533, 11608, 20564, 2667, 1510, 1886, 25955, 18361, 1509, 2196, 17, 6, 2246, 1786, 10502, 12155, 2557, 15, 6, 27011, 1831, 17, 2173, 14991, 1489, 6123, 3093, 1708, 4279, 31514, 1541, 3523, 1533, 2196, 34, 12287, 29, 14991, 1489, 22215, 2277, 7750, 20387, 2221, 1769, 31514, 1541, 3523, 36, 17, 3803, 2196, 1944, 1786, 5450, 1535, 2842, 2778, 3160, 17, 6, 20629, 2957, 17, 5052, 1538, 34, 31514, 1541, 3523, 36, 2230, 1509, 4266, 1541, 15, 6, 27011, 14991, 1489, 17, 11, 3047, 18, 9876, 19018, 2133, 1509, 4224, 6201, 12290, 12, 17, 1, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2], 'attention_mask': [1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0], 'labels': [3, 7463, 5201, 2584, 11986, 4726, 1572, 6446, 2605, 6874, 6196, 1570, 2575, 4444, 2229, 4879, 3523, 17, 2618, 11389, 2309, 1786, 4279, 4695, 3487, 2601, 1535, 2842, 2778, 3160, 17, 1, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2], 'decoder_input_ids': [3, 3, 7463, 5201, 2584, 11986, 4726, 1572, 6446, 2605, 6874, 6196, 1570, 2575, 4444, 2229, 4879, 3523, 17, 2618, 11389, 2309, 1786, 4279, 4695, 3487, 2601, 1535, 2842, 2778, 3160, 17, 1, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2]}
```

These preprocessing steps are vital in ensuring the data is well-prepared for training the Bert2GPT Indonesian Text Summarizer, facilitating effective learning and optimization of the model.

---

## Load Pre-trained Models

The process of loading pre-trained models is crucial for initializing the Bert2GPT Indonesian Text Summarizer with established weights and configurations. This section outlines the steps taken to load the pre-trained BERT and GPT-2 models, detailing their roles as the encoder and decoder, respectively, in the sequence-to-sequence architecture.

### 1. Load Pre-trained BERT Model
The BERT model, specifically "cahya/bert-base-indonesian-1.5G", is loaded as the encoder component of the summarization model. This pre-trained BERT model is adept at understanding and encoding the context and nuances of Indonesian language texts, making it an ideal choice for the encoding phase. Its primary role is to process the input articles, creating contextual embeddings that represent the content's semantic and syntactic features.

### 2. Load Pre-trained GPT-2 Model
Following the encoder, the GPT-2 model configuration "cahya/gpt2-small-indonesian-522M" is loaded and modified to enable cross-attention, allowing it to function effectively as the decoder in the summarization model. This modification is essential for the GPT-2 model to attend to the encoded representations generated by the BERT encoder, facilitating coherent and contextually relevant text generation. The GPT-2 model, serving as the decoder, takes the encoded input and generates the summary, ensuring that the output is both linguistically fluent and aligned with the input content's intent.

By leveraging these pre-trained models, the Bert2GPT Indonesian Text Summarizer capitalizes on the strengths of both BERT and GPT-2, combining their capabilities to create a powerful summarization tool tailored for the Indonesian language. This approach not only enhances the model's performance but also significantly reduces the time and resources required for training from scratch.

---

## Create Model

The creation of the model is a pivotal step in setting up the Bert2GPT Indonesian Text Summarizer. This section outlines the process of integrating the pre-trained BERT and GPT-2 models to form a cohesive encoder-decoder architecture, along with configuring the special tokens and preparing the model for training.

### 1. Create the GPT-2 Model with Modified Configuration
First, the GPT-2 model is instantiated using the previously loaded and modified GPT-2 configuration. This step involves initializing the GPT-2 model with the configuration that enables cross-attention, ensuring that the decoder can effectively utilize the encoded inputs from the BERT encoder.

### 2. Combine BERT and GPT-2 into an Encoder-Decoder Model
The BERT and GPT-2 models are then combined to form an Encoder-Decoder model. In this setup, the BERT model serves as the encoder, processing and encoding the input text. The encoded representations are passed to the GPT-2 model, which acts as the decoder, generating the summarized text. This combination leverages the strengths of both models to create a powerful summarization tool.

### 3. Update Special Tokens Based on the Tokenizer
The model configuration is updated to include special tokens based on the tokenizer settings. This includes setting the decoder start token, pad token, and end-of-sequence (EOS) token IDs. These tokens are crucial for the model to recognize the start and end of sequences and handle variable-length inputs during training and inference.

### 4. Check for GPU Availability
Finally, the availability of a GPU is checked to determine the model's training environment. Utilizing a GPU can significantly accelerate the training process, allowing for faster model development and iteration. If a GPU is not available, the model will default to using the CPU, which may result in longer training times.

By meticulously setting up the model, including the integration of pre-trained components and the configuration of special tokens, the Bert2GPT Indonesian Text Summarizer is prepared for effective training and summarization tasks. This setup ensures that the model can leverage advanced language understanding and generation capabilities to produce high-quality summaries.

---

## Training Model

Training the Bert2GPT Indonesian Text Summarizer involves a detailed setup of training arguments, the creation of a trainer object, and the execution of the training process. This section outlines the initial training phase and subsequent continuation of training to further refine the model's performance.

## 1. Initial Training
The initial training phase sets up the environment and parameters for training the model. This includes specifying the output directory for results, the total number of training steps, batch sizes for training and evaluation, warmup steps for the learning rate scheduler, weight decay for regularization, and the directory for storing logs. A `Trainer` object is then created, configured with the model, training arguments, and datasets. The training is initiated using the `Trainer.train()` method, starting the process of model optimization based on the provided datasets.

### 2. Training Arguments
Training arguments are defined to control various aspects of the training process, such as the output directory, number of training steps, batch sizes, warmup steps, weight decay, and logging configurations. These arguments play a crucial role in managing the training workflow and ensuring efficient utilization of computational resources.

### 3. Trainer Creation
A `Trainer` object is instantiated with the model, training arguments, training dataset, and evaluation dataset. This object orchestrates the training process, handling tasks such as data loading, model optimization, and evaluation.

### 4. Model Training
The model training is initiated with the `trainer.train()` method, which starts the optimization process based on the defined training steps and datasets. This step is pivotal in adjusting the model weights to minimize the loss function and improve summarization performance.

## 5. Continue Training
To further enhance the model's capabilities, training can be continued from a specific checkpoint. This involves loading the model and tokenizer from a previous checkpoint and redefining the training arguments, possibly with adjusted parameters like the total number of training steps. The continuation of training allows for incremental improvements to the model, leveraging the progress made in earlier training phases.

### 6. Loading Model from Checkpoint
The model and tokenizer are reloaded from a specified checkpoint, ensuring that training resumes from the last saved state. This step is crucial for maintaining continuity in the training process and building upon the previously learned weights.

### 7. Redefining Training Arguments
Training arguments are redefined, possibly with adjustments to reflect the new phase of training. This includes setting a new total number of training steps and specifying the checkpoint to resume from, ensuring a seamless continuation of the training process.

### 8. Reinitializing the Trainer
A new `Trainer` object is created with the updated model, tokenizer, and training arguments. This trainer is then used to continue the training process, further refining the model's performance based on additional optimization steps.

By structuring the training into initial and continued phases, the Bert2GPT Indonesian Text Summarizer benefits from a flexible and iterative approach to model development, allowing for ongoing improvements and adjustments based on performance evaluations and new requirements.

---

## Model Evaluation

### Training and Validation Losses
The graph illustrates the model's learning progress, showing a decline in both training and validation losses over time, which indicates improving model performance.

![image](https://github.com/aridofflimits/IndonesianTextSummarizer/assets/147245715/b479ab56-28d8-441f-a6d7-0c0819fcd7ea)

### ROUGE Score
This graph displays the ROUGE scores for the summarization model, highlighting its ability to generate summaries that closely match the reference texts in terms of content accuracy and fluency.

![image](https://github.com/aridofflimits/IndonesianTextSummarizer/assets/147245715/3661d609-d5b8-41b9-8a43-653f8a7ac022)

---

# Results
## Testing the Model

Testing the Bert2GPT Indonesian Text Summarizer involves loading the trained model and tokenizer, setting up the input text for summarization, generating a summary, and decoding the output to human-readable text. This section outlines the steps taken to test the model's summarization capabilities on a provided article.

### 1. Load the Tokenizer and Model
The tokenizer and model are essential components for the summarization task. The tokenizer, "cahya/bert2gpt-indonesian-summarization", is loaded with specific configurations for the beginning and end of sequences tokens. The model is then loaded from a specified checkpoint, "/content/drive/MyDrive/results/186k-steps-model", which contains the trained weights and configuration necessary for generating summaries.

### 2. Tokenizer Configuration
The tokenizer's beginning-of-sequence and end-of-sequence tokens are set to ensure it properly formats the input text for the model. This configuration is crucial for the model to understand where the input text starts and ends, facilitating accurate summarization.

### 3. Model Loading
The model is loaded from a pre-trained checkpoint, which includes the learned weights from the training process. This step ensures that the summarization leverages the full capabilities of the trained model, producing high-quality summaries.

### 4. Input Article for Summarization
An article is provided as input to the summarization model. This text serves as the basis for generating a summary, allowing the model to demonstrate its ability to condense and capture the essence of the content.

### 5. Generate Summary
The summarization process involves encoding the input article, generating a summary with specified parameters (such as minimum and maximum length, number of beams for beam search, repetition penalty, and others), and decoding the generated summary IDs back into text. This process utilizes the model's capabilities to produce a concise and coherent summary of the provided article.

### 6. Summary Generation Parameters
Parameters such as minimum and maximum length, beam number, repetition penalty, and others are set to guide the summarization process. These parameters balance the summary's brevity and informativeness, ensuring the output is of high quality and relevance to the input text.

### 7. Decoding the Summary
The generated summary IDs are decoded back into human-readable text, stripping away any special tokens used during the summarization process. This decoded text represents the model's summarization output, providing a concise version of the original article.

The result is shown below:

| Aspect                | Details                                                                                                                                                                                                                      |
|-----------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Article to Summarize** | Liputan6.com, Jakarta: Tentara Nasional Indonesia hendaknya benar-benar profesional. TNI juga harus berada di atas seluruh kekuatan politik yang ada. Demikian permintaan mantan Presiden Partai Keadilan Sejahtera Hidayat Nur Wahid, di sela-sela Munas PKS, Sabtu (19/6), di Jakarta. TNI adalah alat negara yang harus netral dan berada di atas seluruh kekuatan politik yang ada. Ini untuk menjaga keamanan teritorial dan keutuhan Negara Kesatuan Republik Indonesia, kata Hidayat, seperti ditulis Antara. Menurut Hidayat, TNI baru mungkin memiliki hak pilih pada pemilu jika diatur secara konstitusional melalui perundang-undangan. Saya kira wacana TNI memiliki hak pilih dalam pemilu harus melalui pembahasan lebih lanjut di DPR, ujar anggota Komisi I DPR RI itu. Dari pembicaraan dengan pimpinan TNI, kata Hidayat, sampai saat ini TNI masih memilih belum terlibat di pemilu. Hal ini belajar dari pengalaman pada pemilu 1955, di mana TNI terlibat di pemilu sehingga terbelah pada sejumlah kekuatan politik. Kondisi ini membuat sistem keamanan nasional menjadi tidak optimal. Sebelumnya, Presiden Susilo Bambang Yudhoyono mengatakan, suatu saat TNI harus diberikan haknya untuk memberikan hak suara pada pemilu jika sudah tidak ada hambatan yang mengganggu kekompakan. Bisa tidaknya anggota TNI menggunakan hak pilihnya dalam pemilu maupun pilkada, kata Presiden, dapat ditentukan oleh undang-undang yang dibahas oleh pemerintah bersama DPR.                                  |
| **Summarization Parameters** | `min_length=20`, `max_length=80`, `num_beams=10`, `repetition_penalty=2.5`, `length_penalty=1.0`, `early_stopping=True`, `no_repeat_ngram_size=2`, `use_cache=True`, `do_sample=True`, `temperature=0.3`, `top_k=50`, `top_p=0.95` |
| **Summarized Article**  | tni adalah alat negara yang harus netral dan berada di atas seluruh kekuatan politik yang ada. ini untuk menjaga keamanan teritorial dan keutuhan negara kesatuan republik indonesia, kata hidayat nur wahid.                |

---

# Room for Improvement
Room for improvement includes additional training sessions to further minimize the loss values, enhancing the model's accuracy and overall summarization quality.

---
# Attachment
Google Colab: [Bert2GPT](https://colab.research.google.com/drive/1x1l6m5rKQGUszmX3CkqHf9tpvKvMkpzB#scrollTo=gCEldMjP1FnD)
