<script>
  let isOpen = false;
  import { links } from "svelte-routing";
  import NavLink from "./NavLink.svelte";

  const handleClick = () => {
    if (window.innerWidth < 992) {
      isOpen = !isOpen;
    }
  };
</script>

<button on:click={handleClick}>
  <div class={`burger burger--${isOpen ? "close" : ""}`} />
</button>
<ul class={`mega-menu--${isOpen ? "show" : "hidden"}`} use:links>
  <NavLink desktopHide={true} {handleClick} to="/">Hjem</NavLink>
  <NavLink {handleClick} to="/salg">Kontakt oss</NavLink>
  <NavLink {handleClick} to="/konsulent">Karriere</NavLink>
  <NavLink {handleClick} to="/oss">Våre konsulenter</NavLink>
  <NavLink {handleClick} to="https://phb.elate.no">Personalhåndboka</NavLink>
</ul>

<style>
  .burger {
    position: relative;
    height: 2px;
    width: 40px;
    z-index: 1;
    margin-right: 20px;
    background-color: white;
    transition: 125ms ease-in-out background-color;
    display: none;
  }

  .burger::after,
  .burger::before {
    position: absolute;
    content: "";
    width: 100%;
    height: 2px;
    left: 0;
    background-color: white;
    transition: 125ms ease-in-out transform;
  }

  .burger::before {
    top: -10px;
  }

  .burger::after {
    top: 10px;
  }

  button {
    background-color: transparent;
    border: none;
    min-height: 40px;
    z-index: 1;
  }

  button:active {
    background-color: transparent;
  }

  .burger--close {
    background-color: transparent;
  }

  .burger--close::before {
    transform: translateY(10px) rotate(-45deg);
  }
  .burger--close::after {
    transform: translateY(-10px) rotate(45deg);
  }

  .mega-menu--hidden {
    display: flex;
  }

  @keyframes appear {
    to {
      opacity: 1;
      transform: translateY(0);
    }
  }

  .mega-menu--show {
    display: flex;
    flex-direction: column;
    align-items: flex-end;
    position: fixed;
    top: 0;
    bottom: 0;
    left: 0;
    right: 0;
    bottom: 0;
    overflow-y: scroll;
    background-color: var(--color-blue);
    margin: 0;
    padding: 0;
    padding-top: 114px;
    opacity: 0;
    transform: translateY(-100px);
    animation: appear;
    animation-duration: 250ms;
    animation-fill-mode: forwards;
  }

  ul {
    list-style: none;
    color: white;
    font-size: 1.25rem;
  }
  @media screen and (max-width: 992px) {
    ul {
      font-size: 1.75rem;
    }

    .mega-menu--hidden {
      display: none;
    }

    .burger {
      display: block;
    }
  }
</style>
