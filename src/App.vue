<template>
    <div>{{ greet }} {{ name }}</div>
    <div v-text="channel" ></div>
    <div v-text="name"></div>
    <div v-html="bind" ></div>
    <div v-html="hack"></div>
    <h2 v-bind:id="headingId">Heading</h2>
    <h2 class="underline">Underline text</h2>
    <h2 v-bind:class="status">Status</h2>
    <h2 v-bind:class="isPromoted && 'prometed'">Promoted movie</h2>
    <h2 v-bind:calss="isSoldout ? 'sold-out' : 'new' ">Soldout? Movie</h2>
    <h2 v-bind:style="{
        color:highlightColor
    }">Inline Style</h2>

    <h2
    v-bind:style="{
      color: highlightColor,
      fontSize: headerSize + 'px',
      padding: '20px',
    }"
  >
    Inline Style
  </h2>

  <h2 v-bind:style="headerStyleObject">Style Obejct </h2>
  <div v-bind:style="[baseStyleObject, successStyleObject]">Success Style</div>
  <div v-bind:style="[baseStyleObject, dangerStyleObject]">Danger Style</div>

  <!-- Conditional Rendering -->
  <h1 v-if="num === 0">The number is zero</h1>
  <h2 v-else-if="num < 0">The number is negative</h2>
  <h2 v-else-if="num > 0">The number is positive</h2>
  <h2 v-else>Not a number</h2>

    <template v-if="showElement">
    <h2>Bijit</h2>
    <h2>Codevolution 1</h2>
    <h2>Vue 3 2</h2>
  </template>

</template>

<script>


export default {
    name: 'App',
    data() {
       return { 
        greet: "Hello",
        name: "Authlab",
        channel: 'Code',
        bind: "<b>Hello world</b>",
        hack: `<a href="#" onClick="alert('You have been hacked')">Win a prize</a>`,
        headingId: 'heading',
        status: "danger",
        isPromoted: true,
        isSoldout: false,
        highlightColor: 'orange',
        headerSize: 50,
        headerStyleObject: {
        color: 'orange',
        fontSize: '50px',
        padding: '20px',
      },
        baseStyleObject: {
        fontSize: '50px',
        padding: '10px',
      },
      successStyleObject: {
        color: 'green',
        backgroundColor: 'lightgreen',
        border: '1px solid green',
      },
      dangerStyleObject: {
        color: 'darkred',
        backgroundColor: 'red',
        border: '1px solid darkred',
      },
      num: 5,
      showElement: true,
    };
    },

}
</script>

<style>
#app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    
    margin-top: 60px;
}

.underline{
    text-decoration: underline;
}

.prometed{
    font-style: italic;
}

.new{
    color: green;
}

.sold-out{
    color: red;

}
</style>
