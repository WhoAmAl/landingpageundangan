<script>
    export let groom = "LAKI LAKI";
    export let bride = "PEREMPUAN";
    import LandingPage from '../assets/landingpage.jpg'; // pastikan path benar
</script>

<section class="card">
  <div class="card-inner">

    <h2 class="change-title">Change</h2>
    <h3 class="change-sub">of Plans</h3>

    <div class="photo">
      <img
        src={LandingPage}
        alt="Illustration"
      />
    </div>

    <p class="message">
      Kepada Keluarga dan Teman-Teman,<br />
      Karena ada beberpa hal yang tidak terduga, kami harus mengubah rencana pernikahan
    </p>

    <h2 class="names">{groom} &amp; {bride}</h2>

    <p class="status">telah ditunda</p>

    <p class="apology">
      Kami mohon maaf apabila<br />
      terjadi ketidaknyamanan atas perubahan ini.
    </p>

    <p class="note">
      Ditunda sampai<br />
      <strong>00 Desember 20xx</strong>
    </p>

  </div>
</section>

<style>
  @import url('https://fonts.googleapis.com/css2?family=Great+Vibes&family=Inter:wght@400;600&family=Playfair+Display:wght@500&display=swap');

  .card {
    max-width: 480px;
    margin: 2rem auto;
    padding: 2rem 1.5rem;
    border-radius: 1rem;
    box-shadow: 0 10px 20px rgba(0,0,0,0.05);
    font-family: 'Inter', sans-serif;
    text-align: center;
    position: relative;
    overflow: hidden;
    background-image: linear-gradient(180deg, #fdfdfd 0%, #fdfdfd 100%);
  }

  .card::before,
  .card::after {
    content: "";
    position: absolute;
    width: 120px;
    height: 120px;
    background: url('/assets/leaves-corner-top.png') no-repeat center;
    background-size: contain;
    z-index: 0;
  }

  .card::before {
    top: 0;
    left: 0;
  }

  .card::after {
    bottom: 0;
    right: 0;
    transform: rotate(180deg);
  }

  .card-inner {
    position: relative;
    z-index: 1;
  }

  .change-title {
    font-family: 'Great Vibes', cursive;
    font-size: 2.5rem;
    margin: 0;
    line-height: 1;
  }

  .change-sub {
    font-family: 'Playfair Display', serif;
    text-transform: uppercase;
    font-size: 0.9rem;
    letter-spacing: 1.5px;
    margin: 0 0 1rem;
  }

  .photo img {
    width: 100%;
    height: auto;
    border-radius: 0.5rem;
    margin: 1rem 0;
  }

  .message,
  .status,
  .apology,
  .note {
    font-size: 0.95rem;
    color: #444;
    margin: 0.75rem 0;
  }

  .names {
    font-family: 'Great Vibes', cursive;
    font-size: 2rem;
    margin: 0.5rem 0;
    color: #222;
  }

  .status {
    text-transform: uppercase;
    font-weight: 600;
    font-size: 1rem;
    margin-top: 0.75rem;
  }

  .note strong {
    font-weight: 600;
    color: #000;
  }

  /* Tablet breakpoint */
  @media (min-width: 640px) {
    .card {
      padding: 3rem 2rem;
    }

    .names {
      font-size: 2.5rem;
    }

    .change-title {
      font-size: 3rem;
    }

    .message,
    .apology,
    .note {
      font-size: 1rem;
    }
  }

  /* Laptop breakpoint */
  @media (min-width: 1024px) {
    .card {
      max-width: 600px;
      padding: 4rem 3rem;
    }

    .change-title {
      font-size: 3.25rem;
    }

    .names {
      font-size: 3rem;
    }

    .status {
      font-size: 1.1rem;
    }

    .photo img {
      max-height: 360px;
      object-fit: cover;
    }
  }
</style>
