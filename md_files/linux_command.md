# WSLで使えるメジャーなコマンド集 🐧

WSLを使うときに便利なコマンドを初心者向けにまとめました！  
コマンドはターミナル（Ubuntuの画面）で入力してね。

---

## **1. ファイルやフォルダの操作**

### **現在の場所を確認する**
```bash
pwd
```
- **何をする？** 今いるフォルダ（ディレクトリ）の場所を教えてくれます。

---

### **フォルダ内のファイルを表示する**
```bash
ls
```
- **何をする？** 現在のフォルダにあるファイルやフォルダを一覧表示します。
- **オプション：**
  - `ls -l`：詳細な情報も表示。
  - `ls -a`：隠しファイルも表示。

---

### **フォルダを移動する**
```bash
cd フォルダ名
```
- **何をする？** 指定したフォルダに移動します。
- **例：**
  ```bash
  cd Documents
  ```

---

### **新しいフォルダを作る**
```bash
mkdir フォルダ名
```
- **何をする？** 新しいフォルダを作ります。
- **例：**
  ```bash
  mkdir my_project
  ```

---

### **ファイルを削除する**
```bash
rm ファイル名
```
- **何をする？** 指定したファイルを削除します。
- **注意！** 削除したファイルは復元できません。

---

### **フォルダを削除する**
```bash
rm -r フォルダ名
```
- **何をする？** 指定したフォルダと中身をすべて削除します。

---

## **2. システム関連のコマンド**

### **Ubuntuを終了する**
```bash
exit
```
- **何をする？** WSLを終了します。

---

### **ディスク容量を確認する**
```bash
df -h
```
- **何をする？** 使っているディスクや残りの容量を表示します。

---

### **現在動いているプロセスを見る**
```bash
top
```
- **何をする？** CPUやメモリを使っているプログラムの一覧を表示します。

---

## **3. ファイルの内容を操作する**

### **ファイルを作る**
```bash
touch ファイル名
```
- **何をする？** 空のファイルを作ります。
- **例：**
  ```bash
  touch test.txt
  ```

---

### **ファイルの中身を見る**
```bash
cat ファイル名
```
- **何をする？** 指定したファイルの内容を表示します。
- **例：**
  ```bash
  cat test.txt
  ```

---

### **テキストを編集する**
```bash
nano ファイル名
```
- **何をする？** 簡単なテキストエディタが開きます。  
- **ヒント：**
  - 書き終わったら、`Ctrl + O` で保存。
  - `Ctrl + X` で終了。

---

## **4. ネットワーク関連のコマンド**

### **自分のIPアドレスを確認する**
```bash
ip a
```
- **何をする？** ネットワーク設定やIPアドレスを表示します。

---

### **他のコンピュータに接続できるか確認する**
```bash
ping ホスト名またはIPアドレス
```
- **何をする？** 他のコンピュータが動いているかチェックします。
- **例：**
  ```bash
  ping google.com
  ```

---

## **5. パッケージの管理**

### **ソフトをアップデートする**
```bash
sudo apt update && sudo apt upgrade
```
- **何をする？** インストール済みのソフトやパッケージを最新にします。

---

### **ソフトをインストールする**
```bash
sudo apt install パッケージ名
```
- **何をする？** 新しいソフトやツールをインストールします。
- **例：**
  ```bash
  sudo apt install git
  ```

---

### **インストール済みのソフトを削除する**
```bash
sudo apt remove パッケージ名
```
- **何をする？** 指定したソフトを削除します。

---

## **6. ヘルプを確認する**

### **コマンドの使い方を調べる**
```bash
man コマンド名
```
- **何をする？** 指定したコマンドの詳しい説明を表示します。
- **例：**
  ```bash
  man ls
  ```

---

これらのコマンドを使えるようになると、WSLでの操作がもっと楽しくなりますよ！✨  
最初は難しく感じるかもしれませんが、少しずつ慣れていきましょう😊

---