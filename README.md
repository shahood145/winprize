<!DOCTYPE html>
<html>
<head>
    <title>Educational Demo - Suspicious Link</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            padding: 50px;
        }
        #blackScreen {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: black;
            color: white;
            display: none;
            justify-content: center;
            align-items: center;
            font-size: 24px;
            z-index: 9999;
        }
    </style>
</head>
<body>
    <h1>Educational Demo: Suspicious Link</h1>
    <p>This is a safe demonstration of how a malicious link might behave.</p>
    
    <a href="#" id="suspiciousLink" style="color: red; font-weight: bold;">⚠️ Click Me (Educational Demo) ⚠️</a>
    
    <div id="blackScreen">
        <p>This simulates a malicious attack. In a real scenario, this could be harmful.</p>
        <p>Screen will return in <span id="countdown">5</span> seconds...</p>
    </div>

    <script>
        document.getElementById("suspiciousLink").addEventListener("click", function(e) {
            e.preventDefault();
            
            const blackScreen = document.getElementById("blackScreen");
            const countdownElement = document.getElementById("countdown");
            
            blackScreen.style.display = "flex";
            
            let seconds = 5;
            const timer = setInterval(() => {
                seconds--;
                countdownElement.textContent = seconds;
                
                if (seconds <= 0) {
                    clearInterval(timer);
                    blackScreen.style.display = "none";
                }
            }, 1000);
        });
    </script>
</body>
</html>
