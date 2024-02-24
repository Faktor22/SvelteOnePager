<script>
  const currentYear = new Date().getFullYear();
</script>

<footer class="site-footer">
  <div class="footer-container">
    <nav class="footer-nav">
      <a href="/" class="footer-logo">
        <img
          src="/img/icon.svg"
          alt="SvelteOnePager logo"
          class="footer-icon"
        />
      </a>
      <a href="/doc/privacy.pdf" target="_blank" rel="noopener noreferrer"
        >Privacy</a
      >
      <a href="/doc/terms.pdf" target="_blank" rel="noopener noreferrer"
        >Terms and Conditions</a
      >
    </nav>
    <div class="footer-version">
      © <span id="currentYear">{currentYear}</span> |
      <a
        href="https://github.com/Faktor22/SvelteOnePager"
        target="_blank"
        rel="noopener noreferrer"
        aria-label="Visit GitHub repository">GitHub Repository</a
      >
    </div>
  </div>
</footer>

<style>
  .site-footer {
    color: #000;
    padding: 10px;
    display: flex;
    justify-content: center;
    align-items: center;
    flex-wrap: wrap;
  }

  .footer-container {
    display: flex;
    justify-content: space-between;
    align-items: center;
    width: 100%;
    max-width: 1280px;
  }

  .footer-logo img {
    width: 30px; /* Adjust based on actual logo size */
  }

  .footer-nav {
    display: flex;
    align-items: center;
  }

  .footer-nav a {
    font-size: 14px;
    margin: 0 10px;
    text-decoration: none;
    color: inherit;
  }

  .footer-version {
    background-color: #000;
    color: #fff;
    padding: 5px 10px;
    border-radius: 5px;
    font-size: 14px;
  }

  .footer-version a {
    color: #fff;
    text-decoration: none;
  }

  @media (max-width: 1000px) {
    .footer-container {
      flex-direction: column;
      text-align: center;
    }

    .footer-nav {
      margin-top: 20px;
    }
  }

  @media (max-width: 650px) {
    .footer-nav a {
      display: block; /* Stack links vertically on smaller screens */
      margin: 5px 0; /* Adjust margin for stacked links */
    }
  }
</style>
