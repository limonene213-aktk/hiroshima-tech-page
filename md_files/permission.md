# パーミッション（アクセス権）の基本 🛡️

Linuxでは、ファイルやディレクトリを守るために「**パーミッション（アクセス権）**」という仕組みを使います。この仕組みで、誰がどのファイルやフォルダにアクセスできるかを管理します。

---

## **1. パーミッションを確認する：`ls -l`コマンド**

### **基本コマンド**
```bash
ls -l
```
- **何をする？** ファイルやディレクトリの詳細な情報を表示します。

#### **例**
```bash
ls -l
```
**出力例**：
```
-rw-r--r--  1 user group 1024 Nov 26 14:00 file.txt
drwxr-xr-x  2 user group 4096 Nov 26 14:00 my_folder
```

---

## **2. ls -lの出力の見方**

### **1行の意味**
```plaintext
-rw-r--r--  1 user group 1024 Nov 26 14:00 file.txt
```

#### **各部分の説明**
| **部分**          | **例**        | **意味**                                                                            |
|-------------------|--------------|------------------------------------------------------------------------------------|
| **1文字目**       | `-` or `d`   | `-`：ファイル、`d`：ディレクトリ                                                   |
| **2〜10文字目**   | `rw-r--r--`  | パーミッション（後で詳しく説明）                                                   |
| **リンク数**      | `1`          | このファイルがリンクされている数                                                   |
| **ユーザー名**     | `user`       | このファイルの所有者（ユーザー名）                                                |
| **グループ名**     | `group`      | 所有者が属するグループ名                                                          |
| **ファイルサイズ** | `1024`       | ファイルのサイズ（バイト単位）                                                    |
| **日付**          | `Nov 26 14:00` | 最後に変更された日時                                                             |
| **名前**          | `file.txt`   | ファイルやディレクトリの名前                                                      |

---

### **先頭の`-`と`d`の違い**

- **`-`**：これは普通のファイルを表します。
- **`d`**：これはディレクトリ（フォルダ）を表します。

#### **例**
```plaintext
-rw-r--r--  file.txt       ← ファイル
drwxr-xr-x  my_folder      ← ディレクトリ
```

---

## **3. パーミッション（rw-r--r--）の読み方**

パーミッションは、9つの文字で構成されています。

#### **例：`rw-r--r--`**
```plaintext
rw-   r--   r--
↓     ↓     ↓
所有者 グループ 他のユーザー
```

### **意味の詳細**
- **`r`（read）**：読む権限。
- **`w`（write）**：書き込み（編集）権限。
- **`x`（execute）**：実行する権限（ファイルをプログラムとして実行したり、ディレクトリを開く権限）。

#### **区切り方**
| **対象**           | **意味**                      | **例**（`rw-r--r--`の場合） |
|--------------------|------------------------------|---------------------------|
| **所有者（最初の3文字）** | このファイルの持ち主の権限       | `rw-`（読む＋書くができる） |
| **グループ（次の3文字）** | 同じグループの人たちの権限       | `r--`（読むだけができる）   |
| **他のユーザー（最後の3文字）** | それ以外の人たちの権限          | `r--`（読むだけができる）   |

---

## **4. すべてのファイルを表示：`ls -la`**

### **基本コマンド**
```bash
ls -la
```
- **何をする？** 隠しファイルも含めて、すべてのファイルとディレクトリを表示します。

#### **例**
```bash
ls -la
```
**出力例**：
```
drwxr-xr-x  2 user group 4096 Nov 26 14:00 .
drwxr-xr-x  3 user group 4096 Nov 26 14:00 ..
-rw-r--r--  1 user group 1024 Nov 26 14:00 .hidden_file
-rw-r--r--  1 user group 1024 Nov 26 14:00 file.txt
```

### **ポイント**
- `.`：現在のディレクトリ。
- `..`：1つ上のディレクトリ。
- `.`で始まるファイル：隠しファイル（**ドットファイル**という）。

---

## **5. パーミッションの変更**

パーミッションを変更すると、アクセス権を自由に設定できます。

### **基本コマンド：`chmod`**
```bash
chmod 権限 ファイル名
```

#### **例：所有者だけが読み書きできるようにする**
```bash
chmod 600 file.txt
```

#### **数字の意味**
| **数字** | **パーミッション**  | **意味**              |
|----------|--------------------|----------------------|
| `7`      | `rwx`             | 読む＋書く＋実行      |
| `6`      | `rw-`             | 読む＋書く            |
| `5`      | `r-x`             | 読む＋実行            |
| `4`      | `r--`             | 読むだけ              |
| `0`      | `---`             | 何もできない          |

---

## **6. 練習してみよう！**

1. **現在のパーミッションを確認**
   ```bash
   ls -l
   ```

2. **新しいファイルを作成**
   ```bash
   echo "Hello, World!" > my_file.txt
   ```

3. **隠しファイルを表示**
   ```bash
   ls -la
   ```

4. **パーミッションを変更**
   ```bash
   chmod 644 my_file.txt
   ```

5. **変更後のパーミッションを確認**
   ```bash
   ls -l
   ```

---

## **7. ポイントまとめ**

- **`ls -l`**：詳細情報を確認。
- **`ls -la`**：隠しファイルを含めたすべてのファイルを表示。
- **`-`と`d`の違い**：ファイルかディレクトリか。
- **パーミッションの読み方**：
  - `rw-`：読む＋書く。
  - `r--`：読むだけ。
- **パーミッションの変更**：`chmod`コマンドを使う。

---

これで、Linuxのパーミッションをしっかり理解できるようになります！😊  
少しずつ練習して、ファイルやディレクトリを安全に管理できるようになりましょう。

---