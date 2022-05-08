<template>
<div class="container container-box">
        <img :src="item.poster" alt="item.author">
        <h4>{{item.title}}</h4>
        <p>{{item.author}}</p>
        <span>{{item.year}}</span>
</div>

         <!-- author: "Bon Jovi"
        genre: "Rock"
        poster: "https://www.onstageweb.com/wp-content/uploads/2018/09/bon-jovi-new-jersey.jpg"
        title: "New Jersey"
        year: "1988" -->
    
</template>

<script>

export default {
  name: 'AppCard',
  props: {
    item: Object,
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss">
@import '../style/variables.scss';

.box {
    background-color: $bgCard;
    text-align: center;
    padding: 15px 0;
    color: $textWhite;
    font-size: 10px;
    h4 {
        margin-top: 15px;
        font-size: 14px;
        text-transform: uppercase;
    }
    p {
        margin-bottom: 0;
        color: $textGrey;
    }
    span {
        color: $textGrey;
    }
}


img {
    width: 100%;
}

</style>