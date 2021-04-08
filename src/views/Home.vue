<template>
  <div class="home">
    <h1>{{ message }}</h1>
    <!-- <img
      class="main-image"
      src="https://nationaltoday.com/wp-content/uploads/2020/02/national-golden-retriever-day.jpg"
      alt="golden boi"
    />
    <br /> -->
    <button id="button" aria-describedby="tooltip">I'm a button</button>
    <div id="tooltip" role="tooltip">
      I'm a tooltip
      <div id="arrow" data-popper-arrow></div>
    </div>
  </div>
</template>

<style>
.main-image {
  max-width: 50%;
}

#tooltip {
  background: #333;
  color: white;
  font-weight: bold;
  padding: 4px 8px;
  font-size: 13px;
  border-radius: 4px;
}
#arrow,
#arrow::before {
  position: absolute;
  width: 8px;
  height: 8px;
  background: inherit;
}

#arrow {
  visibility: hidden;
}

#arrow::before {
  visibility: visible;
  content: "";
  transform: rotate(45deg);
}

#tooltip[data-popper-placement^="top"] > #arrow {
  bottom: -4px;
}

#tooltip[data-popper-placement^="bottom"] > #arrow {
  top: -4px;
}

#tooltip[data-popper-placement^="left"] > #arrow {
  right: -4px;
}

#tooltip[data-popper-placement^="right"] > #arrow {
  left: -4px;
}

#tooltip {
  /* ... */
  display: none;
}

#tooltip[data-show] {
  display: block;
}
</style>

<script>
import { createPopper } from "@popperjs/core";
const button = document.querySelector("#button");
const tooltip = document.querySelector("#tooltip");

// Pass the button, the tooltip, and some options, and Popper will do the
// magic positioning for you:
createPopper(button, tooltip, {
  modifiers: [
    {
      name: "offset",
      options: {
        offset: [0, 8],
      },
    },
  ],
});

export default {
  data: function () {
    return {
      message: "Welcome to the Pooch Page!",
    };
  },
  created: function () {},
  methods: {
     show: function() {
  tooltip.setAttribute('data-show', '');

  // We need to tell Popper to update the tooltip position
  // after we show the tooltip, otherwise it will be incorrect
  popperInstance.update();
},

 hide: function() {
  tooltip.removeAttribute('data-show');
},

const showEvents = ['mouseenter', 'focus'];
const hideEvents = ['mouseleave', 'blur'];

showEvents.forEach(event => {
  button.addEventListener(event, show);
});

hideEvents.forEach(event => {
  button.addEventListener(event, hide);
});

  },
};
</script>
