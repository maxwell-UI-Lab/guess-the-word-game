[wordgame.html](https://github.com/user-attachments/files/28095720/wordgame.html)
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Skribbl.io Clone</title>
    <script src="https://unpkg.com/peerjs@1.5.2/dist/peerjs.min.js"></script>
    <style>
        :root {
            --bg-color: #164e63;
            --panel-bg: #ffffff;
            --primary: #0284c7;
            --secondary: #22c55e;
            --danger: #ef4444;
            --dark: #1e293b;
            --gray-light: #f1f5f9;
            --gray-border: #cbd5e1;
        }
        
        * { box-sizing: border-box; font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif; }
        
        body {
            background-color: var(--bg-color);
            color: var(--dark);
            margin: 0;
            padding: 20px;
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
        }

        .lobby-container {
            width: 100%;
            max-width: 500px;
            background: var(--panel-bg);
            padding: 30px;
            border-radius: 16px;
            box-shadow: 0 10px 25px rgba(0,0,0,0.3);
            text-align: center;
        }

        .screen { display: none; }
        .active { display: block; }
        
        /* Skribbl Dual Panel Layout */
        .game-container {
            display: grid;
            grid-template-columns: 2fr 1fr;
            gap: 20px;
            width: 100%;
            max-width: 950px;
            background: #0f172a;
            padding: 20px;
            border-radius: 16px;
            box-shadow: 0 15px 30px rgba(0,0,0,0.4);
        }

        @media (max-width: 768px) {
            .game-container { grid-template-columns: 1fr; }
        }

        /* Left Side: Game Display Panel */
        .game-main {
            background: var(--panel-bg);
            border-radius: 12px;
            padding: 20px;
            display: flex;
            flex-direction: column;
            justify-content: space-between;
            min-height: 400px;
            position: relative;
        }

        /* Right Side: Chat & Guessing Panel */
        .game-sidebar {
            background: #f8fafc;
            border-radius: 12px;
            padding: 15px;
            display: flex;
            flex-direction: column;
            height: 450px;
            border: 4px solid var(--gray-border);
        }

        /* Top Status Bar Style */
        .top-bar {
            display: flex;
            justify-content: space-between;
            align-items: center;
            background: #e2e8f0;
            padding: 10px 15px;
            border-radius: 8px;
            font-weight: bold;
            margin-bottom: 15px;
        }

        .timer-badge {
            background: var(--danger);
            color: white;
            padding: 5px 12px;
            border-radius: 20px;
            font-size: 18px;
        }

        /* Hidden Blank Blanks Area */
        .word-canvas-area {
            flex-grow: 1;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            background: #fdfdfd;
            border: 2px dashed #cbd5e1;
            border-radius: 8px;
            margin-bottom: 15px;
            padding: 20px;
        }

        #word-display {
            font-size: 42px;
            letter-spacing: 12px;
            font-family: monospace;
            font-weight: bold;
            color: #0f172a;
            margin-bottom: 5px;
            text-align: center;
        }

        #hint-display {
            font-size: 16px;
            color: #64748b;
            font-weight: 600;
            font-style: italic;
        }

        /* Word Choosing Interface */
        .word-choices {
            display: flex;
            gap: 10px;
            width: 100%;
            justify-content: center;
            margin-top: 15px;
        }

        .word-card {
            background: #0284c7;
            color: white;
            padding: 12px 24px;
            font-weight: bold;
            border-radius: 8px;
            cursor: pointer;
            border: none;
            transition: transform 0.1s, background 0.2s;
        }
        .word-card:hover { background: #0369a1; transform: scale(1.05); }

        /* Forms & Interactive Controls */
        .input-group {
            display: flex;
            gap: 8px;
            margin-top: auto;
        }

        input[type="text"] {
            flex-grow: 1;
            padding: 12px;
            border: 2px solid var(--gray-border);
            border-radius: 8px;
            font-size: 16px;
            outline: none;
        }
        input[type="text"]:focus { border-color: var(--primary); }

        .btn {
            background: var(--primary);
            color: white;
            border: none;
            padding: 12px 20px;
            font-weight: bold;
            border-radius: 8px;
            cursor: pointer;
        }
        .btn:hover { opacity: 0.9; }
        .btn-success { background: var(--secondary); }

        /* Chat feed box matching Skribbl */
        #chat-box {
            flex-grow: 1;
            overflow-y: auto;
            margin-bottom: 10px;
            padding: 5px;
            display: flex;
            flex-direction: column;
            gap: 6px;
            font-size: 15px;
        }

        .chat-msg {
            padding: 6px 10px;
            border-radius: 6px;
            background: #f1f5f9; 
            color: var(--dark);
            word-break: break-all;
        }
        .chat-msg.wrong { background: #fee2e2; color: #991b1b; }
        .chat-msg.correct { background: #dcfce7; color: #166534; font-weight: bold; border-left: 5px solid var(--secondary); }
        .chat-msg.system { background: #ffedd5; color: #9a3412; font-weight: bold; text-align: center; }
    </style>
</head>
<body>

    <div id="lobby-screen" class="screen active lobby-container">
        <h2 style="color: var(--primary); margin-top: 0;">Skribbl Word Game</h2>
        <input type="text" id="username" placeholder="Enter Nickname" value="Player">
        <button class="btn btn-success" style="width:100%; margin-bottom:12px;" onclick="createRoom()">Create Room</button>
        <div style="margin: 10px 0; color: #64748b; font-weight: bold;">OR</div>
        <input type="text" id="join-room-id" placeholder="Enter Room ID">
        <button class="btn" style="width:100%; margin-bottom:12px;" onclick="joinRoom()">Join Room</button>
        <button class="btn" style="width:100%; background:#64748b;" onclick="joinRandom()">Play Random Match</button>
    </div>

    <div id="waiting-screen" class="screen lobby-container">
        <h3>Waiting for Players...</h3>
        <div class="room-id-box" id="display-room-id" style="background:#f1f5f9; padding:15px; border-radius:8px; font-family:monospace; margin:15px 0;">Generating ID...</div>
        <p style="font-size: 14px; color:#64748b;">Give this Room ID to your partner to connect.</p>
        <button class="btn" style="background:var(--danger);" onclick="location.reload()">Exit Room</button>
    </div>

    <div id="game-screen" class="screen game-container">
        
        <div class="game-main">
            <div class="top-bar">
                <span id="player-role">Role: Loading...</span>
                <span id="game-status">Get Ready...</span>
                <div class="timer-badge" id="timer-box"><span id="timer-count">30</span>s</div>
            </div>

            <div class="word-canvas-area">
                <div id="word-display">_ _ _ _ _</div>
                <div id="hint-display">(Waiting for word selection)</div>
            </div>

            <div id="host-selection" style="display:none; background:#f8fafc; padding:15px; border-radius:10px; border:2px solid #cbd5e1;">
                <h4 style="margin:0 0 10px 0; text-align:center; color: var(--primary)">Select your secret word:</h4>
                <div class="word-choices">
                    <button class="word-card" id="word-opt-0" onclick="selectWord(0)">Word1</button>
                    <button class="word-card" id="word-opt-1" onclick="selectWord(1)">Word2</button>
                    <button class="word-card" id="word-opt-2" onclick="selectWord(2)">Word3</button>
                </div>
                <input type="text" id="secret-hint" placeholder="Add a custom hint/clue (Optional)" style="margin-top:12px;">
            </div>
        </div>

        <div class="game-sidebar">
            <div style="font-weight:bold; border-bottom: 2px solid var(--gray-border); padding-bottom:5px; margin-bottom:10px;" id="opponent-name">Opponent: -</div>
            
            <div id="chat-box"></div>

            <div id="game-controls" class="input-group" style="display:none;">
                <input type="text" id="guess-input" placeholder="Type a message or a guess..." onkeydown="if(event.key==='Enter') submitInput()">
                <button class="btn btn-success" onclick="submitInput()">Send</button>
            </div>
        </div>

    </div>

<script>
    let peer = null, conn = null;
    let myName = "Player", opponentName = "Opponent";
    let isWordMaster = false; 
    let amIRoomCreator = false; 
    
    const wordPool = [
        "APPLE", "BANANA", "GUITAR", "MONKEY", "ROCKET", "CASTLE", "DRAGON", "ROBOT", 
        "PIRATE", "PIZZA", "BURGER", "CAMERA", "LAPTOP", "SPIDER", "WIZARD", "ZOMBIE",
        "DOCTOR", "SOCCER", "NINJA", "AIRPLANE", "SHARK", "DIAMOND", "SUBWAY", "COFFEE"
    ];
    let currentChoices = [], currentWord = "", currentHint = "", guessedLetters = [], lives = 6;
    let turnTimer = null, timeLeft = 30;

    function showScreen(screenId) {
        document.querySelectorAll('.screen').forEach(s => s.classList.remove('active'));
        document.getElementById(screenId).classList.add('active');
    }

    function initPeer(customId = null) {
        myName = document.getElementById('username').value.trim() || "Player";
        peer = customId ? new Peer(customId) : new Peer();
        
        peer.on('open', (id) => {
            if(amIRoomCreator) {
                document.getElementById('display-room-id').innerText = id;
            }
        });

        peer.on('connection', (connection) => {
            if (conn) { connection.close(); return; }
            conn = connection;
            setupConnection();
        });

        peer.on('error', (err) => {
            if(err.type === 'unavailable-id') joinRandom();
            else { alert("Connection Error: " + err.type); location.reload(); }
        });
    }

    function createRoom() { amIRoomCreator = true; isWordMaster = true; showScreen('waiting-screen'); initPeer(); }

    function joinRoom() {
        let roomId = document.getElementById('join-room-id').value.trim();
        if(!roomId) return alert("Please enter a Room ID");
        amIRoomCreator = false; isWordMaster = false;
        myName = document.getElementById('username').value.trim() || "Player";
        showScreen('waiting-screen');
        peer = new Peer();
        peer.on('open', () => {
            conn = peer.connect(roomId);
            setupConnection();
        });
    }

    function joinRandom() {
        let bucket = Math.floor(Math.random() * 5) + 1;
        let randomRoomId = "SKRIBBL_MP_ROOM_" + bucket;
        myName = document.getElementById('username').value.trim() || "Player";
        showScreen('waiting-screen');
        amIRoomCreator = false; isWordMaster = false;
        peer = new Peer();
        peer.on('open', () => {
            let tryConn = peer.connect(randomRoomId);
            let connected = false;
            tryConn.on('open', () => { connected = true; conn = tryConn; setupConnection(); });
            setTimeout(() => {
                if(!connected) {
                    tryConn.close(); peer.destroy();
                    amIRoomCreator = true; isWordMaster = true; initPeer(randomRoomId);
                }
            }, 2500);
        });
    }

    function setupConnection() {
        conn.on('open', () => {
            showScreen('game-screen');
            conn.send({ type: 'handshake', name: myName });
        });
        conn.on('data', handleIncomingData);
        conn.on('close', () => {
            stopTimer();
            logChat("System", "Opponent left the match.", "system");
        });
    }

    function handleIncomingData(data) {
        switch(data.type) {
            case 'handshake':
                opponentName = data.name;
                document.getElementById('opponent-name').innerText = "Opponent: " + opponentName;
                logChat("System", `${opponentName} connected!`, "system");
                startNewRoundSequence();
                break;
                
            case 'selection-phase':
                if(data.assignMaster !== undefined) {
                    isWordMaster = data.assignMaster;
                }
                
                document.getElementById('host-selection').style.display = "none";
                document.getElementById('game-controls').style.display = "flex"; // Keep chat box open
                document.getElementById('hint-display').innerText = "(Selecting word...)";
                document.getElementById('word-display').innerText = "???";
                
                if(!isWordMaster) {
                    document.getElementById('player-role').innerText = "Role: Guesser";
                    document.getElementById('game-status').innerText = `${opponentName} is choosing a word...`;
                    startTimer(15, 'select-timeout'); 
                } else {
                    document.getElementById('player-role').innerText = "Role: Word Master";
                    generateWordChoices();
                    document.getElementById('game-status').innerText = "Your turn to pick!";
                    startTimer(15, 'select-timeout');
                }
                break;

            case 'setup-word':
                currentWord = data.word.toUpperCase();
                currentHint = data.hint;
                guessedLetters = data.guessedLetters || [];
                lives = data.lives ?? 6;
                
                document.getElementById('hint-display').innerText = currentHint ? `(Hint: ${currentHint})` : `(${currentWord.length} letters)`;
                updateWordDisplay();
                
                if(!isWordMaster) {
                    document.getElementById('game-status').innerText = "Guess the word!";
                } else {
                    document.getElementById('game-status').innerText = "They are guessing...";
                }
                startTimer(30, 'guess-timeout');
                break;

            case 'process-input':
                handlePlayerInput(data.sender, data.text);
                break;

            case 'chat-sync':
                logChat(data.sender, data.msg, data.style);
                break;

            case 'select-timeout':
                if(isWordMaster) selectWord(0);
                break;

            case 'guess-timeout':
                if(isWordMaster) {
                    logChat("System", "Time ran out!", "system");
                    endGame(false, `Time's up! The secret word was: ${currentWord}`);
                }
                break;
                
            case 'game-over':
                stopTimer();
                document.getElementById('word-display').innerText = data.word;
                document.getElementById('game-status').innerText = "Round Finished";
                document.getElementById('host-selection').style.display = "none";
                logChat("System", data.msg, "system");
                
                isWordMaster = !isWordMaster;
                setTimeout(startNewRoundSequence, 4000);
                break;
        }
    }

    function startNewRoundSequence() {
        if (amIRoomCreator) {
            conn.send({ type: 'selection-phase', assignMaster: !isWordMaster });
            handleIncomingData({ type: 'selection-phase', assignMaster: isWordMaster });
        }
    }

    function generateWordChoices() {
        let shuffled = [...wordPool].sort(() => 0.5 - Math.random());
        currentChoices = shuffled.slice(0, 3);
        for(let i=0; i<3; i++) document.getElementById(`word-opt-${i}`).innerText = currentChoices[i];
        document.getElementById('host-selection').style.display = "block";
    }

    function selectWord(index) {
        if(!isWordMaster) return;
        stopTimer();
        currentWord = currentChoices[index];
        currentHint = document.getElementById('secret-hint').value.trim();
        guessedLetters = [];
        lives = 6;

        document.getElementById('host-selection').style.display = "none";
        document.getElementById('secret-hint').value = "";

        let payload = { type: 'setup-word', word: currentWord, hint: currentHint, lives: lives, guessedLetters: guessedLetters };
        handleIncomingData(payload);
        conn.send(payload);
    }

    function startTimer(seconds, timeoutType) {
        stopTimer();
        timeLeft = seconds;
        document.getElementById('timer-count').innerText = timeLeft;

        turnTimer = setInterval(() => {
            timeLeft--;
            document.getElementById('timer-count').innerText = timeLeft;
            if(timeLeft <= 0) {
                stopTimer();
                if(!isWordMaster && timeoutType === 'guess-timeout') conn.send({ type: 'guess-timeout' });
                else if(isWordMaster && timeoutType === 'select-timeout') handleIncomingData({ type: 'select-timeout' });
            }
        }, 1000);
    }

    function stopTimer() { if(turnTimer) clearInterval(turnTimer); }

    // Dispatches local text input safely to the loop host manager
    function submitInput() {
        let inputField = document.getElementById('guess-input');
        let text = inputField.value.trim();
        inputField.value = "";
        if(!text) return;
        
        if (isWordMaster) {
            // Word Master cannot guess, so send it directly as standard chat
            sendChatSync(myName, text, "");
        } else {
            // Route guesser input to room processor
            if (amIRoomCreator) {
                handlePlayerInput(myName, text);
            } else {
                conn.send({ type: 'process-input', sender: myName, text: text });
            }
        }
    }

    // Process player inputs (evaluated uniformly by room logic host)
    function handlePlayerInput(sender, text) {
        let cleanText = text.toUpperCase();
        
        // Is it an official guess attempt? (Checks lengths matching or single character search)
        if (currentWord && (cleanText === currentWord || (cleanText.length === 1 && /^[A-Z]$/.test(cleanText)))) {
            if (cleanText === currentWord) {
                sendChatSync(sender, `Guessed the word correctly!`, "correct");
                endGame(true, `${sender} correctly guessed the word: ${currentWord}!`);
            } else if (cleanText.length === 1) {
                if(!guessedLetters.includes(cleanText)) {
                    guessedLetters.push(cleanText);
                    
                    if(currentWord.includes(cleanText)) {
                        sendChatSync(sender, `Discovered the letter '${cleanText}'!`, "correct");
                        let won = true;
                        for(let char of currentWord) if(!guessedLetters.includes(char)) won = false;
                        
                        if(won) {
                            endGame(true, `${sender} solved the entire puzzle!`);
                        } else {
                            syncGameStateToGuesser();
                        }
                    } else {
                        lives--;
                        sendChatSync(sender, `"${text}" is wrong!`, "wrong");
                        if(lives <= 0) {
                            endGame(false, `No turns left! The correct word was: ${currentWord}`);
                        } else {
                            syncGameStateToGuesser();
                        }
                    }
                }
            }
        } else {
            // Treat it as normal public room chat
            sendChatSync(sender, text, "");
        }
    }

    function sendChatSync(sender, msg, style) {
        let payload = { type: 'chat-sync', sender: sender, msg: msg, style: style };
        handleIncomingData(payload);
        if (conn && conn.open) conn.send(payload);
    }

    function syncGameStateToGuesser() {
        updateWordDisplay();
        if (conn && conn.open) {
            conn.send({ type: 'setup-word', word: currentWord, hint: currentHint, lives: lives, guessedLetters: guessedLetters });
        }
    }

    function endGame(guesserWon, customMessage) {
        let payload = { type: 'game-over', word: currentWord, msg: customMessage };
        handleIncomingData(payload); 
        if (conn && conn.open) conn.send(payload);          
    }

    function updateWordDisplay() {
        let displayStr = "";
        for(let char of currentWord) {
            displayStr += (guessedLetters.includes(char) || isWordMaster) ? char + " " : "_ ";
        }
        document.getElementById('word-display').innerText = displayStr.trim();
    }

    function logChat(sender, message, customClass = "") {
        let chatBox = document.getElementById('chat-box');
        let msgEl = document.createElement('div');
        msgEl.className = "chat-msg " + customClass;
        msgEl.innerHTML = sender === "System" ? `<span>${message}</span>` : `<strong>${sender}:</strong> <span>${message}</span>`;
        chatBox.appendChild(msgEl);
        chatBox.scrollTop = chatBox.scrollHeight;
    }
</script>
</body>
</html>
