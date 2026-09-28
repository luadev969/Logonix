<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Download Page</title>
    <style>
        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        body {
            background: linear-gradient(135deg, #0f0c29, #302b63, #24243e);
            color: #ffffff;
            min-height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            padding: 20px;
        }

        .card {
            background: rgba(255, 255, 255, 0.05);
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.1);
            border-radius: 20px;
            padding: 30px;
            width: 100%;
            max-width: 400px;
            text-align: center;
            box-shadow: 0 15px 35px rgba(0, 0, 0, 0.5);
        }

        h2 {
            margin-bottom: 10px;
            font-size: 24px;
            color: #fff;
        }

        p {
            color: #aaa;
            font-size: 14px;
            margin-bottom: 25px;
        }

        .btn {
            display: block;
            width: 100%;
            padding: 14px;
            margin-bottom: 15px;
            border: none;
            border-radius: 12px;
            font-size: 16px;
            font-weight: 600;
            cursor: pointer;
            text-decoration: none;
            transition: all 0.3s ease;
            box-shadow: 0 4px 15px rgba(0,0,0,0.2);
        }

        .btn-sub {
            background: #ff0000;
            color: white;
        }

        .btn-sub:hover {
            background: #cc0000;
            transform: translateY(-2px);
        }

        .btn-like {
            background: #2196F3;
            color: white;
        }

        .btn-like:hover {
            background: #0b7dda;
            transform: translateY(-2px);
        }

        .btn.completed {
            background: #4CAF50 !important;
            cursor: default;
            transform: none !important;
        }

        .btn-download {
            background: #9c27b0;
            color: white;
            display: none; /* Скрыта изначально */
        }

        .btn-download:hover {
            background: #7b1fa2;
            transform: translateY(-2px);
        }

        .status {
            font-size: 12px;
            color: #ff9800;
            margin-top: 15px;
        }
    </style>
</head>
<body>

    <div class="card">
        <h2>Unlock File</h2>
        <p>Complete the steps below to unlock your download link.</p>

        <!-- Кнопка Подписки -->
        <a href="https://www.youtube.com/@LuaDev-X" target="_blank" id="subBtn" class="btn btn-sub" onclick="completeStep('sub')">Subscribe Channel</a>

        <!-- Кнопка Лайка -->
        <a href="https://youtu.be/oPsR9CsTveU?si=O3XRmr3oC7dQJw6Y" target="_blank" id="likeBtn" class="btn btn-like" onclick="completeStep('like')">Like Video</a>

        <!-- Кнопка Скачивания (появится после выполнения) -->
        <a href="https://www.mediafire.com/file/gpylmo569xe7vam/script+[logonix].zip/file" target="_blank" id="downloadBtn" class="btn btn-download">Open Download Link</a>

        <div class="status" id="statusText">Complete steps 1 and 2 to unlock</div>
    </div>

    <script>
        let steps = {
            sub: false,
            like: false
        };

        function completeStep(step) {
            if (!steps[step]) {
                steps[step] = true;
                
                if (step === 'sub') {
                    let btn = document.getElementById('subBtn');
                    btn.innerHTML = "✓ Subscribed";
                    btn.classList.add('completed');
                } else if (step === 'like') {
                    let btn = document.getElementById('likeBtn');
                    btn.innerHTML = "✓ Liked";
                    btn.classList.add('completed');
                }

                checkUnlock();
            }
        }

        function checkUnlock() {
            if (steps.sub && steps.like) {
                document.getElementById('downloadBtn').style.display = 'block';
                document.getElementById('statusText').style.color = '#4CAF50';
                document.getElementById('statusText').innerHTML = "Unlocked successfully!";
            } else {
                let remaining = [];
                if (!steps.sub) remaining.push("Subscribe");
                if (!steps.like) remaining.push("Like");
                document.getElementById('statusText').innerHTML = "Please complete: " + remaining.join(" and ");
            }
        }
    </script>

</body>
</html>
<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Download Page</title>
    <style>
        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        body {
            background: linear-gradient(135deg, #0f0c29, #302b63, #24243e);
            color: #ffffff;
            min-height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            padding: 20px;
        }

        .card {
            background: rgba(255, 255, 255, 0.05);
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.1);
            border-radius: 20px;
            padding: 30px;
            width: 100%;
            max-width: 400px;
            text-align: center;
            box-shadow: 0 15px 35px rgba(0, 0, 0, 0.5);
        }

        h2 {
            margin-bottom: 10px;
            font-size: 24px;
            color: #fff;
        }

        p {
            color: #aaa;
            font-size: 14px;
            margin-bottom: 25px;
        }

        .btn {
            display: block;
            width: 100%;
            padding: 14px;
            margin-bottom: 15px;
            border: none;
            border-radius: 12px;
            font-size: 16px;
            font-weight: 600;
            cursor: pointer;
            text-decoration: none;
            transition: all 0.3s ease;
            box-shadow: 0 4px 15px rgba(0,0,0,0.2);
        }

        .btn-sub {
            background: #ff0000;
            color: white;
        }

        .btn-sub:hover {
            background: #cc0000;
            transform: translateY(-2px);
        }

        .btn-like {
            background: #2196F3;
            color: white;
        }

        .btn-like:hover {
            background: #0b7dda;
            transform: translateY(-2px);
        }

        .btn.completed {
            background: #4CAF50 !important;
            cursor: default;
            transform: none !important;
        }

        .btn-download {
            background: #9c27b0;
            color: white;
            display: none; /* Скрыта изначально */
        }

        .btn-download:hover {
            background: #7b1fa2;
            transform: translateY(-2px);
        }

        .status {
            font-size: 12px;
            color: #ff9800;
            margin-top: 15px;
        }
    </style>
</head>
<body>

    <div class="card">
        <h2>Unlock File</h2>
        <p>Complete the steps below to unlock your download link.</p>

        <!-- Кнопка Подписки -->
        <a href="https://www.youtube.com/@LuaDev-X" target="_blank" id="subBtn" class="btn btn-sub" onclick="completeStep('sub')">Subscribe Channel</a>

        <!-- Кнопка Лайка -->
        <a href="https://youtu.be/oPsR9CsTveU?si=O3XRmr3oC7dQJw6Y" target="_blank" id="likeBtn" class="btn btn-like" onclick="completeStep('like')">Like Video</a>

        <!-- Кнопка Скачивания (появится после выполнения) -->
        <a href="https://www.mediafire.com/file/gpylmo569xe7vam/script+[logonix].zip/file" target="_blank" id="downloadBtn" class="btn btn-download">Open Download Link</a>

        <div class="status" id="statusText">Complete steps 1 and 2 to unlock</div>
    </div>

    <script>
        let steps = {
            sub: false,
            like: false
        };

        function completeStep(step) {
            if (!steps[step]) {
                steps[step] = true;
                
                if (step === 'sub') {
                    let btn = document.getElementById('subBtn');
                    btn.innerHTML = "✓ Subscribed";
                    btn.classList.add('completed');
                } else if (step === 'like') {
                    let btn = document.getElementById('likeBtn');
                    btn.innerHTML = "✓ Liked";
                    btn.classList.add('completed');
                }

                checkUnlock();
            }
        }

        function checkUnlock() {
            if (steps.sub && steps.like) {
                document.getElementById('downloadBtn').style.display = 'block';
                document.getElementById('statusText').style.color = '#4CAF50';
                document.getElementById('statusText').innerHTML = "Unlocked successfully!";
            } else {
                let remaining = [];
                if (!steps.sub) remaining.push("Subscribe");
                if (!steps.like) remaining.push("Like");
                document.getElementById('statusText').innerHTML = "Please complete: " + remaining.join(" and ");
            }
        }
    </script>

</body>
</html>
