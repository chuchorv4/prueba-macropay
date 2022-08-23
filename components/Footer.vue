<template>
  <footer class= 'footer container'>
    <b-row class="justify-content-md-center p-2">
      <b-col cols="12" lg="4">
        <h4 class="title">{{ title }}</h4>
        <p>{{ address }}</p>
        <p>{{ phone }}</p>
        <p v-if="email"><a :href="'mailto:'+email">{{ email }}</a></p>
      </b-col>
      <b-col cols="12" lg="4" class="footer-map">
        <div class="mapouter">
          <div class="gmap_canvas">
            <iframe width="300" height="180" id="gmap_canvas" src="https://maps.google.com/maps?q=monumento%20patria&t=&z=13&ie=UTF8&iwloc=&output=embed" frameborder="0" scrolling="no" marginheight="0" marginwidth="0"></iframe>
              <a href="https://putlocker-is.org"></a>
            <br>
            <style>.mapouter{position:relative;text-align:right;height:180px;width:300px;}</style>
              <a href="https://www.embedgooglemap.net"></a>
            <style>.gmap_canvas {overflow:hidden;background:none!important;height:180px;width:300px;}</style>
          </div>
        </div>
      </b-col>
      <b-col cols="12" lg="4">
        <b-row class="justify-content-md-center">
          <b-col cols='2'>
            <a class="icon-rs" :href="youtube">
              <b-icon class="m-auto" icon="youtube" font-scale="1"></b-icon>
            </a>
          </b-col>
          <b-col cols='2'>
            <a class="icon-rs" :href="facebook">
              <b-icon class="m-auto" icon="facebook" font-scale="1"></b-icon>
            </a>
          </b-col>
          <b-col cols='2'>
            <a class="icon-rs" :href="twitter">
              <b-icon class="m-auto" icon="twitter" font-scale="1"></b-icon>
            </a>
          </b-col>
        </b-row>
      </b-col>
    </b-row>
  </footer>
</template>
<script>
export default {
  data() {
    return {
      title: 'Macropay',
      address: 'Calle num',
      phone: '9999000000',
      email: 'jesr.v.4@gmail.com',
      facebook: '#',
      youtube: '#',
      twitter: '#',
    }
  }
}
</script>
<style scoped>
  .footer {
    width: 100%;
    height: 200px;
    background-color: #ddd;
    color: #222;
    font-family: 'Trebuchet MS', 'Lucida Sans Unicode', 'Lucida Grande', 'Lucida Sans', Arial, sans-serif;
  }
  .icon-rs {
    text-decoration: none;
    color: #888;
    font-size: 40px;
    line-height: 35px;
    border-radius: 50%;
    padding: 0px 4px;
    background-color: #fff;
  }
  .icon-rs:hover {
    color: #008ee0;
  }
  img {
    margin: auto;
    display: block;
  }
  @media only screen and (max-width: 996px) {
    .footer-map {
      display: none;
    }
    .icon-rs {
      font-size: 28px;
      line-height: 20px;
    }
  }
</style>