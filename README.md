<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>For Amaka ❤️</title>

<style>
    body {
        font-family: Arial, sans-serif;
        background: linear-gradient(135deg, #ff4e8b, #ff8ac6);
        display: flex;
        justify-content: center;
        align-items: center;
        height: 100vh;
        margin: 0;
        text-align: center;
        color: white;
    }

    .card {
        background: rgba(0,0,0,0.45);
        padding: 40px;
        border-radius: 20px;
        width: 90%;
        max-width: 420px;
        box-shadow: 0 10px 30px rgba(0,0,0,0.4);
    }

    h1 {
        margin-bottom: 25px;
        font-size: 24px;
    }

    button {
        padding: 12px 28px;
        font-size: 16px;
        border: none;
        border-radius: 8px;
        cursor: pointer;
        margin: 10px;
        transition: 0.3s ease;
    }

    .yes {
        background-color: #00e676;
        color: white;
    }

    .no {
        background-color: #ff1744;
        color: white;
    }

    button:hover {
        transform: scale(1.1);
    }

    #response {
        margin-top: 25px;
        font-size: 18px;
        font-weight: bold;
    }
</style>
</head>

<body>

<div class="card">
    <h1>Amaka, will you be my girl? ❤️</h1>

    <button class="yes" onclick="sayYes()">Yes</button>
    <button class="no" onclick="sayNo()">No</button>

    <p id="response"></p>
</div>

<script>
function sayYes() {
    document.getElementById("response").innerHTML =
        "Amaka, you just made me the happiest person alive ❤️🥰 I promise to treat you right.";
}

function sayNo() {
    document.getElementById("response").innerHTML =
        "No worries Amaka 😊 I still respect you and wish you the best.";
}
</script>

</body>
</html>
