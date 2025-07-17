<script>
  import { onMount } from 'svelte';
  let show = false;

  onMount(() => {
    // Trigger animasi saat komponen mount
    requestAnimationFrame(() => {
      show = true;
    });
  });

  export let links = [
    { label: 'Home', href: '#' },
    { label: 'Features', href: '#features' },
    { label: 'Pricing', href: '#pricing' },
    { label: 'Contact', href: 'https://wa.me/6289675882770' },
  ];
</script>

<header class="navbar {show ? 'show' : ''}">
  <div class="navbar-inner">
    <!-- Logo -->
    <div class="logo">✨ MyBrand</div>

    <!-- Navigation -->
    <nav class="nav-links">
      {#each links as link}
        <a href={link.href}>{link.label}</a>
      {/each}
    </nav>
  </div>
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

  .logo {
    font-size: 1.75rem;
    font-weight: 700;
    color: #111;
  }

  .nav-links {
    display: flex;
    gap: clamp(1rem, 2vw, 2.5rem);
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

  @media (max-width: 768px) {
    .nav-links {
      display: none;
    }
  }
</style>
