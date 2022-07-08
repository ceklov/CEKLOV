<template>
  <section id="links" class="lower-section">
    <div>
      <h2>Links</h2>
    </div>

    <div>
      <h4>If you'd like to see more</h4>
    </div>

    <Waypoint :options="options" @change="slideIn">
      <div class="flex justify-center mt-9 mb-24 md:mb-32 links-list">
        <span class="pre-slide-in">
          <a href="https://www.github.com/ceklov/" target="_blank">
            <svg
              height="64"
              aria-hidden="true"
              viewBox="0 0 16 16"
              version="1.1"
              width="64"
              data-view-component="true"
              class="octicon octicon-mark-github v-align-middle"
            >
              <path
                fill-rule="evenodd"
                d="M8 0C3.58 0 0 3.58 0 8c0 3.54 2.29 6.53 5.47 7.59.4.07.55-.17.55-.38 0-.19-.01-.82-.01-1.49-2.01.37-2.53-.49-2.69-.94-.09-.23-.48-.94-.82-1.13-.28-.15-.68-.52-.01-.53.63-.01 1.08.58 1.23.82.72 1.21 1.87.87 2.33.66.07-.52.28-.87.51-1.07-1.78-.2-3.64-.89-3.64-3.95 0-.87.31-1.59.82-2.15-.08-.2-.36-1.02.08-2.12 0 0 .67-.21 2.2.82.64-.18 1.32-.27 2-.27.68 0 1.36.09 2 .27 1.53-1.04 2.2-.82 2.2-.82.44 1.1.16 1.92.08 2.12.51.56.82 1.27.82 2.15 0 3.07-1.87 3.75-3.65 3.95.29.25.54.73.54 1.48 0 1.07-.01 1.93-.01 2.2 0 .21.15.46.55.38A8.013 8.013 0 0016 8c0-4.42-3.58-8-8-8z"
              ></path>
            </svg>
          </a>
        </span>
        <span class="pre-slide-in">
          <a
            href="https://www.linkedin.com/in/cody-eklov-b8507b97/"
            target="_blank"
          >
            <svg
              xmlns="http://www.w3.org/2000/svg"
              viewBox="0 0 24 24"
              data-supported-dps="24x24"
              fill="rgb(10,102,194)"
              class="mercado-match"
              width="64"
              height="64"
              focusable="false"
            >
              <path
                d="M20.5 2h-17A1.5 1.5 0 002 3.5v17A1.5 1.5 0 003.5 22h17a1.5 1.5 0 001.5-1.5v-17A1.5 1.5 0 0020.5 2zM8 19H5v-9h3zM6.5 8.25A1.75 1.75 0 118.3 6.5a1.78 1.78 0 01-1.8 1.75zM19 19h-3v-4.74c0-1.42-.6-1.93-1.38-1.93A1.74 1.74 0 0013 14.19a.66.66 0 000 .14V19h-3v-9h2.9v1.3a3.11 3.11 0 012.7-1.4c1.55 0 3.36.86 3.36 3.66z"
              ></path>
            </svg>
          </a>
        </span>
        <span class="pre-slide-in">
          <a href="https://www.designforchiropractors.com/" target="_blank">
            <svg
              xmlns:dc="http://purl.org/dc/elements/1.1/"
              xmlns:cc="http://creativecommons.org/ns#"
              xmlns:rdf="http://www.w3.org/1999/02/22-rdf-syntax-ns#"
              xmlns:svg="http://www.w3.org/2000/svg"
              xmlns="http://www.w3.org/2000/svg"
              xmlns:sodipodi="http://sodipodi.sourceforge.net/DTD/sodipodi-0.dtd"
              xmlns:inkscape="http://www.inkscape.org/namespaces/inkscape"
              viewBox="0 0 15 15"
              version="1.1"
              id="svg8"
              sodipodi:docname="favicon.svg"
              inkscape:version="0.92.4 (5da689c313, 2019-01-14)"
              height="64"
              width="64"
            >
              <g
                inkscape:label="Layer 1"
                inkscape:groupmode="layer"
                id="layer1"
                transform="translate(0,-282)"
              >
                <rect
                  id="rect12"
                  width="8.4666672"
                  height="8.9958267"
                  x="3.4395833"
                  y="285.09375"
                  style="
                    fill: none;
                    stroke: #2563eb;
                    stroke-width: 0.86832273;
                    stroke-miterlimit: 4;
                    stroke-dasharray: none;
                    stroke-opacity: 0.87058824;
                  "
                />
                <rect
                  style="
                    fill: none;
                    stroke: #3b82f6;
                    stroke-width: 0.93252218;
                    stroke-miterlimit: 4;
                    stroke-dasharray: none;
                    stroke-opacity: 0.68627451;
                  "
                  id="rect836"
                  width="10.054167"
                  height="10.583325"
                  x="2.6458333"
                  y="284.29999"
                />
                <rect
                  style="
                    fill: none;
                    stroke: #3b82f6;
                    stroke-width: 0.92794198;
                    stroke-miterlimit: 4;
                    stroke-dasharray: none;
                    stroke-opacity: 0.68627451;
                  "
                  id="rect840"
                  width="6.8791671"
                  height="7.4083414"
                  x="4.2333331"
                  y="285.88751"
                  inkscape:export-xdpi="85.258743"
                  inkscape:export-ydpi="85.258743"
                />
              </g>
            </svg>
          </a>
        </span>
      </div>
    </Waypoint>
  </section>
</template>

<script>
import { Waypoint } from "vue-waypoint";

export default {
  name: "LinksComponent",
  components: {
    Waypoint
  },
  setup() {
    const options = {
      root: document.getElementById("links"),
      rootMargin: "0px",
      threshold: 0.75
    }

    let visible = false;

    const slideIn = (waypointState) => {
      if (waypointState.going === "IN" && !visible) {
        // grab each of the .link-lists spans and slide them into view
        let spans = waypointState.el.getElementsByTagName("span");
        let delay = 0;
        for (let span of spans) {
          setTimeout(function() { span.classList.add("slide-in") }, delay * 300);
          delay++;
        }
        visible = true;
      }
    }

    return {
      slideIn,
      options,
    };
  },
};
</script>