<template>
  <div id="app">
    <div class="container">
      <div class="row">
        <!-- Example 1 - Car -->
        <div class="col-6 mb-4 card p-0 card">
          <div class="card-body">
            <vue-three-sixty 
              :amount=52
              imagePath="https://s3-sa-east-1.amazonaws.com/qcarro/360/34"
              fileName="{index}"
              spinReverse
              buttonClass="dark"
              :buttonsVerify="true"
              :hotSpot="data"
              :carID="34"
            >
            </vue-three-sixty>
          </div>
        </div>
        <!--/ Example 1 - Car -->

        <div class="col-12 mb-4 text-center card">
          <h4>More Examples</h4>
          <p>A simple, interactive resource that can be used to provide a virtual tour of your product.</p>
          <p>100% Mobile Responsive with Touch Actions</p>
          <p>Features include Zoom, Pan, Autoplay, Loop, Crop, Reverse Spin, Show/Hide Header, and more. <a href="https://github.com/rajeevgade/vue-360-viewer">Click here for more information.</a> </p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>

//import I360Viewer from './components/I360Viewer.vue'

export default {
  name: 'app',
  data() {
    return {
      data: [{
        XPos: 915.7893585742847,
        YPos: 500.9178893400493,
        frame: 1,
        ID: 1,
        data: 'https://res.cloudinary.com/cazoo/image/upload/c_scale,f_auto,h_1080,q_auto,w_1920/cazoo-imagery/car_gallery_images/MK16ERY/dqAc68JXzS3fSbZGnRL0.JPG'
      },
      {
        XPos: 487.3764756483823,
        YPos: 794.9959518803277,
        frame: 2,
        ID: 2,
      }]
    }
  },
  mounted() {
    //safari zoom bug fix
    this.disableZoomin();
  },
  methods: {
    disableZoomin(){
      document.addEventListener("gesturestart", function (e) {
        e.preventDefault();
          document.body.style.zoom = 0.99;
      });
      document.addEventListener("gesturechange", function (e) {
        e.preventDefault();
        document.body.style.zoom = 0.99;
      });
      
      document.addEventListener("gestureend", function (e) {
          e.preventDefault();
          document.body.style.zoom = 1;
      });
    }
  }
}
</script>