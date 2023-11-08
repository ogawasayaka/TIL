## 非同期処理（Promise）
コードが書かれた順番外で処理が行われる。逆は、同期処理（コードが読まれた順番に処理が反映）
コールバック関数などが非同期処理。例）特定の時間が経ったら処理されるなど

### awit/async
- thenメソッドを使う必要なくシンプルに記載できる。
    >awaitは何をするのか
    awaitを指定した関数のPromiseの結果が返されるまで、async function内の処理を一時停止する。
結果が返されたらasync function内の処理を再開する。
awaitはasync function内でないと利用できないため、async/awaitの利用例を見ていく。

>async/awaitの利用例
>以下は単純なasync/awaitの利用例。
```
function sampleResolve(value) {
    return new Promise(resolve => {
        setTimeout(() => {
            resolve(value * 2);
        }, 2000);
    })
}

/**
 * sampleResolve()をawaitしているため、Promiseの結果が返されるまで処理が一時停止される
 * 今回の場合、2秒後にresolve(10)が返ってきてその後の処理（return result + 5;）が再開される
 * resultにはresolveされた10が格納されているため、result + 5 = 15がreturnされる
 */
async function sample() {
    const result = await sampleResolve(5);
    return result + 5;
}

sample().then(result => {
    console.log(result); // => 15
});
```
>上記の処理をPromiseの構文で書くと以下のようになる。
```
function sampleResolve(value) {
    return new Promise(resolve => {
        setTimeout(() => {
            resolve(value * 2);
        }, 2000);
    })
}

function sample() {
    return sampleResolve(5).then(result => {
        return result + 5;
    });
}

sample().then(result => {
    console.log(result); // => 15
});
```
>2つを見比べてみると、async/awaitの方が簡潔に書けることがわかる。

引用　https://qiita.com/soarflat/items/1a9613e023200bbebcb3#await%E3%81%A8%E3%81%AF
