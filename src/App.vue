<template>
  <h1>Advice Generator</h1>
</template>

<script>
export default {
  name: "App",
  components: {},
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
}
</style>
