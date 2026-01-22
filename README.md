# Devtown-Project
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Weather Web Application</title>

    <style>
        body {
            font-family: Arial, sans-serif;
            background: linear-gradient(to right, #2c3e50, #3498db);
            height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            margin: 0;
            color: #fff;
        }

        .weather-app {
            background: rgba(0, 0, 0, 0.3);
            padding: 25px;
            border-radius: 12px;
            width: 320px;
            text-align: center;
            box-shadow: 0 10px 25px rgba(0,0,0,0.4);
        }

        h2 {
            margin-bottom: 15px;
        }

        input {
            width: 90%;
            padding: 10px;
            border-radius: 6px;
            border: none;
            outline: none;
            margin-bottom: 10px;
        }

        button {
            padding: 10px 20px;
            border: none;
            border-radius: 6px;
            background: #1abc9c;
            color: white;
            cursor: pointer;
            font-size: 15px;
        }

        button:hover {
            background: #16a085;
        }

        .result {
            margin-top: 20px;
            display: none;
        }

        .temp {
            font-size: 40px;
            margin: 10px 0;
        }

        .details {
            font-size: 16px;
        }

        .error {
            margin-top: 10px;
            color: #ff7675;
        }
    </style>
</head>

<body>

<div class="weather-app">
    <h2>Weather Application</h2>

    <input type="text" id="city" placeholder="Enter City Name">
    <br>
    <button onclick="getWeather()">Get Weather</button>

    <div class="error" id="error"></div>

    <div class="result" id="result">
        <h3 id="cityName"></h3>
        <div class="temp" id="temperature"></div>
        <div class="details" id="weather"></div>
        <div class="details" id="humidity"></div>
        <div class="details" id="wind"></div>
    </div>
</div>

<script>
    function getWeather() {
        const city = document.getElementById("city").value;
        const error = document.getElementById("error");
        const result = document.getElementById("result");

        if (city === "") {
            error.innerText = "Please enter city name";
            result.style.display = "none";
            return;
        }

        error.innerText = "";

        // Demo weather data (for college project – no API needed)
        // You can replace this with real API later if required

        const demoWeather = {
            temp: Math.floor(Math.random() * 15) + 20,
            weather: "Clear Sky",
            humidity: Math.floor(Math.random() * 40) + 40,
            wind: Math.floor(Math.random() * 10) + 5
        };

        document.getElementById("cityName").innerText = city;
        document.getElementById("temperature").innerText = demoWeather.temp + "°C";
        document.getElementById("weather").innerText = "Weather: " + demoWeather.weather;
        document.getElementById("humidity").innerText = "Humidity: " + demoWeather.humidity + "%";
        document.getElementById("wind").innerText = "Wind Speed: " + demoWeather.wind + " km/h";

        result.style.display = "block";
    }
</script>

</body>
</html>
