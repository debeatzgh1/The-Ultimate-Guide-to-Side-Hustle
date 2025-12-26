<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Side Hustle Floating Hub</title>

<style>
body{
  margin:0;
  font-family:system-ui,-apple-system,BlinkMacSystemFont,sans-serif;
  background:#f3f4f6;
}

/* ================= FLOATING LAUNCHER ================= */
#fab-launcher{
  position:fixed;
  bottom:20px;
  right:20px;
  width:58px;
  height:58px;
  border-radius:50%;
  background:#2563eb;
  color:#fff;
  font-size:26px;
  font-weight:700;
  border:none;
  cursor:pointer;
  z-index:9999;
  box-shadow:0 10px 28px rgba(0,0,0,.3);
}

/* ================= MODAL ================= */
.modal-bg{
  display:none;
  position:fixed;
  inset:0;
  background:rgba(0,0,0,.75);
  backdrop-filter:blur(6px);
  justify-content:center;
  align-items:center;
  z-index:9998;
}

.modal-box{
  width:95%;
  height:92%;
  background:#fff;
  border-radius:18px;
  overflow:hidden;
  position:relative;
}

/* ================= CONTROLS ================= */
.modal-controls{
  position:absolute;
  top:10px;
  left:10px;
  display:flex;
  gap:8px;
  z-index:10;
}

.ctrl-btn{
  background:rgba(0,0,0,.85);
  color:#fff;
  padding:6px 12px;
  border-radius:10px;
  font-size:12px;
  font-weight:700;
  cursor:pointer;
}

iframe{
  width:100%;
  height:100%;
  border:none;
}
</style>
</head>

<body>

<!-- FLOATING LAUNCHER -->
<button id="fab-launcher" title="Open Side Hustle Hub">🚀</button>

<!-- MODAL -->
<div class="modal-bg" id="previewModal">
  <div class="modal-box" id="previewBox">
    <div class="modal-controls">
      <div class="ctrl-btn" id="nextBtn" style="display:none;" onclick="openNext()">➜ Next</div>
      <div class="ctrl-btn" onclick="toggleFS()">⛶ Fullscreen</div>
      <div class="ctrl-btn" onclick="closePreview()">✕ Close</div>
    </div>
    <iframe id="previewFrame"></iframe>
  </div>
</div>

<script>
const launcher = document.getElementById("fab-launcher");
const modal = document.getElementById("previewModal");
const frame = document.getElementById("previewFrame");
const nextBtn = document.getElementById("nextBtn");

/* FIRST PAGE */
const FIRST_URL = "https://debeatzgh.wordpress.com/begin-a-side-hustle/";
const NEXT_URL  = "https://digimartgh.blogspot.com/";

/* OPEN FIRST */
function openFirst(){
  frame.src = FIRST_URL;
  modal.style.display = "flex";
  nextBtn.style.display = "block"; // auto show
}

/* NEXT */
function openNext(){
  frame.src = NEXT_URL;
}

/* CLOSE */
function closePreview(){
  modal.style.display = "none";
  frame.src = "";
  if(document.fullscreenElement){
    document.exitFullscreen();
  }
}

/* FULLSCREEN */
function toggleFS(){
  const box = document.getElementById("previewBox");
  if(!document.fullscreenElement){
    box.requestFullscreen();
  }else{
    document.exitFullscreen();
  }
}

/* LAUNCHER CLICK */
launcher.addEventListener("click", openFirst);

/* CLICK OUTSIDE CLOSE */
modal.addEventListener("click", e=>{
  if(e.target === modal) closePreview();
});
</script>

</body>
</html>
