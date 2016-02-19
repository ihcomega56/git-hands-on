# HandsOn  

リポジトリを作って、コミット・プッシュしよう。  

1. ローカルリポジトリを作ろう  
`git init firstRepository`  

1. ファイルを作ってステージに追加しよう  
`vi self-introduction.txt`
`git add self-introduction.txt`  

1. ローカルリポジトリにコミットしよう  
`git commit -m "Initial commit"`  

1. GitHubにリモートリポジトリを作ろう  

1. 作成したリモートリポジトリをローカルで追加しよう  
`git add origin ***.git`  

1. リモートリポジトリにプッシュしよう  
`git push origin master`  

コミットする前に編集した内容を破棄する操作をしよう。  
コミットの履歴(ログ)を見てみよう。  

1. リモートリポジトリから新たなローカルリポジトリを作ろう  
`git clone ***.git secondRepository`  

1. ファイルを編集してステージに追加しよう  
`vi self-introduction.txt`
`git add self-introduction.txt`  

1. ステータスを確認しよう  
`git status`  

1. まだコミットしていないファイルを再度編集しよう  
`vi self-introduction.txt`

1. ステータスを確認しよう  
`git status`  

1. ファイルの編集を破棄しよう  
`git checkout -- self-introduction.txt`  

1. ファイルをアンステージしよう  
`git reset self-introduction.txt`        

1. ステータスを確認しよう  
`git status`  

1. ファイルを編集してステージに追加しよう  
`vi self-introduction.txt`
`git add self-introduction.txt`  

1. ローカルリポジトリにコミットしよう  
`git commit -m "自己紹介を編集しました"`  

1. ログを確認しよう  
`git log`  

1. リモートリポジトリにプッシュしよう  
`git push origin master`  

新しいブランチで作業し、元のブランチにマージしよう。  

1. firstRepositoryに戻ろう  

1. secondRepositoryの変更を反映しよう  
`git fetch origin`
`git merge FETCH_HEAD`

1. ログを確認しよう  
`git log`  

1. ブランチを作成しよう  
`git branch first-branch`  

1. ブランチを切り替えよう
`git checkout first-branch`

1. first-branchブランチでファイルを編集してコミットしよう
`vi self-introduction.txt`
`git commit -am "自己紹介を編集しました"`

1. masterブランチとの差分を確認しよう
`git diff master`

1. masterブランチでファイルを編集してコミットしよう
`vi self-introduction.txt`
`git commit -am "自己紹介を編集しました"`

1. first-branchブランチをnon-fast-forwardでマージしよう
`git merge first-branch --no-ff`

1. fast-forwardだとマージコミットが出来ないのを確認しよう
`git checkout -b second-branch`
`git checkout master`
`git merge second-branch --ff`

コンフリクトを解消しよう。  

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

コミットを打ち消そう。  

1. 直前のコミットを打ち消そう(打ち消しの記録を残す)
`git log -1`
`git revert xxx(打ち消す対象のコミット)`

1. 直前のコミットを打ち消そう(完全に抹消する)
`git reset --hard xxx(戻したい対象のコミット)`

reflogを活用しよう。

1. 消したものが残っているか確認してみよう
`git reflog`

1. reflogから前の状態に戻そう
`git reset --hard xxx(戻したい対象のコミット)`