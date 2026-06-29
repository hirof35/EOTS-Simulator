# AN/AAQ-40 EOTS Tactical Simulator

F-35戦闘機に搭載されている先進的な電子光学照準システム**「AN/AAQ-40 EOTS (Electro-Optical Targeting System)」**のコア機能を再現した、Pythonベースの簡易タクティカルシミュレーターです。

ステルス性を維持しつつ、前方赤外線（FLIR）による熱源探知、ターゲット自動追尾（ロックオン）、レーザー測距・指定を行う戦闘機パイロットの視界を体験できます。
<img width="1122" height="847" alt="スクリーンショット 2026-06-30 073139" src="https://github.com/user-attachments/assets/2f42fa2e-03c8-472a-a35b-391fb4e91fa4" />
---

## 🚀 主な機能

*   **FLIR（前方赤外線ビジョン）モード切替**: 熱源を白く表現する「WHITE HOT (WHOT)」と、黒く表現する「BLACK HOT (BHOT)」のシミュレート。
*   **オートトラック（LOCK-ON機能）**: 視界内のターゲットを選択・固定すると、EOTSのジンバルが目標の移動に合わせて自動追従。
*   **レーザー指定（LASER DESIGNATOR）**: レーザー照射による正確な目標距離（RNG）の測定。
*   **光学ズーム（FOV調整）**: 視野角（Field of View）を絞ることで、遠距離のターゲットを拡大。

---

## 🛠 動作環境・必要ライブラリ

*   Python 3.10 以上（推奨）
*   以下の外部ライブラリが必要です。

```bash
pip install numpy opencv-python pillow
💻 実行方法
リポジトリ（またはフォルダ）内で以下のコマンドを実行してください。

Bash
python EOTSSimulator.py
🎮 操作方法・画面の見方
⚙️ コントロールパネル（右側）
FLIR ボタン: 赤外線映像のカラー（WHOT / BHOT）を切り替えます。

OPTICAL ZOOM (FOV) スライダー: 視野角を変更します。数値を小さくするほどズーム（拡大）になります。

GIMBAL CONTROL:

▲ ELEV+ / ▼ ELEV-: センサーの上下角（仰俯角）を手動調整。

◀ AZIM- / AZIM+ ▶: センサーの左右角（方位角）を手動調整。

LOCK: 自動追尾モードのON/OFF。ターゲットが視界内にいる状態で押すと追尾を開始します。

LSR DESG ボタン: レーザーの照射ON/OFF。

📊 センサーディスプレイ（左側 / HUD）
中央のクロスヘア（照準）: センサーの中心軸です。

AZ / EL: 現在のセンサーが向いている方位角（Azimuth）と仰俯角（Elevation）。

RNG: 目標までの距離（※実機を模しているため、レーザーONまたはロックオン時のみ測定値が表示されます）。
