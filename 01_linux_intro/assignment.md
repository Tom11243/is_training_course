#第１回トレーニングコース課題

##課題１

- Ctrl+R : 過去のコマンドの履歴を参照し、Tabを押すことで決定
- Alt+B  : カーソル位置を一単語左へ移動
- ctrl+A : カーソル位置を行の先頭へ移動
- Alt+F  : カーソル位置を一単語右へ移動
- ctrl+W : カーソル位置の単語を削除

##課題２

1. `which bash` 　whichコマンドは指定したファイルの場所を確認
2. `ls -l <1で表示された場所>`  lsコマンドは指定したディレクトリやファイルの一覧を表示、特に引数-lで詳細を表示
3. `echo $PATH`  echoコマンドは指定したものをそのまま表示

##課題３

1. lsはディレクトリやファイルの情報を一覧表示するコマンドである
2. `-h`を`-l`や`-s`と一緒に使用することでファイルサイズを人が読める単位で表示することができる

##課題４

- アクセスしようとしたファイルが存在しないことを示す
```$ ls no_such_file.txt
ls: cannot access 'no_such_file.txt': No such file or directory
```

- 存在しないコマンドを実行したことを示す
```
$ not_a_real_command
not_a_real_command: command not found
```

- 実行したコマンドの引数が不足していることを示す
```$ rm
rm: missing operand
```

- アクセスしようとしたディレクトリが存在しないことを示す
```$ cd /no/such/dir
-bash: cd: /no/such/dir: No such file or directory
```
