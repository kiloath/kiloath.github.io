windows docker
===
- 前提:
  - 主機板支援
  - 開啟hypervisorlaunchtype
    ```
    bcdedit /set hypervisorlaunchtype auto
    ```
  - 已完成 [安裝Hyper-V](./install/hyperv.md)
- 安裝container
  ```
  Enable-WindowsOptionalFeature -Online -FeatureName "containers" -All
  ```
- 移除container
  ```
  Disable-WindowsOptionalFeature -Online -FeatureName "containers"
  ```
- 安裝Docker
  ```
  $v='28.0.1';$ps='install_docker.ps1'
  irm -Uri https://gitlab.com/api/v4/projects/58360840/repository/files/$ps/raw | iex
  ```
- 執行Start-Service docker後, 就會建立C:\ProgramData\docker目錄
  - 新增`C:\ProgramData\docker\config\daemon.json`檔案
  - daemon.json
    ```
    {
      "experimental": false,
      "hosts": [
        "npipe:////./pipe/docker_engine_windows"
      ]
    }
    ```
  - 修改接口
    ```
    Stop-Service docker
    Start-Service docker
    docker context create win --docker "host=npipe:////./pipe/docker_engine_windows"
    docker context use win
    ```
  - 設定powershell
    ```
    notepad $PROFILE
    ```
  - $PROFILE
    ```
    Set-Alias docker "$HOME\KiloathApp\docker\docker\docker.exe"
    ```


