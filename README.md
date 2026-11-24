# nOTICE-HUB
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">
<title>NoticeHub – SmartCampus Announcement and Memo Hub</title>
<link href="https://fonts.googleapis.com/css2?family=Bricolage+Grotesque:wght@600;800&family=Source+Sans+3:wght@400;600&display=swap" rel="stylesheet">
<style>
:root{--bg:#F3F6F4;--surface:#fff;--ink:#14211C;--muted:#566860;--line:#D5DDD8;--brand:#1F5C4D;--onbrand:#fff;--accent:#FFD23F;--danger:#B3261E;--ok:#1F7A4D;color-scheme:light;box-sizing:border-box;padding-top:env(safe-area-inset-top,0px);padding-bottom:env(safe-area-inset-bottom,0px)}
@media (prefers-color-scheme:dark){:root:not([data-theme="light"]){--bg:#101715;--surface:#18221F;--ink:#E8F0EC;--muted:#98A9A0;--line:#2B3A35;--brand:#5FC4A5;--onbrand:#0D1A15;--danger:#FF8A80;--ok:#6FD3A0;color-scheme:dark}}
:root[data-theme="dark"]{--bg:#101715;--surface:#18221F;--ink:#E8F0EC;--muted:#98A9A0;--line:#2B3A35;--brand:#5FC4A5;--onbrand:#0D1A15;--danger:#FF8A80;--ok:#6FD3A0;color-scheme:dark}
html{scroll-padding-top:env(safe-area-inset-top,0px)}
*,*:before,*:after{box-sizing:border-box}
body{margin:0;background:var(--bg);color:var(--ink);font:400 16px/1.5 "Source Sans 3",system-ui,-apple-system,"Segoe UI",sans-serif}
h1,h2,h3{font-family:"Bricolage Grotesque","Trebuchet MS",system-ui,sans-serif;margin:0;line-height:1.15}
button,input,select,textarea{font:inherit;color:inherit}
:focus-visible{outline:3px solid var(--accent);outline-offset:2px}
header{background:var(--brand);color:var(--onbrand);padding:14px 20px;display:flex;flex-wrap:wrap;gap:12px;align-items:center;justify-content:space-between}
.brand{font:800 1.5rem "Bricolage Grotesque","Trebuchet MS",sans-serif}
.brand small{display:block;font:400 .85rem "Source Sans 3",system-ui,sans-serif;opacity:.85}
.seg{display:flex;background:rgba(0,0,0,.22);border-radius:10px;padding:3px}
.seg button{border:0;background:none;color:inherit;padding:8px 16px;border-radius:8px;cursor:pointer;font-weight:600}
.seg button[aria-pressed=true]{background:var(--accent);color:#14211C}
main{max-width:1060px;margin:0 auto;padding:20px;display:grid;gap:20px}
@media(min-width:860px){main.teacher{grid-template-columns:340px 1fr;align-items:start}}
.panel{background:var(--surface);border:1px solid var(--line);border-radius:10px;padding:18px}
.panel h2{font-size:1.25rem;margin-bottom:12px}
label{display:block;font-weight:600;margin:12px 0 4px;font-size:.95rem}
input[type=text],select,textarea{width:100%;padding:9px 10px;border:1px solid var(--line);border-radius:8px;background:var(--bg)}
textarea{min-height:110px;resize:vertical}
.chk{display:flex;gap:8px;align-items:center;margin-top:12px;font-weight:400}
.chk input{width:18px;height:18px}
.btn{border:0;border-radius:8px;padding:9px 16px;font-weight:600;cursor:pointer;background:var(--brand);color:var(--onbrand)}
.btn.ghost{background:none;border:1px solid var(--line);color:var(--ink)}
.btn.sm{padding:6px 12px;font-size:.9rem}
.btn:disabled{opacity:.55;cursor:default}
.aud{border:1px solid var(--line);border-radius:8px;margin:12px 0 0;padding:8px 10px}
legend{font-weight:600;padding:0 4px}
.chips{display:flex;flex-wrap:wrap;gap:6px;margin-top:8px}
.chip{display:inline-flex;align-items:center;gap:6px;margin:0;font-weight:400;border:1px solid var(--line);border-radius:99px;padding:3px 10px;cursor:pointer;background:var(--bg)}
.chip input{width:16px;height:16px}
.chip:has(input:checked){border-color:var(--brand);background:var(--brand);color:var(--onbrand)}
.chip.all{font-weight:600}
.feed{display:grid;gap:14px}
.item{background:var(--surface);border:1px solid var(--line);border-left:6px solid var(--muted);border-radius:10px;padding:16px}
.item.Urgent{border-left-color:var(--danger)}.item.Event{border-left-color:var(--brand)}.item.Reminder{border-left-color:var(--accent)}
.item.unread{box-shadow:0 0 0 2px var(--accent)}
.meta{display:flex;flex-wrap:wrap;gap:8px;align-items:center;font-size:.88rem;color:var(--muted);margin-bottom:6px}
.tag{font-weight:600;padding:1px 8px;border-radius:99px;border:1px solid currentColor}
.tag.Urgent{color:var(--danger)}.tag.Event{color:var(--brand)}
.item h3{font-size:1.2rem;margin-bottom:6px}
.item p{margin:0 0 10px;white-space:pre-wrap;max-width:70ch}
.row{display:flex;flex-wrap:wrap;gap:10px;align-items:center}
.bar{height:10px;background:var(--line);border-radius:99px;overflow:hidden;flex:1;min-width:120px}
.bar i{display:block;height:100%;background:var(--ok)}
.stat{font-weight:600;font-size:.92rem}
.recips{list-style:none;margin:12px 0 0;padding:0;display:grid;gap:6px;grid-template-columns:repeat(auto-fill,minmax(230px,1fr))}
.recips li{display:flex;justify-content:space-between;gap:8px;border:1px solid var(--line);border-radius:8px;padding:6px 10px;font-size:.92rem}
.on{color:var(--ok);font-weight:600}.off{color:var(--danger);font-weight:600}
.tabs{display:flex;gap:8px;flex-wrap:wrap;margin-bottom:14px}
.tabs button{border:1px solid var(--line);background:var(--surface);border-radius:99px;padding:6px 14px;cursor:pointer;font-weight:600}
.tabs button[aria-pressed=true]{background:var(--brand);color:var(--onbrand);border-color:var(--brand)}
.empty{padding:28px;text-align:center;color:var(--muted);border:1px dashed var(--line);border-radius:10px}
.note{font-size:.88rem;color:var(--muted);margin-top:10px}
#toast{position:fixed;left:50%;bottom:calc(20px + env(safe-area-inset-bottom,0px));transform:translateX(-50%);background:var(--ink);color:var(--bg);padding:10px 18px;border-radius:10px;opacity:0;pointer-events:none;transition:opacity .2s;max-width:90vw;z-index:5}
#toast.show{opacity:1}
@media(prefers-reduced-motion:reduce){#toast{transition:none}}
</style>
</head>
<body>
<header>
  <div class="brand">NoticeHub<small>SmartCampus · Announcement and Memo Hub</small></div>
  <div class="seg" role="group" aria-label="Switch view">
    <button data-role="teacher" aria-pressed="true">Teacher view</button>
    <button data-role="parent" aria-pressed="false">Parent view</button>
    <button data-role="student" aria-pressed="false">Student view</button>
  </div>
</header>
<main id="app"></main>
<div id="toast" role="status" aria-live="polite"></div>
<script>
(function(){
var KEY="noticehub-v3";
var SECTIONS=["Virchow","Einstein","Bloomberg","Plato","Dell","Mendel","Euclid","Bezos","Newton","Backus","Curie","Aristotle","Dalton","Archimedes & Descartes","Hilbert","Darwin","Thomson","Bernoulli"];
var POOL=["Mrs. Reyes","Mr. Dela Cruz","Mrs. Santos","Mr. Bautista","Mrs. Lim","Mr. Ocampo","Mrs. Garcia","Mr. Tan","Mrs. Villanueva","Mr. Aquino","Mrs. Cruz","Mr. Mendoza"];
var ME="You (parent)", MES="You (student)", MYSEC="Virchow";
var SPOOL=["Ana","Ben","Carlo","Dane","Ella","Francis","Gab","Hana","Ian","Jules","Kim","Leo"];
function slist(s){var i=SECTIONS.indexOf(s),o=[MES];for(var k=0;k<5;k++)o.push(SPOOL[(i*2+k)%SPOOL.length]);return o}
function me(){return S.role==="student"?MES:ME}
function wh(){return S.role==="student"?"Student":"Parent"}
function plist(s){var i=SECTIONS.indexOf(s),o=[ME];for(var k=0;k<5;k++)o.push(POOL[(i*3+k)%POOL.length]);return o}
function pk(s,p){return s+"|"+p}
function audTxt(a){if(a.length===SECTIONS.length)return"all sections";var t=a.slice(0,3).map(esc).join(", ");return a.length>3?a.slice(0,2).map(esc).join(", ")+" +"+(a.length-2)+" more":t}
var H=3600000;
function seed(){
 var n=Date.now(), a=[
 {id:1,title:"Classes suspended tomorrow, Wednesday, Nov 25",body:"Due to the heavy rain warning, there will be no face-to-face classes tomorrow. Teachers will post modules online by 8:00 AM.",cat:"Urgent",aud:SECTIONS.slice(),who:["Parent","Student"],ack:false,t:n-2*H},
 {id:2,title:"Parent-teacher conference on Dec 5",body:"Please attend the conference at 8:00 AM in Room 204 to receive your child's first-semester report card. Tap \"I acknowledge\" so we can plan seating.",cat:"Event",aud:["Virchow","Einstein"],who:["Parent"],ack:true,t:n-26*H},
 {id:3,title:"Research proposal due Nov 30",body:"Groups must submit the printed research proposal to the adviser. Late submissions will lose 10 points.",cat:"Reminder",aud:["Virchow","Plato"],who:["Parent","Student"],ack:false,t:n-50*H}];
 var reads={},pat={1:[1,1,1,0,1,0,1,1,1,1,0,1,1,0,1,1],2:[1,0,1,1,0,1,1,1,0,1,1,0,1,1,1,0],3:[1,1,0,1,1,0,1,0,1,1,1,0,1,1,0,1]};
 a.forEach(function(x){reads[x.id]={};targets(x.aud,x.who).forEach(function(p,i){
  var r=(pat[x.id]||[])[i%16];
  if(p.p===ME||p.p===MES){r=(x.id===3)?1:0}
  if(r){reads[x.id][p.k]={at:x.t+(i+1)*H/2,ack:x.ack&&i%2===0}}
 })});
 return {role:"teacher",items:a,reads:reads,next:4};
}
function targets(aud,who){var o=[];SECTIONS.forEach(function(s){if(aud.indexOf(s)>-1){if(who.indexOf("Parent")>-1)plist(s).forEach(function(p){o.push({s:s,p:p,k:pk(s,p),r:"Parent"})});if(who.indexOf("Student")>-1)slist(s).forEach(function(p){o.push({s:s,p:p,k:pk(s,p),r:"Student"})})}});return o}
var S;try{S=JSON.parse(localStorage.getItem(KEY))}catch(e){S=null}
if(!S||!S.items){S=seed()}
function save(){try{localStorage.setItem(KEY,JSON.stringify(S))}catch(e){}}
function esc(s){return String(s).replace(/[&<>"]/g,function(c){return {"&":"&amp;","<":"&lt;",">":"&gt;",'"':"&quot;"}[c]})}
function ago(t){var m=Math.round((Date.now()-t)/60000);if(m<1)return"just now";if(m<60)return m+" min ago";var h=Math.round(m/60);if(h<24)return h+" h ago";var d=Math.round(h/24);return d+(d===1?" day ago":" days ago")}
function toast(m){var e=document.getElementById("toast");e.textContent=m;e.className="show";clearTimeout(toast.t);toast.t=setTimeout(function(){e.className=""},2600)}
var open={},filter="all";
function counts(x){var ps=targets(x.aud,x.who),r=0,k=0;ps.forEach(function(p){var v=S.reads[x.id]&&S.reads[x.id][p.k];if(v){r++;if(v.ack)k++}});return{total:ps.length,read:r,ack:k,ps:ps}}
function render(){
 var app=document.getElementById("app");
 document.querySelectorAll(".seg button").forEach(function(b){b.setAttribute("aria-pressed",b.dataset.role===S.role)});
 app.className=S.role;
 app.innerHTML=S.role==="teacher"?teacherView():parentView();
}
function teacherView(){
 var opts=SECTIONS.map(function(s){return'<label class="chip"><input type="checkbox" name="sec" value="'+esc(s)+'"> '+esc(s)+'</label>'}).join("");
 var f='<section class="panel"><h2>New announcement</h2><form id="compose" onsubmit="return false">'+
 '<label for="t">Title</label><input type="text" id="t" maxlength="90" placeholder="e.g. Early dismissal on Friday">'+
 '<label for="c">Type</label><select id="c"><option>Memo</option><option>Urgent</option><option>Event</option><option>Reminder</option></select>'+
 '<fieldset class="aud"><legend>Send to (tick one or more)</legend><label class="chip all"><input type="checkbox" id="all"> Select all sections</label><div class="chips">'+opts+'</div></fieldset>'+
 '<fieldset class="aud"><legend>Who receives it</legend><div class="chips"><label class="chip"><input type="checkbox" name="who" value="Parent" checked> Parents</label><label class="chip"><input type="checkbox" name="who" value="Student" checked> Students</label></div></fieldset>'+
 '<label for="b">Message</label><textarea id="b" placeholder="Write the full details here."></textarea>'+
 '<label class="chk"><input type="checkbox" id="k"> Ask parents to acknowledge</label>'+
 '<div class="row" style="margin-top:14px"><button class="btn" id="post">Post announcement</button></div></form>'+
 '<p class="note">Parents and students see this in one place instead of group chats, and you see who has read it.</p></section>';
 var list=S.items.slice().sort(function(a,b){return b.t-a.t}).map(teacherItem).join("");
 return f+'<section><h2 style="margin-bottom:12px">Sent announcements</h2><div class="feed">'+(list||'<div class="empty">Nothing posted yet. Use the form to send your first announcement.</div>')+'</div></section>';
}
function teacherItem(x){
 var c=counts(x),pct=c.total?Math.round(c.read/c.total*100):0,un=c.total-c.read;
 var s='<article class="item '+x.cat+'"><div class="meta"><span class="tag '+x.cat+'">'+x.cat+'</span><span>To '+x.who.map(function(w){return w+"s"}).join(" and ")+' in '+audTxt(x.aud)+'</span><span>'+ago(x.t)+'</span></div><h3>'+esc(x.title)+'</h3><p>'+esc(x.body)+'</p>'+
 '<div class="row"><div class="bar" role="img" aria-label="'+pct+' percent read"><i style="width:'+pct+'%"></i></div><span class="stat">'+c.read+' of '+c.total+' read'+(x.ack?" · "+c.ack+" acknowledged":"")+'</span></div>'+
 '<div class="row" style="margin-top:10px"><button class="btn ghost sm" data-act="toggle" data-id="'+x.id+'">'+(open[x.id]?"Hide receipts":"View receipts")+'</button>'+
 '<button class="btn sm" data-act="remind" data-id="'+x.id+'"'+(un?"":" disabled")+'>Remind '+un+' unread</button>'+
 '<button class="btn ghost sm" data-act="del" data-id="'+x.id+'">Delete</button></div>';
 if(open[x.id]){s+='<ul class="recips">'+c.ps.map(function(p){var v=S.reads[x.id]&&S.reads[x.id][p.k];
  return"<li><span>"+esc(p.p)+' <small>'+p.r+', '+esc(p.s)+'</small></span>'+(v?'<span class="on">'+(x.ack&&v.ack?"Acknowledged":"Read")+" · "+ago(v.at)+"</span>":'<span class="off">Not yet read</span>')+"</li>"}).join("")+"</ul>"}
 return s+"</article>";
}
function mine(){return S.items.filter(function(x){return x.aud.indexOf(MYSEC)>-1&&x.who.indexOf(wh())>-1}).sort(function(a,b){return b.t-a.t})}
function myv(x){return S.reads[x.id]&&S.reads[x.id][pk(MYSEC,me())]}
function parentView(){
 var all=mine(),un=all.filter(function(x){return!myv(x)}).length,need=all.filter(function(x){return x.ack&&!(myv(x)&&myv(x).ack)}).length;
 var list=all.filter(function(x){return filter==="all"||(filter==="unread"&&!myv(x))||(filter==="reply"&&x.ack&&!(myv(x)&&myv(x).ack))});
 var tabs='<div class="tabs" role="group" aria-label="Filter">'+[["all","All ("+all.length+")"],["unread","Unread ("+un+")"],["reply","Needs your reply ("+need+")"]].map(function(t){return'<button data-filter="'+t[0]+'" aria-pressed="'+(filter===t[0])+'">'+t[1]+'</button>'}).join("")+"</div>";
 var items=list.map(function(x){var v=myv(x);
  var s='<article class="item '+x.cat+(v?"":" unread")+'"><div class="meta"><span class="tag '+x.cat+'">'+x.cat+'</span><span>From Adviser, '+MYSEC+'</span><span>'+ago(x.t)+'</span></div><h3>'+esc(x.title)+'</h3><p>'+esc(x.body)+'</p><div class="row">';
  s+=v?'<span class="on">Read '+ago(v.at)+'</span>':'<button class="btn sm" data-act="read" data-id="'+x.id+'">Mark as read</button>';
  if(x.ack){s+=(v&&v.ack)?'<span class="on">Acknowledged</span>':'<button class="btn sm" data-act="ack" data-id="'+x.id+'">I acknowledge</button>'}
  return s+"</div></article>"}).join("");
 return'<section><h2 style="margin-bottom:6px">Announcements for '+esc(MYSEC)+'</h2><label for="vs">View as a '+wh().toLowerCase()+' in section</label><select id="vs" style="max-width:280px">'+SECTIONS.map(function(s){return'<option'+(s===MYSEC?' selected':'')+'>'+esc(s)+'</option>'}).join("")+'</select><p class="note" style="margin:8px 0 14px">Marking a notice as read updates the teacher\u2019s receipts right away.</p>'+tabs+'<div class="feed">'+(items||'<div class="empty">You are all caught up. New announcements will show up here.</div>')+"</div></section>";
}
document.addEventListener("click",function(e){
 if(e.target.id==="all"){document.querySelectorAll("input[name=sec]").forEach(function(i){i.checked=e.target.checked});return}
 var r=e.target.closest("[data-role]");if(r){S.role=r.dataset.role;save();render();return}
 var f=e.target.closest("[data-filter]");if(f){filter=f.dataset.filter;render();return}
 if(e.target.id==="post"){
  var t=document.getElementById("t").value.trim(),b=document.getElementById("b").value.trim();
  var sel=[].slice.call(document.querySelectorAll("input[name=sec]:checked")).map(function(i){return i.value});
  if(!t||!b){toast("Add a title and a message first.");return}
  if(!sel.length){toast("Pick at least one section to send to.");return}
  var wsel=[].slice.call(document.querySelectorAll("input[name=who]:checked")).map(function(i){return i.value});
  if(!wsel.length){toast("Pick parents, students, or both.");return}
  var x={id:S.next++,title:t,body:b,cat:document.getElementById("c").value,aud:sel,who:wsel,ack:document.getElementById("k").checked,t:Date.now()};
  S.items.push(x);S.reads[x.id]={};save();render();toast("Posted to "+audTxt(x.aud)+".");return}
 var a=e.target.closest("[data-act]");if(!a)return;
 var id=+a.dataset.id,act=a.dataset.act,x=S.items.filter(function(i){return i.id===id})[0];
 if(act==="toggle"){open[id]=!open[id]}
 else if(act==="remind"){var n=counts(x).total-counts(x).read;toast("Reminder sent to "+n+" parent"+(n===1?"":"s")+".");return}
 else if(act==="del"){S.items=S.items.filter(function(i){return i.id!==id});delete S.reads[id]; toast("Announcement deleted.")}
 else if(act==="read"){S.reads[id]=S.reads[id]||{};S.reads[id][pk(MYSEC,me())]={at:Date.now(),ack:false};toast("Marked as read.")}
 else if(act==="ack"){S.reads[id]=S.reads[id]||{};var v=S.reads[id][pk(MYSEC,me())]||{at:Date.now()};v.ack=true;S.reads[id][pk(MYSEC,me())]=v;toast("Acknowledged.")}
 save();render();
});
document.addEventListener("change",function(e){
 if(e.target.id==="vs"){MYSEC=e.target.value;render();return}
 if(e.target.name==="sec"){var all=document.getElementById("all");if(all)all.checked=document.querySelectorAll("input[name=sec]:checked").length===SECTIONS.length}
});
render();
})();
</script>
</body>
</html>
