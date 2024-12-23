# WSLのインポートとエクスポート 📦

WSLには、自分が使っているLinux環境を「**エクスポート（保存）**」したり、他のパソコンにその環境を「**インポート（取り込む）**」する機能があります！  
学校や別のパソコンで作ったWSLの環境を、自分のパソコンに持ってくることもできます。

---

## **1. エクスポート（WSL環境を保存する）**

エクスポートをすると、WSLの環境を**バックアップ**として保存できます。保存されたファイルは、他のパソコンに移動して使うことも可能です。

### **エクスポートの手順**
1. **PowerShellを開く**
   - スタートメニューで「**PowerShell**」と検索して、右クリックで「**管理者として実行**」を選びます。

2. **以下のコマンドを実行**
   ```powershell
   wsl --export <ディストリビューション名> <保存するファイル名>
   ```
   - **例**：Ubuntuの環境を`backup.tar`として保存する場合
     ```powershell
     wsl --export Ubuntu backup.tar
     ```

3. **結果**
   - 実行すると、`backup.tar`というファイルが現在のフォルダに作成されます。このファイルにWSL環境のすべてが保存されています。

---

## **2. インポート（WSL環境を取り込む）**

インポートをすると、他のパソコンでエクスポートされたWSL環境を、自分のパソコンに取り込んで使うことができます。

### **インポートの手順**
1. **エクスポートされたファイルをコピー**
   - 他のパソコンからエクスポートされた`.tar`ファイル（例：`backup.tar`）をUSBやネットワーク経由で自分のパソコンにコピーします。

2. **以下のコマンドを実行**
   ```powershell
   wsl --import <新しいディストリビューション名> <保存するフォルダ> <エクスポートされたファイル>
   ```
   - **例**：`backup.tar`を`MyUbuntu`という名前で取り込む場合
     ```powershell
     wsl --import MyUbuntu C:\WSL\MyUbuntu backup.tar
     ```

3. **結果**
   - `MyUbuntu`という名前でWSL環境が登録され、すぐに使えるようになります。

---

## **3. エクスポートとインポートを使う理由**

### **こんなときに便利！**
- **学校のWSL環境を家で使いたい**：
  - 学校で作ったWSL環境をエクスポートして、自宅のパソコンにインポートすれば、全く同じ環境で作業できます。
- **バックアップとして保存したい**：
  - 重要なデータや設定を失いたくない場合、エクスポートしておけば安心です。
- **パソコンを引っ越しするとき**：
  - 新しいパソコンでも、エクスポートした環境をインポートすれば、すぐに同じ環境が使えます。

---

## **4. 自分の環境にインポートする例**

### **学校の環境を取り込む流れ**
1. **学校でエクスポート**
   - 学校のパソコンで、以下のコマンドを実行：
     ```powershell
     wsl --export Ubuntu school_backup.tar
     ```
   - これで、`school_backup.tar`というファイルが作成されます。

2. **ファイルを持ち帰る**
   - USBメモリやクラウドストレージを使って、この`school_backup.tar`を自宅のパソコンにコピーします。

3. **自宅でインポート**
   - 自宅のパソコンで、以下のコマンドを実行：
     ```powershell
     wsl --import SchoolUbuntu C:\WSL\SchoolUbuntu school_backup.tar
     ```

4. **環境を確認**
   - インポートされた環境があるか確認：
     ```powershell
     wsl --list --verbose
     ```
   - 出力例：
     ```
     NAME            STATE           VERSION
     SchoolUbuntu    Stopped         2
     ```

5. **インポートされた環境を使う**
   - インポートした環境を起動：
     ```powershell
     wsl -d SchoolUbuntu
     ```

---

## **5. 便利なコマンドまとめ**

| コマンド                                      | 何をする？                                    |
|----------------------------------------------|----------------------------------------------|
| `wsl --export <名前> <ファイル名>`           | 指定したWSL環境をエクスポートして保存する     |
| `wsl --import <名前> <フォルダ> <ファイル名>` | エクスポートされた環境をインポートする        |
| `wsl --list --verbose`                       | インストールされているWSL環境を一覧表示する   |
| `wsl -d <名前>`                              | 指定したWSL環境を起動する                    |

---

## **6. 練習してみよう！**

以下の手順で、WSL環境のエクスポートとインポートを試してみましょう：

1. **現在のWSL環境をエクスポート**
   ```powershell
   wsl --export Ubuntu my_backup.tar
   ```

2. **エクスポートしたファイルを確認**
   - エクスプローラーで`my_backup.tar`が作成されているか確認します。

3. **インポートして別の環境として登録**
   ```powershell
   wsl --import MyNewUbuntu C:\WSL\MyNewUbuntu my_backup.tar
   ```

4. **新しい環境を起動**
   ```powershell
   wsl -d MyNewUbuntu
   ```

---

これで、WSLのエクスポートとインポートを使って、自分だけのLinux環境を簡単に保存・復元できるようになります！😊  
学校の環境も家でそのまま使えるので、ぜひ試してみてね！

---