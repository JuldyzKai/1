
<html lang="kk">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Абай және Қыз Жібек жырлары</title>
    <style>
        body {
            margin: 0;
            padding: 0;
            font-family: 'Times New Roman', serif;
            background-color: #a4d014;
            background-image: url('1.jpg');
            color: #333;
            display: flex;
            flex-direction: column;
            min-height: 100vh;
        }
        
        .header {
            background-color: #032d56;
            color: white;
            padding: 15px;
            text-align: center;
            font-size: 22px;
        }
        
        .content-wrapper {
            padding: 10px;
            flex: 1;
            display: flex;
            flex-direction: column;
        }
        
        .columns {
            display: flex;
            flex: 1;
            gap: 10px;
        }
        
        .column {
            flex: 1;
            padding: 15px;
            background-color: white;
            border-radius: 5px;
            box-shadow: 0 2px 5px rgba(0,0,0,0.1);
            display: flex;
            flex-direction: column;
        }
        
        .column-title {
            border-bottom: 2px solid #5d0d04;
            padding-bottom: 8px;
            margin-bottom: 15px;
            color: #2c3e50;
            font-size: 18px;
        }
        
        .poem {
            line-height: 1.6;
            font-size: 16px;
            margin-bottom: 15px;
        }
        
        .poem p {
            margin: 8px 0;
        }
        
        .task-box {
            margin-top: 10px;
            padding: 12px;
            background-color: #f9f9f9;
            border-radius: 5px;
            border: 1px solid #ca7474;
        }
        
        .task-title {
            font-weight: bold;
            margin-bottom: 8px;
            font-size: 15px;
        }
        
        textarea {
            width: 100%;
            min-height: 80px;
            padding: 8px;
            border: 1px solid #0ea613;
            border-radius: 4px;
            font-family: inherit;
            font-size: 14px;
            box-sizing: border-box;
        }
        
        .explanation-area {
            padding: 15px;
            background-color: white;
            margin-top: 10px;
            border-radius: 5px;
            box-shadow: 0 2px 5px rgba(0,0,0,0.1);
        }
        
        .submit-btn {
            display: block;
            width: 180px;
            margin: 15px auto;
            padding: 10px;
            background-color: #2c3e50;
            color: white;
            border: none;
            border-radius: 5px;
            font-size: 16px;
            cursor: pointer;
            transition: background-color 0.3s;
        }
        
        .submit-btn:hover {
            background-color: #1a252f;
        }
        
        @media (max-width: 768px) {
            .columns {
                flex-direction: column;
            }
            
            .column {
                margin-bottom: 10px;
            }
        }
    </style>
</head>
<body>
    <div class="header">
        Қыз Жібек жырын Абай өлеңдерімен салыстыру
    </div>
    
    <div class="content-wrapper">
        <div class="columns">
            <div class="column">
                <h2 class="column-title">Абай өлеңі</h2>
                <div class="poem">
                    <p>Пайда ойлама, ар ойла,</p>
                    <p>Талап қыл артық білуге.</p>
                    <p>Артық ғылым кітапта,</p>
                    <p>Ерінбей оқып көруге.</p>
                </div>
                
                <div class="task-box">
                    <div class="task-title">Абай өлеңінен осы ойды ашатын 2 жолды жазыңыз:</div>
                    <textarea id="abaiAnswer" placeholder="Жауабыңызды осы жерге жазыңыз..."></textarea>
                </div>
            </div>
            
            <div class="column">
                <h2 class="column-title">Қыз Жібек жыры</h2>
                <div class="poem">
                    <p> </p>
                    <p> </p>
                    <p> </p>
                    <p> </p>
                     <div class="task-title">Жырдан  Төлегеннің бейнесін ашатын жолдарды жазыңыз:</div>
                    <textarea id="kyzAnswer" placeholder="Жауабыңызды осы жерге жазыңыз..."></textarea>
                </div>
                
                <div class="task-box">
                    <div class="task-title">осы ойды ашатын 2 жолды жазыңыз:</div>
                    <textarea id="kyzAnswer" placeholder="Жауабыңызды осы жерге жазыңыз..."></textarea>
                </div>
            </div>
        </div>
        
        <div class="explanation-area">
            <div class="task-title">Екі шығарма идеясы мен байланысын 3-4 сөйлеммен түсіндіріңіз:</div>
            <textarea id="explanation" placeholder="Түсіндірмеңізді осы жерге жазыңыз..." style="min-height: 100px;"></textarea>
        </div>
        
        <button class="submit-btn" onclick="submitAnswers()">Жіберу</button>
    </div>
    
    <script>
        function submitAnswers() {
            // Жауаптарды жинау
            const answer1 = document.getElementById('abaiAnswer').value;
            const answer2 = document.getElementById('kyzAnswer').value;
            const explanation = document.getElementById('explanation').value;
            
            // Мұғалімнің email мекенжайы
            const teacherEmail = "Juldiz8469@gmail.com";
            
            // Электрондық пошта құрастыру
            const subject = "Абай және Қыз Жібек жырлары бойынша жауаптар";
            const body = `Абай өлеңінен жауап:\n${answer1}\n\nҚыз Жібек жырынан жауап:\n${answer2}\n\nТүсіндірме:\n${explanation}`;
            
            // Пошта клиентін ашу
            const mailtoLink = `mailto:${teacherEmail}?subject=${encodeURIComponent(subject)}&body=${encodeURIComponent(body)}`;
            
            // Жауаптарды тексеру
            if (!answer1 || !answer2 || !explanation) {
                alert("Барлық жауаптарды толтырыңыз!");
                return;
            }
            
            // Жіберу
            window.location.href = mailtoLink;
            
            // Жауаптарды сақтау (localStorage-ға)
            const submission = {
                abaiAnswer: answer1,
                kyzAnswer: answer2,
                explanation: explanation,
                timestamp: new Date().toISOString()
            };
            localStorage.setItem('lastSubmission', JSON.stringify(submission));
        }
        
        // Алдыңғы жауаптарды жүктеу (егер бар болса)
        window.onload = function() {
            const lastSubmission = localStorage.getItem('lastSubmission');
            if (lastSubmission) {
                const submission = JSON.parse(lastSubmission);
                document.getElementById('abaiAnswer').value = submission.abaiAnswer;
                document.getElementById('kyzAnswer').value = submission.kyzAnswer;
                document.getElementById('explanation').value = submission.explanation;
            }
        };
    </script>
