<!DOCTYPE html>
<html lang="bn">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>জীবন বিজ্ঞান কুইজ - অধ্যায় ৫ (সেট ৭ - ১০ মিনিট)</title>
    <style>
        :root {
            --primary-color: #27ae60;
            --primary-hover: #1e8449;
            --bg-color: #f4f9f4;
            --text-color: #2c3e50;
            --card-bg: #ffffff;
            --correct-color: #2ecc71;
            --wrong-color: #e74c3c;
            --timer-color: #d35400;
            --admin-color: #8e44ad;
            --next-set-color: #2980b9;
            --next-set-hover: #3498db;
        }

        body {
            font-family: 'Segoe UI', Arial, sans-serif;
            background-color: var(--bg-color);
            color: var(--text-color);
            margin: 0;
            padding: 20px;
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
        }

        .container {
            background-color: var(--card-bg);
            width: 100%;
            max-width: 800px;
            padding: 40px 30px;
            border-radius: 12px;
            box-shadow: 0 10px 30px rgba(39, 174, 96, 0.08);
            position: relative;
            height: fit-content;
        }

        h1 {
            text-align: center;
            color: var(--primary-hover);
            margin-bottom: 5px;
            font-size: 1.8em;
        }

        .subtitle {
            text-align: center;
            color: #7f8c8d;
            margin-bottom: 25px;
            font-size: 1em;
        }

        /* Login Section Styles */
        #login-section {
            display: block;
            max-width: 400px;
            margin: 0 auto;
        }

        .form-group {
            margin-bottom: 20px;
        }

        .form-group label {
            display: block;
            margin-bottom: 8px;
            font-weight: bold;
            color: #555;
        }

        .form-group input {
            width: 100%;
            padding: 12px 15px;
            border: 2px solid #e9ecef;
            border-radius: 8px;
            font-size: 1.1em;
            box-sizing: border-box;
            transition: border-color 0.3s ease;
        }

        .form-group input:focus {
            border-color: var(--primary-color);
            outline: none;
        }

        .error-message {
            color: var(--wrong-color);
            text-align: center;
            font-weight: bold;
            margin-bottom: 15px;
            display: none;
        }

        /* Quiz, Admin & Limit Block Sections */
        #quiz-section, #admin-section, #limit-section {
            display: none;
        }

        .limit-box {
            text-align: center;
            padding: 30px;
            background-color: #fce4d6;
            border: 2px solid #f1948a;
            border-radius: 8px;
            color: #c0392b;
            font-size: 1.2em;
            font-weight: bold;
            margin-bottom: 20px;
        }

        .question-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 20px;
            font-weight: bold;
            color: #7f8c8d;
        }

        .timer-box {
            background-color: #fdf2e9;
            color: var(--timer-color);
            padding: 6px 15px;
            border-radius: 20px;
            border: 1px solid #fadbd8;
            font-size: 1.1em;
            display: flex;
            align-items: center;
            gap: 5px;
        }

        .question-text {
            font-size: 1.25em;
            font-weight: 600;
            margin-bottom: 20px;
            line-height: 1.5;
        }

        .options-list {
            list-style: none;
            padding: 0;
            margin: 0;
        }

        .option-item {
            background-color: #f8f9fa;
            border: 2px solid #e9ecef;
            border-radius: 8px;
            padding: 15px 20px;
            margin-bottom: 12px;
            font-size: 1.1em;
            cursor: pointer;
            transition: all 0.2s ease;
        }

        .option-item:hover {
            border-color: var(--primary-color);
            background-color: #f4fbf6;
        }

        .option-item.selected {
            background-color: var(--primary-color);
            color: white;
            border-color: var(--primary-color);
        }

        .btn {
            background-color: var(--primary-color);
            color: white;
            border: none;
            padding: 15px 30px;
            font-size: 1.1em;
            font-weight: bold;
            border-radius: 8px;
            cursor: pointer;
            width: 100%;
            margin-top: 10px;
            transition: background-color 0.3s ease;
        }

        .btn:hover {
            background-color: var(--primary-hover);
        }

        /* Next Set Link Button */
        .btn-next-set {
            background-color: var(--next-set-color);
            text-align: center;
            text-decoration: none;
            display: block;
            box-sizing: border-box;
            font-size: 1.1em;
            font-weight: bold;
            color: white;
            padding: 15px 30px;
            border-radius: 8px;
            margin-top: 10px;
            transition: background-color 0.3s ease;
        }

        .btn-next-set:hover {
            background-color: var(--next-set-hover);
        }

        /* Admin Dashboard Table */
        .admin-title {
            color: var(--admin-color) !important;
        }
        
        table {
            width: 100%;
            border-collapse: collapse;
            margin-top: 20px;
            font-size: 1.05em;
        }

        th, td {
            border: 1px solid #e2e8f0;
            padding: 12px 15px;
            text-align: left;
        }

        th {
            background-color: #f1f5f9;
            color: #334155;
            font-weight: bold;
        }

        tr:nth-child(even) {
            background-color: #f8fafc;
        }

        /* Results Display */
        #result-section {
            display: none;
        }

        .score-board {
            text-align: center;
            padding: 20px;
            background: linear-gradient(135deg, #eaf2e8, #d5ebd5);
            border-radius: 10px;
            margin-bottom: 20px;
        }

        .score-board h2 {
            margin: 0;
            color: #2c3e50;
            font-size: 1.8em;
        }

        .review-item {
            background-color: #fdfdfd;
            border: 1px solid #e0e0e0;
            border-radius: 8px;
            padding: 20px;
            margin-bottom: 20px;
            box-shadow: 0 2px 5px rgba(0,0,0,0.02);
        }

        .review-q {
            font-size: 1.1em;
            font-weight: bold;
            margin-bottom: 15px;
        }

        .review-ans {
            margin-bottom: 8px;
            font-size: 1em;
        }

        .ans-correct { color: var(--correct-color); font-weight: bold; }
        .ans-wrong { color: var(--wrong-color); font-weight: bold; }

        .explanation {
            background-color: #fff9e6;
            border-left: 4px solid #f1c40f;
            padding: 12px 15px;
            margin-top: 15px;
            font-size: 0.95em;
            color: #555;
            border-radius: 0 4px 4px 0;
        }

        .welcome-text {
            color: var(--primary-hover);
            font-weight: bold;
        }
    </style>
</head>
<body>

<div class="container">

    <!-- Login Section -->
    <div id="login-section">
        <h1>স্টুডেন্ট ও অ্যাডমিন লগইন</h1>
        <p class="subtitle">জীবন বিজ্ঞান প্র্যাকটিস সেট শুরু করতে নিচে লগইন করুন</p>

        <div class="form-group">
            <label for="username">ইউজারনেম (Username)</label>
            <input type="text" id="username" placeholder="আপনার ইউজারনেম দিন" autocomplete="off">
        </div>

        <div class="form-group">
            <label for="password">পাসওয়ার্ড (Password)</label>
            <input type="password" id="password" placeholder="আপনার গোপন পাসওয়ার্ড দিন">
        </div>

        <div class="error-message" id="error-message">ইউজারনেম অথবা পাসওয়ার্ড ভুল হয়েছে!</div>

        <button class="btn" id="login-btn">লগইন করুন</button>
    </div>

    <!-- Attempt Limit Exceeded Section -->
    <div id="limit-section">
        <div class="limit-box">
            ⚠️ দুঃখিত, আপনার এই সেটের জন্য নির্ধারিত ১০ বার পরীক্ষার লিমিট শেষ হয়ে গেছে!
        </div>
        <p style="text-align: center; color: #555;">আপনি আর নতুন করে এই কুইজটিতে অংশগ্রহণ করতে পারবেন না। পরবর্তী সুযোগের জন্য আপনার শিক্ষকের সাথে যোগাযোগ করুন।</p>
        <button class="btn" onclick="location.reload()">লগ আউট ও ফিরে যান</button>
    </div>

    <!-- Admin Panel Section -->
    <div id="admin-section">
        <h1 class="admin-title">📊 শিক্ষক ড্যাশবোর্ড (Admin Panel)</h1>
        <p class="subtitle">পরীক্ষার্থীদের লাইভ পারফরম্যান্স ও মক টেস্টের ফুল রিপোর্ট (সর্বোচ্চ ১০ বার লিমিট)</p>
        
        <table>
            <thead>
                <tr>
                    <th>ছাত্রের নাম (Username)</th>
                    <th>সর্বোচ্চ স্কোর (Best Score)</th>
                    <th>মোট কতবার দিয়েছে (Total Attempts)</th>
                    <th>স্ট্যাটাস (Status)</th>
                </tr>
            </thead>
            <tbody id="admin-table-body">
                <!-- Data injected via JS -->
            </tbody>
        </table>
        
        <button class="btn" style="background-color: var(--admin-color); margin-top: 30px;" onclick="clearReports()">সমস্ত রেকর্ড ও লিমিট রিসেট করুন</button>
        <button class="btn" onclick="location.reload()">লগ আউট করুন</button>
    </div>

    <!-- Quiz Section -->
    <div id="quiz-section">
        <h1>জীবন বিজ্ঞান কুইজ: অধ্যায় ৫</h1>
        <div class="subtitle">
            <span class="welcome-text">পরীক্ষার্থী: <span id="student-name"></span></span> | সেট ৭: জীববৈচিত্র্য হ্রাসের কারণ ও সুন্দরবনের সমস্যা
        </div>

        <div class="question-header">
            <span id="q-counter">প্রশ্ন: ১ / ১৫</span>
            <div class="timer-box">
                ⏱️ সময় বাকি: <span id="timer-display">10:00</span>
            </div>
        </div>

        <div class="question-text" id="question-text">এখানে প্রশ্ন আসবে</div>
        <ul class="options-list" id="options-list">
            <!-- Options via JS -->
        </ul>

        <button class="btn" id="next-btn">পরবর্তী প্রশ্ন</button>
    </div>

    <!-- Result Section -->
    <div id="result-section">
        <div class="score-board">
            <h2>পরীক্ষা সম্পন্ন হয়েছে, <span id="result-student-name"></span>!</h2>
            <h1 style="margin-top: 10px;" id="final-score">স্কোর: 0 / 15</h1>
        </div>

        <!-- Set 8 Real Link Added Here -->
        <a href="https://tetsbazar.github.io/LIFE-SCIENCE-CHAPTER-5-SET-8/" target="_blank" class="btn-next-set">
            👉 পরবর্তী মক টেস্ট (সেট - ৮) দেওয়ার জন্য এখানে ক্লিক করুন
        </a>

        <h3 style="margin-top: 30px;">প্রশ্নের বিস্তারিত পর্যালোচনা:</h3>
        <div id="review-container">
            <!-- Review items via JS -->
        </div>
        <button class="btn" onclick="location.reload()">লগ আউট করুন</button>
    </div>

</div>

<script>
    // --- Login System Database ---
    const approvedStudents = {
        "anil7890": "12345677",
        "samir7890": "12345666",
        "rahul2024": "pass1234",
        "rohit999": "88889999",
        "suman007": "abcdef12",
        "Dhiren": "Dhiren1234",
        "Pradip": "Pradip1234",
        "Bijay": "Bijay1234",
        "admin": "admin1234" 
    };

    const attemptLimit = 10; // Maximum allowed exam attempts per student

    const loginSection = document.getElementById("login-section");
    const quizSection = document.getElementById("quiz-section");
    const adminSection = document.getElementById("admin-section");
    const limitSection = document.getElementById("limit-section");
    const adminTableBody = document.getElementById("admin-table-body");
    const usernameInput = document.getElementById("username");
    const passwordInput = document.getElementById("password");
    const loginBtn = document.getElementById("login-btn");
    const errorMessage = document.getElementById("error-message");
    const studentNameDisplay = document.getElementById("student-name");
    const resultStudentName = document.getElementById("result-student-name");

    let currentUsername = "";

    loginBtn.addEventListener("click", () => {
        const username = usernameInput.value.trim();
        const password = passwordInput.value.trim();

        if (approvedStudents[username] && approvedStudents[username] === password) {
            errorMessage.style.display = "none";
            loginSection.style.display = "none";
            currentUsername = username;

            if (username === "admin") {
                adminSection.style.display = "block";
                loadAdminData();
            } else {
                // Check Attempt Limit before starting
                const userReport = JSON.parse(localStorage.getItem(`quiz_report_ch5_s7_${currentUsername}`)) || { bestScore: 0, attempts: 0 };
                
                if (userReport.attempts >= attemptLimit) {
                    limitSection.style.display = "block";
                } else {
                    quizSection.style.display = "block";
                    studentNameDisplay.innerText = username;
                    resultStudentName.innerText = username;

                    loadQuestion();
                    startTimer(10 * 60); // 10 Minutes Timer
                }
            }
        } else {
            errorMessage.style.display = "block";
        }
    });

    // --- Admin Dashboard Storage ---
    function loadAdminData() {
        adminTableBody.innerHTML = "";
        Object.keys(approvedStudents).forEach(user => {
            if (user !== "admin") {
                const userReport = JSON.parse(localStorage.getItem(`quiz_report_ch5_s7_${user}`)) || { bestScore: "পরীক্ষা দেয়নি", attempts: 0 };
                
                let statusText = "চলমান";
                let statusColor = "#27ae60";
                if (userReport.attempts >= attemptLimit) {
                    statusText = "লকড (সীমা শেষ)";
                    statusColor = "var(--wrong-color)";
                } else if (userReport.attempts === 0) {
                    statusText = "অংশগ্রহণ করেনি";
                    statusColor = "#7f8c8d";
                }

                const row = document.createElement("tr");
                row.innerHTML = `
                    <td><strong>${user}</strong></td>
                    <td style="color: ${typeof userReport.bestScore === 'number' ? 'var(--primary-color)' : '#7f8c8d'}; font-weight: bold;">
                        ${typeof userReport.bestScore === 'number' ? userReport.bestScore + ' / 15' : userReport.bestScore}
                    </td>
                    <td><span style="background: #e2e8f0; padding: 3px 10px; border-radius: 10px; font-weight: bold;">${userReport.attempts} / ${attemptLimit} বার</span></td>
                    <td style="color: ${statusColor}; font-weight: bold;">${statusText}</td>
                `;
                adminTableBody.appendChild(row);
            }
        });
    }

    function clearReports() {
        if (confirm("আপনি কি নিশ্চিতভাবে সমস্ত ছাত্র-ছাত্রীর পরীক্ষার রেকর্ড ও অ্যাটেম্পট হিস্ট্রি ডিলিট করে লিমিট নতুন করে রিসেট করতে চান?")) {
            Object.keys(approvedStudents).forEach(user => {
                if (user !== "admin") {
                    localStorage.removeItem(`quiz_report_ch5_s7_${user}`);
                }
            });
            loadAdminData();
            alert("সমস্ত ডাটা এবং পরীক্ষার লিমিট সফলভাবে রিসেট করা হয়েছে।");
        }
    }

    // --- Life Science Chapter 5 Set 7 Question Data Bank ---
    const quizData = [
        {
            question: "১. জীববৈচিত্র্য হ্রাসের অন্যতম একটি প্রধান মনুষ্যসৃষ্ট কারণ কী?",
            options: ["ভূমিকম্প", "বাসস্থান ধ্বংস (Habitat destruction)", "আগ্নেয়গিরি", "সুনামি"],
            answer: "বাসস্থান ধ্বংস (Habitat destruction)",
            explanation: "মানুষ নিজেদের থাকার জন্য ও কৃষিকাজের জন্য নির্বিচারে জঙ্গল কাটছে, যার ফলে প্রাণীদের থাকার জায়গা ধ্বংস হয়ে যাচ্ছে।"
        },
        {
            question: "২. গোয়াম দ্বীপপুঞ্জে কোন বহিরাগত প্রাণীর অনুপ্রবেশের ফলে সেখানকার ১০টি স্থানীয় পাখির প্রজাতি সম্পূর্ণ বিলুপ্ত হয়ে গেছে?",
            options: ["ম্যালেরিয়ার মশা", "বাদামি গেছো সাপ (Brown tree snake / Boiga irregularis)", "আফ্রিকান ক্যাটফিশ", "গিনিপিগ"],
            answer: "বাদামি গেছো সাপ (Brown tree snake / Boiga irregularis)",
            explanation: "বহিরাগত প্রজাতির অনুপ্রবেশ অনেক সময় দেশীয় প্রজাতিকে চরম বিপদে ফেলে ধ্বংস করে দেয়, এটি তার একটি বড় উদাহরণ।"
        },
        {
            question: "৩. মেক্সিকো থেকে আসা কোন বহিরাগত বাহারি গাছটি ভারতের স্থানীয় আগাছা প্রজাতিকে চরম বিপন্ন করেছে?",
            options: ["ল্যান্টানা ক্যামেরা (Lantana camara)", "পার্থেনিয়াম", "কচুরিপানা", "ফণীমনসা"],
            answer: "ল্যান্টানা ক্যামেরা (Lantana camara)",
            explanation: "১৮০৯ সালে আসা এই গাছটি ভারতের জঙ্গলে এত দ্রুত বংশবৃদ্ধি করেছে যে অন্যান্য দেশীয় গাছগুলো টিকে থাকার জায়গা পাচ্ছে না।"
        },
        {
            question: "৪. গন্ডারের চোরাশিকার মূলত কোন জিনিসের লোভে করা হয়ে থাকে?",
            options: ["চামড়ার জন্য", "মাংসের জন্য", "শিংয়ের (Horn) জন্য", "লোমের জন্য"],
            answer: "শিংয়ের (Horn) জন্য",
            explanation: "চোরাপথে গন্ডারের শিং থেকে ওষুধ তৈরির ভ্রান্ত ধারণার কারণে এই নিরীহ প্রাণীটিকে নির্বিচারে মারা হচ্ছে।"
        },
        {
            question: "৫. উত্তরবঙ্গে হাতির আবাসস্থল ধ্বংস করে কোন বাগানের সম্প্রসারণ ঘটানোর ফলে হাতি ও মানুষের মধ্যে সংঘাত অনিবার্য হয়ে উঠছে?",
            options: ["আপেল বাগান", "চা বাগান", "কফি বাগান", "আঙুর বাগান"],
            answer: "চা বাগান",
            explanation: "হাতির জঙ্গলের ভেতর দিয়ে রেললাইন পাতা এবং চা বাগানের জন্য জঙ্গল কাটার ফলে হাতিরা লোকালয়ে ঢুকে পড়ছে।"
        },
        {
            question: "৬. সুন্দরবনের অপরূপ জীববৈচিত্র্য ও ম্যানগ্রোভ অরণ্যকে সম্মান জানিয়ে কোন সংস্থা একে 'ওয়ার্ল্ড হেরিটেজ সাইট' (World Heritage) ঘোষণা করেছে?",
            options: ["WHO", "UNICEF", "UNESCO (ইউনেস্কো)", "WWF"],
            answer: "UNESCO (ইউনেস্কো)",
            explanation: "১৯৯৭ সালে ইউনেস্কো সুন্দরবনের জীববৈচিত্র্যের এই আন্তর্জাতিক স্বীকৃতি প্রদান করে।"
        },
        {
            question: "৭. সুন্দরবনের পরিবেশে 'মিষ্টি জলের সংকট' তৈরি হওয়ার প্রধান কারণ কী?",
            options: ["অতিরিক্ত বৃষ্টি", "ভূগর্ভস্থ জলের যথেচ্ছ ব্যবহার ও আবহাওয়ার কারণে নদীতে নোনা জল বেশি ঢোকা", "নদীর জল শুকিয়ে যাওয়া", "বরফ গলে যাওয়া"],
            answer: "ভূগর্ভস্থ জলের যথেচ্ছ ব্যবহার ও আবহাওয়ার কারণে নদীতে নোনা জল বেশি ঢোকা",
            explanation: "এর ফলে সুন্দরবনের মানুষ ও বন্যপ্রাণীর পানীয় জলের এবং কৃষিকাজের জন্য মিষ্টি জলের প্রবল অভাব দেখা দিচ্ছে।"
        },
        {
            question: "৮. সুন্দরবনে রয়্যাল বেঙ্গল টাইগারের লোকালয়ে ঢুকে পড়ার বা খাদ্যাভাবের প্রধান কারণ কোনটি?",
            options: ["বাঘেদের বয়স বেড়ে যাওয়া", "খাদ্য-খাদকের ভারসাম্যের অভাব (যেমন- চোরাশিকারের ফলে হরিণ কমে যাওয়া)", "বাঘের সাঁতার কাটতে না পারা", "নদীর জল নোংরা হওয়া"],
            answer: "খাদ্য-খাদকের ভারসাম্যের অভাব (যেমন- চোরাশিকারের ফলে হরিণ কমে যাওয়া)",
            explanation: "বনে বাঘের খাবার অর্থাৎ হরিণ বা শূকর কমে যাওয়ায় বাঘ নিরুপায় হয়ে খাবারের খোঁজে গ্রামে ঢুকে পড়ছে।"
        },
        {
            question: "৯. সুন্দরবনে সমুদ্রের জলস্তর বৃদ্ধি পেয়ে ছোট ছোট দ্বীপগুলো ডুবে যাওয়ার (দ্বীপভূমির নিমজ্জন) মূল কারণ কী?",
            options: ["বিশ্ব উষ্ণায়ন (Global Warming)", "অতিরিক্ত বৃষ্টিপাত", "সুনামি", "জোয়ার-ভাটা"],
            answer: "বিশ্ব উষ্ণায়ন (Global Warming)",
            explanation: "পৃথিবীর তাপমাত্রা বাড়ার কারণে সমুদ্রের জলের তাপীয় প্রসারণ ও বরফ গলার ফলে জলস্তর বেড়ে গিয়ে সুন্দরবনের দ্বীপগুলো তলিয়ে যাচ্ছে।"
        },
        {
            question: "১০. সুন্দরবনের नदीগুলোতে দূষণের একটি বড় কারণ কী?",
            options: ["মাছ বেশি হওয়া", "নৌকা ও জাহাজ থেকে নির্গত তেল এবং শহরের কারখানার রাসায়নিক বর্জ্য", "পাতা পড়ে জল পচে যাওয়া", "কুমিরের সংখ্যা বৃদ্ধি"],
            answer: "নৌকা ও জাহাজ থেকে নির্গত তেল এবং শহরের কারখানার রাসায়নিক বর্জ্য",
            explanation: "এর ফলে নদীর মোহনার জল বিষাক্ত হচ্ছে এবং জলজ প্রাণীদের বেঁচে থাকা কঠিন হচ্ছে।"
        },
        {
            question: "১১. গবাদি পশুকে দেওয়া 'ডাইক্লোফেন্যাক' (Diclofenac) নামক ব্যথানাশক ওষুধের কারণে ভারতের কোন পাখির প্রজাতি প্রায় বিলুপ্তির মুখে?",
            options: ["ঈগল", "চিল", "শকুন", "পেঁচা"],
            answer: "শকুন",
            explanation: "مৃত গরুর মাংস খাওয়ার সময় এই ওষুধ শকুনের শরীরে প্রবেশ করে তাদের কিডনি নষ্ট করে দেয়।"
        },
        {
            question: "১২. সুন্দরবনে বসতি স্থাপনের জন্য প্রধানত কোন উদ্ভিদটি ধ্বংস করা হচ্ছে?",
            options: ["পাইন গাছ", "ক্যাকটাস", "লবণাম্বু বা ম্যানগ্রোভ উদ্ভিদ (যেমন- সুন্দরী, গরাণ)", "পদ্মফুল"],
            answer: "লবণাম্বu বা ম্যানগ্রোভ উদ্ভিদ (যেমন- সুন্দরী, গরাণ)",
            explanation: "মানুষ বন কেটে নিজেদের বাসস্থান তৈরি করছে, যা সুন্দরবনের প্রাকৃতিক বাঁধকে দুর্বল করে দিচ্ছে।"
        },
        {
            question: "১৩. বিশ্ব উষ্ণায়ন ও জলবায়ু পরিবর্তনের ফলে হাজার হাজার বছর আগে কোন প্রাণীটি বিলুপ্ত হয়ে গেছে বলে মনে করা হয়?",
            options: ["ডাইনোসর", "ডোদো পাখি", "উটপাখি", "ম্যামথ"],
            answer: "ডাইনোসর",
            explanation: "প্রাকৃতিক জলবায়ুর ব্যাপক পরিবর্তনে তারা মানিয়ে নিতে পারেনি। বর্তমানেও অনেক প্রাণী এই কারণে বিপন্ন।"
        },
        {
            question: "১৪. কোন দূষণের কারণে বর্তমানে জলাশয়ে মাছ ও জলজ প্রাণীর মৃত্যু ঘটছে এবং পরিযায়ী পাখিদের আগমন কমে যাচ্ছে?",
            options: ["শব্দদূষণ", "জলদূষণ ও ইউট্রোফিকেশন", "বায়ুদূষণ", "ক এবং খ উভয়ই"],
            answer: "ক এবং খ উভয়ই",
            explanation: "জলদূষণে মাছ মারা যায় এবং তীব্র শব্দদূষণে ভয় পেয়ে পরিযায়ী পাখিরা নির্দিষ্ট এলাকায় আসা বন্ধ করে দেয়।"
        },
        {
            question: "১৫. সুন্দরবনের বাস্তুতন্ত্রে খাদ্যশৃঙ্খলের একদম শীর্ষে অবস্থান করে কোন প্রাণী?",
            options: ["হরিণ", "বন্য শূকর", "রয়্যাল বেঙ্গল টাইগার", "কুমির"],
            answer: "রয়্যাল বেঙ্গল টাইগার",
            explanation: "বাঘ হলো সর্বোচ্চ স্তরের খাদক, যার ওপর পুরো জঙ্গলের ইকোসিস্টেমের ব্যালেন্স নির্ভর করে।"
        }
    ];

    let currentQuestionIndex = 0;
    let score = 0;
    let selectedOption = "";
    let userAnswers = [];
    let timerInterval;

    const questionTextEl = document.getElementById("question-text");
    const optionsListEl = document.getElementById("options-list");
    const nextBtn = document.getElementById("next-btn");
    const qCounterEl = document.getElementById("q-counter");
    const timerDisplayEl = document.getElementById("timer-display");

    const resultSection = document.getElementById("result-section");
    const reviewContainer = document.getElementById("review-container");
    const finalScoreEl = document.getElementById("final-score");

    function startTimer(durationInSeconds) {
        let timeRemaining = durationInSeconds;
        
        timerInterval = setInterval(() => {
            let minutes = Math.floor(timeRemaining / 60);
            let seconds = timeRemaining % 60;

            minutes = minutes < 10 ? "0" + minutes : minutes;
            seconds = seconds < 10 ? "0" + seconds : seconds;

            timerDisplayEl.innerText = `${minutes}:${seconds}`;

            if (timeRemaining <= 0) {
                clearInterval(timerInterval);
                alert("আপনার কুইজের নির্ধারিত ১০ মিনিট সময় শেষ হয়ে গেছে! কুইজটি স্বয়ংক্রিয়ভাবে সাবমিট করা হচ্ছে।");
                showResults();
            }
            timeRemaining--;
        }, 1000);
    }

    function loadQuestion() {
        selectedOption = "";
        const currentData = quizData[currentQuestionIndex];

        qCounterEl.innerText = `প্রশ্ন: ${currentQuestionIndex + 1} / ${quizData.length}`;
        questionTextEl.innerText = currentData.question;
        optionsListEl.innerHTML = "";

        if(currentQuestionIndex === quizData.length - 1) {
            nextBtn.innerText = "কুইজ সম্পূর্ণ সাবমিট করুন";
            nextBtn.style.backgroundColor = "#27ae60";
        } else {
            nextBtn.innerText = "পরবর্তী প্রশ্ন";
            nextBtn.style.backgroundColor = "var(--primary-color)";
        }

        currentData.options.forEach(option => {
            const li = document.createElement("li");
            li.classList.add("option-item");
            li.innerText = option;
            li.onclick = () => selectOption(li, option);
            optionsListEl.appendChild(li);
        });
    }

    function selectOption(li, option) {
        const allOptions = document.querySelectorAll(".option-item");
        allOptions.forEach(opt => opt.classList.remove("selected"));
        li.classList.add("selected");
        selectedOption = option;
    }

    function saveStudentReport(finalScore) {
        let userReport = JSON.parse(localStorage.getItem(`quiz_report_ch5_s7_${currentUsername}`)) || { bestScore: 0, attempts: 0 };
        
        userReport.attempts += 1; 
        if (finalScore > userReport.bestScore) {
            userReport.bestScore = finalScore; 
        }

        localStorage.setItem(`quiz_report_ch5_s7_${currentUsername}`, JSON.stringify(userReport));
    }

    function showResults() {
        clearInterval(timerInterval);
        quizSection.style.display = "none";
        resultSection.style.display = "block";
        finalScoreEl.innerText = `স্কোর: ${score} / ${quizData.length}`;

        saveStudentReport(score);

        reviewContainer.innerHTML = ""; 
        quizData.forEach((item, index) => {
            const userAnswer = userAnswers[index];
            const isCorrect = userAnswer === item.answer;

            const reviewHtml = `
                <div class="review-item">
                    <div class="review-q">${item.question}</div>
                    <div class="review-ans">
                        আপনার উত্তর: <span class="${isCorrect ? 'ans-correct' : 'ans-wrong'}">
                            ${userAnswer ? userAnswer : 'উত্তর দেননি (Skipped/Time Out)'}
                        </span>
                    </div>
                    ${!isCorrect ? `<div class="review-ans">সঠিক উত্তর: <span class="ans-correct">${item.answer}</span></div>` : ''}
                    <div class="explanation">
                        <strong>ব্যাখ্যা:</strong> ${item.explanation}
                    </div>
                </div>
            `;
            reviewContainer.innerHTML += reviewHtml;
        });
    }

    nextBtn.addEventListener("click", () => {
        if (selectedOption === "") {
            const confirmSkip = confirm("আপনি কোনো অপশন সিলেক্ট করেননি। আপনি কি এই প্রশ্নটি স্কিপ (Skip) করতে চান?");
            if (!confirmSkip) {
                return; 
            }
            userAnswers[currentQuestionIndex] = null; 
        } else {
            userAnswers[currentUsername] = selectedOption;
            userAnswers[currentQuestionIndex] = selectedOption;
            if (selectedOption === quizData[currentQuestionIndex].answer) {
                score++;
            }
        }

        currentQuestionIndex++;

        if (currentQuestionIndex < quizData.length) {
            loadQuestion();
        } else {
            showResults();
        }
    });
</script>

</body>
</html>
