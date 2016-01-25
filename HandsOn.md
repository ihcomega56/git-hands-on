1. ローカルリポジトリを作ろう  
`git init firstRepository`  

1. ファイルを作ってステージに追加しよう  
`git add self-introduction.txt`  

1. ローカルリポジトリにコミットしよう  
`git commit -m "Initial commit"`  

1. GitHubにリモートリポジトリを作ろう  

1. 作成したリモートリポジトリをローカルで追加しよう  
`git add origin ***.git`  

1. リモートリポジトリにプッシュしよう  
`git push origin master`  

1. リモートリポジトリから新たなローカルリポジトリを作ろう  
`git clone ***.git secondRepository`  

1. ファイルを編集してステージに追加しよう  
`git add self-introduction.txt`  

1. ステータスを確認しよう  
`git status`  

1. まだコミットしていないファイルを再度編集しよう  

1. ステータスを確認しよう  
`git status`  

1. ファイルの編集を破棄しよう  
`git checkout -- self-introduction.txt`  

1. ファイルをアンステージしよう  
`git reset self-introduction.txt`        

1. ステータスを確認しよう  
`git status`  

1. ファイルを編集してステージに追加しよう  
`git add self-introduction.txt`  

1. ローカルリポジトリにコミットしよう  
`git commit -m "自己紹介を編集しました"`  

1. ログを確認しよう  
`git log`  

1. リモートリポジトリにプッシュしよう  
`git push origin master`  

1. firstRepositoryに戻ろう  

1. secondRepositoryの変更を反映しよう  
`git fetch origin`
`git merge ~~~`

1. ログを確認しよう  
`git log`  

1. ブランチを作成しよう  
`git branch first-branch`  
