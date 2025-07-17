<script>
  export let groom = "LAKI LAKI";
  export let bride = "PEREMPUAN";
  import LandingPage from '../assets/landingpage.jpg';

  let imgRef;

  function handleMouseMove(event) {
    const { left, top, width, height } = imgRef.getBoundingClientRect();
    const x = event.clientX - left;
    const y = event.clientY - top;

    const rotateX = ((y / height) - 0.5) * -20; // lebih tajam
    const rotateY = ((x / width) - 0.5) * 20;

    imgRef.style.transform = `perspective(600px) rotateX(${rotateX}deg) rotateY(${rotateY}deg) scale(1.05)`;
  }

  function resetTransform() {
    imgRef.style.transform = 'rotateX(0deg) rotateY(0deg) scale(1)';
  }
</script>

<section id="card-section" class="card">
  <div class="card-inner">
    <h2 class="change-title">Wedding</h2>
    <h3 class="change-sub">Invitations</h3>

    <div class="photo">
      <img
        src={LandingPage}
        alt="Illustration"
        bind:this={imgRef}
        on:mousemove={handleMouseMove}
        on:mouseleave={resetTransform}
      />
    </div>

    <h2 class="invitation-heading">You're Invited!</h2>

    <p class="invitation-text">
      Dengan penuh sukacita, kami mengundang Bapak/Ibu/Saudara/i untuk hadir dalam acara pernikahan kami:
    </p>

    <h1 class="couple-names">{groom} &amp; {bride}</h1>

    <div class="invitation-detail">
      <p class="date">🗓 Sabtu, 28 Desember 20xx</p>
      <p class="time">🕓 Pukul 16.00 WIB – selesai</p>
      <p class="place">📍 Ballroom Grand Amara, Jakarta</p>
    </div>

    <blockquote class="invitation-poetry">
      "Kasih menyatukan dua hati<br />
      dalam doa dan harapan abadi."<br />
      — Tidak sabar menantikan kehadiran Anda 🌷
    </blockquote>
  </div>
</section>

<style>
  @import url('https://fonts.googleapis.com/css2?family=Great+Vibes&family=Playfair+Display:wght@500;600&family=Inter:wght@400;500&display=swap');

  .card {
    max-width: 640px;
    margin: 3rem auto;
    padding: 3rem 2rem;
    border-radius: 1rem;
    box-shadow: 0 12px 30px rgba(0, 0, 0, 0.05);
    background: linear-gradient(to bottom right, #fdfbf7, #fff);
    text-align: center;
    position: relative;
    font-family: 'Inter', sans-serif;
  }

  .card-inner {
    position: relative;
    z-index: 1;
  }

  .change-title {
    font-family: 'Great Vibes', cursive;
    font-size: 3rem;
    margin: 0;
    color: #d6336c;
  }

  .change-sub {
    font-family: 'Playfair Display', serif;
    text-transform: uppercase;
    font-size: 1rem;
    letter-spacing: 2px;
    margin-bottom: 1.5rem;
    color: #444;
  }

  .photo {
    perspective: 600px;
  }

  .photo img {
    width: 100%;
    height: auto;
    border-radius: 0.75rem;
    margin: 1.5rem 0;
    object-fit: cover;
    max-height: 350px;
    transition: transform 0.15s ease-out;
    transform-style: preserve-3d;
    will-change: transform;
  }

  .invitation-heading {
    font-family: 'Playfair Display', serif;
    font-size: 1.75rem;
    font-weight: 600;
    color: #222;
    margin-bottom: 0.75rem;
  }

  .invitation-text {
    font-size: 1.05rem;
    color: #555;
    line-height: 1.8;
    margin-bottom: 2rem;
  }

  .couple-names {
    font-size: 2.5rem;
    font-weight: 500;
    color: black;
    margin: 1.25rem 0;
  }

  .invitation-detail {
    font-size: 1rem;
    color: #444;
    line-height: 1.8;
    margin-bottom: 2rem;
  }

  .invitation-detail p {
    margin: 0.25rem 0;
  }

  .invitation-poetry {
    font-style: italic;
    font-size: 1rem;
    color: #666;
    margin-top: 1.5rem;
    font-family: 'Playfair Display', serif;
    line-height: 1.6;
  }

  @media (max-width: 640px) {
    .change-title {
      font-size: 2.4rem;
    }

    .couple-names {
      font-size: 2rem;
    }

    .invitation-heading {
      font-size: 1.5rem;
    }

    .invitation-text,
    .invitation-detail,
    .invitation-poetry {
      font-size: 0.95rem;
    }

    .card {
      padding: 2rem 1.5rem;
    }
  }

  @media (min-width: 1024px) {
    .card {
      padding: 4rem 3rem;
      max-width: 700px;
    }

    .change-title {
      font-size: 3.5rem;
    }

    .couple-names {
      font-size: 3rem;
    }
  }
</style>
