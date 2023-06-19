<template>
    <div class="card">
        <div class="photo">
            <img :src="`${props.card.image}`">
        </div>
        <div class="description">
            <h3>{{props.card.title}}</h3>
            <h4>Popular House Plant</h4>
            <h1>{{props.card.price}} $</h1>
            <p>{{props.card.description}}</p>
            <button>Add to Cart</button>
            <button>Wishlist</button>
        </div>
    </div>
</template>
<script setup>
    const props = defineProps(['card'])
</script>

<style scoped>
.card {
    width: 650px;
    height: 350px;
    margin-top: 10px;
    box-shadow: 0 2px 5px 0 rgba(0,0,0,0.16),0 2px 10px 0 rgba(0,0,0,0.12);  
}
.card:hover {
  box-shadow: 0 8px 17px 0 rgba(0,0,0,0.2),0 6px 20px 0 rgba(0,0,0,0.19);
} 
.photo {  
      padding: 30px;
      width: 45%;
      text-align: center;
      float: left;
      overflow: overlay;
}  
img { 
        max-height: 240px; 
}
.description {
       padding: 15px;
       float: left;
       width: 55%;
       border-left: 2px solid #efefef;
}
.description h1 {
         color: #515151;
         font-weight: 300;
         padding-top: 15px;
         margin: 0;
         font-size: 30px;
         font-weight: 300;
}
.description h2 {
        color: #515151;
        margin: 0;
        text-transform: uppercase;
        font-weight: 500;
}
.description h4 { 
         margin: 0;
         color: #727272;
         text-transform: uppercase;
         font-weight: 500;
         font-size: 12px
} 
.description p { 
         font-size: 12px; 
         line-height: 20px;
         color: #727272;
         padding: 20px 0;
         margin: 0;
         max-width: 330px;
         overflow: auto;
        max-height: 120px;
}   
button {
         outline: 0;
         border: 0;
         background: none;
         border: 1px solid #d9d9d9;
         padding: 8px 0px;
         margin-bottom: 30px;
         color: #515151;
         text-transform: uppercase;
         width: 125px;
         font-family: inherit;
         margin-right: 5px;
         transition: all 0.3s ease;
         font-weight: 500;
}         
button:hover {
           background: darken(white, 2%);
           border: 1px solid #aedaa6;
           color: #aedaa6;
           cursor: pointer;
        }
</style>