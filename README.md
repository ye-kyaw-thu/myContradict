# myContradict: Contradictory Sentence Generation for Myanmar language

## Overview
This dataset contains pairs of sentences in the Myanmar language, where each pair consists of an original sentence and its manually created contradictory version. The dataset is designed to support research in natural language understanding, particularly in the area of sentence contradiction and semantic analysis.
The source files are noted with src and target files are with tgt for both syllable- and word-level parallel corpora. We also put POS-Tagged corpora, which was used in our experiments. For the experiments, we used OpenNMT and we shared our yaml files for baseline experiments.

## Dataset Statistics

| Split       | No. of Syllables | No. of Words | No. of Sentences |
|-------------|------------------|--------------|------------------|
| **Train**   | 150,986 (Source) / 151,007 (Target) | 112,917 (Source) / 112,900 (Target) | 9,702 (Source) / 9,702 (Target) |
| **Valid**   | 18,613 (Source) / 18,622 (Target) | 14,050 (Source) / 14,043 (Target) | 1,214 (Source) / 1,214 (Target) |
| **Test**    | 19,418 (Source) / 19,392 (Target) | 14,498 (Source) / 14,499 (Target) | 1,214 (Source) / 1,214 (Target) |

## Segmentation Examples

The dataset includes different segmentations of sentences, both with and without Part-of-Speech (POS) tags. Below is an example of the word **"ကရုဏာသက်"** (compassionate) segmented in various ways:

| Description               | Segmentation Example                                                                 |
|---------------------------|-------------------------------------------------------------------------------------|
| Syllables without POS Tags | က ရု ဏာ သက်                                                                    |
| Syllables with POS Tags    | က\|B-n ရု\|I-n ဏာ\|E-n သက်\|S-v                                                  |
| Words without POS Tags     | ကရုဏာ သက်                                                                    |
| Words with POS Tags        | ကရုဏာ\|n သက်\|v                                                                  |

## Dataset Preparation

The dataset was created by collecting random sentences and manually converting them into their contradictory forms. Two native speakers (one male and one female) performed the conversion, and the pairs were verified by a domain expert. The sentences were then segmented into syllables and words using the **myWord** tool, followed by manual validation.

### Types of Contradictions
In the Myanmar language, nouns, verbs, and post-positional markers are crucial for understanding sentence meaning. The dataset focuses on three main types of contradictions:

1. **Negation**:  
   - Example: `ရ|v ပါ|part တယ်|ppm` → `မ|part ရ|v ပါ|v ဘူး|ppm`  
     (Translation: *It is okay.* → *It is not okay.*)  
   - In negation, the verb is modified with a negative particle (`မ`), and post-positional markers are adjusted.

2. **Antonyms**:  
   - Example: `ဝ|v တဲ့|part ပုဂ္ဂိုလ်|n က|ppm ကျွန်မ|pron တို့|part အဖေ|n ပါ|ppm` → `ကျွန်မ|pron တို့|part အဖေ|n က|part ပိန်|v ပါ|part တယ်|ppm`  
     (Translation: *Fat person is our father.* → *Our father is thin.*)  
   - Here, the verb `ဝ` (fat) is replaced with its antonym `ပိန်` (thin).

3. **Counterpart**:  
   - Example: `မန္တလေး|n သို့|ppm သွား|v သည်|ppm` → `မန္တလေး|n မှ|ppm လာ|v သည်|ppm`  
     (Translation: *He goes to Mandalay.* → *He comes from Mandalay.*)  
   - This involves changing post-positional markers and verbs to indicate temporal or directional opposites.

## POS Tagging
For training multi-feature models, POS tagging was performed using the **myPOS** version 3.0 model, which leverages the **RDRPOSTagger** and achieves an F1-score of 96.53%. POS tags are provided at the word level, and for syllable-level tagging, a BIES (Begin, Inside, End, Single) scheme is used.

## Citation

If you use this dataset in your work, please cite the following paper:

```bibtex
@inproceedings{thu2024mycontradict,
  title={myContradict: Semi-supervised Contradictory Sentence Generation for Myanmar Language},
  author={Thu, Ye Kyaw and Nwe, Ei Myat and Aung, Thura},
  booktitle={2024 19th International Joint Symposium on Artificial Intelligence and Natural Language Processing (iSAI-NLP)},
  pages={1--6},
  year={2024},
  doi={10.1109/iSAI-NLP64410.2024.10799350},
  keywords={Semantics; Neural networks; Bidirectional long short term memory; Semi-supervised learning; Linguistics; Transformers; Tokenization; Artificial intelligence; self-training; sentence generation; Myanmar language; compositional semantics},
  location={Chonburi, Thailand}
}
```

## Contributions
- Conceptualization: Ye Kyaw Thu
- Data collection and validation: Thura Aung, Ei Myat Nwe
- Data annotation: Ei Myat Nwe, Thura Aung
- Experiments: Thura Aung, Ye Kyaw Thu

## License
Creative Commons Attribution-NonCommercial-Share Alike 4.0 International (CC BY-NC-SA 4.0) [For more details](https://creativecommons.org/licenses/by-nc-sa/4.0/)

## Acknowledgement
We would like to show our gratitude to Myat Noe Oo, Robotics and AI Engineering, KMITL for providing us computing resources to train text-to-text translation models.

## References
- **myWord Tool**: [GitHub Repository](https://github.com/ye-kyaw-thu/myWord)
- **myPOS Tool**: [GitHub Repository](https://github.com/ye-kyaw-thu/myPOS)
- **RDRPOSTagger**: [Reference Paper](https://aclanthology.org/P12-3005/)
- **OpenNMT**: [OpenNMT](https://opennmt.net/)

## Corresponding authors
- Ye Kyaw Thu [Email](ykt.nlp.ai@gmail.com) [Website](https://sites.google.com/site/yekyawthunlp/)
- Thura Aung [Email](thuraaung.ai.mdy@gmail.com) [LinkedIn](https://www.linkedin.com/in/thura-aung)
