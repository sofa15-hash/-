<!DOCTYPE html>
<!-- saved from url=(0062)file:///C:/Users/Asus/Downloads/rechevoy_detektor_emotsiy.html -->
<html lang="ru"><head><meta http-equiv="Content-Type" content="text/html; charset=UTF-8">

<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Речевой детектор эмоций</title>
<style>
:root{--green:#30483f;--green2:#496357;--sage:#dce0d5;--cream:#f7f2e9;--paper:#fffdf8;--ink:#20241f;--muted:#6f7169;--line:#cfc2b1;--sand:#c7b39c;--gold:#a88e70}
*{box-sizing:border-box}
body{margin:0;background:#e8e0d5;color:var(--ink);font-family:Georgia,"Times New Roman",serif}
.poster{max-width:1100px;margin:24px auto;background:var(--cream);box-shadow:0 12px 45px #3c33251c;overflow:hidden;position:relative}
.top{padding:48px 7% 28px;text-align:center;background:linear-gradient(135deg,#f8f4ec,#eee6da);position:relative;border-bottom:1px solid var(--line)}
.kicker{font:italic 15px Georgia;color:var(--green2);letter-spacing:2px}
h1{font-size:clamp(32px,5vw,58px);line-height:1.04;margin:13px 0 8px;color:#17241e}
.subtitle{font-size:clamp(17px,2.5vw,25px);font-weight:bold;margin:0}
.intro{max-width:730px;margin:20px auto 0;font-size:17px;line-height:1.55}
.decor{position:absolute;color:#a9957e;opacity:.45;font-size:70px}
.decor.left{left:3%;top:22px}.decor.right{right:4%;bottom:15px}
.content{padding:28px 6% 34px}
.section-title{display:flex;align-items:center;gap:13px;margin:8px 0 16px;color:var(--green);font-size:25px}
.section-title:after{content:"";height:1px;background:var(--line);flex:1}
.legend{width:100%;border-collapse:collapse;margin:10px 0 25px;font-size:16px}
.legend th{background:var(--green);color:#fff;padding:13px 15px;text-align:left;font-size:17px}
.legend td{padding:12px 15px;border-bottom:1px solid #e2d9ce;line-height:1.35}
.legend tr:nth-child(even) td{background:#eee8de}
.legend td:first-child{width:48%;font-weight:bold}
.note{border:1px solid var(--line);border-radius:17px;padding:18px 22px;display:flex;gap:17px;align-items:flex-start;background:#fbf7f0;margin:20px 0 28px}
.note-icon{font-size:35px;color:var(--gold);line-height:1}
.note strong{font-size:22px;display:block;margin-bottom:5px}
.note p{margin:0;line-height:1.5;font-size:16px}
.detector{border:1.5px solid var(--sand);border-radius:18px;padding:22px;background:#fbf8f2}
.detector-head{text-align:center;margin:-40px auto 20px;background:#d8c8b5;border-radius:30px;padding:9px 25px;width:max-content;max-width:100%;font-size:25px;font-weight:bold}
.field-label{font-size:18px;font-weight:bold;margin:8px 0}
.hint{font:14px Arial,sans-serif;color:var(--muted);line-height:1.5}
textarea{width:100%;min-height:135px;resize:vertical;border:1px solid #c9bba9;border-radius:12px;padding:15px;background:#fffdf9;color:#252720;font:17px/1.55 Georgia,serif;outline:none}
textarea:focus{border-color:var(--green2);box-shadow:0 0 0 3px #49635718}
.controls{display:flex;gap:10px;flex-wrap:wrap;margin:13px 0}
button{border:0;border-radius:9px;padding:12px 18px;font: bold 15px Arial,sans-serif;cursor:pointer;transition:.2s}
button:hover{transform:translateY(-1px);filter:brightness(1.04)}
.primary{background:var(--green);color:white;flex:1;min-width:210px}
.secondary{background:#e7dfd3;color:#26372f;border:1px solid #cbbda9}
.examples{display:flex;flex-wrap:wrap;gap:8px;margin:10px 0 15px}
.examples button{font-size:13px;padding:9px 12px}
.counter{font:12px Arial,sans-serif;color:var(--muted);text-align:right}
#status{display:none;margin-top:15px;padding:13px;border-radius:10px;background:#e9eee7;font:14px Arial,sans-serif;color:#30483f}
#status.show{display:block}
.progress{height:7px;background:#d7ded4;border-radius:20px;overflow:hidden;margin-top:10px}
.progress span{display:block;height:100%;width:0;background:#547565;transition:width .35s}
.results{display:none;margin-top:22px}
.results.show{display:block}
.result-card{background:#fffdf8;border:1px solid var(--line);border-radius:15px;padding:19px;margin:13px 0}
.result-top{display:flex;align-items:center;gap:17px}
.emoji{font-size:49px}
.result-name{font-size:27px;font-weight:bold;color:var(--green)}
.smallcaps{font:11px Arial,sans-serif;letter-spacing:1.6px;text-transform:uppercase;color:var(--muted)}
.scoreline{display:flex;justify-content:space-between;font:14px Arial,sans-serif;margin:17px 0 7px}
.bar{height:9px;border-radius:20px;background:#e8e5dc;overflow:hidden}
.bar span{display:block;height:100%;width:0;border-radius:20px;transition:width .8s}
.disclaimer{font:12px/1.5 Arial,sans-serif;color:var(--muted);margin-top:9px}
.chart-row{display:grid;grid-template-columns:180px 1fr 42px;gap:10px;align-items:center;margin:12px 0;font:14px Arial,sans-serif}
.chart-row .bar{height:10px}
.tags{display:flex;flex-wrap:wrap;gap:7px;margin-top:10px}
.tag{border:1px solid #d4c9b9;background:#f0ece3;border-radius:20px;padding:6px 10px;font:13px Arial,sans-serif}
.explain{font-size:16px;line-height:1.55}
.method-grid{display:grid;grid-template-columns:repeat(4,1fr);gap:12px;margin-top:15px}
.method{background:#eeece3;border-radius:12px;padding:13px}
.method b{display:block;margin:5px 0;font-size:15px}
.method p{margin:0;font:13px/1.45 Arial,sans-serif;color:var(--muted)}
.bottom{background:var(--green);color:#f7f1e7;text-align:center;padding:20px;font-size:13px;letter-spacing:5px}
.footer-note{display:flex;gap:15px;align-items:center;margin:24px 0 5px;font-size:15px;line-height:1.5}
.footer-note .book{font-size:38px;background:#c9b8a3;border-radius:50%;width:65px;height:65px;display:grid;place-items:center;flex:none}
@media(max-width:650px){.poster{margin:0}.top{padding:35px 6% 25px}.decor{display:none}.content{padding:23px 5%}.legend{font-size:14px}.legend th{font-size:14px}.legend td{padding:9px}.method-grid{grid-template-columns:repeat(2,1fr)}.chart-row{grid-template-columns:125px 1fr 35px;font-size:12px}.note{padding:15px}.detector{padding:16px}.detector-head{font-size:20px}.bottom{letter-spacing:3px}}
@media print{body{background:white}.poster{margin:0;box-shadow:none}.controls button{display:none}}
</style>
</head>
<body>
<div class="poster">
<header class="top">
 <div class="decor left">❝</div><div class="decor right">✦</div>
 <div class="kicker">ИССЛЕДОВАНИЕ РЕЧИ И ЭМОЦИЙ</div>
 <h1>Речевой детектор эмоций</h1>
 <p class="subtitle">как слова рассказывают о состоянии человека</p>
 <p class="intro">Интерактивный инструмент для наблюдения за эмоциональными особенностями речи. Введите сообщение — и детектор покажет возможные эмоциональные сигналы, найденные в тексте.</p>
</header>
<main class="content">
 <h2 class="section-title">Что замечаем в речи</h2>
 <table class="legend">
 <thead><tr><th>Особенность речи</th><th>Возможное эмоциональное состояние</th></tr></thead>
 <tbody>
 <tr><td>Много повторов</td><td>Волнение, напряжение</td></tr>
 <tr><td>Короткие фразы</td><td>Усталость, раздражение, тревога</td></tr>
 <tr><td>Много вопросов</td><td>Сомнение, беспокойство</td></tr>
 <tr><td>Восклицательные знаки</td><td>Сильная эмоциональная реакция</td></tr>
 <tr><td>Резкие слова</td><td>Раздражение, гнев</td></tr>
 <tr><td>Многоточия и недосказанность</td><td>Неуверенность, задумчивость</td></tr>
 <tr><td>Сленг, шутки и эмодзи</td><td>Дополнительная передача эмоций</td></tr>
 <tr><td>Спокойные последовательные фразы</td><td>Возможное эмоциональное равновесие</td></tr>
 </tbody></table>
 <div class="note"><div class="note-icon">!</div><div><strong>Важное правило</strong><p>Речь — это подсказка, а не точный диагноз. Нельзя определить психологическое состояние человека только по одному слову или сообщению. Важно учитывать контекст, ситуацию и особенности самого человека.</p></div></div>
 <section class="detector">
  <div class="detector-head">Практическое задание · Детектор</div>
  <p class="field-label">Введите сообщение для анализа</p>
  <p class="hint">Напишите фразу или небольшой текст. Программа исследует эмоционально окрашенные слова, повторы, знаки препинания и некоторые языковые конструкции.</p>
  <textarea id="message" maxlength="3000" placeholder="Например: Ты где??? Я уже 20 минут жду!!!"></textarea>
  <div class="counter" id="counter">24 / 3000 символов</div>
  <p class="field-label">Или проверьте готовый пример:</p>
  <div class="examples">
   <button class="secondary" data-text="Ты где??? Я уже 20 минут жду!!!">① Беспокойство</button>
   <button class="secondary" data-text="Ну да... хорошо...">② Разочарование</button>
   <button class="secondary" data-text="Урааа!!! Мы победили!!! 🎉">③ Радость</button>
   <button class="secondary" data-text="Не знаю. Наверное, потом.">④ Неуверенность</button>
  </div>
  <div class="controls">
   <button class="primary" id="analyze">🔎 Анализировать сообщение</button>
   <button class="secondary" id="clear">Очистить</button>
  </div>
  <div id="status" aria-live="polite" class=""><b id="statusText">Формируем результат…</b><div class="progress"><span id="progress" style="width: 110%;"></span></div></div>
  <div class="results" id="results">
   <h2 class="section-title">Результаты анализа</h2>
   <div class="result-card">
    <div class="smallcaps">Наиболее выраженный эмоциональный сигнал</div>
    <div class="result-top"><div class="emoji" id="mainEmoji">😌</div><div><div class="result-name" id="mainName">Спокойствие</div><div class="hint" id="mainDesc">Преимущественно нейтральная окраска</div></div></div>
    <div class="scoreline"><span>Относительная выраженность</span><b id="mainScore">100%</b></div>
    <div class="bar"><span id="mainBar" style="background: rgb(108, 153, 142); width: 100%;"></span></div>
    <p class="disclaimer">Процент показывает долю категории среди найденных сигналов, а не вероятность того, что автор действительно испытывает эту эмоцию.</p>
   </div>
   <div class="result-card"><h3>Эмоциональная карта сообщения</h3><div id="chart"><div class="chart-row"><span>😌 Спокойствие</span><div class="bar"><span style="width: 100%; background: rgb(108, 153, 142);"></span></div><b>100%</b></div><div class="chart-row"><span>😊 Радость</span><div class="bar"><span style="width: 0%; background: rgb(84, 139, 112);"></span></div><b>0%</b></div><div class="chart-row"><span>😢 Грусть</span><div class="bar"><span style="width: 0%; background: rgb(102, 139, 185);"></span></div><b>0%</b></div><div class="chart-row"><span>😟 Тревога</span><div class="bar"><span style="width: 0%; background: rgb(199, 151, 70);"></span></div><b>0%</b></div><div class="chart-row"><span>😠 Раздражение / гнев</span><div class="bar"><span style="width: 0%; background: rgb(197, 108, 83);"></span></div><b>0%</b></div><div class="chart-row"><span>😲 Удивление</span><div class="bar"><span style="width: 0%; background: rgb(154, 128, 189);"></span></div><b>0%</b></div><div class="chart-row"><span>🤔 Неопределённость</span><div class="bar"><span style="width: 0%; background: rgb(146, 150, 156);"></span></div><b>0%</b></div></div></div>
   <div class="result-card"><h3>Какие признаки обнаружены?</h3><div class="tags" id="tags"><span class="tag">явные маркеры не обнаружены</span></div><p class="explain" id="evidenceText">В тексте не найдено достаточно явных эмоциональных маркеров. Попробуйте более развёрнутое сообщение.</p></div>
   <div class="result-card"><h3>Интерпретация</h3><p class="explain" id="interpretation">В тексте не обнаружено выраженных эмоциональных маркеров. Он выглядит преимущественно нейтральным.</p><p class="disclaimer">Это предположение на основе языковых признаков. Ирония, контекст, отношения между собеседниками и индивидуальный стиль могут изменить смысл сообщения.</p></div>
   <button class="secondary" id="again">↻ Провести новый анализ</button>
  </div>
 </section>
 <h2 class="section-title" style="margin-top:30px">Как работает программа</h2>
 <div class="method-grid">
  <div class="method"><div style="font-size:27px">🔤</div><b>Слова</b><p>Поиск эмоционально окрашенной лексики.</p></div>
  <div class="method"><div style="font-size:27px">❗</div><b>Пунктуация</b><p>Анализ восклицаний, вопросов и многоточий.</p></div>
  <div class="method"><div style="font-size:27px">🔁</div><b>Повторы</b><p>Выявление повторяющихся слов и букв.</p></div>
  <div class="method"><div style="font-size:27px">💬</div><b>Контекст</b><p>Учет отрицаний и сочетаний слов.</p></div>
 </div>
 <div class="footer-note"><div class="book">📖</div><div>Этот инструмент можно использовать на уроках русского языка и литературы при изучении речи персонажей, эмоционально окрашенной лексики и современной подростковой коммуникации.</div></div>
</main>
<footer class="bottom">БОЛЬШЕ, ЧЕМ СЛОВА</footer>
</div>
<script>
(()=>{
const $=id=>document.getElementById(id);
const cats=[
{id:'joy',name:'Радость',emoji:'😊',desc:'Положительная эмоциональная окраска',color:'#548b70',words:'рад радость счастлив счастье прекрасно отлично замечательно здорово супер класс круто великолепно получилось победили ура люблю обожаю весело приятно довольна доволен восторг восхитительно спасибо благодарю'.split(' ')},
{id:'sad',name:'Грусть',emoji:'😢',desc:'Возможные признаки печали и разочарования',color:'#668bb9',words:'грустно грусть печально печаль плохо одиноко одиночество скучаю скучно тоска несчастье разочарован разочарована плачу слезы больно потерял потеряла устал устала бессмысленно жаль тяжело'.split(' ')},
{id:'anxiety',name:'Тревога',emoji:'😟',desc:'Возможные признаки беспокойства и неуверенности',color:'#c79746',words:'страшно боюсь бояться тревожно тревога переживаю волнуюсь беспокоюсь вдруг неизвестно сомневаюсь паника паниковать неуверен неуверенность опасность риск наверное возможно проблема успею'.split(' ')},
{id:'anger',name:'Раздражение / гнев',emoji:'😠',desc:'Возможные признаки недовольства и напряжения',color:'#c56c53',words:'злюсь злость бесит раздражает раздражен раздражена ненавижу достал достала ужасно отвратительно надоело хватит прекрати глупость возмущен возмущена злой злая бесят опять'.split(' ')},
{id:'surprise',name:'Удивление',emoji:'😲',desc:'Возможные признаки неожиданной реакции',color:'#9a80bd',words:'неожиданно удивительно удивлен удивлена шок невероятно правда серьезно ничего себе ого вау внезапно неужели'.split(' ')},
{id:'calm',name:'Спокойствие',emoji:'😌',desc:'Преимущественно нейтральная окраска',color:'#6c998e',words:'спокойно нормально хорошо понятно согласен согласна думаю считаю план конечно ладно просто обычный уверен уверена'.split(' ')},
{id:'uncertain',name:'Неопределённость',emoji:'🤔',desc:'Возможные признаки сомнения и недосказанности',color:'#92969c',words:'не знаю наверное наверно может возможно кажется сомневаюсь не уверен не уверена подумаю посмотрим как-нибудь вроде пожалуй трудно'.split(' ')}
];
const neg=['не','ни','нет','никогда','ничего'];
const intens=['очень','так','настолько','ужасно','невероятно','крайне','совсем','абсолютно','безумно'];
function analyse(s){
 const words=(s.toLowerCase().replace(/ё/g,'е').match(/[а-яa-z]+/g)||[]);
 const scores=Object.fromEntries(cats.map(c=>[c.id,0]));
 const found=Object.fromEntries(cats.map(c=>[c.id,[]]));
 const add=(id,n,w)=>{scores[id]+=n;if(w&&!found[id].includes(w))found[id].push(w)};
 words.forEach((w,i)=>cats.filter(c=>c.id!=='calm').forEach(c=>{
  const match=c.words.find(t=>w===t||(t.length>=5&&w.startsWith(t)));
  if(!match)return;
  let id=c.id,n=1.35;
  if(words.slice(Math.max(0,i-2),i).some(x=>neg.includes(x))){
   if(id==='joy')id='sad';else if(id==='sad')id='joy';else if(id==='anger')id='calm';else n=.35;
  }
  if(intens.includes(words[i-1]))n*=1.5;
  add(id,n,w);
 }));
 const emoji={joy:['😊','😄','😁','😍','🥳','🎉','❤️','❤','😂','💖','😃'],sad:['😢','😭','😔','😞','☹','💔'],anxiety:['😰','😟','😨','😬','😥'],anger:['😡','😠','🤬'],surprise:['😲','😮','😯','🤯'],calm:['😌','🙂'],uncertain:['🤔','😕']};
 Object.entries(emoji).forEach(([id,arr])=>arr.forEach(e=>{if(s.includes(e))add(id,1.5,e)}));
 const bangs=(s.match(/!/g)||[]).length,questions=(s.match(/\?/g)||[]).length,dots=(s.match(/\.{2,}/g)||[]).length;
 if(bangs)add('joy',Math.min(bangs*.24,.9),'!');
 if(questions)add('anxiety',Math.min(questions*.18,.65),'?');
 if(dots)add('uncertain',Math.min(dots*.45,1.1),'...');
 if(/\b(ура|ураа+|вау|ого)\b/i.test(s))add('surprise',1.1,'эмоциональное восклицание');
 if(/([!?])\1+/.test(s))add('anger',.35,'повтор знаков');
 if(/([а-я])\1{2,}/i.test(s)){add('joy',.3,'повтор букв');add('anger',.3,'повтор букв')}
 words.forEach((w,i)=>{if(i>0&&w.length>2&&words.indexOf(w)!==i)add('anxiety',.2,'повтор слов')});
 if(!Object.values(scores).some(x=>x>0))scores.calm=1;
 const total=Object.values(scores).reduce((a,b)=>a+b,0);
 const ranked=cats.map(c=>({...c,score:scores[c.id],percent:Math.round(scores[c.id]/total*100)})).sort((a,b)=>b.score-a.score);
 const top=ranked[0],second=ranked[1],evidence=found[top.id].slice(0,12);
 let interpretation={
 joy:'В сообщении найдены положительно окрашенные слова или другие признаки, которые могут передавать удовольствие, удовлетворение или восторг.',
 sad:'В тексте обнаружены слова с отрицательной эмоциональной окраской. Они могут указывать на печаль или разочарование.',
 anxiety:'В сообщении присутствуют маркеры беспокойства, сомнения или ожидания неопределённого результата.',
 anger:'Обнаружены резкие выражения или слова недовольства, которые могут указывать на раздражение.',
 surprise:'Обнаружены выражения неожиданной реакции и удивления.',
 calm:'В тексте не обнаружено выраженных эмоциональных маркеров. Он выглядит преимущественно нейтральным.',
 uncertain:'В сообщении присутствуют слова сомнения, предположения или незавершённости мысли.'
 }[top.id];
 if(second.score>0&&second.percent>=20)interpretation+=' Также заметны признаки категории «'+second.name.toLowerCase()+'». Возможно, сообщение имеет смешанную эмоциональную окраску.';
 const structural=[];
 if(bangs)structural.push('восклицательные знаки: '+bangs);
 if(questions)structural.push('вопросительные знаки: '+questions);
 if(dots)structural.push('многоточия: '+dots);
 return {ranked,top,evidence,structural,interpretation};
}
$('message').addEventListener('input',()=>$('counter').textContent=$('message').value.length+' / 3000 символов');
document.querySelectorAll('[data-text]').forEach(b=>b.addEventListener('click',()=>{$('message').value=b.dataset.text;$('counter').textContent=b.dataset.text.length+' / 3000 символов';$('message').focus()}));
function run(){
 const s=$('message').value.trim();
 if(!s){alert('Сначала введите сообщение или выберите пример.');return}
 if(!/[а-яёa-z]/i.test(s)){alert('Добавьте в сообщение хотя бы несколько букв.');return}
 $('results').classList.remove('show');$('status').classList.add('show');
 $('analyze').disabled=true;
 const labels=['Выделяем эмоционально окрашенные слова…','Изучаем знаки препинания и повторы…','Сопоставляем признаки с категориями…','Формируем результат…'];
 let i=0;$('statusText').textContent=labels[0];$('progress').style.width='10%';
 const timer=setInterval(()=>{
  i++;$('statusText').textContent=labels[Math.min(i,3)];$('progress').style.width=(i*25+10)+'%';
  if(i>=4){
   clearInterval(timer);const r=analyse(s);
   $('mainEmoji').textContent=r.top.emoji;$('mainName').textContent=r.top.name;$('mainDesc').textContent=r.top.desc;
   $('mainScore').textContent=r.top.percent+'%';$('mainBar').style.width=r.top.percent+'%';$('mainBar').style.background=r.top.color;
   $('chart').innerHTML='';
   r.ranked.forEach(c=>{
    const row=document.createElement('div');row.className='chart-row';
    const label=document.createElement('span');label.textContent=c.emoji+' '+c.name;
    const bar=document.createElement('div');bar.className='bar';
    const fill=document.createElement('span');fill.style.width=c.percent+'%';fill.style.background=c.color;bar.append(fill);
    const pct=document.createElement('b');pct.textContent=c.percent+'%';
    row.append(label,bar,pct);$('chart').append(row);
   });
   $('tags').innerHTML='';
   const all=[...r.evidence,...r.structural];
   if(!all.length)all.push('явные маркеры не обнаружены');
   all.forEach(w=>{const tag=document.createElement('span');tag.className='tag';tag.textContent=w;$('tags').append(tag)});
   $('evidenceText').textContent=r.evidence.length?'Детектор сопоставил найденные слова с эмоциональным словарём. Пунктуация и повторы учитывались как дополнительные сигналы.':'В тексте не найдено достаточно явных эмоциональных маркеров. Попробуйте более развёрнутое сообщение.';
   $('interpretation').textContent=r.interpretation;
   $('status').classList.remove('show');$('results').classList.add('show');$('analyze').disabled=false;
   $('results').scrollIntoView({behavior:'smooth',block:'start'});
  }
 },350);
}
$('analyze').addEventListener('click',run);
$('clear').addEventListener('click',()=>{$('message').value='';$('counter').textContent='0 / 3000 символов';$('results').classList.remove('show');$('status').classList.remove('show')});
$('again').addEventListener('click',()=>{$('results').classList.remove('show');$('message').focus()});
})();
</script>

</body></html>
