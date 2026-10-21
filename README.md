
<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width,initial-scale=1,maximum-scale=1,user-scalable=no">
<meta name="theme-color" content="#061226">
<title>Eisen SMS</title>
<link rel="icon" href="icon.png">
<style>
:root{
  --bg:#050b17;--panel:#0b1830;--panel2:#10213d;
  --blue:#247bff;--cyan:#48d7f4;--text:#f4f7ff;
  --muted:#8fa4c4;--border:#1c3150;--green:#42dfad;
}
*{box-sizing:border-box}
body{
  margin:0;background:var(--bg);color:var(--text);
  font-family:Arial,"Segoe UI",sans-serif;min-height:100vh;
}
button,input{font:inherit}
button{cursor:pointer}
button:disabled{opacity:.5;cursor:wait}
.page{
  display:none;min-height:100vh;padding:22px;
  animation:appear .25s ease;
}
.page.active{display:flex}
@keyframes appear{
  from{opacity:0;transform:translateY(8px)}
  to{opacity:1;transform:translateY(0)}
}
.center{align-items:center;justify-content:center}
.welcome{
  width:100%;max-width:440px;text-align:center;
}
.logo-wrap{
  width:126px;height:126px;margin:0 auto 27px;
  border-radius:34px;display:grid;place-items:center;
  background:linear-gradient(145deg,#12356b,#08152b);
  border:1px solid #244d80;
  box-shadow:0 0 65px #1265ff30;
  animation:logoIn .8s ease;
}
.logo-wrap img{width:83px;height:83px;object-fit:contain}
@keyframes logoIn{
  from{opacity:0;transform:scale(.65) rotate(-12deg)}
  to{opacity:1;transform:scale(1) rotate(0)}
}
.brand{font-size:35px;font-weight:900;letter-spacing:-1px}
.brand span{color:var(--cyan)}
.subtitle{color:var(--muted);line-height:1.9;font-size:14px}
.welcome .subtitle{max-width:320px;margin:15px auto 30px}
.primary,.secondary,.danger{
  border:0;border-radius:14px;padding:15px 18px;
  width:100%;font-weight:800;transition:.2s;
}
.primary{background:linear-gradient(110deg,#1769f5,#328cff);color:white}
.primary:active{transform:scale(.98)}
.secondary{background:var(--panel2);border:1px solid var(--border);color:white}
.danger{background:#381b2b;color:#ffb4c4}
.actions{display:grid;gap:12px}
.foot{color:#607798;font-size:11px;margin-top:28px}
.auth-card{
  width:100%;max-width:420px;background:var(--panel);
  border:1px solid var(--border);border-radius:26px;padding:26px;
  box-shadow:0 20px 70px #0005;
}
.top-brand{display:flex;align-items:center;gap:12px;margin-bottom:28px}
.top-brand img{width:45px;height:45px;object-fit:contain}
.top-brand strong{font-size:22px}
h1{font-size:25px;margin:0 0 10px}
.description{font-size:13px;color:var(--muted);line-height:1.8;margin-bottom:25px}
.field{margin:17px 0}
.field label{display:block;font-size:13px;color:#c2d4f1;margin-bottom:9px}
.field input{
  width:100%;background:#061124;border:1px solid #243c5e;
  border-radius:12px;color:white;padding:15px;outline:none;
  direction:ltr;text-align:left;
}
.field input:focus{border-color:var(--blue);box-shadow:0 0 0 3px #247bff18}
.hint{font-size:11px;color:var(--muted);line-height:1.8;margin-top:8px}
.back{
  background:none;border:0;color:#9eb9df;padding:0 0 22px;
}
.link-button{
  border:0;background:none;color:var(--cyan);
  padding:15px 4px 0;font-size:13px;width:100%;
}
.notice{
  display:none;background:#112a40;border:1px solid #244c6d;
  color:#c8efff;padding:12px;border-radius:12px;
  font-size:13px;line-height:1.7;margin:15px 0;
  overflow-wrap:anywhere;
}
.notice.show{display:block}
.app-page{padding:0;flex-direction:column}
.app-header{
  padding:19px 18px;background:#081429;
  border-bottom:1px solid var(--border);
  display:flex;align-items:center;justify-content:space-between;gap:12px;
  position:sticky;top:0;z-index:2;
}
.app-title{display:flex;align-items:center;gap:10px;min-width:0}
.app-title img{width:39px;height:39px;object-fit:contain}
.app-title strong{font-size:21px}
.app-title small{display:block;color:var(--muted);font-size:11px;margin-top:4px}
.icon-btn{
  background:var(--panel2);border:1px solid var(--border);
  color:white;border-radius:12px;padding:11px;
}
.app-content{width:100%;max-width:850px;margin:auto;padding:20px;flex:1}
.section-title{font-size:21px;margin:7px 0}
.section-sub{font-size:12px;color:var(--muted);line-height:1.8}
.user-card{
  background:linear-gradient(125deg,#10284b,#0b1830);
  border:1px solid #25456c;border-radius:18px;padding:17px;margin:18px 0;
  overflow-wrap:anywhere;
}
.user-card small{color:var(--muted)}
.user-id{font-size:12px;direction:ltr;text-align:left;word-break:break-all;margin:9px 0}
.contact-form{
  display:grid;grid-template-columns:1fr auto;gap:9px;margin:20px 0;
}
.contact-form input{
  min-width:0;background:#09152a;border:1px solid var(--border);
  color:white;padding:14px;border-radius:12px;direction:ltr;
}
.contact-form button{width:auto;padding:12px 17px}
.chat-list{display:grid;gap:10px;margin-top:17px}
.chat-row{
  display:flex;align-items:center;gap:12px;text-align:right;
  background:var(--panel);border:1px solid var(--border);
  color:white;border-radius:16px;padding:15px;width:100%;
}
.avatar{
  width:46px;height:46px;flex-shrink:0;border-radius:16px;
  display:grid;place-items:center;background:#143768;color:#8ceaff;
  font-size:20px;font-weight:bold;
}
.chat-info{flex:1;min-width:0}
.chat-info strong{display:block;font-size:14px;overflow-wrap:anywhere}
.chat-info small{display:block;color:var(--muted);margin-top:6px;font-size:11px}
.empty{text-align:center;padding:35px 12px;color:var(--muted);font-size:13px;line-height:2}
.chat-page{padding:0;flex-direction:column;height:100dvh;min-height:500px}
.chat-header{
  display:flex;align-items:center;gap:12px;padding:12px;
  background:#081429;border-bottom:1px solid var(--border);
}
.chat-header .chat-info{flex:1}
.messages{
  flex:1;overflow-y:auto;padding:18px 13px;display:flex;
  flex-direction:column;gap:12px;scroll-behavior:smooth;
}
.message{
  max-width:82%;padding:12px 14px;border-radius:16px;
  line-height:1.65;font-size:14px;overflow-wrap:anywhere;
  white-space:pre-wrap;
}
.message.mine{
  align-self:flex-start;background:#155cc9;border-bottom-left-radius:4px;
}
.message.theirs{
  align-self:flex-end;background:#13233c;border:1px solid #243b5b;
  border-bottom-right-radius:4px;
}
.message time{display:block;font-size:10px;color:#c3d6f7;margin-top:5px;opacity:.8}
.composer{
  display:flex;gap:9px;padding:12px;background:#081429;
  border-top:1px solid var(--border);padding-bottom:max(12px,env(safe-area-inset-bottom));
}
.composer textarea{
  flex:1;min-width:0;resize:none;max-height:110px;
  background:#0d1b32;color:white;border:1px solid var(--border);
  border-radius:14px;padding:13px;outline:none;
}
.composer button{width:52px;flex-shrink:0;border-radius:14px}
.status{font-size:11px;color:var(--muted);padding:0 15px 9px;background:#081429}
#recaptcha-container{margin:14px 0;display:flex;justify-content:center}
@media(min-width:600px){
  .page{padding:30px}
  .app-page,.chat-page{padding:0}
}
</style>
</head>
<body>

<!-- WELCOME -->
<section class="page center active" id="welcome">
 <div class="welcome">
  <div class="logo-wrap"><img src="icon.png" alt="Eisen SMS"></div>
  <div class="brand">Eisen <span>SMS</span></div>
  <p class="subtitle">رسائلك الخاصة، في مكان واحد.<br>تواصل بأمان عبر أجهزتك.</p>
  <div class="actions">
   <button class="primary" onclick="showPage('login')">تسجيل الدخول</button>
   <button class="secondary" onclick="showPage('register')">إنشاء حساب جديد</button>
  </div>
  <div class="foot">EISEN SMS · PRIVATE MESSAGING</div>
 </div>
</section>

<!-- LOGIN -->
<section class="page center" id="login">
 <div class="auth-card">
  <button class="back" onclick="showPage('welcome')">→ العودة</button>
  <div class="top-brand"><img src="icon.png" alt=""><strong>Eisen SMS</strong></div>
  <h1>مرحباً بعودتك</h1>
  <p class="description">أدخل رقم هاتفك لتسجيل الدخول. سنرسل إليك رمز تحقق برسالة SMS.</p>
  <div class="field">
   <label for="loginPhone">رقم الهاتف مع رمز الدولة</label>
   <input id="loginPhone" type="tel" autocomplete="tel" placeholder="+213XXXXXXXXX">
   <div class="hint">مثال للجزائر: +213 ثم رقم الهاتف دون الصفر الأول.</div>
  </div>
  <div id="loginRecaptcha"></div>
  <button class="primary" id="loginSend" onclick="sendCode('login')">إرسال رمز التحقق</button>
  <div class="field" id="loginOtpField" hidden>
   <label for="loginOtp">رمز التحقق المكوّن من 6 أرقام</label>
   <input id="loginOtp" inputmode="numeric" autocomplete="one-time-code" maxlength="6" placeholder="000000">
  </div>
  <button class="primary" id="loginVerify" onclick="verifyCode('login')" hidden>تأكيد وتسجيل الدخول</button>
  <div class="notice" id="loginNotice"></div>
  <button class="link-button" onclick="showPage('register')">ليس لديك حساب؟ أنشئ حساباً</button>
 </div>
</section>

<!-- REGISTER -->
<section class="page center" id="register">
 <div class="auth-card">
  <button class="back" onclick="showPage('welcome')">→ العودة</button>
  <div class="top-brand"><img src="icon.png" alt=""><strong>Eisen SMS</strong></div>
  <h1>إنشاء حساب جديد</h1>
  <p class="description">أنشئ حسابك باستخدام رقم هاتفك فقط. لا تحتاج إلى بريد إلكتروني أو كلمة مرور.</p>
  <div class="field">
   <label for="registerName">اسم العرض</label>
   <input id="registerName" type="text" maxlength="40" autocomplete="nickname"
          dir="auto" placeholder="كيف سيظهر اسمك للآخرين؟">
  </div>
  <div class="field">
   <label for="registerPhone">رقم الهاتف مع رمز الدولة</label>
   <input id="registerPhone" type="tel" autocomplete="tel" placeholder="+213XXXXXXXXX">
   <div class="hint">استخدم رقماً تستطيع استقبال رسائل SMS عليه.</div>
  </div>
  <div id="registerRecaptcha"></div>
  <button class="primary" id="registerSend" onclick="sendCode('register')">إنشاء الحساب وإرسال الرمز</button>
  <div class="field" id="registerOtpField" hidden>
   <label for="registerOtp">رمز التحقق</label>
   <input id="registerOtp" inputmode="numeric" autocomplete="one-time-code" maxlength="6" placeholder="000000">
  </div>
  <button class="primary" id="registerVerify" onclick="verifyCode('register')" hidden>تأكيد وإنشاء الحساب</button>
  <div class="notice" id="registerNotice"></div>
  <button class="link-button" onclick="showPage('login')">لديك حساب بالفعل؟ تسجيل الدخول</button>
 </div>
</section>

<!-- MAIN INBOX -->
<section class="page app-page" id="inbox">
 <header class="app-header">
  <div class="app-title">
   <img src="icon.png" alt="">
   <div><strong>Eisen <span style="color:var(--cyan)">SMS</span></strong><small>رسائلك الخاصة</small></div>
  </div>
  <button class="icon-btn" onclick="logout()">خروج</button>
 </header>
 <main class="app-content">
  <h2 class="section-title">المحادثات</h2>
  <p class="section-sub">ابدأ محادثة خاصة مع مستخدم آخر.</p>
  <div class="user-card">
   <small>حسابك · معرّف المستخدم الخاص بك</small>
   <div class="user-id" id="myUid">...</div>
   <button class="secondary" onclick="copyMyUid()">نسخ المعرّف</button>
  </div>
  <h3 style="font-size:15px">محادثة جديدة</h3>
  <p class="section-sub">اطلب معرّف المستخدم من الشخص الآخر. لا تعرض هذه الصفحة قائمة عامة بأرقام الهواتف.</p>
  <form class="contact-form" onsubmit="startChat(event)">
   <input id="peerUid" placeholder="معرّف المستخدم UID" autocomplete="off" required>
   <button class="primary" type="submit">بدء</button>
  </form>
  <div class="notice" id="inboxNotice"></div>
  <h3 style="font-size:15px;margin-top:28px">رسائلك الأخيرة</h3>
  <div class="chat-list" id="chatList">
   <div class="empty">جارٍ تحميل المحادثات...</div>
  </div>
 </main>
</section>

<!-- CHAT -->
<section class="page chat-page" id="chat">
 <header class="chat-header">
  <button class="icon-btn" onclick="showPage('inbox')">→</button>
  <div class="avatar">E</div>
  <div class="chat-info"><strong id="chatPeerName">محادثة خاصة</strong><small id="chatPeerPhone">Eisen SMS</small></div>
  <button class="icon-btn" onclick="showPage('inbox')">✕</button>
 </header>
 <div class="messages" id="messages">
  <div class="empty">جارٍ تحميل الرسائل...</div>
 </div>
 <div class="status" id="chatStatus">المحادثة خاصة</div>
 <form class="composer" onsubmit="sendMessage(event)">
  <textarea id="messageInput" rows="1" maxlength="4000" placeholder="اكتب رسالتك..." required></textarea>
  <button class="primary" type="submit" aria-label="إرسال">➤</button>
 </form>
</section>

<script type="module">
import { initializeApp } from "https://www.gstatic.com/firebasejs/13.0.0/firebase-app.js";
import {
 getAuth, RecaptchaVerifier, signInWithPhoneNumber,
 onAuthStateChanged, signOut
} from "https://www.gstatic.com/firebasejs/13.0.0/firebase-auth.js";
import {
 getFirestore, doc, setDoc, getDoc, collection, addDoc,
 query, where, orderBy, limit, onSnapshot, serverTimestamp,
 updateDoc, arrayUnion
} from "https://www.gstatic.com/firebasejs/13.0.0/firebase-firestore.js";
import { getAnalytics } from "https://www.gstatic.com/firebasejs/13.0.0/firebase-analytics.js";

const firebaseConfig = {
 apiKey: "AIzaSyCNkJaxbQHkv9gntmt0tWdiVPMmjmWg-4g",
 authDomain: "eisen-mail.firebaseapp.com",
 projectId: "eisen-mail",
 storageBucket: "eisen-mail.firebasestorage.app",
 messagingSenderId: "857237566012",
 appId: "1:857237566012:web:fcc30291da60edfd2ac939",
 measurementId: "G-BMFXSBYLKP"
};

const app = initializeApp(firebaseConfig);
const auth = getAuth(app);
const db = getFirestore(app);
try { getAnalytics(app); } catch(e) { console.warn("Analytics unavailable",e); }

let confirmation = {login:null,register:null};
let recaptchas = {login:null,register:null};
let currentUser = null;
let activeChatId = null;
let activePeer = null;
let stopChats = null;
let stopMessages = null;
let chatCache = [];
let busy = false;

window.showPage = function(id){
 document.querySelectorAll(".page").forEach(p=>p.classList.remove("active"));
 document.getElementById(id).classList.add("active");
 if(id==="login" || id==="register") setupRecaptcha(id);
 if(id==="inbox" && currentUser) loadChats();
};

function notice(id,message,isError=false){
 const el=document.getElementById(id);
 el.textContent=message;
 el.style.borderColor=isError?"#8d3850":"#244c6d";
 el.style.color=isError?"#ffb8c6":"#c8efff";
 el.classList.add("show");
}
function clearNotice(id){
 const el=document.getElementById(id);
 el.textContent="";el.classList.remove("show");
}
function friendlyError(e){
 const code=e?.code||"";
 const messages={
  "auth/invalid-phone-number":"رقم الهاتف غير صحيح. أدخله مع رمز الدولة.",
  "auth/too-many-requests":"تم إرسال طلبات كثيرة. حاول لاحقاً.",
  "auth/invalid-verification-code":"رمز التحقق غير صحيح.",
  "auth/code-expired":"انتهت صلاحية الرمز. اطلب رمزاً جديداً.",
  "auth/quota-exceeded":"تم بلوغ حد الرسائل المتاح في Firebase.",
  "auth/network-request-failed":"تحقق من اتصال الإنترنت.",
  "auth/operation-not-allowed":"فعّل تسجيل الدخول برقم الهاتف من إعدادات Firebase.",
  "auth/unauthorized-domain":"أضف نطاق الموقع إلى Authorized domains في Firebase.",
  "permission-denied":"ليس لديك إذن لتنفيذ هذه العملية. تحقق من قواعد Firestore.",
  "failed-precondition":"تحقق من إعدادات قاعدة البيانات أو الفهارس المطلوبة."
 };
 return messages[code] || (e?.message||"حدث خطأ غير متوقع.");
}
function validPhone(value){
 return /^\+[1-9]\d{7,14}$/.test(value.trim());
}
function setupRecaptcha(type){
 if(recaptchas[type]) return;
 const container=document.getElementById(type+"Recaptcha");
 container.innerHTML="";
 try{
  recaptchas[type]=new RecaptchaVerifier(auth,container,{
   size:"normal",
   callback:()=>{},
   "expired-callback":()=>{recaptchas[type]=null;}
  });
  recaptchas[type].render().catch(e=>{
   console.error(e);
   recaptchas[type]=null;
   notice(type+"Notice","تعذر تحميل التحقق. حدّث الصفحة وتأكد من النطاق المسموح.",true);
  });
 }catch(e){
  console.error(e);
  notice(type+"Notice",friendlyError(e),true);
 }
}
window.sendCode=async function(type){
 if(busy)return;
 clearNotice(type+"Notice");
 const phone=document.getElementById(type+"Phone").value.trim();
 if(!validPhone(phone)){
  notice(type+"Notice","أدخل رقم الهاتف بصيغة دولية صحيحة، مثلاً +213XXXXXXXXX.",true);
  return;
 }
 if(type==="register" && !document.getElementById("registerName").value.trim()){
  notice("registerNotice","أدخل اسم العرض أولاً.",true);return;
 }
 busy=true;
 const btn=document.getElementById(type+"Send");
 btn.disabled=true;
 try{
  if(!recaptchas[type]) setupRecaptcha(type);
  if(!recaptchas[type]) throw new Error("تعذر إعداد اختبار التحقق. أعد تحميل الصفحة.");
  confirmation[type]=await signInWithPhoneNumber(auth,phone,recaptchas[type]);
  document.getElementById(type+"OtpField").hidden=false;
  document.getElementById(type+"Verify").hidden=false;
  btn.textContent="إعادة إرسال الرمز";
  notice(type+"Notice","تم إرسال رمز التحقق إن كان الرقم مؤهلاً للاستقبال. أدخل الرمز لإكمال العملية.");
 }catch(e){
  notice(type+"Notice",friendlyError(e),true);
  try{await recaptchas[type]?.clear();}catch(_){}
  recaptchas[type]=null;
  document.getElementById(type+"Recaptcha").innerHTML="";
 }finally{
  busy=false;btn.disabled=false;
 }
};
window.verifyCode=async function(type){
 if(busy)return;
 clearNotice(type+"Notice");
 const code=document.getElementById(type+"Otp").value.trim();
 if(!confirmation[type]){
  notice(type+"Notice","اطلب رمز التحقق أولاً.",true);return;
 }
 if(!/^\d{6}$/.test(code)){
  notice(type+"Notice","أدخل رمز التحقق المكوّن من 6 أرقام.",true);return;
 }
 busy=true;
 const btn=document.getElementById(type+"Verify");
 btn.disabled=true;
 try{
  const result=await confirmation[type].confirm(code);
  const user=result.user;
  const ref=doc(db,"users",user.uid);
  const existing=await getDoc(ref);
  if(type==="register"){
   if(existing.exists()){
    // رقم الهاتف مسجل مسبقاً؛ لا ننشئ ملفاً جديداً ولا نمسح بياناته.
    notice(type+"Notice","هذا الرقم لديه حساب بالفعل. تم التحقق من هويتك.",false);
   }else{
    await setDoc(ref,{
     uid:user.uid,
     displayName:document.getElementById("registerName").value.trim().slice(0,40),
     phoneNumber:user.phoneNumber,
     createdAt:serverTimestamp()
    });
   }
  }else if(!existing.exists()){
   await setDoc(ref,{
    uid:user.uid,
    displayName:"مستخدم Eisen",
    phoneNumber:user.phoneNumber,
    createdAt:serverTimestamp()
   });
  }
  confirmation[type]=null;
  currentUser=user;
  await enterApp(user);
 }catch(e){
  notice(type+"Notice",friendlyError(e),true);
 }finally{
  busy=false;btn.disabled=false;
 }
};

onAuthStateChanged(auth,async user=>{
 currentUser=user;
 if(user){
  try{await enterApp(user);}catch(e){
   console.error(e);
   showPage("inbox");
   notice("inboxNotice","تعذر تحميل الحساب: "+friendlyError(e),true);
  }
 }else{
  stopChats?.();stopChats=null;
  stopMessages?.();stopMessages=null;
  activeChatId=null;activePeer=null;
  showPage("welcome");
 }
});

async function enterApp(user){
 document.getElementById("myUid").textContent=user.uid;
 showPage("inbox");
 loadChats();
}

window.logout=async function(){
 try{await signOut(auth);}
 catch(e){alert(friendlyError(e));}
};

window.copyMyUid=async function(){
 try{
  await navigator.clipboard.writeText(currentUser.uid);
  notice("inboxNotice","تم نسخ معرّف المستخدم.");
 }catch(e){
  notice("inboxNotice","معرّفك هو: "+currentUser.uid);
 }
};

function getChatId(a,b){return [a,b].sort().join("_");}

window.startChat=async function(event){
 event.preventDefault();
 if(!currentUser)return;
 const peerUid=document.getElementById("peerUid").value.trim();
 clearNotice("inboxNotice");
 if(!peerUid || peerUid===currentUser.uid){
  notice("inboxNotice","أدخل معرّف مستخدم آخر.",true);return;
 }
 if(!/^[A-Za-z0-9_-]{20,128}$/.test(peerUid)){
  notice("inboxNotice","صيغة المعرّف غير صحيحة. انسخ UID كاملاً.",true);return;
 }
 try{
  const peerSnap=await getDoc(doc(db,"users",peerUid));
  if(!peerSnap.exists()){
   notice("inboxNotice","لم يتم العثور على هذا الحساب.",true);return;
  }
  const peer=peerSnap.data();
  const chatId=getChatId(currentUser.uid,peerUid);
  const chatRef=doc(db,"chats",chatId);
  const chatSnap=await getDoc(chatRef);
  if(!chatSnap.exists()){
   await setDoc(chatRef,{
    members:[currentUser.uid,peerUid].sort()
    createdAt:serverTimestamp(),
    lastMessage:"",
    updatedAt:serverTimestamp()
   });
  }else if(!chatSnap.data().members?.includes(currentUser.uid) ||
           !chatSnap.data().members?.includes(peerUid)){
   throw new Error("تعذر التحقق من صلاحية المحادثة.");
  }
  document.getElementById("peerUid").value="";
  await openChat(
   chatId,
   peerUid,
   peer.displayName||"مستخدم Eisen",
   peer.phoneNumber||""
  );
 }catch(e){
  notice("inboxNotice",friendlyError(e),true);
 }
};

function loadChats(){
 if(!currentUser)return;
 stopChats?.();

 const q=query(
  collection(db,"chats"),
  where("members","array-contains",currentUser.uid),
  orderBy("updatedAt","desc"),
  limit(50)
 );

 stopChats=onSnapshot(q,async snap=>{
  const list=document.getElementById("chatList");
  list.innerHTML="";

  if(snap.empty){
   list.innerHTML=
    '<div class="empty">لا توجد محادثات بعد.<br>ابدأ محادثة باستخدام معرّف المستخدم.</div>';
   return;
  }

  for(const d of snap.docs){
   const data=d.data();
   const peerUid=(data.members||[]).find(
    id=>id!==currentUser.uid
   );
   if(!peerUid)continue;

   let name="مستخدم Eisen";
   try{
    const p=await getDoc(doc(db,"users",peerUid));
    if(p.exists())name=p.data().displayName||name;
   }catch(_){}

   const row=document.createElement("button");
   row.className="chat-row";

   const avatar=document.createElement("div");
   avatar.className="avatar";
   avatar.textContent=name.charAt(0).toUpperCase()||"E";

   const info=document.createElement("div");
   info.className="chat-info";

   const title=document.createElement("strong");
   title.textContent=name;

   const last=document.createElement("small");
   last.textContent=data.lastMessage||"ابدأ المحادثة الآن";

   info.append(title,last);
   row.append(avatar,info);

   row.onclick=()=>openChat(
    d.id,peerUid,name,""
   );

   list.append(row);
  }
 },e=>{
  notice("inboxNotice",friendlyError(e),true);
 });
}

async function openChat(chatId,peerUid,name,phone){
 stopMessages?.();

 activeChatId=chatId;
 activePeer=peerUid;

 document.getElementById("chatPeerName").textContent=name;
 document.getElementById("chatPeerPhone").textContent=
  phone||"محادثة خاصة";

 document.getElementById("messages").innerHTML=
  '<div class="empty">جارٍ تحميل الرسائل...</div>';

 showPage("chat");

 const q=query(
  collection(db,"chats",chatId,"messages"),
  orderBy("createdAt","asc"),
  limit(200)
 );

 stopMessages=onSnapshot(q,snap=>{
  const area=document.getElementById("messages");
  area.innerHTML="";

  if(snap.empty){
   area.innerHTML=
    '<div class="empty">هذه بداية المحادثة.<br>أرسل رسالتك الأولى.</div>';
   return;
  }

  snap.forEach(d=>{
   const m=d.data();
   const bubble=document.createElement("div");

   bubble.className="message "+
    (m.senderId===currentUser.uid?"mine":"theirs");

   const content=document.createElement("div");
   content.textContent=m.text||"";

   const time=document.createElement("time");
   time.textContent=m.createdAt?.toDate
    ?m.createdAt.toDate().toLocaleTimeString("ar-DZ",{
      hour:"2-digit",minute:"2-digit"
     })
    :"";

   bubble.append(content,time);
   area.append(bubble);
  });

  area.scrollTop=area.scrollHeight;
 },e=>{
  document.getElementById("chatStatus").textContent=
   friendlyError(e);
 });
}

window.sendMessage=async function(event){
 event.preventDefault();

 const input=document.getElementById("messageInput");
 const text=input.value.trim();

 if(!text||!currentUser||!activeChatId)return;

 input.disabled=true;

 try{
  const chatRef=doc(db,"chats",activeChatId);
  const snap=await getDoc(chatRef);

  if(!snap.exists()||
     !snap.data().members?.includes(currentUser.uid)){
   throw new Error("ليس لديك إذن لإرسال الرسائل.");
  }

  await addDoc(
   collection(db,"chats",activeChatId,"messages"),
   {
    text:text.slice(0,4000),
    senderId:currentUser.uid,
    createdAt:serverTimestamp()
   }
  );

  await updateDoc(chatRef,{
   lastMessage:text.slice(0,120),
   updatedAt:serverTimestamp()
  });

  input.value="";
  document.getElementById("chatStatus").textContent=
   "تم إرسال الرسالة";

 }catch(e){
  document.getElementById("chatStatus").textContent=
   friendlyError(e);
 }finally{
  input.disabled=false;
  input.focus();
 }
};

document.getElementById("messageInput")
 .addEventListener("keydown",e=>{
  if(e.key==="Enter"&&!e.shiftKey){
   e.preventDefault();
   document.querySelector(".composer").requestSubmit();
  }
 });

</script>
</body>
</html>
