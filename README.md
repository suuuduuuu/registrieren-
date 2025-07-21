# registrieren-
<!DOCTYPE html>
<html>
<head>
  <title>Registrierung</title>
  <script src="https://www.gstatic.com/firebasejs/9.0.0/firebase-app-compat.js"/script><
  <script src="https://www.gstatic.com/firebasejs/9.0.0/firebase-auth-compat.js"/script><
</head>
<body>
  <h1>Registrieren</h1>
  <input id="email" placeholder="E-Mail">
  <input id="password" placeholder="Passwort" type="password">
  <button onclick="register()">Registrieren</button>

  <script>
    const firebaseConfig = {
      apiKey: "AIzaSyAlsXFovYjR7OdUWn_gMIWBRNQ1d39EGC8",
      authDomain: "login-30236.firebaseapp.com"
    };
    firebase.initializeApp(firebaseConfig);

    function register() {
      const email = document.getElementById("email").value;
      const password = document.getElementById("password").value;
      firebase.auth().createUserWithEmailAndPassword(email, password)
        .then(user => {
          alert("Erfolgreich registriert!");
        })
        .catch(error => {
          alert("Fehler: " + error.message);
        });
    }
  </script>
</body>
</html>
