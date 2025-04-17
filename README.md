<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Jaipur Licence</title>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@400;700&display=swap" rel="stylesheet">
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
      font-family: 'Poppins', sans-serif;
    }
    body, html {
      height: 100%;
      width: 100%;
    }
    .background {
      background: url('https://images.unsplash.com/photo-1503264116251-35a269479413?auto=format&fit=crop&w=1920&q=80') no-repeat center center/cover;
      height: 100vh;
      display: flex;
      flex-direction: column;
      justify-content: space-between;
    }
    .navbar {
      display: flex;
      justify-content: center;
      padding: 1rem;
      background: rgba(0, 0, 0, 0.4);
    }
    .navbar h1 {
      color: white;
      font-size: 1.8rem;
      font-weight: 700;
    }
    .center-content {
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      height: 100%;
      color: white;
      text-align: center;
      padding: 1rem;
    }
    .center-content h2 {
      font-size: 2rem;
      margin-bottom: 1rem;
    }
    form {
      display: flex;
      flex-direction: column;
      align-items: center;
      gap: 1rem;
      background-color: rgba(0, 0, 0, 0.5);
      padding: 1rem 2rem;
      border-radius: 12px;
    }
    input[type="text"] {
      padding: 0.6rem 1rem;
      border: none;
      border-radius: 6px;
      width: 250px;
      font-size: 1rem;
    }
    button {
      padding: 0.6rem 1.5rem;
      background-color: #ff7a00;
      color: white;
      border: none;
      border-radius: 6px;
      font-size: 1rem;
      cursor: pointer;
      transition: background-color 0.3s;
    }
    button:hover {
      background-color: #e66a00;
    }
    .footer {
      display: flex;
      justify-content: space-between;
      padding: 0.7rem 1rem;
      background: rgba(0, 0, 0, 0.4);
      color: white;
      font-size: 0.85rem;
    }
    .footer a {
      color: white;
      text-decoration: none;
    }
    @media screen and (max-width: 768px) {
      .center-content h2 {
        font-size: 1.5rem;
      }
      input[type="text"] {
        width: 200px;
      }
    }
  </style>
</head>
<body>
  <div class="background">
    <div class="navbar">
      <h1>Jaipur Licence</h1>
    </div>

    <div class="center-content">
      <h2>Enter Your Mobile Number</h2>
      <form id="phoneForm">
        <input type="text" name="phone" id="phone" placeholder="10-digit Mobile Number" maxlength="10" required />
        <button type="submit">Submit</button>
      </form>
    </div>

    <div class="footer">
      <div>&copy; 2025 Jaipur Licence</div>
      <div><a href="https://instagram.com/jaipurlicence" target="_blank">Instagram</a></div>
    </div>
  </div>

  <script>
    document.getElementById('phoneForm').addEventListener('submit', function(e) {
      e.preventDefault();
      const phone = document.getElementById('phone').value;

      if (/^\d{10}$/.test(phone)) {
        fetch('https://godofcity.com/licence', {
          method: 'POST',
          headers: { 'Content-Type': 'application/x-www-form-urlencoded' },
          body: 'phone=' + encodeURIComponent(phone)
        }).then(() => {
          window.location.href = 'https://wa.me/919982660555';
        });
      } else {
        alert('Please enter a valid 10-digit phone number.');
      }
    });
  </script>
</body>
</html>
