<template>
  <f7-page name="allphotos">
    <f7-navbar title="All Photos" style="color: teal;"></f7-navbar>
    <f7-block-title style="margin-top: 15px; color: teal;">About Posts Photos</f7-block-title>

    <f7-block style="padding: 0px;" id="photos">
      <f7-link v-for="(photo, index) in photos" :key="index">
        <img :src="photo.post_image" >
      </f7-link>
    </f7-block>
  </f7-page>
</template>


<script>
export default {
  data  () {
    return {
      photos: [
        { post_image: 'https://tinypng.com/images/social/website.jpg' },
        { post_image: 'https://media.wired.com/photos/5c1ae77ae91b067f6d57dec0/master/pass/Comparison-City-MAIN-ART.jpg' },
        { post_image: 'https://cdn.pixabay.com/photo/2015/12/01/20/28/road-1072823__340.jpg' },
        { post_image: 'https://cdn.pixabay.com/photo/2015/06/19/21/24/the-road-815297__340.jpg' },
        { post_image: 'https://www.freedigitalphotos.net/images/img/homepage/394230.jpg' },
        { post_image: 'https://www.hd-freewallpapers.com/latest-wallpapers/desktop-parrot-images-free-download.jpg' },
        { post_image: 'https://i.pinimg.com/originals/94/dd/57/94dd573e4b4de604ea7f33548da99fd6.jpg' },
        
        { post_image: 'https://www.freedigitalphotos.net/images/img/homepage/394230.jpg' },
        { post_image: 'https://www.hd-freewallpapers.com/latest-wallpapers/desktop-parrot-images-free-download.jpg' },
        { post_image: 'https://tinypng.com/images/social/website.jpg' },
        { post_image: 'https://media.wired.com/photos/5c1ae77ae91b067f6d57dec0/master/pass/Comparison-City-MAIN-ART.jpg' },       
      ]
    }
  },
}
</script>

<style scoped>
/*last */
#photos {
   /* Prevent vertical gaps */
   line-height: 0;
   -webkit-column-count: 5;
   -webkit-column-gap:   2px;
   -moz-column-count:    5;
   -moz-column-gap:      2px;
   column-count:         5;
   column-gap:           2px;
}

#photos img { 
  width: 100% !important;
  height: auto !important;
  margin-bottom: 2px;
}
@media (max-width: 600px) {
  #photos {
    -moz-column-count:    3;
    -webkit-column-count: 3;
    column-count:         3;
  }
}

/*@media (max-width: 1200px) {
  #photos {
    -moz-column-count:    4;
    -webkit-column-count: 4;
    column-count:         4;
  }
}
@media (max-width: 1000px) {
  #photos {
  -moz-column-count:    3;
  -webkit-column-count: 3;
  column-count:         3;
  }
}
@media (max-width: 800px) {
  #photos {
  -moz-column-count:    2;
  -webkit-column-count: 2;
  column-count:         2;
  }
}
@media (max-width: 400px) {
  #photos {
  -moz-column-count:    1;
  -webkit-column-count: 1;
  column-count:         1;
  }
}*/
</style>
