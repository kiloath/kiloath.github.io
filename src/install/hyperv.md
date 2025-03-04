
安裝hyper-v
===
- 前提:
  - 主機板支援
  - 開啟hypervisorlaunchtype
    ```
    bcdedit /set hypervisorlaunchtype auto
    ```
- 安裝Hyper-V, 需有管理員權限
  ```
  Enable-WindowsOptionalFeature -Online -FeatureName "Microsoft-Hyper-V" -All
  ```
- 移除Hyper-V
  ```
  Disable-WindowsOptionalFeature -Online -FeatureName "Microsoft-Hyper-V-All"
  ```
- 備忘
  - 不移除管理工具
    ```
    Disable-WindowsOptionalFeature -Online -FeatureName "Microsoft-Hyper-V"
    ```
  - cmd指令
    ```
    dism.exe /online /enable-feature /featurename:"Microsoft-Hyper-V" /ALL
    dism.exe /online /disable-feature /FeatureName:"Microsoft-Hyper-V-All"
    ```