# seat-chart-test2
# 座席管理システム ブロック図テスト

```mermaid

flowchart TD

%% 列のグループ定義（縦に流れる）
subgraph L[ユーザー操作]
  U1[応援者登録]
  U2[座席一覧の確認]
  U3[座席予約]
  U4[予約済み座席の確認]
  U5[座席開放]
  U6[解放済みの確認]
end

subgraph M[VBAマクロ処理]
  V1[Help_Registration]
  V2[座席表更新]
  V3[既存データ確認]
  V4[座席登録]
  V5[座席検索]
  V6[座席を探す]
  V7[座席開放]
end

subgraph R["座席記録表_data.xlsx\n(座席DB)"]
  D1[list_Ouen に登録・更新]
  D2[座席データの読込 AM/PM]
  D3[座席予約データ書込]
  D4[検索用データ参照]
  D5[座席解放データ書込]
end

%% 縦方向の接続
U1 --> V1 --> D1
U2 --> V2 --> D2
U3 --> V3 --> V4 --> D3
U4 --> V5 --> V6 --> D4
U5 --> V3 --> V7 --> D5
U6 --> V2 --> D2
