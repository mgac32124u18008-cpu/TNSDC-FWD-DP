<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1" />
<title>Mental Health Awareness Portfolio</title>
<style>
  body {
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    margin: 0;
    padding: 0;
    background: #e3f2fd;
    color: #212121;
  }
  header {
    background: #0288d1;
    color: white;
    padding: 1.5rem;
    text-align: center;
    box-shadow: 0 2px 4px rgba(0,0,0,0.1);
  }
  header h1 {
    margin: 0;
    font-weight: 700;
    font-size: 2.5rem;
  }
  main {
    max-width: 900px;
    margin: 2rem auto;
    padding: 0 1rem;
  }
  section {
    background: white;
    padding: 1.5rem 2rem;
    border-radius: 8px;
    margin-bottom: 2rem;
    box-shadow: 0 4px 8px rgb(0 0 0 / 0.1);
  }
  section h2 {
    color: #01579b;
    margin-top: 0;
  }
  .tips {
    list-style-type: none;
    padding-left: 0;
  }
  .tips li {
    background: #b3e5fc;
    margin: 0.4rem 0;
    padding: 0.5rem 1rem;
    border-radius: 4px;
    cursor: pointer;
    transition: background-color 0.3s ease;
  }
  .tips li:hover {
    background-color: #81d4fa;
  }
  .tip-detail {
    margin-top: 1rem;
    font-style: italic;
    color: #0277bd;
  }
  form {
    display: flex;
    flex-direction: column;
  }
  label {
    margin-top: 1rem;
    font-weight: 600;
  }
  input, textarea {
    padding: 0.6rem;
    font-size: 1rem;
    border: 1px solid #ccc;
    border-radius: 4px;
    resize: vertical;
  }
  button {
    margin-top: 1.5rem;
    padding: 0.8rem 1.2rem;
    font-size: 1.1rem;
    border: none;
    border-radius: 4px;
    background-color: #0288d1;
    color: white;
    cursor: pointer;
    transition: background-color 0.3s ease;
  }
  button:hover {
    background-color: #0277bd;
  }
  footer {
    text-align: center;
    padding: 1rem;
    color: #555;
    background: #f0f0f0;
    margin-top: 3rem;
  }
</style>
</head>
<body>

<header>
  <h1>Mental Health Awareness Digital Portfolio</h1>
</header>

<main>
  <section aria-label="About Mental Health Awareness">
    <h2>About Mental Health Awareness</h2>
    <p>
      Mental health is essential to overall well-being, involving emotional, psychological, and social aspects. 
      Raising awareness can help reduce stigma, encourage support, and promote healthy habits.
    </p>
  </section>

  <section aria-label="Mental Health Tips">
    <h2>Mental Health Tips</h2>
    <ul class="tips" role="list" tabindex="0">
      <li tabindex="0" data-tip="Stay connected with friends and family to share feelings and reduce stress.">Stay Socially Connected</li>
      <li tabindex="0" data-tip="Maintain a regular exercise routine to improve mood and reduce anxiety.">Exercise Regularly</li>
      <li tabindex="0" data-tip="Ensure you get enough restful sleep each night to help your body and mind recover.">Get Quality Sleep</li>
      <li tabindex="0" data-tip="Practice mindfulness or meditation to stay present and calm your mind.">Practice Mindfulness</li>
      <li tabindex="0" data-tip="Seek professional help if feelings of sadness or stress become overwhelming.">Seek Professional Help</li>
    </ul>
    <div id="tipDetail" class="tip-detail" aria-live="polite" aria-atomic="true"></div>
  </section>

  <section aria-label="Contact form for more information or support">
    <h2>Contact Me</h2>
    <form id="contactForm" aria-describedby="formMessage">
      <label for="name">Name:</label>
      <input type="text" id="name" name="name" required aria-required="true" />
      
      <label for="email">Email:</label>
      <input type="email" id="email" name="email" required aria-required="true" />
      
      <label for="message">Message:</label>
      <textarea id="message" name="message" rows="4" required aria-required="true"></textarea>
      
      <button type="submit">Send</button>
      <p id="formMessage" role="alert" style="margin-top:1rem; color: green;"></p>
    </form>
  </section>
</main>

<footer>
  &copy; 2025 Mental Health Awareness Portfolio
</footer>

<script>
  const tipsList = document.querySelectorAll('.tips li');
  const tipDetail = document.getElementById('tipDetail');
  tipsList.forEach(tip => {
    tip.addEventListener('click', () => {
      tipDetail.textContent = tip.getAttribute('data-tip');
    });
    tip.addEventListener('keypress', (e) => {
      if (e.key === 'Enter' || e.key === ' ') {
        tipDetail.textContent = tip.getAttribute('data-tip');
        e.preventDefault();
      }
    });
  });

  const form = document.getElementById('contactForm');
  const formMessage = document.getElementById('formMessage');

  form.addEventListener('submit', function(e) {
    e.preventDefault();
    // For demonstration, just show a success message.
    formMessage.textContent = 'Thank you for contacting! Your message has been received.';
    form.reset();
  });
</script>

</body>
</html>
