<template>
  <div id="app">
    <template v-if="events.length > 0">
      <template v-for=" (event, index) in events ">
        <template v-if="index % 2 == 0">
          <div class="timeline-block">
            <div class="timeline-img">
              <div class="round">
              </div>
            </div>
            <div class="timeline-content left">
              <div class="timeline-media-section">
                <img src="http://code2beer.com/timeline/demo/images/img-02.jpg" />
              </div>
              <div class="timeline-text-section">
                <div class="timeline-text">
                  <span class="day-time">9:00 AM</span>
                  <h2>First Responsive Timeline</h2>
                  <p>Modern design and clean code</p>
                </div>
              </div>
            </div>
          </div>
        </template>
        <template v-else>
          <div class="timeline-block">
            <div class="timeline-img">
              <div class="round">
              </div>
            </div>
            <div class="timeline-content right">
              <div class="timeline-media-section">
                <img src="http://code2beer.com/timeline/demo/images/img-02.jpg" />
              </div>
              <div class="timeline-text-section">
                <div class="timeline-text">
                  <span class="day-time">9:00 AM</span>
                  <h2>First Responsive Timeline</h2>
                  <p>Modern design and clean code</p>
                </div>
              </div>
            </div>
          </div>
        </template>
      </template>
    </template>
    <mugen-scroll :handler="loadEvents" :should-handle="true">
      <div>loading</div>
    </mugen-scroll>
  
  </div>
</template>
<script>
import mugenScroll from 'vue-mugen-scroll'
export default {
  name: 'app',
  methods: {
    loadEvents () {
      for (let i = 0; i < 10; i++) {
        let event = {}
        this.events.push(event)
      }
    }
  },
  data () {
    return {
      events: []
    }
  },
  components: {
    mugenScroll
  }
}
</script>

<style>
body {
  background: #FBFAF6;
  font-size: 14px;
}

.timeline-text h2,
span {
  font-size: 16px;
  color: #514141;
}

.timeline-media-section img {
  max-width: 100%;
}

.timeline-img {
  padding: 0;
  position: absolute;
  width: 36px;
  height: 36px;
  left: 0;
}

.timeline-content {
  position: relative;
  width: calc(50% - 96px);
  padding: 20px;
  border-width: 1px;
  color: rgb(119, 119, 119);
  border-color: rgb(204, 204, 204);
  border-style: solid;
  background-color: white;
}

.timeline-media-section {
  width: 100%;
}

.timeline-text-section {
  position: relative;
}

.timeline-content .timeline-text-section .day-time {
  top: 0;
  right: 0;
}



.timeline-block {
  position: relative;
  padding: 35px;
  padding-top: 0;
}

.timeline-block::after {
  content: "";
  display: block;
  clear: both;
}

.timeline-block::before {
  width: 2px;
  background: black;
  content: "";
  position: absolute;
  height: 100%;
  top: 0;
  left: 0;
  margin-left: 17px;
}

.round {
  width: 50%;
  height: 50%;
  top: 0px;
  margin: auto;
  border-radius: 50%;
  background: black;
}

.timelien-content {
  float: left;
}

@media only screen and (min-width: 679px) {
  .timeline-img {
    left: 50% !important;
  }

  .timeline-block::before {
    left: 50% !important;
  }

  .timeline-content.left .timeline-text-section .timeline-text {
    padding-right: 100px;
    text-align: right;
  }

  .timeline-content.right .timeline-text-section .timeline-text {
    padding-left: 100px;
    text-align: left;
  }
  .timeline-content.left .timeline-text-section .day-time {
    right: 0;
  }

  .timeline-content.right .timeline-text-section .day-time {
    left: 0;
  }
  .timeline-content.left {
    float: left;
  }

  .timeline-content.right {
    float: right;
  }
  .timeline-content .timeline-text-section .day-time {
    position: absolute;
  }
}
</style>
