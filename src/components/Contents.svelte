<section class="contents-section">
  <!-- Konten Tengah -->
  <div class="content">
    <h2 class="title">Buat Undangan Pernikahan Online Kalian Disini!</h2>
    <p class="description">
      Tersedia berbagai macam desain undangan yang menarik dan tampil baik di semua perangkat (Smartphone, Tablet bahkan Laptop dan PC).
    </p>
    <a href="#buat" class="cta-button">Buat Undangan ✍️</a>
  </div>
</section>

<style>
  .contents-section {
    margin-top: clamp(5rem, 10vh, 10rem);
    background-color: #ef4444;
    color: white;
    padding: clamp(3rem, 8vw, 6rem) 1.5rem;
    text-align: center;
    overflow: hidden;
  }

  .content {
    max-width: 900px;
    margin: 0 auto;
    z-index: 1;
    position: relative;
  }

  .title {
    font-size: clamp(1.75rem, 4vw, 2.5rem);
    font-weight: 700;
    margin-bottom: 1rem;
  }

  .description {
    font-size: clamp(1rem, 1.5vw, 1.25rem);
    line-height: 1.8;
    margin-bottom: 2rem;
    color: #d6e1e2;
  }

  .cta-button {
    display: inline-block;
    padding: 0.75rem 1.5rem;
    background-color: #2f80ed;
    color: white;
    text-decoration: none;
    font-weight: 600;
    border-radius: 8px;
    transition: background-color 0.3s ease;
  }

  .cta-button:hover {
    background-color: #1366d6;
  }

  .leaf {
    position: absolute;
    width: 100px;
    z-index: 0;
    opacity: 0.7;
  }

  .leaf-left {
    top: 0;
    left: 0;
    transform: rotate(-10deg);
  }

  .leaf-right {
    bottom: 0;
    right: 0;
    transform: rotate(10deg);
  }

  @media (max-width: 640px) {
    .leaf {
      width: 60px;
    }
  }
</style>
