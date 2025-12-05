<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Inside Out: The Journey Home</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        /* CSS Variables for Therapeutic Design System - ENHANCED */
        :root {
            /* Vibrant therapeutic colors - ENHANCED */
            --background: 210 40% 98%;
            --foreground: 215 25% 27%;

            --card: 0 0% 100%;
            --card-foreground: 215 25% 27%;

            --popover: 0 0% 100%;
            --popover-foreground: 215 25% 27%;

            /* Vibrant gradient for primary actions - ENHANCED */
            --primary: 187 71% 45%;
            --primary-foreground: 0 0% 100%;

            /* Soft blue-grey for secondary - ENHANCED */
            --secondary: 210 25% 92%;
            --secondary-foreground: 215 25% 27%;

            --muted: 210 30% 95%;
            --muted-foreground: 215 16% 47%;

            /* Warm coral for hope/encouragement - ENHANCED */
            --accent: 16 85% 70%;
            --accent-foreground: 0 0% 100%;

            /* Hope points - vibrant orange - ENHANCED */
            --hope: 25 95% 53%;
            --hope-foreground: 0 0% 100%;

            /* Insight points - vibrant purple - ENHANCED */
            --insight: 270 70% 60%;
            --insight-foreground: 0 0% 100%;

            /* Success - vibrant green - ENHANCED */
            --success: 142 76% 36%;
            --success-foreground: 0 0% 100%;

            --destructive: 0 84% 60%;
            --destructive-foreground: 0 0% 100%;

            --border: 210 30% 88%;
            --input: 210 30% 88%;
            --ring: 187 71% 45%;

            --radius: 0.75rem;

            /* Convert HSL to hex for compatibility - ENHANCED */
            --bg-hex: #f8fafc;
            --primary-hex: #0ea5e9;
            --accent-hex: #fb923c;
            --success-hex: #16a34a;
            --hope-hex: #ea580c;
            --insight-hex: #9333ea;
            --vibrant-blue: #3b82f6;
            --vibrant-purple: #8b5cf6;
            --vibrant-pink: #ec4899;
            --vibrant-cyan: #06b6d4;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        body {
            background: var(--bg-hex);
            color: hsl(var(--foreground));
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            padding: 20px;
            line-height: 1.6;
            background-image: url('https://images.unsplash.com/photo-1507525428034-b723cf961d3e?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=2070&q=80');
            background-size: cover;
            background-position: center;
            background-attachment: fixed;
        }

        .container {
            width: 100%;
            max-width: 1200px;
            background-color: rgba(255, 255, 255, 0.95);
            border-radius: var(--radius);
            box-shadow: 0 15px 40px rgba(0, 0, 0, 0.25);
            overflow: hidden;
            position: relative;
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.5);
        }

        /* Login Screen Styles - ENHANCED */
        #login-screen {
            padding: 40px;
            text-align: center;
            background: linear-gradient(135deg, 
                rgba(14, 165, 233, 0.9), 
                rgba(59, 130, 246, 0.9), 
                rgba(139, 92, 246, 0.9));
            color: white;
            position: relative;
            overflow: hidden;
        }

        #login-screen::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 100 100" preserveAspectRatio="none"><path d="M0,0 L100,0 L100,100 Z" fill="rgba(255,255,255,0.1)"/></svg>');
            background-size: cover;
        }

        .game-title {
            color: white;
            margin-bottom: 10px;
            font-size: 2.8rem;
            font-weight: 800;
            text-shadow: 0 4px 8px rgba(0,0,0,0.3);
            background: linear-gradient(to right, #ffffff, #e0f2fe);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .game-subtitle {
            color: rgba(255, 255, 255, 0.95);
            margin-bottom: 40px;
            font-size: 1.3rem;
            font-weight: 500;
            text-shadow: 0 2px 4px rgba(0,0,0,0.2);
        }

        .login-form {
            max-width: 500px;
            margin: 0 auto;
            background: rgba(255, 255, 255, 0.95);
            padding: 35px;
            border-radius: var(--radius);
            box-shadow: 0 10px 25px rgba(0, 0, 0, 0.15);
            position: relative;
            z-index: 1;
            color: hsl(var(--foreground));
            border: 1px solid rgba(255, 255, 255, 0.7);
        }

        .form-group {
            margin-bottom: 20px;
            text-align: right;
        }

        .english .form-group {
            text-align: left;
        }

        label {
            display: block;
            margin-bottom: 8px;
            color: hsl(var(--foreground));
            font-weight: 600;
        }

        input, select {
            width: 100%;
            padding: 14px 16px;
            border: 1px solid hsl(var(--border));
            border-radius: var(--radius);
            font-size: 1rem;
            transition: all 0.3s ease;
            background: white;
        }

        input:focus, select:focus {
            outline: none;
            border-color: hsl(var(--primary));
            box-shadow: 0 0 0 3px hsl(var(--primary) / 0.3);
        }

        .checkbox-group {
            display: flex;
            align-items: center;
            margin-bottom: 20px;
            flex-direction: row-reverse;
            justify-content: flex-end;
        }

        .english .checkbox-group {
            flex-direction: row;
            justify-content: flex-start;
        }

        .checkbox-group input {
            width: auto;
            margin-left: 10px;
            margin-right: 0;
        }

        .english .checkbox-group input {
            margin-left: 0;
            margin-right: 10px;
        }

        .language-toggle {
            display: flex;
            justify-content: center;
            margin-bottom: 30px;
        }

        .language-btn {
            padding: 10px 24px;
            background: none;
            border: 1px solid white;
            color: white;
            cursor: pointer;
            transition: all 0.3s ease;
            font-weight: 500;
        }

        .language-btn:first-child {
            border-radius: var(--radius) 0 0 var(--radius);
        }

        .language-btn:last-child {
            border-radius: 0 var(--radius) var(--radius) 0;
        }

        .language-btn.active {
            background-color: white;
            color: hsl(var(--primary));
        }

        .btn {
            padding: 14px 32px;
            background: linear-gradient(135deg, hsl(var(--primary)), hsl(201, 96%, 32%));
            color: white;
            border: none;
            border-radius: var(--radius);
            font-size: 1rem;
            cursor: pointer;
            transition: all 0.3s ease;
            display: inline-block;
            font-weight: 600;
            box-shadow: 0 6px 12px rgba(0, 0, 0, 0.15);
        }

        .btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 8px 16px rgba(0, 0, 0, 0.2);
        }

        .btn-secondary {
            background: linear-gradient(135deg, hsl(var(--secondary)), hsl(210, 20%, 80%));
            color: hsl(var(--secondary-foreground));
        }

        .btn-accent {
            background: linear-gradient(135deg, hsl(var(--accent)), hsl(16, 75%, 50%));
            color: white;
        }

        .admin-btn {
            position: absolute;
            top: 20px;
            right: 20px;
            background: rgba(255, 255, 255, 0.2);
            color: white;
            border: 1px solid rgba(255, 255, 255, 0.5);
            padding: 10px 18px;
            border-radius: var(--radius);
            cursor: pointer;
            transition: all 0.3s ease;
            z-index: 2;
            font-weight: 500;
        }

        .english .admin-btn {
            right: auto;
            left: 20px;
        }

        .admin-btn:hover {
            background: rgba(255, 255, 255, 0.3);
        }

        /* Admin Panel Styles - ENHANCED */
        #admin-panel {
            display: none;
            padding: 40px;
            background: linear-gradient(135deg, rgba(30, 41, 59, 0.95), rgba(51, 65, 85, 0.95));
            color: white;
            min-height: 100vh;
        }

        .admin-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 30px;
        }

        .admin-title {
            font-size: 2.2rem;
            font-weight: 800;
        }

        .admin-login {
            max-width: 400px;
            margin: 50px auto;
            background: rgba(255, 255, 255, 0.1);
            padding: 35px;
            border-radius: var(--radius);
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.2);
        }

        .admin-stats {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            gap: 20px;
            margin-bottom: 30px;
        }

        .stat-card {
            background: rgba(255, 255, 255, 0.1);
            padding: 25px;
            border-radius: var(--radius);
            text-align: center;
            backdrop-filter: blur(5px);
            border: 1px solid rgba(255, 255, 255, 0.1);
            transition: all 0.3s ease;
        }

        .stat-card:hover {
            transform: translateY(-5px);
            background: rgba(255, 255, 255, 0.15);
        }

        .stat-value {
            font-size: 2.2rem;
            font-weight: 800;
            margin: 10px 0;
        }

        .player-list {
            background: rgba(255, 255, 255, 0.1);
            border-radius: var(--radius);
            padding: 25px;
            backdrop-filter: blur(5px);
            border: 1px solid rgba(255, 255, 255, 0.1);
        }

        .player-item {
            display: flex;
            justify-content: space-between;
            padding: 18px;
            border-bottom: 1px solid rgba(255, 255, 255, 0.1);
            transition: all 0.3s ease;
        }

        .player-item:hover {
            background: rgba(255, 255, 255, 0.05);
        }

        .player-details {
            flex: 1;
        }

        .player-name {
            font-weight: 700;
            margin-bottom: 5px;
        }

        .player-progress {
            font-size: 0.9rem;
            color: rgba(255, 255, 255, 0.7);
        }

        .player-stats {
            display: flex;
            gap: 15px;
        }

        .stat {
            text-align: center;
        }

        .stat-value {
            font-size: 1.3rem;
            font-weight: 700;
        }

        .stat-label {
            font-size: 0.8rem;
            color: rgba(255, 255, 255, 0.7);
        }

        /* Chapter Map Styles - ENHANCED */
        #chapter-map {
            display: none;
            padding: 20px;
            position: relative;
            background: linear-gradient(135deg, rgba(14, 165, 233, 0.9), rgba(59, 130, 246, 0.9));
            min-height: 100vh;
        }

        .header-bar {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 18px 25px;
            background: white;
            color: hsl(var(--foreground));
            border-radius: var(--radius);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
            margin-bottom: 25px;
            border: 1px solid rgba(255, 255, 255, 0.7);
        }

        .points-display {
            display: flex;
            gap: 20px;
        }

        .point-type {
            display: flex;
            align-items: center;
            gap: 10px;
            background: hsl(var(--muted));
            padding: 10px 18px;
            border-radius: 25px;
            font-weight: 600;
            box-shadow: 0 3px 8px rgba(0, 0, 0, 0.1);
        }

        .hope-points {
            background: linear-gradient(135deg, hsl(var(--hope)), hsl(25, 85%, 45%));
            color: white;
        }

        .insight-points {
            background: linear-gradient(135deg, hsl(var(--insight)), hsl(270, 60%, 50%));
            color: white;
        }

        .point-icon {
            font-size: 1.3rem;
        }

        .home-btn {
            background: none;
            border: none;
            color: hsl(var(--primary));
            cursor: pointer;
            font-size: 1.3rem;
            transition: all 0.3s ease;
            padding: 10px;
            border-radius: 50%;
            font-weight: 600;
        }

        .home-btn:hover {
            background: hsl(var(--primary) / 0.1);
            transform: scale(1.1);
        }

        .map-container {
            padding: 25px;
            overflow: auto;
        }

        .welcome-message {
            margin-bottom: 25px;
            text-align: center;
            padding: 25px;
            background: rgba(255, 255, 255, 0.95);
            border-radius: var(--radius);
            box-shadow: 0 8px 20px rgba(0, 0, 0, 0.1);
            backdrop-filter: blur(5px);
            border: 1px solid rgba(255, 255, 255, 0.7);
        }

        .chapters-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(270px, 1fr));
            gap: 25px;
            margin-top: 25px;
        }

        .chapter-card {
            background: white;
            border-radius: var(--radius);
            box-shadow: 0 8px 20px rgba(0, 0, 0, 0.1);
            padding: 0;
            text-align: center;
            transition: all 0.3s ease;
            cursor: pointer;
            position: relative;
            border: 2px solid transparent;
            overflow: hidden;
        }

        .chapter-card:hover {
            transform: translateY(-8px);
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.2);
            border-color: hsl(var(--primary) / 0.4);
        }

        .chapter-card.locked {
            opacity: 0.6;
            cursor: not-allowed;
        }

        .chapter-card.completed {
            border-color: hsl(var(--success));
        }

        .chapter-number {
            font-size: 1.1rem;
            font-weight: 800;
            color: white;
            background: linear-gradient(135deg, hsl(var(--primary)), hsl(201, 96%, 32%));
            padding: 12px;
        }

        .chapter-title {
            font-size: 1.2rem;
            margin: 18px 0 8px;
            color: hsl(var(--foreground));
            font-weight: 700;
            padding: 0 18px;
        }

        .chapter-thumbnail {
            width: 100%;
            height: 140px;
            background-size: cover;
            background-position: center;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 2.8rem;
            color: white;
        }

        .chapter-description {
            padding: 0 18px 18px;
            color: hsl(var(--muted-foreground));
            font-size: 0.95rem;
        }

        .chapter-symptom {
            background: hsl(var(--muted));
            padding: 6px 12px;
            border-radius: 18px;
            font-size: 0.85rem;
            color: hsl(var(--muted-foreground));
            display: inline-block;
            margin: 12px 0;
            font-weight: 500;
        }

        .lock-icon, .check-icon {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            font-size: 2.2rem;
            color: hsl(var(--muted-foreground));
            background: white;
            border-radius: 50%;
            width: 70px;
            height: 70px;
            display: flex;
            align-items: center;
            justify-content: center;
            box-shadow: 0 8px 20px rgba(0, 0, 0, 0.15);
        }

        .check-icon {
            color: hsl(var(--success));
        }

        /* Game Screen Styles - ENHANCED */
        #game-screen {
            display: none;
            padding: 25px;
            background: linear-gradient(135deg, rgba(14, 165, 233, 0.9), rgba(59, 130, 246, 0.9));
            min-height: 100vh;
        }

        .game-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 25px;
            padding: 18px;
            background: white;
            color: hsl(var(--foreground));
            border-radius: var(--radius);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
            border: 1px solid rgba(255, 255, 255, 0.7);
        }

        .chapter-info {
            text-align: center;
        }

        .chapter-name {
            font-size: 1.6rem;
            margin-bottom: 8px;
            color: hsl(var(--primary));
            font-weight: 700;
        }

        .chapter-symptom-game {
            font-size: 1.1rem;
            color: hsl(var(--muted-foreground));
            font-weight: 500;
        }

        .game-container {
            background-color: white;
            border-radius: var(--radius);
            padding: 25px;
            box-shadow: 0 8px 20px rgba(0, 0, 0, 0.1);
            min-height: 450px;
            border: 1px solid rgba(255, 255, 255, 0.7);
        }

        .game-scene {
            margin-bottom: 25px;
            text-align: center;
        }

        .scene-visual {
            width: 100%;
            min-height: 320px;
            border-radius: var(--radius);
            margin-bottom: 18px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.6rem;
            color: hsl(var(--foreground));
            padding: 25px;
            position: relative;
            overflow: hidden;
            background-size: cover;
            background-position: center;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
        }

        .game-instructions {
            margin-bottom: 25px;
            line-height: 1.6;
            padding: 18px;
            background: hsl(var(--muted));
            border-radius: var(--radius);
            font-weight: 500;
        }

        .game-mechanics {
            margin-bottom: 25px;
        }

        .interactive-options {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(160px, 1fr));
            gap: 18px;
            margin-bottom: 25px;
        }

        .interactive-option {
            padding: 18px;
            background: hsl(var(--muted));
            border-radius: var(--radius);
            text-align: center;
            cursor: pointer;
            transition: all 0.3s ease;
            border: 2px solid transparent;
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 12px;
            font-weight: 500;
        }

        .interactive-option:hover {
            background: hsl(var(--primary) / 0.1);
            transform: translateY(-5px);
            border-color: hsl(var(--primary) / 0.4);
            box-shadow: 0 5px 12px rgba(0, 0, 0, 0.1);
        }

        .interactive-option i {
            font-size: 1.6rem;
            color: hsl(var(--primary));
        }

        .game-feedback {
            padding: 18px;
            background: hsl(var(--muted));
            border-radius: var(--radius);
            margin-bottom: 25px;
            text-align: center;
            display: none;
            font-weight: 500;
        }

        .game-controls {
            display: flex;
            justify-content: space-between;
        }

        .inner-guide {
            position: fixed;
            bottom: 25px;
            right: 25px;
            max-width: 320px;
            padding: 18px;
            background: linear-gradient(135deg, hsl(var(--primary)), hsl(201, 96%, 32%));
            color: white;
            border-radius: var(--radius);
            box-shadow: 0 8px 20px rgba(0, 0, 0, 0.25);
            display: none;
            z-index: 100;
            border: 1px solid rgba(255, 255, 255, 0.3);
        }

        .english .inner-guide {
            right: auto;
            left: 25px;
        }

        .inner-guide-text {
            margin-bottom: 12px;
            font-weight: 500;
        }

        .close-guide {
            background: none;
            border: none;
            color: white;
            cursor: pointer;
            float: left;
        }

        .english .close-guide {
            float: right;
        }

        /* Mini-game specific styles - ENHANCED */
        .puzzle-container {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 12px;
            margin-bottom: 25px;
        }

        .puzzle-piece {
            width: 100%;
            height: 90px;
            background: hsl(var(--muted));
            border-radius: var(--radius);
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
            transition: all 0.3s ease;
            border: 2px solid transparent;
            flex-direction: column;
            gap: 8px;
            font-weight: 500;
        }

        .puzzle-piece:hover {
            background: hsl(var(--primary) / 0.1);
            border-color: hsl(var(--primary) / 0.4);
        }

        .memory-game {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 12px;
            margin-bottom: 25px;
        }

        .memory-card {
            width: 100%;
            height: 90px;
            background: linear-gradient(135deg, hsl(var(--primary)), hsl(201, 96%, 32%));
            border-radius: var(--radius);
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
            transition: all 0.3s ease;
            color: white;
            font-size: 1.6rem;
            box-shadow: 0 3px 8px rgba(0, 0, 0, 0.1);
        }

        .memory-card.flipped {
            background: hsl(var(--muted));
            color: hsl(var(--foreground));
        }

        .progress-bar {
            width: 100%;
            height: 22px;
            background: hsl(var(--muted));
            border-radius: 12px;
            margin-bottom: 25px;
            overflow: hidden;
            box-shadow: inset 0 2px 4px rgba(0, 0, 0, 0.1);
        }

        .progress-fill {
            height: 100%;
            background: linear-gradient(to right, hsl(var(--success)), hsl(142, 76%, 36%));
            width: 0%;
            transition: width 0.5s ease;
        }

        /* Arabic language support */
        .arabic {
            direction: rtl;
            text-align: right;
        }

        .english {
            direction: ltr;
            text-align: left;
        }

        /* Responsive Design - ENHANCED */
        @media (max-width: 768px) {
            .chapters-grid {
                grid-template-columns: repeat(auto-fill, minmax(220px, 1fr));
            }
            
            .header-bar {
                flex-direction: column;
                gap: 12px;
            }
            
            .game-controls {
                flex-direction: column;
                gap: 12px;
            }
            
            .btn {
                width: 100%;
            }
            
            .game-title {
                font-size: 2.2rem;
            }
        }

        /* Audio Controls - ENHANCED */
        .audio-controls {
            display: flex;
            align-items: center;
            gap: 12px;
            margin-top: 12px;
            position: absolute;
            bottom: 12px;
            left: 12px;
            background: rgba(255, 255, 255, 0.9);
            padding: 12px;
            border-radius: var(--radius);
            box-shadow: 0 3px 8px rgba(0, 0, 0, 0.1);
            border: 1px solid rgba(255, 255, 255, 0.7);
        }

        .audio-btn {
            background: none;
            border: none;
            color: hsl(var(--primary));
            cursor: pointer;
            font-size: 1.3rem;
            transition: all 0.3s ease;
            padding: 10px;
            border-radius: 50%;
        }

        .audio-btn:hover {
            background: hsl(var(--primary) / 0.1);
            transform: scale(1.1);
        }

        /* Group Mode Styles - ENHANCED */
        .group-members {
            display: flex;
            justify-content: center;
            gap: 18px;
            margin-bottom: 25px;
            flex-wrap: wrap;
        }

        .group-member {
            text-align: center;
            padding: 12px;
            border-radius: var(--radius);
            background: hsl(var(--muted));
            width: 130px;
            box-shadow: 0 3px 8px rgba(0, 0, 0, 0.1);
            transition: all 0.3s ease;
        }

        .group-member:hover {
            transform: translateY(-5px);
            box-shadow: 0 5px 12px rgba(0, 0, 0, 0.15);
        }

        .member-avatar {
            width: 70px;
            height: 70px;
            border-radius: 50%;
            margin: 0 auto 12px;
            background: linear-gradient(135deg, hsl(var(--primary)), hsl(201, 96%, 32%));
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 1.7rem;
            box-shadow: 0 3px 8px rgba(0, 0, 0, 0.1);
        }

        .member-name {
            font-weight: 700;
            margin-bottom: 6px;
        }

        .member-status {
            font-size: 0.85rem;
            color: hsl(var(--muted-foreground));
        }

        /* Improved puzzle game for chapter 6 - ENHANCED */
        .puzzle-grid {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 12px;
            margin-bottom: 25px;
        }

        .puzzle-item {
            padding: 18px;
            background: hsl(var(--muted));
            border-radius: var(--radius);
            text-align: center;
            cursor: pointer;
            transition: all 0.3s ease;
            border: 2px solid transparent;
            font-weight: 500;
        }

        .puzzle-item:hover {
            background: hsl(var(--primary) / 0.1);
            border-color: hsl(var(--primary) / 0.4);
        }

        .puzzle-item.selected {
            background: hsl(var(--primary) / 0.2);
            border-color: hsl(var(--primary));
        }

        .puzzle-item.correct {
            background: hsl(var(--success) / 0.2);
            border-color: hsl(var(--success));
        }

        .puzzle-item.incorrect {
            background: hsl(var(--destructive) / 0.2);
            border-color: hsl(var(--destructive));
        }

        /* AI Companion Styles - UPDATED: Removed circle for individual mode */
        .ai-companion {
            position: fixed;
            bottom: 25px;
            left: 25px;
            width: 90px;
            height: 90px;
            border-radius: 50%;
            background: linear-gradient(135deg, hsl(var(--primary)), hsl(201, 96%, 32%));
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 2.2rem;
            box-shadow: 0 8px 20px rgba(0, 0, 0, 0.25);
            cursor: pointer;
            transition: all 0.3s ease;
            z-index: 99;
            border: 2px solid white;
        }

        .english .ai-companion {
            left: auto;
            right: 25px;
        }

        .ai-companion.group-mode {
            display: flex;
        }

        .ai-companion.individual-mode {
            display: none;
        }

        .companion-message {
            position: absolute;
            bottom: 110px;
            left: 0;
            width: 280px;
            padding: 18px;
            background: white;
            border-radius: var(--radius);
            box-shadow: 0 8px 20px rgba(0, 0, 0, 0.2);
            display: none;
            z-index: 100;
            border: 1px solid rgba(255, 255, 255, 0.7);
        }

        .english .companion-message {
            left: auto;
            right: 0;
        }

        .companion-message::after {
            content: '';
            position: absolute;
            top: 100%;
            left: 25px;
            border-width: 12px;
            border-style: solid;
            border-color: white transparent transparent transparent;
        }

        .english .companion-message::after {
            left: auto;
            right: 25px;
        }

        /* Improved audio controls for chapter 1 - ENHANCED */
        .sound-controls {
            display: flex;
            flex-direction: column;
            gap: 18px;
            margin-top: 25px;
            padding: 18px;
            background: hsl(var(--muted));
            border-radius: var(--radius);
            box-shadow: 0 3px 8px rgba(0, 0, 0, 0.1);
        }

        .sound-item {
            display: flex;
            align-items: center;
            gap: 12px;
            padding: 12px;
            background: white;
            border-radius: var(--radius);
            cursor: pointer;
            transition: all 0.3s ease;
            font-weight: 500;
        }

        .sound-item:hover {
            background: hsl(var(--primary) / 0.1);
        }

        .sound-item.playing {
            background: hsl(var(--primary) / 0.2);
            border: 2px solid hsl(var(--primary));
        }

        .sound-icon {
            font-size: 1.6rem;
            color: hsl(var(--primary));
        }

        /* New game for chapter 6 - Emotion Sorting - ENHANCED */
        .emotion-sorting {
            display: flex;
            flex-direction: column;
            gap: 18px;
            margin-top: 25px;
        }

        .emotion-category {
            padding: 18px;
            background: hsl(var(--muted));
            border-radius: var(--radius);
            min-height: 120px;
            box-shadow: 0 3px 8px rgba(0, 0, 0, 0.1);
        }

        .emotion-item {
            display: inline-block;
            padding: 10px 18px;
            margin: 6px;
            background: white;
            border-radius: 25px;
            cursor: grab;
            transition: all 0.3s ease;
            border: 2px solid transparent;
            font-weight: 500;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
        }

        .emotion-item:hover {
            transform: translateY(-3px);
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.15);
        }

        .emotion-item.correct {
            background: hsl(var(--success) / 0.2);
            border-color: hsl(var(--success));
        }

        .emotion-item.incorrect {
            background: hsl(var(--destructive) / 0.2);
            border-color: hsl(var(--destructive));
        }

        /* Enhanced visual design - ENHANCED */
        .visual-shapes {
            display: flex;
            justify-content: center;
            gap: 18px;
            margin: 25px 0;
            flex-wrap: wrap;
        }

        .visual-shape {
            width: 90px;
            height: 90px;
            border-radius: 18px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.7rem;
            color: white;
            cursor: pointer;
            transition: all 0.3s ease;
            box-shadow: 0 5px 12px rgba(0, 0, 0, 0.15);
        }

        .visual-shape:hover {
            transform: scale(1.1);
        }

        .shape-circle {
            border-radius: 50%;
            background: linear-gradient(135deg, #FF6B6B, #FF8E8E);
        }

        .shape-square {
            background: linear-gradient(135deg, #4ECDC4, #88D9D3);
        }

        .shape-triangle {
            background: linear-gradient(135deg, #FFD166, #FFE099);
            clip-path: polygon(50% 0%, 0% 100%, 100% 100%);
        }

        .shape-star {
            background: linear-gradient(135deg, #6A0572, #9D4EDD);
            clip-path: polygon(50% 0%, 61% 35%, 98% 35%, 68% 57%, 79% 91%, 50% 70%, 21% 91%, 32% 57%, 2% 35%, 39% 35%);
        }

        /* Improved color palette - ENHANCED */
        .color-options {
            display: flex;
            gap: 12px;
            margin: 25px 0;
            flex-wrap: wrap;
            justify-content: center;
        }

        .color-option {
            width: 70px;
            height: 70px;
            border-radius: 12px;
            cursor: pointer;
            transition: all 0.3s ease;
            border: 3px solid transparent;
            box-shadow: 0 3px 8px rgba(0, 0, 0, 0.1);
        }

        .color-option:hover {
            transform: scale(1.1);
        }

        .color-option.selected {
            border-color: hsl(var(--primary));
            box-shadow: 0 0 15px rgba(14, 165, 233, 0.6);
        }

        /* Enhanced performance for chapter 16 */
        .performance-optimized {
            transform: translateZ(0);
            will-change: transform;
        }

        /* Chapter 12 new game - ENHANCED */
        .new-game-container {
            display: flex;
            flex-direction: column;
            gap: 25px;
            margin-top: 25px;
        }

        .game-board {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 12px;
            margin-bottom: 25px;
        }

        .game-tile {
            width: 100%;
            height: 90px;
            background: hsl(var(--muted));
            border-radius: var(--radius);
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
            transition: all 0.3s ease;
            font-size: 1.6rem;
            box-shadow: 0 3px 8px rgba(0, 0, 0, 0.1);
        }

        .game-tile:hover {
            background: hsl(var(--primary) / 0.1);
        }

        .game-tile.selected {
            background: hsl(var(--primary) / 0.2);
            border: 2px solid hsl(var(--primary));
        }

        .game-tile.correct {
            background: hsl(var(--success) / 0.2);
            border: 2px solid hsl(var(--success));
        }

        .game-tile.incorrect {
            background: hsl(var(--destructive) / 0.2);
            border: 2px solid hsl(var(--destructive));
        }

        /* Chapter 4 - Random Questions - ENHANCED */
        .question-container {
            padding: 25px;
            background: hsl(var(--muted));
            border-radius: var(--radius);
            margin-bottom: 25px;
            box-shadow: 0 3px 8px rgba(0, 0, 0, 0.1);
        }

        .question-text {
            font-size: 1.3rem;
            margin-bottom: 18px;
            font-weight: 600;
        }

        .answer-options {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 12px;
        }

        .answer-option {
            padding: 14px;
            background: white;
            border-radius: var(--radius);
            cursor: pointer;
            transition: all 0.3s ease;
            text-align: center;
            font-weight: 500;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
        }

        .answer-option:hover {
            background: hsl(var(--primary) / 0.1);
        }

        .answer-option.selected {
            background: hsl(var(--primary) / 0.2);
            border: 2px solid hsl(var(--primary));
        }

        .answer-option.correct {
            background: hsl(var(--success) / 0.2);
            border: 2px solid hsl(var(--success));
        }

        .answer-option.incorrect {
            background: hsl(var(--destructive) / 0.2);
            border: 2px solid hsl(var(--destructive));
        }

        /* Companion Response Styles - ENHANCED */
        .companion-response {
            padding: 12px 18px;
            background: hsl(var(--success) / 0.2);
            border-radius: var(--radius);
            margin: 12px 0;
            border: 2px solid hsl(var(--success));
            box-shadow: 0 3px 8px rgba(0, 0, 0, 0.1);
        }

        .companion-response .companion-name {
            font-weight: 800;
            color: hsl(var(--success));
            margin-bottom: 8px;
        }

        .companion-answer {
            background: hsl(var(--success) / 0.1);
            padding: 12px;
            border-radius: var(--radius);
            margin: 12px 0;
            border-right: 4px solid hsl(var(--success));
            box-shadow: 0 3px 8px rgba(0, 0, 0, 0.1);
        }

        .english .companion-answer {
            border-right: none;
            border-left: 4px solid hsl(var(--success));
        }

        .companion-turn {
            background: hsl(var(--primary) / 0.1);
            padding: 18px;
            border-radius: var(--radius);
            margin: 18px 0;
            border: 2px solid hsl(var(--primary));
            box-shadow: 0 3px 8px rgba(0, 0, 0, 0.1);
        }

        .companion-turn .companion-name {
            font-weight: 800;
            color: hsl(var(--primary));
            margin-bottom: 12px;
        }

        /* New Maze Game for Chapter 14 - ENHANCED */
        .maze-game {
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 25px;
            margin-top: 25px;
        }

        .maze-container {
            display: grid;
            grid-template-columns: repeat(5, 1fr);
            gap: 6px;
            margin-bottom: 25px;
        }

        .maze-cell {
            width: 70px;
            height: 70px;
            background: hsl(var(--muted));
            border-radius: 10px;
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
            transition: all 0.3s ease;
            font-weight: 800;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
        }

        .maze-cell:hover {
            background: hsl(var(--primary) / 0.1);
        }

        .maze-cell.path {
            background: hsl(var(--success) / 0.2);
            border: 2px solid hsl(var(--success));
        }

        .maze-cell.wall {
            background: hsl(var(--destructive) / 0.2);
            border: 2px solid hsl(var(--destructive));
        }

        .maze-cell.start {
            background: hsl(var(--primary) / 0.2);
            border: 2px solid hsl(var(--primary));
        }

        .maze-cell.end {
            background: hsl(var(--hope) / 0.2);
            border: 2px solid hsl(var(--hope));
        }

        /* New Garden Game for Chapter 16 - ENHANCED */
        .garden-game {
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 25px;
            margin-top: 25px;
        }

        .garden-container {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 12px;
            margin-bottom: 25px;
        }

        .garden-plant {
            width: 90px;
            height: 90px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
            transition: all 0.3s ease;
            font-size: 2.2rem;
            position: relative;
            box-shadow: 0 5px 12px rgba(0, 0, 0, 0.15);
        }

        .garden-plant:hover {
            transform: scale(1.1);
        }

        .garden-plant.wilting {
            background: linear-gradient(135deg, hsl(var(--destructive) / 0.4), hsl(0, 70%, 50%));
        }

        .garden-plant.overgrown {
            background: linear-gradient(135deg, hsl(var(--accent) / 0.4), hsl(16, 85%, 60%));
        }

        .garden-plant.balanced {
            background: linear-gradient(135deg, hsl(var(--success) / 0.4), hsl(142, 76%, 36%));
        }

        .plant-status {
            position: absolute;
            bottom: -25px;
            font-size: 0.85rem;
            color: hsl(var(--muted-foreground));
            font-weight: 500;
        }

        /* Enhanced Design Elements - ENHANCED */
        .enhanced-card {
            background: white;
            border-radius: var(--radius);
            box-shadow: 0 12px 30px rgba(0, 0, 0, 0.15);
            padding: 28px;
            margin-bottom: 25px;
            border-left: 6px solid hsl(var(--primary));
            transition: all 0.3s ease;
        }

        .english .enhanced-card {
            border-left: none;
            border-right: 6px solid hsl(var(--primary));
        }

        .enhanced-card:hover {
            transform: translateY(-8px);
            box-shadow: 0 18px 35px rgba(0, 0, 0, 0.2);
        }

        .vibrant-btn {
            background: linear-gradient(135deg, hsl(var(--primary)), hsl(201, 96%, 32%));
            color: white;
            border: none;
            border-radius: var(--radius);
            padding: 14px 28px;
            font-weight: 700;
            cursor: pointer;
            transition: all 0.3s ease;
            box-shadow: 0 6px 15px rgba(14, 165, 233, 0.4);
        }

        .vibrant-btn:hover {
            transform: translateY(-5px);
            box-shadow: 0 8px 20px rgba(14, 165, 233, 0.5);
        }

        .colorful-header {
            background: linear-gradient(135deg, hsl(var(--primary)), hsl(201, 96%, 32%), hsl(270, 70%, 60%));
            color: white;
            padding: 25px;
            border-radius: var(--radius);
            text-align: center;
            margin-bottom: 25px;
            box-shadow: 0 8px 20px rgba(0, 0, 0, 0.25);
        }

        /* NEW: Enhanced feedback messages */
        .feedback-positive {
            background: linear-gradient(135deg, hsl(var(--success) / 0.1), hsl(142, 76%, 36% / 0.1));
            border: 2px solid hsl(var(--success));
            color: hsl(var(--success));
            padding: 15px;
            border-radius: var(--radius);
            margin: 10px 0;
            font-weight: 600;
        }

        .feedback-negative {
            background: linear-gradient(135deg, hsl(var(--destructive) / 0.1), hsl(0, 84%, 60% / 0.1));
            border: 2px solid hsl(var(--destructive));
            color: hsl(var(--destructive));
            padding: 15px;
            border-radius: var(--radius);
            margin: 10px 0;
            font-weight: 600;
        }

        /* NEW: Enhanced game elements */
        .game-explanation {
            background: hsl(var(--muted));
            padding: 18px;
            border-radius: var(--radius);
            margin: 15px 0;
            border-left: 4px solid hsl(var(--primary));
            font-weight: 500;
        }

        .english .game-explanation {
            border-left: none;
            border-right: 4px solid hsl(var(--primary));
        }

        .turn-indicator {
            background: linear-gradient(135deg, hsl(var(--primary) / 0.1), hsl(201, 96%, 32% / 0.1));
            padding: 12px 18px;
            border-radius: var(--radius);
            margin: 12px 0;
            border: 2px solid hsl(var(--primary) / 0.3);
            font-weight: 600;
            text-align: center;
        }
    </style>
</head>
<body class="arabic">
    <div class="container">
        <!-- Login Screen -->
        <div id="login-screen">
            <button class="admin-btn" id="admin-btn">لوحة المشرف</button>
            <h1 class="game-title">Inside Out: The Journey Home</h1>
            <p class="game-subtitle">لعبة تأهيلية قائمة على السرد</p>
            
            <div class="language-toggle">
                <button class="language-btn active" data-lang="ar">AR</button>
                <button class="language-btn" data-lang="en">EN</button>
            </div>
            
            <div class="login-form">
                <div class="form-group">
                    <label for="player-name">الاسم</label>
                    <input type="text" id="player-name" placeholder="أدخل اسمك">
                </div>
                
                <div class="form-group">
                    <label for="player-email">البريد الإلكتروني (اختياري)</label>
                    <input type="email" id="player-email" placeholder="أدخل بريدك الإلكتروني">
                </div>
                
                <div class="form-group">
                    <label for="player-gender">الشخصية</label>
                    <select id="player-gender">
                        <option value="male">رجل</option>
                        <option value="female">امرأة</option>
                    </select>
                </div>
                
                <div class="form-group">
                    <label for="game-mode">نمط اللعبة</label>
                    <select id="game-mode">
                        <option value="individual">الوضع الفردي</option>
                        <option value="group">الوضع الجماعي</option>
                    </select>
                </div>
                
                <div class="checkbox-group">
                    <input type="checkbox" id="accept-terms">
                    <label for="accept-terms">أوافق على الشروط وسياسة الخصوصية</label>
                </div>
                
                <button id="start-btn" class="btn">ابدأ الرحلة</button>
                <button id="guest-btn" class="btn btn-secondary">العب كضيف</button>
            </div>
        </div>
        
        <!-- Admin Panel -->
        <div id="admin-panel">
            <div class="admin-header">
                <h1 class="admin-title">لوحة المشرف</h1>
                <button class="btn" id="back-to-game-btn">العودة إلى اللعبة</button>
            </div>
            
            <div class="admin-login" id="admin-login-form">
                <h2>تسجيل دخول المشرف</h2>
                <div class="form-group">
                    <label for="admin-email">البريد الإلكتروني</label>
                    <input type="email" id="admin-email" placeholder="أدخل أي بريد إلكتروني">
                </div>
                <div class="form-group">
                    <label for="admin-password">كلمة المرور</label>
                    <input type="password" id="admin-password" placeholder="أدخل أي كلمة مرور">
                </div>
                <button class="btn" id="admin-login-btn">تسجيل الدخول</button>
            </div>
            
            <div id="admin-dashboard" style="display: none;">
                <div class="admin-stats">
                    <div class="stat-card">
                        <h3>إجمالي اللاعبين</h3>
                        <div class="stat-value" id="total-players">0</div>
                    </div>
                    <div class="stat-card">
                        <h3>النشطون اليوم</h3>
                        <div class="stat-value" id="active-today">0</div>
                    </div>
                    <div class="stat-card">
                        <h3>متوسط التقدم</h3>
                        <div class="stat-value" id="avg-progress">0%</div>
                    </div>
                    <div class="stat-card">
                        <h3>معدل الإكمال</h3>
                        <div class="stat-value" id="completion-rate">0%</div>
                    </div>
                </div>
                
                <div class="player-list">
                    <h2>إحصائيات اللاعبين</h2>
                    <div id="players-container">
                        <!-- Player data will be dynamically generated here -->
                    </div>
                </div>
            </div>
        </div>
        
        <!-- Chapter Map -->
        <div id="chapter-map">
            <div class="header-bar">
                <div class="points-display">
                    <div class="point-type hope-points">
                        <span class="point-icon"><i class="fas fa-star"></i></span>
                        <span id="hope-points">0 نقاط الأمل</span>
                    </div>
                    <div class="point-type insight-points">
                        <span class="point-icon"><i class="fas fa-lightbulb"></i></span>
                        <span id="insight-points">0 نقاط البصيرة</span>
                    </div>
                </div>
                <button class="home-btn" id="map-home-btn"><i class="fas fa-home"></i> الرئيسية</button>
            </div>
            
            <div class="map-container">
                <div class="welcome-message">
                    <h2>رحلتك</h2>
                    <p id="welcome-text">مرحبًا بك في رحلة العلاج النفسي التفاعلية. هذه اللعبة مصممة لمساعدتك في رحلتك نحو الشفاء والتعافي. من خلال سلسلة من الفصول التفاعلية، ستتعلم مهارات جديدة وتكتسب رؤى قيمة حول نفسك.</p>
                    <p>ابدأ رحلتك من خلال إكمال الفصول بالترتيب. كل فصل مصمم لمعالجة تحدٍ محدد ويساعدك في تطوير أدوات للتعامل مع الأعراض.</p>
                </div>
                
                <div class="chapters-grid" id="chapters-container">
                    <!-- Chapters will be dynamically generated here -->
                </div>
            </div>
        </div>
        
        <!-- Game Screen -->
        <div id="game-screen">
            <div class="game-header">
                <button class="btn btn-secondary" id="exit-chapter-btn">خروج من الفصل</button>
                <div class="chapter-info">
                    <div class="chapter-name" id="current-chapter-name">الفصل 1: الشاطئ الهامس</div>
                    <div class="chapter-symptom-game" id="current-chapter-symptom">العَرَض: الخوف والبارانويا</div>
                </div>
                <div class="points-display">
                    <div class="point-type hope-points">
                        <span class="point-icon"><i class="fas fa-star"></i></span>
                        <span id="game-hope-points">0</span>
                    </div>
                    <div class="point-type insight-points">
                        <span class="point-icon"><i class="fas fa-lightbulb"></i></span>
                        <span id="game-insight-points">0</span>
                    </div>
                </div>
            </div>
            
            <div class="game-container">
                <div class="game-scene">
                    <div class="scene-visual" id="scene-visual">
                        <!-- Scene visualization will be dynamically generated -->
                    </div>
                    <div class="game-instructions" id="game-instructions">
                        <!-- Game instructions will be dynamically generated -->
                    </div>
                </div>
                
                <div class="game-mechanics" id="game-mechanics">
                    <!-- Game mechanics will be dynamically generated -->
                </div>
                
                <div class="game-feedback" id="game-feedback">
                    <!-- Game feedback will be dynamically generated -->
                </div>
                
                <div class="game-controls">
                    <button class="btn" id="next-challenge-btn" style="display: none;">التحدي التالي</button>
                    <button class="btn btn-accent" id="complete-chapter-btn" style="display: none;">إكمال الفصل</button>
                </div>
            </div>
        </div>
    </div>
    
    <!-- AI Companion - UPDATED: Only show in group mode -->
    <div class="ai-companion individual-mode" id="ai-companion">
        <span id="companion-avatar">👤</span>
        <div class="companion-message" id="companion-message">
            <div class="companion-text" id="companion-text">مرحبًا! أنا هنا لمساعدتك في رحلتك.</div>
            <button class="close-guide" id="close-companion"><i class="fas fa-times"></i></button>
        </div>
    </div>

    <!-- Inner Guide Popup -->
    <div class="inner-guide" id="inner-guide">
        <div class="inner-guide-text" id="inner-guide-text">
            مرحبًا بك في رحلتك. تذكر أن تتنفس وتركز على اللحظة الحالية.
        </div>
        <button class="close-guide" id="close-guide"><i class="fas fa-times"></i></button>
    </div>

    <script>
        // Game Data
        const gameData = {
            player: {
                name: "",
                email: "",
                gender: "male",
                mode: "individual",
                language: "ar",
                companion: null
            },
            points: {
                hope: 0,
                insight: 0
            },
            currentChapter: 1,
            completedChapters: [],
            startTime: null,
            companions: {
                male: {
                    name: { en: "John", ar: "رضوان" },
                    avatar: "🧑‍💼",
                    messages: {
                        encouragement: [
                            { en: "You're doing great! Keep going!", ar: "أنت تبلي بلاءً حسناً! استمر!" },
                            { en: "I believe in you! You can do this!", ar: "أنا أؤمن بك! يمكنك القيام بذلك!" },
                            { en: "Every step forward is progress!", ar: "كل خطوة إلى الأمام هي تقدم!" },
                            { en: "Your effort is inspiring!", ar: "جهودك ملهمة!" },
                            { en: "You're making amazing progress!", ar: "أنت تحقق تقدماً مذهلاً!" }
                        ],
                        guidance: [
                            { en: "Remember to breathe deeply when you feel overwhelmed.", ar: "تذكر أن تتنفس بعمق عندما تشعر بالإرهاق." },
                            { en: "Focus on one task at a time.", ar: "ركز على مهمة واحدة في كل مرة." },
                            { en: "It's okay to take breaks when you need them.", ar: "لا بأس في أخذ فترات راحة عندما تحتاجها." },
                            { en: "Trust your instincts on this one.", ar: "ثق بحدسك في هذا الأمر." },
                            { en: "Let's work through this together.", ar: "دعنا نعمل على هذا معًا." }
                        ],
                        celebration: [
                            { en: "Amazing work! You're making great progress!", ar: "عمل رائع! أنت تحقق تقدماً كبيراً!" },
                            { en: "I'm proud of your efforts today!", ar: "أنا فخور بجهودك اليوم!" },
                            { en: "You're getting stronger with each challenge!", ar: "أنت تزداد قوة مع كل تحدٍ!" },
                            { en: "Your resilience is remarkable!", ar: "مرونتك ملحوظة!" },
                            { en: "You've come so far already!", ar: "لقد قطعت شوطًا كبيرًا بالفعل!" }
                        ]
                    }
                },
                female: {
                    name: { en: "Zelda", ar: "ريم" },
                    avatar: "👩‍💼",
                    messages: {
                        encouragement: [
                            { en: "You're stronger than you think!", ar: "أنت أقوى مما تعتقد!" },
                            { en: "I'm here to support you every step of the way!", ar: "أنا هنا لدعمك في كل خطوة!" },
                            { en: "Your progress is inspiring!", ar: "تقدمك ملهم!" },
                            { en: "You're handling this beautifully!", ar: "أنت تتعامل مع هذا بشكل رائع!" },
                            { en: "Your determination is admirable!", ar: "تصميمك جدير بالإعجاب!" }
                        ],
                        guidance: [
                            { en: "Take a moment to appreciate how far you've come.", ar: "خذ لحظة لتقدير مدى تقدمك." },
                            { en: "Trust in your abilities - you have what it takes.", ar: "ثق في قدراتك - لديك ما يلزم." },
                            { en: "Remember that healing is a journey, not a destination.", ar: "تذكر أن الشفاء رحلة وليس وجهة." },
                            { en: "Let's approach this step by step.", ar: "دعنا نقترب من هذا خطوة بخطوة." },
                            { en: "Your perspective is valuable here.", ar: "وجهة نظرك قيمة هنا." }
                        ],
                        celebration: [
                            { en: "Wonderful job! Your resilience is remarkable!", ar: "عمل رائع! مرونتك ملحوظة!" },
                            { en: "You're blossoming with each challenge you overcome!", ar: "أنت تزدهر مع كل تحدٍ تتغلب عليه!" },
                            { en: "Your growth is beautiful to witness!", ar: "من الجميل أن نشهد نموك!" },
                            { en: "You're showing incredible strength!", ar: "أنت تظهر قوة لا تصدق!" },
                            { en: "Your progress fills me with joy!", ar: "تقدمك يملأني فرحًا!" }
                        ]
                    }
                }
            },
            groupMembers: [
                { name: { en: "John", ar: "رضوان" }, avatar: "🧑‍💼", status: { en: "Supportive Guide", ar: "مرشد داعم" }, active: true },
                { name: { en: "Zelda", ar: "ريم" }, avatar: "👩‍💼", status: { en: "Encouraging Friend", ar: "صديقة مشجعة" }, active: true }
            ],
            chapters: [
                {
                    id: 1,
                    title: { en: "The Whispering Shore", ar: "الشاطئ الهامس" },
                    symptom: { en: "Fear & Paranoia", ar: "الخوف والبارانويا" },
                    description: { en: "A foggy beach with whispers from unseen sources", ar: "شاطئ ضبابي مع همسات من مصادر غير مرئية" },
                    thumbnail: "https://i.pinimg.com/736x/76/36/d0/7636d0b5c6703426802b470fe5d2a2fa.jpg",
                    scene: "beach",
                    mechanics: "soundIdentification",
                    unlocked: true,
                    story: {
                        en: "You awaken on a foggy beach, hearing whispers all around you. Some sound familiar, others feel threatening. Your first challenge is to distinguish reality from illusion.",
                        ar: "تستيقظ على شاطئ ضبابي، تسمع همسات حولك. بعضها يبدو مألوفًا، والبعض الآخر يبدو مهددًا. تحديك الأول هو التمييز بين الواقع والوهم."
                    },
                    instructions: {
                        en: "Listen carefully and identify which sounds are real (waves, birds) and which are illusions. Click on the real sounds to earn points.",
                        ar: "استمع بعناية وحدد الأصوات الحقيقية (الأمواج، الطيور) والأصوات الوهمية. انقر على الأصوات الحقيقية لكسب النقاط."
                    },
                    hopePoints: 15,
                    insightPoints: 10
                },
                {
                    id: 2,
                    title: { en: "The Empty Village", ar: "القرية الفارغة" },
                    symptom: { en: "Apathy & Avolition", ar: "اللامبالاة وقلة الإرادة" },
                    description: { en: "A silent town where nothing moves", ar: "بلدة صامتة حيث لا شيء يتحرك" },
                    thumbnail: "https://i.pinimg.com/1200x/e1/cd/19/e1cd193226838eff14adef6bd11383cc.jpg",
                    scene: "village",
                    mechanics: "routineBuilding",
                    unlocked: false,
                    story: {
                        en: "The village stands silent, its inhabitants frozen in place. To restore life, you must complete small daily tasks that build momentum.",
                        ar: "تقف القرية صامتة، وسكانها متجمدون في أماكنهم. لاستعادة الحياة، يجب أن تكمل مهام يومية صغيرة تبني الزخم."
                    },
                    instructions: {
                        en: "Complete small daily routines to restore energy to the village. Each completed task brings back color and life.",
                        ar: "أكمل الروتينات اليومية الصغيرة لاستعادة الطاقة إلى القرية. كل مهمة مكتملة تعيد اللون والحياة."
                    },
                    hopePoints: 20,
                    insightPoints: 15
                },
                {
                    id: 3,
                    title: { en: "Hall of Echoes", ar: "قاعة الأصداء" },
                    symptom: { en: "Alogia (Speech Issues)", ar: "فقر الكلام (مشاكل النطق)" },
                    description: { en: "A hall where echoes respond briefly to speech", ar: "قاعة حيث تستجيب الأصداء بإيجاز للكلام" },
                    thumbnail: "https://i.pinimg.com/1200x/9d/94/c3/9d94c34d006c2b288d199a27f1a55cbe.jpg",
                    scene: "hall",
                    mechanics: "communication",
                    unlocked: false,
                    story: {
                        en: "The marble hall echoes your words back emptily. You must help the echo learn emotional depth through meaningful communication.",
                        ar: "تتردد قاعة الرخام كلماتك فارغة. يجب أن تساعد الصدى على تعلم العمق العاطفي من خلال التواصل الهادف."
                    },
                    instructions: {
                        en: "Respond to emotional prompts with descriptive language. The more expressive you are, the richer the echo's response.",
                        ar: "رد على المطالبات العاطفية بلغة وصفية. كلما كنت أكثر تعبيرًا، كانت استجابة الصدى أغنى."
                    },
                    hopePoints: 15,
                    insightPoints: 20
                },
                {
                    id: 4,
                    title: { en: "Mirror Garden", ar: "حديقة المرايا" },
                    symptom: { en: "Blunted Affect", ar: "تسطيح المشاعر" },
                    description: { en: "A garden with statues showing different emotions", ar: "حديقة بها تماثيل تعبر عن مشاعر مختلفة" },
                    thumbnail: "https://i.pinimg.com/1200x/aa/b2/27/aab227ffb0e5a6891abf00af8269676f.jpg",
                    scene: "garden",
                    mechanics: "emotionRecognition",
                    unlocked: false,
                    story: {
                        en: "Frozen statues stand throughout the garden, their faces blank. You must help them express emotions to bring the garden to life.",
                        ar: "تماثيل مجمدة تقف في جميع أنحاء الحديقة، وجوهها فارغة. يجب أن تساعدهم على التعبير عن المشاعر لإحياء الحديقة."
                    },
                    instructions: {
                        en: "Match emotions to facial expressions and situations. Help the statues express their feelings.",
                        ar: "طابق المشاعر مع تعبيرات الوجه والمواقف. ساعد التماثيل على التعبير عن مشاعرها."
                    },
                    hopePoints: 20,
                    insightPoints: 15
                },
                {
                    id: 5,
                    title: { en: "The Silent Lake", ar: "البحيرة الصامتة" },
                    symptom: { en: "Anhedonia", ar: "انعدام التلذذ" },
                    description: { en: "A gray lake where music notes rise from water", ar: "بحيرة رمادية حيث تتصاعد نوتات موسيقية من الماء" },
                    thumbnail: "https://i.pinimg.com/736x/5b/c0/70/5bc07080ae2786ebb16919646bec5dff.jpg",
                    scene: "lake",
                    mechanics: "memoryGame",
                    unlocked: false,
                    story: {
                        en: "The lake appears dull and lifeless. Faint music notes emerge from the water, waiting for you to discover the joy they represent.",
                        ar: "تبدو البحيرة باهتة وبلا حياة. تظهر نوتات موسيقية خافتة من الماء، تنتظر منك اكتشاف الفرح الذي تمثله."
                    },
                    instructions: {
                        en: "Remember the sequence of notes and repeat it correctly. Discover the joy in simple melodies.",
                        ar: "تذكر تسلسل النغمات وكرره بشكل صحيح. اكتشف الفرح في الألحان البسيطة."
                    },
                    hopePoints: 25,
                    insightPoints: 15
                },
                {
                    id: 6,
                    title: { en: "Tower of Doubt", ar: "برج الشك" },
                    symptom: { en: "Cognitive Disorganization", ar: "التفكير غير المنظم" },
                    description: { en: "A tower with shifting staircases and fragmented thoughts", ar: "برج به سلالم متغيرة وأفكار مجزأة" },
                    thumbnail: "https://i.pinimg.com/736x/d7/54/5b/d7545bc50f4eb1a86ac098f2cecc8308.jpg",
                    scene: "tower",
                    mechanics: "emotionSorting",
                    unlocked: false,
                    story: {
                        en: "The tower's thoughts are scattered and disorganized. You must sort emotions into their proper categories to bring order to the chaos.",
                        ar: "أفكار البرج مبعثرة وغير منظمة. يجب أن تصنف المشاعر في فئاتها المناسبة لتحقيق النظام في الفوضى."
                    },
                    instructions: {
                        en: "Drag and drop emotions into the correct categories. Organize your feelings to stabilize the tower.",
                        ar: "اسحب وأسقط المشاعر في الفئات الصحيحة. نظم مشاعرك لتحقيق الاستقرار في البرج."
                    },
                    hopePoints: 15,
                    insightPoints: 25
                },
                {
                    id: 7,
                    title: { en: "Hall of Reflections", ar: "قاعة الانعكاسات" },
                    symptom: { en: "Delusion Awareness", ar: "الوعي بالضلالات" },
                    description: { en: "A hall with distorted reflections whispering conflicting realities", ar: "قاعة بها انعكاسات مشوهة تهمس بواقعيات متضاربة" },
                    thumbnail: "https://i.pinimg.com/736x/82/30/97/82309732535bba748fd4177664a40fda.jpg",
                    scene: "hall",
                    mechanics: "realityTesting",
                    unlocked: false,
                    story: {
                        en: "Your reflections show different versions of reality, each claiming to be true. You must determine which reflection aligns with actual events.",
                        ar: "تظهر انعكاساتك إصدارات مختلفة من الواقع، كل منها تدعي أنها الحقيقة. يجب أن تحدد أي انعكاس يتوافق مع الأحداث الفعلية."
                    },
                    instructions: {
                        en: "Identify which reflections are based on memory, fear, or logic. Question delusions safely.",
                        ar: "حدد أي الانعكاسات تستند إلى الذاكرة، الخوف، أو المنطق. شكك في الضلالات بأمان."
                    },
                    hopePoints: 20,
                    insightPoints: 20
                },
                {
                    id: 8,
                    title: { en: "Bridge of Trust", ar: "جسر الثقة" },
                    symptom: { en: "Social Anxiety", ar: "القلق الاجتماعي" },
                    description: { en: "A shaky bridge requiring cooperation to cross", ar: "جسر مهتز يتطلب التعاون لعبوره" },
                    thumbnail: "https://i.pinimg.com/736x/3f/64/78/3f6478003d508f2f6b75911d9787d231.jpg",
                    scene: "bridge",
                    mechanics: "trustBuilding",
                    unlocked: false,
                    story: {
                        en: "The bridge sways precariously over a deep ravine. Only through trusting cooperation with others can you safely cross to the other side.",
                        ar: "يتأرجح الجسر بشكل خطير فوق واد عميق. فقط من خلال التعاون الواثق مع الآخرين يمكنك عبور الجانب الآخر بأمان."
                    },
                    instructions: {
                        en: "Choose cooperative actions and build trust with companions. Only collaboration stabilizes the bridge.",
                        ar: "اختر الإجراءات التعاونية وابنِ الثقة مع الرفاق. فقط التعاون يثبت الجسر."
                    },
                    hopePoints: 25,
                    insightPoints: 15
                },
                {
                    id: 9,
                    title: { en: "Library of Thoughts", ar: "مكتبة الأفكار" },
                    symptom: { en: "Cognitive Training", ar: "التدريب المعرفي" },
                    description: { en: "A library with fragmented memories on shelves", ar: "مكتبة بها ذكريات مجزأة على الرفوف" },
                    thumbnail: "https://images.unsplash.com/photo-1507842217343-583bb7270b66?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=500&q=80",
                    scene: "library",
                    mechanics: "memoryTraining",
                    unlocked: false,
                    story: {
                        en: "The library shelves hold fragmented memories and thoughts. You must organize them logically to restore clarity to your mind.",
                        ar: "تحمل رفوف المكتبة ذكريات وأفكار مجزأة. يجب أن تنظمها بشكل منطقي لاستعادة الوضوح لعقلك."
                    },
                    instructions: {
                        en: "Match related memories and complete pattern recognition tasks. Reorganize your mind's archive.",
                        ar: "طابق الذكريات ذات الصلة وأكمل مهام التعرف على الأنماط. أعد تنظيم أرشيف عقلك."
                    },
                    hopePoints: 15,
                    insightPoints: 25
                },
                {
                    id: 10,
                    title: { en: "City of Voices", ar: "مدينة الأصوات" },
                    symptom: { en: "Reality Orientation", ar: "توجيه الواقع" },
                    description: { en: "A bustling city with helpful and misleading voices", ar: "مدينة نابضة بالحياة بها أصوات مفيدة ومضللة" },
                    thumbnail: "https://images.unsplash.com/photo-1477959858617-67f85cf4f1df?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=500&q=80",
                    scene: "city",
                    mechanics: "voiceDiscrimination",
                    unlocked: false,
                    story: {
                        en: "The city is filled with voices - some offer guidance, others lead astray. You must learn to distinguish which voices to trust.",
                        ar: "المدينة مليئة بالأصوات - بعضها يقدم التوجيه، والبعض الآخر يضل. يجب أن تتعلم التمييز بين الأصوات التي تثق بها."
                    },
                    instructions: {
                        en: "Identify credible communication sources through conversation choices. Learn to trust reliable voices.",
                        ar: "حدد مصادر الاتصال الموثوقة من خلال خيارات المحادثة. تعلم أن تثق بالأصوات الموثوقة."
                    },
                    hopePoints: 20,
                    insightPoints: 20
                },
                {
                    id: 11,
                    title: { en: "The Shifting Forest", ar: "الغابة المتغيرة" },
                    symptom: { en: "Visual Distortions", ar: "التشوهات البصرية" },
                    description: { en: "A forest where trees and paths seem to change", ar: "غابة حيث الأشجار والمسارات تبدو وكأنها تتغير" },
                    thumbnail: "https://images.unsplash.com/photo-1448375240586-882707db888b?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=500&q=80",
                    scene: "forest",
                    mechanics: "patternRecognition",
                    unlocked: false,
                    story: {
                        en: "The forest ahead seems to shift and change before your eyes. Nothing stays the same for long. You must find the stable patterns to navigate through.",
                        ar: "الغابة أمامك تبدو وكأنها تتحرك وتتغير أمام عينيك. لا شيء يبقى كما هو لفترة طويلة. يجب أن تجد الأنماط المستقرة للتنقل خلالها."
                    },
                    instructions: {
                        en: "In the shifting forest, some patterns remain stable while others change unpredictably. Identify the stable patterns to find your way.",
                        ar: "في الغابة المتغيرة، بعض الأنماط تبقى مستقرة بينما يتغير البعض الآخر بشكل غير متوقع. حدد الأنماط المستقرة لتجد طريقك."
                    },
                    hopePoints: 15,
                    insightPoints: 20
                },
                {
                    id: 12,
                    title: { en: "Echo Valley", ar: "وادي الصدى" },
                    symptom: { en: "Auditory Hallucinations", ar: "الهلوسات السمعية" },
                    description: { en: "A valley where echoes distort reality", ar: "وادي حيث الأصداء تشوه الواقع" },
                    thumbnail: "https://images.unsplash.com/photo-1506905925346-21bda4d32df4?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=500&q=80",
                    scene: "valley",
                    mechanics: "echoIdentification",
                    unlocked: false,
                    story: {
                        en: "As you enter the valley, every sound echoes back to you, sometimes changed or distorted. You must learn which echoes reflect reality.",
                        ar: "عند دخولك الوادي، كل صوت يتردد صداها إليك، أحيانًا يتغير أو يشوه. يجب أن تتعلم أي الأصداء تعكس الواقع."
                    },
                    instructions: {
                        en: "In Echo Valley, some echoes reflect reality accurately while others distort it. Listen carefully and identify the true echoes.",
                        ar: "في وادي الصدى، بعض الأصداء تعكس الواقع بدقة بينما يشوه البعض الآخر. استمع بعناية وحدد الأصداء الحقيقية."
                    },
                    hopePoints: 20,
                    insightPoints: 15
                },
                {
                    id: 13,
                    title: { en: "Mirror Lake", ar: "بحيرة المرايا" },
                    symptom: { en: "Identity Confusion", ar: "الارتباك الهوياتي" },
                    description: { en: "A lake that reflects distorted versions of yourself", ar: "بحيرة تعكس نسخ مشوهة من نفسك" },
                    thumbnail: "https://i.pinimg.com/1200x/be/24/88/be2488f5ca7f8d9d88ac9e6e805e740f.jpg",
                    scene: "lake",
                    mechanics: "selfRecognition",
                    unlocked: false,
                    story: {
                        en: "The still lake shows reflections that don't quite match who you are. Some show you as stronger, others as weaker. Which reflection is the real you?",
                        ar: "البحيرة الهادئة تعكس انعكاسات لا تتطابق تمامًا مع من أنت. بعضها يظهرك أقوى، والبعض الآخر أضعف. أي انعكاس هو أنت الحقيقي؟"
                    },
                    instructions: {
                        en: "The lake shows many reflections, but only one represents your true self. Look for the reflection that shows balance and authenticity.",
                        ar: "البحيرة تظهر العديد من الانعكاسات، لكن واحد فقط يمثل نفسك الحقيقية. ابحث عن الانعكاس الذي يظهر التوازن والأصالة."
                    },
                    hopePoints: 25,
                    insightPoints: 15
                },
                {
                    id: 14,
                    title: { en: "The Maze of Thoughts", ar: "متاهة الأفكار" },
                    symptom: { en: "Disorganized Thinking", ar: "التفكير غير المنظم" },
                    description: { en: "A maze where paths represent different thought patterns", ar: "متاهة حيث تمثل المسارات أنماط تفكير مختلفة" },
                    thumbnail: "https://i.pinimg.com/1200x/2c/c9/d2/2cc9d25808547ec388757b524fc592ac.jpg",
                    scene: "maze",
                    mechanics: "pathFinding",
                    unlocked: false,
                    story: {
                        en: "Before you stands a complex maze of twisting corridors. Each path represents a different thought pattern. You must find the logical path through.",
                        ar: "أمامك تقف متاهة معقدة من الممرات المتعرجة. كل مسار يمثل نمط تفكير مختلف. يجب أن تجد المسار المنطقي للعبور."
                    },
                    instructions: {
                        en: "The labyrinth represents different thought patterns. Some lead to dead ends, while others progress logically. Choose the path that follows a clear, sequential pattern.",
                        ar: "تمثل المتاهة أنماط التفكير المختلفة. بعضها يؤدي إلى طريق مسدود، بينما يتقدم البعض الآخر بشكل منطقي. اختر المسار الذي يتبع نمطًا تسلسليًا واضحًا."
                    },
                    hopePoints: 15,
                    insightPoints: 25
                },
                {
                    id: 15,
                    title: { en: "The Clock Tower", ar: "برج الساعة" },
                    symptom: { en: "Time Perception Issues", ar: "مشاكل إدراك الوقت" },
                    description: { en: "A tower where time seems to move irregularly", ar: "برج حيث يبدو الوقت يتحرك بشكل غير منتظم" },
                    thumbnail: "https://i.pinimg.com/736x/72/27/ed/7227edcc827cf8d4087fd57e2cd702a9.jpg",
                    scene: "tower",
                    mechanics: "timeManagement",
                    unlocked: false,
                    story: {
                        en: "The clock tower's hands move erratically, sometimes fast, sometimes slow. You must restore the proper flow of time to proceed.",
                        ar: "تتحرك أيدي برج الساعة بشكل غير منتظم، أحيانًا بسرعة، وأحيانًا ببطء. يجب أن تعيد التدفق الصحيح للوقت للمتابعة."
                    },
                    instructions: {
                        en: "The clock's hands move unpredictably. Your task is to establish a consistent rhythm by selecting the correct time sequences.",
                        ar: "تتحرك أيدي الساعة بشكل غير متوقع. مهمتك هي إنشاء إيقاع ثابت من خلال اختيار تسلسلات الوقت الصحيحة."
                    },
                    hopePoints: 20,
                    insightPoints: 20
                },
                {
                    id: 16,
                    title: { en: "Garden of Emotions", ar: "حديقة المشاعر" },
                    symptom: { en: "Emotional Dysregulation", ar: "عدم انتظام المشاعر" },
                    description: { en: "A garden where emotions manifest as colorful plants", ar: "حديقة حيث تتجلى المشاعر كنباتات ملونة" },
                    thumbnail: "https://i.pinimg.com/originals/f7/cc/87/f7cc871262a30b444b818409b4d0d4df.png",
                    scene: "garden",
                    mechanics: "emotionMatching",
                    unlocked: false,
                    story: {
                        en: "In this vibrant garden, each plant represents a different emotion. Some are wilting, others overgrown. You must bring balance to the garden.",
                        ar: "في هذه الحديقة النابضة بالحياة، كل نبات يمثل مشاعر مختلفة. بعضها يذبل، والبعض الآخر ينمو بشكل مفرط. يجب أن تحقق التوازن في الحديقة."
                    },
                    instructions: {
                        en: "Match the emotions to their appropriate expressions and situations to bring harmony to the garden.",
                        ar: "طابق المشاعر مع تعبيراتها وحالاتها المناسبة لجلب الانسجام إلى الحديقة."
                    },
                    hopePoints: 25,
                    insightPoints: 15
                },
                {
                    id: 17,
                    title: { en: "The Crystal Caves", ar: "كهوف الكريستال" },
                    symptom: { en: "Sensory Overload", ar: "الحمل الحسي الزائد" },
                    description: { en: "Caves filled with glowing crystals and ambient sounds", ar: "كهوف مليئة بالكريستالات المتوهجة والأصوات المحيطة" },
                    thumbnail: "https://i.pinimg.com/736x/74/57/41/74574190e33b151934318fc48e80ee37.jpg",
                    scene: "cave",
                    mechanics: "sensoryFiltering",
                    unlocked: false,
                    story: {
                        en: "The caves glow with intense colors and echo with overwhelming sounds. You must filter through the sensory input to find your way.",
                        ar: "تتوهج الكهوف بألوان شديدة وتتردد بأصوات ساحقة. يجب أن تصفي المدخلات الحسية لتجد طريقك."
                    },
                    instructions: {
                        en: "The caves are overwhelming with sensory information. Identify which sensations are important and which are distractions.",
                        ar: "الكهوف ساحقة بالمعلومات الحسية. حدد الأحاسيس المهمة وتلك التي تشتت الانتباه."
                    },
                    hopePoints: 15,
                    insightPoints: 25
                },
                {
                    id: 18,
                    title: { en: "The Bridge of Connections", ar: "جسر الروابط" },
                    symptom: { en: "Social Withdrawal", ar: "الانسحاب الاجتماعي" },
                    description: { en: "A bridge that requires cooperation to cross", ar: "جسر يتطلب التعاون لعبوره" },
                    thumbnail: "https://i.pinimg.com/736x/63/b4/79/63b4798ca60734367b24d6ee1a2c0a37.jpg",
                    scene: "bridge",
                    mechanics: "socialInteraction",
                    unlocked: false,
                    story: {
                        en: "A deep chasm separates you from the next part of your journey. The bridge appears fragile, requiring careful cooperation to cross safely.",
                        ar: "يفصلك هوة عميقة عن الجزء التالي من رحلتك. يبدو الجسر هشًا، ويتطلب تعاونًا دقيقًا لعبوره بأمان."
                    },
                    instructions: {
                        en: "The bridge can only be stabilized through positive social interactions. Choose responses that build connection and trust.",
                        ar: "لا يمكن تثبيت الجسر إلا من خلال التفاعلات الاجتماعية الإيجابية. اختر الردود التي تبني التواصل والثقة."
                    },
                    hopePoints: 30,
                    insightPoints: 20
                },
                {
                    id: 19,
                    title: { en: "The Summit of Self", ar: "قمة الذات" },
                    symptom: { en: "Lack of Motivation", ar: "نقص الدافع" },
                    description: { en: "A mountain peak representing personal achievement", ar: "قمة جبل تمثل الإنجاز الشخصي" },
                    thumbnail: "https://i.pinimg.com/736x/f4/6c/81/f46c81320f8ee2dce7b8d79e77f716d1.jpg",
                    scene: "mountain",
                    mechanics: "goalSetting",
                    unlocked: false,
                    story: {
                        en: "The mountain peak towers above you, representing the challenges ahead. Each step requires determination and focus on your ultimate goal.",
                        ar: "تعلو قمة الجبل فوقك، ممثلة التحديات المقبلة. كل خطوة تتطلب العزيمة والتركيز على هدفك النهائي."
                    },
                    instructions: {
                        en: "Reach the summit by setting achievable goals and maintaining motivation through small, consistent steps.",
                        ar: "صل إلى القمة من خلال تحديد أهداف قابلة للتحقيق والحفاظ على الدافع من خلال خطوات صغيرة ومتسقة."
                    },
                    hopePoints: 25,
                    insightPoints: 25
                },
                {
                    id: 20,
                    title: { en: "The Homeland", ar: "الوطن" },
                    symptom: { en: "Integration", ar: "التكامل" },
                    description: { en: "Your restored homeland representing wholeness", ar: "وطنك المستعاد يمثل الكمال" },
                    thumbnail: "https://i.pinimg.com/736x/b5/b1/ae/b5b1ae0ea9440f6fe54339a11154ddd6.jpg",
                    scene: "homeland",
                    mechanics: "integration",
                    unlocked: false,
                    story: {
                        en: "After your long journey, you finally approach your homeland. The challenges you've overcome have prepared you for this final integration.",
                        ar: "بعد رحلتك الطويلة، تقترب أخيرًا من وطنك. التحديات التي تغلبت عليها أعدتك لهذا التكامل النهائي."
                    },
                    instructions: {
                        en: "Reflect on your journey and integrate all the lessons you've learned. You are now ready to return home whole.",
                        ar: "تأمل في رحلتك وادمج كل الدروس التي تعلمتها. أنت الآن مستعد للعودة إلى الوطن كاملًا."
                    },
                    hopePoints: 50,
                    insightPoints: 50
                }
            ],
            language: {
                en: {
                    gameTitle: "Inside Out: The Journey Home",
                    gameSubtitle: "A narrative-driven rehabilitation game",
                    name: "Name",
                    email: "Email (optional)",
                    character: "Character",
                    man: "Man",
                    woman: "Woman",
                    gameMode: "Game Mode",
                    individualMode: "Individual Mode",
                    groupMode: "Group Mode",
                    acceptTerms: "I accept the Terms & Privacy Policy",
                    startJourney: "Start Journey",
                    playAsGuest: "Play as Guest",
                    yourJourney: "Your Journey",
                    welcome: "Welcome to the interactive mental health journey. This game is designed to help you on your path to healing and recovery. Through a series of interactive chapters, you will learn new skills and gain valuable insights about yourself.",
                    welcome2: "Start your journey by completing the chapters in order. Each chapter is designed to address a specific challenge and helps you develop tools to deal with symptoms.",
                    completeChapters: "Complete chapters to restore balance and heal symptoms",
                    hopePoints: "Hope Points",
                    insightPoints: "Insight Points",
                    home: "Home",
                    exitChapter: "Exit Chapter",
                    symptom: "Symptom",
                    nextChallenge: "Next Challenge",
                    completeChapter: "Complete Chapter",
                    innerGuide: {
                        welcome: "Welcome to your journey. Remember to breathe and focus on the present moment.",
                        encouragement: "You're doing great. Every step forward is progress.",
                        reflection: "Take a moment to reflect on what you've learned.",
                        resilience: "Challenges help us grow. You're building resilience with each step."
                    }
                },
                ar: {
                    gameTitle: "من الداخل إلى الخارج: رحلة العودة إلى الديار",
                    gameSubtitle: "لعبة تأهيلية قائمة على السرد",
                    name: "الاسم",
                    email: "البريد الإلكتروني (اختياري)",
                    character: "الشخصية",
                    man: "رجل",
                    woman: "امرأة",
                    gameMode: "نمط اللعبة",
                    individualMode: "الوضع الفردي",
                    groupMode: "الوضع الجماعي",
                    acceptTerms: "أوافق على الشروط وسياسة الخصوصية",
                    startJourney: "ابدأ الرحلة",
                    playAsGuest: "العب كضيف",
                    yourJourney: "رحلتك",
                    welcome: "مرحبًا بك في رحلة العلاج النفسي التفاعلية. هذه اللعبة مصممة لمساعدتك في رحلتك نحو الشفاء والتعافي. من خلال سلسلة من الفصول التفاعلية، ستتعلم مهارات جديدة وتكتسب رؤى قيمة حول نفسك.",
                    welcome2: "ابدأ رحلتك من خلال إكمال الفصول بالترتيب. كل فصل مصمم لمعالجة تحدٍ محدد ويساعدك في تطوير أدوات للتعامل مع الأعراض.",
                    completeChapters: "أكمل الفصول لاستعادة التوازن وعلاج الأعراض",
                    hopePoints: "نقاط الأمل",
                    insightPoints: "نقاط البصيرة",
                    home: "الرئيسية",
                    exitChapter: "خروج من الفصل",
                    symptom: "العَرَض",
                    nextChallenge: "التحدي التالي",
                    completeChapter: "إكمال الفصل",
                    innerGuide: {
                        welcome: "مرحبًا بك في رحلتك. تذكر أن تتنفس وتركز على اللحظة الحالية.",
                        encouragement: "أنت تبلي بلاءً حسنًا. كل خطوة إلى الأمام هي تقدم.",
                        reflection: "خذ لحظة للتفكير فيما تعلمته.",
                        resilience: "التحديات تساعدنا على النمو. أنت تبني المرونة مع كل خطوة."
                    }
                }
            }
        };

        // DOM Elements
        const loginScreen = document.getElementById('login-screen');
        const adminPanel = document.getElementById('admin-panel');
        const chapterMap = document.getElementById('chapter-map');
        const gameScreen = document.getElementById('game-screen');
        const chaptersContainer = document.getElementById('chapters-container');
        const welcomeText = document.getElementById('welcome-text');
        const startBtn = document.getElementById('start-btn');
        const guestBtn = document.getElementById('guest-btn');
        const adminBtn = document.getElementById('admin-btn');
        const backToGameBtn = document.getElementById('back-to-game-btn');
        const adminLoginBtn = document.getElementById('admin-login-btn');
        const adminLoginForm = document.getElementById('admin-login-form');
        const adminDashboard = document.getElementById('admin-dashboard');
        const mapHomeBtn = document.getElementById('map-home-btn');
        const exitChapterBtn = document.getElementById('exit-chapter-btn');
        const languageBtns = document.querySelectorAll('.language-btn');
        const hopePointsDisplay = document.getElementById('hope-points');
        const insightPointsDisplay = document.getElementById('insight-points');
        const gameHopePointsDisplay = document.getElementById('game-hope-points');
        const gameInsightPointsDisplay = document.getElementById('game-insight-points');
        const currentChapterName = document.getElementById('current-chapter-name');
        const currentChapterSymptom = document.getElementById('current-chapter-symptom');
        const sceneVisual = document.getElementById('scene-visual');
        const gameInstructions = document.getElementById('game-instructions');
        const gameMechanics = document.getElementById('game-mechanics');
        const gameFeedback = document.getElementById('game-feedback');
        const nextChallengeBtn = document.getElementById('next-challenge-btn');
        const completeChapterBtn = document.getElementById('complete-chapter-btn');
        const innerGuide = document.getElementById('inner-guide');
        const innerGuideText = document.getElementById('inner-guide-text');
        const closeGuideBtn = document.getElementById('close-guide');
        const aiCompanion = document.getElementById('ai-companion');
        const companionAvatar = document.getElementById('companion-avatar');
        const companionMessage = document.getElementById('companion-message');
        const companionText = document.getElementById('companion-text');
        const closeCompanion = document.getElementById('close-companion');

        // Initialize Game
        function initGame() {
            loadGameProgress();
            renderChapters();
            updatePointsDisplay();
            setupEventListeners();
            showInnerGuide(gameData.language[gameData.player.language].innerGuide.welcome);
            
            // Set start time for session tracking
            gameData.startTime = new Date();
            
            console.log("Game initialized successfully!");
        }

        // Load game progress from localStorage
        function loadGameProgress() {
            const savedProgress = localStorage.getItem('insideOutGameProgress');
            if (savedProgress) {
                try {
                    const progress = JSON.parse(savedProgress);
                    gameData.points = progress.points || { hope: 0, insight: 0 };
                    gameData.completedChapters = progress.completedChapters || [];
                    gameData.currentChapter = progress.currentChapter || 1;
                    
                    // Update chapter unlocked status
                    gameData.chapters.forEach(chapter => {
                        chapter.unlocked = chapter.id <= gameData.currentChapter;
                    });
                    
                    console.log("Game progress loaded:", progress);
                } catch (e) {
                    console.error("Error loading game progress:", e);
                }
            } else {
                console.log("No saved game progress found, starting fresh");
            }
        }

        // Save game progress to localStorage
        function saveGameProgress() {
            const progress = {
                points: gameData.points,
                completedChapters: gameData.completedChapters,
                currentChapter: gameData.currentChapter,
                lastUpdated: new Date().toISOString()
            };
            
            localStorage.setItem('insideOutGameProgress', JSON.stringify(progress));
            console.log("Game progress saved:", progress);
        }

        // Save player data to localStorage
        function savePlayerData() {
            const endTime = new Date();
            const sessionTime = Math.floor((endTime - gameData.startTime) / 1000); // in seconds
            
            const playerData = {
                name: gameData.player.name,
                email: gameData.player.email,
                gender: gameData.player.gender,
                mode: gameData.player.mode,
                language: gameData.player.language,
                points: gameData.points,
                completedChapters: gameData.completedChapters,
                currentChapter: gameData.currentChapter,
                lastPlayed: new Date().toISOString(),
                sessionTime: sessionTime,
                totalPlayTime: 0
            };
            
            // Get existing players or initialize empty array
            let players = JSON.parse(localStorage.getItem('insideOutPlayers')) || [];
            
            // Check if player already exists
            const existingPlayerIndex = players.findIndex(p => p.name === playerData.name);
            if (existingPlayerIndex !== -1) {
                // Update existing player - add session time to total
                playerData.totalPlayTime = (players[existingPlayerIndex].totalPlayTime || 0) + sessionTime;
                players[existingPlayerIndex] = playerData;
            } else {
                // Add new player
                playerData.totalPlayTime = sessionTime;
                players.push(playerData);
            }
            
            // Save updated players list
            localStorage.setItem('insideOutPlayers', JSON.stringify(players));
            console.log("Player data saved:", playerData);
        }

        // Render chapters on the map
        function renderChapters() {
            chaptersContainer.innerHTML = '';
            
            gameData.chapters.forEach(chapter => {
                const isCompleted = gameData.completedChapters.includes(chapter.id);
                const isUnlocked = chapter.unlocked || chapter.id === 1; // الفصل الأول دائمًا مفتوح
                const lang = gameData.player.language;
                
                const chapterCard = document.createElement('div');
                chapterCard.className = `chapter-card ${isUnlocked ? '' : 'locked'} ${isCompleted ? 'completed' : ''}`;
                
                chapterCard.innerHTML = `
                    <div class="chapter-number">${lang === 'ar' ? 'الفصل' : 'Chapter'} ${chapter.id}</div>
                    <div class="chapter-thumbnail" style="background-image: url('${chapter.thumbnail}')">
                        ${isCompleted ? '<div class="check-icon"><i class="fas fa-check"></i></div>' : ''}
                        ${!isUnlocked ? '<div class="lock-icon"><i class="fas fa-lock"></i></div>' : ''}
                    </div>
                    <div class="chapter-title">${chapter.title[lang]}</div>
                    <div class="chapter-symptom">${chapter.symptom[lang]}</div>
                    <div class="chapter-description">${chapter.description[lang]}</div>
                `;
                
                if (isUnlocked) {
                    chapterCard.addEventListener('click', () => startChapter(chapter.id));
                }
                
                chaptersContainer.appendChild(chapterCard);
            });
            
            // Update welcome message
            const lang = gameData.player.language;
            welcomeText.innerHTML = `
                <p>${gameData.language[lang].welcome}</p>
                <p>${gameData.language[lang].welcome2}</p>
            `;
            
            console.log("Chapters rendered successfully");
        }

        // Update points display
        function updatePointsDisplay() {
            const lang = gameData.player.language;
            hopePointsDisplay.textContent = `${gameData.points.hope} ${gameData.language[lang].hopePoints}`;
            insightPointsDisplay.textContent = `${gameData.points.insight} ${gameData.language[lang].insightPoints}`;
            gameHopePointsDisplay.textContent = gameData.points.hope;
            gameInsightPointsDisplay.textContent = gameData.points.insight;
        }

        // Setup event listeners
        function setupEventListeners() {
            console.log("Setting up event listeners...");
            
            startBtn.addEventListener('click', startGame);
            guestBtn.addEventListener('click', startAsGuest);
            adminBtn.addEventListener('click', showAdminPanel);
            backToGameBtn.addEventListener('click', showLoginScreen);
            adminLoginBtn.addEventListener('click', adminLogin);
            mapHomeBtn.addEventListener('click', showLoginScreen);
            exitChapterBtn.addEventListener('click', showChapterMap);
            nextChallengeBtn.addEventListener('click', nextChallenge);
            completeChapterBtn.addEventListener('click', completeChapter);
            closeGuideBtn.addEventListener('click', () => {
                innerGuide.style.display = 'none';
                console.log("Inner guide closed");
            });
            
            // AI Companion events
            aiCompanion.addEventListener('click', toggleCompanionMessage);
            closeCompanion.addEventListener('click', (e) => {
                e.stopPropagation();
                companionMessage.style.display = 'none';
            });
            
            // Language switching
            languageBtns.forEach(btn => {
                btn.addEventListener('click', function() {
                    console.log("Language button clicked:", this.dataset.lang);
                    
                    languageBtns.forEach(b => b.classList.remove('active'));
                    this.classList.add('active');
                    const newLang = this.dataset.lang;
                    gameData.player.language = newLang;
                    
                    // Update all texts immediately
                    updateLanguage();
                    
                    // Re-render chapters with new language
                    renderChapters();
                    
                    // Update points display
                    updatePointsDisplay();
                    
                    // If in game screen, reload the game
                    if (gameScreen.style.display !== 'none') {
                        const currentChapter = gameData.currentChapter;
                        startChapter(currentChapter);
                    }
                    
                    console.log("Language changed to:", newLang);
                });
            });
            
            console.log("Event listeners setup complete");
        }

        // Toggle companion message visibility
        function toggleCompanionMessage() {
            if (companionMessage.style.display === 'block') {
                companionMessage.style.display = 'none';
            } else {
                companionMessage.style.display = 'block';
                // Show a random message from the companion
                showCompanionMessage('encouragement');
            }
        }

        // Show a message from the companion
        function showCompanionMessage(type) {
            if (!gameData.player.companion) return;
            
            const messages = gameData.player.companion.messages[type];
            const randomMessage = messages[Math.floor(Math.random() * messages.length)];
            const lang = gameData.player.language;
            
            companionText.textContent = randomMessage[lang];
            companionMessage.style.display = 'block';
            
            // Auto-hide after 5 seconds
            setTimeout(() => {
                companionMessage.style.display = 'none';
            }, 5000);
        }

        // Update language throughout the game
        function updateLanguage() {
            const lang = gameData.player.language;
            const texts = gameData.language[lang];
            
            console.log("Updating language to:", lang);
            
            // Update login screen
            document.querySelector('.game-title').textContent = texts.gameTitle;
            document.querySelector('.game-subtitle').textContent = texts.gameSubtitle;
            
            const nameLabel = document.querySelector('label[for="player-name"]');
            if (nameLabel) nameLabel.textContent = texts.name;
            
            const emailLabel = document.querySelector('label[for="player-email"]');
            if (emailLabel) emailLabel.textContent = texts.email;
            
            const genderLabel = document.querySelector('label[for="player-gender"]');
            if (genderLabel) genderLabel.textContent = texts.character;
            
            const maleOption = document.querySelector('#player-gender option[value="male"]');
            if (maleOption) maleOption.textContent = texts.man;
            
            const femaleOption = document.querySelector('#player-gender option[value="female"]');
            if (femaleOption) femaleOption.textContent = texts.woman;
            
            const modeLabel = document.querySelector('label[for="game-mode"]');
            if (modeLabel) modeLabel.textContent = texts.gameMode;
            
            const individualOption = document.querySelector('#game-mode option[value="individual"]');
            if (individualOption) individualOption.textContent = texts.individualMode;
            
            const groupOption = document.querySelector('#game-mode option[value="group"]');
            if (groupOption) groupOption.textContent = texts.groupMode;
            
            const termsLabel = document.querySelector('label[for="accept-terms"]');
            if (termsLabel) termsLabel.textContent = texts.acceptTerms;
            
            if (startBtn) startBtn.textContent = texts.startJourney;
            if (guestBtn) guestBtn.textContent = texts.playAsGuest;
            
            // Update chapter map
            const journeyTitle = document.querySelector('#chapter-map .welcome-message h2');
            if (journeyTitle) journeyTitle.textContent = texts.yourJourney;
            
            if (welcomeText) {
                welcomeText.innerHTML = `
                    <p>${texts.welcome}</p>
                    <p>${texts.welcome2}</p>
                `;
            }
            
            if (hopePointsDisplay) {
                hopePointsDisplay.textContent = `${gameData.points.hope} ${texts.hopePoints}`;
            }
            
            if (insightPointsDisplay) {
                insightPointsDisplay.textContent = `${gameData.points.insight} ${texts.insightPoints}`;
            }
            
            if (mapHomeBtn) {
                mapHomeBtn.innerHTML = `<i class="fas fa-home"></i> ${texts.home}`;
            }
            
            // Update game screen
            if (exitChapterBtn) exitChapterBtn.textContent = texts.exitChapter;
            if (nextChallengeBtn) nextChallengeBtn.textContent = texts.nextChallenge;
            if (completeChapterBtn) completeChapterBtn.textContent = texts.completeChapter;
            
            // Apply language styling
            if (lang === 'ar') {
                document.body.className = 'arabic';
                document.body.dir = 'rtl';
                if (loginScreen) loginScreen.className = 'arabic';
                if (chapterMap) chapterMap.className = 'arabic';
                if (gameScreen) gameScreen.className = 'arabic';
            } else {
                document.body.className = 'english';
                document.body.dir = 'ltr';
                if (loginScreen) loginScreen.className = 'english';
                if (chapterMap) chapterMap.className = 'english';
                if (gameScreen) gameScreen.className = 'english';
            }
            
            // Update current chapter if in game
            if (gameScreen && gameScreen.style.display !== 'none') {
                const currentChapter = gameData.chapters.find(c => c.id === gameData.currentChapter);
                if (currentChapterName && currentChapter) {
                    currentChapterName.textContent = `${lang === 'ar' ? 'الفصل' : 'Chapter'} ${currentChapter.id}: ${currentChapter.title[lang]}`;
                }
                if (currentChapterSymptom && currentChapter) {
                    currentChapterSymptom.textContent = `${texts.symptom}: ${currentChapter.symptom[lang]}`;
                }
            }
            
            console.log("Language update complete");
        }

        // Start game with player data
        function startGame() {
            console.log("Start game button clicked");
            
            const playerName = document.getElementById('player-name').value;
            const acceptTerms = document.getElementById('accept-terms').checked;
            const lang = gameData.player.language;
            
            if (!playerName || playerName.trim() === '') {
                alert(lang === 'ar' ? "الرجاء إدخال اسمك" : "Please enter your name");
                return;
            }
            
            if (!acceptTerms) {
                alert(lang === 'ar' ? "الرجاء الموافقة على الشروط والأحكام" : "Please accept the terms and conditions");
                return;
            }
            
            gameData.player.name = playerName.trim();
            gameData.player.email = document.getElementById('player-email').value;
            gameData.player.gender = document.getElementById('player-gender').value;
            gameData.player.mode = document.getElementById('game-mode').value;
            
            // Set companion based on gender and language - ONLY in group mode
            if (gameData.player.mode === "group") {
                gameData.player.companion = gameData.companions[gameData.player.gender];
                if (companionAvatar) {
                    companionAvatar.textContent = gameData.player.companion.avatar;
                }
                
                // Use only one companion based on gender choice
                gameData.groupMembers = [gameData.groupMembers.find(member => 
                    member.name[gameData.player.language] === gameData.player.companion.name[gameData.player.language]
                )];
            } else {
                gameData.player.companion = null;
            }
            
            // Update AI companion display based on game mode
            if (gameData.player.mode === "group") {
                aiCompanion.className = "ai-companion group-mode";
            } else {
                aiCompanion.className = "ai-companion individual-mode";
            }
            
            // Reset points to zero
            gameData.points.hope = 0;
            gameData.points.insight = 0;
            
            // If group mode, add starting points
            if (gameData.player.mode === "group") {
                gameData.points.hope += 20;
                gameData.points.insight += 10;
            }
            
            // Save player data
            savePlayerData();
            
            showChapterMap();
            
            console.log("Game started for player:", gameData.player.name);
        }

        // Start as guest
        function startAsGuest() {
            console.log("Starting as guest");
            
            gameData.player.name = gameData.player.language === 'ar' ? "ضيف" : "Guest";
            gameData.player.email = "";
            gameData.player.gender = "male";
            gameData.player.mode = "individual";
            gameData.player.companion = null;
            
            // Update AI companion display based on game mode
            aiCompanion.className = "ai-companion individual-mode";
            
            // Reset points to zero
            gameData.points.hope = 0;
            gameData.points.insight = 0;
            
            // Save player data
            savePlayerData();
            
            showChapterMap();
            
            console.log("Started as guest");
        }

        // Show login screen
        function showLoginScreen() {
            loginScreen.style.display = 'block';
            adminPanel.style.display = 'none';
            chapterMap.style.display = 'none';
            gameScreen.style.display = 'none';
            aiCompanion.style.display = 'none';
            
            console.log("Showing login screen");
        }

        // Show admin panel
        function showAdminPanel() {
            loginScreen.style.display = 'none';
            adminPanel.style.display = 'block';
            chapterMap.style.display = 'none';
            gameScreen.style.display = 'none';
            aiCompanion.style.display = 'none';
            
            console.log("Showing admin panel");
        }

        // Admin login
        function adminLogin() {
            const email = document.getElementById('admin-email').value;
            const password = document.getElementById('admin-password').value;
            const lang = gameData.player.language;
            
            // Simple authentication - accept any email and password
            if (email && password) {
                adminLoginForm.style.display = 'none';
                adminDashboard.style.display = 'block';
                loadAdminData();
                console.log("Admin login successful");
            } else {
                alert(lang === 'ar' ? "الرجاء إدخال البريد الإلكتروني وكلمة المرور" : "Please enter email and password");
            }
        }

        // Load admin data
        function loadAdminData() {
            // Get players data from localStorage
            const playersData = JSON.parse(localStorage.getItem('insideOutPlayers')) || [];
            
            // Update stats
            document.getElementById('total-players').textContent = playersData.length;
            
            // Calculate active today (players who played today)
            const today = new Date().toISOString().split('T')[0];
            const activeToday = playersData.filter(p => {
                if (!p.lastPlayed) return false;
                const lastPlayedDate = new Date(p.lastPlayed).toISOString().split('T')[0];
                return lastPlayedDate === today;
            }).length;
            document.getElementById('active-today').textContent = activeToday;
            
            // Calculate average progress
            const avgProgress = playersData.length > 0 
                ? Math.round(playersData.reduce((sum, p) => sum + (p.completedChapters ? (p.completedChapters.length / 20 * 100) : 0), 0) / playersData.length)
                : 0;
            document.getElementById('avg-progress').textContent = avgProgress + "%";
            
            // Calculate completion rate (players who completed all chapters)
            const completionRate = playersData.length > 0
                ? Math.round(playersData.filter(p => p.completedChapters && p.completedChapters.length >= 20).length / playersData.length * 100)
                : 0;
            document.getElementById('completion-rate').textContent = completionRate + "%";
            
            // Render player list
            const playersContainer = document.getElementById('players-container');
            playersContainer.innerHTML = '';
            
            if (playersData.length === 0) {
                playersContainer.innerHTML = `<p>${gameData.player.language === 'ar' ? 'لا توجد بيانات للاعبين بعد.' : 'No player data available yet.'}</p>`;
                return;
            }
            
            playersData.forEach(player => {
                const playerItem = document.createElement('div');
                playerItem.className = 'player-item';
                
                const progress = player.completedChapters ? Math.round(player.completedChapters.length / 20 * 100) : 0;
                const correctAnswers = player.points ? Math.floor((player.points.hope + player.points.insight) / 5) : 0;
                const wrongAnswers = player.points ? Math.floor((player.points.hope + player.points.insight) / 10) : 0;
                
                // Calculate total play time in hours and minutes
                const totalSeconds = player.totalPlayTime || 0;
                const hours = Math.floor(totalSeconds / 3600);
                const minutes = Math.floor((totalSeconds % 3600) / 60);
                const timeSpent = `${hours}h ${minutes}m`;
                
                const lastActive = player.lastPlayed ? new Date(player.lastPlayed).toLocaleDateString('en-US') : "Not available";
                
                playerItem.innerHTML = `
                    <div class="player-details">
                        <div class="player-name">${player.name}</div>
                        <div class="player-progress">${player.email || 'No email'} | ${gameData.player.language === 'ar' ? 'آخر نشاط:' : 'Last active:'} ${lastActive}</div>
                    </div>
                    <div class="player-stats">
                        <div class="stat">
                            <div class="stat-value">${progress}%</div>
                            <div class="stat-label">${gameData.player.language === 'ar' ? 'التقدم' : 'Progress'}</div>
                        </div>
                        <div class="stat">
                            <div class="stat-value">${correctAnswers}</div>
                            <div class="stat-label">${gameData.player.language === 'ar' ? 'صحيح' : 'Correct'}</div>
                        </div>
                        <div class="stat">
                            <div class="stat-value">${wrongAnswers}</div>
                            <div class="stat-label">${gameData.player.language === 'ar' ? 'خطأ' : 'Wrong'}</div>
                        </div>
                        <div class="stat">
                            <div class="stat-value">${timeSpent}</div>
                            <div class="stat-label">${gameData.player.language === 'ar' ? 'الوقت' : 'Time'}</div>
                        </div>
                    </div>
                `;
                
                playersContainer.appendChild(playerItem);
            });
            
            console.log("Admin data loaded for", playersData.length, "players");
        }

        // Show chapter map
        function showChapterMap() {
            loginScreen.style.display = 'none';
            adminPanel.style.display = 'none';
            chapterMap.style.display = 'block';
            gameScreen.style.display = 'none';
            
            // Show AI companion only in group mode
            if (gameData.player.mode === "group") {
                aiCompanion.style.display = 'flex';
            } else {
                aiCompanion.style.display = 'none';
            }
            
            renderChapters();
            updatePointsDisplay();
            
            console.log("Showing chapter map");
        }

        // Show game screen
        function showGameScreen() {
            loginScreen.style.display = 'none';
            adminPanel.style.display = 'none';
            chapterMap.style.display = 'none';
            gameScreen.style.display = 'block';
            
            // Show AI companion only in group mode
            if (gameData.player.mode === "group") {
                aiCompanion.style.display = 'flex';
            } else {
                aiCompanion.style.display = 'none';
            }
            
            console.log("Showing game screen for chapter", gameData.currentChapter);
        }

        // Start a chapter
        function startChapter(chapterId) {
            console.log("Starting chapter:", chapterId);
            
            gameData.currentChapter = chapterId;
            const chapter = gameData.chapters.find(c => c.id === chapterId);
            const lang = gameData.player.language;
            
            if (!chapter) {
                console.error("Chapter not found:", chapterId);
                return;
            }
            
            // Update UI with chapter info
            if (currentChapterName) {
                currentChapterName.textContent = `${lang === 'ar' ? 'الفصل' : 'Chapter'} ${chapter.id}: ${chapter.title[lang]}`;
            }
            
            if (currentChapterSymptom) {
                currentChapterSymptom.textContent = `${gameData.language[lang].symptom}: ${chapter.symptom[lang]}`;
            }
            
            // Set up the game based on chapter mechanics
            setupChapterGame(chapter);
            
            showGameScreen();
            
            console.log("Chapter started successfully:", chapter.title[lang]);
        }

        // Set up the game for a specific chapter
        function setupChapterGame(chapter) {
            const lang = gameData.player.language;
            
            console.log("Setting up game for chapter:", chapter.id, "with mechanics:", chapter.mechanics);
            
            // Reset UI elements
            if (gameFeedback) {
                gameFeedback.style.display = 'none';
                gameFeedback.innerHTML = '';
            }
            
            if (nextChallengeBtn) nextChallengeBtn.style.display = 'none';
            if (completeChapterBtn) completeChapterBtn.style.display = 'none';
            
            // Set scene visual with story and background
            if (sceneVisual) {
                sceneVisual.innerHTML = `
                    <div style="text-align: ${lang === 'ar' ? 'right' : 'left'}; padding: 25px; background: rgba(255,255,255,0.9); border-radius: var(--radius); max-width: 80%; margin: 0 auto; box-shadow: 0 5px 15px rgba(0,0,0,0.1);">
                        <h3>${chapter.title[lang]}</h3>
                        <p>${chapter.story[lang]}</p>
                    </div>
                `;
                
                // Set background image based on chapter scene
                let backgroundImage = chapter.thumbnail;
                
                sceneVisual.style.background = `linear-gradient(rgba(0,0,0,0.3), rgba(0,0,0,0.3)), url('${backgroundImage}')`;
                sceneVisual.style.backgroundSize = "cover";
                sceneVisual.style.backgroundPosition = "center";
            }
            
            // Set instructions
            if (gameInstructions) {
                gameInstructions.innerHTML = `
                    <h3>${lang === 'ar' ? 'التعليمات' : 'Instructions'}</h3>
                    <p>${chapter.instructions[lang]}</p>
                `;
                
                // Show group members if in group mode
                if (gameData.player.mode === "group") {
                    const groupHTML = `
                        <div class="group-members">
                            ${gameData.groupMembers.filter(m => m.active).map(member => `
                                <div class="group-member">
                                    <div class="member-avatar">${member.avatar}</div>
                                    <div class="member-name">${member.name[lang]}</div>
                                    <div class="member-status">${member.status[lang]}</div>
                                </div>
                            `).join('')}
                        </div>
                    `;
                    gameInstructions.innerHTML += groupHTML;
                }
            }
            
            // Clear previous game mechanics
            if (gameMechanics) {
                gameMechanics.innerHTML = '';
            }
            
            // Set up game based on mechanics type
            switch(chapter.mechanics) {
                case "soundIdentification":
                    setupSoundIdentificationGame(chapter);
                    break;
                case "routineBuilding":
                    setupRoutineBuildingGame(chapter);
                    break;
                case "communication":
                    setupCommunicationGame(chapter);
                    break;
                case "emotionRecognition":
                    setupEmotionRecognitionGame(chapter);
                    break;
                case "memoryGame":
                    setupMemoryGame(chapter);
                    break;
                default:
                    // For chapters without specific mechanics, show a simple completion button
                    setupDefaultGame(chapter);
            }
            
            console.log("Game setup complete for chapter", chapter.id);
        }

        // Set up sound identification game (Chapter 1) - IMPROVED VERSION with real sounds
        function setupSoundIdentificationGame(chapter) {
            const lang = gameData.player.language;
            
            console.log("Setting up sound identification game");
            
            // Create sounds array
            const sounds = [
                { 
                    name: lang === 'ar' ? "أمواج البحر" : "Ocean Waves", 
                    type: "real", 
                    icon: "fas fa-water",
                    explanation: lang === 'ar' ? "هذا صوت حقيقي للأمواج يمكن سماعه بوضوح على الشاطئ" : "This is a real sound of waves that can be clearly heard on the beach"
                },
                { 
                    name: lang === 'ar' ? "طيور النورس" : "Seagulls", 
                    type: "real", 
                    icon: "fas fa-dove",
                    explanation: lang === 'ar' ? "طيور النورس تصدر أصواتًا حقيقية على الشواطئ" : "Seagulls make real sounds on beaches"
                },
                { 
                    name: lang === 'ar' ? "رياح هادئة" : "Gentle Wind", 
                    type: "real", 
                    icon: "fas fa-wind",
                    explanation: lang === 'ar' ? "الرياح الخفيفة صوت حقيقي في المناطق الساحلية" : "Gentle wind is a real sound in coastal areas"
                },
                { 
                    name: lang === 'ar' ? "همسات مخيفة" : "Scary Whispers", 
                    type: "illusion", 
                    icon: "fas fa-ghost",
                    explanation: lang === 'ar' ? "هذا صوت وهمي من صنع الخوف والبارانويا" : "This is an illusionary sound created by fear and paranoia"
                },
                { 
                    name: lang === 'ar' ? "صوت خطوات خلفك" : "Footsteps Behind You", 
                    type: "illusion", 
                    icon: "fas fa-walking",
                    explanation: lang === 'ar' ? "لا يوجد أحد خلفك، هذا صوت وهمي" : "There's no one behind you, this is an illusionary sound"
                },
                { 
                    name: lang === 'ar' ? "ضحكات ساخرة" : "Mocking Laughter", 
                    type: "illusion", 
                    icon: "fas fa-grin-squint-tears",
                    explanation: lang === 'ar' ? "هذه ضحكات وهمية لا وجود لها في الواقع" : "This is mocking laughter that doesn't exist in reality"
                }
            ];
            
            // Shuffle sounds
            const shuffledSounds = [...sounds].sort(() => Math.random() - 0.5);
            
            let correctSelections = 0;
            const totalRealSounds = sounds.filter(s => s.type === "real").length;
            let companionAnswered = false;
            let playerTurn = true;
            
            // Create game HTML
            gameMechanics.innerHTML = `
                ${gameData.player.mode === "group" ? `
                <div class="companion-turn">
                    <div class="companion-name">${gameData.player.companion.name[lang]}:</div>
                    <p>${lang === 'ar' ? 'دعنا نستمع إلى الأصوات معًا. سأختار أولاً ثم دورك!' : "Let's listen to the sounds together. I'll choose first then it's your turn!"}</p>
                </div>
                ` : ''}
                <div class="sound-controls">
                    <div class="game-instructions">
                        <p>${lang === 'ar' ? 'حدد الأصوات الحقيقية من بين الخيارات التالية:' : 'Identify the real sounds from the following options:'}</p>
                    </div>
                    <div class="interactive-options" style="margin-top: 25px;">
                        ${shuffledSounds.map((sound, index) => `
                            <div class="interactive-option" data-type="${sound.type}" data-index="${index}" data-name="${sound.name}">
                                <i class="${sound.icon} sound-icon"></i>
                                <span>${sound.name}</span>
                            </div>
                        `).join('')}
                    </div>
                    <div class="progress-info" style="margin-top: 15px; text-align: center;">
                        <p>${lang === 'ar' ? `تم تحديد ${correctSelections} من ${totalRealSounds} أصوات حقيقية` : `Selected ${correctSelections} of ${totalRealSounds} real sounds`}</p>
                    </div>
                </div>
                <p>${lang === 'ar' ? 'يجب عليك تحديد جميع الأصوات الحقيقية بشكل صحيح لإكمال الفصل.' : 'You must identify all real sounds correctly to complete the chapter.'}</p>
            `;
            
            // Companion makes first move after a delay (only in group mode)
            if (gameData.player.mode === "group") {
                setTimeout(() => {
                    const realSounds = shuffledSounds.filter(sound => sound.type === "real");
                    if (realSounds.length > 0) {
                        const firstRealSound = realSounds[0];
                        const soundElement = document.querySelector(`.interactive-option[data-index="${shuffledSounds.indexOf(firstRealSound)}"]`);
                        
                        if (soundElement) {
                            // Show companion response
                            const companionResponse = document.createElement('div');
                            companionResponse.className = 'companion-answer';
                            companionResponse.innerHTML = `
                                <div class="companion-name">${gameData.player.companion.name[lang]}:</div>
                                <p>${lang === 'ar' ? 'أعتقد أن' : 'I think'} "${firstRealSound.name}" ${lang === 'ar' ? 'صوت حقيقي!' : 'is a real sound!'}</p>
                            `;
                            gameMechanics.insertBefore(companionResponse, gameMechanics.querySelector('.sound-controls'));
                            
                            // Mark companion answer as correct
                            soundElement.style.backgroundColor = "hsl(var(--success))";
                            soundElement.style.color = "white";
                            soundElement.dataset.completed = "true";
                            companionAnswered = true;
                            correctSelections++;
                            
                            gameData.points.hope += 5;
                            gameData.points.insight += 3;
                            updatePointsDisplay();
                            
                            // Update progress info
                            document.querySelector('.progress-info p').textContent = 
                                lang === 'ar' ? 
                                `تم تحديد ${correctSelections} من ${totalRealSounds} أصوات حقيقية` :
                                `Selected ${correctSelections} of ${totalRealSounds} real sounds`;
                            
                            // Show turn indicator
                            const turnIndicator = document.createElement('div');
                            turnIndicator.className = 'turn-indicator';
                            turnIndicator.innerHTML = lang === 'ar' ? 'الآن دورك! اختر صوتًا حقيقيًا.' : 'Now your turn! Choose a real sound.';
                            gameMechanics.insertBefore(turnIndicator, gameMechanics.querySelector('.sound-controls'));
                        }
                    }
                }, 2000);
            }
            
            // Add event listeners to sound options
            const soundOptions = document.querySelectorAll('.interactive-option');
            
            soundOptions.forEach(option => {
                option.addEventListener('click', function() {
                    if (!playerTurn || this.dataset.completed) return;
                    
                    const soundType = this.dataset.type;
                    const soundName = this.dataset.name;
                    const soundIndex = this.dataset.index;
                    
                    console.log("Sound clicked:", soundName, "Type:", soundType);
                    
                    if (soundType === 'real') {
                        this.style.backgroundColor = "hsl(var(--success))";
                        this.style.color = "white";
                        this.dataset.completed = "true";
                        correctSelections++;
                        
                        gameData.points.hope += 5;
                        gameData.points.insight += 3;
                        
                        // Show positive feedback
                        const feedbackDiv = document.createElement('div');
                        feedbackDiv.className = 'feedback-positive';
                        feedbackDiv.innerHTML = lang === 'ar' ? 
                            `صحيح! "${soundName}" هو صوت حقيقي.` : 
                            `Correct! "${soundName}" is a real sound.`;
                        gameFeedback.innerHTML = '';
                        gameFeedback.appendChild(feedbackDiv);
                        gameFeedback.style.display = 'block';
                        
                        // Show companion encouragement (only in group mode)
                        if (gameData.player.mode === "group") {
                            showCompanionMessage('encouragement');
                        }
                    } else {
                        this.style.backgroundColor = "hsl(var(--destructive))";
                        this.style.color = "white";
                        gameData.points.insight += 1; // Still gain some insight for trying
                        
                        // Show negative feedback
                        const feedbackDiv = document.createElement('div');
                        feedbackDiv.className = 'feedback-negative';
                        feedbackDiv.innerHTML = lang === 'ar' ? 
                            `غير صحيح! "${soundName}" ليس صوتًا حقيقيًا. حاول مرة أخرى!` : 
                            `Incorrect! "${soundName}" is not a real sound. Try again!`;
                        gameFeedback.innerHTML = '';
                        gameFeedback.appendChild(feedbackDiv);
                        gameFeedback.style.display = 'block';
                        
                        // Don't mark as completed, let user try again
                        setTimeout(() => {
                            this.style.backgroundColor = "";
                            this.style.color = "";
                        }, 1500);
                        
                        setTimeout(() => {
                            gameFeedback.style.display = 'none';
                        }, 3000);
                        
                        updatePointsDisplay();
                        return;
                    }
                    
                    // Update progress info
                    document.querySelector('.progress-info p').textContent = 
                        lang === 'ar' ? 
                        `تم تحديد ${correctSelections} من ${totalRealSounds} أصوات حقيقية` :
                        `Selected ${correctSelections} of ${totalRealSounds} real sounds`;
                    
                    updatePointsDisplay();
                    
                    // Check if all real sounds have been identified
                    const requiredAnswers = gameData.player.mode === "group" ? totalRealSounds + 1 : totalRealSounds;
                    const currentAnswers = gameData.player.mode === "group" ? correctSelections + (companionAnswered ? 1 : 0) : correctSelections;
                    
                    console.log("Current answers:", currentAnswers, "Required:", requiredAnswers);
                    
                    if (currentAnswers === requiredAnswers) {
                        const successDiv = document.createElement('div');
                        successDiv.className = 'feedback-positive';
                        successDiv.innerHTML = lang === 'ar' ? 
                            'ممتاز! لقد حددت جميع الأصوات الحقيقية. الهمسات تتلاشى والشاطئ يصبح أكثر هدوءًا.' : 
                            'Excellent! You\'ve identified all the real sounds. The whispers are fading away and the beach becomes more peaceful.';
                        gameFeedback.innerHTML = '';
                        gameFeedback.appendChild(successDiv);
                        gameFeedback.style.display = 'block';
                        
                        // Show complete chapter button after a delay
                        setTimeout(() => {
                            completeChapterBtn.style.display = 'block';
                        }, 2000);
                    } else {
                        // In group mode, alternate turns
                        if (gameData.player.mode === "group") {
                            playerTurn = false;
                            
                            // Companion's turn after a delay
                            setTimeout(() => {
                                const remainingRealSounds = Array.from(document.querySelectorAll('.interactive-option[data-type="real"]:not([data-completed="true"])'));
                                if (remainingRealSounds.length > 0) {
                                    const companionChoice = remainingRealSounds[0];
                                    const soundName = companionChoice.dataset.name;
                                    
                                    companionChoice.style.backgroundColor = "hsl(var(--success))";
                                    companionChoice.style.color = "white";
                                    companionChoice.dataset.completed = "true";
                                    correctSelections++;
                                    
                                    // Show companion response
                                    const companionResponse = document.createElement('div');
                                    companionResponse.className = 'companion-answer';
                                    companionResponse.innerHTML = `
                                        <div class="companion-name">${gameData.player.companion.name[lang]}:</div>
                                        <p>${lang === 'ar' ? 'أعتقد أن' : 'I think'} "${soundName}" ${lang === 'ar' ? 'صوت حقيقي أيضًا!' : 'is also a real sound!'}</p>
                                    `;
                                    gameMechanics.insertBefore(companionResponse, gameMechanics.querySelector('.sound-controls'));
                                    
                                    gameData.points.hope += 5;
                                    gameData.points.insight += 3;
                                    updatePointsDisplay();
                                    
                                    // Update progress info
                                    document.querySelector('.progress-info p').textContent = 
                                        lang === 'ar' ? 
                                        `تم تحديد ${correctSelections} من ${totalRealSounds} أصوات حقيقية` :
                                        `Selected ${correctSelections} of ${totalRealSounds} real sounds`;
                                    
                                    // Show turn indicator
                                    const turnIndicator = document.createElement('div');
                                    turnIndicator.className = 'turn-indicator';
                                    turnIndicator.innerHTML = lang === 'ar' ? 'الآن دورك مرة أخرى!' : 'Now your turn again!';
                                    gameMechanics.insertBefore(turnIndicator, gameMechanics.querySelector('.sound-controls'));
                                    
                                    playerTurn = true;
                                    
                                    // Check if all real sounds have been identified after companion's turn
                                    if (correctSelections === requiredAnswers) {
                                        const successDiv = document.createElement('div');
                                        successDiv.className = 'feedback-positive';
                                        successDiv.innerHTML = lang === 'ar' ? 
                                            'ممتاز! لقد حددت جميع الأصوات الحقيقية. الهمسات تتلاشى والشاطئ يصبح أكثر هدوءًا.' : 
                                            'Excellent! You\'ve identified all the real sounds. The whispers are fading away and the beach becomes more peaceful.';
                                        gameFeedback.innerHTML = '';
                                        gameFeedback.appendChild(successDiv);
                                        gameFeedback.style.display = 'block';
                                        
                                        // Show complete chapter button after a delay
                                        setTimeout(() => {
                                            completeChapterBtn.style.display = 'block';
                                        }, 2000);
                                    }
                                }
                            }, 2000);
                        }
                        
                        setTimeout(() => {
                            gameFeedback.style.display = 'none';
                        }, 3000);
                    }
                });
            });
            
            console.log("Sound identification game setup complete");
        }

        // Complete the current chapter
        function completeChapter() {
            const chapter = gameData.chapters.find(c => c.id === gameData.currentChapter);
            const lang = gameData.player.language;
            
            console.log("Completing chapter:", chapter.id);
            
            // Mark chapter as completed
            if (!gameData.completedChapters.includes(chapter.id)) {
                gameData.completedChapters.push(chapter.id);
            }
            
            // Unlock next chapter if exists
            if (chapter.id < gameData.chapters.length) {
                const nextChapter = gameData.chapters.find(c => c.id === chapter.id + 1);
                if (nextChapter) {
                    nextChapter.unlocked = true;
                    // Update currentChapter to next chapter
                    gameData.currentChapter = nextChapter.id;
                    
                    console.log(`Chapter ${nextChapter.id} unlocked`);
                }
            }
            
            // Add chapter completion points
            gameData.points.hope += chapter.hopePoints;
            gameData.points.insight += chapter.insightPoints;
            
            // Save progress
            saveGameProgress();
            savePlayerData();
            
            // Show completion message
            const successDiv = document.createElement('div');
            successDiv.className = 'feedback-positive';
            successDiv.innerHTML = `
                <p style="font-weight: bold; font-size: 1.2rem;">${lang === 'ar' ? 'اكتمل الفصل!' : 'Chapter Completed!'}</p>
                <p>${lang === 'ar' ? 'لقد حققت تقدمًا في معالجة' : 'You\'ve made progress in addressing'} ${chapter.symptom[lang]}.</p>
                <p>${lang === 'ar' ? `نقاط الأمل: +${chapter.hopePoints} | نقاط البصيرة: +${chapter.insightPoints}` : `Hope Points: +${chapter.hopePoints} | Insight Points: +${chapter.insightPoints}`}</p>
            `;
            gameFeedback.innerHTML = '';
            gameFeedback.appendChild(successDiv);
            gameFeedback.style.display = 'block';
            
            updatePointsDisplay();
            
            // Show companion celebration (only in group mode)
            if (gameData.player.mode === "group") {
                showCompanionMessage('celebration');
            }
            
            // Show inner guide with reflection
            showInnerGuide(gameData.language[gameData.player.language].innerGuide.reflection);
            
            // Return to chapter map after a delay
            setTimeout(() => {
                showChapterMap();
            }, 4000);
            
            console.log("Chapter completed successfully");
        }

        // Show inner guide message
        function showInnerGuide(message) {
            if (innerGuideText) {
                innerGuideText.textContent = message;
                innerGuide.style.display = 'block';
                
                // Auto-hide after 5 seconds
                setTimeout(() => {
                    innerGuide.style.display = 'none';
                }, 5000);
            }
        }

        // Placeholder function for next challenge
        function nextChallenge() {
            // In a full implementation, this would load the next challenge in the chapter
            if (nextChallengeBtn) nextChallengeBtn.style.display = 'none';
            if (completeChapterBtn) completeChapterBtn.style.display = 'block';
            
            showInnerGuide(gameData.language[gameData.player.language].innerGuide.encouragement);
        }

        // Initialize the game when the page loads
        window.addEventListener('DOMContentLoaded', function() {
            console.log("DOM fully loaded, initializing game...");
            initGame();
        });

// ================================================
// الجزء الأول: ألعاب الفصول 1-4 (معدل نهائي)
// ================================================

// Set up sound identification game (Chapter 1) - معدل مع صوت الشاطئ الحقيقي
function setupSoundIdentificationGame(chapter) {
    const lang = gameData.player.language;
    
    console.log("Setting up sound identification game");
    
    // Create sounds array
    const sounds = [
        { name: lang === 'ar' ? "أمواج البحر" : "Ocean Waves", type: "real", icon: "fas fa-water", explanation: lang === 'ar' ? "صوت الأمواج الحقيقي الذي يمكن سماعه على الشاطئ" : "Real ocean waves sound that can be heard on the beach" },
        { name: lang === 'ar' ? "طيور النورس" : "Seagulls", type: "real", icon: "fas fa-dove", explanation: lang === 'ar' ? "طيور النورس تصدر أصواتاً حقيقية على الشواطئ" : "Seagulls make real sounds on beaches" },
        { name: lang === 'ar' ? "همسات مخيفة" : "Scary Whispers", type: "illusion", icon: "fas fa-ghost", explanation: lang === 'ar' ? "همسات وهمية ناتجة عن الخوف والبارانويا" : "Illusionary whispers caused by fear and paranoia" },
        { name: lang === 'ar' ? "ضجيج مزعج" : "Annoying Noise", type: "illusion", icon: "fas fa-volume-up", explanation: lang === 'ar' ? "ضجيج وهمي غير موجود في الواقع" : "Illusionary noise that doesn't exist in reality" },
        { name: lang === 'ar' ? "رياح هادئة" : "Gentle Wind", type: "real", icon: "fas fa-wind", explanation: lang === 'ar' ? "صوت الرياح الحقيقي في المناطق الساحلية" : "Real wind sound in coastal areas" },
        { name: lang === 'ar' ? "صوت خطوات" : "Footsteps", type: "illusion", icon: "fas fa-walking", explanation: lang === 'ar' ? "خطوات وهمية لا وجود لها في الواقع" : "Illusionary footsteps that don't exist" }
    ];
    
    // Shuffle sounds
    const shuffledSounds = [...sounds].sort(() => Math.random() - 0.5);
    
    let correctSelections = 0;
    const totalRealSounds = sounds.filter(s => s.type === "real").length;
    let companionTurn = gameData.player.mode === "group";
    let playerTurn = !companionTurn;
    let gameCompleted = false;
    
    // Create game HTML
    gameMechanics.innerHTML = `
        ${companionTurn ? `
        <div class="companion-turn">
            <div class="companion-name">${gameData.player.companion.name[lang]}:</div>
            <p>${lang === 'ar' ? 'دعنا نستمع إلى الأصوات معًا! سأبدأ أولاً.' : "Let's listen to the sounds together! I'll start first."}</p>
        </div>
        ` : ''}
        <div class="sound-controls">
            <div class="game-instructions">
                <p>${lang === 'ar' ? 'حدد الأصوات الحقيقية من بين الخيارات التالية:' : 'Identify the real sounds from the following options:'}</p>
                <p>${lang === 'ar' ? 'يجب تحديد جميع الأصوات الحقيقية (3 أصوات) لإكمال الفصل.' : 'You must identify all real sounds (3 sounds) to complete the chapter.'}</p>
            </div>
            <button class="btn play-sound-btn" id="play-beach-sound">
                <i class="fas fa-play-circle"></i> ${lang === 'ar' ? 'تشغيل صوت الشاطئ' : 'Play Beach Sound'}
            </button>
            <div class="interactive-options" style="margin-top: 25px;">
                ${shuffledSounds.map((sound, index) => `
                    <div class="interactive-option" data-type="${sound.type}" data-index="${index}" data-name="${sound.name}">
                        <i class="${sound.icon}" style="font-size: 1.8rem;"></i>
                        <span>${sound.name}</span>
                    </div>
                `).join('')}
            </div>
            <div class="progress-info" style="margin-top: 15px; text-align: center;">
                <p>${lang === 'ar' ? `تم تحديد ${correctSelections} من ${totalRealSounds} أصوات حقيقية` : `Selected ${correctSelections} of ${totalRealSounds} real sounds`}</p>
            </div>
        </div>
    `;
    
    // Play beach sound functionality with REAL beach sound
    const playSoundBtn = document.getElementById('play-beach-sound');
    let beachSound = null;
    
    playSoundBtn.addEventListener('click', function() {
        try {
            // Use the specific beach sound URL requested
            const soundUrl = 'https://cdn.pixabay.com/download/audio/2022/03/15/audio_34224.mp3';
            
            if (beachSound) {
                beachSound.pause();
                beachSound.currentTime = 0;
            }
            
            beachSound = new Audio(soundUrl);
            beachSound.volume = 0.7;
            
            // Visual feedback
            const originalHTML = this.innerHTML;
            this.innerHTML = '<i class="fas fa-volume-up"></i> ' + (lang === 'ar' ? 'جاري التشغيل...' : 'Playing...');
            this.disabled = true;
            
            // Play the sound
            const playPromise = beachSound.play();
            
            if (playPromise !== undefined) {
                playPromise.then(() => {
                    console.log("Beach sound playing successfully");
                }).catch(error => {
                    console.log("Audio play failed:", error);
                    this.innerHTML = '<i class="fas fa-volume-mute"></i> ' + (lang === 'ar' ? 'انقر مرة أخرى للاستماع' : 'Click again to listen');
                    this.disabled = false;
                });
            }
            
            // Restore button when sound ends
            beachSound.onended = () => {
                this.innerHTML = originalHTML;
                this.disabled = false;
            };
            
            // Also restore after 5 seconds max
            setTimeout(() => {
                this.innerHTML = originalHTML;
                this.disabled = false;
            }, 5000);
            
        } catch (error) {
            console.log("Audio error:", error);
            // Fallback visual feedback
            const originalHTML = this.innerHTML;
            this.innerHTML = '<i class="fas fa-volume-up"></i> ' + (lang === 'ar' ? 'صوت الشاطئ' : 'Beach Sound');
            this.style.backgroundColor = "hsl(var(--primary))";
            this.style.color = "white";
            
            setTimeout(() => {
                this.innerHTML = originalHTML;
                this.style.backgroundColor = "";
                this.style.color = "";
            }, 1000);
        }
    });
    
    // Function for companion to play
    function companionPlay() {
        if (!companionTurn || gameCompleted) return;
        
        setTimeout(() => {
            const remainingRealSounds = Array.from(document.querySelectorAll('.interactive-option[data-type="real"]:not([data-completed="true"])'));
            if (remainingRealSounds.length > 0) {
                const companionChoice = remainingRealSounds[0];
                const soundName = companionChoice.dataset.name;
                const soundObj = sounds.find(s => s.name === soundName);
                
                // Show companion response
                const companionResponse = document.createElement('div');
                companionResponse.className = 'companion-answer';
                companionResponse.innerHTML = `
                    <div class="companion-name">${gameData.player.companion.name[lang]}:</div>
                    <p>${lang === 'ar' ? 'أعتقد أن' : 'I think'} "${soundName}" ${lang === 'ar' ? 'صوت حقيقي! ' : 'is a real sound! '} ${soundObj.explanation}</p>
                `;
                gameMechanics.insertBefore(companionResponse, gameMechanics.querySelector('.sound-controls'));
                
                // Mark companion's choice
                companionChoice.style.backgroundColor = "hsl(var(--success))";
                companionChoice.style.color = "white";
                companionChoice.dataset.completed = "true";
                correctSelections++;
                
                gameData.points.hope += 5;
                gameData.points.insight += 3;
                updatePointsDisplay();
                
                // Update progress info
                document.querySelector('.progress-info p').textContent = 
                    lang === 'ar' ? 
                    `تم تحديد ${correctSelections} من ${totalRealSounds} أصوات حقيقية` :
                    `Selected ${correctSelections} of ${totalRealSounds} real sounds`;
                
                // Check if game is complete
                if (correctSelections === totalRealSounds) {
                    endGame();
                } else {
                    // Switch turns
                    companionTurn = false;
                    playerTurn = true;
                    
                    // Show turn indicator
                    const turnIndicator = document.createElement('div');
                    turnIndicator.className = 'turn-indicator';
                    turnIndicator.innerHTML = lang === 'ar' ? 'الآن دورك! اختر صوتًا حقيقيًا.' : 'Now your turn! Choose a real sound.';
                    gameMechanics.insertBefore(turnIndicator, gameMechanics.querySelector('.sound-controls'));
                }
            }
        }, 1500);
    }
    
    // Start with companion if it's companion's turn
    if (companionTurn && gameData.player.mode === "group") {
        companionPlay();
    }
    
    // Add event listeners to sound options
    const soundOptions = document.querySelectorAll('.interactive-option');
    
    soundOptions.forEach(option => {
        option.addEventListener('click', function() {
            if (!playerTurn || this.dataset.completed || gameCompleted) return;
            
            const soundType = this.dataset.type;
            const soundName = this.dataset.name;
            const soundObj = sounds.find(s => s.name === soundName);
            
            if (soundType === 'real') {
                // Correct selection
                this.style.backgroundColor = "hsl(var(--success))";
                this.style.color = "white";
                this.dataset.completed = "true";
                correctSelections++;
                
                gameData.points.hope += 5;
                gameData.points.insight += 3;
                
                // Show positive feedback
                const feedbackDiv = document.createElement('div');
                feedbackDiv.className = 'feedback-positive';
                feedbackDiv.innerHTML = lang === 'ar' ? 
                    `🎉 صحيح! "${soundName}" هو صوت حقيقي. ${soundObj.explanation}` : 
                    `🎉 Correct! "${soundName}" is a real sound. ${soundObj.explanation}`;
                gameFeedback.innerHTML = '';
                gameFeedback.appendChild(feedbackDiv);
                gameFeedback.style.display = 'block';
                
                // Show companion encouragement (only in group mode)
                if (gameData.player.mode === "group") {
                    showCompanionMessage('encouragement');
                }
            } else {
                // Wrong selection
                this.style.backgroundColor = "hsl(var(--destructive))";
                this.style.color = "white";
                gameData.points.insight += 1;
                
                // Show negative feedback
                const feedbackDiv = document.createElement('div');
                feedbackDiv.className = 'feedback-negative';
                feedbackDiv.innerHTML = lang === 'ar' ? 
                    `❌ خطأ! "${soundName}" ليس صوتًا حقيقيًا. ${soundObj.explanation} حاول مرة أخرى!` : 
                    `❌ Wrong! "${soundName}" is not a real sound. ${soundObj.explanation} Try again!`;
                gameFeedback.innerHTML = '';
                gameFeedback.appendChild(feedbackDiv);
                gameFeedback.style.display = 'block';
                
                // Reset after delay to allow retry
                setTimeout(() => {
                    this.style.backgroundColor = "";
                    this.style.color = "";
                    gameFeedback.style.display = 'none';
                }, 2000);
                
                updatePointsDisplay();
                return;
            }
            
            // Update progress info
            document.querySelector('.progress-info p').textContent = 
                lang === 'ar' ? 
                `تم تحديد ${correctSelections} من ${totalRealSounds} أصوات حقيقية` :
                `Selected ${correctSelections} of ${totalRealSounds} real sounds`;
            
            updatePointsDisplay();
            
            // Check if all real sounds have been identified
            if (correctSelections === totalRealSounds) {
                endGame();
            } else {
                // In group mode, alternate turns
                if (gameData.player.mode === "group") {
                    playerTurn = false;
                    companionTurn = true;
                    
                    // Companion's turn after a delay
                    setTimeout(() => {
                        companionPlay();
                    }, 2000);
                }
                
                setTimeout(() => {
                    gameFeedback.style.display = 'none';
                }, 2000);
            }
        });
    });
    
    function endGame() {
        gameCompleted = true;
        const successDiv = document.createElement('div');
        successDiv.className = 'feedback-positive';
        successDiv.innerHTML = lang === 'ar' ? 
            '🎉 ممتاز! لقد حددت جميع الأصوات الحقيقية. الهمسات تتلاشى والشاطئ يصبح أكثر هدوءًا.' : 
            '🎉 Excellent! You\'ve identified all the real sounds. The whispers are fading away and the beach becomes more peaceful.';
        gameFeedback.innerHTML = '';
        gameFeedback.appendChild(successDiv);
        gameFeedback.style.display = 'block';
        
        // Add bonus points
        gameData.points.hope += 10;
        gameData.points.insight += 5;
        updatePointsDisplay();
        
        // Show complete chapter button after a delay
        setTimeout(() => {
            completeChapterBtn.style.display = 'block';
        }, 2000);
    }
    
    console.log("Sound identification game setup complete");
}



// Set up emotion recognition game (Chapter 4) - نظام محسن للأوضاع الفردية والجماعية
function setupEmotionRecognitionGame(chapter) {
    const lang = gameData.player.language;
    
    console.log("Setting up emotion recognition game");
    
    const emotions = lang === 'ar' ? [
        { name: "سعادة", emoji: "😊", description: "شعور بالفرح والرضا" },
        { name: "حزن", emoji: "😢", description: "شعور بالخسارة أو خيبة الأمل" },
        { name: "غضب", emoji: "😠", description: "شعور بالإحباط أو الاستياء" },
        { name: "خوف", emoji: "😨", description: "شعور بالقلق أو التهديد" },
        { name: "دهشة", emoji: "😲", description: "شعور بالمفاجأة أو الصدمة" },
        { name: "اشمئزاز", emoji: "🤢", description: "شعور بالنفور أو الرفض" },
        { name: "ثقة", emoji: "😌", description: "شعور بالأمان والاعتماد" },
        { name: "خجل", emoji: "😳", description: "شعور بالحرج أو الإحراج" }
    ] : [
        { name: "Happiness", emoji: "😊", description: "Feeling of joy and contentment" },
        { name: "Sadness", emoji: "😢", description: "Feeling of loss or disappointment" },
        { name: "Anger", emoji: "😠", description: "Feeling of frustration or resentment" },
        { name: "Fear", emoji: "😨", description: "Feeling of anxiety or threat" },
        { name: "Surprise", emoji: "😲", description: "Feeling of astonishment or shock" },
        { name: "Disgust", emoji: "🤢", description: "Feeling of revulsion or rejection" },
        { name: "Trust", emoji: "😌", description: "Feeling of security and reliance" },
        { name: "Shame", emoji: "😳", description: "Feeling of embarrassment or humiliation" }
    ];
    
    const situations = lang === 'ar' ? [
        { situation: "فوز في مسابقة", correctEmotion: "سعادة", explanation: "الفوز عادةً ما يسبب شعورًا بالسعادة والفرح." },
        { situation: "فقدان شخص عزيز", correctEmotion: "حزن", explanation: "فقدان شخص عزيز يسبب شعورًا عميقًا بالحزن." },
        { situation: "ظلم من شخص آخر", correctEmotion: "غضب", explanation: "التعرض للظلم يسبب شعورًا بالغضب والاستياء." },
        { situation: "المشي في شارع مظلم", correctEmotion: "خوف", explanation: "المواقف الخطرة أو المجهولة تسبب الخوف." },
        { situation: "هدية غير متوقعة", correctEmotion: "دهشة", explanation: "الأشياء غير المتوقعة تسبب الدهشة." },
        { situation: "طعام فاسد", correctEmotion: "اشمئزاز", explanation: "الأشياء المكروهة تسبب الشعور بالاشمئزاز." },
        { situation: "شخص يساعدك عندما تحتاج", correctEmotion: "ثقة", explanation: "المساعدة في وقت الحاجة تسبب الشعور بالثقة." },
        { situation: "خطأ أمام مجموعة من الناس", correctEmotion: "خجل", explanation: "الأخطاء العلنية تسبب الشعور بالخجل." }
    ] : [
        { situation: "Winning a competition", correctEmotion: "Happiness", explanation: "Winning usually causes feelings of happiness and joy." },
        { situation: "Losing a loved one", correctEmotion: "Sadness", explanation: "Losing a loved one causes deep feelings of sadness." },
        { situation: "Being treated unfairly", correctEmotion: "Anger", explanation: "Being treated unfairly causes feelings of anger and resentment." },
        { situation: "Walking in a dark alley", correctEmotion: "Fear", explanation: "Dangerous or unknown situations cause fear." },
        { situation: "Receiving an unexpected gift", correctEmotion: "Surprise", explanation: "Unexpected things cause surprise." },
        { situation: "Eating spoiled food", correctEmotion: "Disgust", explanation: "Disliked things cause feelings of disgust." },
        { situation: "Someone helps you when you need it", correctEmotion: "Trust", explanation: "Help in times of need causes feelings of trust." },
        { situation: "Making a mistake in front of a group", correctEmotion: "Shame", explanation: "Public mistakes cause feelings of shame." }
    ];
    
    // Shuffle situations and select 4 random ones
    const shuffledSituations = [...situations].sort(() => Math.random() - 0.5).slice(0, 4);
    let currentSituation = 0;
    let gameCompleted = false;
    
    // For group mode: track whose turn it is
    let isCompanionTurn = (gameData.player.mode === "group");
    
    function displaySituation() {
        if (currentSituation >= shuffledSituations.length) {
            endGame();
            return;
        }
        
        const situation = shuffledSituations[currentSituation];
        
        // Get the correct emotion object
        const correctEmotion = emotions.find(e => e.name === situation.correctEmotion);
        
        // Shuffle emotion options (include correct one and 3 random wrong ones)
        const wrongEmotions = emotions.filter(e => e.name !== situation.correctEmotion);
        const randomWrongEmotions = [...wrongEmotions].sort(() => Math.random() - 0.5).slice(0, 3);
        const emotionOptions = [correctEmotion, ...randomWrongEmotions].sort(() => Math.random() - 0.5);
        
        gameMechanics.innerHTML = '';
        
        // For group mode: show who's turn it is
        if (gameData.player.mode === "group") {
            if (isCompanionTurn) {
                const companionTurnDiv = document.createElement('div');
                companionTurnDiv.className = 'companion-turn';
                companionTurnDiv.innerHTML = `
                    <div class="companion-name">${gameData.player.companion.name[lang]}:</div>
                    <p>${lang === 'ar' ? 'دعنا نحدد المشاعر معًا! دوري الآن.' : "Let's identify emotions together! My turn now."}</p>
                `;
                gameMechanics.appendChild(companionTurnDiv);
            } else {
                const playerTurnDiv = document.createElement('div');
                playerTurnDiv.className = 'player-turn';
                playerTurnDiv.innerHTML = `
                    <div class="player-name">${lang === 'ar' ? 'دورك:' : 'Your turn:'}</div>
                    <p>${lang === 'ar' ? '🏃‍♂️ الآن دورك! اختر الشعور المناسب.' : '🏃‍♂️ Now your turn! Choose the appropriate emotion.'}</p>
                `;
                gameMechanics.appendChild(playerTurnDiv);
            }
        }
        
        const questionContainer = document.createElement('div');
        questionContainer.className = 'question-container';
        questionContainer.innerHTML = `
            <div class="question-text">
                <p><strong>${lang === 'ar' ? 'الموقف:' : 'Situation:'}</strong> ${situation.situation}</p>
                <p>${lang === 'ar' ? 'ما هو الشعور المناسب لهذا الموقف؟' : 'What is the appropriate emotion for this situation?'}</p>
            </div>
            <div class="answer-options" id="answer-options">
                ${emotionOptions.map(emotion => `
                    <div class="answer-option" data-emotion="${emotion.name}" data-correct="${emotion.name === situation.correctEmotion}">
                        <span style="font-size: 2rem;">${emotion.emoji}</span>
                        <span>${emotion.name}</span>
                    </div>
                `).join('')}
            </div>
        `;
        gameMechanics.appendChild(questionContainer);
        
        const instructionText = document.createElement('p');
        instructionText.textContent = lang === 'ar' ? 'اختر المشاعر التي تتوافق مع الموقف.' : 'Choose the emotion that matches the situation.';
        gameMechanics.appendChild(instructionText);
        
        // Function for companion to play in group mode
        function companionPlay() {
            if (!isCompanionTurn || gameData.player.mode !== "group" || gameCompleted) return;
            
            setTimeout(() => {
                // Show companion response
                const companionResponse = document.createElement('div');
                companionResponse.className = 'companion-answer';
                companionResponse.innerHTML = `
                    <div class="companion-name">${gameData.player.companion.name[lang]}:</div>
                    <p>${lang === 'ar' ? 'أعتقد أن الشعور المناسب هو' : 'I think the appropriate emotion is'} "${situation.correctEmotion}" ${lang === 'ar' ? 'لأن' : 'because'} ${correctEmotion.description}.</p>
                `;
                
                // إدراج الاستجابة قبل خيارات الإجابة
                const answerOptionsElement = document.getElementById('answer-options');
                if (answerOptionsElement) {
                    questionContainer.insertBefore(companionResponse, answerOptionsElement);
                }
                
                // Automatically select the correct answer for companion
                const correctOption = document.querySelector(`.answer-option[data-emotion="${situation.correctEmotion}"]`);
                if (correctOption) {
                    correctOption.style.backgroundColor = "hsl(var(--success))";
                    correctOption.style.color = "white";
                    correctOption.dataset.completed = "true";
                }
                
                gameData.points.hope += 5;
                gameData.points.insight += 5;
                updatePointsDisplay();
                
                // Move to next question after delay
                setTimeout(() => {
                    currentSituation++;
                    isCompanionTurn = false; // Next turn will be player's turn
                    
                    if (currentSituation < shuffledSituations.length) {
                        displaySituation();
                    } else {
                        endGame();
                    }
                }, 2000);
                
            }, 2000);
        }
        
        // Start with companion if it's companion's turn in group mode
        if (isCompanionTurn && gameData.player.mode === "group") {
            companionPlay();
        }
        
        // إضافة مستمعي الأحداث بعد إنشاء العناصر
        setTimeout(() => {
            // Add event listeners to emotion options (only if it's player's turn or individual mode)
            if (gameData.player.mode !== "group" || !isCompanionTurn) {
                const emotionOptionsElements = document.querySelectorAll('.answer-option');
                
                emotionOptionsElements.forEach(option => {
                    option.addEventListener('click', () => {
                        if (gameCompleted) return;
                        
                        const selectedEmotion = option.dataset.emotion;
                        const isCorrect = selectedEmotion === situation.correctEmotion;
                        
                        if (isCorrect) {
                            // Correct answer
                            option.classList.add('correct');
                            option.style.backgroundColor = "hsl(var(--success))";
                            option.style.color = "white";
                            
                            gameData.points.hope += 5;
                            gameData.points.insight += 5;
                            
                            // Show feedback
                            const feedbackDiv = document.createElement('div');
                            feedbackDiv.className = 'feedback-positive';
                            feedbackDiv.innerHTML = `
                                <p style="color: hsl(var(--success));">${lang === 'ar' ? '🎉 صحيح! هذا هو الشعور المناسب.' : '🎉 Correct! This is the appropriate emotion.'}</p>
                                <p>${situation.explanation}</p>
                            `;
                            
                            gameFeedback.innerHTML = '';
                            gameFeedback.appendChild(feedbackDiv);
                            gameFeedback.style.display = 'block';
                            
                            updatePointsDisplay();
                            
                            // Show companion encouragement (only in group mode)
                            if (gameData.player.mode === "group") {
                                showCompanionMessage('encouragement');
                            }
                            
                            // Move to next question after delay
                            setTimeout(() => {
                                gameFeedback.style.display = 'none';
                                currentSituation++;
                                
                                // في الوضع الجماعي، التناوب في الأدوار
                                if (gameData.player.mode === "group") {
                                    isCompanionTurn = true; // الرفيق يلعب في الجولة القادمة
                                }
                                
                                if (currentSituation < shuffledSituations.length) {
                                    displaySituation();
                                } else {
                                    endGame();
                                }
                            }, 1500);
                        } else {
                            // Wrong answer - stay on same question
                            option.classList.add('incorrect');
                            option.style.backgroundColor = "hsl(var(--destructive))";
                            option.style.color = "white";
                            
                            gameData.points.insight += 1;
                            
                            // Show correct answer
                            emotionOptionsElements.forEach(opt => {
                                if (opt.dataset.emotion === situation.correctEmotion) {
                                    opt.classList.add('correct');
                                    opt.style.backgroundColor = "hsl(var(--success))";
                                    opt.style.color = "white";
                                }
                            });
                            
                            const feedbackDiv = document.createElement('div');
                            feedbackDiv.className = 'feedback-negative';
                            feedbackDiv.innerHTML = `
                                <p style="color: hsl(var(--destructive));">${lang === 'ar' ? '❌ ليس صحيحًا. الشعور المناسب هو' : '❌ Not correct. The appropriate emotion is'} "${situation.correctEmotion}".</p>
                                <p>${situation.explanation}</p>
                                <p>${lang === 'ar' ? 'حاول مرة أخرى!' : 'Try again!'}</p>
                            `;
                            
                            gameFeedback.innerHTML = '';
                            gameFeedback.appendChild(feedbackDiv);
                            gameFeedback.style.display = 'block';
                            
                            updatePointsDisplay();
                            
                            // Remove incorrect class after delay to allow retry
                            setTimeout(() => {
                                option.classList.remove('incorrect');
                                option.style.backgroundColor = "";
                                option.style.color = "";
                                
                                emotionOptionsElements.forEach(opt => {
                                    if (opt.dataset.emotion === situation.correctEmotion) {
                                        opt.classList.remove('correct');
                                        opt.style.backgroundColor = "";
                                        opt.style.color = "";
                                    }
                                });
                                
                                gameFeedback.style.display = 'none';
                            }, 2000);
                        }
                    });
                });
            }
        }, 100);
    }
    
    function endGame() {
        const successDiv = document.createElement('div');
        successDiv.className = 'feedback-positive';
        successDiv.innerHTML = lang === 'ar' ? 
            '🎉 ممتاز! لقد ساعدت التماثيل على التعبير عن مشاعرها. الحديقة تعود للحياة بألوان زاهية ومشاعر متنوعة.' : 
            '🎉 Excellent! You\'ve helped the statues express their emotions. The garden is coming back to life with vibrant colors and diverse emotions.';
        gameFeedback.innerHTML = '';
        gameFeedback.appendChild(successDiv);
        gameFeedback.style.display = 'block';
        
        // Add bonus points
        gameData.points.hope += 15;
        gameData.points.insight += 10;
        updatePointsDisplay();
        
        // إخفاء زر إكمال الفصل إذا كان ظاهر من قبل
        if (completeChapterBtn) {
            completeChapterBtn.style.display = 'none';
        }
        
        // إنشاء زر إكمال الفصل الجديد إذا لم يكن موجود
        if (!completeChapterBtn) {
            completeChapterBtn = document.createElement('button');
            completeChapterBtn.className = 'btn btn-primary';
            completeChapterBtn.id = 'complete-chapter-btn';
            completeChapterBtn.innerHTML = lang === 'ar' ? ' إكمال الفصل' : ' Complete Chapter';
            completeChapterBtn.addEventListener('click', completeChapter);
        }
        
        // إضافة زر إكمال الفصل بعد الرسالة النهائية
        setTimeout(() => {
            // إضافة الزر إلى الواجهة
            gameFeedback.appendChild(document.createElement('br'));
            gameFeedback.appendChild(document.createElement('br'));
            gameFeedback.appendChild(completeChapterBtn);
            
            // إظهار الزر
            completeChapterBtn.style.display = 'block';
            
            // إضافة بعض التباعد
            completeChapterBtn.style.marginTop = '20px';
            completeChapterBtn.style.padding = '12px 24px';
            completeChapterBtn.style.fontSize = '1.1rem';
            
            // تحديث النص حسب اللغة
            completeChapterBtn.innerHTML = lang === 'ar' ? 
                ' إكمال الفصل ' : 
                ' Complete Chapter';
        }, 1000);
        
        gameCompleted = true;
    }
    
    displaySituation();
    
    console.log("Emotion recognition game setup complete with proper turn system and complete chapter button");
}


// Set up routine building game (Chapter 2) - معدل مع نظام الأدوار الصحيح
function setupRoutineBuildingGame(chapter) {
    const lang = gameData.player.language;
    
    console.log("Setting up routine building game");
    
    const tasks = lang === 'ar' ? [
        { name: "إضاءة المصابيح", type: "correct", icon: "fas fa-lightbulb", explanation: "هذا يساعد في إضاءة القرية وجعلها أكثر ترحيبًا." },
        { name: "إطعام الطيور", type: "correct", icon: "fas fa-dove", explanation: "رعاية الكائنات الحية يجلب الحياة إلى القرية." },
        { name: "إصلاح الساعات", type: "correct", icon: "fas fa-clock", explanation: "إصلاح الساعات يساعد في استعادة إحساس الزمن." },
        { name: "تنظيف الشوارع", type: "correct", icon: "fas fa-broom", explanation: "النظافة تجعل القرية مكانًا أكثر صحة للعيش." },
        { name: "رمي القمامة على الأرض", type: "wrong", icon: "fas fa-trash", explanation: "هذا يجعل القرية قذرة وغير مرتبة." },
        { name: "تكسير الزجاج", type: "wrong", icon: "fas fa-times-circle", explanation: "التخريب لا يساعد في استعادة الحياة إلى القرية." },
        { name: "إهمال العمل", type: "wrong", icon: "fas fa-bed", explanation: "الإهمال لا يبني الزخم اللازم لاستعادة الحياة." },
        { name: "إهمال الجيران", type: "wrong", icon: "fas fa-user-slash", explanation: "التواصل الاجتماعي مهم لاستعادة الحياة للقرية." }
    ] : [
        { name: "Light Lamps", type: "correct", icon: "fas fa-lightbulb", explanation: "This helps illuminate the village and make it more welcoming." },
        { name: "Feed Birds", type: "correct", icon: "fas fa-dove", explanation: "Caring for living beings brings life to the village." },
        { name: "Fix Clocks", type: "correct", icon: "fas fa-clock", explanation: "Fixing clocks helps restore a sense of time." },
        { name: "Clean Streets", type: "correct", icon: "fas fa-broom", explanation: "Cleanliness makes the village a healthier place to live." },
        { name: "Throw Trash on Ground", type: "wrong", icon: "fas fa-trash", explanation: "This makes the village dirty and untidy." },
        { name: "Break Glass", type: "wrong", icon: "fas fa-times-circle", explanation: "Vandalism doesn't help restore life to the village." },
        { name: "Neglect Work", type: "wrong", icon: "fas fa-bed", explanation: "Neglect doesn't build the momentum needed to restore life." },
        { name: "Ignore Neighbors", type: "wrong", icon: "fas fa-user-slash", explanation: "Social connection is important to restore life to the village." }
    ];
    
    // Shuffle tasks
    const shuffledTasks = [...tasks].sort(() => Math.random() - 0.5);
    let correctTasks = 0;
    let totalCorrectTasks = 4; // There are 4 correct tasks
    let selectedTasks = [];
    let companionTurn = gameData.player.mode === "group";
    let playerTurn = !companionTurn;
    let gameCompleted = false;
    
    gameMechanics.innerHTML = `
        ${companionTurn ? `
        <div class="companion-turn">
            <div class="companion-name">${gameData.player.companion.name[lang]}:</div>
            <p>${lang === 'ar' ? 'دعنا نعمل معًا لاستعادة الطاقة إلى القرية! سأبدأ أولاً.' : "Let's work together to restore energy to the village! I'll start first."}</p>
        </div>
        ` : ''}
        <div class="game-instructions">
            <p>${lang === 'ar' ? 'اختر المهام التي تساعد في استعادة الطاقة إلى القرية:' : 'Choose tasks that help restore energy to the village:'}</p>
            <p>${lang === 'ar' ? 'يجب تحديد جميع المهام الصحيحة (4 مهام) لإكمال الفصل.' : 'You must identify all correct tasks (4 tasks) to complete the chapter.'}</p>
        </div>
        <div class="progress-bar">
            <div class="progress-fill" id="routine-progress" style="width: ${(correctTasks / totalCorrectTasks) * 100}%"></div>
        </div>
        <div class="interactive-options">
            ${shuffledTasks.map((task, index) => `
                <div class="interactive-option" data-type="${task.type}" data-index="${index}" data-name="${task.name}">
                    <i class="${task.icon}" style="font-size: 1.8rem;"></i>
                    <span>${task.name}</span>
                </div>
            `).join('')}
        </div>
        <div class="progress-info" style="margin-top: 15px; text-align: center;">
            <p>${lang === 'ar' ? `تم تحديد ${correctTasks} من ${totalCorrectTasks} مهام صحيحة` : `Selected ${correctTasks} of ${totalCorrectTasks} correct tasks`}</p>
        </div>
    `;
    
    // Function for companion to play
    function companionPlay() {
        if (!companionTurn || gameCompleted) return;
        
        setTimeout(() => {
            const correctTasksElements = Array.from(document.querySelectorAll('.interactive-option[data-type="correct"]:not([data-completed="true"])'));
            if (correctTasksElements.length > 0) {
                const firstCorrectTask = correctTasksElements[0];
                const taskName = firstCorrectTask.dataset.name;
                const task = tasks.find(t => t.name === taskName);
                
                // Show companion response
                const companionResponse = document.createElement('div');
                companionResponse.className = 'companion-answer';
                companionResponse.innerHTML = `
                    <div class="companion-name">${gameData.player.companion.name[lang]}:</div>
                    <p>${lang === 'ar' ? 'أعتقد أن' : 'I think'} "${taskName}" ${lang === 'ar' ? 'مهمة صحيحة! ' : 'is a correct task! '} ${task.explanation}</p>
                `;
                gameMechanics.insertBefore(companionResponse, gameMechanics.querySelector('.interactive-options'));
                
                firstCorrectTask.style.backgroundColor = "hsl(var(--success))";
                firstCorrectTask.style.color = "white";
                firstCorrectTask.dataset.completed = "true";
                selectedTasks.push(taskName);
                correctTasks++;
                
                // Update progress
                const progressFill = document.getElementById('routine-progress');
                progressFill.style.width = `${(correctTasks / totalCorrectTasks) * 100}%`;
                
                // Update progress info
                document.querySelector('.progress-info p').textContent = 
                    lang === 'ar' ? 
                    `تم تحديد ${correctTasks} من ${totalCorrectTasks} مهام صحيحة` :
                    `Selected ${correctTasks} of ${totalCorrectTasks} correct tasks`;
                
                gameData.points.hope += 5;
                gameData.points.insight += 3;
                updatePointsDisplay();
                
                // Check if game is complete
                if (correctTasks === totalCorrectTasks) {
                    endGame();
                } else {
                    // Switch turns
                    companionTurn = false;
                    playerTurn = true;
                    
                    // Show turn indicator
                    const turnIndicator = document.createElement('div');
                    turnIndicator.className = 'turn-indicator';
                    turnIndicator.innerHTML = lang === 'ar' ? 'الآن دورك! اختر مهمة صحيحة.' : 'Now your turn! Choose a correct task.';
                    gameMechanics.insertBefore(turnIndicator, gameMechanics.querySelector('.interactive-options'));
                }
            }
        }, 1500);
    }
    
    // Start with companion if it's companion's turn
    if (companionTurn && gameData.player.mode === "group") {
        companionPlay();
    }
    
    const taskOptions = document.querySelectorAll('.interactive-option');
    
    taskOptions.forEach(option => {
        option.addEventListener('click', function() {
            if (!playerTurn || this.dataset.completed || gameCompleted) return;
            
            const taskType = this.dataset.type;
            const taskName = this.dataset.name;
            const task = tasks.find(t => t.name === taskName);
            
            if (taskType === 'correct') {
                // Correct task
                this.style.backgroundColor = "hsl(var(--success))";
                this.style.color = "white";
                this.dataset.completed = "true";
                selectedTasks.push(taskName);
                correctTasks++;
                
                // Update progress
                const progressFill = document.getElementById('routine-progress');
                progressFill.style.width = `${(correctTasks / totalCorrectTasks) * 100}%`;
                
                // Update progress info
                document.querySelector('.progress-info p').textContent = 
                    lang === 'ar' ? 
                    `تم تحديد ${correctTasks} من ${totalCorrectTasks} مهام صحيحة` :
                    `Selected ${correctTasks} of ${totalCorrectTasks} correct tasks`;
                
                gameData.points.hope += 5;
                gameData.points.insight += 3;
                
                // Show positive feedback
                const feedbackDiv = document.createElement('div');
                feedbackDiv.className = 'feedback-positive';
                feedbackDiv.innerHTML = lang === 'ar' ? 
                    `🎉 ممتاز! "${taskName}" مهمة صحيحة. ${task.explanation}` : 
                    `🎉 Excellent! "${taskName}" is a correct task. ${task.explanation}`;
                gameFeedback.innerHTML = '';
                gameFeedback.appendChild(feedbackDiv);
                gameFeedback.style.display = 'block';
                
                // Show companion encouragement (only in group mode)
                if (gameData.player.mode === "group") {
                    showCompanionMessage('encouragement');
                }
            } else {
                // Wrong task
                this.style.backgroundColor = "hsl(var(--destructive))";
                this.style.color = "white";
                gameData.points.insight += 1;
                
                const feedbackDiv = document.createElement('div');
                feedbackDiv.className = 'feedback-negative';
                feedbackDiv.innerHTML = lang === 'ar' ? 
                    `❌ "${taskName}" ليس تصرفًا صحيحًا. ${task.explanation} حاول مرة أخرى!` : 
                    `❌ "${taskName}" is not correct behavior. ${task.explanation} Try again!`;
                gameFeedback.innerHTML = '';
                gameFeedback.appendChild(feedbackDiv);
                gameFeedback.style.display = 'block';
                
                setTimeout(() => {
                    this.style.backgroundColor = "";
                    this.style.color = "";
                    gameFeedback.style.display = 'none';
                }, 2000);
                
                updatePointsDisplay();
                return;
            }
            
            updatePointsDisplay();
            
            // Check if all correct tasks have been selected
            if (correctTasks === totalCorrectTasks) {
                endGame();
            } else {
                // In group mode, alternate turns
                if (gameData.player.mode === "group") {
                    playerTurn = false;
                    companionTurn = true;
                    
                    // Companion's turn after a delay
                    setTimeout(() => {
                        companionPlay();
                    }, 2000);
                }
                
                setTimeout(() => {
                    gameFeedback.style.display = 'none';
                }, 2000);
            }
        });
    });
    
    function endGame() {
        gameCompleted = true;
        const successDiv = document.createElement('div');
        successDiv.className = 'feedback-positive';
        successDiv.innerHTML = lang === 'ar' ? 
            '🎉 ممتاز! لقد استعدت الحياة للقرية. الألوان تعود والشوارع تمتلئ بالحركة.' : 
            '🎉 Excellent! You restored life to the village. Colors are returning and streets are filling with movement.';
        gameFeedback.innerHTML = '';
        gameFeedback.appendChild(successDiv);
        gameFeedback.style.display = 'block';
        
        // Add bonus points
        gameData.points.hope += 10;
        gameData.points.insight += 5;
        updatePointsDisplay();
        
        // Show complete chapter button after a delay
        setTimeout(() => {
            completeChapterBtn.style.display = 'block';
        }, 2000);
    }
    
    console.log("Routine building game setup complete");
}



// Set up communication game (Chapter 3) - معدل مع نظام الأدوار الصحيح
function setupCommunicationGame(chapter) {
    const lang = gameData.player.language;
    
    console.log("Setting up communication game");

 // game 3
    
    const prompts = lang === 'ar' ? [
        { 
            prompt: "كيف تشعر اليوم؟", 
            responses: [
                { text: "أشعر بالقلق قليلاً", type: "brief", correct: false, explanation: "هذه إجابة مختصرة جدًا." },
                { text: "أشعر بالقلق لأنني لست متأكدًا مما سيحدث لاحقًا، لكنني أحاول أن أبقى إيجابيًا", type: "descriptive", correct: true, explanation: "هذه إجابة تعبيرية وعميقة." },
                { text: "لا أعرف", type: "brief", correct: false, explanation: "هذه إجابة مختصرة جدًا." },
                { text: "أشعر بالقلق والتوتر، لكنني أعلم أن هذه المشاعر مؤقتة وسوف تتحسن", type: "descriptive", correct: true, explanation: "هذه إجابة تعبيرية وعميقة." }
            ],
            requiredCorrect: 2,
            explanation: "الإجابات التعبيرية والعميقة تساعد في التواصل الفعال وتثري المحادثة."
        },
        { 
            prompt: "ما الذي يجعلك سعيدًا؟", 
            responses: [
                { text: "الأشياء الجيدة", type: "brief", correct: false, explanation: "هذه إجابة عامة جدًا." },
                { text: "الوقت الذي أقضيه مع أحبائي، والأشياء الصغيرة التي تجعل يومي مميزًا", type: "descriptive", correct: true, explanation: "هذه إجابة تفصيلية وعاطفية." },
                { text: "لا شيء", type: "brief", correct: false, explanation: "هذه إجابة سلبية ومختصرة." },
                { text: "رؤية الآخرين سعداء، وتحقيق أهدافي الصغيرة يوميًا", type: "descriptive", correct: true, explanation: "هذه إجابة تفصيلية وعاطفية." }
            ],
            requiredCorrect: 2,
            explanation: "التعبير عن المشاعر بتفصيل يساعد في بناء اتصال عاطفي أقوى."
        }
    ] : [
        { 
            prompt: "How are you feeling today?", 
            responses: [
                { text: "A bit anxious", type: "brief", correct: false, explanation: "This is a very brief answer." },
                { text: "I feel a bit anxious because I'm not sure what will happen later, but I'm trying to stay positive", type: "descriptive", correct: true, explanation: "This is an expressive and deep answer." },
                { text: "I don't know", type: "brief", correct: false, explanation: "This is a very brief answer." },
                { text: "I feel anxious and tense, but I know these feelings are temporary and will improve", type: "descriptive", correct: true, explanation: "This is an expressive and deep answer." }
            ],
            requiredCorrect: 2,
            explanation: "Expressive and deep answers help with effective communication and enrich the conversation."
        },
        { 
            prompt: "What makes you happy?", 
            responses: [
                { text: "Good things", type: "brief", correct: false, explanation: "This answer is too general." },
                { text: "The time I spend with loved ones, and the small things that make my day special", type: "descriptive", correct: true, explanation: "This is a detailed and emotional answer." },
                { text: "Nothing", type: "brief", correct: false, explanation: "This is a negative and brief answer." },
                { text: "Seeing others happy, achieving my small goals daily", type: "descriptive", correct: true, explanation: "This is a detailed and emotional answer." }
            ],
            requiredCorrect: 2,
            explanation: "Expressing feelings in detail helps build stronger emotional connections."
        }
    ];
    
    let currentPrompt = 0;
    let companionTurn = gameData.player.mode === "group";
    let selectedOptions = [];
    let selectedCorrect = 0;
    let gameCompleted = false;
    
    function displayPrompt() {
        if (currentPrompt >= prompts.length) {
            const successDiv = document.createElement('div');
            successDiv.className = 'feedback-positive';
            successDiv.innerHTML = lang === 'ar' ? 
                '🎉 ممتاز! لقد تعلمت كيفية التواصل بشكل أكثر تعبيرًا. الأصداء أصبحت أكثر ثراءً وعمقًا وتستجيب بمشاعر حقيقية.' : 
                '🎉 Excellent! You\'ve learned how to communicate more expressively. The echoes have become richer and deeper, responding with genuine emotions.';
            gameFeedback.innerHTML = '';
            gameFeedback.appendChild(successDiv);
            gameFeedback.style.display = 'block';
            
            // Add bonus points
            gameData.points.hope += 15;
            gameData.points.insight += 10;
            updatePointsDisplay();
            
            setTimeout(() => {
                completeChapterBtn.style.display = 'block';
            }, 2000);
            return;
        }
        
        const prompt = prompts[currentPrompt];
        selectedOptions = [];
        selectedCorrect = 0;
        
        gameMechanics.innerHTML = `
            ${companionTurn ? `
            <div class="companion-turn">
                <div class="companion-name">${gameData.player.companion.name[lang]}:</div>
                <p>${lang === 'ar' ? 'دعنا نتواصل مع الأصداء معًا! سأبدأ أولاً.' : "Let's communicate with the echoes together! I'll start first."}</p>
            </div>
            ` : ''}
            <div class="game-instructions">
                <p><strong>${lang === 'ar' ? 'الصدى يسأل:' : 'The echo asks:'}</strong> "${prompt.prompt}"</p>
                <p>${lang === 'ar' ? `اختر ${prompt.requiredCorrect} ردود تعبيرية وعميقة:` : `Choose ${prompt.requiredCorrect} expressive and deep responses:`}</p>
                <p>${lang === 'ar' ? 'يمكنك اختيار أكثر من إجابة.' : 'You can select multiple answers.'}</p>
            </div>
            <div class="interactive-options">
                ${prompt.responses.map((response, index) => `
                    <div class="interactive-option" data-correct="${response.correct}" data-index="${index}">
                        <span>"${response.text}"</span>
                    </div>
                `).join('')}
            </div>
            <div class="progress-info" style="margin-top: 15px; text-align: center;">
                <p>${lang === 'ar' ? `تم اختيار ${selectedCorrect} من ${prompt.requiredCorrect} إجابات صحيحة` : `Selected ${selectedCorrect} of ${prompt.requiredCorrect} correct answers`}</p>
            </div>
            <button class="btn" id="check-answers" style="margin-top: 15px;">${lang === 'ar' ? 'تحقق من الإجابات' : 'Check Answers'}</button>
        `;
        
        // Function for companion to play in group mode
        function companionPlay() {
            if (!companionTurn || gameData.player.mode !== "group" || gameCompleted) return;
            
            setTimeout(() => {
                // Find correct answers
                const correctIndices = prompt.responses
                    .map((response, idx) => response.correct ? idx : -1)
                    .filter(idx => idx !== -1)
                    .slice(0, 1); // Companion selects one correct answer
                
                // Show companion response
                const companionResponse = document.createElement('div');
                companionResponse.className = 'companion-answer';
                const companionAnswers = correctIndices.map(idx => prompt.responses[idx].text).join(' و ');
                companionResponse.innerHTML = `
                    <div class="companion-name">${gameData.player.companion.name[lang]}:</div>
                    <p>${lang === 'ar' ? 'أعتقد أن' : 'I think'} "${companionAnswers}" ${lang === 'ar' ? 'هي إجابة تعبيرية. الآن دورك!' : 'is an expressive answer. Now your turn!'}</p>
                `;
                gameMechanics.insertBefore(companionResponse, gameMechanics.querySelector('.interactive-options'));
                
                // Automatically select the correct answer for companion
                correctIndices.forEach(correctIndex => {
                    const optionElement = document.querySelector(`.interactive-option[data-index="${correctIndex}"]`);
                    if (optionElement) {
                        optionElement.style.backgroundColor = "hsl(var(--success))";
                        optionElement.style.color = "white";
                        optionElement.dataset.completed = "true";
                        selectedOptions.push(correctIndex);
                        selectedCorrect++;
                    }
                });
                
                // Update progress info
                document.querySelector('.progress-info p').textContent = 
                    lang === 'ar' ? 
                    `تم اختيار ${selectedCorrect} من ${prompt.requiredCorrect} إجابات صحيحة` :
                    `Selected ${selectedCorrect} of ${prompt.requiredCorrect} correct answers`;
                
                gameData.points.hope += 4;
                gameData.points.insight += 3;
                updatePointsDisplay();
                
                // Switch turns
                companionTurn = false;
                
                // Show turn indicator
                const turnIndicator = document.createElement('div');
                turnIndicator.className = 'turn-indicator';
                turnIndicator.innerHTML = lang === 'ar' ? 'الآن دورك! اختر إجابة تعبيرية.' : 'Now your turn! Choose an expressive answer.';
                gameMechanics.insertBefore(turnIndicator, gameMechanics.querySelector('.interactive-options'));
                
            }, 2000);
        }
        
        // Start with companion if it's companion's turn
        if (companionTurn && gameData.player.mode === "group") {
            companionPlay();
        }
        
        const responseOptions = document.querySelectorAll('.interactive-option');
        const checkBtn = document.getElementById('check-answers');
        const progressInfo = document.querySelector('.progress-info p');
        
        responseOptions.forEach(option => {
            option.addEventListener('click', function() {
                // Don't allow clicking if option is already selected by companion
                if (this.dataset.completed === "true") return;
                // Don't allow clicking if companion is playing
                if (companionTurn && gameData.player.mode === "group") return;
                if (gameCompleted) return;
                
                const isCorrect = this.dataset.correct === 'true';
                const index = parseInt(this.dataset.index);
                
                if (selectedOptions.includes(index)) {
                    // Deselect
                    this.style.backgroundColor = "";
                    this.style.color = "";
                    selectedOptions = selectedOptions.filter(i => i !== index);
                    if (isCorrect) selectedCorrect--;
                } else {
                    // Select
                    this.style.backgroundColor = isCorrect ? "hsl(var(--primary) / 0.3)" : "hsl(var(--destructive) / 0.3)";
                    selectedOptions.push(index);
                    if (isCorrect) selectedCorrect++;
                }
                
                // Update progress info
                progressInfo.textContent = 
                    lang === 'ar' ? 
                    `تم اختيار ${selectedCorrect} من ${prompt.requiredCorrect} إجابات صحيحة` :
                    `Selected ${selectedCorrect} of ${prompt.requiredCorrect} correct answers`;
            });
        });
        
        checkBtn.addEventListener('click', function() {
            if (selectedCorrect === prompt.requiredCorrect && selectedOptions.length === prompt.requiredCorrect) {
                // Mark all selected options
                responseOptions.forEach(option => {
                    const index = parseInt(option.dataset.index);
                    if (selectedOptions.includes(index)) {
                        const isCorrect = option.dataset.correct === 'true';
                        if (isCorrect) {
                            option.style.backgroundColor = "hsl(var(--success))";
                            option.style.color = "white";
                        }
                    }
                });
                
                const feedbackDiv = document.createElement('div');
                feedbackDiv.className = 'feedback-positive';
                feedbackDiv.innerHTML = lang === 'ar' ? 
                    `🎉 ممتاز! لقد اخترت ${prompt.requiredCorrect} إجابات تعبيرية. ${prompt.explanation}` : 
                    `🎉 Excellent! You selected ${prompt.requiredCorrect} expressive responses. ${prompt.explanation}`;
                gameFeedback.innerHTML = '';
                gameFeedback.appendChild(feedbackDiv);
                gameFeedback.style.display = 'block';
                
                gameData.points.hope += 8;
                gameData.points.insight += 6;
                updatePointsDisplay();
                
                // Show companion encouragement (only in group mode)
                if (gameData.player.mode === "group") {
                    showCompanionMessage('encouragement');
                }
                
                currentPrompt++;
                if (gameData.player.mode === "group") {
                    companionTurn = true;
                }
                
                setTimeout(() => {
                    gameFeedback.style.display = 'none';
                    displayPrompt();
                }, 2000);
            } else {
                // Mark correct and incorrect answers
                responseOptions.forEach(option => {
                    const index = parseInt(option.dataset.index);
                    const isCorrect = option.dataset.correct === 'true';
                    
                    if (selectedOptions.includes(index)) {
                        if (isCorrect) {
                            option.style.backgroundColor = "hsl(var(--success))";
                            option.style.color = "white";
                        } else {
                            option.style.backgroundColor = "hsl(var(--destructive))";
                            option.style.color = "white";
                        }
                    } else if (isCorrect) {
                        option.style.backgroundColor = "hsl(var(--success) / 0.3)";
                    }
                });
                
                const feedbackDiv = document.createElement('div');
                feedbackDiv.className = 'feedback-negative';
                feedbackDiv.innerHTML = lang === 'ar' ? 
                    `❌ تحتاج إلى اختيار ${prompt.requiredCorrect} إجابات تعبيرية صحيحة. حاول مرة أخرى!` : 
                    `❌ You need to select ${prompt.requiredCorrect} correct expressive answers. Try again!`;
                gameFeedback.innerHTML = '';
                gameFeedback.appendChild(feedbackDiv);
                gameFeedback.style.display = 'block';
                
                gameData.points.insight += 2;
                updatePointsDisplay();
                
                // Reset after delay
                setTimeout(() => {
                    gameFeedback.style.display = 'none';
                    selectedOptions = [];
                    selectedCorrect = 0;
                    responseOptions.forEach(opt => {
                        if (opt.dataset.completed !== "true") {
                            opt.style.backgroundColor = "";
                            opt.style.color = "";
                        }
                    });
                    progressInfo.textContent = 
                        lang === 'ar' ? 
                        `تم اختيار ${selectedCorrect} من ${prompt.requiredCorrect} إجابات صحيحة` :
                        `Selected ${selectedCorrect} of ${prompt.requiredCorrect} correct answers`;
                }, 2000);
            }
        });
    }
    
    displayPrompt();
    
    console.log("Communication game setup complete");
}


// ================================================
// الجزء الثالث: ألعاب الفصول 5-8
// ================================================

// Chapter 5


function setupMemoryGame(chapter) {
    const lang = gameData.player.language;
    
    console.log("Setting up memory game for chapter 5");
    
    // دالة واحدة لتوليد التسلسل - من الكود الأول
    const generateSequence = (length) => {
        const notes = ["C", "D", "E", "F", "G", "A", "B"];
        const sequence = [];
        for (let i = 0; i < length; i++) {
            sequence.push(notes[Math.floor(Math.random() * notes.length)]);
        }
        return sequence;
    };
    
    // إنشاء 3 تسلسلات - من الكود الأول
    const sequences = [
        { 
            notes: generateSequence(3),
            name: lang === 'ar' ? "التسلسل الأول" : "First Sequence",
            color: "hsl(160, 60%, 40%)"
        },
        { 
            notes: generateSequence(4),
            name: lang === 'ar' ? "التسلسل الثاني" : "Second Sequence", 
            color: "hsl(210, 60%, 45%)"
        },
        { 
            notes: generateSequence(5),
            name: lang === 'ar' ? "التسلسل الثالث" : "Third Sequence",
            color: "hsl(280, 50%, 45%)"
        }
    ];
    
    let currentSequence = 0;
    let playerSequence = [];
    let showingSequence = true;
    let companionTurn = gameData.player.mode === "group";
    let playerTurn = !companionTurn;
    let gameCompleted = false;
    let sequenceCompleted = false;
    let currentAttempt = 0;
    const maxAttemptsPerSequence = 3; // الحد الأقصى للمحاولات لكل تسلسل
    
    // نسخ من التسلسلات الأصلية للحفاظ عليها ثابتة
    const originalSequences = JSON.parse(JSON.stringify(sequences));
    
    function displaySequence() {
        if (gameCompleted) return;
        
        if (currentSequence >= sequences.length) {
            // ✅ هنا رجعت لطريقة الكود الأول في إكمال الفصل
            const successDiv = document.createElement('div');
            successDiv.className = 'feedback-positive';
            successDiv.innerHTML = lang === 'ar' ? 
                'رائع! لقد اكتشفت الفرح في الموسيقى. البحيرة تتألق بالألوان والنغمات الجميلة.' : 
                'Wonderful! You\'ve discovered joy in music. The lake is glowing with colors and beautiful melodies.';
            gameFeedback.innerHTML = '';
            gameFeedback.appendChild(successDiv);
            gameFeedback.style.display = 'block';
            
            // Show complete chapter button after a delay - من الكود الأول
            setTimeout(() => {
                if (completeChapterBtn) {
                    completeChapterBtn.style.display = 'block';
                }
            }, 3000);
            
            gameCompleted = true;
            return;
        }
        
        // إعادة تعيين محاولات التسلسل الحالي
        if (currentAttempt === 0) {
            // نسخ التسلسل الأصلي
            sequences[currentSequence].notes = [...originalSequences[currentSequence].notes];
        }
        
        const sequence = sequences[currentSequence];
        playerSequence = [];
        showingSequence = true;
        sequenceCompleted = false;
        playerTurn = !companionTurn;
        currentAttempt++;
        
        const displayNotes = [...sequence.notes];
        
        gameMechanics.innerHTML = `
            ${companionTurn ? `
            <div class="companion-turn" style="background: ${sequence.color}15; padding: 12px; border-radius: 10px; margin-bottom: 15px; border-left: 4px solid ${sequence.color};">
                <div style="color: ${sequence.color}; font-weight: bold; margin-bottom: 5px;">${gameData.player.companion.name[lang]}:</div>
                <p style="margin: 0; color: hsl(var(--foreground));">${lang === 'ar' ? 'سأبدأ أولاً!' : "I'll start first!"}</p>
            </div>
            ` : ''}
            
            ${!companionTurn && gameData.player.mode === "group" ? `
            <div class="turn-indicator" style="background: hsl(var(--accent)/0.1); padding: 12px; border-radius: 10px; margin-bottom: 15px; border-left: 4px solid hsl(var(--accent));">
                <div style="color: hsl(var(--accent)); font-weight: bold; margin-bottom: 5px;">${lang === 'ar' ? 'دورك الآن!' : 'Your Turn!'}</div>
                <p style="margin: 0; color: hsl(var(--foreground));">${lang === 'ar' ? 'الآن دورك! أعد إنشاء التسلسل.' : 'Now your turn! Recreate the sequence.'}</p>
            </div>
            ` : ''}
            
            <div class="game-instructions" style="background: hsl(var(--card)); padding: 15px; border-radius: 10px; margin-bottom: 15px; border: 1px solid hsl(var(--border));">
                <p style="margin: 0 0 8px 0; font-size: 1.1rem;">
                    <strong style="color: ${sequence.color};">${sequence.name}</strong>
                    <span style="color: hsl(var(--muted-foreground)); font-size: 0.9rem; margin-right: 10px;">(${lang === 'ar' ? 'تسلسل' : 'Sequence'} ${currentSequence + 1}/${sequences.length})</span>
                </p>
                <p style="margin: 0; font-weight: 500;">${lang === 'ar' ? 'شاهد تسلسل النغمات ثم أعد إنشائه:' : 'Watch the sequence of notes then recreate it:'}</p>
                ${currentAttempt > 1 ? `
                <p style="margin: 8px 0 0 0; font-size: 0.9rem; color: hsl(var(--accent));">
                    ${lang === 'ar' ? `محاولة ${currentAttempt}/${maxAttemptsPerSequence}` : `Attempt ${currentAttempt}/${maxAttemptsPerSequence}`}
                </p>
                ` : ''}
            </div>
            
            <div class="sequence-display-container" style="margin-bottom: 20px;">
                <p style="margin: 0 0 10px 0; color: hsl(var(--muted-foreground)); font-size: 0.9rem; text-align: center;">
                    ${lang === 'ar' ? 'تسلسل النغمات:' : 'Note sequence:'}
                </p>
                <div class="interactive-options" id="sequence-display" style="display: flex; flex-wrap: wrap; gap: 8px; justify-content: center;">
                    ${displayNotes.map((note, index) => `
                        <div class="interactive-option sequence-note" data-note="${note}" data-index="${index}" style="
                            background: ${sequence.color};
                            color: white;
                            border-radius: 10px;
                            padding: 12px 15px;
                            min-width: 60px;
                            text-align: center;
                            cursor: pointer;
                            transition: all 0.2s ease;
                            box-shadow: 0 3px 6px rgba(0,0,0,0.15);
                            font-weight: 500;
                            opacity: 0.8;
                        ">
                            <span style="font-size: 1.5rem; display: block;">${note}</span>
                        </div>
                    `).join('')}
                </div>
            </div>
            
            <div id="player-sequence" style="margin: 15px 0; padding: 12px; background: hsl(var(--muted)); border-radius: 10px; display: none;">
                <p style="margin: 0 0 8px 0; color: hsl(var(--foreground)); font-weight: 500;">${lang === 'ar' ? 'تسلسلك:' : 'Your sequence:'}</p>
                <div style="background: hsl(var(--card)); padding: 10px; border-radius: 8px; border: 1px solid hsl(var(--border)); min-height: 24px;">
                    <span id="player-notes-display" style="font-weight: 500; font-size: 1.1rem; color: ${sequence.color};">
                        ${lang === 'ar' ? 'لم يتم اختيار أي نغمات بعد' : 'No notes selected yet'}
                    </span>
                </div>
            </div>
            
            <div style="margin-top: 20px; display: flex; gap: 8px; justify-content: center; flex-wrap: wrap;" id="buttons-container">
                ${!companionTurn || gameData.player.mode !== "group" ? `
                <button class="btn" id="start-sequence" style="background: ${sequence.color}; border-color: ${sequence.color}; padding: 10px 20px;">
                    ${lang === 'ar' ? 'ابدأ العرض' : 'Start Display'}
                </button>
                ` : ''}
                <button class="btn" id="check-sequence" style="display: none; background: hsl(140, 60%, 40%); border-color: hsl(140, 60%, 40%); padding: 10px 20px;">
                    ${lang === 'ar' ? 'تحقق' : 'Check'}
                </button>
                <button class="btn btn-secondary" id="reset-sequence" style="display: none; padding: 10px 20px;">
                    ${lang === 'ar' ? 'إعادة' : 'Reset'}
                </button>
                <button class="btn btn-secondary" id="show-sequence-again" style="display: none; padding: 10px 20px;">
                    ${lang === 'ar' ? 'عرض التسلسل مرة أخرى' : 'Show Sequence Again'}
                </button>
            </div>
            
            <div style="margin-top: 15px; padding: 10px; background: hsl(var(--card)); border-radius: 8px; border: 1px solid hsl(var(--border));">
                <p style="margin: 0; color: hsl(var(--muted-foreground)); font-size: 0.9rem; text-align: center;">
                    ${lang === 'ar' ? 'انقر على النغمات بنفس الترتيب الذي ظهرت به' : 'Click on notes in the same order they appeared'}
                    ${gameData.player.mode === "group" ? 
                        `<br><span style="color: ${sequence.color}; font-weight: 500;">${lang === 'ar' ? 'دور' : 'Turn'}: ${companionTurn ? gameData.player.companion.name[lang] : lang === 'ar' ? 'اللاعب' : 'Player'}</span>` 
                        : ''}
                </p>
            </div>
        `;
        
        setTimeout(() => {
            const sequenceNotes = document.querySelectorAll('.sequence-note');
            const startSequenceBtn = document.getElementById('start-sequence');
            const checkSequenceBtn = document.getElementById('check-sequence');
            const resetSequenceBtn = document.getElementById('reset-sequence');
            const showSequenceAgainBtn = document.getElementById('show-sequence-again');
            const buttonsContainer = document.getElementById('buttons-container');
            
            // Function to show the sequence with visual effects
            function showSequence(showButtons = true) {
                let delay = 0;
                
                // إعادة تعيين أي تسلسل سابق
                playerSequence = [];
                document.getElementById('player-notes-display').textContent = 
                    lang === 'ar' ? 'لم يتم اختيار أي نغمات بعد' : 'No notes selected yet';
                
                // إخفاء زر "عرض التسلسل مرة أخرى" مؤقتاً
                if (showSequenceAgainBtn) {
                    showSequenceAgainBtn.style.display = 'none';
                }
                
                // توليد تسلسل عرض جديد عشوائي (ولكن يحافظ على نفس النغمات)
                const displayOrder = [...displayNotes];
                if (currentAttempt > 1) {
                    // خلط ترتيب العرض فقط، ليس النغمات نفسها
                    for (let i = displayOrder.length - 1; i > 0; i--) {
                        const j = Math.floor(Math.random() * (i + 1));
                        [displayOrder[i], displayOrder[j]] = [displayOrder[j], displayOrder[i]];
                    }
                }
                
                // إعادة ترتيب العناصر المرئية
                const sequenceDisplay = document.getElementById('sequence-display');
                sequenceDisplay.innerHTML = displayOrder.map((note, index) => `
                    <div class="interactive-option sequence-note" data-note="${note}" data-index="${index}" style="
                        background: ${sequence.color};
                        color: white;
                        border-radius: 10px;
                        padding: 12px 15px;
                        min-width: 60px;
                        text-align: center;
                        cursor: pointer;
                        transition: all 0.2s ease;
                        box-shadow: 0 3px 6px rgba(0,0,0,0.15);
                        font-weight: 500;
                        opacity: 0.8;
                    ">
                        <span style="font-size: 1.5rem; display: block;">${note}</span>
                    </div>
                `).join('');
                
                // إعادة ربط الأحداث
                const newSequenceNotes = document.querySelectorAll('.sequence-note');
                
                newSequenceNotes.forEach(option => {
                    option.addEventListener('click', () => {
                        if (showingSequence || !playerTurn) return;
                        
                        const note = option.dataset.note;
                        playerSequence.push(note);
                        document.getElementById('player-notes-display').textContent = playerSequence.join(' - ');
                    });
                });
                
                // عرض التسلسل مع تأثيرات
                newSequenceNotes.forEach(note => {
                    setTimeout(() => {
                        note.style.transform = "scale(1.15)";
                        note.style.boxShadow = "0 0 20px rgba(0,0,0,0.3)";
                        note.style.opacity = "1";
                        note.style.border = "2px solid white";
                        
                        playNoteSound(note.dataset.note);
                    }, delay);
                    
                    setTimeout(() => {
                        note.style.transform = "";
                        note.style.boxShadow = "0 3px 6px rgba(0,0,0,0.15)";
                        note.style.opacity = "0.8";
                        note.style.border = "none";
                    }, delay + 800);
                    
                    delay += 1000;
                });
                
                setTimeout(() => {
                    showingSequence = false;
                    document.getElementById('player-sequence').style.display = 'block';
                    
                    if (showButtons) {
                        if (startSequenceBtn) startSequenceBtn.style.display = 'none';
                        if (checkSequenceBtn) checkSequenceBtn.style.display = 'inline-block';
                        if (resetSequenceBtn) resetSequenceBtn.style.display = 'inline-block';
                        if (showSequenceAgainBtn) showSequenceAgainBtn.style.display = 'inline-block';
                    }
                    
                    // منطق الوضع الجماعي
                    if (companionTurn && gameData.player.mode === "group") {
                        setTimeout(() => {
                            playerSequence = [...displayNotes];
                            document.getElementById('player-notes-display').textContent = playerSequence.join(' - ');
                            
                            const companionResponse = document.createElement('div');
                            companionResponse.className = 'companion-answer';
                            companionResponse.innerHTML = `
                                <div style="background: ${sequence.color}10; padding: 10px; border-radius: 8px; margin: 10px 0; border-left: 3px solid ${sequence.color};">
                                    <div style="color: ${sequence.color}; font-weight: 500; margin-bottom: 3px;">${gameData.player.companion.name[lang]}:</div>
                                    <p style="margin: 0; color: hsl(var(--foreground)); font-size: 0.95rem;">
                                        ${lang === 'ar' ? 'التسلسل هو:' : 'The sequence is:'} 
                                        <span style="color: ${sequence.color}; font-weight: 500;">${displayNotes.join(' - ')}</span>. 
                                        ${lang === 'ar' ? 'الآن دورك' : 'Now your turn'}
                                    </p>
                                </div>
                            `;
                            gameMechanics.insertBefore(companionResponse, gameMechanics.querySelector('#player-sequence'));
                            
                            gameData.points.hope += 3;
                            gameData.points.insight += 5;
                            updatePointsDisplay();
                            
                            sequenceCompleted = true;
                            
                            setTimeout(() => {
                                companionTurn = false;
                                playerTurn = true;
                                currentAttempt = 0; // إعادة تعيين المحاولات للدور الجديد
                                displaySequence();
                            }, 2000);
                            
                        }, 1000);
                    }
                }, delay);
            }
            
            // منطق بدء التسلسل
            if (companionTurn && gameData.player.mode === "group") {
                setTimeout(() => {
                    showSequence(false);
                }, 1000);
            } else if (startSequenceBtn) {
                startSequenceBtn.addEventListener('click', () => showSequence(true));
            }
            
            // زر التحقق من التسلسل
            if (checkSequenceBtn) {
                checkSequenceBtn.addEventListener('click', () => {
                    if (!playerTurn) return;
                    
                    const isCorrect = JSON.stringify(playerSequence) === JSON.stringify(sequence.notes);
                    
                    if (isCorrect) {
                        const feedbackDiv = document.createElement('div');
                        feedbackDiv.className = 'feedback-positive';
                        feedbackDiv.innerHTML = lang === 'ar' ? 
                            `ممتاز! هذا هو التسلسل الصحيح. لقد تمكنت من تذكر النغمات بدقة.` : 
                            `Excellent! This is the correct sequence. You remembered the notes accurately.`;
                        gameFeedback.innerHTML = '';
                        gameFeedback.appendChild(feedbackDiv);
                        gameFeedback.style.display = 'block';
                        
                        // نقاط أقل للمحاولات المتأخرة
                        const hopePoints = currentAttempt === 1 ? 8 : 
                                          currentAttempt === 2 ? 5 : 3;
                        const insightPoints = currentAttempt === 1 ? 5 : 
                                             currentAttempt === 2 ? 3 : 2;
                        
                        gameData.points.hope += hopePoints;
                        gameData.points.insight += insightPoints;
                        updatePointsDisplay();
                        
                        // التقدم للتسلسل التالي
                        currentSequence++;
                        currentAttempt = 0; // إعادة تعيين المحاولات
                        companionTurn = gameData.player.mode === "group";
                        playerTurn = !companionTurn;
                        sequenceCompleted = true;
                        
                        setTimeout(() => {
                            displaySequence();
                        }, 2000);
                    } else {
                        const feedbackDiv = document.createElement('div');
                        feedbackDiv.className = 'feedback-negative';
                        feedbackDiv.innerHTML = lang === 'ar' ? 
                            `ليس صحيحًا تمامًا. المحاولة ${currentAttempt}/${maxAttemptsPerSequence}. حاول مرة أخرى.` : 
                            `Not quite right. Attempt ${currentAttempt}/${maxAttemptsPerSequence}. Try again.`;
                        gameFeedback.innerHTML = '';
                        gameFeedback.appendChild(feedbackDiv);
                        gameFeedback.style.display = 'block';
                        
                        // إخفاء أزرار التحقق والإعادة مؤقتاً
                        checkSequenceBtn.style.display = 'none';
                        resetSequenceBtn.style.display = 'none';
                        
                        // إظهار زر "عرض التسلسل مرة أخرى"
                        if (showSequenceAgainBtn) {
                            showSequenceAgainBtn.style.display = 'inline-block';
                            showSequenceAgainBtn.textContent = lang === 'ar' ? 
                                'عرض التسلسل مرة أخرى' : 'Show Sequence Again';
                        }
                        
                        // عدم إعادة تعيين التسلسل - يبقى اللاعب في نفس المستوى
                    }
                });
            }
            
            // زر إعادة تعيين التسلسل الحالي
            if (resetSequenceBtn) {
                resetSequenceBtn.addEventListener('click', () => {
                    playerSequence = [];
                    document.getElementById('player-notes-display').textContent = 
                        lang === 'ar' ? 'لم يتم اختيار أي نغمات بعد' : 'No notes selected yet';
                });
            }
            
            // زر عرض التسلسل مرة أخرى
            if (showSequenceAgainBtn) {
                showSequenceAgainBtn.addEventListener('click', () => {
                    // لا تتغير المحاولة - يبقى في نفس المحاولة
                    showingSequence = true;
                    
                    // إعادة عرض التسلسل
                    showSequence(true);
                    
                    // إعادة إظهار أزرار التحقق والإعادة
                    const updatedCheckBtn = document.getElementById('check-sequence');
                    const updatedResetBtn = document.getElementById('reset-sequence');
                    
                    if (updatedCheckBtn) updatedCheckBtn.style.display = 'inline-block';
                    if (updatedResetBtn) updatedResetBtn.style.display = 'inline-block';
                    if (showSequenceAgainBtn) showSequenceAgainBtn.style.display = 'none';
                    
                    // مسح الرسالة السابقة
                    gameFeedback.style.display = 'none';
                    gameFeedback.innerHTML = '';
                });
            }
            
            // دالة لعمل صوت النغمة
            function playNoteSound(note) {
                try {
                    const audioContext = new (window.AudioContext || window.webkitAudioContext)();
                    const oscillator = audioContext.createOscillator();
                    const gainNode = audioContext.createGain();
                    
                    oscillator.connect(gainNode);
                    gainNode.connect(audioContext.destination);
                    
                    const noteFrequencies = {
                        "C": 261.63, "D": 293.66, "E": 329.63,
                        "F": 349.23, "G": 392.00, "A": 440.00,
                        "B": 493.88
                    };
                    
                    oscillator.type = 'sine';
                    oscillator.frequency.setValueAtTime(noteFrequencies[note] || 440, audioContext.currentTime);
                    
                    gainNode.gain.setValueAtTime(0, audioContext.currentTime);
                    gainNode.gain.linearRampToValueAtTime(0.2, audioContext.currentTime + 0.1);
                    gainNode.gain.exponentialRampToValueAtTime(0.01, audioContext.currentTime + 0.8);
                    
                    oscillator.start(audioContext.currentTime);
                    oscillator.stop(audioContext.currentTime + 0.8);
                } catch (error) {
                    console.log("Audio not supported");
                }
            }
        }, 100);
    }
    
    // بدء اللعبة
    displaySequence();
    
    console.log("✅ Chapter 5 memory game setup complete - WITH RETRY SYSTEM");
}



// Set up emotion sorting game (Chapter 6) - UPDATED with role system and retry
function setupEmotionSortingGame(chapter) {
    const lang = gameData.player.language;
    
    console.log("Setting up emotion sorting game");
    
    const emotions = lang === 'ar' ? [
        { name: "سعادة", category: "إيجابي", emoji: "😊", description: "مشاعر الفرح والبهجة" },
        { name: "حزن", category: "سلبي", emoji: "😢", description: "مشاعر الخسارة والحزن" },
        { name: "غضب", category: "سلبي", emoji: "😠", description: "مشاعر الإحباط والاستياء" },
        { name: "خوف", category: "سلبي", emoji: "😨", description: "مشاعر القلق والخوف" },
        { name: "دهشة", category: "محايد", emoji: "😲", description: "مشاعر المفاجأة والصدمة" },
        { name: "اشمئزاز", category: "سلبي", emoji: "🤢", description: "مشاعر النفور والرفض" },
        { name: "ثقة", category: "إيجابي", emoji: "😌", description: "مشاعر الأمان والاعتماد" },
        { name: "حب", category: "إيجابي", emoji: "❤️", description: "مشاعر الحب والتعلق" },
        { name: "قلق", category: "سلبي", emoji: "😟", description: "مشاعر التوتر والقلق" },
        { name: "سلام", category: "إيجابي", emoji: "☮️", description: "مشاعر الهدوء والسلام" },
        { name: "حيرة", category: "محايد", emoji: "🤔", description: "مشاعر التردد والحيرة" },
        { name: "حماس", category: "إيجابي", emoji: "🎉", description: "مشاعر الحماس والترقب" }
    ] : [
        { name: "Happiness", category: "Positive", emoji: "😊", description: "Feelings of joy and delight" },
        { name: "Sadness", category: "Negative", emoji: "😢", description: "Feelings of loss and sorrow" },
        { name: "Anger", category: "Negative", emoji: "😠", description: "Feelings of frustration and resentment" },
        { name: "Fear", category: "Negative", emoji: "😨", description: "Feelings of anxiety and fear" },
        { name: "Surprise", category: "Neutral", emoji: "😲", description: "Feelings of astonishment and shock" },
        { name: "Disgust", category: "Negative", emoji: "🤢", description: "Feelings of revulsion and rejection" },
        { name: "Trust", category: "Positive", emoji: "😌", description: "Feelings of security and reliance" },
        { name: "Love", category: "Positive", emoji: "❤️", description: "Feelings of love and attachment" },
        { name: "Anxiety", category: "Negative", emoji: "😟", description: "Feelings of tension and anxiety" },
        { name: "Peace", category: "Positive", emoji: "☮️", description: "Feelings of calm and peace" },
        { name: "Confusion", category: "Neutral", emoji: "🤔", description: "Feelings of hesitation and confusion" },
        { name: "Excitement", category: "Positive", emoji: "🎉", description: "Feelings of excitement and anticipation" }
    ];
    
    // Select random emotions for the game
    const selectedEmotions = [...emotions].sort(() => Math.random() - 0.5).slice(0, 9);
    
    const categories = lang === 'ar' ? [
        { name: "إيجابي", color: "hsl(var(--success))", description: "المشاعر التي تشعرنا بالرضا والسعادة" },
        { name: "سلبي", color: "hsl(var(--destructive))", description: "المشاعر التي تشعرنا بعدم الراحة أو الألم" },
        { name: "محايد", color: "hsl(var(--primary))", description: "المشاعر التي ليست إيجابية ولا سلبية بوضوح" }
    ] : [
        { name: "Positive", color: "hsl(var(--success))", description: "Feelings that make us feel satisfied and happy" },
        { name: "Negative", color: "hsl(var(--destructive))", description: "Feelings that make us feel uncomfortable or in pain" },
        { name: "Neutral", color: "hsl(var(--primary))", description: "Feelings that are not clearly positive or negative" }
    ];
    
    let sortedEmotions = [];
    let companionTurn = gameData.player.mode === "group";
    let gameCompleted = false;
    
    // Function to check if all emotions are correctly sorted
    function checkSorting() {
        const emotionElements = document.querySelectorAll('.emotion-item');
        let allCorrect = true;
        
        emotionElements.forEach(element => {
            const emotionName = element.dataset.name;
            const currentCategory = element.parentElement.dataset.category;
            const emotion = emotions.find(e => e.name === emotionName);
            
            if (emotion && emotion.category !== currentCategory) {
                allCorrect = false;
            }
        });
        
        return allCorrect;
    }
    
    gameMechanics.innerHTML = `
        ${companionTurn ? `
        <div class="companion-turn">
            <div class="companion-name">${gameData.player.companion.name[lang]}:</div>
            <p>${lang === 'ar' ? 'دعنا نصنف المشاعر معًا! سأبدأ أولاً.' : "Let's sort emotions together! I'll start first."}</p>
        </div>
        ` : ''}
        <div class="game-instructions">
            <p>${lang === 'ar' ? 'اسحب وأسقط المشاعر في الفئة المناسبة لتنظيم برج الأفكار.' : 'Drag and drop emotions into the appropriate category to organize the tower of thoughts.'}</p>
            <p>${lang === 'ar' ? 'يجب تصنيف جميع المشاعر بشكل صحيح لإكمال الفصل.' : 'All emotions must be correctly categorized to complete the chapter.'}</p>
        </div>
        
        <div class="emotion-sorting">
            ${categories.map(category => `
                <div class="emotion-category" data-category="${category.name}" style="border-left: 5px solid ${category.color};">
                    <h4 style="color: ${category.color}; margin-bottom: 10px;">${category.name}</h4>
                    <p style="font-size: 0.9rem; color: hsl(var(--muted-foreground)); margin-bottom: 15px;">${category.description}</p>
                    <div class="category-items" style="min-height: 120px; padding: 10px; background: hsl(var(--muted) / 0.3); border-radius: 8px;">
                        <!-- Emotions will be placed here -->
                    </div>
                </div>
            `).join('')}
        </div>
        
        <div class="available-emotions" style="margin-top: 25px;">
            <h4>${lang === 'ar' ? 'المشاعر المتاحة:' : 'Available Emotions:'}</h4>
            <div style="display: flex; flex-wrap: wrap; gap: 10px; margin-top: 15px; padding: 15px; background: hsl(var(--muted)); border-radius: var(--radius);">
                ${selectedEmotions.map(emotion => `
                    <div class="emotion-item" data-name="${emotion.name}" data-category="${emotion.category}" draggable="true" 
                         style="padding: 10px 15px; background: white; border-radius: 20px; cursor: grab; display: flex; align-items: center; gap: 8px; box-shadow: 0 2px 5px rgba(0,0,0,0.1);">
                        <span style="font-size: 1.2rem;">${emotion.emoji}</span>
                        <span>${emotion.name}</span>
                    </div>
                `).join('')}
            </div>
        </div>
        
        <div style="margin-top: 20px; text-align: center;">
            <button class="btn" id="check-sorting">${lang === 'ar' ? 'تحقق من التصنيف' : 'Check Sorting'}</button>
        </div>
    `;
    
    // إظهار زر اكمال الفصل فقط بعد انتهاء اللعبة
    const originalCompleteBtn = document.querySelector('#complete-chapter-btn');
    if (originalCompleteBtn) {
        originalCompleteBtn.style.display = 'none';
    }
    
    // If it's companion's turn in group mode
    if (companionTurn && gameData.player.mode === "group") {
        setTimeout(() => {
            // Companion sorts first emotion
            const firstEmotion = selectedEmotions[0];
            const correctCategory = document.querySelector(`.emotion-category[data-category="${firstEmotion.category}"] .category-items`);
            const emotionElement = document.querySelector(`.emotion-item[data-name="${firstEmotion.name}"]`);
            
            if (correctCategory && emotionElement) {
                // Move emotion to correct category
                emotionElement.style.transform = "translateX(0)";
                correctCategory.appendChild(emotionElement);
                emotionElement.style.cursor = "default";
                
                // Show companion response
                const companionResponse = document.createElement('div');
                companionResponse.className = 'companion-answer';
                companionResponse.innerHTML = `
                    <div class="companion-name">${gameData.player.companion.name[lang]}:</div>
                    <p>${lang === 'ar' ? 'أعتقد أن' : 'I think'} "${firstEmotion.name}" ${lang === 'ar' ? 'ينتمي إلى فئة' : 'belongs to the'} "${firstEmotion.category}" ${lang === 'ar' ? 'لأن' : 'because'} ${firstEmotion.description}. ${lang === 'ar' ? 'الآن دورك!' : 'Now your turn!'}</p>
                `;
                gameMechanics.insertBefore(companionResponse, gameMechanics.querySelector('.emotion-sorting'));
                
                gameData.points.hope += 3;
                gameData.points.insight += 5;
                updatePointsDisplay();
                
                companionTurn = false;
            }
        }, 2000);
    }
    
    // Add drag and drop functionality
    const emotionItems = document.querySelectorAll('.emotion-item');
    const categoryContainers = document.querySelectorAll('.category-items');
    
    // Make emotions draggable
    emotionItems.forEach(item => {
        item.addEventListener('dragstart', function(e) {
            if (companionTurn || gameCompleted) return;
            e.dataTransfer.setData('text/plain', this.dataset.name);
            this.style.opacity = '0.5';
        });
        
        item.addEventListener('dragend', function() {
            this.style.opacity = '1';
        });
    });
    
    // Make category containers droppable
    categoryContainers.forEach(container => {
        container.addEventListener('dragover', function(e) {
            if (companionTurn || gameCompleted) return;
            e.preventDefault();
            this.style.backgroundColor = 'hsl(var(--primary) / 0.1)';
        });
        
        container.addEventListener('dragleave', function() {
            this.style.backgroundColor = '';
        });
        
        container.addEventListener('drop', function(e) {
            if (companionTurn || gameCompleted) return;
            e.preventDefault();
            this.style.backgroundColor = '';
            
            const emotionName = e.dataTransfer.getData('text/plain');
            const emotionElement = document.querySelector(`.emotion-item[data-name="${emotionName}"]`);
            const emotion = emotions.find(e => e.name === emotionName);
            const category = this.parentElement.dataset.category;
            
            if (emotionElement && emotion) {
                // Move emotion to this category
                this.appendChild(emotionElement);
                emotionElement.style.cursor = "default";
                
                // Check if placement is correct
                const isCorrect = emotion.category === category;
                
                if (isCorrect) {
                    emotionElement.style.backgroundColor = "hsl(var(--success) / 0.2)";
                    emotionElement.style.border = "2px solid hsl(var(--success))";
                    
                    // Show positive feedback occasionally
                    if (Math.random() > 0.7) {
                        const feedbackDiv = document.createElement('div');
                        feedbackDiv.className = 'feedback-positive';
                        feedbackDiv.innerHTML = lang === 'ar' ? 
                            `صحيح! "${emotion.name}" ينتمي إلى فئة "${category}".` : 
                            `Correct! "${emotion.name}" belongs to the "${category}" category.`;
                        gameFeedback.innerHTML = '';
                        gameFeedback.appendChild(feedbackDiv);
                        gameFeedback.style.display = 'block';
                        
                        setTimeout(() => {
                            gameFeedback.style.display = 'none';
                        }, 1500);
                    }
                } else {
                    emotionElement.style.backgroundColor = "hsl(var(--destructive) / 0.2)";
                    emotionElement.style.border = "2px solid hsl(var(--destructive))";
                    
                    // Show negative feedback
                    const feedbackDiv = document.createElement('div');
                    feedbackDiv.className = 'feedback-negative';
                    feedbackDiv.innerHTML = lang === 'ar' ? 
                        `ليس صحيحًا. "${emotion.name}" لا ينتمي إلى فئة "${category}". حاول مرة أخرى!` : 
                        `Not correct. "${emotion.name}" does not belong to the "${category}" category. Try again!`;
                    gameFeedback.innerHTML = '';
                    gameFeedback.appendChild(feedbackDiv);
                    gameFeedback.style.display = 'block';
                    
                    gameData.points.insight += 1;
                    updatePointsDisplay();
                    
                    // Allow user to move it again
                    setTimeout(() => {
                        emotionElement.style.backgroundColor = "";
                        emotionElement.style.border = "";
                    }, 1500);
                    
                    setTimeout(() => {
                        gameFeedback.style.display = 'none';
                    }, 2000);
                    
                    return;
                }
                
                // Check if all emotions are sorted
                const allSorted = document.querySelectorAll('.available-emotions .emotion-item').length === 0;
                if (allSorted) {
                    // Auto-check after a delay
                    setTimeout(() => {
                        document.getElementById('check-sorting').click();
                    }, 1000);
                }
            }
        });
    });
    
    // Check sorting button
    document.getElementById('check-sorting').addEventListener('click', () => {
        if (gameCompleted) return;
        
        const allCorrect = checkSorting();
        
        if (allCorrect) {
            // Mark all emotions as correct
            emotionItems.forEach(item => {
                item.style.backgroundColor = "hsl(var(--success) / 0.2)";
                item.style.border = "2px solid hsl(var(--success))";
            });
            
            gameFeedback.innerHTML = `<p style="color: hsl(var(--success));">${lang === 'ar' ? 'ممتاز! جميع المشاعر مصنفة بشكل صحيح. البرج أصبح منظمًا ومستقرًا.' : 'Excellent! All emotions are correctly categorized. The tower is now organized and stable.'}</p>`;
            gameData.points.hope += 15;
            gameData.points.insight += 10;
            
            // Show companion celebration (only in group mode)
            if (gameData.player.mode === "group") {
                showCompanionMessage('celebration');
            }
            
            gameCompleted = true;
            
            // تحديث تقدم اللعبة
            gameData.player.progress.chaptersCompleted = Math.max(gameData.player.progress.chaptersCompleted, 6);
            gameData.player.progress.currentChapter = 7;
            saveGameData();
            
            // إظهار زر اكمال الفصل بعد النجاح
            setTimeout(() => {
                gameFeedback.style.display = 'none';
                
                // إنشاء زر جديد لاستمرار اللعبة
                const continueBtn = document.createElement('button');
                continueBtn.className = 'btn';
                continueBtn.style.cssText = `
                    display: block;
                    margin: 20px auto;
                    padding: 12px 30px;
                    font-size: 1.1rem;
                    background: hsl(var(--primary));
                    color: white;
                    border: none;
                    border-radius: var(--radius);
                    cursor: pointer;
                    transition: all 0.3s ease;
                `;
                continueBtn.innerHTML = lang === 'ar' ? 
                    'متابعة إلى الفصل السابع' : 
                    'Continue to Chapter 7';
                
                continueBtn.onclick = function() {
                    // الانتقال للفصل التالي
                    if (gameData.player.mode === "individual") {
                        window.location.href = 'index.html?chapter=7';
                    } else {
                        window.location.href = 'index.html?chapter=7&mode=group';
                    }
                };
                
                // إضافة الزر للواجهة
                gameMechanics.appendChild(continueBtn);
            }, 2000);
        } else {
            // Highlight incorrect placements
            emotionItems.forEach(item => {
                const emotionName = item.dataset.name;
                const currentCategory = item.closest('.emotion-category')?.dataset.category;
                const emotion = emotions.find(e => e.name === emotionName);
                
                if (emotion && emotion.category !== currentCategory) {
                    item.style.backgroundColor = "hsl(var(--destructive) / 0.2)";
                    item.style.border = "2px solid hsl(var(--destructive))";
                    item.style.animation = "shake 0.5s";
                }
            });
            
            gameFeedback.innerHTML = `<p style="color: hsl(var(--destructive));">${lang === 'ar' ? 'بعض المشاعر ليست في الفئة الصحيحة. راجع تصنيفك وحاول مرة أخرى.' : 'Some emotions are not in the correct category. Review your sorting and try again.'}</p>`;
            gameData.points.insight += 3;
            
            // Add shake animation
            const style = document.createElement('style');
            style.textContent = `
                @keyframes shake {
                    0%, 100% { transform: translateX(0); }
                    25% { transform: translateX(-5px); }
                    75% { transform: translateX(5px); }
                }
            `;
            document.head.appendChild(style);
        }
        
        updatePointsDisplay();
        gameFeedback.style.display = 'block';
        
        if (!allCorrect) {
            setTimeout(() => {
                gameFeedback.style.display = 'none';
                // Remove animations
                emotionItems.forEach(item => {
                    item.style.animation = "";
                });
            }, 2000);
        }
    });
    
    console.log("Emotion sorting game setup complete");
}




// Set up reality testing game (Chapter 7) - IMPROVED VERSION with more scenarios and role system
function setupRealityTestingGame(chapter) {
    const lang = gameData.player.language;
    
    console.log("Setting up reality testing game");
    
    const scenarios = lang === 'ar' ? [
        { 
            reflection: "الجميع يتحدث عني في الغرفة المجاورة", 
            question: "هل سمعت أحدًا يقول اسمك؟", 
            correctAnswer: "no",
            explanation: "هذا مثال على التفكير المرجعي. في معظم الأحيان، لا يكون الناس مهتمين بنا كما نعتقد. يمكنك التحقق من خلال الاستماع بعناية أو سؤال شخص تثق به."
        },
        { 
            reflection: "أرى أنماطًا مخيفة في الظل", 
            question: "هل يمكنك التحقق مما إذا كانت هذه الأنماط حقيقية؟", 
            correctAnswer: "no",
            explanation: "يمكن أن تسبب القلق أوقاتًا رؤية أشياء غير موجودة. التحقق من الواقع يساعد في التمييز بين الخيال والحقيقة. حاول إضاءة المنطقة أو النظر من زاوية أخرى."
        },
        { 
            reflection: "أشعر أن هناك مؤامرة ضدي", 
            question: "هل لديك دليل ملموس على ذلك؟", 
            correctAnswer: "no",
            explanation: "الشعور بالمؤامرة هو عرض شائع. من المهم البحث عن أدلة واقعية قبل الاستنتاج. تحدث مع شخص تثق به عن مشاعرك."
        },
        { 
            reflection: "أشعر أنني قادر على تحقيق أي شيء أريده", 
            question: "هل هذا الشعور مبني على إنجازات سابقة؟", 
            correctAnswer: "yes",
            explanation: "الثقة بالنفس أمر إيجابي عندما تكون مبنية على تجارب حقيقية وإنجازات سابقة. هذا يساعد في الحفاظ على نظرة واقعية."
        }
    ] : [
        { 
            reflection: "Everyone in the next room is talking about me", 
            question: "Did you hear anyone say your name?", 
            correctAnswer: "no",
            explanation: "This is an example of referential thinking. Most of the time, people aren't as interested in us as we think. You can check by listening carefully or asking someone you trust."
        },
        { 
            reflection: "I see scary patterns in the shadows", 
            question: "Can you verify if these patterns are real?", 
            correctAnswer: "no",
            explanation: "Anxiety can sometimes cause us to see things that aren't there. Reality checking helps distinguish imagination from fact. Try lighting the area or looking from a different angle."
        },
        { 
            reflection: "I feel like there's a conspiracy against me", 
            question: "Do you have tangible evidence of this?", 
            correctAnswer: "no",
            explanation: "Feeling conspired against is a common symptom. It's important to look for real evidence before drawing conclusions. Talk to someone you trust about your feelings."
        },
        { 
            reflection: "I feel like I can achieve anything I want", 
            question: "Is this feeling based on past achievements?", 
            correctAnswer: "yes",
            explanation: "Self-confidence is positive when it's based on real experiences and past achievements. This helps maintain a realistic perspective."
        }
    ];
    
    // Shuffle scenarios
    const shuffledScenarios = [...scenarios].sort(() => Math.random() - 0.5);
    let currentScenario = 0;
    let companionTurn = gameData.player.mode === "group";
    let scenarioCompleted = false;
    
    function displayScenario() {
        if (currentScenario >= shuffledScenarios.length) {
            const successDiv = document.createElement('div');
            successDiv.className = 'feedback-positive';
            successDiv.innerHTML = lang === 'ar' ? 
                'ممتاز! لقد تعلمت كيفية اختبار الواقع والتمييز بين الحقيقة والوهم. الانعكاسات أصبحت أكثر وضوحًا وتعكس الحقيقة بدقة.' : 
                'Excellent! You\'ve learned how to test reality and distinguish between fact and illusion. The reflections have become clearer and reflect reality accurately.';
            gameFeedback.innerHTML = '';
            gameFeedback.appendChild(successDiv);
            gameFeedback.style.display = 'block';
            
            // Show complete chapter button after a delay
            setTimeout(() => {
                completeChapterBtn.style.display = 'block';
            }, 2000);
            return;
        }
        
        const scenario = shuffledScenarios[currentScenario];
        scenarioCompleted = false;
        
        gameMechanics.innerHTML = `
            ${companionTurn ? `
            <div class="companion-turn">
                <div class="companion-name">${gameData.player.companion.name[lang]}:</div>
                <p>${lang === 'ar' ? 'دعنا نختبر الواقع معًا! سأبدأ أولاً.' : "Let's test reality together! I'll start first."}</p>
            </div>
            ` : ''}
            <div class="game-instructions">
                <div style="background: hsl(var(--primary) / 0.1); padding: 15px; border-radius: var(--radius); margin-bottom: 15px; border-left: 4px solid hsl(var(--primary));">
                    <p><strong>${lang === 'ar' ? 'الانعكاس يقول:' : 'The reflection says:'}</strong></p>
                    <p style="font-size: 1.1rem; color: hsl(var(--foreground));">"${scenario.reflection}"</p>
                </div>
                <p><strong>${lang === 'ar' ? 'سؤال اختبار الواقع:' : 'Reality testing question:'}</strong> ${scenario.question}</p>
                <p>${lang === 'ar' ? 'فكر في السؤال بناءً على اختبار الواقع، وليس على المشاعر.' : 'Think about the question based on reality testing, not on feelings.'}</p>
            </div>
            <div class="interactive-options">
                <div class="interactive-option" data-answer="yes">
                    <span>${lang === 'ar' ? 'نعم' : 'Yes'}</span>
                </div>
                <div class="interactive-option" data-answer="no">
                    <span>${lang === 'ar' ? 'لا' : 'No'}</span>
                </div>
            </div>
            <p style="margin-top: 15px; color: hsl(var(--muted-foreground)); font-size: 0.9rem;">
                ${lang === 'ar' ? 'اختر الإجابة الصحيحة بناءً على اختبار الواقع والتفكير المنطقي.' : 'Choose the correct answer based on reality testing and logical thinking.'}
            </p>
        `;
        
        // If it's companion's turn in group mode
        if (companionTurn && gameData.player.mode === "group") {
            setTimeout(() => {
                // Show companion response
                const companionResponse = document.createElement('div');
                companionResponse.className = 'companion-answer';
                companionResponse.innerHTML = `
                    <div class="companion-name">${gameData.player.companion.name[lang]}:</div>
                    <p>${lang === 'ar' ? 'أعتقد أن الإجابة الصحيحة هي' : 'I think the correct answer is'} "${scenario.correctAnswer === 'yes' ? (lang === 'ar' ? 'نعم' : 'Yes') : (lang === 'ar' ? 'لا' : 'No')}". ${lang === 'ar' ? 'الآن دورك!' : 'Now your turn!'}</p>
                `;
                gameMechanics.insertBefore(companionResponse, gameMechanics.querySelector('.interactive-options'));
                
                gameData.points.hope += 5;
                gameData.points.insight += 8;
                updatePointsDisplay();
                
                // Auto-click after delay
                setTimeout(() => {
                    const correctAnswerElement = document.querySelector(`.interactive-option[data-answer="${scenario.correctAnswer}"]`);
                    correctAnswerElement.click();
                }, 1500);
            }, 2000);
        }
        
        // Add event listeners to answer options
        const answerOptions = document.querySelectorAll('.interactive-option');
        
        answerOptions.forEach(option => {
            option.addEventListener('click', () => {
                if (scenarioCompleted) return;
                
                const selectedAnswer = option.dataset.answer;
                const isCorrect = selectedAnswer === scenario.correctAnswer;
                
                if (isCorrect) {
                    option.style.backgroundColor = "hsl(var(--success))";
                    option.style.color = "white";
                    
                    // Only add points if it's the player's turn
                    if (!companionTurn || gameData.player.mode !== "group") {
                        gameData.points.hope += 5;
                        gameData.points.insight += 8;
                    }
                    
                    gameFeedback.innerHTML = `
                        <div class="feedback-positive">
                            <p><strong>${lang === 'ar' ? 'صحيح!' : 'Correct!'}</strong></p>
                            <p>${scenario.explanation}</p>
                        </div>
                    `;
                    
                    scenarioCompleted = true;
                    currentScenario++;
                    companionTurn = !companionTurn; // Switch turns
                } else {
                    option.style.backgroundColor = "hsl(var(--destructive))";
                    option.style.color = "white";
                    gameData.points.insight += 3;
                    
                    gameFeedback.innerHTML = `
                        <div class="feedback-negative">
                            <p><strong>${lang === 'ar' ? 'ليس صحيحًا.' : 'Not correct.'}</strong></p>
                            <p>${scenario.explanation}</p>
                            <p style="margin-top: 10px;">${lang === 'ar' ? 'حاول مرة أخرى!' : 'Try again!'}</p>
                        </div>
                    `;
                    
                    // Don't advance, keep trying
                }
                
                updatePointsDisplay();
                gameFeedback.style.display = 'block';
                
                if (isCorrect) {
                    setTimeout(() => {
                        gameFeedback.style.display = 'none';
                        displayScenario();
                    }, 2000);
                } else {
                    setTimeout(() => {
                        gameFeedback.style.display = 'none';
                        // Reset option colors for retry
                        answerOptions.forEach(opt => {
                            opt.style.backgroundColor = "";
                            opt.style.color = "";
                        });
                    }, 2000);
                }
            });
        });
    }
    
    displayScenario();
    
    console.log("Reality testing game setup complete");
}

// Set up trust building game (Chapter 8) - IMPROVED VERSION with role system
function setupTrustBuildingGame(chapter) {
    const lang = gameData.player.language;
    
    console.log("Setting up trust building game");
    
    const trustScenarios = lang === 'ar' ? [
        { 
            situation: "أنت وشخص آخر على الجسر المهتز. ماذا تفعل؟", 
            options: [
                { text: "تتقدم بسرعة وتترك الشخص الآخر خلفك", trustValue: -2, correct: false, explanation: "هذا يضعف الثقة ويجعل الجسر أكثر خطورة." },
                { text: "تطلب من الشخص الآخر أن يمسك بيدك وتتقدمان معًا", trustValue: 3, correct: true, explanation: "التعاون يبني الثقة ويجعل الجسر أكثر استقرارًا." },
                { text: "تتوقف وتنتظر حتى يجد الشخص الآخر طريقة", trustValue: 1, correct: false, explanation: "الانتظار السلبي لا يبني الثقة بشكل فعال." }
            ],
            correctAnswers: [1],
            explanation: "في المواقف الصعبة، التعاون النشط يبني أقوى روابط الثقة."
        },
        { 
            situation: "يبدو الشخص الآخر خائفًا. كيف تتفاعل؟", 
            options: [
                { text: "تتجاهل خوفه وتستمر", trustValue: -1, correct: false, explanation: "التجاهل يزيد من الخوف ويضعف الثقة." },
                { text: "تطمئنه وتخبره أنكما ستتخطيان هذا معًا", trustValue: 2, correct: true, explanation: "الطمأنينة تبني الثقة وتقلل من الخوف." },
                { text: "تسأله عن سبب خوفه وتستمع إليه", trustValue: 3, correct: true, explanation: "الاستماع الفعال يبني الثقة العميقة." }
            ],
            correctAnswers: [1, 2],
            explanation: "الاستماع والتعاطف هما أساس بناء الثقة في العلاقات."
        },
        { 
            situation: "الجسر يهتز بشدة. الشخص الآخر يبدو غير قادر على الاستمرار.", 
            options: [
                { text: "تستمر وحدك", trustValue: -3, correct: false, explanation: "التخلي يدمر الثقة تمامًا." },
                { text: "تعرض المساعدة وتشجعه على الاستمرار", trustValue: 2, correct: true, explanation: "العرض المساعدة يبني الثقة ويقوي العلاقة." },
                { text: "تتوقف وتقترح العودة معًا", trustValue: 1, correct: false, explanation: "العودة للخلف قد تكون آمنة ولكنها لا تبني ثقة قوية." }
            ],
            correctAnswers: [1],
            explanation: "في لحظات الضعف، تقديم الدعم يبني أقوى أنواع الثقة."
        }
    ] : [
        { 
            situation: "You and another person are on the shaky bridge. What do you do?", 
            options: [
                { text: "Move forward quickly and leave the other person behind", trustValue: -2, correct: false, explanation: "This weakens trust and makes the bridge more dangerous." },
                { text: "Ask the other person to hold your hand and move forward together", trustValue: 3, correct: true, explanation: "Cooperation builds trust and makes the bridge more stable." },
                { text: "Stop and wait until the other person finds a way", trustValue: 1, correct: false, explanation: "Passive waiting doesn't effectively build trust." }
            ],
            correctAnswers: [1],
            explanation: "In difficult situations, active cooperation builds the strongest trust bonds."
        },
        { 
            situation: "The other person seems scared. How do you react?", 
            options: [
                { text: "Ignore their fear and continue", trustValue: -1, correct: false, explanation: "Ignoring increases fear and weakens trust." },
                { text: "Reassure them and tell them you'll get through this together", trustValue: 2, correct: true, explanation: "Reassurance builds trust and reduces fear." },
                { text: "Ask them why they're scared and listen to them", trustValue: 3, correct: true, explanation: "Active listening builds deep trust." }
            ],
            correctAnswers: [1, 2],
            explanation: "Listening and empathy are the foundation of building trust in relationships."
        },
        { 
            situation: "The bridge is shaking violently. The other person seems unable to continue.", 
            options: [
                { text: "Continue alone", trustValue: -3, correct: false, explanation: "Abandonment completely destroys trust." },
                { text: "Offer help and encourage them to continue", trustValue: 2, correct: true, explanation: "Offering help builds trust and strengthens the relationship." },
                { text: "Stop and suggest going back together", trustValue: 1, correct: false, explanation: "Going back may be safe but doesn't build strong trust." }
            ],
            correctAnswers: [1],
            explanation: "In moments of weakness, offering support builds the strongest types of trust."
        }
    ];
    
    let currentScenario = 0;
    let totalTrust = 0;
    let companionTurn = gameData.player.mode === "group";
    let selectedOptions = [];
    let scenarioCompleted = false;
    
    function displayScenario() {
        if (currentScenario >= trustScenarios.length) {
            const trustScore = totalTrust;
            let feedbackMessage = "";
            let trustLevel = "";
            
            if (trustScore >= 6) {
                trustLevel = lang === 'ar' ? "عالية جدًا" : "Very High";
                feedbackMessage = lang === 'ar' 
                    ? "مذهل! لقد بنيت ثقة قوية. الجسر أصبح مستقرًا تمامًا وتستطيعان العبور بأمان." 
                    : "Amazing! You've built strong trust. The bridge is completely stable and you can cross safely.";
            } else if (trustScore >= 3) {
                trustLevel = lang === 'ar' ? "جيدة" : "Good";
                feedbackMessage = lang === 'ar' 
                    ? "جيد! لقد بنيت بعض الثقة. الجسر أصبح أكثر استقرارًا ولكن يحتاج إلى مزيد من التعاون." 
                    : "Good! You've built some trust. The bridge is more stable but needs more cooperation.";
            } else {
                trustLevel = lang === 'ar' ? "ضعيفة" : "Weak";
                feedbackMessage = lang === 'ar' 
                    ? "يحتاج الجسر إلى المزيد من الثقة. حاول بناء علاقات أفضل في المرة القادمة." 
                    : "The bridge needs more trust. Try to build better relationships next time.";
            }
            
            gameFeedback.innerHTML = `
                <div class="feedback-positive">
                    <p><strong>${lang === 'ar' ? 'اكتمل اختبار الثقة!' : 'Trust test completed!'}</strong></p>
                    <p>${lang === 'ar' ? 'مستوى الثقة:' : 'Trust Level:'} <strong>${trustLevel}</strong> (${totalTrust} ${lang === 'ar' ? 'نقطة' : 'points'})</p>
                    <p>${feedbackMessage}</p>
                </div>
            `;
            gameFeedback.style.display = 'block';
            
            // Add points based on trust score
            gameData.points.hope += Math.max(5, trustScore);
            gameData.points.insight += Math.max(5, trustScore);
            updatePointsDisplay();
            
            // Show complete chapter button after a delay
            setTimeout(() => {
                completeChapterBtn.style.display = 'block';
            }, 3000);
            return;
        }
        
        const scenario = trustScenarios[currentScenario];
        selectedOptions = [];
        scenarioCompleted = false;
        
        gameMechanics.innerHTML = `
            ${companionTurn ? `
            <div class="companion-turn">
                <div class="companion-name">${gameData.player.companion.name[lang]}:</div>
                <p>${lang === 'ar' ? 'دعنا نبني الثقة معًا! سأبدأ أولاً.' : "Let's build trust together! I'll start first."}</p>
            </div>
            ` : ''}
            <div class="game-instructions">
                <div style="background: hsl(var(--primary) / 0.1); padding: 15px; border-radius: var(--radius); margin-bottom: 15px; border-left: 4px solid hsl(var(--primary));">
                    <p><strong>${lang === 'ar' ? 'الموقف:' : 'Situation:'}</strong></p>
                    <p style="font-size: 1.1rem; color: hsl(var(--foreground));">${scenario.situation}</p>
                </div>
                ${scenario.correctAnswers.length > 1 ? 
                    `<p>${lang === 'ar' ? 'يمكنك اختيار أكثر من إجابة صحيحة.' : 'You can select more than one correct answer.'}</p>` : 
                    ''}
                <p>${lang === 'ar' ? 'اختر الإجراء الذي يبني الثقة والتعاون:' : 'Choose the action that builds trust and cooperation:'}</p>
            </div>
            <div class="interactive-options">
                ${scenario.options.map((option, index) => `
                    <div class="interactive-option" data-index="${index}" data-trust="${option.trustValue}" data-correct="${option.correct}">
                        <span>${option.text}</span>
                    </div>
                `).join('')}
            </div>
            <div style="margin-top: 15px; text-align: center;">
                <button class="btn" id="check-answers" style="display: none;">${lang === 'ar' ? 'تحقق من الإجابات' : 'Check Answers'}</button>
            </div>
            <p style="margin-top: 10px; color: hsl(var(--muted-foreground)); font-size: 0.9rem;">
                ${lang === 'ar' ? 'يمكنك اختيار إجابة واحدة أو أكثر ثم التحقق.' : 'You can select one or more answers then check.'}
            </p>
        `;
        
        // If it's companion's turn in group mode
        if (companionTurn && gameData.player.mode === "group") {
            setTimeout(() => {
                // Companion selects correct answers
                scenario.correctAnswers.forEach(correctIndex => {
                    const optionElement = document.querySelector(`.interactive-option[data-index="${correctIndex}"]`);
                    optionElement.click();
                });
                
                // Show companion response
                const companionResponse = document.createElement('div');
                companionResponse.className = 'companion-answer';
                const companionAnswers = scenario.correctAnswers.map(idx => scenario.options[idx].text).join(' و ');
                companionResponse.innerHTML = `
                    <div class="companion-name">${gameData.player.companion.name[lang]}:</div>
                    <p>${lang === 'ar' ? 'أعتقد أن' : 'I think'} "${companionAnswers}" ${lang === 'ar' ? 'هي الخيارات الصحيحة لبناء الثقة. الآن دورك!' : 'are the correct choices for building trust. Now your turn!'}</p>
                `;
                gameMechanics.insertBefore(companionResponse, gameMechanics.querySelector('.interactive-options'));
                
                // Auto-check after delay
                setTimeout(() => {
                    document.getElementById('check-answers').click();
                }, 1500);
            }, 2000);
        }
        
        // Add event listeners to option buttons
        const optionButtons = document.querySelectorAll('.interactive-option');
        const checkAnswersBtn = document.getElementById('check-answers');
        
        optionButtons.forEach(button => {
            button.addEventListener('click', () => {
                if (scenarioCompleted) return;
                
                const index = parseInt(button.dataset.index);
                
                if (selectedOptions.includes(index)) {
                    // Deselect
                    selectedOptions = selectedOptions.filter(i => i !== index);
                    button.style.backgroundColor = "";
                    button.style.color = "";
                    button.style.borderColor = "transparent";
                } else {
                    // Select
                    selectedOptions.push(index);
                    button.style.backgroundColor = "hsl(var(--primary) / 0.2)";
                    button.style.borderColor = "hsl(var(--primary))";
                }
                
                // Show check button when at least one option is selected
                if (selectedOptions.length > 0) {
                    checkAnswersBtn.style.display = 'inline-block';
                } else {
                    checkAnswersBtn.style.display = 'none';
                }
            });
        });
        
        // Add event listener to check answers button
        checkAnswersBtn.addEventListener('click', () => {
            if (scenarioCompleted) return;
            
            // Check if all correct answers are selected and no incorrect ones
            const allCorrectSelected = scenario.correctAnswers.every(idx => selectedOptions.includes(idx));
            const noIncorrectSelected = selectedOptions.every(idx => scenario.correctAnswers.includes(idx));
            const isPerfect = allCorrectSelected && noIncorrectSelected;
            
            // Calculate trust value from selected options
            let scenarioTrust = 0;
            selectedOptions.forEach(idx => {
                scenarioTrust += scenario.options[idx].trustValue;
            });
            
            if (isPerfect) {
                totalTrust += scenarioTrust;
                
                // Mark correct answers
                scenario.correctAnswers.forEach(idx => {
                    const option = document.querySelector(`.interactive-option[data-index="${idx}"]`);
                    option.style.backgroundColor = "hsl(var(--success))";
                    option.style.color = "white";
                    option.style.borderColor = "hsl(var(--success))";
                });
                
                gameData.points.hope += 5;
                gameData.points.insight += 5;
                gameFeedback.innerHTML = `
                    <div class="feedback-positive">
                        <p><strong>${lang === 'ar' ? 'ممتاز! جميع الإجابات صحيحة.' : 'Excellent! All answers are correct.'}</strong></p>
                        <p>${scenario.explanation}</p>
                        <p>${lang === 'ar' ? 'نقاط الثقة المكتسبة:' : 'Trust points gained:'} <strong>+${scenarioTrust}</strong></p>
                    </div>
                `;
                
                scenarioCompleted = true;
                currentScenario++;
                companionTurn = !companionTurn; // Switch turns
            } else {
                // Mark correct and incorrect answers
                optionButtons.forEach(button => {
                    const idx = parseInt(button.dataset.index);
                    if (scenario.correctAnswers.includes(idx)) {
                        button.style.backgroundColor = "hsl(var(--success))";
                        button.style.color = "white";
                        button.style.borderColor = "hsl(var(--success))";
                    } else if (selectedOptions.includes(idx)) {
                        button.style.backgroundColor = "hsl(var(--destructive))";
                        button.style.color = "white";
                        button.style.borderColor = "hsl(var(--destructive))";
                    }
                });
                
                gameData.points.insight += 2;
                gameFeedback.innerHTML = `
                    <div class="feedback-negative">
                        <p><strong>${lang === 'ar' ? 'ليست جميع الإجابات صحيحة.' : 'Not all answers are correct.'}</strong></p>
                        <p>${scenario.explanation}</p>
                        <p>${lang === 'ar' ? 'حاول مرة أخرى!' : 'Try again!'}</p>
                    </div>
                `;
                
                // Don't advance, keep trying
                selectedOptions = [];
                checkAnswersBtn.style.display = 'none';
            }
            
            updatePointsDisplay();
            gameFeedback.style.display = 'block';
            
            if (isPerfect) {
                setTimeout(() => {
                    gameFeedback.style.display = 'none';
                    displayScenario();
                }, 2000);
            } else {
                setTimeout(() => {
                    gameFeedback.style.display = 'none';
                    // Reset for retry
                    optionButtons.forEach(button => {
                        button.style.backgroundColor = "";
                        button.style.color = "";
                        button.style.borderColor = "transparent";
                    });
                    checkAnswersBtn.style.display = 'none';
                }, 2000);
            }
        });
    }
    
    displayScenario();
    
    console.log("Trust building game setup complete");
}


// ================================================
// الجزء الرابع: ألعاب الفصول 9-12
// ================================================

// Set up memory training game (Chapter 9) - IMPROVED VERSION with role system
function setupMemoryTrainingGame(chapter) {
    const lang = gameData.player.language;
    
    console.log("Setting up memory training game");
    
    // Create memory pairs with icons
    const memoryPairs = [
        { item1: "book", item2: "library", icon1: "📖", icon2: "📚", ar1: "كتاب", ar2: "مكتبة", category: "أشياء مرتبطة" },
        { item1: "pen", item2: "paper", icon1: "✏️", icon2: "📄", ar1: "قلم", ar2: "ورقة", category: "أدوات الكتابة" },
        { item1: "apple", item2: "orange", icon1: "🍎", icon2: "🍊", ar1: "تفاحة", ar2: "برتقالة", category: "فواكه" },
        { item1: "car", item2: "airplane", icon1: "🚗", icon2: "✈️", ar1: "سيارة", ar2: "طائرة", category: "مركبات" },
        { item1: "sun", item2: "moon", icon1: "☀️", icon2: "🌙", ar1: "شمس", ar2: "قمر", category: "أجرام سماوية" },
        { item1: "cat", item2: "dog", icon1: "🐱", icon2: "🐶", ar1: "قطة", ar2: "كلب", category: "حيوانات أليفة" }
    ];
    
    // Select 4 random pairs for the game
    const selectedPairs = [...memoryPairs].sort(() => Math.random() - 0.5).slice(0, 4);
    
    // Shuffle and prepare memory cards
    const memoryCards = [];
    selectedPairs.forEach(pair => {
        memoryCards.push({ 
            text: lang === 'ar' ? pair.ar1 : pair.item1, 
            pair: lang === 'ar' ? pair.ar2 : pair.item2, 
            icon: pair.icon1, 
            category: pair.category,
            matched: false 
        });
        memoryCards.push({ 
            text: lang === 'ar' ? pair.ar2 : pair.item2, 
            pair: lang === 'ar' ? pair.ar1 : pair.item1, 
            icon: pair.icon2, 
            category: pair.category,
            matched: false 
        });
    });
    
    // Shuffle the cards
    for (let i = memoryCards.length - 1; i > 0; i--) {
        const j = Math.floor(Math.random() * (i + 1));
        [memoryCards[i], memoryCards[j]] = [memoryCards[j], memoryCards[i]];
    }
    
    let firstCard = null;
    let secondCard = null;
    let lockBoard = false;
    let matchedPairs = 0;
    let companionTurn = gameData.player.mode === "group";
    let attempts = 0;
    
    gameMechanics.innerHTML = `
        ${companionTurn ? `
        <div class="companion-turn">
            <div class="companion-name">${gameData.player.companion.name[lang]}:</div>
            <p>${lang === 'ar' ? 'دعنا نلعب لعبة الذاكرة معًا! سأبدأ أولاً.' : "Let's play memory game together! I'll start first."}</p>
        </div>
        ` : ''}
        <div class="game-instructions">
            <p>${lang === 'ar' ? 'ابحث عن الأزواج المتطابقة لتنظيم مكتبة ذاكرتك.' : 'Find the matching pairs to organize your memory library.'}</p>
            <p>${lang === 'ar' ? 'كل زوج ينتمي إلى نفس الفئة.' : 'Each pair belongs to the same category.'}</p>
        </div>
        <div class="progress-info" style="margin-bottom: 15px; text-align: center;">
            <p>${lang === 'ar' ? 'الأزواج المتطابقة:' : 'Matched pairs:'} <span id="matched-count" style="font-weight: bold;">0</span> / ${selectedPairs.length}</p>
            <p>${lang === 'ar' ? 'المحاولات:' : 'Attempts:'} <span id="attempts-count" style="font-weight: bold;">0</span></p>
        </div>
        <div class="memory-game" id="memory-game">
            ${memoryCards.map((card, index) => `
                <div class="memory-card" data-index="${index}" data-text="${card.text}" data-pair="${card.pair}" data-category="${card.category}" data-matched="false">
                    <span style="font-size: 2rem;">❓</span>
                </div>
            `).join('')}
        </div>
        <p style="margin-top: 15px; color: hsl(var(--muted-foreground)); font-size: 0.9rem;">
            ${lang === 'ar' ? 'انقر على البطاقات للكشف عنها وإيجاد الأزواج المتطابقة.' : 'Click on the cards to reveal them and find matching pairs.'}
        </p>
    `;
    
    // If it's companion's turn in group mode
    if (companionTurn && gameData.player.mode === "group") {
        setTimeout(() => {
            // Companion finds first pair
            // Find an unmatched pair
            let firstUnmatchedIndex = -1;
            let secondUnmatchedIndex = -1;
            
            for (let i = 0; i < memoryCards.length; i++) {
                if (!memoryCards[i].matched) {
                    firstUnmatchedIndex = i;
                    // Try to find its pair
                    for (let j = i + 1; j < memoryCards.length; j++) {
                        if (!memoryCards[j].matched && 
                            (memoryCards[i].pair === memoryCards[j].text || 
                             memoryCards[i].text === memoryCards[j].pair)) {
                            secondUnmatchedIndex = j;
                            break;
                        }
                    }
                    if (secondUnmatchedIndex !== -1) break;
                }
            }
            
            if (firstUnmatchedIndex !== -1 && secondUnmatchedIndex !== -1) {
                const firstCardElement = document.querySelector(`.memory-card[data-index="${firstUnmatchedIndex}"]`);
                const secondCardElement = document.querySelector(`.memory-card[data-index="${secondUnmatchedIndex}"]`);
                
                // Reveal first card
                setTimeout(() => {
                    firstCardElement.innerHTML = `<span style="font-size: 2rem;">${memoryCards[firstUnmatchedIndex].icon}</span>`;
                    
                    // Reveal second card after delay
                    setTimeout(() => {
                        secondCardElement.innerHTML = `<span style="font-size: 2rem;">${memoryCards[secondUnmatchedIndex].icon}</span>`;
                        
                        // Mark as matched
                        setTimeout(() => {
                            memoryCards[firstUnmatchedIndex].matched = true;
                            memoryCards[secondUnmatchedIndex].matched = true;
                            firstCardElement.dataset.matched = "true";
                            secondCardElement.dataset.matched = "true";
                            firstCardElement.style.backgroundColor = "hsl(var(--success))";
                            secondCardElement.style.backgroundColor = "hsl(var(--success))";
                            
                            // Remove event listeners
                            firstCardElement.removeEventListener('click', flipCard);
                            secondCardElement.removeEventListener('click', flipCard);
                            
                            // Show companion response
                            const companionResponse = document.createElement('div');
                            companionResponse.className = 'companion-answer';
                            const category = memoryCards[firstUnmatchedIndex].category;
                            companionResponse.innerHTML = `
                                <div class="companion-name">${gameData.player.companion.name[lang]}:</div>
                                <p>${lang === 'ar' ? 'لقد وجدت زوجًا متطابقًا!' : 'I found a matching pair!'} ${memoryCards[firstUnmatchedIndex].icon} & ${memoryCards[secondUnmatchedIndex].icon} (${category}) ${lang === 'ar' ? 'الآن دورك!' : 'Now your turn!'}</p>
                            `;
                            gameMechanics.insertBefore(companionResponse, gameMechanics.querySelector('.memory-game'));
                            
                            matchedPairs++;
                            attempts++;
                            document.getElementById('matched-count').textContent = matchedPairs;
                            document.getElementById('attempts-count').textContent = attempts;
                            
                            gameData.points.hope += 3;
                            gameData.points.insight += 5;
                            updatePointsDisplay();
                            
                            companionTurn = false;
                            
                            // Check if game is complete
                            if (matchedPairs === selectedPairs.length) {
                                endGame();
                            }
                        }, 1000);
                    }, 1000);
                }, 1000);
            }
        }, 2000);
    }
    
    // Add event listeners to memory cards
    const cardElements = document.querySelectorAll('.memory-card');
    
    function flipCard() {
        if (lockBoard) return;
        if (this === firstCard) return;
        if (this.dataset.matched === "true") return;
        if (companionTurn) return;
        
        const cardIndex = parseInt(this.dataset.index);
        this.innerHTML = `<span style="font-size: 2rem;">${memoryCards[cardIndex].icon}</span>`;
        this.style.backgroundColor = "white";
        
        if (!firstCard) {
            firstCard = this;
            return;
        }
        
        secondCard = this;
        attempts++;
        document.getElementById('attempts-count').textContent = attempts;
        lockBoard = true;
        
        checkForMatch();
    }
    
    function checkForMatch() {
        const firstIndex = parseInt(firstCard.dataset.index);
        const secondIndex = parseInt(secondCard.dataset.index);
        
        const isMatch = memoryCards[firstIndex].pair === memoryCards[secondIndex].text || 
                       memoryCards[firstIndex].text === memoryCards[secondIndex].pair;
        
        if (isMatch) {
            disableCards();
            matchedPairs++;
            document.getElementById('matched-count').textContent = matchedPairs;
            
            gameData.points.hope += 3;
            gameData.points.insight += 5;
            updatePointsDisplay();
            
            // Show category info
            const category = memoryCards[firstIndex].category;
            const feedbackDiv = document.createElement('div');
            feedbackDiv.className = 'feedback-positive';
            feedbackDiv.innerHTML = lang === 'ar' ? 
                `ممتاز! زوج متطابق - ${category}` : 
                `Excellent! Matching pair - ${category}`;
            gameFeedback.innerHTML = '';
            gameFeedback.appendChild(feedbackDiv);
            gameFeedback.style.display = 'block';
            
            setTimeout(() => {
                gameFeedback.style.display = 'none';
            }, 1500);
            
            // Show companion encouragement (only in group mode)
            if (gameData.player.mode === "group" && matchedPairs % 2 === 0) {
                showCompanionMessage('encouragement');
            }
            
            if (matchedPairs === selectedPairs.length) {
                endGame();
            } else {
                // Switch turns in group mode
                if (gameData.player.mode === "group") {
                    companionTurn = !companionTurn;
                    if (companionTurn) {
                        setTimeout(() => {
                            companionPlay();
                        }, 1000);
                    }
                }
            }
        } else {
            unflipCards();
        }
    }
    
    function disableCards() {
        const firstIndex = parseInt(firstCard.dataset.index);
        const secondIndex = parseInt(secondCard.dataset.index);
        
        memoryCards[firstIndex].matched = true;
        memoryCards[secondIndex].matched = true;
        firstCard.dataset.matched = "true";
        secondCard.dataset.matched = "true";
        
        firstCard.style.backgroundColor = "hsl(var(--success))";
        secondCard.style.backgroundColor = "hsl(var(--success))";
        
        firstCard.removeEventListener('click', flipCard);
        secondCard.removeEventListener('click', flipCard);
        
        resetBoard();
    }
    
    function unflipCards() {
        setTimeout(() => {
            firstCard.innerHTML = '<span style="font-size: 2rem;">❓</span>';
            secondCard.innerHTML = '<span style="font-size: 2rem;">❓</span>';
            firstCard.style.backgroundColor = "";
            secondCard.style.backgroundColor = "";
            
            // Show feedback for incorrect match
            const feedbackDiv = document.createElement('div');
            feedbackDiv.className = 'feedback-negative';
            feedbackDiv.innerHTML = lang === 'ar' ? 
                'ليس زوجًا متطابقًا. حاول مرة أخرى!' : 
                'Not a matching pair. Try again!';
            gameFeedback.innerHTML = '';
            gameFeedback.appendChild(feedbackDiv);
            gameFeedback.style.display = 'block';
            
            setTimeout(() => {
                gameFeedback.style.display = 'none';
            }, 1500);
            
            resetBoard();
        }, 1000);
    }
    
    function resetBoard() {
        [firstCard, secondCard, lockBoard] = [null, null, false];
    }
    
    function companionPlay() {
        if (!companionTurn) return;
        
        // Find an unmatched pair
        let firstUnmatchedIndex = -1;
        let secondUnmatchedIndex = -1;
        
        for (let i = 0; i < memoryCards.length; i++) {
            if (!memoryCards[i].matched) {
                firstUnmatchedIndex = i;
                // Try to find its pair
                for (let j = i + 1; j < memoryCards.length; j++) {
                    if (!memoryCards[j].matched && 
                        (memoryCards[i].pair === memoryCards[j].text || 
                         memoryCards[i].text === memoryCards[j].pair)) {
                        secondUnmatchedIndex = j;
                        break;
                    }
                }
                if (secondUnmatchedIndex !== -1) break;
            }
        }
        
        if (firstUnmatchedIndex !== -1 && secondUnmatchedIndex !== -1) {
            const firstCardElement = document.querySelector(`.memory-card[data-index="${firstUnmatchedIndex}"]`);
            const secondCardElement = document.querySelector(`.memory-card[data-index="${secondUnmatchedIndex}"]`);
            
            // Reveal first card
            setTimeout(() => {
                firstCardElement.innerHTML = `<span style="font-size: 2rem;">${memoryCards[firstUnmatchedIndex].icon}</span>`;
                firstCardElement.style.backgroundColor = "white";
                
                // Reveal second card after delay
                setTimeout(() => {
                    secondCardElement.innerHTML = `<span style="font-size: 2rem;">${memoryCards[secondUnmatchedIndex].icon}</span>`;
                    secondCardElement.style.backgroundColor = "white";
                    
                    // Mark as matched
                    setTimeout(() => {
                        memoryCards[firstUnmatchedIndex].matched = true;
                        memoryCards[secondUnmatchedIndex].matched = true;
                        firstCardElement.dataset.matched = "true";
                        secondCardElement.dataset.matched = "true";
                        firstCardElement.style.backgroundColor = "hsl(var(--success))";
                        secondCardElement.style.backgroundColor = "hsl(var(--success))";
                        
                        firstCardElement.removeEventListener('click', flipCard);
                        secondCardElement.removeEventListener('click', flipCard);
                        
                        matchedPairs++;
                        attempts++;
                        document.getElementById('matched-count').textContent = matchedPairs;
                        document.getElementById('attempts-count').textContent = attempts;
                        
                        gameData.points.hope += 3;
                        gameData.points.insight += 5;
                        updatePointsDisplay();
                        
                        if (matchedPairs === selectedPairs.length) {
                            endGame();
                        } else {
                            companionTurn = false;
                        }
                    }, 1000);
                }, 1000);
            }, 1000);
        }
    }
    
    function endGame() {
        const efficiency = Math.round((selectedPairs.length / attempts) * 100);
        let efficiencyMessage = "";
        
        if (efficiency >= 80) {
            efficiencyMessage = lang === 'ar' ? "كفاءة ممتازة!" : "Excellent efficiency!";
        } else if (efficiency >= 60) {
            efficiencyMessage = lang === 'ar' ? "كفاءة جيدة!" : "Good efficiency!";
        } else {
            efficiencyMessage = lang === 'ar' ? "تحتاج إلى تحسين الذاكرة!" : "Need to improve memory!";
        }
        
        gameFeedback.innerHTML = `
            <div class="feedback-positive">
                <p><strong>${lang === 'ar' ? 'ممتاز! لقد نظمت مكتبة ذاكرتك بنجاح.' : 'Excellent! You\'ve successfully organized your memory library.'}</strong></p>
                <p>${lang === 'ar' ? 'الكفاءة:' : 'Efficiency:'} <strong>${efficiency}%</strong> (${selectedPairs.length}/${attempts} ${lang === 'ar' ? 'زوج/محاولة' : 'pair/attempt'})</p>
                <p>${efficiencyMessage}</p>
            </div>
        `;
        gameFeedback.style.display = 'block';
        
        // Show complete chapter button after a delay
        setTimeout(() => {
            completeChapterBtn.style.display = 'block';
        }, 3000);
    }
    
    cardElements.forEach(card => {
        if (card.dataset.matched !== "true") {
            card.addEventListener('click', flipCard);
        }
    });
    
    console.log("Memory training game setup complete");
}

// Set up voice discrimination game (Chapter 10) - IMPROVED VERSION with role system
function setupVoiceDiscriminationGame(chapter) {
    const lang = gameData.player.language;
    
    console.log("Setting up voice discrimination game");
    
    const voiceScenarios = lang === 'ar' ? [
        { 
            voice: "يجب أن تذهب إلى ذلك المبنى. إنه آمن.", 
            question: "هل هذه النصيحة مفيدة؟", 
            correctAnswer: "yes",
            explanation: "هذه نصيحة واضحة ومباشرة. تبدو مفيدة وواقعية.",
            voiceType: "مفيد"
        },
        { 
            voice: "لا تثق بأحد. الجميع يكذبون.", 
            question: "هل هذه النصيحة معقولة؟", 
            correctAnswer: "no",
            explanation: "هذه النصيحة متطرفة وغير معقولة. لا يمكن تعميمها على الجميع.",
            voiceType: "مضلل"
        },
        { 
            voice: "أنت لست جيدًا بما يكفي. يجب أن تستسلم.", 
            question: "هل يجب أن تتبع هذه النصيحة؟", 
            correctAnswer: "no",
            explanation: "هذه النصيحة سلبية وغير بناءة. من الأفضل تجاهلها والبحث عن دعم إيجابي.",
            voiceType: "سلبي"
        },
        { 
            voice: "خذ وقتك في التفكير. القرارات المتسرعة قد تكون خطيرة.", 
            question: "هل هذه نصيحة جيدة؟", 
            correctAnswer: "yes",
            explanation: "هذه النصيحة حكيمة ومدروسة. من الجيد اتباعها في المواقف المهمة.",
            voiceType: "حكيم"
        },
        { 
            voice: "الجميع يحبك ولا يمكن أن يخطئ أحد في حقك.", 
            question: "هل هذه النصيحة واقعية؟", 
            correctAnswer: "no",
            explanation: "هذه النصيحة غير واقعية ومثالية جدًا. العلاقات البشرية أكثر تعقيدًا.",
            voiceType: "غير واقعي"
        },
        { 
            voice: "استمع إلى مشاعرك ولكن تحقق من الحقائق أيضًا.", 
            question: "هل هذه نصيحة متوازنة؟", 
            correctAnswer: "yes",
            explanation: "هذه نصيحة متوازنة تجمع بين المشاعر والمنطق. هذا نهج صحي.",
            voiceType: "متوازن"
        }
    ] : [
        { 
            voice: "You should go to that building. It's safe.", 
            question: "Is this advice helpful?", 
            correctAnswer: "yes",
            explanation: "This is clear, direct advice. It seems helpful and realistic.",
            voiceType: "Helpful"
        },
        { 
            voice: "Don't trust anyone. Everyone lies.", 
            question: "Is this advice reasonable?", 
            correctAnswer: "no",
            explanation: "This advice is extreme and unreasonable. It can't be generalized to everyone.",
            voiceType: "Misleading"
        },
        { 
            voice: "You're not good enough. You should give up.", 
            question: "Should you follow this advice?", 
            correctAnswer: "no",
            explanation: "This advice is negative and unconstructive. It's better to ignore it and seek positive support.",
            voiceType: "Negative"
        },
        { 
            voice: "Take your time to think. Hasty decisions can be dangerous.", 
            question: "Is this good advice?", 
            correctAnswer: "yes",
            explanation: "This is wise, thoughtful advice. It's good to follow it in important situations.",
            voiceType: "Wise"
        },
        { 
            voice: "Everyone loves you and no one can wrong you.", 
            question: "Is this advice realistic?", 
            correctAnswer: "no",
            explanation: "This advice is unrealistic and too idealistic. Human relationships are more complex.",
            voiceType: "Unrealistic"
        },
        { 
            voice: "Listen to your feelings but also check the facts.", 
            question: "Is this balanced advice?", 
            correctAnswer: "yes",
            explanation: "This is balanced advice that combines feelings and logic. This is a healthy approach.",
            voiceType: "Balanced"
        }
    ];
    
    // Select random scenarios
    const selectedScenarios = [...voiceScenarios].sort(() => Math.random() - 0.5).slice(0, 4);
    let currentScenario = 0;
    let correctAnswers = 0;
    let companionTurn = gameData.player.mode === "group";
    let scenarioCompleted = false;
    
    function displayScenario() {
        if (currentScenario >= selectedScenarios.length) {
            const successRate = Math.round((correctAnswers / selectedScenarios.length) * 100);
            let feedbackMessage = "";
            let trustLevel = "";
            
            if (successRate >= 75) {
                trustLevel = lang === 'ar' ? "ممتاز" : "Excellent";
                feedbackMessage = lang === 'ar' 
                    ? "ممتاز! أنت ماهر في تمييز الأصوات الموثوقة. يمكنك الاعتماد على حكمك في المواقف الاجتماعية." 
                    : "Excellent! You're skilled at distinguishing reliable voices. You can rely on your judgment in social situations.";
            } else if (successRate >= 50) {
                trustLevel = lang === 'ar' ? "جيد" : "Good";
                feedbackMessage = lang === 'ar' 
                    ? "جيد! أنت تتحسن في تمييز الأصوات الموثوقة. استمر في الممارسة." 
                    : "Good! You're getting better at distinguishing reliable voices. Keep practicing.";
            } else {
                trustLevel = lang === 'ar' ? "يحتاج تحسين" : "Needs Improvement";
                feedbackMessage = lang === 'ar' 
                    ? "تحتاج إلى مزيد من الممارسة لتمييز الأصوات الموثوقة. حاول التركيز أكثر على النصائح الواقعية والمتوازنة." 
                    : "You need more practice to distinguish reliable voices. Try to focus more on realistic and balanced advice.";
            }
            
            gameFeedback.innerHTML = `
                <div class="feedback-positive">
                    <p><strong>${lang === 'ar' ? 'اكتمل اختبار الأصوات!' : 'Voice test completed!'}</strong></p>
                    <p>${lang === 'ar' ? 'الدقة:' : 'Accuracy:'} <strong>${successRate}%</strong> (${correctAnswers}/${selectedScenarios.length})</p>
                    <p>${lang === 'ar' ? 'مستوى الثقة:' : 'Trust Level:'} <strong>${trustLevel}</strong></p>
                    <p>${feedbackMessage}</p>
                </div>
            `;
            gameFeedback.style.display = 'block';
            
            // Add points based on success rate
            gameData.points.hope += Math.max(5, successRate / 10);
            gameData.points.insight += Math.max(5, successRate / 10);
            updatePointsDisplay();
            
            // Show complete chapter button after a delay
            setTimeout(() => {
                completeChapterBtn.style.display = 'block';
            }, 3000);
            return;
        }
        
        const scenario = selectedScenarios[currentScenario];
        scenarioCompleted = false;
        
        gameMechanics.innerHTML = `
            ${companionTurn ? `
            <div class="companion-turn">
                <div class="companion-name">${gameData.player.companion.name[lang]}:</div>
                <p>${lang === 'ar' ? 'دعنا نميز الأصوات معًا! سأبدأ أولاً.' : "Let's distinguish voices together! I'll start first."}</p>
            </div>
            ` : ''}
            <div class="game-instructions">
                <div style="background: hsl(var(--primary) / 0.1); padding: 15px; border-radius: var(--radius); margin-bottom: 15px; border-left: 4px solid hsl(var(--primary));">
                    <p><strong>${lang === 'ar' ? 'الصوت يقول:' : 'The voice says:'}</strong></p>
                    <p style="font-size: 1.1rem; color: hsl(var(--foreground)); font-style: italic;">"${scenario.voice}"</p>
                    <p style="margin-top: 10px; font-size: 0.9rem; color: hsl(var(--muted-foreground));">
                        ${lang === 'ar' ? 'نوع الصوت:' : 'Voice type:'} <strong>${scenario.voiceType}</strong>
                    </p>
                </div>
                <p><strong>${scenario.question}</strong></p>
                <p>${lang === 'ar' ? 'فكر في النصيحة بناءً على واقعيتها وفائدتها.' : 'Think about the advice based on its realism and usefulness.'}</p>
            </div>
            <div class="interactive-options">
                <div class="interactive-option" data-answer="yes">
                    <span>${lang === 'ar' ? 'نعم' : 'Yes'}</span>
                </div>
                <div class="interactive-option" data-answer="no">
                    <span>${lang === 'ar' ? 'لا' : 'No'}</span>
                </div>
            </div>
            <p style="margin-top: 15px; color: hsl(var(--muted-foreground)); font-size: 0.9rem;">
                ${lang === 'ar' ? 'اختر الإجابة الصحيحة بناءً على تقييمك للنصيحة.' : 'Choose the correct answer based on your assessment of the advice.'}
            </p>
        `;
        
        // If it's companion's turn in group mode
        if (companionTurn && gameData.player.mode === "group") {
            setTimeout(() => {
                // Show companion response
                const companionResponse = document.createElement('div');
                companionResponse.className = 'companion-answer';
                companionResponse.innerHTML = `
                    <div class="companion-name">${gameData.player.companion.name[lang]}:</div>
                    <p>${lang === 'ar' ? 'أعتقد أن الإجابة الصحيحة هي' : 'I think the correct answer is'} "${scenario.correctAnswer === 'yes' ? (lang === 'ar' ? 'نعم' : 'Yes') : (lang === 'ar' ? 'لا' : 'No')}". ${lang === 'ar' ? 'الآن دورك!' : 'Now your turn!'}</p>
                `;
                gameMechanics.insertBefore(companionResponse, gameMechanics.querySelector('.interactive-options'));
                
                // Auto-answer after delay
                setTimeout(() => {
                    const correctAnswerElement = document.querySelector(`.interactive-option[data-answer="${scenario.correctAnswer}"]`);
                    correctAnswerElement.click();
                }, 1500);
            }, 2000);
        }
        
        // Add event listeners to answer options
        const answerOptions = document.querySelectorAll('.interactive-option');
        
        answerOptions.forEach(option => {
            option.addEventListener('click', () => {
                if (scenarioCompleted) return;
                
                const selectedAnswer = option.dataset.answer;
                const isCorrect = selectedAnswer === scenario.correctAnswer;
                
                if (isCorrect) {
                    option.style.backgroundColor = "hsl(var(--success))";
                    option.style.color = "white";
                    correctAnswers++;
                    
                    // Only add points if it's player's turn
                    if (!companionTurn || gameData.player.mode !== "group") {
                        gameData.points.hope += 3;
                        gameData.points.insight += 5;
                    }
                    
                    gameFeedback.innerHTML = `
                        <div class="feedback-positive">
                            <p><strong>${lang === 'ar' ? 'صحيح!' : 'Correct!'}</strong></p>
                            <p>${scenario.explanation}</p>
                        </div>
                    `;
                    
                    scenarioCompleted = true;
                    currentScenario++;
                    companionTurn = !companionTurn; // Switch turns
                } else {
                    option.style.backgroundColor = "hsl(var(--destructive))";
                    option.style.color = "white";
                    gameData.points.insight += 2;
                    
                    gameFeedback.innerHTML = `
                        <div class="feedback-negative">
                            <p><strong>${lang === 'ar' ? 'ليس صحيحًا.' : 'Not correct.'}</strong></p>
                            <p>${scenario.explanation}</p>
                            <p style="margin-top: 10px;">${lang === 'ar' ? 'حاول مرة أخرى!' : 'Try again!'}</p>
                        </div>
                    `;
                    
                    // Don't advance, keep trying
                }
                
                updatePointsDisplay();
                gameFeedback.style.display = 'block';
                
                if (isCorrect) {
                    setTimeout(() => {
                        gameFeedback.style.display = 'none';
                        displayScenario();
                    }, 2000);
                } else {
                    setTimeout(() => {
                        gameFeedback.style.display = 'none';
                        // Reset option colors for retry
                        answerOptions.forEach(opt => {
                            opt.style.backgroundColor = "";
                            opt.style.color = "";
                        });
                    }, 2000);
                }
            });
        });
    }
    
    displayScenario();
    
    console.log("Voice discrimination game setup complete");
}

// Set up pattern recognition game (Chapter 11) - FULL BILINGUAL with role system and retry until correct
function setupPatternRecognitionGame(chapter) {
    const lang = gameData.player.language;
    
    console.log("Setting up pattern recognition game");
    
    const patterns = [
        { 
            sequence: ["circle", "square", "circle", "square", "?"], 
            answer: "circle",
            arSequence: ["دائرة", "مربع", "دائرة", "مربع", "؟"],
            arAnswer: "دائرة",
            patternType: lang === 'ar' ? "تناوب" : "Alternation",
            explanation: lang === 'ar' ? "النمط يتناوب بين دائرة ومربع." : "The pattern alternates between circle and square."
        },
        { 
            sequence: ["red", "blue", "green", "red", "blue", "?"], 
            answer: "green",
            arSequence: ["أحمر", "أزرق", "أخضر", "أحمر", "أزرق", "؟"],
            arAnswer: "أخضر",
            patternType: lang === 'ar' ? "تسلسل ألوان" : "Color sequence",
            explanation: lang === 'ar' ? "النمط يتكرر كل 3 ألوان: أحمر، أزرق، أخضر." : "The pattern repeats every 3 colors: red, blue, green."
        },
        { 
            sequence: ["up", "up", "down", "up", "up", "down", "?"], 
            answer: "up",
            arSequence: ["أعلى", "أعلى", "أسفل", "أعلى", "أعلى", "أسفل", "؟"],
            arAnswer: "أعلى",
            patternType: lang === 'ar' ? "مجموعات" : "Grouping",
            explanation: lang === 'ar' ? "النمط يتكون من مجموعات: أعلى، أعلى، أسفل." : "The pattern consists of groups: up, up, down."
        },
        { 
            sequence: ["1", "2", "3", "1", "2", "?"], 
            answer: "3",
            arSequence: ["١", "٢", "٣", "١", "٢", "؟"],
            arAnswer: "٣",
            patternType: lang === 'ar' ? "تسلسل رقمي" : "Numerical sequence",
            explanation: lang === 'ar' ? "النمط يتكرر كل 3 أرقام: 1، 2، 3." : "The pattern repeats every 3 numbers: 1, 2, 3."
        }
    ];
    
    // Select random patterns
    const selectedPatterns = [...patterns].sort(() => Math.random() - 0.5).slice(0, 3);
    let currentPattern = 0;
    let companionTurn = gameData.player.mode === "group";
    let patternCompleted = false;
    
    function displayPattern() {
        if (currentPattern >= selectedPatterns.length) {
            const successDiv = document.createElement('div');
            successDiv.className = 'feedback-positive';
            successDiv.innerHTML = lang === 'ar' ? 
                'ممتاز! لقد تعلمت كيفية التعرف على الأنماط في الغابة المتغيرة. يمكنك الآن التنقل بثقة بين المسارات المتغيرة.' : 
                'Excellent! You\'ve learned how to recognize patterns in the shifting forest. You can now navigate confidently between changing paths.';
            gameFeedback.innerHTML = '';
            gameFeedback.appendChild(successDiv);
            gameFeedback.style.display = 'block';
            
            // Show complete chapter button after a delay
            setTimeout(() => {
                completeChapterBtn.style.display = 'block';
            }, 2000);
            return;
        }
        
        const pattern = selectedPatterns[currentPattern];
        patternCompleted = false;
        
        // Create visual representation for the pattern
        let visualHTML = '';
        const sequence = lang === 'ar' ? pattern.arSequence : pattern.sequence;
        const answer = lang === 'ar' ? pattern.arAnswer : pattern.answer;
        
        if (pattern.sequence[0] === "circle") {
            visualHTML = `
                <div class="visual-shapes" style="margin: 20px 0;">
                    <div class="visual-shape shape-circle" style="margin: 5px;"></div>
                    <div class="visual-shape shape-square" style="margin: 5px;"></div>
                    <div class="visual-shape shape-circle" style="margin: 5px;"></div>
                    <div class="visual-shape shape-square" style="margin: 5px;"></div>
                    <div class="visual-shape" style="background: hsl(var(--muted)); border: 2px dashed hsl(var(--border)); margin: 5px; display: flex; align-items: center; justify-content: center; font-size: 1.5rem;">؟</div>
                </div>
            `;
        } else if (pattern.sequence[0] === "red") {
            visualHTML = `
                <div class="color-options" style="justify-content: center; margin: 20px 0;">
                    <div class="color-option" style="background: #FF6B6B; margin: 5px;"></div>
                    <div class="color-option" style="background: #4ECDC4; margin: 5px;"></div>
                    <div class="color-option" style="background: #06D6A0; margin: 5px;"></div>
                    <div class="color-option" style="background: #FF6B6B; margin: 5px;"></div>
                    <div class="color-option" style="background: #4ECDC4; margin: 5px;"></div>
                    <div class="color-option" style="background: hsl(var(--muted)); border: 2px dashed hsl(var(--border)); margin: 5px; display: flex; align-items: center; justify-content: center; color: hsl(var(--foreground)); font-weight: bold;">؟</div>
                </div>
            `;
        } else if (pattern.sequence[0] === "up") {
            visualHTML = `
                <div style="display: flex; justify-content: center; align-items: center; gap: 10px; margin: 20px 0; flex-wrap: wrap;">
                    <div style="padding: 10px 15px; background: hsl(var(--primary)); color: white; border-radius: 8px; font-weight: bold;">${sequence[0]}</div>
                    <div style="padding: 10px 15px; background: hsl(var(--primary)); color: white; border-radius: 8px; font-weight: bold;">${sequence[1]}</div>
                    <div style="padding: 10px 15px; background: hsl(var(--accent)); color: white; border-radius: 8px; font-weight: bold;">${sequence[2]}</div>
                    <div style="padding: 10px 15px; background: hsl(var(--primary)); color: white; border-radius: 8px; font-weight: bold;">${sequence[3]}</div>
                    <div style="padding: 10px 15px; background: hsl(var(--primary)); color: white; border-radius: 8px; font-weight: bold;">${sequence[4]}</div>
                    <div style="padding: 10px 15px; background: hsl(var(--accent)); color: white; border-radius: 8px; font-weight: bold;">${sequence[5]}</div>
                    <div style="padding: 10px 15px; background: hsl(var(--muted)); border: 2px dashed hsl(var(--border)); border-radius: 8px; font-weight: bold; color: hsl(var(--foreground));">؟</div>
                </div>
            `;
        } else {
            visualHTML = `
                <div style="font-size: 1.5rem; font-weight: bold; margin: 20px 0; text-align: center; display: flex; justify-content: center; align-items: center; gap: 10px; flex-wrap: wrap;">
                    <span>${sequence[0]}</span>
                    <span>→</span>
                    <span>${sequence[1]}</span>
                    <span>→</span>
                    <span>${sequence[2]}</span>
                    <span>→</span>
                    <span>${sequence[3]}</span>
                    <span>→</span>
                    <span>${sequence[4]}</span>
                    <span>→</span>
                    <span style="background: hsl(var(--muted)); padding: 5px 10px; border-radius: 8px; border: 2px dashed hsl(var(--border));">؟</span>
                </div>
            `;
        }
        
        // Generate answer options
        const allOptions = lang === 'ar' ? 
            ["دائرة", "مربع", "مثلث", "نجمة", "أحمر", "أزرق", "أخضر", "أعلى", "أسفل", "١", "٢", "٣"] :
            ["circle", "square", "triangle", "star", "red", "blue", "green", "up", "down", "1", "2", "3"];
        
        // Filter to include correct answer and some random options
        const options = [answer];
        while (options.length < 4) {
            const randomOption = allOptions[Math.floor(Math.random() * allOptions.length)];
            if (!options.includes(randomOption)) {
                options.push(randomOption);
            }
        }
        
        // Shuffle options
        options.sort(() => Math.random() - 0.5);
        
        gameMechanics.innerHTML = `
            ${companionTurn ? `
            <div class="companion-turn">
                <div class="companion-name">${gameData.player.companion.name[lang]}:</div>
                <p>${lang === 'ar' ? 'دعنا نتعرف على الأنماط معًا! سأبدأ أولاً.' : "Let's recognize patterns together! I'll start first."}</p>
            </div>
            ` : ''}
            <div class="game-instructions">
                <p><strong>${lang === 'ar' ? 'نوع النمط:' : 'Pattern type:'}</strong> ${pattern.patternType}</p>
                <p>${lang === 'ar' ? 'ما هو العنصر التالي في التسلسل؟' : 'What is the next item in the sequence?'}</p>
                <p><strong>${sequence.slice(0, -1).join(' → ')} → ?</strong></p>
            </div>
            ${visualHTML}
            <div class="interactive-options">
                ${options.map(option => {
                    let icon = "";
                    if (option === "circle" || option === "دائرة") icon = '<div class="visual-shape shape-circle" style="width: 40px; height: 40px;"></div>';
                    else if (option === "square" || option === "مربع") icon = '<div class="visual-shape shape-square" style="width: 40px; height: 40px;"></div>';
                    else if (option === "triangle" || option === "مثلث") icon = '<div class="visual-shape shape-triangle" style="width: 40px; height: 40px;"></div>';
                    else if (option === "star" || option === "نجمة") icon = '<div class="visual-shape shape-star" style="width: 40px; height: 40px;"></div>';
                    else if (option === "red" || option === "أحمر") icon = '<div class="color-option" style="background: #FF6B6B; width: 40px; height: 40px;"></div>';
                    else if (option === "blue" || option === "أزرق") icon = '<div class="color-option" style="background: #4ECDC4; width: 40px; height: 40px;"></div>';
                    else if (option === "green" || option === "أخضر") icon = '<div class="color-option" style="background: #06D6A0; width: 40px; height: 40px;"></div>';
                    else if (option === "up" || option === "أعلى") icon = '<div style="padding: 8px 12px; background: hsl(var(--primary)); color: white; border-radius: 6px; font-weight: bold;">↑</div>';
                    else if (option === "down" || option === "أسفل") icon = '<div style="padding: 8px 12px; background: hsl(var(--accent)); color: white; border-radius: 6px; font-weight: bold;">↓</div>';
                    else icon = `<div style="padding: 8px 12px; background: hsl(var(--primary)); color: white; border-radius: 6px; font-weight: bold; font-size: 1.2rem;">${option}</div>`;
                    
                    return `
                        <div class="interactive-option" data-answer="${option}">
                            ${icon}
                            <span style="margin-top: 5px;">${option}</span>
                        </div>
                    `;
                }).join('')}
            </div>
            <p style="margin-top: 15px; color: hsl(var(--muted-foreground)); font-size: 0.9rem;">
                ${lang === 'ar' ? 'ابحث عن النمط واختر الإجابة الصحيحة.' : 'Look for the pattern and choose the correct answer.'}
            </p>
        `;
        
        // If it's companion's turn in group mode
        if (companionTurn && gameData.player.mode === "group") {
            setTimeout(() => {
                // Show companion response
                const companionResponse = document.createElement('div');
                companionResponse.className = 'companion-answer';
                companionResponse.innerHTML = `
                    <div class="companion-name">${gameData.player.companion.name[lang]}:</div>
                    <p>${lang === 'ar' ? 'أعتقد أن الإجابة الصحيحة هي' : 'I think the correct answer is'} "${answer}" ${lang === 'ar' ? 'لأن النمط هو' : 'because the pattern is'} ${pattern.explanation}. ${lang === 'ar' ? 'الآن دورك!' : 'Now your turn!'}</p>
                `;
                gameMechanics.insertBefore(companionResponse, gameMechanics.querySelector('.interactive-options'));
                
                // Auto-answer after delay
                setTimeout(() => {
                    const correctAnswerElement = document.querySelector(`.interactive-option[data-answer="${answer}"]`);
                    correctAnswerElement.click();
                }, 1500);
            }, 2000);
        }
        
        // Add event listeners to answer options
        const answerOptions = document.querySelectorAll('.interactive-option');
        
        answerOptions.forEach(option => {
            option.addEventListener('click', () => {
                if (patternCompleted) return;
                
                const selectedAnswer = option.dataset.answer;
                const isCorrect = selectedAnswer === answer;
                
                if (isCorrect) {
                    option.style.backgroundColor = "hsl(var(--success))";
                    option.style.color = "white";
                    
                    // Only add points if it's player's turn
                    if (!companionTurn || gameData.player.mode !== "group") {
                        gameData.points.hope += 5;
                        gameData.points.insight += 5;
                    }
                    
                    gameFeedback.innerHTML = `
                        <div class="feedback-positive">
                            <p><strong>${lang === 'ar' ? 'صحيح! لقد وجدت النمط.' : 'Correct! You found the pattern.'}</strong></p>
                            <p>${pattern.explanation}</p>
                        </div>
                    `;
                    
                    patternCompleted = true;
                    currentPattern++;
                    companionTurn = !companionTurn; // Switch turns
                } else {
                    option.style.backgroundColor = "hsl(var(--destructive))";
                    option.style.color = "white";
                    gameData.points.insight += 2;
                    
                    gameFeedback.innerHTML = `
                        <div class="feedback-negative">
                            <p><strong>${lang === 'ar' ? 'ليس صحيحًا. حاول مرة أخرى.' : 'Not correct. Try again.'}</strong></p>
                            <p>${pattern.explanation}</p>
                            <p style="margin-top: 10px;">${lang === 'ar' ? 'انظر إلى النمط بعناية!' : 'Look at the pattern carefully!'}</p>
                        </div>
                    `;
                    
                    // Don't advance, keep trying
                }
                
                updatePointsDisplay();
                gameFeedback.style.display = 'block';
                
                if (isCorrect) {
                    setTimeout(() => {
                        gameFeedback.style.display = 'none';
                        displayPattern();
                    }, 2000);
                } else {
                    setTimeout(() => {
                        gameFeedback.style.display = 'none';
                        // Reset option colors for retry
                        answerOptions.forEach(opt => {
                            opt.style.backgroundColor = "";
                            opt.style.color = "";
                        });
                    }, 2000);
                }
            });
        });
    }
    
    displayPattern();
    
    console.log("Pattern recognition game setup complete");
}

// Set up echo identification game (Chapter 12) - UPDATED: New game with role system and retry
function setupEchoIdentificationGame(chapter) {
    const lang = gameData.player.language;
    
    console.log("Setting up echo identification game");
    
    // New game: Match the echo to the correct sound
    const soundPairs = [
        { 
            original: lang === 'ar' ? "مرحبًا" : "Hello", 
            echoes: [
                { text: lang === 'ar' ? "مرحبًا" : "Hello", correct: true, distortion: "none" },
                { text: lang === 'ar' ? "أهلاً" : "Hi", correct: false, distortion: "different_word" },
                { text: lang === 'ar' ? "كيف حالك؟" : "How are you?", correct: false, distortion: "different_phrase" }
            ],
            explanation: lang === 'ar' ? "الصدى الحقيقي يكرر الكلمات بدقة." : "The true echo repeats the words accurately."
        },
        { 
            original: lang === 'ar' ? "كيف حالك؟" : "How are you?", 
            echoes: [
                { text: lang === 'ar' ? "كيف حالك؟" : "How are you?", correct: true, distortion: "none" },
                { text: lang === 'ar' ? "من أنت؟" : "Who are you?", correct: false, distortion: "different_question" },
                { text: lang === 'ar' ? "أنا بخير" : "I'm fine", correct: false, distortion: "answer_instead" }
            ],
            explanation: lang === 'ar' ? "الصدى الحقيقي يحافظ على نفس المعنى والصيغة." : "The true echo maintains the same meaning and form."
        },
        { 
            original: lang === 'ar' ? "أنا بخير" : "I'm fine", 
            echoes: [
                { text: lang === 'ar' ? "أنا بخير" : "I'm fine", correct: true, distortion: "none" },
                { text: lang === 'ar' ? "أنت بخير" : "You're fine", correct: false, distortion: "changed_person" },
                { text: lang === 'ar' ? "أنا لست بخير" : "I'm not fine", correct: false, distortion: "negated" }
            ],
            explanation: lang === 'ar' ? "الصدى الحقيقي لا يغير المعنى الأساسي." : "The true echo doesn't change the basic meaning."
        },
        { 
            original: lang === 'ar' ? "شكرًا لك" : "Thank you", 
            echoes: [
                { text: lang === 'ar' ? "شكرًا لك" : "Thank you", correct: true, distortion: "none" },
                { text: lang === 'ar' ? "عفواً" : "You're welcome", correct: false, distortion: "response_instead" },
                { text: lang === 'ar' ? "من فضلك" : "Please", correct: false, distortion: "different_phrase" }
            ],
            explanation: lang === 'ar' ? "الصدى الحقيقي يكرر العبارة كما هي." : "The true echo repeats the phrase as is."
        }
    ];
    
    // Select random pairs
    const selectedPairs = [...soundPairs].sort(() => Math.random() - 0.5).slice(0, 3);
    let currentPair = 0;
    let correctAnswers = 0;
    let companionTurn = gameData.player.mode === "group";
    let pairCompleted = false;
    
    function displayPair() {
        if (currentPair >= selectedPairs.length) {
            const accuracy = Math.round((correctAnswers / selectedPairs.length) * 100);
            let feedbackMessage = "";
            
            if (accuracy >= 80) {
                feedbackMessage = lang === 'ar' 
                    ? "ممتاز! حاسة السمع لديك دقيقة جدًا. يمكنك التمييز بين الأصداء الحقيقية والزائفة بسهولة." 
                    : "Excellent! Your hearing is very accurate. You can easily distinguish between true and false echoes.";
            } else if (accuracy >= 60) {
                feedbackMessage = lang === 'ar' 
                    ? "جيد! أنت تتحسن في تمييز الأصداء. واصل التركيز على التفاصيل الدقيقة." 
                    : "Good! You're getting better at distinguishing echoes. Keep focusing on subtle details.";
            } else {
                feedbackMessage = lang === 'ar' 
                    ? "تحتاج إلى مزيد من التركيز على التفاصيل الدقيقة في الأصوات." 
                    : "You need to focus more on subtle details in sounds.";
            }
            
            gameFeedback.innerHTML = `
                <div class="feedback-positive">
                    <p><strong>${lang === 'ar' ? 'اكتمل اختبار الأصداء!' : 'Echo test completed!'}</strong></p>
                    <p>${lang === 'ar' ? 'الدقة:' : 'Accuracy:'} <strong>${accuracy}%</strong> (${correctAnswers}/${selectedPairs.length})</p>
                    <p>${feedbackMessage}</p>
                </div>
            `;
            gameFeedback.style.display = 'block';
            
            // Add points based on accuracy
            gameData.points.hope += Math.max(5, accuracy / 10);
            gameData.points.insight += Math.max(5, accuracy / 10);
            updatePointsDisplay();
            
            // Show complete chapter button after a delay
            setTimeout(() => {
                completeChapterBtn.style.display = 'block';
            }, 3000);
            return;
        }
        
        const pair = selectedPairs[currentPair];
        pairCompleted = false;
        
        gameMechanics.innerHTML = `
            ${companionTurn ? `
            <div class="companion-turn">
                <div class="companion-name">${gameData.player.companion.name[lang]}:</div>
                <p>${lang === 'ar' ? 'دعنا نميز الأصداء معًا! سأبدأ أولاً.' : "Let's distinguish echoes together! I'll start first."}</p>
            </div>
            ` : ''}
            <div class="game-instructions">
                <div style="background: hsl(var(--primary) / 0.1); padding: 15px; border-radius: var(--radius); margin-bottom: 15px; border-left: 4px solid hsl(var(--primary));">
                    <p><strong>${lang === 'ar' ? 'أنت تقول:' : 'You say:'}</strong></p>
                    <p style="font-size: 1.2rem; color: hsl(var(--foreground)); font-weight: bold;">"${pair.original}"</p>
                </div>
                <p>${lang === 'ar' ? 'أي من هذه الأصداء هو الحقيقي (يكرر كلماتك بدقة)؟' : 'Which of these echoes is the true one (repeats your words accurately)?'}</p>
                <p>${lang === 'ar' ? 'انقر على الصدى الحقيقي:' : 'Click on the true echo:'}</p>
            </div>
            <div class="interactive-options">
                ${pair.echoes.map((echo, index) => `
                    <div class="interactive-option" data-index="${index}" data-correct="${echo.correct}" data-distortion="${echo.distortion}">
                        <div style="font-size: 1.5rem; margin-bottom: 5px;">🔊</div>
                        <span>"${echo.text}"</span>
                    </div>
                `).join('')}
            </div>
            <p style="margin-top: 15px; color: hsl(var(--muted-foreground)); font-size: 0.9rem;">
                ${lang === 'ar' ? 'ابحث عن الصدى الذي يكرر الكلمات بدقة دون تغيير.' : 'Look for the echo that repeats words accurately without change.'}
            </p>
        `;
        
        // If it's companion's turn in group mode
        if (companionTurn && gameData.player.mode === "group") {
            setTimeout(() => {
                const correctEcho = pair.echoes.find(echo => echo.correct);
                const correctIndex = pair.echoes.findIndex(echo => echo.correct);
                
                // Show companion response
                const companionResponse = document.createElement('div');
                companionResponse.className = 'companion-answer';
                companionResponse.innerHTML = `
                    <div class="companion-name">${gameData.player.companion.name[lang]}:</div>
                    <p>${lang === 'ar' ? 'أعتقد أن الصدى الحقيقي هو' : 'I think the true echo is'} "${correctEcho.text}" ${lang === 'ar' ? 'لأنه يكرر الكلمات بدقة. الآن دورك!' : 'because it repeats the words accurately. Now your turn!'}</p>
                `;
                gameMechanics.insertBefore(companionResponse, gameMechanics.querySelector('.interactive-options'));
                
                // Auto-answer after delay
                setTimeout(() => {
                    const correctAnswerElement = document.querySelector(`.interactive-option[data-index="${correctIndex}"]`);
                    correctAnswerElement.click();
                }, 1500);
            }, 2000);
        }
        
        // Add event listeners to echo options
        const echoOptions = document.querySelectorAll('.interactive-option');
        
        echoOptions.forEach(option => {
            option.addEventListener('click', () => {
                if (pairCompleted) return;
                
                const isCorrect = option.dataset.correct === "true";
                const distortion = option.dataset.distortion;
                
                if (isCorrect) {
                    option.style.backgroundColor = "hsl(var(--success))";
                    option.style.color = "white";
                    correctAnswers++;
                    
                    // Only add points if it's player's turn
                    if (!companionTurn || gameData.player.mode !== "group") {
                        gameData.points.hope += 5;
                        gameData.points.insight += 5;
                    }
                    
                    gameFeedback.innerHTML = `
                        <div class="feedback-positive">
                            <p><strong>${lang === 'ar' ? 'صحيح! هذا هو الصدى الحقيقي.' : 'Correct! This is the true echo.'}</strong></p>
                            <p>${pair.explanation}</p>
                        </div>
                    `;
                    
                    pairCompleted = true;
                    currentPair++;
                    companionTurn = !companionTurn; // Switch turns
                } else {
                    option.style.backgroundColor = "hsl(var(--destructive))";
                    option.style.color = "white";
                    gameData.points.insight += 2;
                    
                    let distortionExplanation = "";
                    if (distortion === "different_word") {
                        distortionExplanation = lang === 'ar' ? "هذا يستخدم كلمة مختلفة." : "This uses a different word.";
                    } else if (distortion === "different_phrase") {
                        distortionExplanation = lang === 'ar' ? "هذه عبارة مختلفة تمامًا." : "This is a completely different phrase.";
                    } else if (distortion === "different_question") {
                        distortionExplanation = lang === 'ar' ? "هذا سؤال مختلف." : "This is a different question.";
                    } else if (distortion === "answer_instead") {
                        distortionExplanation = lang === 'ar' ? "هذه إجابة وليس تكرارًا." : "This is an answer, not a repetition.";
                    } else if (distortion === "changed_person") {
                        distortionExplanation = lang === 'ar' ? "هذا يغير الضمير." : "This changes the pronoun.";
                    } else if (distortion === "negated") {
                        distortionExplanation = lang === 'ar' ? "هذا ينفي المعنى." : "This negates the meaning.";
                    } else if (distortion === "response_instead") {
                        distortionExplanation = lang === 'ar' ? "هذا رد وليس تكرارًا." : "This is a response, not a repetition.";
                    }
                    
                    gameFeedback.innerHTML = `
                        <div class="feedback-negative">
                            <p><strong>${lang === 'ar' ? 'ليس صحيحًا. هذا ليس الصدى الحقيقي.' : 'Not correct. This is not the true echo.'}</strong></p>
                            <p>${distortionExplanation} ${pair.explanation}</p>
                            <p style="margin-top: 10px;">${lang === 'ar' ? 'حاول مرة أخرى!' : 'Try again!'}</p>
                        </div>
                    `;
                    
                    // Don't advance, keep trying
                }
                
                updatePointsDisplay();
                gameFeedback.style.display = 'block';
                
                if (isCorrect) {
                    setTimeout(() => {
                        gameFeedback.style.display = 'none';
                        displayPair();
                    }, 2000);
                } else {
                    setTimeout(() => {
                        gameFeedback.style.display = 'none';
                        // Reset option colors for retry
                        echoOptions.forEach(opt => {
                            opt.style.backgroundColor = "";
                            opt.style.color = "";
                        });
                    }, 2000);
                }
            });
        });
    }
    
    displayPair();
    
    console.log("Echo identification game setup complete");
}
switch(chapter.mechanics) {
    case "soundIdentification":
        setupSoundIdentificationGame(chapter);
        break;
    case "routineBuilding":
        setupRoutineBuildingGame(chapter);
        break;
    // ... الدوال السابقة ...
    case "selfRecognition":
        setupSelfRecognitionGame(chapter);  // الفصل 13
        break;
    case "pathFinding":
        setupPathFindingGame(chapter);      // الفصل 14
        break;
    case "timeManagement":
        setupTimeManagementGame(chapter);   // الفصل 15
        break;
    case "emotionMatching":
        setupEmotionMatchingGame(chapter);  // الفصل 16
        break;
    // ... الدوال اللاحقة ...
    default:
        setupDefaultGame(chapter);
}

switch(chapter.mechanics) {
    case "soundIdentification":
        setupSoundIdentificationGame(chapter);
        break;
    case "routineBuilding":
        setupRoutineBuildingGame(chapter);
        break;
    case "communication":
        setupCommunicationGame(chapter);
        break;
    case "emotionRecognition":
        setupEmotionRecognitionGame(chapter);
        break;
    case "memoryGame":
        setupMemoryGame(chapter);
        break;
    case "emotionSorting":
        setupEmotionSortingGame(chapter);
        break;
    case "realityTesting":
        setupRealityTestingGame(chapter);
        break;
    case "trustBuilding":
        setupTrustBuildingGame(chapter);
        break;
    case "memoryTraining":
        setupMemoryTrainingGame(chapter);
        break;
    case "voiceDiscrimination":
        setupVoiceDiscriminationGame(chapter);
        break;
    case "patternRecognition":
        setupPatternRecognitionGame(chapter);
        break;
    case "echoIdentification":
        setupEchoIdentificationGame(chapter);
        break;
    case "selfRecognition":
        setupSelfRecognitionGame(chapter);  // الفصل 13
        break;
    case "pathFinding":
        setupPathFindingGame(chapter);      // الفصل 14
        break;
    case "timeManagement":
        setupTimeManagementGame(chapter);   // الفصل 15
        break;
    case "emotionMatching":
        setupEmotionMatchingGame(chapter);  // الفصل 16
        break;
    case "sensoryFiltering":
        setupSensoryFilteringGame(chapter); // الفصل 17
        break;
    case "socialInteraction":
        setupSocialInteractionGame(chapter); // الفصل 18
        break;
    case "goalSetting":
        setupGoalSettingGame(chapter);      // الفصل 19
        break;
    case "integration":
        setupIntegrationGame(chapter);      // الفصل 20
        break;
    default:
        setupDefaultGame(chapter);
}








// ================================================
// دوال الفصول الناقصة 13-20
// ================================================

// دالة افتراضية للفصول التي ليس لها لعبة محددة
function setupDefaultGame(chapter) {
    const lang = gameData.player.language;
    
    console.log("Setting up default game for chapter:", chapter.id);
    
    gameMechanics.innerHTML = `
        <div class="game-instructions">
            <p>${lang === 'ar' ? 'هذا الفصل قيد التطوير. استخدم زر إكمال الفصل للمتابعة.' : 'This chapter is under development. Use the complete chapter button to continue.'}</p>
        </div>
        <div style="text-align: center; margin-top: 30px;">
            <button class="btn" id="auto-complete-btn">${lang === 'ar' ? 'إكمال الفصل' : 'Complete Chapter'}</button>
        </div>
    `;
    
    document.getElementById('auto-complete-btn').addEventListener('click', completeChapter);
}

// الفصل 13: التعرف على الذات
function setupSelfRecognitionGame(chapter) {
    const lang = gameData.player.language;
    
    console.log("Setting up self recognition game for chapter 13");
    
    gameMechanics.innerHTML = `
        <div class="game-instructions">
            <p>${lang === 'ar' ? 'انظر إلى الانعكاسات واختر الذي يمثلك الحقيقي:' : 'Look at the reflections and choose the one that represents your true self:'}</p>
        </div>
        
        <div class="reflection-game" style="display: grid; grid-template-columns: repeat(2, 1fr); gap: 20px; margin: 25px 0;">
            <div class="reflection-option" data-correct="false" style="padding: 20px; background: linear-gradient(135deg, #FF6B6B, #FF8E8E); border-radius: 15px; text-align: center; cursor: pointer; transition: all 0.3s ease;">
                <div style="font-size: 3rem; margin-bottom: 15px;">👑</div>
                <h4>${lang === 'ar' ? 'المثالي' : 'The Ideal'}</h4>
                <p>${lang === 'ar' ? 'قوي ولا يقهر' : 'Strong and invincible'}</p>
            </div>
            
            <div class="reflection-option" data-correct="false" style="padding: 20px; background: linear-gradient(135deg, #4ECDC4, #88D9D3); border-radius: 15px; text-align: center; cursor: pointer; transition: all 0.3s ease;">
                <div style="font-size: 3rem; margin-bottom: 15px;">😔</div>
                <h4>${lang === 'ar' ? 'الضعيف' : 'The Weak'}</h4>
                <p>${lang === 'ar' ? 'هش وعرضة للأذى' : 'Fragile and vulnerable'}</p>
            </div>
            
            <div class="reflection-option" data-correct="true" style="padding: 20px; background: linear-gradient(135deg, #FFD166, #FFE099); border-radius: 15px; text-align: center; cursor: pointer; transition: all 0.3s ease;">
                <div style="font-size: 3rem; margin-bottom: 15px;">😊</div>
                <h4>${lang === 'ar' ? 'المتوازن' : 'The Balanced'}</h4>
                <p>${lang === 'ar' ? 'به نقاط قوة وضعف' : 'Has strengths and weaknesses'}</p>
            </div>
            
            <div class="reflection-option" data-correct="false" style="padding: 20px; background: linear-gradient(135deg, #9D4EDD, #C77DFF); border-radius: 15px; text-align: center; cursor: pointer; transition: all 0.3s ease;">
                <div style="font-size: 3rem; margin-bottom: 15px;">🎭</div>
                <h4>${lang === 'ar' ? 'المتعدد' : 'The Multiple'}</h4>
                <p>${lang === 'ar' ? 'شخصيات مختلفة حسب الموقف' : 'Different personas for different situations'}</p>
            </div>
        </div>
    `;
    
    // إضافة مستمعي الأحداث
    const options = document.querySelectorAll('.reflection-option');
    options.forEach(option => {
        option.addEventListener('click', function() {
            const isCorrect = this.dataset.correct === 'true';
            
            if (isCorrect) {
                this.style.transform = "scale(1.05)";
                this.style.boxShadow = "0 0 20px rgba(255, 209, 102, 0.7)";
                
                gameData.points.hope += 10;
                gameData.points.insight += 15;
                updatePointsDisplay();
                
                const feedbackDiv = document.createElement('div');
                feedbackDiv.className = 'feedback-positive';
                feedbackDiv.innerHTML = lang === 'ar' ? 
                    '🎉 صحيح! الذات الحقيقية هي تلك المتوازنة التي تعترف بنقاط القوة والضعف.' : 
                    '🎉 Correct! The true self is the balanced one that acknowledges both strengths and weaknesses.';
                gameFeedback.innerHTML = '';
                gameFeedback.appendChild(feedbackDiv);
                gameFeedback.style.display = 'block';
                
                setTimeout(() => {
                    completeChapterBtn.style.display = 'block';
                }, 2000);
            } else {
                this.style.transform = "scale(0.95)";
                this.style.boxShadow = "0 0 20px rgba(255, 107, 107, 0.7)";
                
                const feedbackDiv = document.createElement('div');
                feedbackDiv.className = 'feedback-negative';
                feedbackDiv.innerHTML = lang === 'ar' ? 
                    '❌ ليس صحيحًا. هذا انعكاس مشوه. حاول مرة أخرى!' : 
                    '❌ Not correct. This is a distorted reflection. Try again!';
                gameFeedback.innerHTML = '';
                gameFeedback.appendChild(feedbackDiv);
                gameFeedback.style.display = 'block';
                
                setTimeout(() => {
                    this.style.transform = "";
                    this.style.boxShadow = "";
                    gameFeedback.style.display = 'none';
                }, 1500);
            }
        });
    });
}

// الفصل 14: إيجاد المسار
function setupPathFindingGame(chapter) {
    const lang = gameData.player.language;
    
    console.log("Setting up path finding game for chapter 14");
    
    // إنشاء متاهة بسيطة
    const maze = [
        ['S', 'P', 'W', 'P', 'P'],
        ['P', 'W', 'P', 'W', 'P'],
        ['P', 'P', 'P', 'P', 'P'],
        ['W', 'W', 'P', 'W', 'P'],
        ['P', 'P', 'P', 'W', 'E']
    ];
    
    let currentPosition = {x: 0, y: 0};
    let gameCompleted = false;
    
    gameMechanics.innerHTML = `
        <div class="game-instructions">
            <p>${lang === 'ar' ? 'جد المسار الصحيح من البداية (S) إلى النهاية (E):' : 'Find the correct path from Start (S) to End (E):'}</p>
            <p>${lang === 'ar' ? 'P = مسار، W = حائط' : 'P = Path, W = Wall'}</p>
        </div>
        
        <div class="maze-container" id="maze-container" style="display: grid; grid-template-columns: repeat(5, 1fr); gap: 10px; margin: 25px 0; max-width: 400px; margin-left: auto; margin-right: auto;">
            ${maze.map((row, y) => 
                row.map((cell, x) => `
                    <div class="maze-cell" data-x="${x}" data-y="${y}" data-type="${cell}"
                         style="width: 60px; height: 60px; display: flex; align-items: center; justify-content: center; 
                                border-radius: 8px; font-weight: bold; cursor: pointer; transition: all 0.3s ease;
                                ${cell === 'S' ? 'background: hsl(var(--primary)); color: white;' : 
                                  cell === 'E' ? 'background: hsl(var(--accent)); color: white;' :
                                  cell === 'W' ? 'background: hsl(var(--destructive)); color: white;' :
                                  'background: hsl(var(--muted)); color: hsl(var(--foreground));'}">
                        ${cell === 'S' ? (lang === 'ar' ? 'بد' : 'S') : 
                          cell === 'E' ? (lang === 'ar' ? 'ن' : 'E') :
                          cell === 'W' ? (lang === 'ar' ? 'ح' : 'W') : 
                          (lang === 'ar' ? 'م' : 'P')}
                    </div>
                `).join('')
            ).join('')}
        </div>
        
        <div style="text-align: center; margin-top: 20px;">
            <p id="path-message">${lang === 'ar' ? 'انقر على الخلايا لبناء المسار' : 'Click cells to build path'}</p>
            <button class="btn" id="check-path">${lang === 'ar' ? 'تحقق من المسار' : 'Check Path'}</button>
            <button class="btn btn-secondary" id="reset-path" style="margin-left: 10px;">${lang === 'ar' ? 'إعادة' : 'Reset'}</button>
        </div>
        
        <div class="path-display" style="margin-top: 20px; padding: 15px; background: hsl(var(--muted)); border-radius: 10px;">
            <p>${lang === 'ar' ? 'المسار الحالي:' : 'Current path:'} <span id="current-path">${lang === 'ar' ? 'بداية' : 'Start'}</span></p>
        </div>
    `;
    
    const path = [{x: 0, y: 0}];
    
    // إضافة مستمعي الأحداث
    const cells = document.querySelectorAll('.maze-cell');
    const checkBtn = document.getElementById('check-path');
    const resetBtn = document.getElementById('reset-path');
    const pathMessage = document.getElementById('path-message');
    const currentPath = document.getElementById('current-path');
    
    cells.forEach(cell => {
        cell.addEventListener('click', function() {
            if (gameCompleted) return;
            
            const x = parseInt(this.dataset.x);
            const y = parseInt(this.dataset.y);
            const type = this.dataset.type;
            
            if (type === 'W') {
                this.style.animation = "shake 0.5s";
                pathMessage.textContent = lang === 'ar' ? '❌ لا يمكن المرور عبر الحائط!' : '❌ Cannot pass through wall!';
                pathMessage.style.color = "hsl(var(--destructive))";
                
                setTimeout(() => {
                    this.style.animation = "";
                }, 500);
                return;
            }
            
            const lastCell = path[path.length - 1];
            const isAdjacent = Math.abs(x - lastCell.x) + Math.abs(y - lastCell.y) === 1;
            
            if (!isAdjacent) {
                pathMessage.textContent = lang === 'ar' ? '⚠️ يجب أن يكون الخيار مجاوراً للخطوة السابقة' : '⚠️ Must be adjacent to previous step';
                pathMessage.style.color = "hsl(var(--accent))";
                return;
            }
            
            // إضافة إلى المسار
            path.push({x, y});
            this.style.background = "hsl(var(--success))";
            this.style.color = "white";
            
            // تحديث عرض المسار
            currentPath.textContent += ` → (${x},${y})`;
            pathMessage.textContent = lang === 'ar' ? '✅ تمت إضافة خطوة إلى المسار' : '✅ Step added to path';
            pathMessage.style.color = "hsl(var(--success))";
            
            // إذا وصلنا للنهاية
            if (type === 'E') {
                gameCompleted = true;
                pathMessage.textContent = lang === 'ar' ? '🎉 وصلت إلى النهاية!' : '🎉 Reached the end!';
                
                gameData.points.hope += 12;
                gameData.points.insight += 10;
                updatePointsDisplay();
                
                setTimeout(() => {
                    completeChapterBtn.style.display = 'block';
                }, 2000);
            }
        });
    });
    
    checkBtn.addEventListener('click', () => {
        // المسار الصحيح مسبقاً
        const correctPath = [
            {x: 0, y: 0}, {x: 1, y: 0}, {x: 0, y: 1}, {x: 0, y: 2},
            {x: 1, y: 2}, {x: 2, y: 2}, {x: 3, y: 2}, {x: 4, y: 2},
            {x: 4, y: 3}, {x: 4, y: 4}
        ];
        
        // تحقق إذا كان المسار صحيحاً
        const isCorrect = JSON.stringify(path) === JSON.stringify(correctPath);
        
        if (isCorrect) {
            gameData.points.hope += 15;
            gameData.points.insight += 12;
            updatePointsDisplay();
            
            const feedbackDiv = document.createElement('div');
            feedbackDiv.className = 'feedback-positive';
            feedbackDiv.innerHTML = lang === 'ar' ? 
                '🎉 ممتاز! لقد وجدت المسار الصحيح للمتاهة.' : 
                '🎉 Excellent! You found the correct path through the maze.';
            gameFeedback.innerHTML = '';
            gameFeedback.appendChild(feedbackDiv);
            gameFeedback.style.display = 'block';
            
            setTimeout(() => {
                completeChapterBtn.style.display = 'block';
            }, 2000);
        } else {
            const feedbackDiv = document.createElement('div');
            feedbackDiv.className = 'feedback-negative';
            feedbackDiv.innerHTML = lang === 'ar' ? 
                '❌ المسار غير صحيح. حاول مرة أخرى!' : 
                '❌ Path is not correct. Try again!';
            gameFeedback.innerHTML = '';
            gameFeedback.appendChild(feedbackDiv);
            gameFeedback.style.display = 'block';
        }
    });
    
    resetBtn.addEventListener('click', () => {
        path.length = 1; // إعادة تعيين المسار
        pathMessage.textContent = lang === 'ar' ? 'انقر على الخلايا لبناء المسار' : 'Click cells to build path';
        pathMessage.style.color = "";
        currentPath.textContent = lang === 'ar' ? 'بداية' : 'Start';
        gameCompleted = false;
        
        cells.forEach(cell => {
            const type = cell.dataset.type;
            if (type === 'S') {
                cell.style.background = "hsl(var(--primary))";
                cell.style.color = "white";
            } else if (type === 'E') {
                cell.style.background = "hsl(var(--accent))";
                cell.style.color = "white";
            } else if (type === 'W') {
                cell.style.background = "hsl(var(--destructive))";
                cell.style.color = "white";
            } else {
                cell.style.background = "hsl(var(--muted))";
                cell.style.color = "hsl(var(--foreground))";
            }
        });
    });
}

// الفصل 15: إدارة الوقت
function setupTimeManagementGame(chapter) {
    const lang = gameData.player.language;
    
    console.log("Setting up time management game for chapter 15");
    
    gameMechanics.innerHTML = `
        <div class="game-instructions">
            <p>${lang === 'ar' ? 'رتب المهام حسب الأولوية الصحيحة لإدارة وقتك:' : 'Arrange tasks in the correct priority order to manage your time:'}</p>
        </div>
        
        <div class="time-game" style="margin: 25px 0;">
            <div id="tasks-container" style="display: flex; flex-direction: column; gap: 15px;">
                <div class="task-item" data-priority="1" draggable="true" style="padding: 15px; background: white; border-radius: 10px; border: 2px solid hsl(var(--border)); cursor: grab;">
                    <div style="display: flex; align-items: center; gap: 10px;">
                        <span style="font-size: 1.2rem;">📝</span>
                        <span>${lang === 'ar' ? 'موعد طبي مهم (اليوم)' : 'Important medical appointment (Today)'}</span>
                    </div>
                </div>
                
                <div class="task-item" data-priority="4" draggable="true" style="padding: 15px; background: white; border-radius: 10px; border: 2px solid hsl(var(--border)); cursor: grab;">
                    <div style="display: flex; align-items: center; gap: 10px;">
                        <span style="font-size: 1.2rem;">🎮</span>
                        <span>${lang === 'ar' ? 'لعب ألعاب الفيديو' : 'Playing video games'}</span>
                    </div>
                </div>
                
                <div class="task-item" data-priority="2" draggable="true" style="padding: 15px; background: white; border-radius: 10px; border: 2px solid hsl(var(--border)); cursor: grab;">
                    <div style="display: flex; align-items: center; gap: 10px;">
                        <span style="font-size: 1.2rem;">🛒</span>
                        <span>${lang === 'ar' ? 'شراء احتياجات أساسية (غداً)' : 'Buying basic necessities (Tomorrow)'}</span>
                    </div>
                </div>
                
                <div class="task-item" data-priority="3" draggable="true" style="padding: 15px; background: white; border-radius: 10px; border: 2px solid hsl(var(--border)); cursor: grab;">
                    <div style="display: flex; align-items: center; gap: 10px;">
                        <span style="font-size: 1.2rem;">📧</span>
                        <span>${lang === 'ar' ? 'الرد على رسائل البريد الإلكتروني' : 'Responding to emails'}</span>
                    </div>
                </div>
            </div>
        </div>
        
        <div style="margin-top: 30px; text-align: center;">
            <p>${lang === 'ar' => 'اسحب وأسقط المهام لترتيبها حسب الأولوية (من الأعلى للأهم):' : 'Drag and drop tasks to arrange them by priority (top is most important):'}</p>
            <button class="btn" id="check-order">${lang === 'ar' ? 'تحقق من الترتيب' : 'Check Order'}</button>
        </div>
    `;
    
    // جعل العناصر قابلة للسحب
    const taskItems = document.querySelectorAll('.task-item');
    const container = document.getElementById('tasks-container');
    let draggedItem = null;
    
    taskItems.forEach(item => {
        item.addEventListener('dragstart', function() {
            draggedItem = this;
            setTimeout(() => {
                this.style.display = 'none';
            }, 0);
        });
        
        item.addEventListener('dragend', function() {
            setTimeout(() => {
                draggedItem.style.display = 'flex';
                draggedItem = null;
            }, 0);
        });
        
        item.addEventListener('dragover', function(e) {
            e.preventDefault();
            this.style.border = "2px dashed hsl(var(--primary))";
        });
        
        item.addEventListener('dragleave', function() {
            this.style.border = "2px solid hsl(var(--border))";
        });
        
        item.addEventListener('drop', function(e) {
            e.preventDefault();
            this.style.border = "2px solid hsl(var(--border))";
            
            if (draggedItem && draggedItem !== this) {
                const allItems = Array.from(container.children);
                const draggedIndex = allItems.indexOf(draggedItem);
                const targetIndex = allItems.indexOf(this);
                
                if (draggedIndex < targetIndex) {
                    container.insertBefore(draggedItem, this.nextSibling);
                } else {
                    container.insertBefore(draggedItem, this);
                }
            }
        });
    });
    
    // زر التحقق
    document.getElementById('check-order').addEventListener('click', () => {
        const items = Array.from(container.children);
        let isCorrect = true;
        
        items.forEach((item, index) => {
            const priority = parseInt(item.dataset.priority);
            if (priority !== index + 1) {
                isCorrect = false;
                item.style.border = "2px solid hsl(var(--destructive))";
            } else {
                item.style.border = "2px solid hsl(var(--success))";
            }
        });
        
        if (isCorrect) {
            gameData.points.hope += 15;
            gameData.points.insight += 10;
            updatePointsDisplay();
            
            const feedbackDiv = document.createElement('div');
            feedbackDiv.className = 'feedback-positive';
            feedbackDiv.innerHTML = lang === 'ar' ? 
                '🎉 ممتاز! لقد نظمت وقتك بشكل صحيح. برج الساعة يعود للعمل بشكل منتظم.' : 
                '🎉 Excellent! You\'ve organized your time correctly. The clock tower is working regularly again.';
            gameFeedback.innerHTML = '';
            gameFeedback.appendChild(feedbackDiv);
            gameFeedback.style.display = 'block';
            
            setTimeout(() => {
                completeChapterBtn.style.display = 'block';
            }, 2000);
        } else {
            gameData.points.insight += 3;
            updatePointsDisplay();
            
            const feedbackDiv = document.createElement('div');
            feedbackDiv.className = 'feedback-negative';
            feedbackDiv.innerHTML = lang === 'ar' ? 
                '❌ الترتيب غير صحيح. حاول مرة أخرى!' : 
                '❌ Order is not correct. Try again!';
            gameFeedback.innerHTML = '';
            gameFeedback.appendChild(feedbackDiv);
            gameFeedback.style.display = 'block';
            
            setTimeout(() => {
                taskItems.forEach(item => {
                    item.style.border = "2px solid hsl(var(--border))";
                });
                gameFeedback.style.display = 'none';
            }, 2000);
        }
    });
}

// الفصل 16: مطابقة المشاعر
function setupEmotionMatchingGame(chapter) {
    const lang = gameData.player.language;
    
    console.log("Setting up emotion matching game for chapter 16");
    
    gameMechanics.innerHTML = `
        <div class="game-instructions">
            <p>${lang === 'ar' ? 'طابق كل نبات مع العناية المناسبة له:' : 'Match each plant with the appropriate care for it:'}</p>
        </div>
        
        <div class="matching-game" style="display: grid; grid-template-columns: repeat(2, 1fr); gap: 20px; margin: 25px 0;">
            <!-- النباتات -->
            <div class="plant" data-id="1" style="padding: 20px; background: linear-gradient(135deg, #FF6B6B, #FF8E8E); border-radius: 15px; text-align: center;">
                <div style="font-size: 3rem; margin-bottom: 10px;">🌵</div>
                <h4>${lang === 'ar' ? 'الصبار' : 'Cactus'}</h4>
                <p style="font-size: 0.9rem; color: rgba(255,255,255,0.9);">${lang === 'ar' ? 'قليل الماء' : 'Needs little water'}</p>
            </div>
            
            <div class="plant" data-id="2" style="padding: 20px; background: linear-gradient(135deg, #4ECDC4, #88D9D3); border-radius: 15px; text-align: center;">
                <div style="font-size: 3rem; margin-bottom: 10px;">🌿</div>
                <h4>${lang === 'ar' ? 'نبات الظل' : 'Shade Plant'}</h4>
                <p style="font-size: 0.9rem; color: rgba(255,255,255,0.9);">${lang === 'ar' => 'لا يتحمل الشمس المباشرة' : 'Cannot tolerate direct sun'}</p>
            </div>
            
            <div class="plant" data-id="3" style="padding: 20px; background: linear-gradient(135deg, #FFD166, #FFE099); border-radius: 15px; text-align: center;">
                <div style="font-size: 3rem; margin-bottom: 10px;">🌻</div>
                <h4>${lang === 'ar' ? 'عباد الشمس' : 'Sunflower'}</h4>
                <p style="font-size: 0.9rem; color: rgba(255,255,255,0.9);">${lang === 'ar' ? 'يحتاج شمس كاملة' : 'Needs full sun'}</p>
            </div>
            
            <div class="plant" data-id="4" style="padding: 20px; background: linear-gradient(135deg, #9D4EDD, #C77DFF); border-radius: 15px; text-align: center;">
                <div style="font-size: 3rem; margin-bottom: 10px;">💧</div>
                <h4>${lang === 'ar' ? 'نبات مائي' : 'Aquatic Plant'}</h4>
                <p style="font-size: 0.9rem; color: rgba(255,255,255,0.9);">${lang === 'ar' ? 'يحتاج الكثير من الماء' : 'Needs lots of water'}</p>
            </div>
            
            <!-- العناية -->
            <div class="care" data-match="3" draggable="true" style="padding: 15px; background: white; border-radius: 10px; border: 2px solid hsl(var(--border)); cursor: grab;">
                <p>${lang === 'ar' ? 'وضع في مكان مشمس' : 'Place in sunny spot'}</p>
            </div>
            
            <div class="care" data-match="1" draggable="true" style="padding: 15px; background: white; border-radius: 10px; border: 2px solid hsl(var(--border)); cursor: grab;">
                <p>${lang === 'ar' ? 'ري مرة كل أسبوعين' : 'Water once every two weeks'}</p>
            </div>
            
            <div class="care" data-match="4" draggable="true" style="padding: 15px; background: white; border-radius: 10px; border: 2px solid hsl(var(--border)); cursor: grab;">
                <p>${lang === 'ar' ? 'الحفاظ على التربة رطبة دائماً' : 'Keep soil always moist'}</p>
            </div>
            
            <div class="care" data-match="2" draggable="true" style="padding: 15px; background: white; border-radius: 10px; border: 2px solid hsl(var(--border)); cursor: grab;">
                <p>${lang === 'ar' ? 'وضع في مكان مظلل' : 'Place in shaded area'}</p>
            </div>
        </div>
        
        <div style="margin-top: 30px; text-align: center;">
            <button class="btn" id="check-matches">${lang === 'ar' ? 'تحقق من المطابقة' : 'Check Matches'}</button>
        </div>
        
        <div style="margin-top: 20px; padding: 15px; background: hsl(var(--muted)); border-radius: 10px;">
            <p style="font-size: 0.9rem; color: hsl(var(--muted-foreground));">
                ${lang === 'ar' ? 'اسحب كل عناية إلى النبات المناسب' : 'Drag each care to the appropriate plant'}
            </p>
        </div>
    `;
    
    let matches = {};
    
    // جعل عناصر العناية قابلة للسحب
    const careItems = document.querySelectorAll('.care');
    const plants = document.querySelectorAll('.plant');
    
    careItems.forEach(care => {
        care.addEventListener('dragstart', function(e) {
            e.dataTransfer.setData('text/plain', this.dataset.match);
        });
    });
    
    plants.forEach(plant => {
        plant.addEventListener('dragover', function(e) {
            e.preventDefault();
            this.style.transform = "scale(1.05)";
        });
        
        plant.addEventListener('dragleave', function() {
            this.style.transform = "scale(1)";
        });
        
        plant.addEventListener('drop', function(e) {
            e.preventDefault();
            this.style.transform = "scale(1)";
            
            const careMatch = e.dataTransfer.getData('text/plain');
            const plantId = this.dataset.id;
            
            matches[plantId] = careMatch;
            
            // إظهار التأثير
            this.style.boxShadow = "0 0 20px rgba(0,0,0,0.2)";
            setTimeout(() => {
                this.style.boxShadow = "";
            }, 500);
        });
    });
    
    // زر التحقق
    document.getElementById('check-matches').addEventListener('click', () => {
        let isCorrect = true;
        
        // التحقق من كل نبات
        for (let i = 1; i <= 4; i++) {
            if (matches[i] !== i.toString()) {
                isCorrect = false;
                break;
            }
        }
        
        if (isCorrect) {
            gameData.points.hope += 18;
            gameData.points.insight += 15;
            updatePointsDisplay();
            
            const feedbackDiv = document.createElement('div');
            feedbackDiv.className = 'feedback-positive';
            feedbackDiv.innerHTML = lang === 'ar' ? 
                '🎉 ممتاز! جميع النباتات تلقت العناية المناسبة. الحديقة تتفتح بألوان زاهية.' : 
                '🎉 Excellent! All plants received appropriate care. The garden is blooming with vibrant colors.';
            gameFeedback.innerHTML = '';
            gameFeedback.appendChild(feedbackDiv);
            gameFeedback.style.display = 'block';
            
            setTimeout(() => {
                completeChapterBtn.style.display = 'block';
            }, 2000);
        } else {
            gameData.points.insight += 5;
            updatePointsDisplay();
            
            const feedbackDiv = document.createElement('div');
            feedbackDiv.className = 'feedback-negative';
            feedbackDiv.innerHTML = lang === 'ar' ? 
                '❌ بعض المطابقات غير صحيحة. حاول مرة أخرى!' : 
                '❌ Some matches are incorrect. Try again!';
            gameFeedback.innerHTML = '';
            gameFeedback.appendChild(feedbackDiv);
            gameFeedback.style.display = 'block';
            
            setTimeout(() => {
                gameFeedback.style.display = 'none';
            }, 2000);
        }
    });
}

// دوال الفصول 17-20 (تستخدم الدالة الافتراضية)
function setupSensoryFilteringGame(chapter) {
    setupDefaultGame(chapter);
}

function setupSocialInteractionGame(chapter) {
    setupDefaultGame(chapter);
}

function setupGoalSettingGame(chapter) {
    setupDefaultGame(chapter);
}

function setupIntegrationGame(chapter) {
    setupDefaultGame(chapter);
}










    </script>
</body>
</html>
