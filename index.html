<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>재미있는 MBTI 성격 테스트</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Noto+Sans+KR:wght@400;700&display=swap');
        
        body {
            font-family: 'Noto Sans KR', sans-serif;
            background-color: #f0f4f8;
            color: #333;
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            margin: 0;
        }

        #app {
            background-color: white;
            width: 90%;
            max-width: 500px;
            border-radius: 20px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.1);
            padding: 40px 30px;
            text-align: center;
        }

        /* 시작 화면 */
        .title { font-size: 28px; font-weight: bold; margin-bottom: 10px; color: #2c3e50; }
        .subtitle { font-size: 16px; color: #7f8c8d; margin-bottom: 30px; }
        .btn {
            background-color: #3498db;
            color: white;
            border: none;
            padding: 15px 30px;
            font-size: 18px;
            border-radius: 30px;
            cursor: pointer;
            transition: background-color 0.3s;
            width: 100%;
        }
        .btn:hover { background-color: #2980b9; }

        /* 질문 화면 */
        #question-screen { display: none; }
        .progress-bar {
            width: 100%;
            background-color: #ecf0f1;
            border-radius: 10px;
            margin-bottom: 20px;
            overflow: hidden;
        }
        .progress {
            width: 0%;
            height: 10px;
            background-color: #2ecc71;
            transition: width 0.3s;
        }
        .question-text { font-size: 22px; font-weight: bold; margin-bottom: 30px; word-break: keep-all; }
        .answer-btn {
            background-color: #ecf0f1;
            color: #2c3e50;
            border: none;
            padding: 15px;
            font-size: 16px;
            border-radius: 15px;
            cursor: pointer;
            margin-bottom: 15px;
            width: 100%;
            transition: all 0.3s;
            word-break: keep-all;
        }
        .answer-btn:hover { background-color: #bdc3c7; transform: translateY(-2px); }

        /* 결과 화면 */
        #result-screen { display: none; }
        .emoji { font-size: 80px; margin-bottom: 10px; }
        .mbti-type { font-size: 24px; font-weight: bold; color: #e74c3c; margin-bottom: 5px; }
        .mbti-title { font-size: 20px; font-weight: bold; margin-bottom: 20px; color: #2c3e50; }
        .desc-box { background-color: #f8f9fa; padding: 20px; border-radius: 15px; margin-bottom: 20px; text-align: left; }
        .desc-title { font-weight: bold; color: #34495e; margin-bottom: 10px; }
        .pros, .cons { margin-bottom: 15px; font-size: 15px; line-height: 1.5; }
    </style>
</head>
<body>

    <div id="app">
        <!-- 시작 화면 -->
        <div id="start-screen">
            <div class="emoji">✨</div>
            <div class="title">나의 진짜 성격은?</div>
            <div class="subtitle">32개의 간단한 질문으로 알아보는 MBTI</div>
            <button class="btn" onclick="startTest()">테스트 시작하기</button>
        </div>

        <!-- 질문 화면 -->
        <div id="question-screen">
            <div class="progress-bar">
                <div class="progress" id="progress"></div>
            </div>
            <div id="question-count" style="color: #7f8c8d; margin-bottom: 10px; font-size: 14px;"></div>
            <div class="question-text" id="question"></div>
            <button class="answer-btn" id="answer1" onclick="nextQuestion(1)"></button>
            <button class="answer-btn" id="answer2" onclick="nextQuestion(2)"></button>
        </div>

        <!-- 결과 화면 -->
        <div id="result-screen">
            <div class="emoji" id="result-emoji"></div>
            <div class="mbti-type" id="result-type"></div>
            <div class="mbti-title" id="result-title"></div>
            
            <div class="desc-box">
                <div class="desc-title">👍 이런 점이 멋져요 (장점)</div>
                <div class="pros" id="result-pros"></div>
                <div class="desc-title">👎 이건 조심해요 (단점)</div>
                <div class="cons" id="result-cons"></div>
            </div>

            <button class="btn" onclick="location.reload()">다시 하기</button>
        </div>
    </div>

    <script>
        // 32개의 간결한 질문 데이터 (E/I, S/N, T/F, J/P 각 8문제)
        const questions = [
            { type: 'EI', q: '주말에 나는?', a1: { text: '친구들과 밖에서 신나게 논다', value: 'E' }, a2: { text: '집에서 혼자 푹 쉰다', value: 'I' } },
            { type: 'EI', q: '처음 가는 모임에서 나는?', a1: { text: '먼저 다가가서 말을 건다', value: 'E' }, a2: { text: '누군가 말을 걸어주길 기다린다', value: 'I' } },
            { type: 'EI', q: '스트레스를 풀 때 나는?', a1: { text: '사람들을 만나 수다를 떤다', value: 'E' }, a2: { text: '혼자만의 시간을 가지며 힐링한다', value: 'I' } },
            { type: 'EI', q: '엘리베이터에 이웃과 단둘이 탔다.', a1: { text: '가벼운 날씨 이야기라도 꺼낸다', value: 'E' }, a2: { text: '조용히 층수만 쳐다본다', value: 'I' } },
            { type: 'EI', q: '친구가 갑자기 만나자고 하면?', a1: { text: '좋아! 당장 나갈게!', value: 'E' }, a2: { text: '아.. 오늘은 이미 누웠는데 내일 볼까?', value: 'I' } },
            { type: 'EI', q: '나의 에너지는 주로?', a1: { text: '외부 활동을 통해 충전된다', value: 'E' }, a2: { text: '혼자 있을 때 충전된다', value: 'I' } },
            { type: 'EI', q: '대화할 때 나는?', a1: { text: '주로 이야기를 주도하는 편이다', value: 'E' }, a2: { text: '주로 들어주는 편이다', value: 'I' } },
            { type: 'EI', q: '팀 프로젝트를 할 때 나는?', a1: { text: '다 같이 모여서 아이디어를 낸다', value: 'E' }, a2: { text: '각자 파트를 나누고 혼자 작업한다', value: 'I' } },
            
            { type: 'SN', q: '사과를 보면 떠오르는 것은?', a1: { text: '빨갛다, 달콤하다, 과일', value: 'S' }, a2: { text: '백설공주, 뉴욕, 아이폰', value: 'N' } },
            { type: 'SN', q: '요리할 때 나는?', a1: { text: '레시피의 정량을 정확히 지킨다', value: 'S' }, a2: { text: '감에 의존해서 대충 넣는다', value: 'N' } },
            { type: 'SN', q: '미래에 대해 생각할 때?', a1: { text: '당장 현실적인 계획부터 세운다', value: 'S' }, a2: { text: '다양한 가능성과 상상을 펼친다', value: 'N' } },
            { type: 'SN', q: '책이나 영화를 볼 때?', a1: { text: '사건의 전개와 사실 관계에 집중한다', value: 'S' }, a2: { text: '숨겨진 의미나 비유를 찾는다', value: 'N' } },
            { type: 'SN', q: '길을 찾을 때 나는?', a1: { text: '지도와 표지판을 꼼꼼히 본다', value: 'S' }, a2: { text: '대략적인 나의 방향 감각을 믿는다', value: 'N' } },
            { type: 'SN', q: '일할 때 선호하는 방식은?', a1: { text: '기존에 검증된 안전한 방식', value: 'S' }, a2: { text: '새롭고 창의적인 방식', value: 'N' } },
            { type: 'SN', q: '멍 때릴 때 나는?', a1: { text: '주변의 소리나 풍경을 느낀다', value: 'S' }, a2: { text: '우주의 끝은 어딜까 상상한다', value: 'N' } },
            { type: 'SN', q: '누군가에게 길을 설명할 때?', a1: { text: '사거리에서 우회전, 100m 직진해', value: 'S' }, a2: { text: '큰 병원 보이면 그 뒷골목에 있어', value: 'N' } },
            
            { type: 'TF', q: '친구가 "우울해서 화분 샀어"라고 한다면?', a1: { text: '무슨 화분 샀어? 사진 보여줘!', value: 'T' }, a2: { text: '왜 우울해? 무슨 일 있었어?', value: 'F' } },
            { type: 'TF', q: '결정을 내릴 때 더 중요한 것은?', a1: { text: '객관적인 논리와 사실', value: 'T' }, a2: { text: '사람들의 감정과 조화', value: 'F' } },
            { type: 'TF', q: '친구가 힘든 일을 겪을 때 나는?', a1: { text: '현실적인 해결책을 제시한다', value: 'T' }, a2: { text: '따뜻하게 공감하고 안아준다', value: 'F' } },
            { type: 'TF', q: '팀원이 실수를 했을 때?', a1: { text: '실수한 원인을 명확히 짚어준다', value: 'T' }, a2: { text: '많이 당황했겠다며 먼저 다독인다', value: 'F' } },
            { type: 'TF', q: '슬픈 영화를 볼 때 나는?', a1: { text: '어떻게 저렇게 연출했지? 분석한다', value: 'T' }, a2: { text: '주인공에 완벽 이입해서 펑펑 운다', value: 'F' } },
            { type: 'TF', q: '나에게 더 상처가 되는 말은?', a1: { text: '넌 왜 이렇게 생각이 없니?', value: 'T' }, a2: { text: '넌 왜 이렇게 매정하니?', value: 'F' } },
            { type: 'TF', q: '논쟁이 일어났을 때 나는?', a1: { text: '무엇이 옳고 그른지 따져야 직성이 풀린다', value: 'T' }, a2: { text: '관계가 상할까 봐 마음이 조마조마하다', value: 'F' } },
            { type: 'TF', q: '부탁을 거절할 때 나는?', a1: { text: '안 되는 이유를 명확하게 말한다', value: 'T' }, a2: { text: '미안해하며 최대한 빙빙 돌려 말한다', value: 'F' } },

            { type: 'JP', q: '여행을 갈 때 나는?', a1: { text: '일별, 시간별로 세부 계획을 짠다', value: 'J' }, a2: { text: '발길 닿는 대로 유동적으로 다닌다', value: 'P' } },
            { type: 'JP', q: '나의 방 청소 스타일은?', a1: { text: '주기적으로 정돈된 상태를 유지한다', value: 'J' }, a2: { text: '어지르다가 날 잡고 한 번에 치운다', value: 'P' } },
            { type: 'JP', q: '약속 시간에 나는?', a1: { text: '미리 도착해서 기다리는 편이다', value: 'J' }, a2: { text: '딱 맞춰 가거나 아슬아슬하게 도착한다', value: 'P' } },
            { type: 'JP', q: '과제가 주어졌을 때?', a1: { text: '미리미리 일정을 짜서 조금씩 해둔다', value: 'J' }, a2: { text: '마감일 직전에 엄청난 집중력을 발휘한다', value: 'P' } },
            { type: 'JP', q: '식당을 고를 때 나는?', a1: { text: '미리 맛집을 검색하고 예약해 둔다', value: 'J' }, a2: { text: '걷다가 맛있어 보이는 곳에 즉흥적으로 간다', value: 'P' } },
            { type: 'JP', q: '예상치 못한 일이 생겼을 때?', a1: { text: '계획이 틀어져서 엄청난 스트레스를 받는다', value: 'J' }, a2: { text: '그 상황에 맞춰 유연하게 대처한다', value: 'P' } },
            { type: 'JP', q: '나의 스마트폰 알림 상태는?', a1: { text: '모두 확인해서 빨간 숫자를 다 없앤다', value: 'J' }, a2: { text: '안 읽은 알림이 999+개 쌓여 있다', value: 'P' } },
            { type: 'JP', q: '목표를 세울 때 나는?', a1: { text: '구체적인 달성 단계를 체계적으로 짠다', value: 'J' }, a2: { text: '대략적인 큰 방향만 잡아둔다', value: 'P' } }
        ];

        // 16가지 결과 데이터
        const results = {
            "ISTJ": { emoji: "📝", title: "꼼꼼한 원칙주의자 거북이", pros: "책임감이 강하고 약속을 철저하게 지켜요. 한번 시작한 일은 끝까지 해내는 성실함이 무기입니다.", cons: "융통성이 다소 부족할 수 있어요. 가끔은 변화를 받아들이는 연습이 필요해요." },
            "ISFJ": { emoji: "🧸", title: "따뜻한 수호천사 곰돌이", pros: "타인의 감정을 잘 살피고 배려심이 깊어요. 조용하지만 든든하게 주변 사람들을 챙깁니다.", cons: "거절을 잘 못해서 혼자 상처받거나 스트레스를 떠안을 때가 많아요." },
            "INFJ": { emoji: "🔮", title: "신비로운 통찰력의 부엉이", pros: "사람과 상황을 꿰뚫어 보는 통찰력이 뛰어나요. 강한 신념을 가지고 이상을 향해 나아갑니다.", cons: "완벽주의 성향이 있어서 스스로를 피곤하게 만들 때가 있어요." },
            "INTJ": { emoji: "♟️", title: "체스 마스터 흑표범", pros: "분석력이 뛰어나고 전략을 세우는 데 천재적이에요. 독립적이고 목표 달성 능력이 탁월합니다.", cons: "감정 표현에 서툴러서 차갑거나 거만하다는 오해를 받을 수 있어요." },
            "ISTP": { emoji: "🛠️", title: "만능 재주꾼 고양이", pros: "위기 상황에서 침착하고 논리적으로 문제를 해결해요. 관찰력이 뛰어나고 손재주가 좋아요.", cons: "지루한 것을 못 참고, 타인의 감정에 공감하는 데 에너지를 잘 쓰지 않아요." },
            "ISFP": { emoji: "🎨", title: "평화로운 예술가 나무늘보", pros: "다정하고 온화하며 현재의 즐거움을 만끽할 줄 알아요. 예술적 감각이 뛰어나고 자유롭습니다.", cons: "규칙이나 속박을 싫어해서 계획을 끝까지 실천하는 추진력이 부족할 수 있어요." },
            "INFP": { emoji: "🌸", title: "감성 충만 몽상가 토끼", pros: "마음이 따뜻하고 상상력이 풍부해요. 타인을 잘 이해하고 진정성 있는 관계를 중요하게 생각해요.", cons: "현실 감각이 떨어질 때가 있고, 감정 기복이 심해 상처를 쉽게 받아요." },
            "INTP": { emoji: "🔬", title: "호기심 많은 괴짜 아인슈타인", pros: "지적 호기심이 뛰어나고 아이디어가 번뜩여요. 논리적이고 객관적인 분석에 강합니다.", cons: "생각만 하다가 실천으로 옮기지 못하는 경우가 많고, 일상적인 규칙을 귀찮아해요." },
            "ESTP": { emoji: "🏎️", title: "스릴을 즐기는 불나방", pros: "에너지가 넘치고 어디서든 적응을 잘해요. 문제 해결이 빠르고 센스가 넘칩니다.", cons: "충동적이고 뒷일을 생각하지 않고 행동해서 가끔 사고를 칠 수 있어요." },
            "ESFP": { emoji: "🎤", title: "무대 체질 파티피플 돌고래", pros: "사교적이고 긍정적인 에너지로 주변을 즐겁게 만들어요. 현재를 가장 행복하게 즐기는 사람입니다.", cons: "진지하고 복잡한 상황을 회피하려 하고, 장기적인 계획을 세우는 것을 어려워해요." },
            "ENFP": { emoji: "🐶", title: "인간 비타민 골든리트리버", pros: "열정이 넘치고 새로운 시도를 좋아해요. 사람을 좋아하고 주변에 긍정적인 영향을 줍니다.", cons: "시작은 잘하지만 끈기 있게 마무리하는 능력이 약하고 산만해 보일 수 있어요." },
            "ENTP": { emoji: "💡", title: "번뜩이는 아이디어 발명가 원숭이", pros: "다방면에 재능이 많고 토론을 즐겨요. 창의적이고 문제를 새로운 시각으로 바라봅니다.", cons: "반복되는 일상을 지루해하며, 가끔은 상대방의 감정보다 논리를 앞세워 상처를 주기도 해요." },
            "ESTJ": { emoji: "💼", title: "불도저 같은 팩트폭격기 호랑이", pros: "리더십이 있고 체계적으로 일을 추진해요. 현실적이고 책임감이 강해 믿고 맡길 수 있습니다.", cons: "자신의 기준을 타인에게 강요하거나 공감 능력 없이 팩트만 말해 상처를 줄 수 있어요." },
            "ESFJ": { emoji: "🤝", title: "다정한 골목대장 펭귄", pros: "친절하고 동정심이 많으며 사람들을 잘 챙겨요. 조화로운 관계를 유지하는 데 탁월한 능력이 있어요.", cons: "타인의 인정과 시선에 너무 의존하며, 남의 부탁을 거절하지 못해 피곤해집니다." },
            "ENFJ": { emoji: "☀️", title: "세상을 이끄는 햇살 강아지", pros: "따뜻한 카리스마로 사람들을 이끌어줘요. 타인의 성장을 돕는 것을 좋아하고 말솜씨가 뛰어납니다.", cons: "남의 문제에 지나치게 관여하다가 정작 자신의 상처나 스트레스를 돌보지 못할 때가 있어요." },
            "ENTJ": { emoji: "👑", title: "카리스마 넘치는 야망가 사자", pros: "결단력이 있고 장기적인 비전을 잘 세워요. 목표를 향해 흔들림 없이 나아가는 타고난 리더입니다.", cons: "효율성을 중시하다 보니 다른 사람의 감정이나 한계를 무시하고 밀어붙일 때가 있어요." }
        };

        // 변수 초기화
        let currentQuestion = 0;
        let scores = { E: 0, I: 0, S: 0, N: 0, T: 0, F: 0, J: 0, P: 0 };

        // 요소 가져오기
        const startScreen = document.getElementById('start-screen');
        const questionScreen = document.getElementById('question-screen');
        const resultScreen = document.getElementById('result-screen');
        const questionEl = document.getElementById('question');
        const answer1El = document.getElementById('answer1');
        const answer2El = document.getElementById('answer2');
        const progressEl = document.getElementById('progress');
        const questionCountEl = document.getElementById('question-count');

        // 테스트 시작
        function startTest() {
            startScreen.style.display = 'none';
            questionScreen.style.display = 'block';
            showQuestion();
        }

        // 질문 표시
        function showQuestion() {
            const q = questions[currentQuestion];
            questionEl.innerText = q.q;
            answer1El.innerText = q.a1.text;
            answer2El.innerText = q.a2.text;
            
            // 진행률 업데이트
            const percent = ((currentQuestion) / questions.length) * 100;
            progressEl.style.width = percent + '%';
            questionCountEl.innerText = `${currentQuestion + 1} / ${questions.length}`;

            // 버튼 클릭 이벤트에 답변 값 전달
            answer1El.onclick = () => selectAnswer(q.a1.value);
            answer2El.onclick = () => selectAnswer(q.a2.value);
        }

        // 답변 선택
        function selectAnswer(value) {
            scores[value]++; // 선택한 성향 점수 증가
            currentQuestion++;

            if (currentQuestion < questions.length) {
                showQuestion();
            } else {
                showResult();
            }
        }

        // 결과 계산 및 표시
        function showResult() {
            questionScreen.style.display = 'none';
            resultScreen.style.display = 'block';

            // MBTI 유형 계산
            let mbti = "";
            mbti += (scores.E >= scores.I) ? "E" : "I";
            mbti += (scores.S >= scores.N) ? "S" : "N";
            mbti += (scores.T >= scores.F) ? "T" : "F";
            mbti += (scores.J >= scores.P) ? "J" : "P";

            const resultData = results[mbti];

            // 결과 화면 업데이트
            document.getElementById('result-emoji').innerText = resultData.emoji;
            document.getElementById('result-type').innerText = mbti;
            document.getElementById('result-title').innerText = resultData.title;
            document.getElementById('result-pros').innerText = resultData.pros;
            document.getElementById('result-cons').innerText = resultData.cons;
        }
    </script>
</body>
</html>
