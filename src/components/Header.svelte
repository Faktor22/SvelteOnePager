<header class="site-header">
  <div class="header-container">
    <!-- Logo linked to the top of the page or home -->
    <a href="#mainHeading" class="logo-link">
      <img
        src="../img/logo-svelte-one-pager.svg"
        alt="Logo One Pager Svelte"
        class="logo"
      />
    </a>

    <!-- Navigation Links -->
    <nav class="site-navigation">
      <ul class="nav-list">
        <li><a href="#services" class="nav-link">Services</a></li>
        <li><a href="#about-us" class="nav-link">About us</a></li>
        <li><a href="#pricing" class="nav-link">Pricing</a></li>
        <li><a href="#faq" class="nav-link">FAQ</a></li>
        <!-- More list items as needed -->
      </ul>

      <!-- Call Action -->
      <a href="tel:0031612345678" class="phone-action">
        <img
          src="../img/icon-phone-white.svg"
          alt="Call us"
          class="phone-icon"
        />
      </a>
    </nav>
  </div>
</header>

<style>
  .header-container {
    display: flex;
    justify-content: space-between;
    align-items: center;
    transition: all 0.2s ease-in-out;
    box-shadow: none;
    margin: 1rem auto;
    border-width: 1px;
    border-style: solid;
    border-radius: 20px;
    border-color: #e4e4e4;
    background: #fff;
    width: 1280px;
    max-width: 1280px;
    position: fixed;
    left: 50%;
    transform: translateX(-50%);
    z-index: 2;
  }

  .logo {
    width: 215px;
    padding: 1rem;
  }

  .nav-list {
    list-style: none;
    display: flex;
    margin-right: 20px;
  }

  .nav-list li {
    margin: 0 10px;
  }

  .site-navigation {
    display: flex;
    align-items: center;
    padding: 1rem 1.3rem;
  }

  .nav-link {
    margin-right: 1rem;
    font-size: 18px;
    color: #000;
  }

  .phone-action img {
    background-color: #000;
    width: 35px;
    padding: 7px;
    border-radius: 25px;
  }

  @media (max-width: 1000px) {
    .header-container {
      width: 100%;
      max-width: 100%;
      position: fixed;
      left: 0;
      transform: none;
      margin-bottom: 50px !important;
      border-radius: 0;
      top: -17px;
    }
    .logo {
      width: 170px;
      padding: 1rem 25px;
    }
    .nav-link,
    .nav-list {
      display: none;
    }
    .phone-action img {
      width: 30px;
    }
  }
</style>
