# Password-strength-check
Password strength check tool
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Password Strength Checker</title>
<style>
html, body {
    height: 100%;
    margin: 0;
    font-family: Arial, sans-serif;
    background: url('https://images.unsplash.com/photo-1518770660439-4636190af475') no-repeat center center/cover;
    color: #f0f0f0; /* light text */
}

.overlay {
    background: rgba(0, 0, 0, 0.85); /* dark overlay */
    width: 100%;
    height: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
}

.container {
    background: rgba(0, 50, 0, 0.9); /* dark green overlay */
    padding: 30px;
    border-radius: 15px;
    width: 450px;
    text-align: center;
    border: 2px solid limegreen;
}

input {
    padding: 12px;
    width: 90%;
    margin-top: 15px;
    border: 2px solid limegreen;
    border-radius: 5px;
    background: #000;
    color: #f0f0f0;
    font-size: 16px;
}

#strength {
    margin-top: 15px;
    font-weight: bold;
    font-size: 16px;
}

.cyber {
    margin-top: 20px;
    font-size: 14px;
    text-align: left;
    line-height: 1.6;
}

.cyber ul {
    padding-left: 20px;
}
</style>
</head>
<body>

<div class="overlay">
<div class="container">
    <h2>Password Strength Checker</h2>
    <input type="password" id="password" placeholder="Enter Password" onkeyup="checkStrength()">
    <div id="strength"></div>

    <div class="cyber">
        <h3>Cybersecurity Tips:</h3>
        <ul>
            <li>Use strong passwords with letters, numbers & symbols.</li>
            <li>Change passwords regularly.</li>
            <li>Enable two-factor authentication.</li>
            <li>Keep software and devices updated.</li>
            <li>Do not reuse passwords across sites.</li>
            <li>Be aware of phishing emails and scams.</li>
            <li>Protect personal and sensitive data.</li>
            <li>Never share passwords with anyone.</li>
            <li>Use password managers for secure storage.</li>
        </ul>
    </div>
</div>
</div>

<script>
function checkStrength() {
    var password = document.getElementById("password").value;
    var strengthText = document.getElementById("strength");

    if(password.length < 6) {
        strengthText.innerHTML = "Weak Password";
        strengthText.style.color = "red";
    } else if(password.match(/[A-Z]/) && password.match(/[0-9]/) && password.match(/[@$!%*?&]/)) {
        strengthText.innerHTML = "Strong Password";
        strengthText.style.color = "limegreen";
    } else {
        strengthText.innerHTML = "Medium Password";
        strengthText.style.color = "orange";
    }
}
</script>

</body>
</html>
