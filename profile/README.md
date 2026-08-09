# RumiCar group

**自動運転アルゴリズムを開発するプラットフォーム / A platform to develop autonomous driving algorithms**

[Website](https://www.rumicar.com/) ・ [シミュレータ / Simulator](https://www.rumicar.com/simulator/) ・ [YouTube](https://www.youtube.com/channel/UCVg3CBSVBcc_00FdC6q2wDg/featured) ・ [connpass](https://rumicar.connpass.com/) ・ [Facebook](https://www.facebook.com/groups/rumicar) ・ [X](https://x.com/RumikaChiba)

---

## 日本語

### RumiCar とは

RumiCar は、**誰もが自動運転のプログラムを作れる環境**を提供することを目指すオープンな開発プラットフォームです。手のひらサイズの実車（RumiCar 車体）と、ブラウザ上のシミュレータの両方で、同じ考え方の自動運転アルゴリズムを開発できます。

プラットフォームは 3 本柱で構成されています。

| 柱 | 内容 |
|---|---|
| **ソフトウェア** | 開発環境、RumiCar ライブラリ、サンプルプログラム、シミュレータ |
| **ハードウェア** | 自動走行車（車体）、回路基板、コンピュータモジュール（CM） |
| **サービス** | ハンズオン、展示会、走行会、オンラインセミナー |

### まず試してみる

**実機がなくても始められます。** ブラウザで動く [RumiCar Simulator](https://www.rumicar.com/simulator/) で、走行プログラムを書いて挙動を確認できます。ここで書いた Arduino C++ のプログラムは、そのまま実機の RumiCar でも動作します。

実機をお持ちの方は、Arduino IDE だけでライブラリを導入できます。

1. Arduino IDE のメニューから **スケッチ → ライブラリをインクルード → ライブラリを管理…** を開く
2. 検索ボックスに `RumiCar` と入力
3. 表示された **RumiCar** を選び **インストール** をクリック
4. 依存ライブラリ（VL53L0X）の確認が出たら **Install all** を選択

### リポジトリ

<!-- AUTO-REPOS-JA:START -->
<!-- この表は自動生成です。手で編集しないでください(毎日、公開リポジトリ一覧から再生成されます)。
     説明文・表示順の変更は .github リポジトリの profile/repos-meta.json を編集してください。
     This table is auto-generated daily from the org's public repositories.
     Edit profile/repos-meta.json in the .github repository to change descriptions/order. -->
| リポジトリ | 内容 | ★ |
|---|---|---|
| [**RumiCar**](https://github.com/RumiCar-group/RumiCar) | 本体。サンプルプログラム、ハンズオン教材(PDF)、結線図、開発資料、シミュレータ用プログラム/コース | 35 |
| [**RumiCar-lib**](https://github.com/RumiCar-group/RumiCar-lib) | Arduino用RumiCarライブラリ(Arduino Library Manager登録済み) | - |
| [**RumiCar-Simulator**](https://github.com/RumiCar-group/RumiCar-Simulator) | ブラウザで動く自動運転シミュレータ(インストール不要・実機互換) | - |
| [**RumiCar-PhotoStrip**](https://github.com/RumiCar-group/RumiCar-PhotoStrip) | 通信量にやさしい写真ストリップ(どのサイトでも使える汎用Web部品・MIT) | - |
| [**RumiCarRos**](https://github.com/RumiCar-group/RumiCarRos) | ROS 2対応の実装 | 3 |
| [**RumiCarEX**](https://github.com/RumiCar-group/RumiCarEX) | 関連プロジェクトのfork(派生車体) | - |
| [**micro-airc**](https://github.com/RumiCar-group/micro-airc) | 関連プロジェクトのfork(AI RCカー) | 1 |
| [**rumicar-duck**](https://github.com/RumiCar-group/rumicar-duck) | 関連プロジェクトのfork(アヒル型走行車) | - |
<!-- AUTO-REPOS-JA:END -->

### ハードウェア構成

RumiCar 車体は、車体前部に **3 基のレーザー測距（ToF）モジュール**（左・中央・右）を搭載し、その測定値をコンピュータモジュール（CM）が処理して、ステアリングと走行モータを制御します。CM は USB ケーブルで PC に接続してプログラムを書き込みます。

CM は用途に応じて複数の選択肢があります。

| CM | 言語 | 主な用途 |
|---|---|---|
| **Arduino Nano** | C++ | 基本構成。これから始める方向け |
| **ESP32** | C++ | Wi-Fi / Bluetooth・BLE 連携、ニューラルネットワーク等（上級者向け） |
| **Raspberry Pi Zero W** | Python | 画像認識・AI 等（上級者向け） |
| **Obniz** | — | ピンアサイン表に対応表を掲載 |

結線図・ピンアサイン表・「RumiCar の作り方」「RumiCar の動作確認方法」は、[RumiCar リポジトリの開発用資料フォルダ](https://github.com/RumiCar-group/RumiCar)にあります。自作される場合は、プログラムの互換性確保のため、ピンアサイン表に従って結線してください。

### 学習の流れ（ハンズオン）

サンプルプログラムは、段階的に自律走行へ進める構成になっています。

- **Exercise 1 — 距離を測ってみよう**：中央センサでの測距、3 センサ同時測距、シリアルプロッタでのグラフ表示
- **Exercise 2 — モータ制御**：ハンドルを切る、速度制御、前進と後進、ジグザグ走行
- **Exercise 3 — 自律走行基礎**：障害物を検知して安全に停止する車、左右の壁を見ながら市街地を走る車

ハンズオン用テキスト（PDF）と、教育機関向けの追加課題も公開しています。授業・演習での利用を歓迎します。

### 参加する

RumiCar は有志で開発しています。**一緒に RumiCar したい方・企業を募集しています。**

- ソフトウェア（自動運転アルゴリズム、IDE、画像認識、Autoware 導入）
- ハードウェア（車体開発・量産、CM 開発、PCB 設計）
- Website 編集・管理（WordPress）、技術アドバイザー
- 広報（YouTube 動画編集、イベント告知）、イベント運営、資金調達

貢献可能な分野とモチベーションを添えて **info@RumiCar.com** までご連絡ください。各国での開発・教室・トレーニング・カンファレンス開催も計画しており、各国拠点でご協力いただける方を探しています。

シミュレータ用の走行プログラムとコースは、プルリクエスト方式で投稿でき、投稿されたものは「みんなの投稿」から誰でも再利用できます。

---

## English

### What is RumiCar?

RumiCar is an open development platform with a single goal: **to let anyone in the world write autonomous driving programs.** You can develop the same algorithms on a palm-sized real vehicle and in a browser-based simulator.

The platform stands on three pillars: **software** (development environment, library, sample programs, simulator), **hardware** (the vehicle, circuit boards, computer modules), and **service** (hands-on workshops, exhibitions, driving events, online seminars).

### Getting started

**No hardware required to begin.** Write and test driving programs in the [RumiCar Simulator](https://www.rumicar.com/simulator/) — Arduino C++ programs written there run unmodified on a real RumiCar.

If you have a vehicle, install the library entirely from within the Arduino IDE:

1. Open **Sketch → Include Library → Manage Libraries…**
2. Search for `RumiCar`
3. Click **Install** on the RumiCar entry
4. When prompted for the dependency (VL53L0X), choose **Install all**

### Repositories

<!-- AUTO-REPOS-EN:START -->
<!-- この表は自動生成です。手で編集しないでください(毎日、公開リポジトリ一覧から再生成されます)。
     説明文・表示順の変更は .github リポジトリの profile/repos-meta.json を編集してください。
     This table is auto-generated daily from the org's public repositories.
     Edit profile/repos-meta.json in the .github repository to change descriptions/order. -->
| Repository | Description | ★ |
|---|---|---|
| [**RumiCar**](https://github.com/RumiCar-group/RumiCar) | Main repository: sample programs, hands-on textbooks (PDF), wiring diagrams, build docs, simulator programs and courses | 35 |
| [**RumiCar-lib**](https://github.com/RumiCar-group/RumiCar-lib) | Arduino library for RumiCar (published to the Arduino Library Manager) | - |
| [**RumiCar-Simulator**](https://github.com/RumiCar-group/RumiCar-Simulator) | Browser-based autonomous-driving simulator (no install, real-car compatible) | - |
| [**RumiCar-PhotoStrip**](https://github.com/RumiCar-group/RumiCar-PhotoStrip) | Bandwidth-friendly photo strip for any website (generic web component, MIT) | - |
| [**RumiCarRos**](https://github.com/RumiCar-group/RumiCarRos) | ROS 2 support for RumiCar | 3 |
| [**RumiCarEX**](https://github.com/RumiCar-group/RumiCarEX) | Fork of a related project (derived vehicle) | - |
| [**micro-airc**](https://github.com/RumiCar-group/micro-airc) | Fork of a related project (AI RC car) | 1 |
| [**rumicar-duck**](https://github.com/RumiCar-group/rumicar-duck) | Fork of a related project (duck-style car) | - |
<!-- AUTO-REPOS-EN:END -->

### Hardware

The vehicle carries **three laser time-of-flight distance sensors** (left, centre, right) at the front. A computer module (CM) reads them and drives the steering and drive motors. The CM connects to your PC over USB for programming.

Supported computer modules: **Arduino Nano** (C++, the standard starting point), **ESP32** (C++, Wi-Fi / Bluetooth / BLE, neural networks), **Raspberry Pi Zero W** (Python, image recognition and AI), and **Obniz**. Wiring diagrams, the pin assignment table, and the build and verification guides are in the RumiCar repository. If you build your own CM, follow the pin assignment table so programs stay compatible.

### Learning path

- **Exercise 1 — Measuring distance**: single sensor, all three sensors, plotting with the Serial Plotter
- **Exercise 2 — Motor control**: steering, speed control, forward and reverse, zig-zag driving
- **Exercise 3 — Autonomous driving basics**: stopping safely for obstacles, driving through a mock town

Hands-on textbooks (PDF) and additional exercises for educational institutions are published in the main repository. Classroom use is welcome.

### Get involved

RumiCar is built by volunteers, and we are looking for people and companies to join us — in algorithms, hardware, PCB design, website maintenance, technical mentoring, video editing, event organising, and fundraising. We are planning development, classes, training, and conferences in other countries, and we are looking for local partners.

Send your areas of interest and motivation to **info@RumiCar.com**.

Simulator programs and courses can be contributed by pull request, and contributed entries become reusable by everyone from within the simulator.

---

## ライセンス / License

主要リポジトリは **MIT License** で公開しています。各リポジトリの `LICENSE` を参照してください。
Core repositories are released under the **MIT License**. See the `LICENSE` file in each repository.

## お問い合わせ / Contact

**info@RumiCar.com**
