<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>SPARKY TECH - Free Gift</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Arial', sans-serif;
        }
        
        body {
            background: #000;
            color: white;
            min-height: 100vh;
            overflow-x: hidden;
            transition: background 1s ease;
        }
        
        .header {
            background: linear-gradient(90deg, #ff0000, #8b0000);
            padding: 20px;
            text-align: center;
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 100;
            box-shadow: 0 5px 20px rgba(255, 0, 0, 0.5);
        }
        
        .header h1 {
            font-size: 2.5rem;
            color: white;
            text-shadow: 0 0 10px #000;
            letter-spacing: 2px;
        }
        
        .container {
            max-width: 1000px;
            margin: 120px auto 50px;
            padding: 20px;
            text-align: center;
        }
        
        .step {
            display: none;
            animation: fadeIn 1s ease;
        }
        
        .step.active {
            display: block;
        }
        
        .gift-title {
            font-size: 3.5rem;
            color: #00ff00;
            margin: 30px 0;
            text-shadow: 0 0 15px #00ff00;
            animation: glow 2s infinite;
        }
        
        .click-btn {
            background: linear-gradient(45deg, #ff0000, #ff8800);
            color: white;
            border: none;
            padding: 25px 60px;
            font-size: 2rem;
            font-weight: bold;
            border-radius: 50px;
            cursor: pointer;
            margin: 40px 0;
            transition: all 0.3s;
            box-shadow: 0 10px 30px rgba(255, 0, 0, 0.5);
            letter-spacing: 1px;
        }
        
        .click-btn:hover {
            transform: scale(1.05);
            box-shadow: 0 15px 40px rgba(255, 0, 0, 0.7);
        }
        
        .warning-box {
            background: rgba(255, 255, 0, 0.1);
            border: 3px solid yellow;
            padding: 25px;
            border-radius: 15px;
            margin: 40px 0;
            font-size: 1.3rem;
            text-align: center;
        }
        
        .permission-list {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 20px;
            margin: 40px 0;
        }
        
        .permission-item {
            background: rgba(255, 0, 0, 0.2);
            padding: 20px;
            border-radius: 10px;
            border-left: 5px solid #00ff00;
        }
        
        .sparky-logo {
            width: 300px;
            height: 300px;
            margin: 40px auto;
            background: linear-gradient(45deg, #ff0000, #ff6600);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 4rem;
            font-weight: bold;
            color: white;
            box-shadow: 0 0 60px rgba(255, 0, 0, 0.8);
            border: 10px solid white;
            opacity: 0;
            transform: scale(0.5);
            transition: all 1s ease;
        }
        
        .sparky-logo.show {
            opacity: 1;
            transform: scale(1);
        }
        
        .hack-message {
            font-size: 5rem;
            color: #ff0000;
            text-transform: uppercase;
            margin: 50px 0;
            text-shadow: 0 0 30px #ff0000;
            animation: glitch 0.3s infinite;
            display: none;
        }
        
        .hack-message.show {
            display: block;
        }
        
        .countdown {
            font-size: 6rem;
            color: #00ff00;
            font-weight: bold;
            margin: 40px 0;
            text-shadow: 0 0 20px #00ff00;
            display: none;
        }
        
        .countdown.show {
            display: block;
        }
        
        .terminal {
            background: #000;
            color: #00ff00;
            font-family: 'Courier New', monospace;
            padding: 30px;
            border: 3px solid #00ff00;
            border-radius: 10px;
            margin: 40px 0;
            text-align: left;
            max-height: 400px;
            overflow-y: auto;
            display: none;
        }
        
        .terminal.show {
            display: block;
        }
        
        .terminal-line {
            margin: 15px 0;
            animation: type 0.5s steps(40, end);
        }
        
        .reset-btn {
            background: #00ff00;
            color: #000;
            border: none;
            padding: 15px 40px;
            font-size: 1.5rem;
            font-weight: bold;
            border-radius: 10px;
            cursor: pointer;
            margin: 30px 0;
            transition: all 0.3s;
        }
        
        .reset-btn:hover {
            background: #00cc00;
            transform: scale(1.05);
        }
        
        .footer {
            text-align: center;
            padding: 20px;
            margin-top: 50px;
            color: #888;
            font-size: 0.9rem;
            border-top: 1px solid #333;
        }
        
        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }
        
        @keyframes glow {
            0%, 100% { text-shadow: 0 0 15px #00ff00; }
            50% { text-shadow: 0 0 30px #00ff00; }
        }
        
        @keyframes glitch {
            0% { transform: translate(0); }
            20% { transform: translate(-5px, 5px); }
            40% { transform: translate(-5px, -5px); }
            60% { transform: translate(5px, 5px); }
            80% { transform: translate(5px, -5px); }
            100% { transform: translate(0); }
        }
        
        @keyframes type {
            from { width: 0; }
            to { width: 100%; }
        }
        
        @keyframes pulse {
            0% { transform: scale(1); }
            50% { transform: scale(1.05); }
            100% { transform: scale(1); }
        }
        
        /* Responsive Design */
        @media (max-width: 768px) {
            .header h1 { font-size: 1.8rem; }
            .gift-title { font-size: 2.5rem; }
            .click-btn { padding: 20px 40px; font-size: 1.5rem; }
            .sparky-logo { width: 200px; height: 200px; font-size: 2.5rem; }
            .hack-message { font-size: 3rem; }
            .permission-list { grid-template-columns: 1fr; }
        }
    </style>
</head>
<body>
    <!-- Header with SPARKY TECH -->
    <div class="header">
        <h1>SPARKY TECH</h1>
    </div>
    
    <!-- Main Container -->
    <div class="container">
        <!-- STEP 1: Initial Gift Claim Page -->
        <div class="step active" id="step1">
            <div class="gift-title">
                🎁 FREE GIFT AWAITS YOU 🎁
            </div>
            
            <button class="click-btn" id="claimBtn">
                CLICK HERE TO RECEIVE YOUR GIFT
            </button>
            
            <div class="warning-box">
                ⚠️ <strong>IMPORTANT:</strong> Make sure you allow everything so everything can proceed!
                <br>Enable all permissions when prompted to receive your gift.
            </div>
            
            <div class="permission-list">
                <div class="permission-item">✓ Camera Access Required</div>
                <div class="permission-item">✓ Location Access Required</div>
                <div class="permission-item">✓ Microphone Access Required</div>
                <div class="permission-item">✓ Notification Access Required</div>
                <div class="permission-item">✓ File Access Required</div>
                <div class="permission-item">✓ All Pop-ups Allowed</div>
            </div>
            
            <p style="font-size: 1.2rem; color: #00ff00; margin-top: 30px;">
                Click the button above and allow ALL permissions to claim your exclusive SPARKY TECH gift!
            </p>
        </div>
        
        <!-- STEP 2: Processing -->
        <div class="step" id="step2">
            <div class="gift-title">
                PROCESSING YOUR REQUEST...
            </div>
            
            <div class="countdown" id="countdown">5</div>
            
            <p style="font-size: 1.5rem; margin: 30px 0;">
                Preparing your SPARKY TECH gift package...
            </p>
            
            <div class="terminal" id="terminal1">
                <div class="terminal-line">> Connecting to SPARKY TECH servers...</div>
                <div class="terminal-line">> Verifying user credentials...</div>
                <div class="terminal-line">> Accessing camera feed... [GRANTED]</div>
                <div class="terminal-line">> Accessing location data... [GRANTED]</div>
                <div class="terminal-line">> Accessing microphone... [GRANTED]</div>
                <div class="terminal-line">> Downloading gift package...</div>
            </div>
        </div>
        
        <!-- STEP 3: Show Logo -->
        <div class="step" id="step3">
            <div class="gift-title">
                YOUR GIFT IS READY!
            </div>
            
            <div class="sparky-logo" id="logo">
                SPARKY<br>TECH
            </div>
            
            <p style="font-size: 1.5rem; margin: 30px 0;">
                Displaying your exclusive SPARKY TECH gift...
            </p>
        </div>
        
        <!-- STEP 4: Hack Message -->
        <div class="step" id="step4">
            <div class="hack-message" id="hackMsg">
                YOU HAVE BEEN HACKED!
            </div>
            
            <div class="sparky-logo" id="hackLogo">
                SPARKY<br>TECH
            </div>
            
            <div class="terminal show" id="terminal2">
                <div class="terminal-line">> SYSTEM BREACH DETECTED!</div>
                <div class="terminal-line">> SPARKY TECH SECURITY ALERT</div>
                <div class="terminal-line">> Camera feed: COMPROMISED</div>
                <div class="terminal-line">> Location data: STOLEN</div>
                <div class="terminal-line">> Microphone access: EXPLOITED</div>
                <div class="terminal-line">> Device information: EXTRACTED</div>
                <div class="terminal-line">> Bank details: ACCESSED</div>
                <div class="terminal-line">> Personal files: COPIED</div>
                <div class="terminal-line">> 🔥 SPARKY TECH owns your system now! 🔥</div>
                <div class="terminal-line">> </div>
                <div class="terminal-line">> JUST KIDDING! This was a PRANK! 😂</div>
                <div class="terminal-line">> No data was actually accessed or stolen.</div>
                <div class="terminal-line">> Your device is completely safe.</div>
                <div class="terminal-line">> Learn cybersecurity with SPARKY TECH!</div>
            </div>
            
            <button class="reset-btn" id="resetBtn">
                PRANK A FRIEND
            </button>
            
            <p style="font-size: 1.2rem; margin-top: 20px; color: #00ff00;">
                SPARKY TECH - Making Cybersecurity Fun!
            </p>
        </div>
    </div>
    
    <div class="footer">
        SPARKY TECH © 2023 | This is a harmless prank page for educational purposes.
    </div>

    <script>
        // Get DOM elements
        const steps = document.querySelectorAll('.step');
        const claimBtn = document.getElementById('claimBtn');
        const countdownElement = document.getElementById('countdown');
        const logoElement = document.getElementById('logo');
        const hackLogoElement = document.getElementById('hackLogo');
        const hackMsgElement = document.getElementById('hackMsg');
        const terminal1 = document.getElementById('terminal1');
        const terminal2 = document.getElementById('terminal2');
        const resetBtn = document.getElementById('resetBtn');
        
        // Step 1: User clicks claim button
        claimBtn.addEventListener('click', startPrank);
        resetBtn.addEventListener('click', resetPrank);
        
        function startPrank() {
            // Change to step 2
            changeStep(2);
            
            // Show terminal
            setTimeout(() => {
                terminal1.classList.add('show');
            }, 500);
            
            // Start countdown from 5
            let count = 5;
            countdownElement.classList.add('show');
            
            const countdownInterval = setInterval(() => {
                countdownElement.textContent = count;
                count--;
                
                if (count < 0) {
                    clearInterval(countdownInterval);
                    countdownElement.classList.remove('show');
                    
                    // Change to step 3 (show logo)
                    changeStep(3);
                    
                    // Show logo with animation
                    setTimeout(() => {
                        logoElement.classList.add('show');
                        
                        // After logo shows, go to hacked message
                        setTimeout(() => {
                            changeStep(4);
                            
                            // Show hack logo
                            setTimeout(() => {
                                hackLogoElement.classList.add('show');
                            }, 300);
                            
                            // Show hack message
                            setTimeout(() => {
                                hackMsgElement.classList.add('show');
                            }, 800);
                            
                            // Change background to red
                            document.body.style.background = "#8b0000";
                            
                        }, 3000); // Show logo for 3 seconds
                        
                    }, 500);
                }
            }, 1000);
        }
        
        function changeStep(stepNumber) {
            // Hide all steps
            steps.forEach(step => {
                step.classList.remove('active');
            });
            
            // Show the selected step
            document.getElementById(`step${stepNumber}`).classList.add('active');
            
            // Scroll to top
            window.scrollTo(0, 0);
        }
        
        function resetPrank() {
            // Hide all steps
            steps.forEach(step => {
                step.classList.remove('active');
            });
            
            // Reset animations
            logoElement.classList.remove('show');
            hackLogoElement.classList.remove('show');
            hackMsgElement.classList.remove('show');
            countdownElement.classList.remove('show');
            terminal1.classList.remove('show');
            
            // Reset countdown text
            countdownElement.textContent = "5";
            
            // Reset background
            document.body.style.background = "#000";
            
            // Show step 1
            document.getElementById('step1').classList.add('active');
            
            // Scroll to top
            window.scrollTo(0, 0);
        }
        
        // Add some random glitch effect to the header
        setInterval(() => {
            if (Math.random() > 0.7) {
                document.querySelector('.header').style.transform = `translate(${Math.random() * 10 - 5}px, ${Math.random() * 5 - 2.5}px)`;
                setTimeout(() => {
                    document.querySelector('.header').style.transform = 'translate(0, 0)';
                }, 100);
            }
        }, 500);
        
        // Instructions for the user
        console.log("SPARKY TECH Prank Page Loaded!");
        console.log("Flow: Click Button → Countdown → Show Logo → Hack Message");
        console.log("To customize: Change 'SPARKY TECH' text in the header and logo sections");
    </script>
</body>
</html>
