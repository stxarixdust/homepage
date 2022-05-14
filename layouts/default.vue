<template>
  <div>
    <Nuxt/>
  </div>
</template>

<style lang="scss">
  body {
    background: #DFE6E9;
    margin: 0;
    font-size: 18px;
    font-family: "Apoc LC Trial Light";
  }
  *{
    scroll-behavior: smooth;
  }
  ::selection {
    color: #DFE6E9;
    background: black;
  }
  h1 {
    font-family: "Attack Type";
    font-weight: 500;
    font-size: 91.13px;
    letter-spacing: -4px;
    line-height: 85%;
    margin: 0;
  }
  h2 {
    font-family: "Attack Type";
    font-weight: 500;
    font-size: 60.75px;
    letter-spacing: -3px;
    line-height: 85%;
    margin: 0;
  }
  a{
    text-decoration: none;
    color: inherit;
  }
  p {
    line-height: 1.6;
    margin: 0;
    text-align: justify;
  }
  .buttonsContainer{
    display: flex;
    gap: 32px;
  }
  .button {
    background: rgba(#9288C2, .11);
    border: 1px solid rgba(#9288C2, .33);
    padding: 16px 12px;
    display: flex;
    gap: 8px;
    align-items: center;
    justify-content: center;
    box-sizing: border-box;
    width: fit-content;
    user-select: none;
    cursor: pointer;
    transition: 120ms;
    &:hover {
      background: rgba(#9288C2, .22);
    }
    &.primary {
      font-family: "Apoc LC Trial Dark";
      background: #4521E6;
      color: #DFE6E9;
      &:hover{
        background: rgba(#4521E6, .66);
      }
    }
    &.fixedWidth {
      text-align: center;
      padding: 16px 0px;
    }
  }
</style>