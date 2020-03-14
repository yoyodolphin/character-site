<template>
  <div class="about">
    <h1>This is an about page</h1>

    <b-button size="lg"
      variant="outline-primary">
      Test Button</b-button>
<br>
<br>
    <p>ギャラリー <b-badge> New </b-badge></p>
<br>
<br>
    <b-carousel
      id="carousel-1"
      v-model="slide"
      :interval="4000"
      controls
      indicators
      background="#ababab"
      img-width=50%
      img-height=50%
      style="text-shadow: 1px 1px 2px #333;"
      @sliding-start="onSlideStart"
      @sliding-end="onSlideEnd"
      >

       <b-carousel-slide
         caption="First slide">
         <template v-slot:img>
           <img
             src="@/assets/caImage1.png">
         </template>
       </b-carousel-slide>

       <b-carousel-slide
         caption="Second slide">
         <template v-slot:img>
           <img
             src="@/assets/caImage2.png">
         </template>
       </b-carousel-slide>

       <b-carousel-slide
         caption="Third slide">
         <template v-slot:img>
           <img
             src="@/assets/caImage3.png">
         </template>
       </b-carousel-slide>

   </b-carousel>

  </div>
</template>
