<template>
  <!-- <div class="superContainer">
    <div class="container">
      <div class="texto">Hola</div>
      <img
        src="https://images.unsplash.com/photo-1513553404607-988bf2703777?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=436&q=80"
        alt=""
        srcset=""
      />
      <div class="overlay1"></div>
    </div>
    <div class="container">
      <img
        src="https://images.unsplash.com/photo-1513553404607-988bf2703777?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=436&q=80"
        alt=""
        srcset=""
      />
      <div class="overlay2"></div>
    </div>
    <div class="container">
      <img
        src="https://images.unsplash.com/photo-1513553404607-988bf2703777?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=436&q=80"
        alt=""
        srcset=""
      />
      <div class="overlay3"></div>
    </div>
  </div> -->
  <section></section>
  <section class="aqui">
    <div class="cosa1"></div>
    <div class="cosa2">
      Lorem ipsum, dolor sit amet consectetur adipisicing elit. Quidem
      excepturi, ipsam sed veritatis fuga nam nesciunt facilis doloremque libero
      quam praesentium, tenetur recusandae ipsa voluptates voluptatem adipisci
      suscipit itaque! Quia! Voluptas repellat facere deserunt distinctio
      maiores adipisci ipsum temporibus porro sapiente, omnis inventore
      architecto excepturi nostrum natus beatae minima sed quasi exercitationem?
      Ad, fuga a amet quam voluptatem cupiditate. Rerum? Totam asperiores fuga,
      nulla eligendi distinctio quae atque saepe optio consectetur perferendis
      dolorem aspernatur veritatis amet suscipit! Labore quam, ut perspiciatis
      sint in facilis blanditiis non veritatis quidem doloribus dolorem! Ipsum
      porro numquam libero recusandae cum, odit architecto, quibusdam quos quis
      et explicabo aut voluptates quod, autem incidunt. Sunt dicta laborum eaque
      nam possimus delectus facilis soluta sint nobis ipsam?
    </div>
  </section>
</template>

<script>
import { gsap } from "gsap";
import ScrollTrigger from "gsap/ScrollTrigger";
gsap.registerPlugin(ScrollTrigger);
export default {
  name: "BaseComponent",
  props: {},
  data() {
    return {};
  },
  mounted() {
    // var tl = gsap.timeline();
    // tl.to(".overlay1", { opacity: 0, duration: 0.5 });
    // tl.to(".overlay2", { opacity: 0, duration: 0.5 });
    // tl.to(".overlay3", { opacity: 0, duration: 0.5 });
    // tl.fromTo(
    //   ".texto",
    //   { y: -10, opacity: 0 },
    //   { y: 0, duration: 0.2, opacity: 1 }
    // );

    //************************************* */
    const scrollTrigger = gsap.timeline();

    const tween1 = gsap.fromTo(
      ".cosa1",
      {
        x: -500,
      },
      {
        x: 0,
        duration: 1,
      }
    );

    const tween2 = gsap.fromTo(
      ".cosa2",
      {
        x: -500,
      },
      {
        x: 0,
        duration: 1,
      }
    );
    scrollTrigger.add(tween1).add(tween2);
    ScrollTrigger.create({
      animation: scrollTrigger,
      trigger: ".aqui",
      start: "top top",
      end: "bottom bottom%",
      scrub: true,
      markers: true,
    });

    //************************************* */

    // gsap.to(".cosa1", {
    //   x: 200,
    //   scrollTrigger: {
    //     trigger: ".aqui",
    //     pin: true, // pin the trigger element while active
    //     start: "top top", // when the top of the trigger hits the top of the viewport
    //     end: "+=500", // end after scrolling 500px beyond the start
    //     scrub: 1, // smooth scrubbing, takes 1 second to "catch up" to the scrollbar
    //     markers: true,
    //   },
    // });
  },
  computed: {},
  methods: {},
};
</script>

<style>
section {
  height: 100vh;
  width: 100vw;
  display: flex;
  flex-direction: row;
}
.cosa1 {
  height: 50%;
  width: 50%;
  background: pink;
}
.cosa2 {
  height: 50%;
  width: 50%;
}
.superContainer {
  display: flex;
}

.container {
  position: relative;
}

.texto {
  position: absolute;
}

.overlay1,
.overlay2,
.overlay3 {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: white;
  opacity: 1; /* You can adjust the opacity as needed */
}
</style>
