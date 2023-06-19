<template>
    <div class="card">
        <div class="photo">
            <img src="https://s-media-cache-ak0.pinimg.com/236x/3b/36/ca/3b36ca3afe0fa0fd4984b9eee2e154bb.jpg">
        </div>
        <div class="description">
            <h2>Classic Peace Lily</h2>
            <h4>Popular House Plant</h4>
            <h1>$18</h1>
            <p>Classic Peace Lily is a spathiphyllum floor plant arranged in a bamboo planter with a blue & red ribbom and butterfly pick.</p>
            <button>Add to Cart</button>
            <button>Wishlist</button>
        </div>
    </div>
</template>
<script setup>

</script>
<style scoped>

.card {
    width: 650px;
    height: 350px;
    margin-top: 10px;
    box-shadow: 0 2px 5px 0 rgba(0,0,0,0.16),0 2px 10px 0 rgba(0,0,0,0.12);  
}
&:hover {
  box-shadow: 0 8px 17px 0 rgba(0,0,0,0.2),0 6px 20px 0 rgba(0,0,0,0.19);
} 
.photo {  
      padding: 30px;
      width: 45%;
      text-align: center;
      float: left;
}  
img { 
        max-height: 240px; 
}
.description {
       padding: 30px;
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