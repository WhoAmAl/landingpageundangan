<script>
  import { onMount } from 'svelte';
  let show = false;
  let mobileNavOpen = false;

  onMount(() => {
    requestAnimationFrame(() => {
      show = true;
    });
  });

  export let links = [
    { label: 'Home', href: '#' },
    { label: 'Card Example', href: '#' },
    { label: 'Contact', href: 'https://wa.me/6289675882770' },
  ];

  function toggleMenu() {
    mobileNavOpen = !mobileNavOpen;
  }
</script>

<header class="navbar {show ? 'show' : ''}">
  <div class="navbar-inner">
    <!-- Logo -->
    <div class="logo">✨ Wedding Day</div>

    <!-- Desktop Navigation -->
    <nav class="nav-links desktop-nav">
      {#each links as link}
        <a
        href={link.href}
        on:click={(e) => {
            if (link.label === 'Card Example') {
            e.preventDefault();
            const section = document.getElementById('card-section');
            if (section) {
                section.scrollIntoView({ behavior: 'smooth' });
                mobileNavOpen = false;
            }
            }
            else if (link.label === 'Home') {
                e.preventDefault();
                window.scrollTo({ top: 0, behavior: 'smooth' });
                mobileNavOpen = false;
            }
        }}
        >
        {link.label}
        </a>
      {/each}
    </nav>

    <!-- Mobile Menu Button -->
    <button class="burger" on:click={toggleMenu} aria-label="Toggle navigation">
      <div class:open={mobileNavOpen}></div>
      <div class:open={mobileNavOpen}></div>
      <div class:open={mobileNavOpen}></div>
    </button>
  </div>

  <!-- Mobile Navigation -->
  {#if mobileNavOpen}
    <nav class="mobile-nav">
      {#each links as link}
        <a href={link.href} on:click={() => (mobileNavOpen = false)}>{link.label}</a>
      {/each}
    </nav>
  {/if}
</header>

<style>
  .navbar {
    position: sticky;
    top: 0;
    width: 100%;
    z-index: 100;
    backdrop-filter: blur(16px);
    background-color: rgba(255, 255, 255, 0.7);
    border-bottom: 1px solid rgba(200, 200, 200, 0.2);
    transform: translateY(-100%);
    opacity: 0;
    transition: transform 0.6s ease, opacity 0.6s ease;
  }

  .navbar.show {
    transform: translateY(0%);
    opacity: 1;
  }

  .navbar-inner {
    max-width: 1600px;
    margin: 0 auto;
    padding: 1rem 1.5rem;
    display: flex;
    align-items: center;
    justify-content: space-between;
  }

  .nav-links {
    display: flex;
    gap: clamp(1rem, 2vw, 2.5rem);
    align-items: center;
    }

  .logo {
    font-size: 1.75rem;
    font-weight: 700;
    color: #111;
  }

  .nav-links a {
    color: #333;
    text-decoration: none;
    font-weight: 500;
    position: relative;
    padding-bottom: 4px;
    transition: color 0.3s ease;
  }

  .nav-links a::after {
    content: "";
    position: absolute;
    height: 2px;
    width: 0%;
    bottom: 0;
    left: 0;
    background-color: #111;
    transition: width 0.3s ease;
  }

  .nav-links a:hover {
    color: #000;
  }

  .nav-links a:hover::after {
    width: 100%;
  }

  /* Burger Button */
  .burger {
    display: none;
    flex-direction: column;
    gap: 4px;
    border: none;
    background: none;
    cursor: pointer;
  }

  .burger div {
    width: 25px;
    height: 3px;
    background-color: #333;
    transition: all 0.3s ease;
  }

  .burger div.open:nth-child(1) {
    transform: rotate(45deg) translate(5px, 5px);
  }

  .burger div.open:nth-child(2) {
    opacity: 0;
  }

  .burger div.open:nth-child(3) {
    transform: rotate(-45deg) translate(5px, -5px);
  }

  /* Mobile Navigation */
  .mobile-nav {
    display: flex;
    flex-direction: column;
    padding: 1rem 1.5rem;
    background-color: white;
    border-bottom: 1px solid #ccc;
  }

  .mobile-nav a {
    padding: 0.75rem 0;
    font-weight: 500;
    color: #333;
    text-decoration: none;
  }

  .mobile-nav a:hover {
    color: #000;
  }

  /* Responsive */
  @media (max-width: 768px) {
    .desktop-nav {
      display: none;
    }

    .burger {
      display: flex;
    }
  }

  @media (min-width: 769px) {
    .mobile-nav {
      display: none;
    }
  }
</style>
