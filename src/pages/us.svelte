<script>
  import { onMount } from "svelte";
  import Nav from "../components/Nav.svelte";
  import Body from "../typography/Body.svelte";
  import DeveloperCard from "./us/DeveloperCard.svelte";
  onMount(() => window.scrollTo(0, 0));

  const employees = [
    {
      name: "Fredrik Løf",
      subTitle: "Daglig leder",
      description: "",
      img: "/blank_avatar.svg",
    },
    {
      name: "Peder Kongelf",
      subTitle: "",
      description: "",
      img: "/blank_avatar.svg",
    },
    {
      name: "Tobias Lundin",
      subTitle: "",
      description: "",
      img: "/blank_avatar.svg",
    },
    {
      name: "Christian Karlsson",
      subTitle: "",
      description: "",
      img: "/blank_avatar.svg",
    },
    {
      name: "Fredrik Sørensen",
      subTitle: "",
      description: "",
      img: "/blank_avatar.svg",
    },
    {
      name: "Jonathan Melchert",
      subTitle: "",
      description: "",
      img: "/blank_avatar.svg",
    },
    {
      name: "Kaja Bye Svartveit",
      subTitle: "",
      description: "",
      img: "/blank_avatar.svg",
    },
    {
      name: "Leiv Fredrik Berge",
      subTitle: "Frontend utvikler & Senior konsulent",
      description:
        "Kan forskjellen på React.useMemo() og React.memo(). Brenner for å gjøre internet mer tilgjengelig.",
      img: "/lfberge.jpg",
    },
    {
      name: "Alf Magnus Stålesen",
      subTitle: "",
      description: "",
      img: "/blank_avatar.svg",
    },
    {
      name: "Christian Dancke Tuen",
      subTitle: "",
      description: "",
      img: "/blank_avatar.svg",
    },
    {
      name: "Øyvind Nordsted Wedøe",
      subTitle: "",
      description: "",
      img: "/blank_avatar.svg",
    },
  ];
</script>

<Nav intersecting={false} />

<section>
  <Body>
    <span>
      Elate er konsulentene i Elate. Vi er seniorkonsulenter med ulike
      spesialiseringer som deler noen kjernerverdier.
    </span>
  </Body>
  {#each employees as employee, i}
    <DeveloperCard
      name={employee.name}
      subTitle={employee.subTitle}
      description={employee.description}
      src={employee.img}
      alt={employee.name}
      reversed={i % 2}
    />
  {/each}
</section>

<style>
  section {
    margin-top: 90px;
    padding: 24px 48px;
    display: grid;
    place-items: center;
  }

  span {
    margin: 64px 0;
    display: block;
  }
  @media screen and (max-width: 992px) {
    section {
      padding: 24px 12px;
    }
  }
</style>
