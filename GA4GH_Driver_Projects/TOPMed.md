# TOPMedについて

とりあえずTOPMedについて調査していて考えたことをいかに記述

## まずTOPMedの特徴
- ここの（https://www.nhlbi.nih.gov/science/trans-omics-precision-medicine-topmed-program）AT A GLANCEがわかりやすい
- 様々な疾患で、120,000WGSを収集する。合わせて、RNA, metaboliteなどのオミックスデータを一部収集する。

## パイプラインについて勉強になるリンク集
- https://www.nhlbiwgs.org
- https://www.nhlbiwgs.org/topmed-whole-genome-sequencing-project-freeze-5b-phases-1-and-2
- https://www.nhlbiwgs.org/standards

## とりあえずパッと見てわかった知見
- TOPMedはCRAM formatで行くようだ。CRAMについてやはり早い段階で検証を加えたい。上記のリンクでCRAMを生成するパイプラインもあるそうなので、参考にしたい。
- [RNA-seQC](https://software.broadinstitute.org/cancer/cga/rna-seqc)は要チェック使えそう（ただ、githubを見た限りリンク切れだったりして、ちょっとどうかなとも思った）。
- GRCh38DHというのがあり、1000 genomeのサイトから取れるらしい。ただ、がんではウイルスが重要だと思うので、考慮する必要あり。
- 重複除去で、sambamba, samblaster, PICARD, bamUiltsを評価しているとのこと。これらについてはできれば評価したい。

