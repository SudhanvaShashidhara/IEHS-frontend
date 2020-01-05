<script>
  import { onMount } from "svelte";
  onMount(() => {
    const images = document.querySelectorAll("[data-src]");
    let imgObserver;
    if (typeof window.IntersectionObserver !== "function") {
      images.forEach(img => {
        const imgSrc = img.getAttribute("data-src");
        img.src = imgSrc;
      });
    } else {
      const imgOptions = { threshold: 0, rootMargin: "0px 0px 5px 0px" };
      const loadImage = imgTarget => {
        const imgSrc = imgTarget.getAttribute("data-src");
        if (!imgSrc) return;
        imgTarget.src = imgSrc;
      };
      imgObserver = new IntersectionObserver((entries, imgObserver) => {
        entries.forEach(entry => {
          if (!entry.isIntersecting) return;
          else {
            loadImage(entry.target);
            imgObserver.unobserve(entry.target);
          }
        });
      }, imgOptions);
      images.forEach(img => {
        imgObserver.observe(img);
      });
    }

    return () => imgObserver.disconnect();
  });
</script>

<style>
  h1 {
    margin-top: 2rem;
    text-shadow: 2px 2px 2px #20fff8, 2px 5px 2px #ff0000;
    text-shadow: 2px 2px 2px #ffcb00, 7px 5px 2px rgba(148, 43, 43, 0.72);
    text-align: center;
  }
  .gallery-image-container {
    width: 85%;
    flex-direction: column;
    margin: 2rem auto;
  }

  .image {
    width: 100%;
    margin-bottom: 1rem;
  }
  [data-src] {
    min-height: 150px;
    min-width: 150px;
  }
  img {
    max-width: 100%;
    height: auto;
  }
  @media only screen and (min-width: 1024px) {
    h1 {
      font-size: 3rem;
    }
    .gallery-image-container {
      width: 80%;
      display: flex;
      flex-wrap: wrap;
      justify-content: space-between;
      align-content: space-between;
      flex-direction: row;
    }

    .image {
      width: 45%;
      margin-bottom: 2rem;
    }
  }

  @media only screen and (min-width: 1280px) {
    .gallery-image-container {
      width: 70%;
    }
    .image {
      width: 32%;
    }
  }
</style>

<svelte:head>
  <title>Gallery Page</title>
</svelte:head>

<h1>GALLERY</h1>
<div class="gallery-image-container">
  <div class="image">
    <img data-src="./gallery/400.JPG" alt="" />
  </div>
  <div class="image">
    <img data-src="./gallery/416.JPG" alt="" />
  </div>
  <div class="image">
    <img data-src="./gallery/DSCN9360.JPG" alt="" />
  </div>
  <div class="image">
    <img data-src="./gallery/IMG_1275.JPG" alt="" />
  </div>
  <div class="image">
    <img data-src="./gallery/IMG_1282.JPG" alt="" />
  </div>
  <div class="image">
    <img data-src="./gallery/IMG_1782.JPG" alt="" />
  </div>

  <div class="image">
    <img data-src="./gallery/IMG_6875.JPG" alt="" />
  </div>
  <div class="image">
    <img data-src="./gallery/IMG_6879.JPG" alt="" />
  </div>
  <div class="image">
    <img data-src="./gallery/IMG_6888.JPG" alt="" />
  </div>
  <div class="image">
    <img data-src="./gallery/IMG_6892.JPG" alt="" />
  </div>
  <div class="image">
    <img data-src="./gallery/IMG_6895.JPG" alt="" />
  </div>
  <div class="image">
    <img data-src="./gallery/IMG_6902.JPG" alt="" />
  </div>

  <div class="image">
    <img data-src="./gallery/IMG_6905.JPG" alt="" />
  </div>
  <div class="image">
    <img data-src="./gallery/IMG_6911.JPG" alt="" />
  </div>
  <div class="image">
    <img data-src="./gallery/IMG_6929.JPG" alt="" />
  </div>
  <div class="image">
    <img data-src="./gallery/IMG_6945.JPG" alt="" />
  </div>
  <div class="image">
    <img data-src="./gallery/IMG_6946.JPG" alt="" />
  </div>
  <div class="image">
    <img data-src="./gallery/IMG_6947.JPG" alt="" />
  </div>

  <div class="image">
    <img data-src="./gallery/IMG_6973.JPG" alt="" />
  </div>
  <div class="image">
    <img data-src="./gallery/IMG_6982.JPG" alt="" />
  </div>
  <div class="image">
    <img data-src="./gallery/IMG_6985.JPG" alt="" />
  </div>
  <div class="image">
    <img data-src="./gallery/IMG_7005.JPG" alt="" />
  </div>
  <div class="image">
    <img data-src="./gallery/IMG_7007.JPG" alt="" />
  </div>
  <div class="image">
    <img data-src="./gallery/IMG_7065.JPG" alt="" />
  </div>

  <div class="image">
    <img data-src="./gallery/IMG_7069.JPG" alt="" />
  </div>
  <div class="image">
    <img data-src="./gallery/IMG_7080.JPG" alt="" />
  </div>
  <div class="image">
    <img data-src="./gallery/IMG_7151.JPG" alt="" />
  </div>
  <div class="image">
    <img data-src="./gallery/IMG_7260.JPG" alt="" />
  </div>
  <div class="image">
    <img data-src="./gallery/IMG-20171214-WA0029.jpg" alt="" />
  </div>
  <div class="image">
    <img data-src="./gallery/IMG-20171214-WA0031.jpg" alt="" />
  </div>

  <div class="image">
    <img data-src="./gallery/IMG-20171214-WA0037.jpg" alt="" />
  </div>
  <div class="image">
    <img data-src="./gallery/IMG-20171214-WA0043.jpg" alt="" />
  </div>
  <div class="image">
    <img data-src="./gallery/IMG-20171214-WA0049.jpg" alt="" />
  </div>
  <div class="image">
    <img data-src="./gallery/IMG-20171215-WA0000.jpg" alt="" />
  </div>
  <div class="image">
    <img data-src="./gallery/IMG-20171215-WA0006.jpg" alt="" />
  </div>
  <div class="image">
    <img data-src="./gallery/IMG-20171215-WA0008.jpg" alt="" />
  </div>

  <div class="image">
    <img data-src="./gallery/IMG-20171222-WA0001.jpg" alt="" />
  </div>

  <div class="image">
    <img data-src="./gallery/IMG-20171222-WA0003.jpg" alt="" />
  </div>

  <div class="image">
    <img data-src="./gallery/IMG-20171222-WA0004.jpg" alt="" />
  </div>

  <div class="image">
    <img data-src="./gallery/IMG-20171222-WA0009.jpg" alt="" />
  </div>

  <div class="image">
    <img data-src="./gallery/IMG-20171222-WA0011.jpg" alt="" />
  </div>

  <div class="image">
    <img data-src="./gallery/IMG-20171222-WA0015.jpg" alt="" />
  </div>

  <div class="image">
    <img data-src="./gallery/IMG-20171224-WA0003.jpg" alt="" />
  </div>

  <div class="image">
    <img data-src="./gallery/IMG-20171224-WA0004.jpg" alt="" />
  </div>

  <div class="image">
    <img data-src="./gallery/IMG-20171228-WA0005.jpg" alt="" />
  </div>

  <div class="image">
    <img data-src="./gallery/IMG-20180104-WA0035.jpg" alt="" />
  </div>
  <div class="image">
    <img data-src="./gallery/IMG-20180104-WA0042.jpg" alt="" />
  </div>
  <div class="image">
    <img data-src="./gallery/IMG-20180104-WA0051.jpg" alt="" />
  </div>

  <div class="image">
    <img data-src="./gallery/SAVE_20171229_184045.jpeg" alt="" />
  </div>
</div>
