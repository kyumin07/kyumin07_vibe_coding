# kyumin07_vibe_coding
바이브 코딩 연습
<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>바이브 코딩 실습 - 투두리스트</title>
    <style>
        /* CSS: 웹사이트의 디자인과 스타일을 담당하는 구문 */
        body {
            font-family: 'Arial', sans-serif;
            background-color: #f4f7f6;
            color: #333;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
            transition: background 0.3s, color 0.3s; /* 부드러운 배경색 전환 */
        }
        /* 다크모드 전용 스타일 */
        body.dark-mode {
            background-color: #1e1e1e;
            color: #ffffff;
        }
        .container {
            background: white;
            padding: 30px;
            border-radius: 10px;
            box-shadow: 0 4px 10px rgba(0,0,0,0.1);
            text-align: center;
        }
        body.dark-mode .container {
            background: #2d2d2d;
        }
        input {
            padding: 10px;
            width: 200px;
            border: 1px solid #ccc;
            border-radius: 5px;
        }
        button {
            padding: 10px 15px;
            border: none;
            background-color: #28a745;
            color: white;
            border-radius: 5px;
            cursor: pointer;
        }
        button:hover { background-color: #218838; }
        ul { list-style: none; padding: 0; }
        li {
            padding: 10px;
            background: #eee;
            margin: 5px 0;
            border-radius: 5px;
            display: flex;
            justify-content: space-between;
        }
        body.dark-mode li { background: #444; }
        .toggle-btn { background-color: #007bff; margin-bottom: 20px; }
    </style>
</head>
<body>

    <div class="container">
        <!-- 상단 다크모드 토글 버튼 -->
        <button class="toggle-btn" id="darkModeBtn">테마 변경</button>
        
        <h2>My Todo List</h2>
        
        <!-- 할 일 입력창과 추가 버튼 -->
        <input type="text" id="todoInput" placeholder="할 일을 입력하세요...">
        <button id="addBtn">추가</button>
        
        <!-- 할 일 목록이 추가될 배열 공간 -->
        <ul id="todoList"></ul>
    </div>

    <!-- JavaScript: 웹사이트의 동적 기능과 논리(로직)를 담당하는 문법 -->
    <script>
        // 1. 변수 선언 (DOM 요소 매칭)
        // const는 변하지 않는 상수를 선언할 때 사용합니다.
        const darkModeBtn = document.getElementById('darkModeBtn');
        const todoInput = document.getElementById('todoInput');
        const addBtn = document.getElementById('addBtn');
        const todoList = document.getElementById('todoList');

        // 2. 이벤트 리스너 (사용자의 클릭 행동 감지)
        // 'click' 이벤트가 발생하면 화살표 함수(=>) 내부의 코드가 실행됩니다.
        darkModeBtn.addEventListener('click', () => {
            // 조건문(if-else) 대신 classList.toggle을 사용해 다크모드 클래스를 켜고 끕니다.
            document.body.classList.toggle('dark-mode');
        });

        // 3. 할 일 추가 함수
        function addTodo() {
            // 변수 선언 (let은 값이 변할 수 있는 변수를 의미합니다)
            let text = todoInput.value.trim(); 

            // 조건문 (기초 문법: IF문)
            // 입력창이 비어있는지 확인합니다.
            if (text === "") {
                alert("내용을 입력해 주세요!"); // 경고창 띄우기
                return; // 함수 종료
            }

            // 새로운 HTML 태그(li)를 자바스크립트로 동적 생성
            const li = document.createElement('li');
            li.textContent = text;

            // 삭제 버튼 추가
            const delBtn = document.createElement('button');
            delBtn.textContent = 'X';
            delBtn.style.backgroundColor = '#dc3545';
            delBtn.style.padding = '2px 8px';
            
            // 삭제 버튼 클릭 시 해당 li 요소를 지우는 이벤트 리스너
            delBtn.addEventListener('click', () => {
                li.remove();
            });

            // 생성된 삭제 버튼을 리스트 항목에 넣고, 최종적으로 UL 태그에 결합
            li.appendChild(delBtn);
            todoList.appendChild(li);

            // 입력창 초기화
            todoInput.value = "";
        }

        // 추가 버튼 클릭 시 함수 실행
        addBtn.addEventListener('click', addTodo);

        // 엔터키를 눌렀을 때도 추가되도록 설정 (조건문 활용)
        todoInput.addEventListener('keypress', (e) => {
            if (e.key === 'Enter') {
                addTodo();
            }
        });
    </script>
</body>
</html>
