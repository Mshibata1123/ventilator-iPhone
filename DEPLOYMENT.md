# GitHubへのデプロイ方法

このガイドでは、人工呼吸器アラーム対応トレーニングアプリをGitHubにアップロードし、スマートフォンでアクセスできるようにする手順を説明します。

## 1. GitHubリポジトリの作成

1. [GitHub](https://github.com)にログイン
2. 右上の「+」メニューから「New repository」を選択
3. リポジトリ名を入力（例：`ventilator-training-app`）
4. Public（公開）を選択
5. 「Create repository」をクリック

## 2. ファイルのアップロード

### 方法A: GitHub Web UIを使用

1. 作成したリポジトリのページで「uploading an existing file」をクリック
2. 以下のファイルをドラッグ&ドロップ：
   - `index.html`
   - `high_pressure_alarm.mp4`
   - `Servo_air.jpg`
   - `Puppy.jpg`
   - `EVO.jpg`
   - `README.md`
   - `.gitignore`
3. 「Commit changes」をクリック

### 方法B: Git コマンドラインを使用

```bash
# リポジトリをクローン
git clone https://github.com/[あなたのユーザー名]/[リポジトリ名].git
cd [リポジトリ名]

# ファイルをコピー
# （プロジェクトフォルダから必要なファイルをコピー）

# ファイルを追加
git add index.html high_pressure_alarm.mp4 *.jpg README.md .gitignore

# コミット
git commit -m "Initial commit: 人工呼吸器トレーニングアプリを追加"

# プッシュ
git push origin main
```

## 3. GitHub Pagesの有効化

1. リポジトリのページで「Settings」タブをクリック
2. 左側メニューから「Pages」を選択
3. Source セクションで以下を選択：
   - Branch: `main`
   - Folder: `/ (root)`
4. 「Save」をクリック
5. 数分待つと、ページ上部に公開URLが表示されます
   - 例：`https://[ユーザー名].github.io/[リポジトリ名]/`

## 4. スマートフォンでのアクセス

1. 表示されたURLをコピー
2. iPhone 12のSafariまたはChromeでURLを開く
3. ホーム画面に追加（オプション）：
   - Safariの共有ボタンをタップ
   - 「ホーム画面に追加」を選択
   - アプリのように使用できます

## 5. 動作確認

- トップページが表示されること
- 呼吸器選択画面が正しく表示されること
- Servo_airを選択するとシナリオが開始されること
- 動画が正しく再生されること
- モバイルレイアウトが適切に表示されること

## トラブルシューティング

### 動画が再生されない場合

- ファイルサイズが大きすぎる可能性があります（GitHubは100MB制限）
- Git LFSを使用するか、動画を圧縮してください

### ページが表示されない場合

- GitHub Pagesの有効化後、反映に最大10分かかることがあります
- ブラウザのキャッシュをクリアしてみてください

### モバイルでレイアウトが崩れる場合

- ブラウザの開発者ツールでモバイルビューを確認
- `index.html`のメディアクエリを確認

## 更新方法

ファイルを更新する場合：

1. GitHub上でファイルを直接編集、または
2. ローカルで編集後、再度 `git add`、`git commit`、`git push`

GitHub Pagesは自動的に更新されます（数分かかる場合があります）。

## セキュリティとプライバシー

- 本アプリケーションはLocalStorageを使用して学習履歴を保存します
- データは全てユーザーのブラウザ内に保存され、外部に送信されません
- 個人情報や患者情報は入力しないでください

## サポート

問題が発生した場合は、GitHubのIssuesタブで報告してください。

