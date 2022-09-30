<script>
  import { getContext } from "svelte";

  export let imageURL = "https://res.cloudinary.com/daog6scxm/image/upload/v1649840554/wallpapers/moonrise_owymlf.png";
  export let emoji = "⚡";

  const { styleable } = getContext("sdk");
  const component = getContext("component");
</script>

<div use:styleable={$component.styles}>
  <section class="image-grid">
    <div class="image-grid-area">
      <img src={imageURL} alt="screen-header" />
    </div>
  </section>
  <section class="header-grid">
    <div class="header-grid-area">
      <div class="emoji-container">
        <div class="emoji">
          <span
            aria-label={emoji}
            style="line-height: 1em; white-space: nowrap;">{emoji}</span
          >
        </div>
      </div>

      <div class="radio-button">
        <input
          type="radio"
          id="imageChoice1"
          name="image"
          value="winter"
          class="radio-item"
          on:change={() => {
            imageURL =
              "https://res.cloudinary.com/daog6scxm/image/upload/v1649840554/wallpapers/moonrise_owymlf.png";
          }}
        />
        <label class="label-item" for="imageChoice1"
          ><img
            src="https://res.cloudinary.com/daog6scxm/image/upload/w_100,c_fill,ar_1:1,g_auto,r_max/v1649840554/wallpapers/moonrise_owymlf.png"
            alt="Winter"
            class="radio-thumbnail"
          /></label
        >

        <input
          type="radio"
          id="imageChoice2"
          name="image"
          value="spring"
          class="radio-item"
          on:change={() => {
            imageURL =
              "https://res.cloudinary.com/daog6scxm/image/upload/v1654716425/wallpapers/blushing-fire_dogkso.png";
          }}
        />
        <label class="label-item" for="imageChoice2"
          ><img
            src="https://res.cloudinary.com/daog6scxm/image/upload/w_100,c_fill,ar_1:1,g_auto,r_max/v1654716425/wallpapers/blushing-fire_dogkso.png"
            alt="Summer"
            class="radio-thumbnail"
          /></label
        >

        <input
          type="radio"
          id="imageChoice3"
          name="image"
          value="summer"
          class="radio-item"
          on:change={() => {
            imageURL =
              "https://res.cloudinary.com/daog6scxm/image/upload/v1649840554/wallpapers/blossom_xz5sfl.png";
          }}
        />
        <label class="label-item" for="imageChoice3"
          ><img
            src="https://res.cloudinary.com/daog6scxm/image/upload/w_100,c_fill,ar_1:1,g_auto,r_max/v1649840554/wallpapers/blossom_xz5sfl.png"
            alt="Summer"
            class="radio-thumbnail"
          /></label
        >

        <input
          type="radio"
          id="imageChoice4"
          name="image"
          value="autumn"
          class="radio-item"
          on:change={() => {
            imageURL =
              "https://res.cloudinary.com/daog6scxm/image/upload/v1664524674/wallpapers/autumnal-peach_d9m19d.png";
          }}
        />
        <label class="label-item" for="imageChoice4"
          ><img
            src="https://res.cloudinary.com/daog6scxm/image/upload/w_100,c_fill,ar_1:1,g_auto,r_max/v1664524674/wallpapers/autumnal-peach_d9m19d.png"
            alt="Autumn"
            class="radio-thumbnail"
          /></label
        >

        <input
          type="radio"
          id="imageChoice5"
          name="image"
          value="random"
          class="radio-item"
          on:change={() => {
            imageURL = "https://source.unsplash.com/random/900×700";
          }}
        />
        <label class="label-item" for="imageChoice5"
          ><img
            src="https://res.cloudinary.com/daog6scxm/image/upload/w_100,c_fill,ar_1:1,g_auto,r_max/v1664532278/wallpapers/simone-secci-49uySSA678U-unsplash_vmp6dj.png"
            alt="Random"
            class="radio-thumbnail"
          /></label
        >
      </div>
    </div>
  </section>
</div>

<style>
  :root {
    --image-height: 25vh;
  }
  .image-grid {
    display: grid;
    flex-shrink: 0;
    grid-template-columns: 1fr;
    grid-template-rows: 1fr auto;
    left: 0;
    min-height: 104px;
    position: sticky;
    position: relative;
    z-index: 5;
    width: 100%;
  }

  .image-grid-area {
    grid-area: 1 / 1 / auto / auto;
    width: 100%;
    height: 100%;
  }

  .header-grid-area {
    grid-area: 1 / 1 / auto / auto;
    width: 100%;
    height: 100%;
  }

  img {
    display: block;
    object-fit: cover;
    border-radius: 0px;
    width: 100%;
    height: var(--image-height);
    opacity: 1;
    object-position: center 40%;
  }

  .header-grid {
    width: 800px;
    max-width: 100%;
    min-width: 0px;
    margin: auto;
    display: flex;
    justify-content: center;
    flex-shrink: 0;
  }

  .emoji-container {
    user-select: none;
    transition: background 20ms ease-in 0s;
    display: flex;
    align-items: center;
    justify-content: center;
    height: 78px;
    width: 78px;
    border-radius: 0.25em;
    flex-shrink: 0;
    position: relative;
    z-index: 6;
    margin-left: 12px;
    margin-bottom: 0px;
    margin-top: -42px;
    pointer-events: auto;
  }

  .emoji {
    position: absolute;
    font-size: 48px;
    line-height: 0;
    padding: 20px;
    background-color: #cccccc98;
    border-radius: 12px;
  }

  .radio-button {
    z-index: 1000;
    display: flex;
    flex-direction: row;
    justify-content: end;
    gap: 12px;
    margin-top: -24px;
    padding-right: 12px;
  }

  .radio-item {
    display: none !important;
  }

  .label-item {
    opacity: 0.2;
    border-radius: 50%;
  }

  .label-item:hover {
    opacity: 0.6;
    cursor: pointer;
    border-radius: 50%;
  }

  .radio-item:checked + label {
    opacity: 1;
    border-radius: 50%;
  }

  .radio-thumbnail {
    width: 24px;
    height: 24px;
  }
</style>
