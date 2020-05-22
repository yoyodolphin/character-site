<template>
  <div class="Commission">
    <h2>コミッションインフォ</h2>
    <div class=com-summary>
      <p>こちらのページではコミッションの受付を行っています。<br>
         詳細をご確認いただきページ下部のフォームからご連絡お願いいたします。</p>
    </div>
    <h2>コミッションの流れ</h2>
    <div class="com-info">
      <p>コミッションのやり取りは以下のようになります。</p>
      <div class="com-flow">
        <div class="com-column">
          <p class="column">1.希望するイラストの内容の決定</p>
          <p>イラストの内容を決めてページ下部のフォームより送信してください。</p>
        </div>
        <div class="com-column">
          <p class="column">2.内容を基に見積もり、下書きの作成</p>
          <p>いただいた内容、オプションを下記の価格表を基にお見積させていただき、合意をいただき次第下書きの作成に取り掛かります。</p>
        </div>
        <div class="com-column">
          <p class="column">3.下書きのご確認、修正</p>
          <p>下書きが完了後、ご確認いただきます。修正箇所があれば受け付けます。</p>
        </div>
        <div class="com-column">
          <p class="column">4.料金のお支払い</p>
          <p>下書きの内容にご納得いただいた後に料金のお支払いをお願いいたします。希望した振込先を提示いたします。</p>
        </div>
        <div class="com-column">
          <p class="column">5.本制作の取り掛かり</p>
          <p>料金のご入金が確認できた後に本制作に取り掛からせていただきます。</p>
        </div>
        <div class="com-column">
          <p class="column">6.完成品のご確認、最終修正</p>
          <p>本制作が完了後低画質版の作品をご確認いただきます。微調整等の修正があれば受け付けます。</p>
        </div>
        <div class="com-column">
          <p class="column">7.完成品のお渡し</p>
          <p>完成品の内容にご納得いただける場合は、高画質版をお渡しして一連の流れは終了となります。</p>
        </div>
      </div>
    </div>
    <h2>オーダー詳細</h2>
    <div class="com-sheet">
      <p class="order-title">料金表</p>
      <div class="com-price">
        <div class="price-column">
          <p>・シンプルイラスト ¥<strong>2000</strong></p>
          <img src="../assets/commission-ex.png">
          <p>線画に着色のみのイラストです。</p>
        </div>
        <div class="price-column">
          <p>・フルカラーイラスト ¥<strong>4000</strong></p>
          <img src="../assets/commission-ex2.png">
          <p>シンプルイラストに光沢、影、シンプルな背景を追加したイラストです。</p>
        </div>
        <div class="price-column">
          <p>・SNSアイコン ¥<strong>1500</strong></p>
          <img src="../assets/commission-exsns.png">
          <p>フルカラーイラストのバストアップ版です。</p>
        </div>
      </div>
      <div class="price-option">
        <p class="order-title">オプション</p>
        <table>
          <tr>
            <td width="60%">キャラ追加</td>
            <td>一体につき+¥<strong>1000</strong></td>
          </tr>
          <tr>
            <td>R-18</td>
            <td>+¥<strong>1500</strong></td>
          </tr>
          <tr>
            <td>差分</td>
            <td>一枚につき+¥<strong>500</strong></td>
          </tr>
        </table>
        <p class="order-title">支払い方法</p>
        <div class="price-pay">
          <p>・ゆうちょ銀行</p>
          <p>・paypal</p>
        </div>
      </div>
    </div>
    <h2>依頼フォーム</h2>
    <div class="com-form">
      <p>現在は受付を行なっておりません。<br>再開時期などはtwitterをご確認お願いいたします。</p>
    </div>
  </div>
</template>

<style scoped lang="scss">
p {
  margin: 0;
  text-align: left;
}

@media screen and (max-width: 767px) {
h2 {
  margin: 30px 5vw;
  text-align: left;
  border-left: 6px solid;
  border-bottom: 2px solid;
}

.com-summary {
  width: 90%;
  margin: 0 5vw 50px 5vw;
}

.com-info {
  width: 90%;
  margin: 0 auto 30px auto;
  > .com-flow {
    > .com-column {
      border: 1px solid;
      padding: 5px;
      margin: 20px 0;
      > .column {
        border-bottom: 1px dotted;
        margin-bottom: 10px;
        font-weight: bold;
        font-size: 13pt;
      }
    }
  }
}

.order-title {
  font-weight: bold;
  font-size: 20pt;
}
.com-sheet {
  width: 90%;
  margin: 0 auto;
  > .com-price {
    margin-bottom: 50px;
    > .price-column {
      margin: 10px 0 30px 0;
      img {
        width: 85%;
        border: solid 2px;
      }
    }
  }
  > .price-option {
    table {
      width: 100%;
      height: 150px;
      margin: 20px 0 50px 0;
    }
    tr {
      text-align: left;
      border-bottom: solid 1px;
    }
    > .price-pay {
      margin: 20px 0 50px 0;
    }
  }
}

.com-form {
  width: 90%;
  margin: 30px auto;
}
}

@media screen and (min-width: 768px) {
.Commission {
  width: 90vw;
  max-width: 900px;
  margin: 0 auto;
}

h2 {
  margin: 30px 5%;
  text-align: left;
  border-left: 6px solid;
  border-bottom: 2px solid;
}

.com-summary {
  width: 90%;
  margin: 0 5vw 50px 5vw;
}

.com-info {
  width: 90%;
  margin: 0 auto 30px auto;
  > .com-flow {
    margin-bottom: 80px;
    > .com-column {
      border: 1px solid;
      padding: 5px;
      margin: 20px 0;
      > .column {
        border-bottom: 1px dotted;
        margin-bottom: 10px;
        font-weight: bold;
        font-size: 13pt;
      }
    }
  }
}

.order-title {
  font-weight: bold;
  font-size: 20pt;
}
.com-sheet {
  width: 90%;
  margin: 0 auto;
  > .com-price {
    margin: 30px 0 50px 0;
    display: flex;
    justify-content: space-between;
    > .price-column {
      width: 33%;
      margin: 10px 0 30px 0;
      img {
        width: 85%;
        border: solid 2px;
      }
    }
  }
  > .price-option {
    table {
      height: 150px;
      margin: 20px 0 50px 0;
    }
    tr {
      text-align: left;
      border-bottom: solid 1px;
    }
    > .price-pay {
      margin: 20px 0 50px 0;
    }
  }
}

.com-form {
  width: 90%;
  margin: 30px auto;
}
}

</style>
