<template>
  <main>
    <h1>Advice # {{ adviceID }}</h1>
    <p class="quote">&quot;{{ adviceText }}&quot;</p>

    <p class="divider">
      <svg width="295" height="16" xmlns="http://www.w3.org/2000/svg">
        <g fill="none" fill-rule="evenodd">
          <path fill="#4F5D74" d="M0 8h122v1H0zM173 8h122v1H173z" />
          <g transform="translate(138)" fill="#CEE3E9">
            <rect width="6" height="16" rx="3" />
            <rect x="14" width="6" height="16" rx="3" />
          </g>
        </g>
      </svg>
    </p>

    <button @click.prevent="getAdvicefromApi" class="dice-bg">
      <svg
        class="dice"
        width="24"
        height="24"
        xmlns="http://www.w3.org/2000/svg"
      >
        <path
          d="M20 0H4a4.005 4.005 0 0 0-4 4v16a4.005 4.005 0 0 0 4 4h16a4.005 4.005 0 0 0 4-4V4a4.005 4.005 0 0 0-4-4ZM7.5 18a1.5 1.5 0 1 1 0-3 1.5 1.5 0 0 1 0 3Zm0-9a1.5 1.5 0 1 1 0-3 1.5 1.5 0 0 1 0 3Zm4.5 4.5a1.5 1.5 0 1 1 0-3 1.5 1.5 0 0 1 0 3Zm4.5 4.5a1.5 1.5 0 1 1 0-3 1.5 1.5 0 0 1 0 3Zm0-9a1.5 1.5 0 1 1 0-3 1.5 1.5 0 0 1 0 3Z"
          fill="#202733"
        />
      </svg>
    </button>
  </main>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      advice: Object,
    };
  },
  computed: {
    adviceID() {
      return this.advice.slip.id;
    },
    adviceText() {
      return this.advice.slip.advice;
    },
  },
  components: {},
  async created() {
    const response = await fetch("https://api.adviceslip.com/advice");
    this.advice = await response.json();
  },
  actions: {
    async getAdvicefromApi() {
      const response = await fetch("https://api.adviceslip.com/advice");
      this.advice = await response.json();
    },
  },
};
</script>

<style>
@font-face {
  font-family: "Manrope";
  font-style: normal;
  font-weight: 800;
  font-display: swap;
  src: url(./assets/xn7_YHE41ni1AdIRqAuZuw1Bx9mbZk59E9_C-bnTfc7AGrY.woff2)
    format("woff2");
  unicode-range: U+0000-00FF, U+0131, U+0152-0153, U+02BB-02BC, U+02C6, U+02DA,
    U+02DC, U+2000-206F, U+2074, U+20AC, U+2122, U+2191, U+2193, U+2212, U+2215,
    U+FEFF, U+FFFD;
}

:root {
  font-family: Manrope, sans-serif;
  font-size: 28px;
  --color-primary-1: hsl(193, 38%, 86%);
  --color-primary-2: hsl(150, 100%, 66%);
  --color-neutral-ligth: hsl(217, 19%, 38%);
  --color-neutral-dark: hsl(217, 19%, 24%);
  --color-neutral-darkblue: hsl(218, 23%, 16%);
}

body {
  width: 375px;
  margin-top: 0px;
  margin: auto;
  background-color: var(--color-neutral-darkblue);
  color: var(--color-primary-1);
}

main {
  background-color: var(--color-neutral-dark);
  text-align: center;
  position: relative;
  margin-inline: 0.5rem;
  margin-top: 2rem;
  padding-inline: 0.5rem;
  border-radius: 15px;
}

h1 {
  margin: 0;
  padding-top: 1rem;
  font-size: 0.4rem;
  color: var(--color-primary-2);
  text-align: center;
  text-transform: uppercase;
  letter-spacing: 0.1rem;
}

.quote {
  letter-spacing: 0.05rem;
  margin-block: 1rem;
}

.dice-bg {
  all: unset;
  background-color: var(--color-primary-2);
  width: 50px;
  height: 50px;
  margin: auto;
  display: flex;
  align-items: center;
  justify-content: center;
  border-radius: 25px;
  position: absolute;
  bottom: -25px;
  left: 148px;
}

.divider {
  padding-bottom: 2rem;
}
</style>
