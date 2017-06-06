class: center, middle

# Start Vue.js <br/>v1.0


[at port_mokumoku #10](http://freestyle-mokumoku.connpass.com/event/21612/)

---


# だれ?


.col-xs-6[
## Pocke
A web engineer.

- GitHub: [`@pocke`](https://github.com/pocke)
- Twitter [`@p_ck_`](https://twitter.com/p_ck_)
]

.col-xs-6[

.pocke-img[
![pocke](pocke.svg)
]

]



---


# だれ?

### おしごと

.center[


[![skyhopper](skyhopper.png)](https://github.com/skyarch-networks/skyhopper)

.sideci-img[
[![sideci](sideci.png)](https://www.sideci.com)
]

]


---

# アジェンダ

- Vue.js について知ってもらう!
- つかいたい!と思ってもらう!

---


# Vue.js ってなに?

- Reactive Components for Modern Web Interfaces
- いわゆる最近のフロントエンドJSフレームワーク!(だと思う)
  - ReactとかAngularとか…


---


# たとえば、input の内容をリアルタイムで表示

<div id="vue-1">
  <input type="text" v-model="name">
  <div>My name is {{name}}</div>
</div>


.col-xs-6[
```html
<div id="vue-1">
  <input type="text" v-model="name">
  <div>My name is {{name}}</div>
</div>
```
]

.col-xs-6[
```javascript
new Vue({
  el: '#vue-1',
  data: {
    name: "pocke",
  },
});
```
]

---


# たとえば、TODOリスト

<div id="vue-2">
<ul>
  <li v-for="t in todos">
    <input type="text" v-model="t">
    <button @click="del(t)">x</button>
  </li>
</ul>
<button @click="add">+</button>
</div>

.col-xs-6[
```html
<div id="vue-2">
<ul>
  <li v-for="t in todos">
    <input type="text" v-model="t">
    <button @click="del(t)">x</button>
  </li>
</ul>
<button @click="add">+</button>
</div>
```
]

.col-xs-6[
```javascript
new Vue({
  el: '#vue-2',
  data: {
    todos: ['買い物', '洗濯'],
  },
  methods: {
    add: function(){
      this.todos.push("new TODO");},
    del: function(data){
      this.todos.$remove(data);},
  },
})
```
]

---

# たとえば、条件分岐

<div id="vue-3">
  素数発見くん<br>
  <input type="number" v-model="n">
  <div v-if="prime">{{n}}!!!!! 素数だ!!!! ｳｵｵｫｫｫｫｵｵｵｵｵ!!</div>
  <div v-else>{{n}}は素数じゃないよ</div>
</div>


.col-xs-6[
```html
<div id="vue-3">
  素数発見くん<br>
  <input type="number" v-model="n">
  <div v-if="prime">{{n}}!!!!! 素数だ!!!! ｳｵｵｫｫｫｫｵｵｵｵｵ!!</div>
  <div v-else>{{n}}は素数じゃないよ</div>
</div>
```
]

.col-xs-6[
```javascript
new Vue({
  el: '#vue-3',
  data: { n: 1 },
  computed: {
    prime: function () {
      if(this.n<2){return false};
      var m=Math.sqrt(this.n);
      for (var i=2;i<=m;i++){
        if (this.n%i===0){return false;}
      }
      return true;
    },
  }
})
```
]

---


<div id="vue-4">
  <div v-html="marked"></div>

  <textarea v-model="md" rows="5">
  </textarea>
</div>


.col-xs-6[
```html
<div id="vue-4">
  <div v-html="marked"></div>

  <textarea v-model="md" rows="5">
  </textarea>
</div>
```
]

.col-xs-6[
```javascript
new Vue({
  el: '#vue-4',
  data: {md: "# たとえば、マークダウンエディタ\n- このスライドもMarkdownで書かれています\n- Markdown最高!"},
  computed: {
    marked: function () {
      return marked(this.md);
    },
  }
})
```
]

---

# たとえば、フィボナッチ数列


- [fibo](http://me.pocke.me/fibo)

# たとえば、Vim戦闘力

- [Vim Scouter](http://me.pocke.me/vim_scouter_web/)


---

# 結局なにがいいの?

## 宣言的!

- jQueryでボタンが押されたらDOM作って挿入して…とかやりたくない

---

# 結局なにがいいの?

## シンプル!とっつきやすい!

- 覚えることが少ない
- 他のものと合わせやすい

---

# 結局なにがいいの?

## 日本語の情報が豊富!

- [公式ドキュメント](http://jp.vuejs.org/)
- [Qiita の vue.js タグ](http://qiita.com/tags/vue.js) 94件も投稿があるらしい!すごい!
- [Vue.js v1.0 へのアップデート | サバカン屋テックブログ](http://www.skyarch.net/blog/?p=4700)
