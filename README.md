<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>西语陈述式一般现在时 - 完整版互动填空特训</title>
<style>
    body { font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif; background-color: #f0f4f8; color: #333; max-width: 800px; margin: 0 auto; padding: 20px; padding-bottom: 100px; }
    h1 { text-align: center; color: #2c3e50; }
    .intro { text-align: center; margin-bottom: 20px; color: #666; line-height: 1.6; }
    .quiz-container { background: white; padding: 30px; border-radius: 12px; box-shadow: 0 4px 6px rgba(0,0,0,0.1); margin-bottom: 20px;}
    .section-title { color: #3b82f6; border-bottom: 2px solid #e2e8f0; padding-bottom: 10px; margin-top: 30px; margin-bottom: 20px; }
    .question { margin-bottom: 20px; font-size: 1.1em; line-height: 1.6; }
    input[type="text"] { width: 100px; padding: 8px; font-size: 1em; border: 2px solid #cbd5e1; border-radius: 6px; text-align: center; outline: none; transition: border-color 0.3s; }
    input[type="text"]:focus { border-color: #3b82f6; }
    .correct { border-color: #22c55e !important; background-color: #f0fdf4; color: #166534; }
    .incorrect { border-color: #ef4444 !important; background-color: #fef2f2; color: #991b1b; }
    .feedback { font-size: 0.9em; margin-left: 10px; font-weight: bold; }
    .btn-submit { display: block; width: 100%; padding: 15px; font-size: 1.2em; background-color: #3b82f6; color: white; border: none; border-radius: 8px; cursor: pointer; margin-top: 20px; font-weight: bold; }
    .btn-submit:hover { background-color: #2563eb; }
    .score { text-align: center; font-size: 1.5em; font-weight: bold; margin-top: 20px; color: #2c3e50; display: none; }
    /* 虚拟键盘样式 */
    .keyboard { position: fixed; bottom: 20px; left: 50%; transform: translateX(-50%); background: #333; padding: 10px; border-radius: 8px; display: flex; gap: 5px; box-shadow: 0 4px 10px rgba(0,0,0,0.3); z-index: 1000; }
    .key { background: white; border: none; padding: 10px 15px; font-size: 1.2em; border-radius: 4px; cursor: pointer; }
    .key:hover { background: #e2e8f0; }
    .key-hint { text-align: center; font-size: 0.8em; color: white; margin-bottom: 5px; }
</style>
</head>
<body>

<h1>🎯 陈述式一般现在时 - 终极默写特训 (40题)</h1>
<p class="intro">这里包含了你提到的所有 34 个不规则动词及 5 个规则动词对照。<br>请填入正确的变位，遇到重音字母可使用下方悬浮面板。</p>

<div class="quiz-container">
    <h2 class="section-title">第一部分：绝对高危区 (错题与易混淆)</h2>
    <div id="quiz-part1"></div>

    <h2 class="section-title">第二部分：拼写与元音裂化挑战</h2>
    <div id="quiz-part2"></div>

    <h2 class="section-title">第三部分：全景巩固区</h2>
    <div id="quiz-part3"></div>
</div>

<button class="btn-submit" onclick="checkAnswers()">提交试卷并判分</button>
<div class="score" id="score-display"></div>

<div class="keyboard" id="virtual-keyboard">
    <div>
        <div class="key-hint">特殊字符面板</div>
        <button class="key" onclick="insertChar('á')">á</button>
        <button class="key" onclick="insertChar('é')">é</button>
        <button class="key" onclick="insertChar('í')">í</button>
        <button class="key" onclick="insertChar('ó')">ó</button>
        <button class="key" onclick="insertChar('ú')">ú</button>
        <button class="key" onclick="insertChar('ñ')">ñ</button>
    </div>
</div>

<script>
    const questionsPart1 = [
        { text: "1. Con tantas maletas, yo no {blank} (caber) en este coche.", answer: "quepo", hint: "yo变位极其特殊" },
        { text: "2. Actualmente, yo {blank} (construir) una maqueta para la clase de arte.", answer: "construyo", hint: "词根带y" },
        { text: "3. ¿Vosotros {blank} (oír) ese ruido extraño en la calle?", answer: "oís", hint: "带重音符号" },
        { text: "4. ¿Adónde {blank} (ir) vosotros de vacaciones este verano?", answer: "vais", hint: "单音节无重音" },
        { text: "5. En el centro de la ciudad {blank} (haber) muchos museos interesantes.", answer: "hay", hint: "无人称形式" },
        { text: "6. Ellos siempre se {blank} (reír) de mis chistes malos.", answer: "ríen", hint: "注意重音位置" },
        { text: "7. Si tú {blank} (continuar) así, vas a sacar notas excelentes.", answer: "continúas", hint: "u上有重音" },
        { text: "8. Mi hermana mayor se {blank} (graduar) de la universidad el mes que viene.", answer: "gradúa", hint: "u上有重音" },
        { text: "9. Mis amigos y yo nos {blank} (reunirse) todos los viernes en el café.", answer: "reunimos", hint: "重音回归常规，无重音符号" },
        { text: "10. Yo {blank} (confiar) plenamente en tu talento para el diseño.", answer: "confío", hint: "i上有重音" },
        { text: "11. Nosotros {blank} (haber - 助动词) de terminar este proyecto hoy mismo.", answer: "hemos", hint: "表示义务的助动词变位" }
    ];

    const questionsPart2 = [
        { text: "12. Nosotros {blank} (seguir) las instrucciones del profesor paso a paso.", answer: "seguimos", hint: "nosotros不发生裂化" },
        { text: "13. Vosotros nunca {blank} (pedir) postre después de cenar.", answer: "pedís", hint: "不发生裂化，有重音" },
        { text: "14. ¿A qué hora {blank} (venir) tú a mi casa esta noche?", answer: "vienes", hint: "e变ie" },
        { text: "15. Vosotros {blank} (trabajar) en una empresa multinacional, ¿verdad?", answer: "trabajáis", hint: "规则动词" },
        { text: "16. Yo siempre {blank} (decir) la verdad, aunque duela.", answer: "digo", hint: "yo形式变g且e变i" },
        { text: "17. Yo no {blank} (ver) la televisión por la noche, prefiero leer.", answer: "veo", hint: "保留e" },
        { text: "18. En mi trabajo, yo {blank} (traducir) textos del inglés al español.", answer: "traduzco", hint: "yo形式变为-zco" },
        { text: "19. Yo siempre {blank} (vencer) mis miedos cuando viajo sola.", answer: "venzo", hint: "yo形式变为-zo" },
        { text: "20. Yo {blank} (coger) el autobús todos los días para ir a la oficina.", answer: "cojo", hint: "yo形式变j" },
        { text: "21. Yo siempre {blank} (elegir) la blusa azul.", answer: "elijo", hint: "yo形式变j且e变i" },
        { text: "22. Yo {blank} (hacer) mucho deporte los fines de semana.", answer: "hago", hint: "yo加g" },
        { text: "23. Yo me {blank} (poner) el abrigo porque hace mucho frío.", answer: "pongo", hint: "yo加g" },
        { text: "24. Yo {blank} (salir) de casa a las ocho en punto de la mañana.", answer: "salgo", hint: "yo加g" },
        { text: "25. Yo te {blank} (traer) un recuerdo muy bonito de mi viaje a España.", answer: "traigo", hint: "yo加ig" },
        { text: "26. Cuando patino sobre hielo, yo me {blank} (caer) con frecuencia.", answer: "caigo", hint: "yo加ig" }
    ];

    const questionsPart3 = [
        { text: "27. Yo no {blank} (saber) hablar alemán, pero quiero aprender.", answer: "sé", hint: "单音节带重音" },
        { text: "28. Esta profesora nos {blank} (dar) muchos consejos útiles para el examen.", answer: "da", hint: "第三人称单数" },
        { text: "29. Yo no {blank} (conocer) a tu hermano, ¿es simpático?", answer: "conozco", hint: "yo变-zco" },
        { text: "30. Nosotros no {blank} (jugar) al fútbol, preferimos el baloncesto.", answer: "jugamos", hint: "nosotros不发生u变ue" },
        { text: "31. La empresa {blank} (adquirir) nuevos equipos tecnológicos cada año.", answer: "adquiere", hint: "i变ie" },
        { text: "32. Nosotros {blank} (pensar) viajar a América Latina el próximo año.", answer: "pensamos", hint: "nosotros不发生裂化" },
        { text: "33. ¿{blank} (poder) tú ayudarme con este ejercicio de gramática?", answer: "puedes", hint: "o变ue" },
        { text: "34. Nosotros {blank} (tener) mucho tiempo libre hoy por la tarde.", answer: "tenemos", hint: "nosotros不发生裂化" },
        { text: "35. Vosotros {blank} (ser) estudiantes muy aplicados y responsables.", answer: "sois", hint: "单音节无重音" },
        { text: "36. Yo {blank} (estar) muy cansada hoy por tanto trabajo.", answer: "estoy", hint: "特殊结尾" },
        { text: "37. ¿Vosotras {blank} (hablar) japonés o coreano?", answer: "habláis", hint: "规则动词" },
        { text: "38. Nosotros {blank} (comer) paella todos los domingos en familia.", answer: "comemos", hint: "规则动词" },
        { text: "39. Mis abuelos {blank} (vivir) en un pueblo muy tranquilo de la montaña.", answer: "viven", hint: "规则动词" },
        { text: "40. ¿Tú le {blank} (escribir) correos a tus clientes todos los días?", answer: "escribes", hint: "规则动词" }
    ];

    const allQuestions = [...questionsPart1, ...questionsPart2, ...questionsPart3];
    let activeInput = null;

    function renderQuestions(qArray, containerId, offset) {
        const container = document.getElementById(containerId);
        qArray.forEach((q, index) => {
            const globalIndex = offset + index;
            const parts = q.text.split('{blank}');
            const questionHtml = `
                <div class="question" id="q${globalIndex}">
                    ${parts[0]} 
                    <input type="text" id="input${globalIndex}" autocomplete="off" onfocus="activeInput = this"> 
                    ${parts[1]}
                    <span class="feedback" id="feedback${globalIndex}"></span>
                </div>
            `;
            container.innerHTML += questionHtml;
        });
    }

    renderQuestions(questionsPart1, 'quiz-part1', 0);
    renderQuestions(questionsPart2, 'quiz-part2', questionsPart1.length);
    renderQuestions(questionsPart3, 'quiz-part3', questionsPart1.length + questionsPart2.length);

    // 插入特殊字符
    function insertChar(char) {
        if (activeInput) {
            const start = activeInput.selectionStart;
            const end = activeInput.selectionEnd;
            const text = activeInput.value;
            activeInput.value = text.slice(0, start) + char + text.slice(end);
            activeInput.focus();
            activeInput.selectionStart = activeInput.selectionEnd = start + 1;
        }
    }

    // 检查答案
    function checkAnswers() {
        let score = 0;
        allQuestions.forEach((q, index) => {
            const inputEl = document.getElementById(`input${index}`);
            const feedbackEl = document.getElementById(`feedback${index}`);
            // 清理空格并转为小写
            const userAnswer = inputEl.value.trim().toLowerCase();
            
            inputEl.classList.remove('correct', 'incorrect');
            
            if (userAnswer === q.answer) {
                inputEl.classList.add('correct');
                feedbackEl.innerHTML = "✅ 正确";
                feedbackEl.style.color = "#166534";
                score++;
            } else {
                inputEl.classList.add('incorrect');
                feedbackEl.innerHTML = `❌ 正确答案: <b>${q.answer}</b> <i>(${q.hint})</i>`;
                feedbackEl.style.color = "#991b1b";
            }
        });

        const scoreDiv = document.getElementById('score-display');
        scoreDiv.style.display = 'block';
        scoreDiv.innerHTML = `总分: ${score} / ${allQuestions.length}`;
        
        if(score === allQuestions.length) {
            scoreDiv.innerHTML += "<br>🎉 太棒了！满分通关！这 40 个动词的变位已经成为你的肌肉记忆了！";
        }
        
        // 自动滚动到分数区域
        scoreDiv.scrollIntoView({ behavior: 'smooth' });
    }
</script>

</body>
</html># conjugaciones-for-Presente-de-infitivo
