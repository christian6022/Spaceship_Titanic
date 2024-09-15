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
|変数名|定義|Key|
|:----|:----|:----|
|PassengerId|- 各乗客の一意のID<br>- gggg_ppの形式で表記される<br>　-gggg：乗客が一緒に旅行しているグループ（家族であることが多いが、必ずしもそうとは限らない）<br>　-pp：グループ内の番号|0:No, 1:Yes|
|HomePlanet|乗客が出発した惑星、通常は永住地の惑星| 1:1st, 2:2nd, 3:3rd|
|CryoSleep|- 乗客が航海中に可視状態になることを選択したかどうか<br>- 冷凍睡眠中の乗客は客室に閉じ込められている||
|Cabin|- 乗客が滞在しているキャビン番号<br>- deck/num/sideの形式を取る<br>　- sideはPortを表す'P'、または、Starboardを表す'S'のいずれか||
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
|日付|精度|モデル|パラメータ|工夫した点|
|:---|:---|:---|:---|:---|
|2024/09/15||||なし（ベースライン）|

## アイデア
