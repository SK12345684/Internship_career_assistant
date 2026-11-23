# Internship_career_assistant
A chatbot that helps students with internship, career guidance, resume building, and job preparation
gh repo clone SK12345684/Internship_career_assistant
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Business & Finance Career Assistant</title>
<style>
*{box-sizing:border-box}
body{font-family:Arial,sans-serif;background:#eef2ff;margin:0;padding:0;padding-bottom:80px}
.top{background:#fff;padding:15px 20px;display:flex;justify-content:space-between;align-items:center;position:sticky;top:0;box-shadow:0 2px 10px rgba(0,0,0,.05)}
.logo{font-weight:800;color:#1e40af;font-size:18px}
.btn{background:#1e40af;color:#fff;border:0;padding:8px 16px;border-radius:20px;font-weight:700}
.container{max-width:500px;margin:auto;padding:16px}
.card{background:#fff;border-radius:16px;padding:18px;margin-bottom:14px;box-shadow:0 4px 15px rgba(0,0,0,.06)}
h1{font-size:27px;line-height:1.2;margin:10px 0 5px}
.tagline{font-size:19px;font-weight:800;color:#1e40af;margin:0}
.subtitle{font-size:14px;color:#666;margin:8px 0 0}
.bar{height:10px;background:#e5e7eb;border-radius:10px;overflow:hidden}
.bar div{height:100%;background:#2563eb;width:28%}
.grid{display:grid;grid-template-columns:1fr 1fr;gap:12px}
.box{background:#f8fafc;padding:16px;border-radius:14px;text-align:center;cursor:pointer}
.box b{display:block;margin-top:6px}
.career{border:1px solid #e5e7eb;border-radius:14px;padding:14px;margin-bottom:12px;background:#fff}
.career h3{margin:0 0 5px}
.pill{display:inline-block;background:#dbeafe;color:#1e40af;padding:4px 10px;border-radius:20px;font-size:12px;font-weight:700;margin:2px}
.quiz-opt{display:block;width:100%;text-align:left;background:#f8fafc;border:1px solid #e5e7eb;padding:12px;border-radius:12px;margin:8px 0;cursor:pointer;font-size:15px}
.quiz-opt:hover{background:#dbeafe}
.correct{background:#dcfce7!important;border-color:green!important}
.wrong{background:#fee2e2!important;border-color:red!important}
.nav{position:fixed;bottom:0;left:0;right:0;background:#fff;display:flex;justify-content:space-around;padding:12px 0;border-top:1px solid #eee;max-width:500px;margin:auto}
.nav button{border:0;background:none;font-size:14px;font-weight:700;color:#888;cursor:pointer}
.nav button.active{color:#1e40af}
.hidden{display:none}
.score{font-size:22px;text-align:center;font-weight:800;color:#1e40af}
</style>
</head>
<body>

<div class="top"><div class="logo">🎓 B&F Assistant</div><button class="btn" onclick="showPage('dashboard')">Get Started</button></div>

<div class="container">

<!-- DASHBOARD -->
<div id="dashboard">
<div class="card">
<h1>Business & Finance<br>Career Assistant</h1>
<p class="tagline">Smart guidance for business careers</p>
<p class="subtitle">Explore courses, careers and skills to build your future in business.</p>
</div>
<div class="card">
<p><b>Learning Progress</b> <span style="float:right">28%</span></p>
<div class="bar"><div></div></div>
<p style="font-size:13px;color:#666">Next: Complete CA Foundation Module</p>
<p>🔥 Study Streak: 1 day &nbsp; | &nbsp; ⭐ XP: 150</p>
</div>
<div class="card"><h3>Quick Actions</h3><div class="grid">
<div class="box" onclick="showPage('careers')">💼<b>Explore Careers</b><span style="font-size:12px;color:#666">CA, CS, BBA & more</span></div>
<div class="box" onclick="showPage('quiz')">🎯<b>Take Quiz</b><span style="font-size:12px;color:#666">Test yourself</span></div>
<div class="box">📚<b>Courses</b><span style="font-size:12px;color:#666">Top courses</span></div>
<div class="box">⭐<b>Skills</b><span style="font-size:12px;color:#666">In-demand skills</span></div>
</div></div>
</div>

<!-- CAREERS -->
<div id="careers" class="hidden">
<div class="card"><h2>Explore Careers</h2><p style="color:#666;font-size:14px">Apne liye best business career chuno.</p></div>
<div class="career"><h3>📊 Chartered Accountant (CA)</h3><p style="color:#666;font-size:14px">India ki sabse respected finance career. Audit, Tax aur Finance me expert bano.</p><span class="pill">₹8-25 LPA</span> <span class="pill">5 Years</span> <span class="pill">High Demand</span></div>
<div class="career"><h3>🏢 Company Secretary (CS)</h3><p style="color:#666;font-size:14px">Company ke legal aur compliance ka boss.</p><span class="pill">₹6-15 LPA</span> <span class="pill">3-4 Years</span></div>
<div class="career"><h3>💰 Investment Banker</h3><p style="color:#666;font-size:14px">Bade deals, stocks aur finance me high salary wali career.</p><span class="pill">₹12-30 LPA</span> <span class="pill">MBA / CFA</span></div>
<div class="career"><h3>📈 Business Analyst</h3><p style="color:#666;font-size:14px">Data se business problems solve karo.</p><span class="pill">₹6-12 LPA</span> <span class="pill">BBA / B.Com</span></div>
<div class="career"><h3>🧾 Financial Analyst (CFA)</h3><p style="color:#666;font-size:14px">Global finance career, international scope.</p><span class="pill">₹10-20 LPA</span> <span class="pill">CFA</span></div>
<div class="career"><h3>🚀 Entrepreneur / Startup Founder</h3><p style="color:#666;font-size:14px">Apna khud ka business shuru karo.</p><span class="pill">Unlimited</span> <span class="pill">BBA + Skills</span></div>
</div>

<!-- QUIZ -->
<div id="quiz" class="hidden">
<div class="card"><h2>Career Quiz 🎯</h2><p style="color:#666;font-size:14px">5 questions, apni best career jaano.</p><p class="score" id="scoreText">Score: 0 / 5</p></div>
<div class="card" id="quizBox"></div>
<button class="btn" style="width:100%;padding:12px" onclick="resetQuiz()">Restart Quiz</button>
</div>

</div>

<div class="nav">
<button id="btn-dashboard" class="active" onclick="showPage('dashboard')">🏠<br>Home</button>
<button id="btn-careers" onclick="showPage('careers')">💼<br>Careers</button>
<button id="btn-quiz" onclick="showPage('quiz')">🎯<br>Quiz</button>
</div>

<script>
function showPage(p){
['dashboard','careers','quiz'].forEach(id=>{
document.getElementById(id).classList.add('hidden');
document.getElementById('btn-'+id).classList.remove('active');
});
document.getElementById(p).classList.remove('hidden');
document.getElementById('btn-'+p).classList.add('active');
window.scrollTo(0,0);
}
const questions=[
{q:"Business me sabse zyada paisa kis field me hai?",o:["Teaching","Investment Banking","Farming","Cooking"],a:1},
{q:"CA ka full form kya hai?",o:["Chartered Accountant","Chief Accountant","Company Auditor","Commerce Analyst"],a:0},
{q:"CFA kis field se related hai?",o:["Medical","Finance","Law","Sports"],a:1},
{q:"Startup ke liye sabse important kya hai?",o:["Idea + Execution","Sirf Paisa","Sirf Degree","Luck"],a:0},
{q:"B.Com ke baad best option kaun sa hai?",o:["CA / CS / MBA","Stop Study","Only Job","Kuch nahi"],a:0}
];
let qi=0, score=0;
function renderQuiz(){
if(qi>=questions.length){
document.getElementById('quizBox').innerHTML=`<h3>🎉 Quiz Complete!</h3><p>Tumhara Score: <b>${score} / 5</b></p><p>${score>=4?'Tum Finance ke liye perfect ho! CA / CFA try karo.':score>=2?'Tumhe Business Analyst / BBA achha lagega.':'Shuruat B.Com + Skills se karo, dheere dheere growth hogi.'}</p>`;
return;
}
let q=questions[qi];
document.getElementById('quizBox').innerHTML=`<p><b>Q${qi+1}. ${q.q}</b></p>`+q.o.map((opt,i)=>`<button class="quiz-opt" onclick="checkAns(${i},this)">${opt}</button>`).join('');
}
function checkAns(i,btn){
let q=questions[qi];
let btns=document.querySelectorAll('.quiz-opt');
if(i===q.a){btn.classList.add('correct');score++;}
else{btn.classList.add('wrong');btns[q.a].classList.add('correct');}
document.getElementById('scoreText').innerText=`Score: ${score} / 5`;
setTimeout(()=>{qi++;renderQuiz();},800);
}
function resetQuiz(){qi=0;score=0;document.getElementById('scoreText').innerText='Score: 0 / 5';renderQuiz();}
renderQuiz();
</script>
</body>
</html>
