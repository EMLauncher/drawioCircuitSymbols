# drawioCircuitSymbols
circuit symbols for Diagram.drawio

### 導入の仕方
1. Diagram.drawioアプリをインストールする
1. File -> Open Library... から、SuzukiCircuitSymbols.xml を読み込む
以上！

----xml書ける人向け----
### シンボル追加の手順
シンボルは自分で適当に描いたものだとスナップできなかったり、回転できなかったりと使い勝手が非常に悪い
xmlを書くことで使いやすいシンボルを作れる

1. シンボルを表すxml文を書く
※独自仕様のため、検索したりすでにあるものからフォーマットを読む必要あり
公式サイト↓
https://www.diagrams.net/doc/faq/shape-complex-create-edit
基本的には以下のような感じ
```
<shape 図形の名前、サイズ可変/不可変などを設定>
  <connections>
    スナップしてほしいポイントを設定
    ここだけx,yはサイズに対する割合なので注意
  </connections>
  <background>
    背景の塗りつぶしなどを記載
    回路図記号で使う場面は少ないと思う
  </background>
  <foreground>
    各種図形を描写
　　円は<ellipse 座標/>、など
  </foreground>
</shape>
```
ちなみ円弧を描くのが結構めんどくさいので注意↓
https://qastack.jp/webapps/70519/how-do-i-add-a-curve-or-arc-to-a-diagram-on-draw-io

1. アプリにて、 Arrange -> Insert -> shape... から、xmlから図形を生成するウィンドウが開く
1. previewで思い通りの図形か確認して、Apply
1. 図形が出てくるので、好きなサイズに変更して、ライブラリにドラッグ&ドロップ
1. 追加されたら、edit(鉛筆みたいなアイコン)をクリックして名前を付けるとよい
1. exportで出力(saveではない)、この際上書き保存ではなく、別の場所に出力すること(なんかバグでフリーズする)
1. 出力した SuzukiCircuitSymbols.xml を古い方があるフォルダに移動して上書き

自分は電源等はw=40,h=40 抵抗などはw=40,h=80 トランジスタとかはw=80,h=80のサイズで統一
スナップは一部を除き25%刻みのキリのいい場所にしか置かないようにしている
