# JARVIS-AI
<!DOCTYPE html>
<html lang="hi">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<title>JARVIS AI</title>
<style>
body {
  margin:0;
  background:#061323;
  color:white;
  font-family:Arial;
  text-align:center;
  padding:25px 15px;
}
h1 {color:#00d9ff}
.circle {
  width:150px;height:150px;
  border:4px solid #00d9ff;
  border-radius:50%;
  margin:35px auto;
  display:grid;place-items:center;
  font-size:25px;
  box-shadow:0 0 25px #00d9ff;
}
input,button,select {
  padding:13px;margin:7px;
  border-radius:10px;
  border:1px solid #00d9ff;
  background:#102b43;color:white;
}
#answer {
  background:#102b43;
  padding:15px;
  border-radius:12px;
  margin-top:20px;
}
</style>
</head>
<body>
<h1>JARVIS AI</h1>
<p>Your Personal Assistant</p>
<div class="circle">JARVIS</div>
<select id="voice">
<option value="male">Male Voice</option>
<option value="female">Female Voice</option>
</select>
<br>
<input id="question" placeholder="Ask me anything...">
<button onclick="ask()">Send</button>
<button onclick="listen()">🎤 Speak</button>
<div id="answer">Namaste! Main JARVIS hoon.</div>
<script>
function ask(){
 let q=document.getElementById("question").value;
 document.getElementById("answer").innerText=
 q ? "Aapne kaha: "+q : "Please kuch likhiye.";
}
function listen(){
 let S=window.SpeechRecognition||window.webkitSpeechRecognition;
 if(!S){alert("Voice support nahi hai.");return;}
 let r=new S();
 r.lang="hi-IN";
 r.onresult=e=>{
 document.getElementById("question").value=e.results[0][0].transcript;
 ask();
 };
 r.start();
}
</script>
</body>
</html>
