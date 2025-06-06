# Dev Container 使用說明

## 環境需求

- Docker Desktop (Windows/Mac) 或 Docker Engine (Linux)
- Visual Studio Code
- VSCode Remote - Containers 擴展 (ms-vscode-remote.remote-containers)

## 已安裝軟體

- 基礎系統 : Ubuntu 20.04
- CUDA Toolkit: 11.2
- Miniconda: Python 3.8 版本
- Python 套件 :
  - openmm==8.1.1

## 使用步驟

1. 克隆此專案到本地
2. 使用 VSCode 開啟專案資料夾
3. 按下 `Ctrl+Shift+P` 開啟命令面板
4. 選擇 "Dev Containers: Reopen in Container"
5. 等待容器建置完成 ( 首次建置可能需要 5-10 分鐘 )

## 容器建置完成後

- 終端機將自動使用容器內的環境
- 可執行 `python --version` 確認 Python 版本
- 可執行 `conda list` 查看已安裝套件
- 可執行 `nvidia-smi` 確認 CUDA 狀態
- 可執行以下命令檢查系統版本：
  ```bash
  lsb_release -a
  ```

## 開發建議

- 所有 Python 套件安裝請使用 conda:
  ```bash
  conda install [ 套件名稱 ]
  ```
- 如需額外系統套件，可修改 `.devcontainer/Dockerfile` 後重建容器
