
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>BoostCamp Coding Test - Tech Selection</title>
    <link href="https://cdn.jsdelivr.net/gh/projectnoonnu/noonfonts_2107@1.0/NaNumSquareNeo.css" rel="stylesheet">
    <style>
        body {
            font-family: 'NanumSquareNeo', sans-serif;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: flex-start; /* 맨 위에서 시작하도록 */
            height: 100vh;
            margin: 0;
        }
        .section {
            margin-bottom: 20px;
            text-align: center;
        }
        .box {
            display: inline-block;
            width: 200px;
            height: 100px;
            border: 2px solid #000;
            text-align: center;
            line-height: 100px;
            margin: 10px;
            cursor: pointer;
            transition: background-color 0.3s;
            font-size: 20px; /* 글자 크기 키움 */
            font-weight: 700;
        }
        .box:hover {
            background-color: #C0F54E;
        }
        .button {
            padding: 10px 20px;
            font-size: 18px;
            font-weight: 700;
            cursor: pointer;
            margin-top: 20px;
            background-color: #9379FF;
            color: #FFF;
            border: none;
            border-radius: 5px;
            transition: background-color 0.3s;
        }
        .button:hover {
            background-color: #B88BFF;
        }
        .button-container { /* 버튼을 가운데 정렬하기 위한 컨테이너 */
            display: flex;
            justify-content: center;
            width: 100%;
        }
        .selected {
            background-color: #45E99A;
        }
        .subtitle {
            font-size: 30px;
            font-weight: 700;
            margin-bottom: 10px;
            background-color: #f0f0f0;
            padding: 5px 10px;
            border-radius: 5px;
        }
        .divider {
            width: 100%;
            height: 1px;
            background-color: #000;
            margin: 20px 0;
        }
    </style>
</head>
<body>
    <div class="section">
    </div>
    <h1>BoostCamp Coding Test</h1>
    <div class="section">
        <div class="subtitle">Choose Your Field</div>
        <div class="box" onclick="selectTech('web')">Web﹒Mobile</div>
        <div class="box" onclick="selectTech('ai')">AI Tech</div>
    </div>
    <div class="divider"></div> <!-- 구분선 추가 -->
    <div class="section">
        <div class="subtitle">Select Your Level</div>
        <div class="box" onclick="selectDifficulty('low')">Low</div>
        <div class="box" onclick="selectDifficulty('medium')">Medium</div>
        <div class="box" onclick="selectDifficulty('high')">High</div>
    </div>
    <div class="button-container">
        <button class="button" onclick="nextPage()">Let's Go</button>
    </div>

    <script>
        let selectedTech = '';
        let selectedDifficulty = '';

        function selectTech(tech) {
            selectedTech = tech;
            const techBoxes = document.querySelectorAll('.section:nth-of-type(2) .box');
            techBoxes.forEach(box => {
                box.classList.remove('selected');
                if (box.textContent.includes(tech === 'web' ? 'Web' : 'AI')) {
                    box.classList.add('selected');
                }
            });
        }

        function selectDifficulty(difficulty) {
            selectedDifficulty = difficulty;
            const difficultyBoxes = document.querySelectorAll('.section:nth-of-type(4) .box');
            difficultyBoxes.forEach(box => {
                box.classList.remove('selected');
                if (box.textContent.toLowerCase() === difficulty) {
                    box.classList.add('selected');
                }
            });
        }

        function nextPage() {
            if (selectedTech === 'web' && selectedDifficulty === 'medium') {
                window.location.href = 'Q1-2.html';
            } else {
                alert('This combination is not yet implemented.');
            }
        }
    </script>
</body>
</html>
