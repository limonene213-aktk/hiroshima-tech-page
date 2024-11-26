<p align="center"><a href="https://learn.microsoft.com/ja-jp/windows/wsl/install" target="_blank"><img src="https://upload.wikimedia.org/wikipedia/commons/thumb/3/35/Tux.svg/800px-Tux.svg.png" width="100" alt="Laravel Logo"></a></p>

# WSLってなに？どうやって使うの？

## 1. **WSLの特徴と利点**
WSL（Windows Subsystem for Linux）は、Windowsの中でLinuxを動かせる機能です！  
たとえば、WindowsのパソコンでLinux専用のソフトやコマンドを使いたいとき、WSLをインストールすると、Linuxを簡単に使えるようになります。

**特徴：**
- WindowsとLinuxを同じパソコンで同時に使える！
- 本物のLinux環境が動く（しかも高速）。
- ファイルをWindowsとLinuxで共有できるから便利。
- 難しい設定をしなくても、すぐに使い始められる。

**利点：**
- **プログラミングの練習に最適**：Linux用のプログラムやツールを試せる。
- **無料で利用可能**：WSL自体は無料で使えます。
- **軽量**：Linux専用のPCを買わなくてもいいし、ハードディスクの容量もあまり使いません。

---

## 2. **BIOSでのCPUの設定（AMD/Intel）**

WSLを動かすには、パソコンのCPUが「仮想化」という機能をオンにしている必要があります。  
以下に、IntelとAMDのパソコンでの設定方法を紹介します。

### **Intel CPUの場合**
1. パソコンを再起動して、起動中に **F2キー** または **DELキー** を押して、BIOS設定画面を開きます。  
   （パソコンによってキーが違う場合があります。起動時に画面下部に表示される「Setup」キーを確認してください。）

2. メニューから「**Advanced**（詳細）」または「**Processor Configuration**（プロセッサ設定）」を選びます。

3. **Intel Virtualization Technology** を「**Enabled**（有効）」にします。

4. 変更を保存して、再起動します。

### **AMD CPUの場合**
1. 再起動後、同じように **F2キー** または **DELキー** でBIOS画面を開きます。

2. 「**Advanced**（詳細）」または「**CPU Configuration**（CPU設定）」を選びます。

3. **SVM Mode（Secure Virtual Machine Mode）** を「**Enabled**（有効）」にします。

4. 変更を保存して再起動します。

---

## 3. **WSLの設定方法**

WSLを使う準備を始めましょう！以下の手順に従えば、簡単に使えるようになります。

### **① WSLをインストールする**
1. **スタートボタン** をクリックして「**PowerShell**」または「**コマンドプロンプト**」と入力し、右クリックして「**管理者として実行**」を選びます。
2. 以下のコマンドを入力します（コピペできます）：
   ```bash
   wsl --install
   ```
3. パソコンが自動的にWSLとUbuntu（Linuxの一つ）をインストールします。

### **② パソコンを再起動する**
- インストールが完了したら、画面の指示に従ってパソコンを再起動します。

### **③ Ubuntuを初期設定する**
1. 再起動後、自動的にUbuntuが起動します。
2. あなたの名前やパスワードを聞かれるので、好きなものを入力します。  
   （注意：パスワードは画面に表示されませんが、ちゃんと入力されています。）

### **④ コマンドを試してみる**
Ubuntuが起動したら、次のコマンドを入力してみましょう：
- 現在の場所を確認する：
  ```bash
  pwd
  ```
- ファイル一覧を見る：
  ```bash
  ls
  ```

---

## **おまけ：トラブルシューティング**

**Q1. WSLがインストールされない？**  
→ PowerShellで以下のコマンドを試してください：
```bash
dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart
dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart
```
その後、パソコンを再起動してもう一度試してみてください。

**Q2. BIOSの設定がわからない？**  
→ メーカーのサポートページを確認するか、周りの詳しい人に相談してみてください。

---

これで、あなたもWSLを使ってLinuxの世界を楽しむ準備ができました！  
もしわからないことがあれば、いつでもこのファイルを読み返してみてくださいね😊

---