<template>
  <section
    id="HeaderUSWDSBanner"
    class="usa-banner"
    aria-label="Official government website"
  >
    <div class="usa-accordion">
      <header class="usa-banner__header">
        <div class="usa-banner__inner">
          <div class="grid-col-auto">
            <img
              class="usa-banner__header-flag"
              src="~uswds/dist/img/us_flag_small.png"
              alt="U.S. flag"
            >
          </div>
          <div class="grid-col-fill tablet:grid-col-auto">
            <p class="usa-banner__header-text">
              An official website of the United States government
            </p>
            <p
              class="usa-banner__header-action"
              aria-hidden="true"
            >
              Here’s how you know
            </p>
          </div>
          <button
            class="usa-accordion__button usa-banner__button"
            aria-expanded="false"
            aria-controls="gov-banner"
          >
            <span class="usa-banner__button-text">Here’s how you know</span>
          </button>
        </div>
      </header>
      <div
        id="gov-banner"
        class="usa-banner__content usa-accordion__content"
      >
        <div class="grid-row grid-gap-lg">
          <div class="usa-banner__guidance tablet:grid-col-6">
            <iconDot
              class="usa-banner__icon usa-media-block__img"
              role="img"
              alt="Dot gov"
            />
            <div class="usa-media-block__body">
              <p>
                <strong>
                  Official websites use .gov
                </strong>
                <br>
                A <strong>.gov</strong> website belongs to an official government organization in the United States.
              </p>
            </div>
          </div>
          <div class="usa-banner__guidance tablet:grid-col-6">
            <iconHTTPS
              class="usa-banner__icon usa-media-block__img"
              role="img"
              alt="Https"
            />
            <div class="usa-media-block__body">
              <p>
                <strong>
                  Secure .gov websites use HTTPS
                </strong>
                <br>
                A <strong>lock</strong> (
                <span class="icon-lock"><svg
                  xmlns="http://www.w3.org/2000/svg"
                  width="52"
                  height="64"
                  viewBox="0 0 52 64"
                  class="usa-banner__lock-image"
                  role="img"
                  aria-labelledby="banner-lock-title banner-lock-description"
                ><title id="banner-lock-title">Lock</title><desc id="banner-lock-description">A locked padlock</desc><path
                  fill="#000000"
                  fill-rule="evenodd"
                  d="M26 0c10.493 0 19 8.507 19 19v9h3a4 4 0 0 1 4 4v28a4 4 0 0 1-4 4H4a4 4 0 0 1-4-4V32a4 4 0 0 1 4-4h3v-9C7 8.507 15.507 0 26 0zm0 8c-5.979 0-10.843 4.77-10.996 10.712L15 19v9h22v-9c0-6.075-4.925-11-11-11z"
                /></svg></span>
                ) or <strong>https://</strong> means you’ve safely connected to the .gov website. Share sensitive information only on official, secure websites.
              </p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
    import iconDot from '../../node_modules/uswds/dist/img/icon-dot-gov.svg';
    import iconHTTPS from '../../node_modules/uswds/dist/img/icon-https.svg';
    export default {
        name: 'HeaderUSWDSBanner',
        components: {
            iconDot,
            iconHTTPS
        },
        mounted() {
            // This is a fix for the weird USWDS glitch that causes the official united states banner pop and then close as the page loads
            const bannerElement = document.querySelector('#gov-banner');
            bannerElement.setAttribute('hidden', '""');
        }
    }
</script>

<style scoped lang="scss">
  @import '~uswds/dist/css/uswds.css';
  $nearBlack: #212222;
  .usa-banner {
    background-color: $nearBlack;
  }
  .usa-banner p, text {
    color: #F0F0F0;
    padding: 0;
  }
  .usa-banner__inner {
    margin-left: 10px;
    padding-left: 5px;
  }
  .usa-banner__button {
    color: #78B4E8;
  }
  .usa-banner__button::after {
    content: none;
  }
  .usa-banner__button:hover {
    color: #A2CCF1;
  }
  .usa-banner__button::after:hover {
    background-color: #A2CCF1;
  }
  .usa-banner__button::after:hover [aria-expanded="true"] {
    content: none;
  }
  .usa-banner__button[aria-expanded=true]::after{
    content: none;
  }
  .usa-banner__button[aria-expanded=true]::after:hover{
    content: none;
  }
  .usa-banner__button[aria-expanded=true]:hover::after {
    content: none;
  }

  #HeaderUSWDSBanner {
    *:focus {
      border: none;
      outline: none;
    }
    .usa-banner__icon {
      width: 4rem;
    }
  }
</style>
