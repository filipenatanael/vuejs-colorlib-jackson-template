<template>
  <section class="colorlib-experience" data-section="experience">
    <div class="colorlib-narrow-content">
      <div class="row">
        <div class="col-md-6 col-md-offset-3 col-md-pull-3 animate-box" data-animate-effect="fadeInLeft">
          <span class="heading-meta">{{content.title}}</span>
          <h2 class="colorlib-heading animate-box">{{content.caption}}</h2>
        </div>
      </div>
      <div class="row">
        <div class="col-md-12">
          <div class="timeline-centered">

            <article v-for="(experience, index) in content.experiences" class="timeline-entry animate-box" data-animate-effect="fadeInLeft">
              <div class="timeline-entry-inner">
                <div v-bind:class="`timeline-icon color-${index+1}`">
                  <i class="icon-pen2"></i>
                </div>

                <div class="timeline-label">
                  <h2><a href="#">{{experience.responsibility}}</a> <span>{{experience.period}}</span></h2>
                  <p>{{experience.description}}</p>
                </div>
              </div>
            </article>

            <article class="timeline-entry begin animate-box" data-animate-effect="fadeInBottom">
              <div class="timeline-entry-inner">
                <div class="timeline-icon color-none">
                </div>
              </div>
            </article>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import store from '../store'
import defaultMixin from './mixins/defaultMixin.js'

export default {
  name: 'Experience',
  mixins: [defaultMixin],
  computed: {
    content(){
      return store.state.experience.content
    }
  }
}
</script>
