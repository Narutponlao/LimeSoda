
# LimeSoda

Thai fake news dataset in the healthcare domain consisting of curate and manually annotated 7,191 documents (only 4,141 documents contain token labels and are used as a test set of the baseline models).

Each document in the dataset is classified as fact, fake, or undefined. Moreover, we also provide token-level annotations for validating classifier decisions based on five high-level annotation tags: misleading headline, imposter, fabrication, false connection, and misleading content.

## Dataset Organization

<pre>
LimeSoda/
  -LimeSoda/
    -Duplicated_Limesoda.jsonl
    -Limesoda.jsonl
  -README.md
</pre>

Please note that the duplicated documents has been splitted into "Duplicated_Limesoda.jsonl" already.

## Dataset Format

Each line in the jsonlines file contains:
- **Title** - a news headline which tokenized by PyICU 2.4.3.
- **Detail** - a news content which tokenized by PyICU 2.4.3.
- **Title Token Tags** - a token labels of a news headline (token-level tags).
- **Detail Token Tags** - a token labels of a news content (token-level tags).
- **Document Tag** - "Fact News", "Fake News", or "Undefined"

## Get Started

<pre>
import json
from typing import Dict, List


def read_jsonlines(file_path: str) -> List[Dict]:
    with open(file_path) as fp:
        return [json.loads(line) for line in fp.readlines()]


data = read_jsonlines(<i><b>"put your file path here"</b></i>)
</pre>

## Citation

If you find this repo useful, please cite our paper.

<pre>
@INPROCEEDINGS{9678187,
  author={Payoungkhamdee, Patomporn and Porkaew, Peerachet and Sinthunyathum, Atthasith and Songphum, Phattharaphon and Kawidam, Witsarut and Loha-Udom, Wichayut and Boonkwan, Prachya and Sutantayawalee, Vipas},
  booktitle={2021 16th International Joint Symposium on Artificial Intelligence and Natural Language Processing (iSAI-NLP)}, 
  title={LimeSoda: Dataset for Fake News Detection in Healthcare Domain}, 
  year={2021},
  volume={},
  number={},
  pages={1-6},
  doi={10.1109/iSAI-NLP54397.2021.9678187}
}
</pre>


