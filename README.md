# seat-chart-test2
# 座席管理システム ブロック図テスト

```mermaid
flowchart TD

subgraph A[座席データ管理: data.xlsx]
  A1[予約ステータス]
  A2[社員番号⇔氏名変換]
  A3[予約&解放ログ]
  A4[応援者リスト]
end

subgraph B[メインUI: 座席記録表.xlsm]
  B1[座席表シート]
  B2[UserForm1: 座席予約入力]
  B3[UserForm2: 座席解放入力]
  B4[UserForm3: 座席検索UI]
  B5[応援者登録UIシート]
end

subgraph C[主なVBA処理モジュール]
  C1[既存データ確認]
  C2[座席登録]
  C3[座席開放]
  C4[座席表更新]
  C5[座席検索]
  C6[座席を探す]
  C7[Help_Registration]
end

U[ユーザー操作] -->|座席予約| B2
U -->|座席解放| B3
U -->|最新化| C4
U -->|座席検索| B4
U -->|応援者登録| B5

B2 --> C2 --> A --> B1
B3 --> C3 --> A --> B1
C4 --> A --> B1
B4 --> C5 --> A
C5 --> C6 --> B1
B5 --> C7 --> A
