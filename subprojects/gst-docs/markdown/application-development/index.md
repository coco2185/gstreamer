---
title: GStreamerアプリケーション開発マニュアル
short-description: GStreamerを使ったアプリケーションの開発方法を解説します。
...

# GStreamerアプリケーション開発マニュアル

## はじめに

GStreamerは、ストリーミングメディアアプリケーションを作成するための非常に強力で多用途なフレームワークです。
GStreamerフレームワークの利点の多くは、そのモジュール性から生まれます。
GStreamerは、新しいプラグインモジュールをシームレスに組み込むことができます。
ただし、モジュール性とパワーは、多くの場合、複雑さの増大を伴い、新しいアプリケーションの作成が必ずしも簡単であるとは限りません。

このガイドは、GStreamerフレームワーク（バージョン0.10.21.1）を理解し、それに基づいてアプリケーションを開発できるようにすることを目的としています。
最初の章では、シンプルなオーディオプレーヤーの開発に焦点を当て、GStreamerの概念を理解できるように重点的に説明します。
後の章では、メディアの再生に関連するより高度なトピックだけでなく、メディア処理の他の形式（キャプチャ、編集など）についても説明します。

## イントロダクション

### このマニュアルを利用される方へ

この本は、アプリケーション開発者の観点からGStreamerについて解説したもので、GStreamerライブラリとツールを使用してGStreamerアプリケーションを作成する方法を説明しています。
プラグインの作成方法については、[プラグイン作成者ガイド](http://gstreamer.freedesktop.org/data/doc/gstreamer/head/pwg/html/index.html)を参照してください。
また、GStreamer Webサイト([http://gstreamer.freedesktop.org/documentation/](http://gstreamer.freedesktop.org/documentation/))にあるその他のドキュメントも確認してください。

### 事前知識として必要なこと

このマニュアルを理解するには、C言語の基礎知識が必要です。

GStreamerはGObjectプログラミングモデルに準拠しているため、このガイドではGObject([http://library.gnome.org/devel/gobject/stable/](http://library.gnome.org/devel/gobject/stable/))の基礎を理解していることを前提としています。
glib ([http://library.gnome.org/devel/glib/stable/](http://library.gnome.org/devel/glib/stable/))プログラミング。特に、

- GObjectインスタンス化
- GObjectプロパティ（設定/取得）
- GObjectキャスト
- GObjectの参照/逆参照
- 巧妙なメモリ管理
- glibシグナルとコールバック
- glibメインループ

について、理解が深いとGstreamerの理解も早いと考えられます。

### このマニュアルの構成

このガイドは、理解しやすいように、いくつかの大きなパートに分けられています。
各パートでは、GStreamerアプリケーション開発に関する特定の幅広いトピックを取り上げています。このガイドの各パートは、次の順序で配置されています。

[About GStreamer][about]
GStreamerの概要を説明します。設計原則と基礎です。

[Building an Application][app-building]
GStreamerアプリケーションプログラミングの基礎について説明します。このパートの最後には、GStreamerを使用して独自のオーディオプレーヤーを構築できるようになります。

[Advanced GStreamer concepts][advanced]
GStreamerを競合他社より優れたものにする高度なトピックに移ります。
動的パラメータとインターフェイスを使用したアプリケーションパイプラインの相互作用、スレッドとスレッドパイプライン、スケジュールとクロック（および同期）について説明します。
これらのトピックのほとんどは、APIを紹介するだけでなく、GStreamerを使用したアプリケーションプログラミングの問題を解決し、その概念を理解するためのより深い洞察を提供することを目的としています。

[Higher-level interfaces for GStreamer applications][highlevel]
GStreamerのより高レベルのプログラミングAPIについて説明します。
これを理解するには、前のパートの詳細をすべて理解する必要はありませんが、それでもGStreamerの基本的な概念を理解する必要があります。
特に、XML、プレイビン、およびオートプラガーについて説明します。

[Appendices][appendix]
GNOME、KDE、OS X、またはWindowsとのインテグレーションに関するいくつかのランダムな情報、デバッグのヘルプ、およびGStreamerプログラミングを改善および簡素化するための一般的なヒントが記載されています。

[about]: application-development/introduction/index.md
[app-building]: application-development/basics/index.md
[advanced]: application-development/advanced/index.md
[highlevel]: application-development/highlevel/index.md
[appendix]: application-development/appendix/index.md
