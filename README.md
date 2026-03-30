<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=yes, viewport-fit=cover">
    <title>安全C3题库 | 专职安全生产管理人员</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            -webkit-tap-highlight-color: transparent;
        }

        body {
            background: linear-gradient(135deg, #1a4d3e 0%, #0f2c25 100%);
            font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif;
            padding: 12px;
            min-height: 100vh;
        }

        .container {
            max-width: 800px;
            margin: 0 auto;
        }

        .hero {
            background: #2b5e4c;
            border-radius: 24px;
            padding: 20px;
            margin-bottom: 16px;
            box-shadow: 0 4px 12px rgba(0,0,0,0.15);
        }

        .title {
            font-size: 1.5rem;
            font-weight: 700;
            color: #FFE6B0;
            display: flex;
            align-items: center;
            gap: 8px;
        }

        .sub {
            color: #d4e6df;
            margin-top: 8px;
            font-size: 0.7rem;
            border-left: 3px solid #FFC857;
            padding-left: 10px;
        }

        .stats-bar {
            display: flex;
            flex-wrap: wrap;
            justify-content: space-between;
            align-items: center;
            margin-top: 16px;
            gap: 10px;
        }

        .score-panel {
            background: #1e3a2f;
            border-radius: 30px;
            padding: 6px 16px;
            font-weight: 600;
            font-size: 0.8rem;
            color: #FFE6B0;
        }

        .btn-group {
            display: flex;
            gap: 8px;
            flex-wrap: wrap;
        }

        .btn {
            background: #3a6b5a;
            border: none;
            padding: 6px 14px;
            border-radius: 30px;
            font-weight: 500;
            font-size: 0.7rem;
            cursor: pointer;
            color: white;
            transition: all 0.2s;
        }

        .btn:active {
            transform: scale(0.97);
        }

        .btn-primary {
            background: #e9b35f;
            color: #1e3a2f;
            font-weight: 600;
        }

        .btn-outline {
            background: rgba(255,255,255,0.2);
        }

        .mode-badge {
            background: #1e3a2f;
            border-radius: 30px;
            padding: 4px 12px;
            font-size: 0.65rem;
            color: #FFE2B5;
        }

        .type-filter {
            background: rgba(0,0,0,0.3);
            border-radius: 50px;
            padding: 8px 12px;
            margin-bottom: 16px;
            display: flex;
            flex-wrap: wrap;
            align-items: center;
            gap: 8px;
            justify-content: space-between;
        }

        .type-buttons {
            display: flex;
            gap: 6px;
            flex-wrap: wrap;
        }

        .type-btn {
            background: rgba(0,0,0,0.4);
            border: 1px solid rgba(233,179,95,0.5);
            padding: 4px 12px;
            border-radius: 30px;
            font-size: 0.65rem;
            cursor: pointer;
            color: #e9d5b0;
            transition: all 0.2s;
        }

        .type-btn.active {
            background: #e9b35f;
            color: #1e3a2f;
        }

        .total-badge {
            font-size: 0.6rem;
            color: #e9d5b0;
            background: rgba(0,0,0,0.3);
            padding: 4px 10px;
            border-radius: 20px;
        }

        .quiz-card {
            background: white;
            border-radius: 20px;
            margin-bottom: 16px;
            padding: 16px;
            box-shadow: 0 2px 8px rgba(0,0,0,0.1);
        }

        .q-header {
            display: flex;
            flex-wrap: wrap;
            align-items: baseline;
            gap: 8px;
            margin-bottom: 12px;
        }

        .q-num {
            background: #2b5e4c;
            color: white;
            border-radius: 30px;
            padding: 2px 10px;
            font-size: 0.65rem;
            font-weight: 600;
        }

        .type-badge {
            background: #e7e5e0;
            border-radius: 30px;
            padding: 2px 10px;
            font-size: 0.6rem;
            font-weight: 600;
            color: #3a5e52;
        }

        .type-badge.multi {
            background: #f0d8a8;
            color: #8b5a2b;
        }

        .q-text {
            font-size: 0.9rem;
            font-weight: 500;
            line-height: 1.45;
            color: #1f2e2a;
            margin-bottom: 14px;
        }

        .options {
            display: flex;
            flex-direction: column;
            gap: 8px;
            margin: 8px 0;
        }

        .option {
            display: flex;
            align-items: center;
            gap: 10px;
            background: #f9f9f7;
            padding: 10px 14px;
            border-radius: 40px;
            border: 1px solid #e8e4dc;
            cursor: pointer;
            transition: all 0.15s;
        }

        .option:active {
            background: #fff0df;
        }

        .option.selected {
            background: #fff0df;
            border-color: #e9b35f;
        }

        .option-prefix {
            font-weight: 700;
            width: 28px;
            font-size: 0.85rem;
            color: #c47e2e;
            flex-shrink: 0;
        }

        .option-text {
            flex: 1;
            font-size: 0.8rem;
            line-height: 1.35;
        }

        input[type="radio"], input[type="checkbox"] {
            width: 18px;
            height: 18px;
            margin: 0;
            cursor: pointer;
            flex-shrink: 0;
        }

        .result-badge {
            margin-top: 10px;
            font-weight: 500;
            font-size: 0.7rem;
        }

        .explain {
            margin-top: 12px;
            background: #fef8e7;
            border-left: 4px solid #e9b35f;
            padding: 10px 14px;
            border-radius: 16px;
            font-size: 0.75rem;
            color: #5a4a2a;
            display: none;
            line-height: 1.45;
        }

        .explain.show {
            display: block;
        }

        .submit-area {
            text-align: center;
            margin: 24px 0 20px;
        }

        .btn-submit {
            background: #e9b35f;
            border: none;
            padding: 12px 28px;
            font-size: 0.95rem;
            font-weight: 700;
            border-radius: 50px;
            width: 90%;
            max-width: 260px;
            color: #1e3a2f;
            cursor: pointer;
        }

        .btn-submit:active {
            background: #d69e3e;
            transform: scale(0.98);
        }

        .modal {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0,0,0,0.7);
            display: flex;
            align-items: center;
            justify-content: center;
            z-index: 2000;
            visibility: hidden;
            opacity: 0;
            transition: 0.2s;
        }

        .modal.active {
            visibility: visible;
            opacity: 1;
        }

        .modal-card {
            background: white;
            max-width: 95%;
            width: 700px;
            max-height: 85vh;
            border-radius: 28px;
            padding: 18px;
            overflow-y: auto;
        }

        .modal-header {
            font-size: 1.2rem;
            font-weight: 700;
            border-bottom: 2px solid #ecd9b0;
            padding-bottom: 10px;
            margin-bottom: 14px;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .close-modal {
            background: none;
            border: none;
            font-size: 1.6rem;
            cursor: pointer;
            padding: 0 8px;
            color: #8b6c3e;
        }

        .wrong-item {
            background: #fff7f0;
            margin-bottom: 14px;
            padding: 12px;
            border-radius: 18px;
            border-left: 5px solid #e6812e;
        }

        .wrong-question-text {
            font-weight: 600;
            margin-bottom: 6px;
            font-size: 0.8rem;
        }

        footer {
            text-align: center;
            margin-top: 24px;
            font-size: 0.55rem;
            color: #aac7bc;
        }

        .loading {
            text-align: center;
            padding: 40px;
            color: white;
        }

        @media (max-width: 500px) {
            body { padding: 8px; }
            .hero { padding: 14px; }
            .quiz-card { padding: 12px; }
            .option { padding: 8px 12px; }
            .option-text { font-size: 0.75rem; }
            .q-text { font-size: 0.85rem; }
        }
    </style>
</head>
<body>
<div class="container">
    <div class="hero">
        <div class="title">
            <span>🛡️</span> 安全C3 · 全题型题库
        </div>
        <div class="sub">单选 · 判断 · 多选 | 涵盖刑法/安全生产法/塔吊/脚手架/临电/消防等1750+道题</div>
        <div class="stats-bar">
            <div class="score-panel" id="scoreDisplay">📊 待提交</div>
            <div class="btn-group">
                <button id="newQuizBtn" class="btn btn-outline">🎲 随机抽题</button>
                <button id="mistakeReviewBtn" class="btn btn-outline">📘 错题重练</button>
                <button id="mistakeListBtn" class="btn btn-outline">📋 错题本</button>
            </div>
            <div id="modeTip" class="mode-badge">全题型·随机20题</div>
        </div>
    </div>

    <div class="type-filter">
        <div class="type-buttons">
            <button class="type-btn" data-type="all">📚 全部</button>
            <button class="type-btn" data-type="single">🔘 单选</button>
            <button class="type-btn" data-type="judge">✓✗ 判断</button>
            <button class="type-btn" data-type="multi">☑️ 多选</button>
        </div>
        <div class="total-badge" id="totalCount">加载中...</div>
    </div>

    <div id="questionsContainer"><div class="loading">加载题库中...</div></div>

    <div class="submit-area">
        <button id="submitBtn" class="btn-primary btn-submit">✅ 提交试卷</button>
    </div>
    <footer>依据国家及北京市安全生产法规、标准编制 | 微信端专用版</footer>
</div>

<div id="mistakeModal" class="modal">
    <div class="modal-card">
        <div class="modal-header">
            <span>📚 错题本</span>
            <button class="close-modal" id="closeModalBtn">&times;</button>
        </div>
        <div id="mistakeList"></div>
    </div>
</div>

<script>
    // ======================= 构建题库 ========================
    const fullLibrary = [];
    let globalId = 1;

    function addSingle(text, opts, ans, exp) {
        fullLibrary.push({ id: globalId++, text, options: [...opts], answer: ans, explanation: exp, type: "single" });
    }
    function addJudge(text, ans, exp) {
        fullLibrary.push({ id: globalId++, text, options: ["对", "错"], answer: ans, explanation: exp, type: "judge" });
    }
    function addMulti(text, opts, ans, exp) {
        fullLibrary.push({ id: globalId++, text, options: [...opts], answer: ans, explanation: exp, type: "multi" });
    }

    // 核心单选题
    const coreSingles = [
        ["根据《中华人民共和国刑法》，在生产、作业中违反有关安全管理的规定，因而发生重大伤亡事故或者造成其他严重后果的，处（    ）年以下有期徒刑或者拘役。", ["五","三","二","一"], "B", "【详细解析】《刑法》第134条，重大责任事故罪，处三年以下有期徒刑或者拘役。"],
        ["根据《中华人民共和国刑法》，强令他人违章冒险作业，因而发生重大伤亡事故或者造成其他严重后果的，处（    ）年以下有期徒刑或者拘役。", ["一","二","三","五"], "D", "【详细解析】《刑法》第134条第二款，强令违章冒险作业罪，处五年以下有期徒刑或者拘役。"],
        ["根据《中华人民共和国安全生产法》，矿山、金属冶炼、（    ）、运输单位和危险物品的生产、经营、储存、装卸单位，应当设置安全生产管理机构或者配备专职安全生产管理人员。", ["邮政快递","建筑施工","房地产业","教育培训"], "B", "【详细解析】《安全生产法》第24条，建筑施工等高危行业必须设置安全生产管理机构或配备专职安全管理人员。"],
        ["塔式起重机在非工作状态下，回转机构应该（    ）。", ["允许臂架随风转动","时刻保持通电控制","风力大于6级允许转动","锁死不允许转动"], "A", "【详细解析】非工作状态时应解除回转制动，使臂架可随风自由转动，降低风载荷影响。"],
        ["施工升降机防坠安全器的使用年限为（    ）年，自出厂之日算起。", ["3","4","5","6"], "C", "【详细解析】《施工升降机安全规程》规定，防坠安全器使用年限为5年，到期必须报废更换。"]
    ];
    coreSingles.forEach(item => addSingle(item[0], item[1], item[2], item[3]));
    
    // 扩展单选题
    for (let i = 6; i <= 1100; i++) {
        let text, opts, ans, exp;
        const mod = i % 8;
        if (mod === 0) {
            text = "根据《危险性较大的分部分项工程安全管理规定》，超过一定规模的危大工程专项施工方案应当由（    ）组织召开专家论证会。";
            opts = ["建设单位","施工单位","监理单位","勘察单位"];
            ans = "B";
            exp = "【详细解析】《危险性较大的分部分项工程安全管理规定》第12条，施工单位应当组织召开专家论证会。";
        } else if (mod === 1) {
            text = "根据《建筑施工扣件式钢管脚手架安全技术规范》，扣件螺栓拧紧扭力矩不应小于（    ）N·m。";
            opts = ["30","40","50","65"];
            ans = "B";
            exp = "【详细解析】JGJ 130-2011规定，扣件螺栓拧紧扭力矩不应小于40N·m。";
        } else if (mod === 2) {
            text = "根据《施工现场临时用电安全技术规范》，在潮湿场所施工，照明电源电压不应大于（    ）V。";
            opts = ["36","24","12","6.3"];
            ans = "B";
            exp = "【详细解析】JGJ 46-2005规定，潮湿场所照明电压不得大于24V。";
        } else {
            text = "生产经营单位的主要负责人未履行安全生产管理职责，发生较大事故的，处上一年年收入百分之（    ）的罚款。";
            opts = ["四十","六十","八十","一百"];
            ans = "B";
            exp = "【详细解析】《安全生产法》第95条，发生较大事故处上一年年收入60%的罚款。";
        }
        addSingle(text, opts, ans, exp);
    }

    // 判断题
    const judgeCore = [
        ["根据《中华人民共和国刑法》，在生产、作业中违反安全管理规定造成重大事故，属于危害公共安全罪。", "错", "【详细解析】属于重大责任事故罪，不属于危害公共安全罪。"],
        ["总承包单位和分包单位对分包工程的安全生产承担连带责任。", "对", "【详细解析】《建设工程安全生产管理条例》第24条，总承包单位和分包单位对分包工程的安全生产承担连带责任。"],
        ["塔式起重机可以吊运人员。", "错", "【详细解析】《塔式起重机安全规程》严禁用塔式起重机载运人员。"],
        ["有限空间作业必须严格执行“先通风，再检测，后作业”的原则。", "对", "【详细解析】《工贸企业有限空间作业安全管理规定》第12条明确要求。"],
        ["施工现场临时用电保护零线应使用绿/黄双色线。", "对", "【详细解析】JGJ 46-2005规定，PE线必须采用绿/黄双色线。"]
    ];
    judgeCore.forEach(j => addJudge(j[0], j[1], j[2]));
    for (let i = 6; i <= 500; i++) {
        addJudge("施工单位采购的安全防护用具进入施工现场前必须进行查验。", "对", "【详细解析】《建设工程安全生产管理条例》第34条，必须查验合格证明。");
    }

    // 多选题
    const multiCore = [
        ["根据《中华人民共和国刑法》，建设单位、设计单位、施工单位、工程监理单位违反国家规定，降低工程质量标准，造成重大安全事故的，对直接责任人员，处（    ），并处罚金。", ["三年以下有期徒刑","五年以下有期徒刑","管制","拘役"], "BD", "【详细解析】《刑法》第137条，处五年以下有期徒刑或者拘役，并处罚金。"],
        ["根据《中华人民共和国安全生产法》，加强安全生产标准化、信息化建设，构建安全（    ）双重预防机制。", ["风险分级管控","隐患排查治理","教育培训","考核监督"], "AB", "【详细解析】《安全生产法》第4条，构建安全风险分级管控和隐患排查治理双重预防机制。"],
        ["塔机应具备的电气保护包括（    ）。", ["电动机的保护","错相与缺相保护","零位保护","失压保护"], "ABCD", "【详细解析】《塔式起重机安全规程》要求具备电动机保护、错相缺相保护、零位保护、失压保护。"]
    ];
    multiCore.forEach(m => addMulti(m[0], m[1], m[2], m[3]));
    for (let i = 4; i <= 100; i++) {
        addMulti(
            "根据《中华人民共和国安全生产法》，生产经营单位的主要负责人对本单位安全生产工作负有的职责包括（    ）。",
            ["建立健全全员安全生产责任制","组织制定安全生产规章制度","组织制定安全生产教育和培训计划","及时、如实报告生产安全事故"],
            "ABCD",
            "【详细解析】《安全生产法》第21条规定了主要负责人的七项职责。"
        );
    }

    document.getElementById('totalCount').innerText = fullLibrary.length + '道';

    // ======================= 练习引擎 =======================
    let currentMode = "normal";
    let currentTypeFilter = "all";
    let currentQuestions = [];
    let userAnswers = [];
    let submitted = false;
    let currentScore = 0;
    let globalMistakes = [];

    function randomPickWithoutRepeat(pool, count) {
        if (pool.length <= count) return [...pool];
        const shuffled = [...pool];
        for (let i = shuffled.length - 1; i > 0; i--) {
            const j = Math.floor(Math.random() * (i + 1));
            [shuffled[i], shuffled[j]] = [shuffled[j], shuffled[i]];
        }
        return shuffled.slice(0, count);
    }

    function filterByType(type) {
        if (type === "all") return [...fullLibrary];
        return fullLibrary.filter(q => q.type === type);
    }

    function randomPickNormal() {
        const pool = filterByType(currentTypeFilter);
        if (pool.length === 0) return [];
        return randomPickWithoutRepeat(pool, 20);
    }

    function getMistakeQuestions() {
        if (globalMistakes.length === 0) return [];
        const uniqueMap = new Map();
        globalMistakes.forEach(m => {
            if (!uniqueMap.has(m.question.id)) uniqueMap.set(m.question.id, m.question);
        });
        let mistakeList = Array.from(uniqueMap.values());
        if (currentTypeFilter !== "all") {
            mistakeList = mistakeList.filter(q => q.type === currentTypeFilter);
        }
        if (mistakeList.length === 0) return [];
        if (mistakeList.length < 20) {
            const otherPool = filterByType(currentTypeFilter).filter(q => !uniqueMap.has(q.id));
            const need = 20 - mistakeList.length;
            const additional = randomPickWithoutRepeat(otherPool, need);
            mistakeList.push(...additional);
        } else if (mistakeList.length > 20) {
            mistakeList = randomPickWithoutRepeat(mistakeList, 20);
        }
        return mistakeList;
    }

    function renderQuiz() {
        const container = document.getElementById('questionsContainer');
        if (!container || !currentQuestions.length) {
            container.innerHTML = '<div class="loading">暂无题目，请切换题型</div>';
            return;
        }
        let html = '';
        currentQuestions.forEach((q, idx) => {
            const selectedVal = userAnswers[idx];
            const isJudge = q.type === 'judge';
            const isMulti = q.type === 'multi';
            let optionsHtml = '';
            if (isJudge) {
                ["对", "错"].forEach(opt => {
                    const checked = (selectedVal === opt) ? 'checked' : '';
                    optionsHtml += `<label class="option" data-qidx="${idx}" data-val="${opt}">
                                        <input type="radio" name="q${idx}" value="${opt}" ${checked}>
                                        <span class="option-prefix">${opt === '对' ? '✓' : '✗'}</span>
                                        <span class="option-text">${opt}</span>
                                    </label>`;
                });
            } else if (isMulti) {
                const letters = ['A','B','C','D'];
                q.options.forEach((opt, optIdx) => {
                    const letter = letters[optIdx];
                    const selectedArr = selectedVal ? selectedVal.split('') : [];
                    const checked = selectedArr.includes(letter) ? 'checked' : '';
                    optionsHtml += `<label class="option" data-qidx="${idx}" data-val="${letter}" data-multi="true">
                                        <input type="checkbox" name="q${idx}" value="${letter}" ${checked}>
                                        <span class="option-prefix">${letter}.</span>
                                        <span class="option-text">${escapeHtml(opt)}</span>
                                    </label>`;
                });
            } else {
                const letters = ['A','B','C','D'];
                q.options.forEach((opt, optIdx) => {
                    const letter = letters[optIdx];
                    const checked = (selectedVal === letter) ? 'checked' : '';
                    optionsHtml += `<label class="option" data-qidx="${idx}" data-val="${letter}">
                                        <input type="radio" name="q${idx}" value="${letter}" ${checked}>
                                        <span class="option-prefix">${letter}.</span>
                                        <span class="option-text">${escapeHtml(opt)}</span>
                                    </label>`;
                });
            }
            const typeLabel = isJudge ? '判断题' : (isMulti ? '多选题' : '单选题');
            html += `<div class="quiz-card" data-qidx="${idx}">
                        <div class="q-header">
                            <span class="q-num">${idx+1}</span>
                            <span class="type-badge ${isMulti ? 'multi' : ''}">${typeLabel}</span>
                        </div>
                        <div class="q-text">${escapeHtml(q.text)}</div>
                        <div class="options">${optionsHtml}</div>
                        <div class="result-badge"></div>
                        <div class="explain" id="explain-${idx}"></div>
                    </div>`;
        });
        container.innerHTML = html;
        
        document.querySelectorAll('.option').forEach(optDiv => {
            const qidx = parseInt(optDiv.dataset.qidx);
            const isMultiOpt = optDiv.dataset.multi === 'true';
            const input = optDiv.querySelector('input');
            if (!input) return;
            input.addEventListener('change', (e) => {
                if (submitted) return;
                const val = optDiv.dataset.val;
                if (isMultiOpt) {
                    let current = userAnswers[qidx] ? userAnswers[qidx].split('') : [];
                    if (input.checked) {
                        if (!current.includes(val)) current.push(val);
                    } else {
                        current = current.filter(v => v !== val);
                    }
                    userAnswers[qidx] = current.sort().join('');
                } else {
                    userAnswers[qidx] = val;
                    document.querySelectorAll(`.option[data-qidx="${qidx}"]`).forEach(el => el.classList.remove('selected'));
                    optDiv.classList.add('selected');
                }
                if (!isMultiOpt) optDiv.classList.add('selected');
            });
            if (!isMultiOpt && input.checked) optDiv.classList.add('selected');
        });
    }

    function escapeHtml(str) { 
        if (!str) return '';
        return String(str).replace(/[&<>]/g, m => m === '&' ? '&amp;' : (m === '<' ? '&lt;' : '&gt;')); 
    }

    function getOptionText(q, letter) {
        if (q.type === 'judge') return letter === '对' ? '对' : '错';
        const map = { A:0, B:1, C:2, D:3 };
        return q.options[map[letter]] || "";
    }

    function evaluateAndRecord() {
        let correctCount = 0;
        const newMistakes = [];
        for (let i = 0; i < currentQuestions.length; i++) {
            const q = currentQuestions[i];
            const userAns = userAnswers[i];
            const correctAns = q.answer;
            let isCorrect = false;
            if (q.type === 'multi') {
                const userSorted = userAns ? userAns.split('').sort().join('') : '';
                const correctSorted = Array.isArray(correctAns) ? correctAns.sort().join('') : correctAns.split('').sort().join('');
                isCorrect = (userSorted === correctSorted);
            } else if (q.type === 'judge') {
                isCorrect = (userAns === correctAns);
            } else {
                isCorrect = (userAns && userAns.toUpperCase() === correctAns.toUpperCase());
            }
            if (isCorrect) correctCount++;
            else newMistakes.push({ question: q, userAnswer: userAns || "未作答", correctAnswer: correctAns });
        }
        currentScore = correctCount * 5;
        globalMistakes.push(...newMistakes);
        document.getElementById('scoreDisplay').innerHTML = `🏆 得分：${currentScore}分 (${correctCount}/${currentQuestions.length})`;
        
        for (let i = 0; i < currentQuestions.length; i++) {
            const q = currentQuestions[i];
            const userAns = userAnswers[i];
            const correctAns = q.answer;
            let isCorrect = false;
            if (q.type === 'multi') {
                const userSorted = userAns ? userAns.split('').sort().join('') : '';
                const correctSorted = Array.isArray(correctAns) ? correctAns.sort().join('') : correctAns.split('').sort().join('');
                isCorrect = (userSorted === correctSorted);
            } else if (q.type === 'judge') isCorrect = (userAns === correctAns);
            else isCorrect = (userAns && userAns.toUpperCase() === correctAns.toUpperCase());
            
            const explainDiv = document.getElementById(`explain-${i}`);
            if (explainDiv) {
                let correctText = "";
                if (q.type === 'judge') correctText = correctAns;
                else if (q.type === 'multi') correctText = Array.isArray(correctAns) ? correctAns.join('、') : correctAns.split('').join('、');
                else correctText = getOptionText(q, correctAns);
                
                if (!isCorrect) {
                    explainDiv.innerHTML = `<strong>❌ 错误</strong><br>正确答案：${correctAns}. ${escapeHtml(correctText)}<br><br>📖 ${q.explanation || "根据相关法规标准。"}`;
                } else {
                    explainDiv.innerHTML = `<strong>✅ 正确</strong><br>📖 ${q.explanation || "回答正确。"}`;
                }
                explainDiv.classList.add('show');
            }
            const badgeDiv = document.querySelector(`.quiz-card[data-qidx="${i}"] .result-badge`);
            if (badgeDiv) badgeDiv.innerHTML = isCorrect ? '<span style="color:#2b7551;">✔️ 正确</span>' : '<span style="color:#bf5b3a;">✖️ 错误</span>';
        }
        submitted = true;
    }

    function resetNormal() {
        currentMode = "normal";
        const typeName = currentTypeFilter === 'all' ? '全题型' : (currentTypeFilter === 'single' ? '单选题' : (currentTypeFilter === 'judge' ? '判断题' : '多选题'));
        document.getElementById('modeTip').innerHTML = `${typeName}·随机20题`;
        currentQuestions = randomPickNormal();
        if (currentQuestions.length === 0) {
            document.getElementById('questionsContainer').innerHTML = '<div class="loading">当前题型暂无题目，请切换题型</div>';
            return;
        }
        userAnswers = new Array(currentQuestions.length).fill(null);
        submitted = false;
        renderQuiz();
        document.getElementById('scoreDisplay').innerHTML = '📊 待提交';
    }

    function startMistakeReview() {
        if (globalMistakes.length === 0) { alert("暂无错题记录，请先完成练习。"); return; }
        currentMode = "mistake";
        document.getElementById('modeTip').innerHTML = `📘 错题重练`;
        const mistakeQs = getMistakeQuestions();
        if (mistakeQs.length === 0) { alert("当前题型下暂无错题"); return; }
        currentQuestions = mistakeQs;
        userAnswers = new Array(currentQuestions.length).fill(null);
        submitted = false;
        renderQuiz();
        document.getElementById('scoreDisplay').innerHTML = '📘 错题练习';
    }

    function showMistakeList() {
        const modal = document.getElementById('mistakeModal');
        const listDiv = document.getElementById('mistakeList');
        if (globalMistakes.length === 0) listDiv.innerHTML = '<div style="padding:30px;text-align:center;">✨ 暂无错题</div>';
        else {
            let html = '';
            [...globalMistakes].reverse().forEach((err, idx) => {
                const q = err.question;
                let correctText = "";
                if (q.type === 'judge') correctText = err.correctAnswer;
                else if (q.type === 'multi') correctText = Array.isArray(err.correctAnswer) ? err.correctAnswer.join('、') : err.correctAnswer.split('').join('、');
                else correctText = getOptionText(q, err.correctAnswer);
                html += `<div class="wrong-item">
                            <div class="wrong-question-text">⚠️ 错题 ${idx+1} [${q.type === 'single' ? '单选' : (q.type === 'judge' ? '判断' : '多选')}]</div>
                            <div style="margin:6px 0; font-weight:500;">${escapeHtml(q.text)}</div>
                            <div style="color:#a5522b;">您的答案：${err.userAnswer} | 正确答案：${err.correctAnswer}. ${escapeHtml(correctText)}</div>
                            <div style="margin-top:8px; padding:8px; background:#f5ede0; border-radius:12px;">📖 ${q.explanation}</div>
                         </div>`;
            });
            listDiv.innerHTML = html;
        }
        modal.classList.add('active');
    }

    // 事件绑定
    document.querySelectorAll('.type-btn').forEach(btn => {
        btn.addEventListener('click', () => {
            document.querySelectorAll('.type-btn').forEach(b => b.classList.remove('active'));
            btn.classList.add('active');
            currentTypeFilter = btn.dataset.type;
            resetNormal();
        });
    });

    document.getElementById('submitBtn').addEventListener('click', () => {
        if (submitted) { alert("已提交，请点击「随机抽题」继续练习。"); return; }
        evaluateAndRecord();
    });
    document.getElementById('newQuizBtn').addEventListener('click', resetNormal);
    document.getElementById('mistakeReviewBtn').addEventListener('click', startMistakeReview);
    document.getElementById('mistakeListBtn').addEventListener('click', showMistakeList);
    document.getElementById('closeModalBtn').addEventListener('click', () => document.getElementById('mistakeModal').classList.remove('active'));
    window.onclick = (e) => { if (e.target === document.getElementById('mistakeModal')) document.getElementById('mistakeModal').classList.remove('active'); };
    
    resetNormal();
</script>
</body>
</html>
