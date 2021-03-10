<script>
  export let name;
  export let subTitle = "";
  export let description;
  export let src;
  export let alt;
  export let reversed = false;
</script>

<article class={reversed ? "reversed" : ""}>
  <img {src} {alt} />
  <div>
    <span class="title">{name}</span>
    <span class="subtitle">{subTitle}</span>
    <p>{description}</p>
  </div>
</article>

<style>
  article {
    box-shadow: 0 0 12px 0 rgba(0, 0, 0, 0.2);
    display: flex;
    border-radius: 8px;
    overflow: hidden;
    margin-bottom: 24px;
    max-width: 600px;
    width: 100%;
  }

  .title {
    font-size: 1.375rem;
    display: block;
  }
  .subtitle {
    font-size: 0.875rem;
    display: block;
  }

  .reversed {
    flex-direction: row-reverse;
  }

  div {
    padding: 24px 48px;
  }

  img {
    width: 125px;
    object-fit: contain;
  }
  @media screen and (max-width: 992px) {
    div {
      padding: 24px 12px;
    }

    article,
    .reversed {
      flex-direction: column;
    }
    img {
      width: 100%;
      max-height: 125px;
      object-fit: cover;
      object-position: 0 15%;
    }
  }
</style>
