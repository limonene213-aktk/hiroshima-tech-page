# wsl.confの設定について ✏️

**`wsl.conf`** は、WSL（Windows Subsystem for Linux）の設定をカスタマイズするためのファイルです。  
これを使うことで、WSLの動作を細かく制御できます！  
特に、**ログインするユーザーの指定**や、**`systemd`の有効化**が簡単に行えます。

---

## **1. wsl.confの場所**

`wsl.conf` は各WSLディストリビューション内にあります。

### **ファイルの場所**
```plaintext
/etc/wsl.conf
```

- このファイルを編集することで設定を変更できます。

---

## **2. wsl.confの基本構造**

`wsl.conf` は、次のようにセクションごとに設定を書きます：
```ini
[セクション名]
キー=値
```

### **よく使うセクション**
- `[user]`：ログイン時のユーザーを指定します。
- `[boot]`：`systemd`を有効化します。
- `[automount]`：Windowsのドライブを自動マウントする設定を行います。

---

## **3. ログインするユーザーの指定**

WSLを起動したときに、特定のユーザーでログインするように設定できます。

### **手順**
1. `wsl.conf`ファイルを編集：
   ```bash
   sudo nano /etc/wsl.conf
   ```

2. 次の内容を追加：
   ```ini
   [user]
   default=ユーザー名
   ```

   - **例**：`testuser`でログインしたい場合
     ```ini
     [user]
     default=testuser
     ```

3. WSLを再起動：
   ```powershell
   wsl --shutdown
   ```
   - 再びWSLを起動すると、指定したユーザーでログインします。

---

## **4. systemdを有効化する**

`systemd`は、Linuxのプロセス管理やサービス起動を行う仕組みです。  
WSLで`systemd`を有効化すると、`systemctl`コマンドが使えるようになります！

### **手順**
1. `wsl.conf`ファイルを編集：
   ```bash
   sudo nano /etc/wsl.conf
   ```

2. 次の内容を追加：
   ```ini
   [boot]
   systemd=true
   ```

3. WSLを再起動：
   ```powershell
   wsl --shutdown
   ```

4. 有効化を確認：
   ```bash
   systemctl list-units
   ```

---

## **5. wsl.confの他の便利な設定**

### **Windowsのドライブを自動マウントしない**
- WSL起動時にWindowsのCドライブやDドライブをマウントしたくない場合の設定です。

#### **手順**
1. `wsl.conf`ファイルを編集：
   ```bash
   sudo nano /etc/wsl.conf
   ```

2. 次の内容を追加：
   ```ini
   [automount]
   enabled=false
   ```

3. WSLを再起動：
   ```powershell
   wsl --shutdown
   ```

---

## **6. wsl.confの設定例**

### **例1：ログインするユーザーとsystemdの有効化**
```ini
[user]
default=testuser

[boot]
systemd=true
```

### **例2：Windowsドライブを自動マウントしない**
```ini
[automount]
enabled=false
```

---

## **7. よくあるトラブルと解決方法**

### **`systemd`が有効にならない**
- **確認**：WSLのバージョンが2であることを確認。
  ```powershell
  wsl --list --verbose
  ```
  **結果例**：
  ```
  NAME            STATE           VERSION
  Ubuntu          Stopped         2
  ```

- **解決方法**：WSLをバージョン2に変更。
  ```powershell
  wsl --set-version ディストリビューション名 2
  ```

---

## **8. wsl.confの変更を適用する方法**

1. `wsl.conf`を編集後、必ずWSLを再起動してください：
   ```powershell
   wsl --shutdown
   ```

2. 再びWSLを起動すると、変更が適用されています。

---

## **9. 練習してみよう！**

1. **ユーザーを変更**
   - `testuser`というユーザーでログインする設定を追加。
     ```ini
     [user]
     default=testuser
     ```

2. **systemdを有効化**
   - 次の内容を追加。
     ```ini
     [boot]
     systemd=true
     ```

3. **設定の確認**
   - WSLを再起動し、以下を実行して確認：
     ```bash
     systemctl list-units
     ```

---

これで、`wsl.conf`を使った設定変更がマスターできるはずです！😊  
ログインするユーザーや`systemd`の有効化など、必要に応じて試してみてくださいね！

---