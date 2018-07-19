# VCFのspecificationについて

とりあえず[VCF version 4.3](https://samtools.github.io/hts-specs/VCFv4.3.pdf)を元に考える。

## 必ず必要な事柄

- 必須の８カラム(#CHROM, POS, ID, REF, ALT, QUAL, FILTER, INFO)。
- VCFフォーマットのvalidator toolにかけてOKであること（vcf-validatorなど？）。
- メタデータの統一か（多分reference genomeを記載することなどは必須かと思う）。

## 検討するべき事柄

- validatorの選定。
- INFO, FORMATに何を記載するか？
- annotationをどうするか？VEPを使う？
- SVのフォーマットについてどうするか検討する。


## 気が付いた事柄のメモ

- INFO, FORMATの違いは結局何だろう?（おそらく、INFOは変異自体のアノテーション情報、FORMATはTUMORとNORMALのそれぞれのシークエンスデータに由来する情報）。

## 重要リンク
- https://docs.gdc.cancer.gov/Data/File_Formats/VCF_Format/

## 参考になりそうなツール

- [bcftools](http://www.htslib.org/doc/bcftools.html)
- [vcflib](https://github.com/vcflib/vcflib)
- [vcftools](https://github.com/vcftools/vcftools)
- [vcf-validator](https://github.com/EBIvariation/vcf-validator)
