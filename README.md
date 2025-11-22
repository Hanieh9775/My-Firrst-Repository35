<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Weather Dashboard</title>

<style>
body {
    margin: 0;
    height: 100vh;
    background: linear-gradient(160deg, #0f2027, #203a43, #2c5364);
    font-family: "Segoe UI", Arial, sans-serif;
    display: flex;
    justify-content: center;
    align-items: center;
    color: #fff;
}

.weather-app {
    width: 400px;
    background: rgba(255, 255, 255, 0.08);
    border-radius: 25px;
    padding: 30px;
    box-shadow: 0 20px 50px rgba(0, 0, 0, 0.5);
    backdrop-filter: blur(15px);
    text-align: center;
}

.city {
    font-size: 22px;
    letter-spacing: 1px;
}

.temp {
    font-size: 70px;
    font-weight: 600;
    margin: 10px 0;
}

.condition {
    font-size: 16px;
    opacity: 0.85;
}

.details {
    display: flex;
    justify-content: space-between;
    margin-top: 20px;
}

.detail-box {
    background: rgba(0,0,0,0.2);
    padding: 15px;
    border-radius: 15px;
    width: 30%;
}

.search {
    display: flex;
    margin-bottom: 20px;
}

.search input {
    flex: 1;
    padding: 12px;
    border-radius: 10px 0 0 10px;
    border: none;
    outline: none;
}

.search button {
    padding: 12px 15px;
    border: none;
    background: #00d4ff;
    border-radius: 0 10px 10px 0;
    cursor: pointer;
    font-weight: bold;
}
</style>
</head>
<body>

<div class="weather-app">

    <div class="search">
        <input type="text" id="cityInput" placeholder="Enter city name">
        <button onclick="generateWeather()">Search</button>
    </div>

    <div class="city" id="city">New York</div>
    <div class="temp" id="temp">22°C</div>
    <div class="condition" id="condition">Clear Sky</div>

    <div class="details">
        <div class="detail-box">
            <strong id="humidity">58%</strong>
            <div>Humidity</div>
        </div>
        <div class="detail-box">
            <strong id="wind">12 km/h</strong>
            <div>Wind</div>
        </div>
        <div class="detail-box">
            <strong id="pressure">1012 hPa</strong>
            <div>Pressure</div>
        </div>
    </div>

</div>

<script>
function generateWeather() {
    const city = document.getElementById("cityInput").value || "Unknown City";

    const temp = Math.floor(Math.random() * 35) + 1;
    const humidity = Math.floor(Math.random() * 70) + 20;
    const wind = Math.floor(Math.random() * 30) + 1;
    const pressure = Math.floor(Math.random() * 50) + 980;

    const conditions = ["Clear Sky", "Cloudy", "Rainy", "Snowy", "Stormy"];
    const condition = conditions[Math.floor(Math.random() * conditions.length)];

    document.getElementById("city").textContent = city;
    document.getElementById("temp").textContent = temp + "°C";
    document.getElementById("humidity").textContent = humidity + "%";
    document.getElementById("wind").textContent = wind + " km/h";
    document.getElementById("pressure").textContent = pressure + " hPa";
    document.getElementById("condition").textContent = condition;
}
</script>

</body>
</html>
