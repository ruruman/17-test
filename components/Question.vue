<template>
  <div class="wrapper">
    <h2>3-1 請說明 Flux, Redux, Vuex 之間的差異</h2>
    <ol>
      <li>Flux、Redux、Vuex均為單向數據流。</li>
      <li>Redux和Vuex是基於Flux的，Vuex 只能用於vue。</li>
      <li>Flux可以有多個Store ，Redux、Vuex全局僅有一個Store（單狀態樹）</li>
      <li>Redux、Vuex適用於大型項目的狀態管理。</li>
      <li>
        Redux中引入了中間件，主要解決異步帶來的副作用，可通過約定完成許多複雜工作。
      </li>
    </ol>
    <h2>3-2 請說明單向資料流與雙向資料流在處理資料更新上的異同</h2>
    <p>
      雙向綁定是指把畫面上的 DOM 與資料透過
      Vue實體來綁定。只要對方有更新，另一方也會更新。
      單向資料流是管理父子元件資料狀態的模式，資料只能由父元件傳列子元件，子元件透過
      props 來接收，但子元件不能直接修改 props 的方式，改變父元件傳來的資料。
      在子元件要改變父元件的資料，就要使用 emit 來實現。 如果
      props的資料是物件型別，並需要把它放到 data 裏使用的話，可以使用 v-bind
      自動解構賦值，或者是深拷貝方法 JSON.parse() 和 JSON.stringify 來處理。
    </p>
    <h2>3-3 這些設計主要想要解決什麼樣的問題? 優缺點為何？</h2>
    <p>單向資料流</p>
    優點：
    <ul>
      <li>
        元件資料傳遞只有唯一的入口和出口，使得程式更直觀、更容易理解，有利於程式的可維護性。
      </li>
    </ul>
    缺點：
    <ul>
      <li>在處理狀態較多的場景時較繁瑣。</li>
    </ul>
    <p>單向資料流</p>
    優點：
    <ul>
      <li>
        在操作表單時使用v-model方便簡單，可以省略繁瑣或重複的onChange事件去處理每個表單資料的變化
      </li>
    </ul>
    缺點：
    <ul>
      <li>改變一個狀態可能會改變到其他狀態，增加debug的難度。</li>
    </ul>
  </div>
</template>
<script>
export default {
  name: "Question",
};
</script>
