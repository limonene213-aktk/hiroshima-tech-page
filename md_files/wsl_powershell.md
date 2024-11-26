# PowerShellで使うWSL関連のコマンド集 🖥️

WSLを使うために、Windows側（PowerShell）で実行するコマンドをまとめました。  
これを覚えれば、WSLのインストールや設定がもっと簡単になります！

---

## **1. WSLのインストールと基本操作**

### **WSLをインストールする**
```powershell
wsl --install
```
- **何をする？** WSLとデフォルトのLinuxディストリビューション（通常はUbuntu）を一括でインストールします。

---

### **利用可能なLinuxディストリビューションを表示する**
```powershell
wsl --list --online
```
- **何をする？** インストール可能なLinuxの種類を一覧表示します。

---

### **特定のLinuxディストリビューションをインストールする**
```powershell
wsl --install -d ディストリビューション名
```
- **何をする？** 選んだLinuxをインストールします。
- **例：**
  ```powershell
  wsl --install -d debian
  ```

---

## **2. WSLの管理**

### **インストール済みのディストリビューションを確認する**
```powershell
wsl --list --verbose
```
- **何をする？** すでにインストールされているLinuxディストリビューションの一覧を表示します。

---

### **WSLを起動する**
```powershell
wsl
```
- **何をする？** デフォルトのLinuxディストリビューションを起動します。

---

### **特定のディストリビューションを起動する**
```powershell
wsl -d ディストリビューション名
```
- **何をする？** 指定したLinuxディストリビューションを起動します。
- **例：**
  ```powershell
  wsl -d ubuntu
  ```

---

### **WSLを終了する**
```powershell
wsl --shutdown
```
- **何をする？** 全てのWSLプロセスを停止します。メモリやCPUの使用をリセットしたいときに便利。

---

## **3. 設定の変更**

### **デフォルトのディストリビューションを設定する**
```powershell
wsl --set-default ディストリビューション名
```
- **何をする？** デフォルトで起動するLinuxを変更します。
- **例：**
  ```powershell
  wsl --set-default debian
  ```

---

### **WSLのバージョンを確認する**
```powershell
wsl --version
```
- **何をする？** 現在使っているWSLのバージョンを表示します。

---

### **特定のディストリビューションのWSLバージョンを変更する**
```powershell
wsl --set-version ディストリビューション名 バージョン番号
```
- **何をする？** 指定したディストリビューションをWSL1またはWSL2に変更します。
- **例：**
  ```powershell
  wsl --set-version ubuntu 2
  ```

---

## **4. ファイルやディスクの操作**

### **WindowsからLinuxファイルを開く**
```powershell
explorer.exe .
```
- **何をする？** 現在のLinuxのフォルダをWindowsのエクスプローラーで開きます。

---

### **WSLのディスク使用量を確認する**
```powershell
wsl --status
```
- **何をする？** WSLの状態やディスク容量を表示します。

---

## **5. トラブルシューティング**

### **WSLの状態をリセットする**
```powershell
wsl --unregister ディストリビューション名
```
- **何をする？** 指定したLinuxディストリビューションを削除（リセット）します。  
- **注意！** 削除するとデータが消えるので、慎重に！

---

### **すべてのWSL設定を再インストールする**
```powershell
wsl --install --force
```
- **何をする？** WSLを再インストールして、初期状態に戻します。

---

これらのPowerShellコマンドを使いこなせば、WSLの管理がとても簡単になります！初心者でも安心して試してみてくださいね😊

---