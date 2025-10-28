<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>بنك أسئلة الكيمياء - الثانوية العامة</title>
    <style>
        :root {
            --primary: #3498db;
            --secondary: #2c3e50;
            --success: #2ecc71;
            --danger: #e74c3c;
            --warning: #f39c12;
            --light: #ecf0f1;
            --dark: #34495e;
        }
        
        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background: linear-gradient(135deg, #f5f7fa 0%, #c3cfe2 100%);
            color: var(--dark);
            line-height: 1.6;
            min-height: 100vh;
            padding: 20px;
        }
        
        .container {
            max-width: 800px;
            margin: 0 auto;
            background-color: white;
            border-radius: 15px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
            overflow: hidden;
        }
        
        header {
            background: linear-gradient(to right, var(--primary), var(--secondary));
            color: white;
            padding: 25px;
            text-align: center;
        }
        
        header h1 {
            font-size: 1.8rem;
            margin-bottom: 10px;
        }
        
        header p {
            font-size: 1rem;
            opacity: 0.9;
        }
        
        .progress-container {
            background-color: var(--light);
            height: 10px;
            width: 100%;
        }
        
        .progress-bar {
            background-color: var(--primary);
            height: 100%;
            width: 0%;
            transition: width 0.3s ease;
        }
        
        .quiz-container {
            padding: 30px;
        }
        
        .question-number {
            color: var(--primary);
            font-weight: bold;
            margin-bottom: 5px;
        }
        
        .question-text {
            font-size: 1.2rem;
            margin-bottom: 20px;
            font-weight: 600;
        }
        
        .options-container {
            display: flex;
            flex-direction: column;
            gap: 12px;
            margin-bottom: 25px;
        }
        
        .option {
            background-color: var(--light);
            border: 2px solid transparent;
            border-radius: 8px;
            padding: 15px;
            cursor: pointer;
            transition: all 0.2s ease;
            display: flex;
            align-items: center;
        }
        
        .option:hover {
            background-color: #dfe6e9;
            transform: translateY(-2px);
        }
        
        .option.selected {
            border-color: var(--primary);
            background-color: rgba(52, 152, 219, 0.1);
        }
        
        .option.correct {
            border-color: var(--success);
            background-color: rgba(46, 204, 113, 0.1);
        }
        
        .option.incorrect {
            border-color: var(--danger);
            background-color: rgba(231, 76, 60, 0.1);
        }
        
        .option-letter {
            display: inline-flex;
            align-items: center;
            justify-content: center;
            width: 30px;
            height: 30px;
            background-color: var(--primary);
            color: white;
            border-radius: 50%;
            margin-left: 10px;
            font-weight: bold;
        }
        
        .navigation {
            display: flex;
            justify-content: space-between;
            margin-top: 20px;
        }
        
        button {
            background-color: var(--primary);
            color: white;
            border: none;
            padding: 12px 25px;
            border-radius: 8px;
            cursor: pointer;
            font-size: 1rem;
            font-weight: 600;
            transition: background-color 0.3s ease;
        }
        
        button:hover {
            background-color: #2980b9;
        }
        
        button:disabled {
            background-color: #bdc3c7;
            cursor: not-allowed;
        }
        
        .result-container {
            text-align: center;
            padding: 40px 20px;
            display: none;
        }
        
        .result-title {
            font-size: 2rem;
            margin-bottom: 20px;
            color: var(--secondary);
        }
        
        .score {
            font-size: 4rem;
            font-weight: bold;
            color: var(--primary);
            margin: 20px 0;
        }
        
        .score-text {
            font-size: 1.2rem;
            margin-bottom: 30px;
        }
        
        .restart-btn {
            background-color: var(--success);
            margin-top: 20px;
        }
        
        .restart-btn:hover {
            background-color: #27ae60;
        }
        
        .feedback {
            margin-top: 15px;
            padding: 10px;
            border-radius: 8px;
            display: none;
        }
        
        .feedback.correct {
            background-color: rgba(46, 204, 113, 0.1);
            color: var(--success);
            border: 1px solid var(--success);
        }
        
        .feedback.incorrect {
            background-color: rgba(231, 76, 60, 0.1);
            color: var(--danger);
            border: 1px solid var(--danger);
        }
        
        @media (max-width: 600px) {
            .container {
                border-radius: 10px;
            }
            
            header {
                padding: 20px 15px;
            }
            
            header h1 {
                font-size: 1.5rem;
            }
            
            .quiz-container {
                padding: 20px 15px;
            }
            
            .question-text {
                font-size: 1.1rem;
            }
            
            .navigation {
                flex-direction: column;
                gap: 10px;
            }
            
            button {
                width: 100%;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <header>
            <h1>بنك أسئلة الكيمياء</h1>
            <p>اختبار إلكتروني تفاعلي لطلاب الثانوية العامة</p>
        </header>
        
        <div class="progress-container">
            <div class="progress-bar" id="progress-bar"></div>
        </div>
        
        <div class="quiz-container" id="quiz-container">
            <div class="question-number" id="question-number">السؤال 1 من 50</div>
            <div class="question-text" id="question-text"></div>
            
            <div class="options-container" id="options-container">
                <!-- سيتم ملء الخيارات ديناميكيًا -->
            </div>
            
            <div class="feedback" id="feedback"></div>
            
            <div class="navigation">
                <button id="prev-btn" disabled>السابق</button>
                <button id="next-btn">التالي</button>
                <button id="submit-btn" style="display: none;">إنهاء الاختبار</button>
            </div>
        </div>
        
        <div class="result-container" id="result-container">
            <h2 class="result-title">نتيجة الاختبار</h2>
            <div class="score" id="score">0/50</div>
            <p class="score-text" id="score-text"></p>
            <button class="restart-btn" id="restart-btn">إعادة الاختبار</button>
        </div>
    </div>

    <script>
        // بيانات الأسئلة مع الإجابات الصحيحة
        const questions = [
            {
                question: "أي مما يلي يُعدّ من حالات المادة الأساسية؟",
                options: ["البلازما", "الصلبة", "الغروية"],
                correctAnswer: 1
            },
            {
                question: "أي خاصية تُميز المادة الصلبة؟",
                options: ["ليس لها حجم ثابت", "لها شكل ثابت", "تنضغط بسهولة"],
                correctAnswer: 1
            },
            {
                question: "أي مما يلي يُعدّ من خصائص السوائل؟",
                options: ["شكل ثابت", "حجم ثابت", "يمكن ضغطها بشدة"],
                correctAnswer: 1
            },
            {
                question: "الغازات تتميز بأنها؟",
                options: ["لها شكل وحجم ثابت", "ليس لها شكل أو حجم ثابت", "لا تتحرك جسيماتها"],
                correctAnswer: 1
            },
            {
                question: "أي مما يلي مثال على بخار؟",
                options: ["بخار الماء", "غاز الأكسجين", "غاز ثاني أكسيد الكربون"],
                correctAnswer: 0
            },
            {
                question: "أي خاصية يمكن ملاحظتها دون تغيير تركيب المادة؟",
                options: ["فيزيائية", "كيميائية", "نوية"],
                correctAnswer: 0
            },
            {
                question: "أي من الخواص التالية تُعدّ خاصية فيزيائية؟",
                options: ["الكثافة", "التفاعل مع الأحماض", "الاشتعال"],
                correctAnswer: 0
            },
            {
                question: "أي من الخواص التالية تُعدّ خاصية كيميائية؟",
                options: ["القابلية للاشتعال", "الكتلة", "الطول"],
                correctAnswer: 0
            },
            {
                question: "الكثافة تُعدّ من الخواص؟",
                options: ["الشدة", "الممتدة", "الكيميائية"],
                correctAnswer: 0
            },
            {
                question: "الطول يُعدّ من الخواص:",
                options: ["نوعية", "كمية", "كيميائية"],
                correctAnswer: 1
            },
            {
                question: "عند إذابة الملح في الماء فإن ذلك:",
                options: ["تغير فيزيائي", "تغير كيميائي", "إنتاج مادة جديدة"],
                correctAnswer: 0
            },
            {
                question: "احتراق الخشب يُعدّ:",
                options: ["تغير فيزيائي", "تغير كيميائي", "تغير شكلي"],
                correctAnswer: 1
            },
            {
                question: "انكسار الزجاج مثال على:",
                options: ["تغير كيميائي", "تغير فيزيائي", "نموي"],
                correctAnswer: 1
            },
            {
                question: "صدأ الحديد يُمثل:",
                options: ["تغير فيزيائي", "تغير كيميائي", "خاصية فيزيائية"],
                correctAnswer: 1
            },
            {
                question: "تبخر الماء مثال على:",
                options: ["تغير كيميائي", "تغير فيزيائي", "لا تغير"],
                correctAnswer: 1
            },
            {
                question: "قلي البيض يُعدّ:",
                options: ["تغير فيزيائي", "تغير كيميائي", "انصهار"],
                correctAnswer: 1
            },
            {
                question: "تخمر العسل يُعتبر:",
                options: ["تغير فيزيائي", "تغير كيميائي", "تغير شكلي"],
                correctAnswer: 1
            },
            {
                question: "أي عامل يؤثر في حالة المادة؟",
                options: ["درجة الحرارة", "اللون", "الطول"],
                correctAnswer: 0
            },
            {
                question: "عند تسخين الجليد فإنه يتحول إلى:",
                options: ["غاز", "سائل", "صلب آخر"],
                correctAnswer: 1
            },
            {
                question: "عملية تحول المادة من صلب إلى سائل تسمى:",
                options: ["تبخر", "انصهار", "تكثف"],
                correctAnswer: 1
            },
            {
                question: "تحول الغاز إلى سائل يسمى:",
                options: ["تبخر", "انصهار", "تكثف"],
                correctAnswer: 2
            },
            {
                question: "العملية التي تتحول فيها المادة الصلبة مباشرة إلى غاز:",
                options: ["ترشيح", "تسام", "تبلور"],
                correctAnswer: 1
            },
            {
                question: "أي خاصية تعتمد على كمية المادة؟",
                options: ["الحجم", "الكثافة", "اللون"],
                correctAnswer: 0
            },
            {
                question: "الكتلة يُعتبر خاصية:",
                options: ["ممتدة", "نوعية", "كيميائية"],
                correctAnswer: 0
            },
            {
                question: "اللون يُعتبر خاصية:",
                options: ["كيميائية", "نوعية", "ممتدة"],
                correctAnswer: 1
            },
            {
                question: "الخاصية التي لا تتغير بتغير كمية المادة:",
                options: ["الحجم", "الكثافة", "الكتلة"],
                correctAnswer: 1
            },
            {
                question: "الشمع عند درجة حرارة الغرفة يُعتبر مادة:",
                options: ["صلبة", "سائلة", "غازية"],
                correctAnswer: 0
            },
            {
                question: "الخشب يطفو على الماء لأن:",
                options: ["كثافته أقل من كثافة الماء", "حجمه كبير", "وزنه صغير"],
                correctAnswer: 0
            },
            {
                question: "عند تجمد الماء فإن حجمه:",
                options: ["يزداد", "ينقص", "يبقى ثابتاً"],
                correctAnswer: 0
            },
            {
                question: "النحاس موصل جيد للكهرباء، وهذا مثال على خاصية:",
                options: ["كيميائية", "فيزيائية", "نووية"],
                correctAnswer: 1
            },
            {
                question: "حشوة الأسنان غالبًا ما تصنع من:",
                options: ["عنصر", "مركب", "محلول"],
                correctAnswer: 2
            },
            {
                question: "سبيكة الحديد والنحاس تُعتبر:",
                options: ["محلول صلب-صلب", "محلول سائل-صلب", "محلول سائل-سائل"],
                correctAnswer: 0
            },
            {
                question: "عند التحليل الكهربائي للماء تكون نسبة الهيدروجين إلى الأكسجين:",
                options: ["1:1", "2:1", "3:1"],
                correctAnswer: 1
            },
            {
                question: "تفاعل الصوديوم مع الماء مثال على:",
                options: ["تغير فيزيائي", "تغير كيميائي", "لا تغير"],
                correctAnswer: 1
            },
            {
                question: "عند غليان الماء فإنه:",
                options: ["يتغير تركيبه", "يتغير حالته فقط", "يتكون مركب جديد"],
                correctAnswer: 1
            },
            {
                question: "القانون الذي يفسر ثبات الكتلة في التفاعلات:",
                options: ["قانون النسب الثابتة", "قانون حفظ الكتلة", "قانون النسب المتضاعفة"],
                correctAnswer: 1
            },
            {
                question: "قانون النسب الثابتة هو:",
                options: ["CO و CO₂", "حفظ الكتلة", "النسب المتضاعفة"],
                correctAnswer: 0
            },
            {
                question: "التغير الفيزيائي يتميز ب:",
                options: ["عدم تكوين مادة جديدة", "تكوين مادة جديدة", "إنتاج حرارة دائمًا"],
                correctAnswer: 0
            },
            {
                question: "أي مما يلي دليل على حدوث تغير كيميائي؟",
                options: ["انكسار الشكل", "تغير اللون", "التبخر"],
                correctAnswer: 1
            },
            {
                question: "تكوين رائحة جديدة أثناء التفاعل دليل على:",
                options: ["تغير فيزيائي", "تغير كيميائي", "تغير"],
                correctAnswer: 1
            },
            {
                question: "إذا تفاعل 16.6g من المغنيسيوم مع 10g من الأكسجين تكون كتلة الناتج:",
                options: ["6.6g", "26.6g", "106.6g"],
                correctAnswer: 1
            },
            {
                question: "عينة كتلتها 100g من مركب تحتوي على 20g هيدروجين، النسبة المئوية للهيدروجين =",
                options: ["11%", "21%", "31%"],
                correctAnswer: 1
            },
            {
                question: "مركب يحتوي على 1g هيدروجين و 19g أكسجين، النسبة المئوية للهيدروجين =",
                options: ["1%", "5%", "95%"],
                correctAnswer: 1
            },
            {
                question: "أيّ من الخواص التالية لا يمكن ملاحظتها مباشرة؟",
                options: ["الكثافة", "اللون", "الشكل"],
                correctAnswer: 0
            },
            {
                question: "أيّ من التغيرات التالية لا يُعدّ كيميائيًا؟",
                options: ["التبخر", "الاحتراق", "الصدأ"],
                correctAnswer: 0
            },
            {
                question: "عند تفاعل الحديد مع الكبريت لتكوين كبريتيد الحديد يحدث:",
                options: ["تغير فيزيائي", "تغير كيميائي", "تغير"],
                correctAnswer: 1
            },
            {
                question: "أيّ مما يلي يُعتبر تغيرًا فيزيائيًا عكسيًا؟",
                options: ["ذوبان الثلج", "احتراق الفحم", "صدأ الحديد"],
                correctAnswer: 0
            },
            {
                question: "الخاصية التي تحدد قدرة المادة على التفاعل مع الأحماض:",
                options: ["كيميائية", "فيزيائية", "ممتدة"],
                correctAnswer: 0
            },
            {
                question: "أي من الحالات التالية لها جسيمات متقاربة جدًا؟",
                options: ["الصلب", "السائل", "الغاز"],
                correctAnswer: 0
            },
            {
                question: "أي من الحالات التالية لها جسيمات متباعدة جدًا؟",
                options: ["الصلب", "السائل", "الغاز"],
                correctAnswer: 2
            }
        ];

        // متغيرات التطبيق
        let currentQuestion = 0;
        let userAnswers = new Array(questions.length).fill(null);
        let score = 0;

        // عناصر DOM
        const questionNumberElement = document.getElementById('question-number');
        const questionTextElement = document.getElementById('question-text');
        const optionsContainer = document.getElementById('options-container');
        const feedbackElement = document.getElementById('feedback');
        const prevButton = document.getElementById('prev-btn');
        const nextButton = document.getElementById('next-btn');
        const submitButton = document.getElementById('submit-btn');
        const progressBar = document.getElementById('progress-bar');
        const quizContainer = document.getElementById('quiz-container');
        const resultContainer = document.getElementById('result-container');
        const scoreElement = document.getElementById('score');
        const scoreTextElement = document.getElementById('score-text');
        const restartButton = document.getElementById('restart-btn');

        // تهيئة التطبيق
        function init() {
            showQuestion();
            updateProgressBar();
        }

        // عرض السؤال الحالي
        function showQuestion() {
            const question = questions[currentQuestion];
            
            // تحديث رقم السؤال
            questionNumberElement.textContent = `السؤال ${currentQuestion + 1} من ${questions.length}`;
            
            // تحديث نص السؤال
            questionTextElement.textContent = question.question;
            
            // مسح الخيارات السابقة
            optionsContainer.innerHTML = '';
            
            // إضافة الخيارات الجديدة
            question.options.forEach((option, index) => {
                const optionElement = document.createElement('div');
                optionElement.classList.add('option');
                
                // تحديد إذا كان الخيار مختارًا
                if (userAnswers[currentQuestion] === index) {
                    optionElement.classList.add('selected');
                }
                
                optionElement.innerHTML = `
                    ${option}
                    <span class="option-letter">${String.fromCharCode(65 + index)}</span>
                `;
                
                optionElement.addEventListener('click', () => selectOption(index));
                optionsContainer.appendChild(optionElement);
            });
            
            // تحديث حالة الأزرار
            prevButton.disabled = currentQuestion === 0;
            nextButton.disabled = false;
            
            // إظهار زر إنهاء الاختبار في السؤال الأخير
            if (currentQuestion === questions.length - 1) {
                nextButton.style.display = 'none';
                submitButton.style.display = 'inline-block';
            } else {
                nextButton.style.display = 'inline-block';
                submitButton.style.display = 'none';
            }
            
            // إخفاء التغذية الراجعة
            feedbackElement.style.display = 'none';
        }

        // اختيار خيار
        function selectOption(optionIndex) {
            userAnswers[currentQuestion] = optionIndex;
            showQuestion();
            
            // التحقق من الإجابة
            const question = questions[currentQuestion];
            const isCorrect = optionIndex === question.correctAnswer;
            
            // عرض التغذية الراجعة
            feedbackElement.textContent = isCorrect ? 
                "إجابة صحيحة! أحسنت!" : 
                "إجابة خاطئة. حاول مرة أخرى!";
            feedbackElement.className = `feedback ${isCorrect ? 'correct' : 'incorrect'}`;
            feedbackElement.style.display = 'block';
            
            // تحديث النتيجة
            if (isCorrect) {
                score++;
            }
        }

        // الانتقال إلى السؤال التالي
        function nextQuestion() {
            if (currentQuestion < questions.length - 1) {
                currentQuestion++;
                showQuestion();
                updateProgressBar();
            }
        }

        // الانتقال إلى السؤال السابق
        function prevQuestion() {
            if (currentQuestion > 0) {
                currentQuestion--;
                showQuestion();
                updateProgressBar();
            }
        }

        // تحديث شريط التقدم
        function updateProgressBar() {
            const progress = ((currentQuestion + 1) / questions.length) * 100;
            progressBar.style.width = `${progress}%`;
        }

        // إنهاء الاختبار وعرض النتيجة
        function submitQuiz() {
            // حساب النتيجة النهائية
            let finalScore = 0;
            userAnswers.forEach((answer, index) => {
                if (answer === questions[index].correctAnswer) {
                    finalScore++;
                }
            });
            
            // عرض النتيجة
            scoreElement.textContent = `${finalScore}/${questions.length}`;
            
            // نص النتيجة بناءً على الأداء
            let scoreText = "";
            const percentage = (finalScore / questions.length) * 100;
            
            if (percentage >= 90) {
                scoreText = "ممتاز! أداء رائع!";
            } else if (percentage >= 80) {
                scoreText = "جيد جداً! أحسنت!";
            } else if (percentage >= 70) {
                scoreText = "جيد! يمكنك التحسين أكثر.";
            } else if (percentage >= 60) {
                scoreText = "مقبول. تحتاج للمزيد من الدراسة.";
            } else {
                scoreText = "ضعيف. يجب مراجعة المادة مرة أخرى.";
            }
            
            scoreTextElement.textContent = scoreText;
            
            // إخفاء واجهة الاختبار وإظهار النتيجة
            quizContainer.style.display = 'none';
            resultContainer.style.display = 'block';
        }

        // إعادة بدء الاختبار
        function restartQuiz() {
            currentQuestion = 0;
            userAnswers = new Array(questions.length).fill(null);
            score = 0;
            
            // إعادة تعيين الواجهة
            quizContainer.style.display = 'block';
            resultContainer.style.display = 'none';
            
            showQuestion();
            updateProgressBar();
        }

        // إضافة مستمعي الأحداث
        nextButton.addEventListener('click', nextQuestion);
        prevButton.addEventListener('click', prevQuestion);
        submitButton.addEventListener('click', submitQuiz);
        restartButton.addEventListener('click', restartQuiz);

        // بدء التطبيق
        init();
    </script>
</body>
</html>
