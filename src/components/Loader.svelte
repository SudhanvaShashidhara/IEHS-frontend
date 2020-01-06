<style>
  .spinner {
    width: 5rem;
    height: 5rem;
    border-radius: 50%;
    background-color: transparent;
    position: relative;
    margin: 2rem auto;
  }

  .spinner::after,
  .spinner::before {
    content: "";
    display: block;
    border-radius: 50%;
    width: 5rem;
    height: 5rem;
  }

  .spinner::after {
    background-color: #f4f4f4;
    position: absolute;
    top: 0;
    left: 0;
    border: 4px solid transparent;
    border-top-color: var(--main-color-variant);
    border-bottom-color: var(--main-color-variant);
    animation: spinny 2s linear infinite;
  }

  @keyframes spinny {
    0% {
      transform: rotate(0deg) scale(1);
      background-color: var(--main-secondary-variant);
      border-top-color: var(--main-color-variant);
      border-bottom-color: var(--main-color-variant);
    }
    50% {
      transform: rotate(180deg) scale(1.2);
      background-color: var(--main-color-variant);
      border-top-color: var(--main-secondary-variant);
      border-bottom-color: var(--main-secondary-variant);
    }
    100% {
      transform: rotate(360deg) scale(1);
      background-color: var(--main-secondary-variant);
      border-top-color: var(--main-color-variant);
      border-bottom-color: var(--main-color-variant);
    }
  }
</style>

<div class="spinner" />
