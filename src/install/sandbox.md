
安裝sandbox
===
- 前提:
  - 主機板支援
  - 開啟hypervisorlaunchtype
    ```
    bcdedit /set hypervisorlaunchtype auto
    ```
  - 安裝時不要把英文輸入排第一, 會變成英文版。
- 安裝SandBox, 需有管理員權限
  ```
  Enable-WindowsOptionalFeature -Online -FeatureName "Containers-DisposableClientVM" -All
  ```
- 移除SandBox
  ```
  Disable-WindowsOptionalFeature -Online -FeatureName "Containers-DisposableClientVM"
  ```
- 備忘
  - cmd指令
    ```
    dism.exe /online /enable-feature /featurename:"Containers-DisposableClientVM" /ALL
    dism.exe /online /disable-feature /FeatureName:"Containers-DisposableClientVM"
    ```