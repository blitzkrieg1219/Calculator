# 計算機プログラム
## プログラムの概要
コマンドラインから引数を受け取って四則演算を行うJavaプログラムです。
受け取る引数は以下の通り。

| 引数 | 引数の概要 | 例 |
|---|---|---|
| 第一引数 | 計算する値 | 10 |
| 第二引数 | 加算（+）、減算（-）、乗算（*）、除算（/）の4つの演算子 | + |
| 第三引数 | 計算する値 | 5 |

### 実行例
```bash
java Calculator 10 + 5
# 結果: 15.0

java Calculator 10 / 0
# エラー: ゼロで割ることはできません
```

### 機能
- 加算（+）、減算（-）、乗算（*）、除算（/）の4つの演算
- コマンドライン引数での入力
- エラーハンドリング（ゼロ除算、無効な入力など）

## フォルダ構成

```
demo/
├── src/                    # 元のJavaファイル
│   ├── Calculator.java     # メインクラス
│   ├── InputValidator.java # 入力検証クラス
│   └── CalculationService.java # 計算サービスクラス
├── modified/               # 修正版Javaファイル（課題用）
│   ├── Calculator.java     # 修正版メインクラス
│   ├── InputValidator.java # 修正版入力検証クラス
│   └── CalculationService.java # 修正版計算サービスクラス
├── docs/                   # ドキュメント
│   └── ISSUE.md           # 改善課題
├── lib/                    # 依存関係
└── README.md              # このファイル
```

## VSCodeでの起動方法

### 1. launch.jsonの作成
1. プロジェクト直下に.vscodeディレクトリを作成します。
2. 作成した.vscodeディレクトリに、docsディレクトリの中にあるlaunch.jsonを配置してください。

### 3. launch.jsonを使った実行方法

#### 基本的な実行手順
1. ctrl + shift + d、もしくはサイドバーから「実行とデバッグ」をクリックします。
2. 「実行とデバッグ」の上部にあるドロップダウンから実行したい設定を選択します。
3. ドロップダウン横のボタンをクリックすると実行します。

#### 利用可能な実行設定
- **Calculator - 基本実行**: `10 + 5` の計算
- **Calculator - 減算テスト**: `20 - 8` の計算
- **Calculator - 乗算テスト**: `6 * 7` の計算
- **Calculator - 除算テスト**: `15 / 3` の計算
- **Calculator - エラーテスト（ゼロ除算）**: `10 / 0` のエラー確認
- **Calculator - エラーテスト（無効な数値）**: `abc + 5` のエラー確認
- **Calculator - エラーテスト（無効な演算子）**: `10 % 5` のエラー確認
- **Calculator - 引数不足テスト**: `10` のみの引数不足エラー確認

#### 引数を変えたい場合
1. `launch.json` ファイルを開きます。
2. 各設定の `"args"` 配列を編集してください

```
    "configurations": [
        {
            "type": "java",
            "name": "Calculator - 基本実行",
            "request": "launch",
            "mainClass": "Calculator",
            "classPaths": ["${workspaceFolder}/src"],
            "modulePaths": [],
            "args": ["10", "+", "5"],　←ここの値を修正する
            "console": "integratedTerminal",
            "cwd": "${workspaceFolder}"
        },
```
3. 保存後、編集した実行設定（上記の例だと「基本実行」）を選択して実行します。
