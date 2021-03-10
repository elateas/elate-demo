<script>
  import { onMount } from "svelte";
  import Nav from "../components/Nav.svelte";
  import Page from "../components/Page.svelte";
  import Body from "../typography/Body.svelte";
  import Lead from "../typography/Lead.svelte";

  onMount(() => window.scrollTo(0, 0));
</script>

<Nav intersecting={false} />
<main>
  <Page src="/laptoper.jpg" alt="person som skriver på laptop">
    <Lead>Kunne du tenkt deg å bli en del av Elate?</Lead>
    <Body>
      Elate kommer aldri til å bli et stort selskap. Vi ser for oss at vi kan
      vokse til å bli 30-40 konsulenter. Elate er konsulentene i Elate, så du
      vil få mulighet til å påvirke selskapet. Vi har bygginger som kan gjøre
      forbedringer på de fleste områdene i selskapet. <a
        href="https://phb.elate.no">Personalhåndboken</a
      > vår ligger offentlig ute, og endringer gjennomføres ved å opprette en Pull
      Request på repoet.
    </Body>
  </Page>
  <Page>
    <Lead>Ansettesles&shy;prosessen</Lead>
    <Body
      >Vi er opptatt at ting skal være enkelt, tydelig og transparent. Så dette
      er prosessen du kommer til å gå igjennom før du kan bli en del av Elate</Body
    >
    <Body>
      <ol>
        <li>
          En kaffeprat. Du kommer til å få vite om Elate, hva som skiller oss
          fra andre konsulentselskap. Vi får vite noe om hvem du er og hva du
          vil som konsulent.
        </li>
        <li>
          Flinke folk vil helst jobbe med andre flinke folk, så andre runde er
          en teknisk gjennomgang innenfor et tema du er god på. Vi kommer ikke
          til å be deg balansere et binærtre eller skrive Dijkstra agloritme på
          whiteboardet, med mindre du har veldig lyst til å gjøre det selv.
        </li>
        <li>
          Hvis alt stemmer for begge parter, så gies det et tilbud med en
          tilhørende gjennomgang av ansetteslesavtalen.
        </li>
      </ol>
    </Body>
  </Page>
</main>

<style>
  ol li {
    margin-bottom: 16px;
    font-size: 1.25rem;
  }
</style>
