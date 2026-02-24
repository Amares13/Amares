<!DOCTYPE html>
<html lang="ar">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>مفاجأة لك 🧸</title>
    <style>
        body {
            margin: 0;
            background-color: #fce4ec;
            font-family: 'Arial', sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            overflow: hidden;
            text-align: center;
        }

        /* تنسيق صندوق الدخول */
        #lock-screen {
            background: white;
            padding: 40px;
            border-radius: 25px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.1);
            transition: 0.5s;
        }

        input {
            display: block;
            margin: 20px auto;
            padding: 12px;
            border: 2px solid #ff85a1;
            border-radius: 15px;
            font-size: 18px;
            outline: none;
        }

        button {
            background: #ff85a1;
            color: white;
            border: none;
            padding: 12px 30px;
            border-radius: 15px;
            cursor: pointer;
            font-size: 18px;
            font-weight: bold;
        }

        /* تنسيق محتوى المفاجأة */
        #content {
            display: none;
            animation: fadeIn 2s;
        }

        .hearts-container {
            font-size: 40px;
            line-height: 1.6;
        }

        h1 { color: #d81b60; font-size: 35px; }

        @keyframes fadeIn {
            from { opacity: 0; transform: scale(0.8); }
            to { opacity: 1; transform: scale(1); }
        }

        /* قلوب متحركة في الخلفية */
        .bg-heart {
            position: absolute;
            color: #ffb7c5;
            animation: float 4s infinite linear;
            z-index: -1;
        }

        @keyframes float {
            0% { transform: translateY(100vh); opacity: 1; }
            100% { transform: translateY(-10vh); opacity: 0; }
        }
    </style>
</head>
<body>

    <div id="lock-screen">
        <h2 style="color: #ff85a1;">🧸 اكتب الباسورد عشان تفتح 🧸</h2>
        <input type="password" id="passInput" placeholder="أدخل الرقم هنا">
        <button onclick="unlock()">فتح المفاجأة ❤️</button>
    </div>

    <div id="content">
        <h1>يا أجمل حد في الدنيا! ❤️</h1>
        <div class="hearts-container">
            🧸 ❤️ 🧸 ❤️ 🧸 ❤️<br>
            ❤️ 🧸 ❤️ 🧸 ❤️ 🧸<br>
            🧸 ❤️ 🧸 ❤️ 🧸 ❤️<br>
            ❤️ 🧸 ❤️ 🧸 ❤️ 🧸<br>
            🧸 ❤️ 🧸 ❤️ 🧸 ❤️
        </div>
        <p style="font-size: 20px; color: #ad1457; margin-top: 20px;">الرسالة دي معمولة عشان تفرحك بس! ✨</p>
    </div>

    <script>
        function unlock() {
            var pass = document.getElementById("passInput").value;
            // الباسورد هنا هو 1234
            if (pass === "1234") {
                document.getElementById("lock-screen").style.display = "none";
                document.body.style.backgroundColor = "#ffc1cc";
                document.getElementById("content").style.display = "block";
                createHearts();
            } else {
                alert("الباسورد غلط.. جرب تاني يا قمر ❌");
            }
        }

        // دالة لعمل قلوب بتطير في الخلفية
        function createHearts() {
            for(let i=0; i<20; i++) {
                setTimeout(() => {
                    let heart = document.createElement('div');
                    heart.className = 'bg-heart';
                    heart.innerHTML = '❤️';
                    heart.style.left = Math.random() * 100 + 'vw';
                    heart.style.animationDuration = (Math.random() * 3 + 2) + 's';
                    document.body.appendChild(heart);
                }, i * 200);
            }
        }
    </script>
</body>
</html>
