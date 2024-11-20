<template>
  <section id="AboutMe" class="about-section">
    <div class="about-header">
      <h1>Hi, I'm Kevin Sheehan</h1>
      <hr class="divider" />
    </div>
    <div class="about-content">
      <p>
        Hello, my name is Kevin. I am currently pursuing a post-graduate certificate in Cloud Computing at Durham College,
        where I am further developing my technical skills in emerging cloud technologies. I graduated from Trent University
        with a Bachelor of Science (Honours) in Computer Science and a Minor in Mathematics. During my time at Trent, I completed four
        semesters of co-op work experience, which helped me gain hands-on experience across various aspects of software development.
        Outside of academics, I am a pianist and currently at Level 10 with the Royal Conservatory of Music.
      </p>
    </div>
  </section>
</template>

<style scoped>

.about-section {

  background: linear-gradient(135deg, #1f1f2e, #28293d);
  padding: 60px 40px;
  max-width: 900px;
  margin: 150px auto;
  border-radius: 12px;
  box-shadow: 0 8px 20px rgba(0, 0, 0, 0.3);
  color: #f5f5f5;
  scroll-margin-top: 100px; /* Ensures the component is not flush with the top */
}

.about-header {
  text-align: center;
  margin-bottom: 20px;
}

.about-header h1 {
  font-family: 'Montserrat', sans-serif;
  font-size: 2.5rem;
  font-weight: 800;
  color: var(--primary-color);
  margin: 0;
  text-shadow: 1px 2px 4px rgba(0, 0, 0, 0.2);
}

.divider {
  width: 50px;
  height: 4px;
  background-color: var(--primary-color);
  margin: 15px auto;
  border: none;
}

.about-content p {
  font-family: 'Roboto', serif;
  font-size: 1.1rem;
  line-height: 1.75;
  color: #dcdcdc;
  text-align: justify;
  background: rgba(255, 255, 255, 0.08);
  padding: 20px;
  border-radius: 8px;
}

@media (max-width: 768px) {
  .about-section {
    padding: 40px 20px;
  }

  .about-header h1 {
    font-size: 2rem;
  }

  .about-content p {
    font-size: 1rem;
  }
}
</style>
