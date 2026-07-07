#第２回トレーニングコース課題

##課題１

1. 実行したコマンドと出力
```
$ ls -R linux_practice
linux_practice:
data  memo

linux_practice/data:
sample1.txt  sample2.txt  sample3.txt

linux_practice/memo:
note1.txt  note2.txt
```

2. 主要なコマンドの説明

- `mkdir`: 指定した名称のディレクトリを作成
- `cd`   : 指定したディレクトリへ移動
- `touch`: 指定した名称の空ファイルを作成
- `ls -R <場所>`: 指定したディレクトリ下にある全てのディレクトリ内容を表示

##課題２

1.　実行コマンドと結果

 （1） `$ cp data/sample1.txt memo/sample1_backup.txt`
 
 （2） `$ mv data/sample2.txt data/result.txt`
 
 （3） `$ mv data/sample3.txt memo/`
 
 （4） `$ ln -s ../memo/note1.txt data/link_to_note1.txt`

   ```
   $ cat data/link_to_note1.txt
   test
   ```
 （5）
 ```
 $ find -type f
./data/sample1.txt
./data/result.txt
./memo/sample3.txt
./memo/sample1_backup.txt
./memo/note2.txt
./memo/note1.txt
```
 （6）
 ```
  $ find -type l
 ./data/link_to_note1.txt
 ```
2. `cp`を用いると、パスが複製されるが、`mv`は移動をしている。したがって、`mv`で同じディレクトリを指定することで名称変更される。また、シンボリックでは特定のパスの指定を行っている（ショートカットキー）。

##課題３

1.`$ printf "apple 80 red\nbanana 120 yellow\napple 80 red\ncherry 150 red\n" > data.txt`
 （1）
 ```
$ cat data.txt
apple 80 red
banana 120 yellow
apple 80 red
cherry 150 red
```
 （2）
```
$ awk '{ print $1, $3 }' data.txt
apple red
banana yellow
apple red
cherry red
```
 （3）
```
$ awk '$2 > 100 { print $0 }' data.txt
banana 120 yellow
cherry 150 red
```
 （4）
```
$ sort data.txt | uniq -c
      2 apple 80 red
      1 banana 120 yellow
      1 cherry 150 red
```
 （5）`$ sed 's/apple/orange/g' data.txt > data_replaced.txt`
 
 （6）
```
$ diff data.txt data_replaced.txt
1c1
< apple 80 red
---
> orange 80 red
3c3
< apple 80 red
---
> orange 80 red
```

2. コマンドの説明
   -`awk`: 列ごとにテキストファイルを扱う
   -`sort`: テキストファイルの行を並べ替える
   -`uniq`: 連続する重複行をまとめる（削除する）
   -`sed`: テキストの置換
   -`diff`: ２つのファイルの内、異なっている箇所を表示

##課題４

見えないプロンプトインジェクションとは、人間に見えている画面では表示されない文字をプロンプト内に忍び込ませて、人間が想定した動作と異なった動作をAIに引き起こさせる攻撃手口である。現在、一部の生成AIでは様々なデータを元に日々知識データベースが強化されているが、データの中には、例に挙げたような悪意のあるコンテンツが含まれている可能性がある。AIがそれらを学習することで意図しない動作を行ってしまう危険性がある。対策としては、信頼できないソース元からの指示文のコピペなどを行う際はUI上で表示されない文字が含まれるかを確認することや、生成AIの強化をしている場合は全てのソースに対してフィルタリングを行うことなどが重要である。他にも、システムプロンプトとユーザー入力を分けたり、ユーザー入力で許容する文字や形式を制限したりすることで被害を抑えることができる。

##参考文献
- https://www.trendmicro.com/ja_jp/research/25/b/invisible-prompt-injection-secure-ai.html
- https://zenn.dev/banboobloom/articles/2025020700001
