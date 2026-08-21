<html lang="ru">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">
<title>Menti-Meter — живая социология</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Geologica:wght@300;400;600&family=Rubik:wght@500;700;900&display=swap" rel="stylesheet">
<style>
:root{
  --creme:#F0EADC;
  --green:#153825;
  --olive:#C7CC51;
  --sky:#36BDC2;
  --coral:#EF454E;
  --lav:#B296DD;
  --surface:#FFFFFF;
  --line:rgba(21,56,36,.16);
  --soft:rgba(21,56,36,.55);
  --display:'Geologica',system-ui,sans-serif;
  --body:'Geologica',system-ui,sans-serif;
}
*{box-sizing:border-box}
html,body{margin:0;padding:0}
body{
  background:var(--creme);color:var(--green);
  font-family:var(--body);font-weight:300;line-height:1.5;
  -webkit-font-smoothing:antialiased;min-height:100vh;
}
h1,h2,h3,.disp{font-family:var(--display);font-weight:900;letter-spacing:-.005em}
button{font-family:var(--display);font-weight:900;cursor:pointer}
input,textarea{font-family:var(--body);font-weight:400}
:focus-visible{outline:3px solid var(--sky);outline-offset:2px}
@media (prefers-reduced-motion:reduce){*{animation:none!important;transition:none!important}}

.eyebrow{font-family:var(--display);font-weight:900;font-size:14px;color:var(--green);text-transform:lowercase}

/* ---------- home ---------- */
.home{max-width:940px;margin:0 auto;padding:52px 22px 80px}
.lockup{line-height:.85;margin:22px 0 18px}
.lockup .w1{display:block;font-family:var(--display);font-weight:900;font-size:clamp(36px,6.6vw,66px);color:var(--sky)}
.lockup .w2{display:block;font-family:var(--display);font-weight:900;font-size:clamp(30px,5.4vw,54px);color:var(--green)}
.home p.lead{font-size:17px;max-width:52ch;margin:0 0 38px;color:var(--green)}
.cards{display:grid;gap:16px;grid-template-columns:repeat(auto-fit,minmax(280px,1fr))}
.card{background:var(--surface);border-radius:18px;padding:26px 24px 24px}
.card h2{margin:0 0 8px;font-size:22px;text-transform:lowercase}
.card p{margin:0 0 18px;color:var(--soft);font-size:14.5px}
.field{display:flex;gap:9px}
.field input{
  flex:1;min-width:0;border:2px solid var(--line);background:var(--creme);border-radius:12px;
  padding:12px 14px;font-size:18px;font-weight:600;letter-spacing:.14em;text-transform:uppercase;color:var(--green)
}
.btn{
  border:none;border-radius:12px;background:var(--green);color:var(--creme);
  font-size:15px;padding:13px 22px;text-transform:lowercase;transition:transform .12s ease
}
.btn:hover{transform:translateY(-1px)}
.btn:active{transform:translateY(0)}
.btn.ghost{background:transparent;color:var(--green);box-shadow:inset 0 0 0 2px var(--line)}
.btn.sky{background:var(--sky);color:var(--green)}
.btn:disabled{opacity:.4;cursor:not-allowed;transform:none}
.hint{font-size:13px;color:var(--soft);margin-top:14px}

/* ---------- presenter ---------- */
.shell{max-width:1200px;margin:0 auto;padding:16px 16px 40px}
.bar{display:flex;align-items:center;gap:10px;flex-wrap:wrap;margin-bottom:12px}
.bar .grow{flex:1}
.pill{
  background:var(--surface);border-radius:999px;padding:9px 16px;font-size:13px;
  font-family:var(--display);font-weight:900;display:flex;align-items:center;gap:8px;text-transform:lowercase
}
.pill b{font-size:16px;letter-spacing:.16em}
.pill .dot{width:9px;height:9px;border-radius:50%;background:var(--sky)}
.iconbtn{
  border:none;background:var(--surface);border-radius:12px;width:44px;height:44px;
  font-size:19px;color:var(--green);display:flex;align-items:center;justify-content:center
}
.iconbtn:disabled{opacity:.35;cursor:not-allowed}
.slide{
  background:var(--surface);border-radius:16px;padding:clamp(24px,4vw,54px);
  min-height:min(74vh,650px);display:flex;flex-direction:column;position:relative
}
.slide h2.q{font-size:clamp(23px,3.1vw,42px);line-height:1.04;margin:0;max-width:20ch}
.slide .body{flex:1;display:flex;flex-direction:column;justify-content:center;padding:32px 0 6px;min-height:0}
.slideno{position:absolute;right:24px;bottom:18px;font-size:12.5px;color:var(--soft);font-weight:400}

/* title slide */
.title-slide{background:var(--creme);display:grid;grid-template-columns:1.15fr .85fr;gap:30px;align-items:center}
.title-slide .tl{display:flex;flex-direction:column;height:100%;justify-content:center}
.title-slide .lockup .w1{font-size:clamp(34px,5.6vw,64px)}
.title-slide .lockup .w2{font-size:clamp(27px,4.4vw,50px)}
.title-slide .sub{font-size:clamp(15px,1.7vw,20px);max-width:28ch;margin-top:14px}
.title-slide .foot{margin-top:26px;font-family:var(--display);font-weight:900;font-size:15px;color:var(--sky)}
.title-slide img.mascot{width:100%;max-width:380px;height:auto;justify-self:center;display:block}
@media(max-width:760px){.title-slide{grid-template-columns:1fr}.title-slide img.mascot{max-width:200px}}

/* ---------- viz ---------- */
.dotgrid{display:grid;grid-template-columns:repeat(2,1fr);grid-auto-rows:1fr;gap:26px 46px;flex:1;min-height:0}
@media(max-width:640px){.dotgrid{grid-template-columns:1fr;grid-auto-rows:auto;gap:18px}}
.dotcell{display:grid;grid-template-rows:1fr auto;min-height:0}
.dotcell .art{display:flex;justify-content:center;align-items:flex-end;min-height:96px;padding-bottom:12px}
.dotcell .art svg{max-height:150px;height:auto;width:auto;max-width:100%}
.optrow{display:flex;gap:14px;align-items:flex-start;border-top:1px solid var(--line);padding-top:11px;min-height:4.8em}
.optrow .n{font-family:var(--display);font-weight:900;font-size:17px;min-width:24px;text-align:right}
.optrow .t{font-size:15.5px;line-height:1.35}

.bars{display:grid;gap:18px;flex:1;min-height:210px;align-items:stretch}
.barcol{display:grid;grid-template-rows:1fr auto;min-height:0}
.barstack{display:flex;flex-direction:column;justify-content:flex-end;min-height:0}
.barcol .cnt{font-family:var(--display);font-weight:900;font-size:28px;margin-bottom:8px}
.barcol .bar-rect{border-radius:6px 6px 0 0;min-height:4px;transition:height .5s cubic-bezier(.4,0,.2,1)}
.barcol .lbl{font-size:14.5px;line-height:1.35;padding-top:12px;min-height:4.8em}

.donutwrap{display:flex;gap:44px;align-items:center;flex-wrap:wrap;justify-content:center}
.donutwrap svg{width:min(300px,50vw);height:auto}
.legend{flex:1;min-width:250px;max-width:520px}
.legend .lrow{display:flex;gap:14px;align-items:flex-start;padding:11px 0;border-bottom:1px solid var(--line)}
.legend .sw{width:14px;height:14px;border-radius:3px;margin-top:5px;flex:none}
.legend .n{font-family:var(--display);font-weight:900;min-width:18px}
.legend .t{font-size:15px;line-height:1.35}

.scalebox{padding-left:2px}
.scalerow{margin-bottom:30px}
.scalerow .st{font-size:clamp(15px,1.8vw,20px);margin-bottom:10px;line-height:1.35}
.scalerow .stn{display:inline-block;margin-left:10px;font-family:var(--display);font-weight:900;font-size:12px;color:var(--soft)}
svg.curve{display:block;width:100%;height:auto;overflow:visible}
.track{position:relative;height:12px;background:rgba(21,56,36,.1);border-radius:99px}
.marker{position:absolute;top:0;height:12px;width:22px;border-radius:99px;transform:translateX(-50%);transition:left .5s cubic-bezier(.4,0,.2,1)}
.ends{display:flex;justify-content:space-between;color:var(--soft);font-family:var(--display);font-weight:900;font-size:13px;margin-top:20px;text-transform:lowercase}

.rankrow{margin-bottom:14px}
.rankrow .rl{display:flex;align-items:baseline;gap:12px;font-size:15.5px;margin-bottom:6px}
.rankrow .rnum{font-family:var(--display);font-weight:900;color:var(--soft);min-width:18px}
.rankrow .rtxt{flex:1}
.rankrow .ravg{font-size:13px;color:var(--soft);white-space:nowrap}
.rankrow .rt{height:13px;background:rgba(21,56,36,.1);border-radius:99px;overflow:hidden}
.rankrow .rf{height:100%;border-radius:99px;transition:width .5s cubic-bezier(.4,0,.2,1)}

.cloud{display:flex;flex-wrap:wrap;gap:4px 22px;align-items:center;justify-content:center;line-height:1}
.cloud span{font-family:var(--display);font-weight:900}

.notes{display:grid;grid-template-columns:repeat(auto-fill,minmax(230px,1fr));gap:12px;align-content:start;overflow:auto}
.note{background:var(--creme);border-radius:12px;padding:14px 15px;font-size:15px;line-height:1.45}
.note .votes{margin-top:10px;font-size:13px;font-family:var(--display);font-weight:900;color:var(--soft)}
.empty{color:var(--soft);font-size:15px;text-align:center}

/* ---------- participant ---------- */
.pwrap{max-width:620px;margin:0 auto;padding:16px 16px 60px}
.ptop{display:flex;align-items:center;gap:10px;margin-bottom:16px}
.qcard{background:var(--surface);border-radius:18px;padding:24px 20px}
.qcard h2{font-size:clamp(21px,5vw,28px);line-height:1.08;margin:0 0 20px}
.opt{
  display:block;width:100%;text-align:left;background:var(--creme);border:none;
  border-radius:13px;padding:15px 16px;font-family:var(--body);font-weight:400;font-size:16px;
  line-height:1.4;margin-bottom:10px;color:var(--green);box-shadow:inset 0 0 0 2px transparent;
  transition:background .15s,color .15s
}
.opt[aria-pressed="true"]{background:var(--green);color:var(--creme)}
.slider-block{margin-bottom:26px}
.slider-block .st{font-size:16.5px;line-height:1.35;margin-bottom:12px}
input[type=range]{width:100%;-webkit-appearance:none;background:transparent;height:34px}
input[type=range]::-webkit-slider-runnable-track{height:12px;background:rgba(21,56,36,.1);border-radius:99px}
input[type=range]::-webkit-slider-thumb{-webkit-appearance:none;width:30px;height:30px;border-radius:50%;background:var(--sky);margin-top:-9px;border:4px solid var(--surface);box-shadow:0 0 0 2px var(--green)}
input[type=range]::-moz-range-track{height:12px;background:rgba(21,56,36,.1);border-radius:99px}
input[type=range]::-moz-range-thumb{width:24px;height:24px;border:4px solid var(--surface);border-radius:50%;background:var(--sky);box-shadow:0 0 0 2px var(--green)}
.endlbl{display:flex;justify-content:space-between;gap:12px;font-size:12px;line-height:1.3;color:var(--soft)}
textarea.free{width:100%;border:2px solid var(--line);border-radius:13px;padding:14px;font-size:16px;min-height:120px;resize:vertical;background:var(--creme);color:var(--green)}
input.word{width:100%;border:2px solid var(--line);border-radius:13px;padding:14px;font-size:16px;background:var(--creme);color:var(--green)}
.counter{font-size:12.5px;color:var(--soft);text-align:right;margin:6px 0 12px}
.ranklist{list-style:none;margin:0 0 16px;padding:0}
.ranklist li{display:flex;align-items:center;gap:10px;background:var(--creme);border-radius:13px;padding:11px 12px;margin-bottom:9px}
.ranklist .pos{font-family:var(--display);font-weight:900;width:22px;color:var(--soft)}
.ranklist .txt{flex:1;font-size:15.5px;line-height:1.3}
.mv{border:none;background:var(--surface);border-radius:9px;width:36px;height:36px;font-size:15px;color:var(--green)}
.mv:disabled{opacity:.3;cursor:not-allowed}
.saved{margin-top:14px;font-family:var(--display);font-weight:900;font-size:14px;color:var(--sky)}
.chiplist{display:flex;flex-wrap:wrap;gap:8px;margin-top:14px}
.chip{background:var(--creme);border-radius:99px;padding:8px 15px;font-size:14px}
.votebtn{display:flex;align-items:flex-start;gap:9px;background:var(--creme);border:none;border-radius:12px;padding:12px 14px;width:100%;text-align:left;margin-bottom:9px;font-family:var(--body);font-weight:400;font-size:15px;line-height:1.4;color:var(--green);box-shadow:inset 0 0 0 2px transparent}
.votebtn[aria-pressed="true"]{box-shadow:inset 0 0 0 2px var(--sky)}
.waiting{text-align:center;padding:34px 10px;color:var(--soft);font-size:16px}
.waiting img{width:120px;height:auto;margin-bottom:18px}
.err{color:var(--coral);font-size:14px;font-family:var(--display);font-weight:900;margin-top:14px}
.iconbtn.sm{width:40px;height:40px;font-size:17px}
.followbar{display:block;width:100%;border:none;background:var(--sky);color:var(--green);border-radius:12px;padding:11px;font-size:14px;margin-bottom:12px;text-transform:lowercase}
.warn{background:var(--coral);color:var(--creme);border-radius:12px;padding:12px 14px;font-family:var(--body);font-weight:400;font-size:13.5px;line-height:1.45;margin-bottom:12px}
h3.sub-h{font-family:var(--display);font-weight:900;font-size:15px;margin:26px 0 10px;text-transform:lowercase}
</style>
</head>
<body>
<div id="app"></div>

<script>
const MASCOT_SRC = "data:image/png;base64,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";

/* ================= deck ================= */
const DECK = [
  {type:'title'},
  {id:1,type:'mc',viz:'dots',q:'Идеальный Израиль — это где…',opts:[
    'Государство отдельно, религия отдельно. Хочешь соблюдать — соблюдай',
    'Мы бережем еврейские традиции и культуру, но пусть это не влияет на решения в личной жизни',
    'Пусть всё остаётся как сейчас, привыкли уже',
    'Побольше Галахи в законах, это всё-таки еврейское государство']},
  {id:2,type:'mc',viz:'bars',q:'Ты хочешь пожениться. Как это должно работать?',opts:[
    'Гражданский брак для всех, хупа для тех, кто хочет',
    'Пусть хотя бы реформисты и консерваторы могут регистрировать',
    'Только ортодоксальная хупа, как иначе']},
  {id:3,type:'scale',q:'Автобусы в шаббат:',stmts:[
    'Должны ходить как в любой другой день',
    'Пусть каждый город решает сам',
    'Шаббат есть шаббат. Никаких автобусов']},
  {id:4,type:'mc',viz:'dots',q:'Что думаешь про студентов йешив и службу в армии:',opts:[
    'Призывать всех. Никаких исключений',
    'Призывать по квотам, кому совсем никак — гражданская служба',
    'Не хотят служить — пусть не получают денег от государства',
    'Пусть учат Тору, это важный вклад для страны']},
  {id:5,type:'open',q:'Большая сделка: Саудовская Аравия признаёт Израиль, США даёт гарантии безопасности, но в перспективе — палестинское государство. Что делаем?'},
  {id:6,type:'mc',viz:'donut',q:'БАГАЦ отменяет решения правительства. Это:',opts:[
    'Единственный тормоз для несправедливых законов, который у нас есть. Не трогать',
    'Штука нужная, но полномочия стоило бы прописать точнее',
    'Судьи слишком много себе позволяют. Ограничить']},
  {id:7,type:'scale',q:'Что важнее?',stmts:[
    'Чтобы власть менялась. Даже если следующие лидеры окажутся хуже',
    'Чтобы во главе стоял сильный лидер. Даже если надолго']},
  {id:8,type:'mc',viz:'dots',q:'Государство должно считать евреем:',opts:[
    'Только по Галахе: мама-еврейка или ортодоксальный гиюр',
    'Ещё и детей отцов-евреев. Это же очевидно',
    'Всех, кто сам себя считает евреем и живёт здесь',
    'Государству вообще не надо разбираться, кто чей внук']},
  {id:9,type:'words',q:'Чего новому репатрианту не хватает больше всего? Впиши свой вариант'},
  {id:10,type:'rank',q:'Первое, чем должно заняться следующее правительство. Расставь в приоритете',items:[
    'Дороговизна жизни','Безопасность','Религия и государство, призыв харедим',
    'Полномочия судов','Коррупция','Медицина, школы, соцслужбы','Раскол в обществе']}
];
const PAL=['#36BDC2','#C7CC51','#EF454E','#B296DD'];
const ON=['#153825','#153825','#F0EADC','#153825'];

/* ================= storage =================
   Чтобы синхронизация работала на любом устройстве и с любого хостинга,
   впиши сюда адрес своей базы Firebase Realtime Database, например:
   const SYNC_URL = "https://fair-choice-default-rtdb.europe-west1.firebasedatabase.app";
   Пусто — используется встроенное хранилище Claude (работает не везде).      */
const SYNC_URL = "https://menti-meter-fair-choice-default-rtdb.europe-west1.firebasedatabase.app";

const mem={};
const hasStore = typeof window!=='undefined' && window.storage && typeof window.storage.list==='function';
const BASE = SYNC_URL ? SYNC_URL.replace(/\/$/,'') : '';
const TRANSPORT = SYNC_URL ? 'внешняя база' : (hasStore ? 'хранилище Claude' : 'только эта вкладка');
const FB = {
  u(k){ return BASE+'/mm/'+encodeURIComponent(k.replace(/:/g,'~'))+'.json' },
  async list(prefix){
    const r=await fetch(BASE+'/mm.json?shallow=true');
    const d=await r.json();
    return Object.keys(d||{}).map(x=>x.replace(/~/g,':')).filter(x=>x.indexOf(prefix)===0);
  },
  async get(k){ const r=await fetch(this.u(k)); const d=await r.json(); return d===null||d===undefined?null:String(d) },
  async set(k,v){ const r=await fetch(this.u(k),{method:'PUT',body:JSON.stringify(String(v))}); if(!r.ok) throw new Error('put'); return true },
  async del(k){ await fetch(this.u(k),{method:'DELETE'}); return true }
};
const S={
  async list(prefix,shared=true){
    if(SYNC_URL){ try{ St.netErr=false; return await FB.list(prefix) }catch(e){ St.netErr=true; return [] } }
    if(!hasStore) return Object.keys(mem).filter(k=>k.startsWith(prefix));
    try{ const r=await window.storage.list(prefix,shared);
      return (r&&r.keys?r.keys:[]).map(k=>typeof k==='string'?k:(k&&k.key)||''); }catch(e){ return [] }
  },
  async get(k,shared=true){
    if(SYNC_URL){ try{ const v=await FB.get(k); St.netErr=false; return v }catch(e){ St.netErr=true; return null } }
    if(!hasStore) return k in mem?mem[k]:null;
    try{ const r=await window.storage.get(k,shared); St.netErr=false; return r?r.value:null }
    catch(e){
      try{ const r2=await window.storage.get(k,shared); return r2?r2.value:null }catch(e2){ return null }
    }
  },
  async set(k,v,shared=true){
    if(SYNC_URL){
      for(let i=0;i<3;i++){
        try{ await FB.set(k,v); St.netErr=false; return true }
        catch(e){ await new Promise(r=>setTimeout(r,450*(i+1))) }
      }
      St.netErr=true; return false;
    }
    if(!hasStore){ mem[k]=v; return true }
    for(let i=0;i<3;i++){
      try{ await window.storage.set(k,v,shared); St.netErr=false; return true }
      catch(e){ await new Promise(r=>setTimeout(r,450*(i+1))) }
    }
    St.netErr=true; return false;
  },
  async del(k,shared=true){
    if(SYNC_URL){ try{ await FB.del(k) }catch(e){} return true }
    if(!hasStore){ delete mem[k]; return true }
    try{ await window.storage.delete(k,shared); return true }catch(e){ return false }
  }
};
function enc(s){ return encodeURIComponent(s).replace(/[!'()*~.]/g,c=>'%'+c.charCodeAt(0).toString(16).toUpperCase()) }
function dec(s){ try{ return decodeURIComponent(s) }catch(e){ return s } }

/* ================= state ================= */
const St={mode:null,code:'',pid:'',cur:0,answers:{},votes:{},openKeys:[],openText:{},people:new Set(),mine:{},timer:null,busy:false,nkeys:0,sig:'',netErr:false,follow:true};
const K=p=>'mm:'+St.code+':'+p;

function devTag(){
  const s=(navigator.userAgent||'')+'|'+(screen.width||0)+'x'+(screen.height||0)+'|'+(navigator.platform||'');
  let x=5381; for(let i=0;i<s.length;i++){ x=((x*33)^s.charCodeAt(i))>>>0 }
  return x.toString(36).slice(0,4);
}
async function ensurePid(){
  if(St.pid) return St.pid;
  let v=null;
  if(hasStore){ try{ const r=await window.storage.get('mm:pid',false); v=r?r.value:null }catch(e){} }
  if(!v){ v=Math.random().toString(36).slice(2,8); if(hasStore){ try{ await window.storage.set('mm:pid',v,false) }catch(e){} } }
  St.pid=v+devTag(); return St.pid;
}
async function pull(){
  const keys=await S.list('mm:'+St.code+':');
  const ans={},votes={},oks=[],ppl=new Set(),mine={};
  for(const k of keys){
    const p=k.split(':'), kind=p[2];
    if(kind==='a'){
      const qid=p[3], pid=p[4], payload=p.slice(5).join(':');
      if(qid.charAt(0)==='v'){
        const q=qid.slice(1);
        (votes[q]=votes[q]||[]).push({pid,target:payload});
        if(pid===St.pid) mine['v'+q]=payload;
      }else{
        (ans[qid]=ans[qid]||[]).push({pid,payload});
        if(pid===St.pid){ if(qid==='9'){ (mine[qid]=mine[qid]||[]).push(payload) } else mine[qid]=payload }
      }
      ppl.add(pid);
    }else if(kind==='o'){ const rid=p[4]; oks.push(rid); ppl.add(rid.split('-')[0]) }
    else if(kind==='p'){ ppl.add(p[3]) }
  }
  St.answers=ans; St.votes=votes; St.openKeys=oks; St.people=ppl; St.mine=mine; St.nkeys=keys.length;
  const missing=oks.filter(r=>!(r in St.openText)).slice(0,40);
  for(const r of missing){ St.openText[r]=await S.get(K('o:5:'+r))||'' }
}

/* ================= tallies ================= */
function tally(q){
  const list=St.answers[String(q.id)]||[];
  if(q.type==='mc'){ const c=q.opts.map(()=>0);
    list.forEach(a=>{ const i=parseInt(a.payload,10); if(i>=0&&i<c.length) c[i]++ }); return c }
  if(q.type==='scale'){ const s=q.stmts.map(()=>0), n=q.stmts.map(()=>0);
    list.forEach(a=>a.payload.split('-').forEach((v,i)=>{ const x=parseInt(v,10); if(!isNaN(x)&&i<s.length){ s[i]+=x; n[i]++ } }));
    return s.map((x,i)=>n[i]?x/n[i]:null) }
  if(q.type==='rank'){ const N=q.items.length, sc=q.items.map(()=>0);
    list.forEach(a=>a.payload.split('-').forEach((v,pos)=>{ const i=parseInt(v,10); if(i>=0&&i<N) sc[i]+=(N-pos) })); return sc }
  if(q.type==='words'){ const m={};
    list.forEach(a=>{ const w=dec(a.payload).trim(); if(w) m[w]=(m[w]||0)+1 });
    return Object.entries(m).sort((a,b)=>b[1]-a[1]).slice(0,32) }
  return [];
}
function voteCount(rid){ return (St.votes['5']||[]).filter(v=>v.target===rid).length }

/* ================= viz ================= */
function dots(n,color){
  n=Math.min(n,60);
  if(n===0) return '<svg viewBox="0 0 10 10" style="width:10px"></svg>';
  const gap=30,r=12.5,cols=Math.max(1,Math.ceil(Math.sqrt(n*1.2))),rows=Math.ceil(n/cols);
  const w=cols*gap+gap,h=rows*gap*0.9+gap;
  let s='';
  for(let i=0;i<n;i++){
    const row=Math.floor(i/cols),col=i%cols,inRow=Math.min(cols,n-row*cols);
    const off=(cols-inRow)*gap/2+(row%2?gap*0.28:0);
    s+='<circle cx="'+(off+col*gap+gap/2)+'" cy="'+(row*gap*0.9+gap/2)+'" r="'+r+'" fill="'+color+'"/>';
  }
  return '<svg viewBox="0 0 '+w+' '+h+'" width="'+w+'" height="'+h+'">'+s+'</svg>';
}
function esc(s){ return String(s).replace(/[&<>"]/g,c=>({'&':'&amp;','<':'&lt;','>':'&gt;','"':'&quot;'}[c])) }

function renderMC(q){
  const c=tally(q), total=c.reduce((a,b)=>a+b,0);
  if(q.viz==='dots'){
    return '<div class="dotgrid">'+q.opts.map((o,i)=>
      '<div class="dotcell"><div class="art">'+dots(c[i],PAL[i%4])+'</div>'+
      '<div class="optrow"><span class="n">'+c[i]+'</span><span class="t">'+esc(o)+'</span></div></div>').join('')+'</div>';
  }
  if(q.viz==='bars'){
    const max=Math.max(1,...c);
    return '<div class="bars" style="grid-template-columns:repeat('+q.opts.length+',1fr)">'+q.opts.map((o,i)=>
      '<div class="barcol"><div class="barstack"><div class="cnt">'+c[i]+'</div>'+
      '<div class="bar-rect" style="height:'+(c[i]/max*100)+'%;background:'+PAL[i%4]+'"></div></div>'+
      '<div class="lbl">'+esc(o)+'</div></div>').join('')+'</div>';
  }
  const R=112,SW=54,C=2*Math.PI*R;
  let acc=0,arcs='',labels='';
  q.opts.forEach((o,i)=>{
    const val=total?c[i]/total:0,len=val*C;
    arcs+='<circle r="'+R+'" cx="0" cy="0" fill="none" stroke="'+PAL[i%4]+'" stroke-width="'+SW+
      '" stroke-dasharray="'+len+' '+(C-len)+'" stroke-dashoffset="'+(-acc*C)+'" transform="rotate(-90)"/>';
    if(c[i]>0){
      const mid=(acc+val/2)*2*Math.PI-Math.PI/2;
      labels+='<text x="'+(Math.cos(mid)*R)+'" y="'+(Math.sin(mid)*R)+'" text-anchor="middle" dominant-baseline="central" font-family="Rubik,sans-serif" font-size="26" font-weight="900" fill="'+ON[i%4]+'">'+c[i]+'</text>';
    }
    acc+=val;
  });
  return '<div class="donutwrap"><svg viewBox="-150 -150 300 300">'+
    (total?arcs+labels:'<circle r="'+R+'" fill="none" stroke="rgba(21,56,36,.1)" stroke-width="'+SW+'"/>')+'</svg>'+
    '<div class="legend">'+q.opts.map((o,i)=>
      '<div class="lrow"><span class="sw" style="background:'+PAL[i%4]+'"></span><span class="n">'+c[i]+'</span><span class="t">'+esc(o)+'</span></div>').join('')+'</div></div>';
}
function curve(arr,color){
  const W=1000,H=118,base=H-10;
  const track='<rect x="0" y="'+(base-6)+'" width="1000" height="12" rx="6" fill="rgba(21,56,36,.09)"/>';
  if(!arr.length) return '<svg class="curve" viewBox="0 0 1000 118">'+track+'</svg>';
  const h=Math.max(6.5,34/Math.sqrt(arr.length));
  const pts=[]; let max=0;
  for(let x=0;x<=100;x++){
    let d=0;
    for(const v of arr){ const z=(x-v)/h; d+=Math.exp(-0.5*z*z) }
    pts.push(d); if(d>max) max=d;
  }
  let path='M 0 '+base;
  pts.forEach((d,x)=>{ path+=' L '+(x*10).toFixed(1)+' '+(base-(d/max)*(base-16)).toFixed(1) });
  path+=' L 1000 '+base+' Z';
  const mean=arr.reduce((a,b)=>a+b,0)/arr.length;
  return '<svg class="curve" viewBox="0 0 1000 118">'+track+
    '<path d="'+path+'" fill="'+color+'" opacity=".92"/>'+
    '<line x1="'+(mean*10).toFixed(1)+'" y1="8" x2="'+(mean*10).toFixed(1)+'" y2="'+(base+5)+
      '" stroke="var(--green)" stroke-width="2.5" stroke-dasharray="6 6"/></svg>';
}
function renderScale(q){
  const list=St.answers[String(q.id)]||[];
  const vals=q.stmts.map(()=>[]);
  list.forEach(a=>a.payload.split('-').forEach((v,i)=>{
    const x=parseInt(v,10); if(!isNaN(x)&&i<vals.length) vals[i].push(x);
  }));
  return '<div class="scalebox">'+q.stmts.map((s,i)=>
    '<div class="scalerow"><div class="st">'+esc(s)+
      (vals[i].length?'<span class="stn">'+vals[i].length+'</span>':'')+'</div>'+
      curve(vals[i],PAL[i%4])+'</div>').join('')+
    '<div class="ends"><span>безусловно не согласны</span><span>безусловно согласны</span></div></div>';
}
function renderRank(q){
  const list=St.answers[String(q.id)]||[], N=q.items.length, sc=tally(q);
  const avg=q.items.map((_,i)=>{
    let s=0,n=0;
    list.forEach(a=>{ const pos=a.payload.split('-').map(Number).indexOf(i); if(pos>=0){ s+=pos+1; n++ } });
    return n? s/n : null;
  });
  const order=q.items.map((_,i)=>i).sort((a,b)=>sc[b]-sc[a]);
  const max=Math.max(1,...sc);
  return '<div>'+order.map((i,place)=>
    '<div class="rankrow"><div class="rl"><span class="rnum">'+(place+1)+'</span>'+
      '<span class="rtxt">'+esc(q.items[i])+'</span>'+
      (avg[i]===null?'':'<span class="ravg">ср. место '+avg[i].toFixed(1).replace('.',',')+'</span>')+'</div>'+
    '<div class="rt"><div class="rf" style="width:'+(sc[i]/max*100)+'%;background:'+PAL[place%4]+'"></div></div></div>').join('')+'</div>';
}
function renderWords(q){
  const w=tally(q);
  if(!w.length) return '<div class="empty">Ответы появятся здесь</div>';
  const max=w[0][1];
  return '<div class="cloud">'+w.map(([word,n],i)=>
    '<span style="font-size:'+(22+Math.round(Math.sqrt(n/max)*58))+'px;color:'+PAL[i%4]+'" title="'+n+'">'+esc(word)+'</span>').join('')+'</div>';
}
function renderOpen(){
  if(!St.openKeys.length) return '<div class="empty">Ответы появятся здесь. До 200 знаков, можно отправить несколько</div>';
  const rows=St.openKeys.map(r=>({r,t:St.openText[r]||'',v:voteCount(r)})).filter(x=>x.t).sort((a,b)=>b.v-a.v);
  return '<div class="notes">'+rows.map(x=>'<div class="note">'+esc(x.t)+(x.v?'<div class="votes">♥ '+x.v+'</div>':'')+'</div>').join('')+'</div>';
}
function renderResults(q){
  if(q.type==='mc') return renderMC(q);
  if(q.type==='scale') return renderScale(q);
  if(q.type==='rank') return renderRank(q);
  if(q.type==='words') return renderWords(q);
  if(q.type==='open') return renderOpen();
  return '';
}

/* ================= screens ================= */
const app=document.getElementById('app');
function sigP(){ return 'p|'+St.cur+'|'+St.nkeys+'|'+St.people.size+'|'+Object.keys(St.openText).length+'|'+(St.netErr?1:0) }
function sigJ(){ return 'j|'+St.cur+'|'+JSON.stringify(St.mine)+'|'+St.openKeys.length+'|'+(St.votes['5']||[]).length+'|'+(St.netErr?1:0) }

function home(){
  const suggested=String(Math.floor(100000+Math.random()*900000));
  app.innerHTML=
  '<div class="home">'+
  '<div class="lockup"><span class="w1">Menti-Meter</span><span class="w2">живая социология</span></div>'+
  '<p class="lead">Отвечай на вопросы и смотри, как распределяются позиции людей в зале в лайв режиме.</p>'+
  '<div class="cards">'+
    '<div class="card"><h2>веду презентацию</h2><p>Экран для проектора: вопросы и результаты, которые обновляются на глазах.</p>'+
      '<div class="field"><input id="pcode" value="'+suggested+'" maxlength="8" aria-label="Код сессии"><button class="btn" id="pgo">открыть</button></div>'+
      '<div class="hint">Код можно поменять на любой. Скажи его залу.</div></div>'+
    '<div class="card"><h2>я в зале</h2><p>Отвечаю с телефона. Экран сам переключится на тот вопрос, который показывает ведущий.</p>'+
      '<div class="field"><input id="jcode" placeholder="КОД" maxlength="8" aria-label="Код сессии"><button class="btn sky" id="jgo">войти</button></div>'+
      '<div class="hint">Одна и та же ссылка — и для зала, и для проектора.</div></div>'+
  '</div>'+
  ((hasStore||SYNC_URL)?'':'<div class="err">Общее хранилище недоступно: ответы видны только в этой вкладке. Впиши SYNC_URL в коде файла.</div>')+'</div>';
  document.getElementById('pgo').onclick=()=>start('present',document.getElementById('pcode').value);
  document.getElementById('jgo').onclick=()=>start('join',document.getElementById('jcode').value);
  document.getElementById('jcode').addEventListener('keydown',e=>{ if(e.key==='Enter') document.getElementById('jgo').click() });
}

async function start(mode,code){
  code=(code||'').toUpperCase().replace(/[^A-Z0-9]/g,'').slice(0,8);
  if(!code){ alert('Введи код сессии'); return }
  St.mode=mode; St.code=code; St.cur=0;
  await ensurePid();
  if(mode==='present'){ await S.set(K('cur'),'0'); await pull(); drawPresent(true); loop() }
  else{
    await S.set(K('p:'+St.pid),'1');
    const c=await S.get(K('cur')); St.cur=parseInt(c||'0',10)||0;
    await pull(); drawJoin(true); loop();
  }
}
async function tick(force){
  if(St.busy||!St.mode) return; St.busy=true;
  try{
    if(St.mode==='present'){ await pull(); drawPresent(!!force) }
    else{
      const c=await S.get(K('cur')); const n=parseInt(c||'0',10)||0;
      const q=DECK[St.cur];
      const needFull = n!==St.cur || force || (q&&(q.type==='open'||q.type==='words'));
      if(n!==St.cur) St.cur=n;
      if(needFull) await pull();
      drawJoin(!!force);
    }
  }finally{ St.busy=false }
}
function loop(){ clearInterval(St.timer); St.timer=setInterval(()=>{ if(!document.hidden) tick() },3000) }
document.addEventListener('visibilitychange',()=>{ if(!document.hidden) tick() });
window.addEventListener('focus',()=>tick());
window.addEventListener('pageshow',()=>tick());

function drawPresent(force){
  const s=sigP(); if(!force && s===St.sig) return; St.sig=s;
  const q=DECK[St.cur], scroll=window.scrollY;
  app.innerHTML=
  '<div class="shell"><div class="bar">'+
    '<button class="pill" id="diag" style="border:none"><span class="dot"'+((St.netErr||(!hasStore&&!SYNC_URL))?' style="background:var(--coral)"':'')+'></span>код <b>'+esc(St.code)+'</b></button>'+
    '<span class="pill">'+St.people.size+' в зале</span><span class="grow"></span>'+
    '<button class="iconbtn" id="prev" '+(St.cur===0?'disabled':'')+' aria-label="Назад">←</button>'+
    '<span class="pill">'+(St.cur+1)+' / '+DECK.length+'</span>'+
    '<button class="iconbtn" id="next" '+(St.cur===DECK.length-1?'disabled':'')+' aria-label="Вперёд">→</button>'+
    '<button class="btn ghost" id="reset">очистить</button>'+
    '<button class="btn ghost" id="exit">выйти</button></div>'+
  (q.type==='title'
    ? '<div class="slide title-slide"><div class="tl">'+
      '<div class="lockup"><span class="w1">Menti-Meter</span><span class="w2">живая социология</span></div>'+
      '<div class="sub">Отвечай на вопросы и смотри, как распределяются позиции людей в зале в лайв режиме.</div>'+
      '<div class="foot">Fair Choice · 27 августа</div></div>'+
      '<img class="mascot" src="'+MASCOT_SRC+'" alt=""></div>'
    : '<div class="slide"><h2 class="q">'+esc(q.q)+'</h2><div class="body">'+renderResults(q)+'</div>'+
      '<div class="slideno">Ответов: '+(q.type==='open'?St.openKeys.length:(St.answers[String(q.id)]||[]).length)+'</div></div>')+
  '</div>';
  window.scrollTo(0,scroll);
  document.getElementById('diag').onclick=()=>showDiag();
  document.getElementById('prev').onclick=()=>move(-1);
  document.getElementById('next').onclick=()=>move(1);
  document.getElementById('exit').onclick=()=>{ clearInterval(St.timer); home() };
  document.getElementById('reset').onclick=async()=>{
    if(!confirm('Удалить все ответы этой сессии?')) return;
    const keys=await S.list('mm:'+St.code+':');
    for(const k of keys){ if(!k.endsWith(':cur')) await S.del(k) }
    St.openText={}; await pull(); drawPresent(true);
  };
}
async function move(d){
  const n=St.cur+d; if(n<0||n>=DECK.length) return;
  St.cur=n; drawPresent(true);
  const ok=await S.set(K('cur'),String(n));
  if(!ok) await S.set(K('cur'),String(n));
  await pull(); drawPresent(true);
}
document.addEventListener('keydown',e=>{
  if(St.mode!=='present') return;
  if(e.key==='ArrowRight'||e.key===' ') move(1);
  if(e.key==='ArrowLeft') move(-1);
});

function drawJoin(force){
  const s=sigJ(); if(!force && s===St.sig) return; St.sig=s;
  const q=DECK[St.cur];
  const active=document.activeElement, aid=active?active.id:null;
  const sel=(active&&active.selectionStart!=null)?active.selectionStart:null;
  const val=(active&&'value' in active)?active.value:null;
  const inner = q.type==='title'
    ? '<div class="qcard"><div class="waiting"><img src="'+MASCOT_SRC+'" alt="">Ты в зале.<br>Ждём первый вопрос ведущего.</div></div>'
    : '<div class="qcard"><h2>'+esc(q.q)+'</h2>'+joinBody(q)+'</div>';
  app.innerHTML='<div class="pwrap"><div class="ptop">'+
    '<button class="pill" id="diag" style="border:none"><span class="dot"'+((St.netErr||(!hasStore&&!SYNC_URL))?' style="background:var(--coral)"':'')+'></span>код <b>'+esc(St.code)+'</b></button>'+
    '<span class="grow"></span>'+
    '<button class="btn ghost" id="refresh">обновить</button>'+
    '<button class="btn ghost" id="leave">выйти</button></div>'+
    ((hasStore||SYNC_URL)?'':'<div class="warn">Общее хранилище на этом устройстве недоступно — ответы не уйдут на общий экран. Нужен внешний адрес базы в SYNC_URL.</div>')+
    inner+'</div>';
  document.getElementById('leave').onclick=()=>{ clearInterval(St.timer); home() };
  document.getElementById('refresh').onclick=()=>tick(true);
  document.getElementById('diag').onclick=()=>showDiag();
  wireJoin(q);
  if(aid){ const el=document.getElementById(aid);
    if(el){ if(val!=null&&'value' in el) el.value=val; el.focus();
      if(sel!=null&&el.setSelectionRange){ try{ el.setSelectionRange(sel,sel) }catch(e){} } } }
}
function joinBody(q){
  const id=String(q.id), mine=St.mine[id];
  if(q.type==='mc'){
    return q.opts.map((o,i)=>'<button class="opt" data-i="'+i+'" aria-pressed="'+(mine===String(i))+'">'+esc(o)+'</button>').join('')+
      (mine!=null?'<div class="saved">ответ сохранён — можно поменять</div>':'');
  }
  if(q.type==='scale'){
    const vals=mine?mine.split('-').map(Number):q.stmts.map(()=>50);
    return q.stmts.map((s,i)=>
      '<div class="slider-block"><div class="st">'+esc(s)+'</div>'+
      '<input type="range" min="0" max="100" value="'+(vals[i]||50)+'" data-i="'+i+'" class="sl" id="sl'+i+'">'+
      '<div class="endlbl"><span>безусловно<br>не согласны</span><span style="text-align:right">безусловно<br>согласны</span></div></div>').join('')+
      '<button class="btn" id="sendScale">'+(mine?'обновить ответ':'отправить')+'</button>'+
      (mine?'<div class="saved">ответ сохранён</div>':'');
  }
  if(q.type==='open'){
    const list=St.openKeys.map(r=>({r,t:St.openText[r]||'',v:voteCount(r)})).filter(x=>x.t).sort((a,b)=>b.v-a.v);
    const myVote=St.mine['v5'];
    const mineCount=St.openKeys.filter(r=>r.split('-')[0]===St.pid).length;
    return '<textarea class="free" id="freeTxt" maxlength="200" placeholder="Твой ответ"></textarea>'+
      '<div class="counter">до 200 знаков · отправлено: '+mineCount+'</div>'+
      '<button class="btn" id="sendOpen">отправить</button>'+
      (list.length?'<h3 class="sub-h">отметь ответ, который нравится</h3>'+
        list.map(x=>'<button class="votebtn" data-r="'+x.r+'" aria-pressed="'+(myVote===x.r)+'"><span>'+(myVote===x.r?'♥':'♡')+'</span><span>'+esc(x.t)+(x.v?' · '+x.v:'')+'</span></button>').join(''):'');
  }
  if(q.type==='words'){
    const mineList=(St.mine['9']||[]).map(dec);
    return '<input class="word" id="wordTxt" maxlength="24" placeholder="Одно-два слова">'+
      '<div class="counter">до 24 знаков · можно до 3 вариантов</div>'+
      '<button class="btn" id="sendWord" '+(mineList.length>=3?'disabled':'')+'>добавить</button>'+
      (mineList.length?'<div class="chiplist">'+mineList.map(w=>'<span class="chip">'+esc(w)+'</span>').join('')+'</div>':'');
  }
  if(q.type==='rank'){
    const order=mine?mine.split('-').map(Number):q.items.map((_,i)=>i);
    return '<ul class="ranklist" id="rank">'+order.map((idx,pos)=>
      '<li data-idx="'+idx+'"><span class="pos">'+(pos+1)+'</span><span class="txt">'+esc(q.items[idx])+'</span>'+
      '<button class="mv up" data-pos="'+pos+'" '+(pos===0?'disabled':'')+' aria-label="Выше">↑</button>'+
      '<button class="mv down" data-pos="'+pos+'" '+(pos===order.length-1?'disabled':'')+' aria-label="Ниже">↓</button></li>').join('')+'</ul>'+
      '<button class="btn" id="sendRank">'+(mine?'обновить порядок':'отправить')+'</button>'+
      (mine?'<div class="saved">ответ сохранён</div>':'');
  }
  return '';
}
function wireJoin(q){
  const id=String(q.id);
  if(q.type==='mc'){
    app.querySelectorAll('.opt').forEach(b=>b.onclick=async()=>{
      const i=b.dataset.i, old=St.mine[id];
      if(old!=null) await S.del(K('a:'+id+':'+St.pid+':'+old));
      await S.set(K('a:'+id+':'+St.pid+':'+i),'1');
      St.mine[id]=i; drawJoin(true);
    });
  }
  if(q.type==='scale'){
    const btn=document.getElementById('sendScale');
    if(btn) btn.onclick=async()=>{
      const vals=[...app.querySelectorAll('.sl')].map(el=>el.value).join('-'), old=St.mine[id];
      if(old!=null) await S.del(K('a:'+id+':'+St.pid+':'+old));
      await S.set(K('a:'+id+':'+St.pid+':'+vals),'1');
      St.mine[id]=vals; drawJoin(true);
    };
  }
  if(q.type==='open'){
    const btn=document.getElementById('sendOpen');
    if(btn) btn.onclick=async()=>{
      const el=document.getElementById('freeTxt'), t=el.value.trim();
      if(!t) return;
      const rid=St.pid+'-'+Math.random().toString(36).slice(2,6);
      await S.set(K('o:5:'+rid),t.slice(0,200));
      St.openText[rid]=t.slice(0,200); St.openKeys.push(rid); el.value=''; drawJoin(true);
    };
    app.querySelectorAll('.votebtn').forEach(b=>b.onclick=async()=>{
      const r=b.dataset.r, old=St.mine['v5'];
      if(old) await S.del(K('a:v5:'+St.pid+':'+old));
      if(old!==r){ await S.set(K('a:v5:'+St.pid+':'+r),'1'); St.mine['v5']=r } else delete St.mine['v5'];
      await pull(); drawJoin(true);
    });
  }
  if(q.type==='words'){
    const btn=document.getElementById('sendWord');
    if(btn) btn.onclick=async()=>{
      const el=document.getElementById('wordTxt'), t=el.value.trim().toLowerCase();
      if(!t) return;
      const p=enc(t.slice(0,24));
      await S.set(K('a:9:'+St.pid+':'+p),'1');
      St.mine['9']=(St.mine['9']||[]).concat([p]); el.value=''; drawJoin(true);
    };
  }
  if(q.type==='rank'){
    const ul=document.getElementById('rank');
    const order=()=>[...ul.querySelectorAll('li')].map(li=>+li.dataset.idx);
    function bindMoves(){
      ul.querySelectorAll('.up').forEach(b=>b.onclick=()=>swap(+b.dataset.pos,+b.dataset.pos-1));
      ul.querySelectorAll('.down').forEach(b=>b.onclick=()=>swap(+b.dataset.pos,+b.dataset.pos+1));
    }
    function swap(a,b){
      const o=order();
      if(b<0||b>=o.length) return;
      const t=o[a]; o[a]=o[b]; o[b]=t;
      const items=DECK[St.cur].items;
      ul.innerHTML=o.map((idx,pos)=>
        '<li data-idx="'+idx+'"><span class="pos">'+(pos+1)+'</span><span class="txt">'+esc(items[idx])+'</span>'+
        '<button class="mv up" data-pos="'+pos+'" '+(pos===0?'disabled':'')+' aria-label="Выше">↑</button>'+
        '<button class="mv down" data-pos="'+pos+'" '+(pos===o.length-1?'disabled':'')+' aria-label="Ниже">↓</button></li>').join('');
      bindMoves();
    }
    bindMoves();
    const btn=document.getElementById('sendRank');
    if(btn) btn.onclick=async()=>{
      const p=order().join('-'), old=St.mine[id];
      if(old!=null) await S.del(K('a:'+id+':'+St.pid+':'+old));
      await S.set(K('a:'+id+':'+St.pid+':'+p),'1');
      St.mine[id]=p; drawJoin(true);
    };
  }
}
async function showDiag(){
  const keys=await S.list('mm:'+St.code+':');
  const cur=await S.get(K('cur'));
  alert('Код: '+St.code+
    '\nТранспорт: '+TRANSPORT+
    '\nМой id: '+St.pid+
    '\nВидно ключей сессии: '+keys.length+
    '\nСлайд ведущего: '+(cur===null?'не найден':cur)+
    '\nТранспорт: '+TRANSPORT);
}
home();
</script>
</body>
</html>
