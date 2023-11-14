

 <section class="carousel">
   <div class="carousel-container">
     {#each slides as { title, imageUrl }, i}
       <div class="slide" style="transform: translateX(-${i * 100}%)">
         <div class="card">
           <img src={imageUrl} alt={title} />
           <div class="card-title">{title}</div>
         </div>
       </div>
     {/each}
      </div>
   <button on:click={prevSlide}>Previous</button>
   <button on:click={nextSlide}>Next</button>
   </section>

 <style>
   .carousel {
     display: flex;
     overflow: hidden;
     width: 100%;
   }
 
   .slide {
     flex: 0 0 100%;
     transition: transform 0.5s ease-in-out;
   }
 
   .carousel-container {
     display: flex;
     /* width: ${slides.length * 100}%;
     transform: translateX(-${currentSlide * 100}%); */
   }
 
   .card {
     border: 1px solid #ccc;
     border-radius: 8px;
     margin: 10px;
     overflow: hidden;
   }
 
   .card img {
     width: 100%;
     height: auto;
     border-bottom: 1px solid #ccc;
   }
 
   .card-title {
     padding: 10px;
     font-size: 18px;
     font-weight: bold;
   }
 </style>

<script>
   let currentSlide = 0;

const slides = [
  {
    title: 'Slide 1',
    imageUrl: '/static/assets/image 252.png', // Replace with the path to your PNG image
  },
  {
    title: 'Slide 2',
    imageUrl: '/static/assets/image 253.png',
  },
  {
    title: 'Slide 3',
    imageUrl: '/static/assets/image 254.png.png',
  },
  // Add more slides as needed
];

const nextSlide = () => {
  currentSlide = (currentSlide + 1) % slides.length;
};

const prevSlide = () => {
  currentSlide = (currentSlide - 1 + slides.length) % slides.length;
};

  </script>
  
    