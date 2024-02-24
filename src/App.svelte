<script>
  import { onMount } from "svelte";
  import Header from "./components/Header.svelte";
  import Footer from "./components/Footer.svelte";

  // State to control which section is open in the accordion
  let openSection = null;

  // Toggle visibility of accordion sections
  function toggleSection(section) {
    openSection = openSection === section ? null : section;
  }

  // Setup draggable slider functionality on mount
  onMount(() => {
    const slider = document.querySelector(".horizontal-scroll-container");
    if (!slider) return; // Exit if slider not found to avoid errors

    let isDown = false;
    let startX;
    let scrollLeft;

    // Mouse down event to initiate dragging
    slider.addEventListener("mousedown", (e) => {
      isDown = true;
      slider.classList.add("active"); // Visual feedback for dragging
      startX = e.pageX - slider.offsetLeft; // Starting X position
      scrollLeft = slider.scrollLeft; // Starting scroll position
    });

    // Clean up drag state on mouse leave and up
    const stopScroll = () => {
      isDown = false;
      slider.classList.remove("active");
    };
    slider.addEventListener("mouseleave", stopScroll);
    slider.addEventListener("mouseup", stopScroll);

    // Mouse move event to handle dragging
    slider.addEventListener("mousemove", (e) => {
      if (!isDown) return; // Only drag if mouse is down
      e.preventDefault(); // Prevent default selection behavior
      const x = e.pageX - slider.offsetLeft; // Current X position
      const walk = (x - startX) * 1; // Calculate drag distance
      slider.scrollLeft = scrollLeft - walk; // Scroll the slider
    });
  });
</script>

<Header />

<main>
  <div class="bg-hero"></div>

  <!-- Hero Section -->
  <section class="hero" aria-label="Introduction">
    <div class="hero-section-1">
      <h1 class="mainHeading" id="mainHeading">
        <span class="heading-title">Svelte One Pager</span><br />
        Transform Your Web with SvelteOnePager
      </h1>
      <p class="heading-subtitle">
        Build, customize, and deploy websites easily with Svelte and Firebase
        integration.
      </p>
      <a href="#about-us" class="cta">About Us →</a>
    </div>
    <div class="hero-section-2">
      <img
        src="/img/bg-hero.svg"
        alt="Illustrative background showing SvelteOnePager's capabilities"
        class="hero-image animate"
      />
    </div>
  </section>

  <!-- Services Section -->
  <section id="services" aria-label="Services">
    <div class="info-section">
      <div class="info-explain">
        <h2>Services: Choose clarity, choose SvelteOnePager.</h2>
        <p>Example Services SvelteOnePager offers.</p>
      </div>
      <div class="scroll-wrapper">
        <div class="horizontal-scroll-container" role="list">
          <div class="service">
            <img src="/img/check.svg" alt="alt-text-icon" class="icon" />
            <h3>Custom Website Design</h3>
          </div>
          <div class="service">
            <img src="/img/check.svg" alt="alt-text-icon" class="icon" />
            <h3>Real-time Development</h3>
          </div>
          <div class="service">
            <img src="/img/check.svg" alt="alt-text-icon" class="icon" />
            <h3>Personal Solutions</h3>
          </div>
          <div class="service">
            <img src="/img/check.svg" alt="alt-text-icon" class="icon" />
            <h3>Integration Consultancy</h3>
          </div>
          <div class="service">
            <img src="/img/check.svg" alt="alt-text-icon" class="icon" />
            <h3>SEO Optimization</h3>
          </div>
        </div>
      </div>
      <div id="about-us"></div>
    </div>
  </section>

  <!-- About Us Section -->
  <section id="about-us" class="about-us">
    <h3>About Us</h3>
    <p>
      Lorem ipsum dolor sit amet, consectetur adipiscing elit. Integer eget
      volutpat purus. Vestibulum imperdiet vehicula elementum. Pellentesque
      accumsan eros vel ornare cursus. Maecenas efficitur diam et posuere
      finibus. Proin a tempus justo. Proin a lacus lacus. Praesent auctor risus
      in imperdiet posuere. Curabitur vel maximus nunc. Suspendisse dictum
      varius sagittis. Integer nec aliquet purus, quis elementum velit. Mauris
      mauris velit, lobortis at tortor nec, tempor accumsan felis. Proin id orci
      fringilla, rhoncus tortor quis, porta nisl.
    </p>
    <p>
      Sed maximus nibh nibh, eu lacinia eros gravida quis. Nam sit amet nisl
      enim. Praesent commodo ante vel tellus luctus bibendum. Morbi vel dui a
      magna viverra malesuada eget vitae sem. Aliquam placerat rhoncus sem. Nam
      nec est ac ipsum gravida malesuada pellentesque quis eros. Maecenas
      imperdiet a leo at ornare. Vestibulum ante ipsum primis in faucibus orci
      luctus et ultrices posuere cubilia curae; Nam vehicula egestas nisi, ut
      facilisis ante lacinia sit amet. Aliquam purus ante, sagittis sed eleifend
      id, vehicula ac ante. Fusce facilisis placerat gravida. Aliquam erat
      volutpat.
    </p>
    <p>
      Sed maximus nibh nibh, eu lacinia eros gravida quis. Nam sit amet nisl
      enim. Praesent commodo ante vel tellus luctus bibendum. Morbi vel dui a
      magna viverra malesuada eget vitae sem. Aliquam placerat rhoncus sem.
    </p>
  </section>

  <!-- Pricing Section -->
  <section id="pricing" class="pricing-section">
    <div class="pricing-content">
      <h3>Simple, Predictable Pricing</h3>
      <p>
        Lorem ipsum dolor sit amet, consectetur adipiscing elit. Integer eget
        volutpat purus. Vestibulum imperdiet vehicula elementum. Pellentesque
        accumsan eros vel ornare cursus.
      </p>
    </div>
    <div class="pricing-plans">
      <!-- Basic Plan -->
      <div class="plan">
        <div class="price">
          <h4>Basic</h4>
          <p class="price-info">Starting at €67/month</p>
        </div>

        <ul class="features">
          <li>Custom Website Design</li>
          <li>Responsive Layouts</li>
          <li>Svelte & Firebase Setup</li>
          <li>Up to 10 Pages</li>
        </ul>
      </div>

      <!-- Plus Plan -->
      <div class="plan">
        <div class="price">
          <h4>Plus</h4>
          <p class="price-info">Starting at €99/month</p>
        </div>

        <ul class="features">
          <li>Everything in Basic</li>
          <li>Advanced SEO Optimization</li>
          <li>Real-time Data Integration</li>
          <li>Custom Components</li>
          <li>Up to 20 Pages</li>
        </ul>
      </div>

      <!-- Premium Plan -->
      <div class="plan">
        <div class="price">
          <h4>Premium</h4>
          <p class="price-info">Contact for Pricing</p>
        </div>

        <ul class="features">
          <li>Everything in Plus</li>
          <li>E-commerce Integration</li>
          <li>High Performance Optimizations</li>
          <li>Unlimited Pages</li>
          <li>Personalized Support</li>
        </ul>
      </div>
    </div>
  </section>

  <!-- Accordion Section -->
  <section id="faq" class="accordion-section">
    <h3>FAQ</h3>
    <div class="toggle">
      <!-- svelte-ignore a11y-click-events-have-key-events -->
      <div class="header" on:click={() => toggleSection("section1")}>
        Lorem ipsum dolor sit amet, consectetur adipiscing elit?
        <img
          src="/img/icon-down-2.svg"
          alt="Arrow accordion 1"
          class:rotate={openSection === "section1"}
        />
      </div>
      {#if openSection === "section1"}
        <div class="content">
          Lorem ipsum dolor sit amet, consectetur adipiscing elit. Integer eget
          volutpat purus. Vestibulum imperdiet vehicula elementum. Pellentesque
          accumsan eros vel ornare cursus. Maecenas efficitur diam et posuere
          finibus. Proin a tempus justo.
        </div>
      {/if}
    </div>
    <div class="toggle">
      <!-- svelte-ignore a11y-click-events-have-key-events -->
      <div class="header" on:click={() => toggleSection("section2")}>
        Lorem ipsum dolor sit amet?
        <img
          src="/img/icon-down-2.svg"
          alt="Arrow accordion 2"
          class:rotate={openSection === "section2"}
        />
      </div>
      {#if openSection === "section2"}
        <div class="content">
          Lorem ipsum dolor sit amet, consectetur adipiscing elit. Integer eget
          volutpat purus. Vestibulum imperdiet vehicula elementum. Pellentesque
          accumsan eros vel ornare cursus. Maecenas efficitur diam et posuere
          finibus. Proin a tempus justo.
        </div>
      {/if}
    </div>
    <div class="toggle">
      <!-- svelte-ignore a11y-click-events-have-key-events -->
      <div class="header" on:click={() => toggleSection("section3")}>
        Lorem ipsum dolor sit amet, consectetur adipiscing elit?
        <img
          src="/img/icon-down-2.svg"
          alt="Arrow accordion 3"
          class:rotate={openSection === "section3"}
        />
      </div>
      {#if openSection === "section3"}
        <div class="content">
          Lorem ipsum dolor sit amet, consectetur adipiscing elit. Integer eget
          volutpat purus. Vestibulum imperdiet vehicula elementum. Pellentesque
          accumsan eros vel ornare cursus. Maecenas efficitur diam et posuere
          finibus. Proin a tempus justo.
        </div>
      {/if}
    </div>
  </section>

  <!-- Additional Section -->
  <section class="additional-content">
    <p>
      Lorem ipsum dolor sit amet, consectetur adipiscing elit. Integer eget
      volutpat purus. Vestibulum imperdiet vehicula elementum. Pellentesque
      accumsan eros vel ornare cursus. Maecenas efficitur diam et posuere
      finibus. Proin a tempus justo. Proin a lacus lacus. Praesent auctor risus
      in imperdiet posuere. Curabitur vel maximus nunc. Suspendisse dictum
      varius sagittis. Integer nec aliquet purus, quis elementum velit. Mauris
      mauris velit, lobortis at tortor nec, tempor accumsan felis. Proin id orci
      fringilla, rhoncus tortor quis, porta nisl.
    </p>
    <p>
      Sed maximus nibh nibh, eu lacinia eros gravida quis. Nam sit amet nisl
      enim. Praesent commodo ante vel tellus luctus bibendum. Morbi vel dui a
      magna viverra malesuada eget vitae sem. Aliquam placerat rhoncus sem.
    </p>
  </section>

  <!-- Contact Section -->
  <section id="contact" class="contact">
    <h3>Contact us</h3>
    <p>
      Lorem ipsum dolor sit amet, consectetur adipiscing elit. Integer eget
      volutpat purus. Vestibulum imperdiet vehicula elementum. Pellentesque
      accumsan eros vel ornare cursus. Maecenas efficitur diam et posuere
      finibus. Proin a tempus justo.
    </p>
    <a href="tel:0031612345678">Call us today →</a>
  </section>
</main>

<Footer />

<style>
  :root {
    --primary-color: #b0ffa0;
    --secondary-color: #f4f4f4;
    --color-black: #000;
    --color-white: #fff;
  }

  :target {
    padding-top: 120px;
    margin-top: -120px;
  }

  main {
    padding: 1em;
    margin: 0 auto;
  }

  .bg-hero {
    background-color: var(--primary-color);
    width: 100%;
    height: 700px;
    position: absolute;
    top: -20px;
    left: 0;
    z-index: -1;
  }

  .hero {
    display: flex;
    justify-content: space-between;
    gap: 150px;
    margin-top: 160px;
  }

  .hero-section-2 {
    align-content: center;
    display: flex;
  }

  .hero-image {
    width: 400px;
    max-width: 600px;
  }

  .cta {
    font-size: 20px;
    margin-top: 10px;
    display: inline-block;
    border: 2px solid #000;
    border-radius: 20px;
    padding: 6px 20px;
  }

  .mainHeading {
    font-size: 50px;
    font-weight: 600;
    color: var(--color-black);
  }

  .heading-title {
    font-size: 22px;
    font-weight: 300;
  }

  .heading-subtitle {
    font-weight: 300;
    font-size: 22px;
    color: var(--color-black);
  }

  .icon {
    width: 35px;
    margin-bottom: 5px;
    align-items: center;
  }

  .horizontal-scroll-container {
    scrollbar-width: none;
  }

  .horizontal-scroll-container::-webkit-scrollbar {
    display: none;
  }

  .horizontal-scroll-container {
    margin: 0 15px;
    display: flex;
    gap: 30px;
    flex: 1;
    overflow-y: hidden;
    transition: all 0.2s;
    transform: scale(0.98);
    will-change: transform;
    user-select: none;
    cursor: pointer;
  }

  .scroll-wrapper {
    position: relative;
    overflow: hidden;
  }

  .info-section {
    display: flex;
    align-items: center;
    margin-top: 60px;
    background-color: var(--color-white);
    padding: 30px;
    border-radius: 20px;
    box-shadow: 10px 10px 20px rgba(25, 51, 94, 0.1);
  }

  .info-explain {
    flex: 0 0 38%;
    margin-right: 40px;
  }

  .info-explain h2 {
    font-size: 25px;
  }

  .service {
    display: flex;
    flex-direction: column;
    align-items: center;
    width: fit-content;
    background-color: var(--secondary-color);
    padding: 30px 15px;
    border-radius: 15px;
    text-align: center;
    height: 90px;
    min-width: 230px;
  }

  .service h3 {
    margin: 5px;
    font-size: 20px;
  }

  .pricing-plans {
    display: flex;
    gap: 30px;
  }

  .pricing-plans ul {
    list-style: none;
    padding: 0;
  }

  .pricing-plans ul li {
    margin: 10px 0;
    font-size: 18px;
  }

  .pricing-plans ul li::before {
    content: "✓";
    color: #04c21d;
    display: inline-block;
    width: 1em;
    margin-left: 0em;
    padding-right: 10px;
  }

  .plan {
    flex: 1;
    background-color: var(--secondary-color);
    padding: 25px;
    border-radius: 20px;
  }

  .plan h4 {
    font-size: 21px;
    margin: 0;
    display: block;
  }

  .price {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 30px;
  }

  .price-info {
    background-color: var(--color-black);
    color: var(--color-white);
    padding: 8px 10px;
    margin: 0;
    border-radius: 10px;
    font-size: 17px !important;
  }

  .about-us,
  .pricing-content,
  .accordion-section,
  .additional-content,
  .contact {
    max-width: 800px;
    margin: 70px auto;
  }

  .accordion-section .toggle {
    background-color: var(--color-white);
    border-radius: 10px;
    margin-bottom: 12px;
    border: 1px solid #d1deee;
  }

  .accordion-section .toggle .header {
    text-align: left;
    padding: 15px;
    font-size: 18px;
    font-weight: 600;
    display: flex;
    justify-content: space-between;
    align-items: center;
    cursor: pointer;
  }

  .accordion-section .toggle .header img {
    width: 15px;
    height: 15px;
    transition: transform 0.3s ease;
    transform: rotate(-90deg);
  }

  .accordion-section .toggle .header img.rotate {
    transform: rotate(0deg);
  }

  .accordion-section .toggle .content {
    padding: 15px;
    border-top: 1px solid #d1deee;
  }

  .animate {
    animation: AnimatieKeyframe 3s ease-in-out infinite;
  }

  @keyframes AnimatieKeyframe {
    0%,
    100% {
      transform: rotate(0deg);
    }
    50% {
      transform: translateX(10px) translateY(10px) translateZ(0) rotateZ(0deg);
    }
  }

  .contact {
    padding: 30px;
    background-color: var(--color-black);
    color: var(--color-white);
    border-radius: 20px;
  }

  .contact a {
    color: #000;
    background-color: var(--color-white);
    padding: 10px 20px;
    border-radius: 10px;
    text-decoration: none;
    font-weight: 600;
    display: inline-block;
    margin-top: 20px;
  }

  @media only screen and (max-width: 1000px) and (min-width: 470px) {
    .bg-hero {
      height: 520px !important;
    }
  }

  @media (max-width: 1000px) {
    :target {
      padding-top: 0px;
      margin-top: 0px;
    }

    main {
      max-width: 100%;
      width: 100%;
      padding: 0;
    }
    .bg-hero {
      height: 675px;
    }
    .hero {
      display: block;
    }
    .hero-section-2 {
      justify-content: end;
      margin: -40px 0 30px 0;
    }
    .hero-image {
      width: 150px;
    }
    .mainHeading {
      margin: 0;
      font-size: 40px;
    }
    .heading-subtitle {
      font-size: 22px;
    }
    .about-us h3 {
      font-size: 25px;
    }
    .info-section {
      border-radius: 0;
      padding: 0;
      margin-top: 0px;
      background-color: unset;
      box-shadow: unset;
    }
    .accordion-section .toggle .header {
      font-size: 17px;
    }
    .accordion-section h3 {
      font-size: 25px;
    }
    .pricing-section {
      flex-direction: column;
    }
    .pricing-plans {
      margin-right: 0;
      margin-bottom: 30px;
      flex-direction: column;
    }
    .pricing-plans ul li {
      font-size: 17px;
    }
    .info-section {
      flex-direction: column;
    }
    .info-explain {
      margin-right: 0;
    }
    .service {
      padding: 30px 10px;
    }
    .scroll-wrapper {
      width: 107%;
    }
    .horizontal-scroll-container {
      gap: 15px;
    }
    .contact {
      width: 85%;
      padding: 25px;
    }
    .contact h3 {
      margin-top: 0;
    }
  }
</style>
