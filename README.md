<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>User Sign-Up Form</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>

  <div class="form-container">
    <h2>Sign Up</h2>
    <form id="signupForm">
      <div class="form-group">
        <label>Full Name</label>
        <input type="text" id="name" required>
        <small class="error" id="nameError"></small>
      </div>

      <div class="form-group">
        <label>Email</label>
        <input type="email" id="email" required>
        <small class="error" id="emailError"></small>
      </div>

      <div class="form-group">
        <label>Password</label>
        <input type="password" id="password" required>
        <small class="error" id="passwordError"></small>
      </div>

      <div class="form-group">
        <button type="submit">Register</button>
      </div>
    </form>
  </div>

  <script src="script.js"></script>
</body>
</html>
body {
    font-family: Arial, sans-serif;
    background-color: #f5f5ff;
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
  }
  
  .form-container {
    background-color: #fff;
    padding: 2rem;
    border-radius: 10px;
    width: 90%;
    max-width: 400px;
    box-shadow: 0 0 10px rgba(128, 0, 128, 0.1);
  }
  
  h2 {
    text-align: center;
    color: #4b0082;
    margin-bottom: 1rem;
  }
  
  .form-group {
    margin-bottom: 1rem;
  }
  
  label {
    display: block;
    margin-bottom: 0.5rem;
    color: #333;
  }
  
  input {
    width: 100%;
    padding: 0.5rem;
    border: 1px solid #aaa;
    border-radius: 5px;
  }
  
  button {
    width: 100%;
    padding: 0.7rem;
    background-color: #4b0082;
    color: white;
    border: none;
    border-radius: 5px;
    font-size: 1rem;
    cursor: pointer;
  }
  
  button:hover {
    background-color: #5e1ea0;
  }
  
  .error {
    color: red;
    font-size: 0.8rem;
    display: none;
  }
  
document.getElementById('signupForm').addEventListener('submit', function (e) {
    e.preventDefault();
  
    let isValid = true;
  
    const name = document.getElementById('name');
    const email = document.getElementById('email');
    const password = document.getElementById('password');
  
    const nameError = document.getElementById('nameError');
    const emailError = document.getElementById('emailError');
    const passwordError = document.getElementById('passwordError');
  
    // Reset errors
    nameError.style.display = 'none';
    emailError.style.display = 'none';
    passwordError.style.display = 'none';
  
    // Validate name
    if (name.value.trim() === '') {
      nameError.textContent = 'Name is required.';
      nameError.style.display = 'block';
      isValid = false;
    }
  
    // Validate email
    const emailRegex = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
    if (!emailRegex.test(email.value)) {
      emailError.textContent = 'Enter a valid email.';
      emailError.style.display = 'block';
      isValid = false;
    }
  
    // Validate password
    if (password.value.length < 6) {
      passwordError.textContent = 'Password must be at least 6 characters.';
      passwordError.style.display = 'block';
      isValid = false;
    }
  
    if (isValid) {
      alert('Form submitted successfully!');
      // You can now send data to the backend
    }
  });
