安裝wsl
===
- 前提:
  - 主機板支援
  - 開啟hypervisorlaunchtype
    ```
    bcdedit /set hypervisorlaunchtype auto
    ```
- 安裝wsl, 需有管理員權限
  ```
  Enable-WindowsOptionalFeature -Online -FeatureName "Microsoft-Windows-Subsystem-Linux" -All
  ```
- 移除
  ```
  Disable-WindowsOptionalFeature -Online -FeatureName "Microsoft-Windows-Subsystem-Linux"
  ```
- 更新
  ```
  wsl --update
  ```