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
  - openmm[cuda11.2]

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
- 可執行以下命令檢查系統版本：`lsb_release -a`

## 環境驗證

- 可執行以下命令測試 OpenMM 環境是否正常：

  ```bash
  python3 tests/test_openmm.py
  ```

## 開發建議

- Python 套件安裝可使用 conda 或 pip:
  ```bash
  conda install [ 套件名稱 ]   # 或使用 pip install [ 套件名稱 ]
  ```
- 如需額外系統套件，可修改 `.devcontainer/Dockerfile` 後重建容器
