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

1.
 
 1. `$ cp data/sample1.txt memo/sample1_backup.txt`
 2. `$ mv data/sample2.txt data/result.txt`
 3. `$ mv data/sample3.txt memo/`
 4. `$ ln -s ../memo/note1.txt data/link_to_note1.txt`

   ```
   $ cat data/link_to_note1.txt
   test
   ```
 5.
 ```
 $ find -type f
./data/sample1.txt
./data/result.txt
./memo/sample3.txt
./memo/sample1_backup.txt
./memo/note2.txt
./memo/note1.txt
```
 6.
 ```
  $ find -type l
 ./data/link_to_note1.txt
 ```
2.


