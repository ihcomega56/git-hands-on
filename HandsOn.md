# HandsOn

## ひとりでもくもくやってみよう編  

**リポジトリを作って、コミット・プッシュしよう。**  

1. ローカルリポジトリを作ろう  
    1. `mkdir javajo-hands-on`  
    `javajo-hands-on`というディレクトリを作る  
    1. `cd javajo-hands-on`  
    作った`javajo-hands-on`に移動する  
    1. `git init`  
    リポジトリを作り`javajo-hands-on`をGitで管理出来るようにする  

1. .gitディレクトリが出来ているのを確認しよう  
    1. `ls -la`  
    `-a`オプションで隠しファイル/ディレクトリも表示されるよ！  

1. ファイルを作ってステージに追加しよう  
    1. `vi self-introduction.txt`  
    `self-introduction.txt`ファイルを作り、自分の名前を書いて保存する  
    1. `git add self-introduction.txt`  
    ファイルをステージにのせる  

1. ローカルリポジトリにコミットしよう  
    1. `git commit -m "Initial commit"`  
    最初のコミットコメントは`Initial commit`とか`First commit`とすることが多いよ  

1. GitHubにリモートリポジトリを作ろう  
    [スクショ〜]  

1. 作成したリモートリポジトリをローカルで追加しよう  
    1. `git add origin https://github.com/XXXXXX/javajo-hands-on.git`  
    [スクショ〜]  

1. リモートリポジトリにプッシュしよう  
    1. `git push origin master`  
    GitHubのユーザネーム、パスワードを入力する必要があるよ  

**コミットする前に編集した内容を破棄する操作をしよう。**  
**コミットの履歴(ログ)を見てみよう。**  

1. リモートリポジトリから新たなローカルリポジトリを作ろう  
    1. `cd ..`
    1つ上の階層に戻る  
    1. `git clone https://github.com/XXXXXX/javajo-hands-on.git javajo-second`  
    今度は、既に存在するリポジトリをローカルにコピーし、`javajo-second`という名前をつける  

1. ファイルを編集してステージに追加しよう  
    1. `cd javajo-second`
    `javajo-second`に移動する  
    1. `vi self-introduction.txt`  
    `self-introduction.txt`を開くと最初に作ったリポジトリでの編集内容を確認できる  
    名前の下に、自己紹介を付け足して保存する  
    1. `git add self-introduction.txt`  
    ファイルをステージにのせる  

1. ステータスを確認しよう  
    1. `git status`  
    `self-introduction.txt`が`modified`となりステージされているはず！  

1. まだコミットしていないファイルを再度編集しよう  
    1. `vi self-introduction.txt`  
    `self-introduction.txt`に間違った自己紹介を付け足して保存する  

1. ステータスを確認しよう  
    1. `git status`  
    ステージされている変更と、されていない変更が表示されているはず！  

1. ファイルの編集を破棄しよう  
    1. `git checkout -- self-introduction.txt`  
    ステージされていない編集を破棄する  
    よく見ると操作方法が説明されているよ！  
    1. `vi self-introduction.txt`
    間違った自己紹介が消えているはず！  

1. ファイルをアンステージしよう  
    1. `git reset self-introduction.txt`  
    よく見ると操作方法が説明されているよ！  

1. ステータスを確認しよう  
    1. `git status`  
    変更がアンステージされているはず！  

1. ステージに追加しよう  
    1. `git add self-introduction.txt`  

1. ローカルリポジトリにコミットしよう  
    1. `git commit -m "XXXを追記しました"`  
    変更内容をコミットコメントとして残そう  

1. ログを確認しよう  
    1. `git log`  
    ログの表示はいろいろな方法があるよ！:[参考](GitLog.md)  

1. リモートリポジトリにプッシュしよう  
    1. `git push origin master`  

**新しいブランチで作業し、元のブランチにマージしよう。**  

1. javajo-hands-onに戻ろう  
    1. `cd ../javajo-hands-on`  

1. javajo-secondの変更を反映しよう  
    1. `git fetch origin`  
    originの変更を取得する  
    1. `git merge origin/master`  
    ワークツリーに変更を反映させる  

1. ログを確認しよう  
    1. `git log`  

1. ブランチを作成しよう  
    1. `git branch first-branch`  
    `first-branch`ブランチを作成する  

1. ブランチを切り替えよう  
    1. `git checkout first-branch`  
    作業する場所を`master`ブランチから`first-branch`ブランチに切り替える  
    1. `git branch`  
    現在のブランチが`first-branch`になっていることを確認する  

1. first-branchブランチでファイルを編集してコミットしよう  
    1. `vi self-introduction.txt`  
    `self-introduction.txt`に自己紹介を付け足して保存する  
    1. `git commit -am "XXXを追記しました"`  
    `-a`オプションを追加することで変更をすべてステージしてコミットできるよ！  

1. masterブランチとの差分を確認しよう  
    1. `git diff master`  
    ローカルの`master`ブランチと比較する  
    1. `git diff origin/master`  
    リモートの`master`ブランチと比較する  
    差分の表示はいろいろな方法があるよ！:[参考](GitDiff.md)  

1. first-branchブランチをnon-fast-forwardでmasterブランチにマージしよう  
    1. `git checkout master`  
    `master`ブランチに切り替える  
    1. `git merge first-branch --no-ff`  
    `--no-ff`オプションをつけてマージする  
    viエディタが立ち上がってマージコミットのコメントを編集できる(たいてい編集せずデフォルトのままでOK)  

1. ログを確認しよう  
    1. `git log`  

1. fast-forwardだとマージコミットが出来ないのを確認しよう  
    1. `git checkout -b second-branch`  
    `-b`オプションをつけてチェックアウトすることで`second-branch`を作成すると同時に切り替えられるよ！  
    1. `vi self-introduction.txt`  
    `self-introduction.txt`に自己紹介を付け足して保存する  
    1. `git commit -am "XXXを追記しました"`  
    変更をすべてステージしてコミットする  
    1. `git checkout master`  
    `master`ブランチに切り替える  
    1. `git merge second-branch --ff`  
    `--ff`オプションをつけてマージする  

1. ログを確認しよう  
    1. `git log`  

**コンフリクトを解消しよう。**  

1. コンフリクトを発生させよう  
`git checkout first-branch`  
`vi self-introduction.txt`  
`git checkout master`  
`vi self-introduction.txt`  
`git merge first-branch --no-ff`  

1. コンフリクトを解消しよう  
`vi self-introduction.txt`  
`git add self-introduction.txt`  
`git commit -m "コンフリクトを解消しました"`  

**コミットを打ち消そう。**  

1. 直前のコミットを打ち消そう(打ち消しの記録を残す)  
`git log -1`  
`git revert xxx(打ち消す対象のコミット)`  

1. 直前のコミットを打ち消そう(完全に抹消する)  
`git reset --hard xxx(戻したい対象のコミット)`  

**reflogを活用しよう。**  

1. 消したものが残っているか確認してみよう  
`git reflog`  

1. reflogから前の状態に戻そう  
`git reset --hard xxx(戻したい対象のコミット)`  

## みんなでわいわいやってみよう編  