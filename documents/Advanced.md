**コミットする前に編集した内容を破棄する操作をしよう。**  
**コミットの履歴(ログ)を見てみよう。**  

1. ファイルを編集してステージに追加しよう  
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
    1. `git checkout -- self-introduction.txt` / `git restore self-instroduction.txt`  
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

**reflogを活用しよう。**  

1. reflogを表示しよう    
    1. `git reflog`  

1. reflogから過去の状態に戻そう  
    1. `git reset --hard xxx(戻したい対象のコミット)`  
