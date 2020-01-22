# akari-level2-vr2.github.io
本宮　レベル2課題（修正1・質問）

ご指摘いただいた点の修正内容

・「フォントがカンプ指定のものと異なる」

→お教えいただいたサルワカさんのサイトを参考に修正。

body {
    font-family: YuGothic,'Yu Gothic',sans-serif;
}

・「h1〜h3(見出しタグ)に抜けがある」
→ヘッダーロゴ「NAVI」にh1タグを挿入


・「320px〜1170pxで横スクロール(デバイスの幅に要素が収まっていない状態)が発生している」

ⅰ「ところどころでinnerの幅を飛び出てしまっている要素がある」

→「news-inner」のpaddingが画面幅を飛び出してしまっていたので、paddingを外し、その子要素である「.news-box」のwidthを90％にして、できた左右marginをautoで整えました。


    .news-inner{
        padding: 0%;
    }

    .news-box{
        flex-direction: column;
        width: 90%;
        margin-right: auto;
        margin-left: auto;
    }


ⅱ「ズレが解消できたら、768px(タブレットサイズ)〜1080px(innerの幅)でレイアウトが大きく崩れていないかどうかも要チェックです」

・header、about、footerなどで画面サイズを動かすとレイアウトが崩れていたので,max-widthを80％にして画面から飛び出て横スクロールが出ないようCSSを再コーディングしました。

例）header

header {
    max-width: 1080px;
    width: 80%;
    margin-right: 10%;
    margin-left: 10%;
    height: 70px;
    color:#333;
}


・「SERVICE、ABOUT、NEWSの見出し
PCサイズではOKですが、タブレット以下(767px)になると崩れが発生してしまっています。緑の横線見出しについては「flexbox」を使ったものなど、いくつかパターンがあるので、検索ワードを工夫しつつ最適な方法を見つけてみてください！」

（SERVICE、ABOUT、NEWSと緑の横線の親要素）

.topic-ttl {
    display: flex;
    justify-content: center;
    align-items: center;
}

 .t-ttl {
        font-size: 28px;
        margin:0  5%;
    }


★質問：どうしても解決・修正できなかった問題（1点）

→「ーSERVICEー」の部分が、タブレット以下のサイズで画面幅を動かすと、それに連動して「浮くように」上下に動いてしまうのはなぜか。（上のコンテンツである「資料請求はこちら」のボタンの上にかかってしまうイメージ）

また、他の類似した二つのコンテンツ（ABOUT、NEWS）も全く同じようにマークアップしたのに「ーSERVICEー」だけ浮くのはなぜか。


・自力で調べたこと：


・「要素　浮く　動く　配置」等でググり調べましたが、

1 要素を浮かして配置する「float」は使用していない。

2「position」も使用していない。念のためそれで配置できないか試したがうまくいかず。

3 「ーSERVICEー」周辺のコーディングでのミス（閉じタグミス、親要素・子要素でのミスなど）がないかあらゆることを検証しましたが、力及ばす自力で解明できませんでした。

この問題に丸1日費やしているので、申し訳ないですがこの問題の原因についてアドバイスいただけませんでしょうか。

お手数おかけしますが、よろしくお願いいたします。


