安裝git
===
- 免安裝git
  ```
  $ps='install_git_latest.ps1'
  irm -Uri https://gitlab.com/api/v4/projects/58360840/repository/files/$ps/raw | iex
  ```
- 安裝Git(要權限)
  ```
  winget upgrade -e --id Git.Git --source winget
  ```
- 組態
  - 查現在的組態值
    ```
    git config --show-origin <組態>
    git config --show-origin init.defaultBranch #例
    ```
  - 預設主線名稱, 以前叫master, 被認為歧視, 所以現在改為main
    ```
    git config --global init.defaultBranch main #預設主線名
    git branch -m master main #將master改為main
    ```
  - 中文檔案亂碼
    - 執行`git status -s`
    - 中文檔名出現亂碼時, 確認以下設定
      ```
      git config --global core.quotepath false
      ```
