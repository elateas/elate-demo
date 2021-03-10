<script>
  export let to;
  export let handleClick;
  export let desktopHide = "";

  const { pathname } = window.location;
  let isActive = pathname === to;
</script>

<li class={`${desktopHide ? "hidden" : ""} ${isActive ? "active" : ""}`}>
  <a aria-current={isActive} on:click={handleClick} href={to}><slot /></a>
</li>

<style>
  @keyframes nav-appear {
    to {
      transform: translate(-12%, 270%);
    }
  }
  a {
    color: #fff;
  }
  li {
    padding-right: 32px;
    position: relative;
  }
  .active::before {
    content: "";
    position: absolute;
    bottom: 0;
    transform: translate(-8%, 350%);
    height: 15px;
    width: 100%;
    background-color: var(--color-pink);
    z-index: -1;
    border-top-left-radius: 4px;
    border-top-right-radius: 4px;
    animation: nav-appear 250ms;
    animation-fill-mode: forwards;
  }

  .hidden {
    display: none;
  }

  @media screen and (max-width: 992px) {
    .hidden {
      display: initial;
    }
    li {
      padding-bottom: 20px;
      padding-right: 24px;
    }
    .active::before {
      right: 0;
      transform: translate(0px, -12px);
      height: 50px;
      border-top-right-radius: 0;
      border-bottom-left-radius: 4px;
      width: 4px;
      animation: none;
    }
  }
</style>
