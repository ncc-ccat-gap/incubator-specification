## Validatorの選定

### [vcf-validator](https://github.com/EBIvariation/vcf-validator)

- 厳しいフォーマットチェックを行っている。[参照](https://docs.google.com/document/d/1Wcr2fjzwQ7NmxvqZEbiT7GVck8dLyWG2KvzmOxXAVfs/edit)
- リファレンスゲノムとREFの整合性はチェックしていない。[参照](https://github.com/EBIvariation/vcf-validator/issues/7)
- mutect2で出力したVCFファイルはvcf-validatorにかけるとエラーとなる。[参照](https://github.com/sigven/pcgr/issues/28)

### vcflibの[vcfcheck](https://github.com/vcflib/vcflib#vcfcheck)

- VCF REFフィールドと指定したリファレンスゲノムが一致しているか確認できる。
- フォーマットエラーのチェックをしていない（実施により確認）

### [GATK](https://software.broadinstitute.org/gatk/documentation/tooldocs/current/org_broadinstitute_hellbender_tools_walkers_variantutils_ValidateVariants.php)

- 基本的なフォーマットチェックはされるが、1つエラーを検出するとThrow Exceptionでエラー終了するので使い勝手が悪い。コマンド名から推察できるがフォーマットチェックがメインではない印象を受けた。
- INFOフィールドのAC,ANやFORMATフィールドGTなどGATK独自の厳重なチェックが行われる。VCF Version 4.2 Speciﬁcationからはこの厳重なチェックをしている理由がわからなかった。
- mutect2で出力したVCFファイルはエラーにならない。 

## ツール
上記の3つのValidatorを簡単に使用するためにラッパーツールを作成した。
そのツールはDockerファイルを使用して3つのValidatorをインストールし、入力したVCFのValidationを行う。
github: ken0-1n/[three-arrowed-vcf-validator](https://github.com/ken0-1n/three-arrowed-vcf-validator)

