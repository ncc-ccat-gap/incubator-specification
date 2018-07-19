# VCFのspecificationについて

とりあえず[VCF version 4.3](https://samtools.github.io/hts-specs/VCFv4.3.pdf)を元に考える。

## 必ず必要な事柄

- 必須の８カラム(#CHROM, POS, ID, REF, ALT, QUAL, FILTER, INFO)。
- VCFフォーマットのvalidator toolにかけてOKであること（vcf-validatorなど？）。
- メタデータの統一か（多分reference genomeを記載することなどは必須かと思う）。

## 検討するべき事柄

### validatorの選定

### FILTER, INFO, FORMATに何を記載するか？

まずは、TUMOR, NORMALをペアとして記載する形式をとる方向で行く（Genomic Data Commonsにそう形）。

#### FILTER

種々のフィルタリングの結果を記載する。参考として、

#### INFO

変異自体のアノテーション情報。VEPなどのアノテーションを付与する形か。

#### FORMAT

TUMOR, NORMALのそれぞれのシークエンスデータに由来する情報（変異リード数、変異比率など）。

#### SVのフォーマット

SNV, short indelの検討の後に、詳細を検討（重要であるが、優先順位は少し下がる）。


## 気が付いた事柄のメモ

- INFO, FORMATの違いは結局何だろう?（おそらく、INFOは変異自体のアノテーション情報、FORMATはTUMORとNORMALのそれぞれのシークエンスデータに由来する情報）。

## 重要リンク
- https://docs.gdc.cancer.gov/Data/File_Formats/VCF_Format/

## 参考になりそうなツール

- [bcftools](http://www.htslib.org/doc/bcftools.html)
- [vcflib](https://github.com/vcflib/vcflib)
- [vcftools](https://github.com/vcftools/vcftools)
- [vcf-validator](https://github.com/EBIvariation/vcf-validator)
