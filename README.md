# Exchange Board

Spring Boot + MySQL を使った掲示板アプリケーションです。  
ローカル環境や Docker 上で動かすことができます。

---

## 🚀 開発環境セットアップ

### ✅ 前提
- Git
- Docker / Docker Compose
- JDK 17+
- Gradle (※ `./gradlew` でも可)

---

### 🪟 Windows の場合
Windows で開発する場合は **WSL2 (Ubuntu 推奨)** を利用してください。

1. [WSL2 のインストール手順 (Microsoft Docs)](https://learn.microsoft.com/ja-jp/windows/wsl/install) に従ってセットアップ

   [こういうの](https://www.kagoya.jp/howto/cloud/container/wsl2_docker/)を参考にしてDockerとDocker composeまでいれておいてね
3. Ubuntu ターミナルを開き、このリポジトリを clone  (パスは私はこんな感じ：\\wsl.localhost\Ubuntu\home\ユーザー名\work\exchange-board）
   ```bash
   git clone https://github.com/zoshigaya/exchange-board.git
   cd exchange-board
   ```
5. 以降は Mac と同じ手順で実行できます

### 🍎 Mac の場合
Mac の方はそのまま以下の手順を実行してください。
  ```bash
  git clone https://github.com/zoshigaya/exchange-board.git
  cd exchange-board
  ```

---

### 🐳 Docker を使った起動方法
1. コンテナ起動
  ```bash
  docker-compose up -d
  ```

- db (MySQL 8.0) がポート 3306 で起動
- backend (Spring Boot) がポート 8080 で起動

2. 動作確認

- API: http://localhost:8080
- MySQL 接続情報
  - Host: localhost
  - Port: 3306
  - User: appuser
  - Password: apppass
  - Database: exchange_board


### 💡 Tips

- .env ファイルは コミットしないでください。
代わりに .env.example を参考にしてください。

- Windows 環境では gradlew の実行権限が落ちることがあります。
その場合は以下で権限を付与してください:
  ```bash
    chmod +x backend/gradlew
  ```

- VSCodeの拡張
    - Docker
    - ESLint（インデントとか見てくれる）
    - EditorConfig for VSCode
    - Github Copilot
    - Github Copilot Chat
    - Gradle for Java
    - YAML
  拡張機能はこんな感じかな
VSCodeのセットアップは[こちら](https://qiita.com/hiropon1839/items/0f48d85733ad0c85b3b1)
