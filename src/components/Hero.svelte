<script>
  import LandingPage from '../assets/landingpage.jpg'; // pastikan path benar
</script>

<!-- Section: Hero -->
<section class="hero-section">
  <div class="hero-container">
    
    <!-- Left: Text -->
    <div class="hero-text">
      <h1 class="hero-title">
        Digital Wedding Invitation
      </h1>
      <p class="hero-description">
        Rayakan momen istimewa Anda dengan kartu pernikahan digital yang personal, interaktif, dan mudah dibagikan. Tanpa batasan jarak dan waktu, undangan Anda hadir dalam genggaman para tamu — lengkap dengan informasi, galeri foto, peta lokasi, RSVP, dan fitur menarik lainnya.
      </p>
      <a href="https://wa.me/6289675882770" class="hero-button">
        Contact Us
      </a>
    </div>

    <!-- Right: Image -->
    <div class="hero-image">
      <img
        src={LandingPage}
        alt="Illustration"
      />
    </div>
  </div>
</section>

<style>
  .hero-section {
    background-color: #ef4444;
    color: white;
    border-radius: 1rem;
    padding: 3rem 2rem;
    margin: 0 auto;
    margin-top: 25px;
    margin-bottom: 100px;
    max-width: 1280px;
    }

    /* Hapus radius & padding samping di mode mobile */
    @media (max-width: 640px) {
    .hero-section {
        border-radius: 0;
        padding-left: 1rem;
        padding-right: 1rem;
    }
    }


  .hero-container {
    display: grid;
    grid-template-columns: 1fr;
    gap: 2.5rem;
    align-items: center;
  }

  @media (min-width: 768px) {
    .hero-container {
      grid-template-columns: 1fr 1fr;
      padding: 0 2rem;
    }
  }

  .hero-text {
    max-width: 700px;
    margin: 0 auto;
  }

  .hero-title {
    font-size: clamp(2rem, 5vw, 4rem);
    font-weight: 800;
    line-height: 1.2;
    margin-bottom: 1rem;
  }

  .hero-description {
    font-size: clamp(1rem, 1.5vw, 1.25rem);
    line-height: 1.8;
    margin-bottom: 1.5rem;
  }

  .hero-button {
    display: inline-block;
    background-color: white;
    color: black;
    padding: 0.75rem 1.5rem;
    border-radius: 0.5rem;
    font-weight: 600;
    text-decoration: none;
    box-shadow: 0 2px 4px rgba(0,0,0,0.1);
    transition: background-color 0.3s ease;
  }

  .hero-button:hover {
    background-color: #f3f4f6;
  }

  .hero-image img {
    width: 100%;
    height: clamp(280px, 40vw, 480px);
    object-fit: cover;
    border-radius: 0.75rem;
    box-shadow: 0 4px 10px rgba(0,0,0,0.1);
  }
</style>
