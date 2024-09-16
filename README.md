# Titanic
URL: https://www.kaggle.com/competitions/spaceship-titanic/overview

## 課題
宇宙船タイタニック号が異常時空間と衝突した際に，<br>
乗客が別の次元に移動したかどうかを予測するモデルを構築する．

## データセット
### 概要
- 訓練データセット（train.csv）
- テストデータセット（test.csv）
### 説明変数
|変数名|定義|
|:----|:----
|PassengerId|- 各乗客の一意のID<br>- gggg_ppの形式で表記される<br>　-gggg：乗客が一緒に旅行しているグループ（家族であることが多いが、必ずしもそうとは限らない）<br>　-pp：グループ内の番号||
|HomePlanet|乗客が出発した惑星、通常は永住地の惑星||
|CryoSleep|- 乗客が航海中に可視状態になることを選択したかどうか<br>- 冷凍睡眠中の乗客は客室に閉じ込められている||
|Cabin|- 乗客が滞在しているキャビン番号<br>- deck/num/sideの形式を取る<br>　- sideはPort（船頭から見て右）を表す'P'、または、Starboard（船頭から見て左）を表す'S'のいずれか||
|Destination|降りる惑星||
|Age|乗客の年齢||
|VIP|乗客が公開中に特別VIPサービスの料金を支払ったかどうか||
|Name|乗客の名前||
|RoomService, FoodCourt, ShoppingMall, Spa, VRDeck|宇宙船タイタニック号の多くの豪華な設備のそれぞれで乗客が請求された金額||
|Transported|乗客が別の次元に移動したかどうか||
### 評価指標
$$Accuracy=\text{Accuracy} = \frac{\text{correct classifications}}{\text{total classifications}} = \frac{TP + TN}{TP + TN + FP + FN}
$$
## 提出ログ
|日付|精度|モデル|メモ（工夫した点）|
|:---|:---|:---|:---|:---|
|2024/09/15|0.7993099482461185|LightGBM|なし（ベースライン）|
|2024/09/15|0.8056354226566993|LightGBM|ベースライン + Optuna|
## アイデア
- PassengerIdの'gggg'で「グループ」を意味するカラムの作成
- PassengerIdの'pp'の他のカラムとの関係性の分析
    - ageと関係はあるか（家族と判定できるような情報を持つか？）
    - Cabinとの関係で近くで泊まっているか？（近いと運命を共にする的な）
- 年齢のビンニング（年齢層でTransportedに傾向はないか？）
- RoomService単体や合計金額とTransportedの関係
- Cabinのグルーピング
    - sideは2値
    - deckとnumは？
- HomePlanet、CryoSleep、Destination、VIPの真理値のAND/ORの値とTransportedとの関係性
- Last Nameを用いて、Groupが家族かどうか判定

## TODO
- Discussionを基に
    - 特徴量エンジニアリング
        - 欠損値の処理
    - モデルの修正・変更
