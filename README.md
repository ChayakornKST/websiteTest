<!DOCTYPE html>
<html lang="th">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ระบบแนะแนวและประชาสัมพันธ์อัจฉริยะ - วิทยาลัยอาชีวศึกษาร้อยเอ็ด "RVC Smart Career PR System"</title>
    <style>
        body {
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            margin: 0;
            padding: 0;
            background: linear-gradient(135deg, #1e40af 0%, #3b82f6 50%, #60a5fa 100%);
            min-height: 100%;
            color: #333;
        }

        .container {
            max-width: 900px;
            margin: 0 auto;
            padding: 20px;
        }

        /* Landing Page Styles */
        .landing-page {
            display: block;
        }

        .landing-page.hidden {
            display: none;
        }

        .hero-section {
            background: linear-gradient(135deg, rgba(255,255,255,0.95), rgba(255,255,255,0.9));
            border-radius: 20px;
            padding: 40px;
            margin-bottom: 30px;
            box-shadow: 0 20px 60px rgba(0,0,0,0.1);
            text-align: center;
            position: relative;
            overflow: hidden;
        }

        .hero-section::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle, rgba(59,130,246,0.1) 0%, transparent 70%);
            animation: float 6s ease-in-out infinite;
        }

        @keyframes float {
            0%, 100% { transform: translateY(0px) rotate(0deg); }
            50% { transform: translateY(-20px) rotate(180deg); }
        }

        .logo-placeholder {
            width: 120px;
            height: 120px;
            background: linear-gradient(135deg, #1e40af, #3b82f6);
            border-radius: 50%;
            margin: 0 auto 20px;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-weight: bold;
            font-size: 36px;
            box-shadow: 0 10px 30px rgba(30,64,175,0.3);
            animation: pulse 2s infinite;
            position: relative;
            z-index: 2;
        }

        @keyframes pulse {
            0% { transform: scale(1); }
            50% { transform: scale(1.05); }
            100% { transform: scale(1); }
        }

        .main-title {
            color: #1e40af;
            font-size: 32px;
            font-weight: bold;
            margin: 20px 0;
            position: relative;
            z-index: 2;
        }

        .subtitle {
            color: #1e40af;
            font-size: 20px;
            font-weight: bold;
            margin-bottom: 20px;
            position: relative;
            z-index: 2;
        }

        .credit {
            font-size: 14px;
            color: #6b7280;
            font-style: italic;
            position: relative;
            z-index: 2;
        }

        .intro-content {
            background: white;
            border-radius: 15px;
            padding: 30px;
            margin-bottom: 30px;
            box-shadow: 0 10px 40px rgba(0,0,0,0.1);
            position: relative;
            z-index: 2;
        }

        .intro-title {
            color: #1e40af;
            font-size: 24px;
            font-weight: bold;
            margin-bottom: 20px;
            text-align: center;
        }

        .intro-text {
            font-size: 16px;
            line-height: 1.6;
            color: #374151;
            margin-bottom: 15px;
        }

        .features-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 20px;
            margin: 30px 0;
        }

        .feature-card {
            background: white;
            border-radius: 15px;
            padding: 25px;
            text-align: center;
            box-shadow: 0 8px 25px rgba(0,0,0,0.1);
            transition: all 0.3s ease;
            border: 2px solid transparent;
        }

        .feature-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 15px 40px rgba(30,64,175,0.2);
            border-color: #3b82f6;
        }

        .feature-icon {
            width: 80px;
            height: 80px;
            margin: 0 auto 15px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 36px;
            color: white;
            background: linear-gradient(135deg, #1e40af, #3b82f6);
        }

        .feature-title {
            color: #1e40af;
            font-size: 18px;
            font-weight: bold;
            margin-bottom: 10px;
        }

        .feature-desc {
            color: #6b7280;
            font-size: 14px;
            line-height: 1.5;
        }

        .aptitude-categories {
            background: white;
            border-radius: 15px;
            padding: 30px;
            margin-bottom: 30px;
            box-shadow: 0 10px 40px rgba(0,0,0,0.1);
        }

        .categories-title {
            color: #1e40af;
            font-size: 24px;
            font-weight: bold;
            margin-bottom: 25px;
            text-align: center;
        }

        .categories-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 15px;
        }

        .category-item {
            background: linear-gradient(135deg, #f8fafc, #e2e8f0);
            border-radius: 12px;
            padding: 20px;
            text-align: center;
            transition: all 0.3s ease;
            border: 2px solid transparent;
        }

        .category-item:hover {
            background: linear-gradient(135deg, #dbeafe, #bfdbfe);
            border-color: #3b82f6;
            transform: scale(1.02);
        }

        .category-icon {
            font-size: 48px;
            margin-bottom: 10px;
            display: block;
        }

        .category-name {
            color: #1e40af;
            font-weight: bold;
            font-size: 16px;
            margin-bottom: 8px;
        }

        .category-majors {
            color: #6b7280;
            font-size: 12px;
            line-height: 1.4;
        }

        .steps-section {
            background: white;
            border-radius: 15px;
            padding: 30px;
            margin-bottom: 30px;
            box-shadow: 0 10px 40px rgba(0,0,0,0.1);
        }

        .steps-title {
            color: #1e40af;
            font-size: 24px;
            font-weight: bold;
            margin-bottom: 25px;
            text-align: center;
        }

        .steps-list {
            display: flex;
            flex-direction: column;
            gap: 20px;
        }

        .step-item {
            display: flex;
            align-items: center;
            gap: 20px;
            padding: 20px;
            background: linear-gradient(135deg, #f8fafc, #e2e8f0);
            border-radius: 12px;
            transition: all 0.3s ease;
        }

        .step-item:hover {
            background: linear-gradient(135deg, #dbeafe, #bfdbfe);
            transform: translateX(10px);
        }

        .step-number {
            width: 50px;
            height: 50px;
            background: linear-gradient(135deg, #1e40af, #3b82f6);
            color: white;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: bold;
            font-size: 20px;
            flex-shrink: 0;
        }

        .step-content {
            flex: 1;
        }

        .step-title {
            color: #1e40af;
            font-weight: bold;
            margin-bottom: 5px;
        }

        .step-desc {
            color: #6b7280;
            font-size: 14px;
        }

        .ai-chat-section {
            background: linear-gradient(135deg, #10b981, #059669);
            color: white;
            border-radius: 15px;
            padding: 30px;
            margin: 30px 0;
            text-align: center;
            box-shadow: 0 10px 40px rgba(16,185,129,0.3);
            position: relative;
            overflow: hidden;
        }

        .ai-chat-section::before {
            content: '';
            position: absolute;
            top: -50%;
            right: -50%;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle, rgba(255,255,255,0.1) 0%, transparent 70%);
            animation: float 8s ease-in-out infinite reverse;
        }

        .ai-chat-title {
            font-size: 28px;
            font-weight: bold;
            margin-bottom: 15px;
            position: relative;
            z-index: 2;
        }

        .ai-chat-desc {
            font-size: 16px;
            margin-bottom: 25px;
            opacity: 0.9;
            position: relative;
            z-index: 2;
        }

        .ai-chat-btn {
            background: white;
            color: #059669;
            border: none;
            padding: 15px 30px;
            font-size: 18px;
            font-weight: bold;
            border-radius: 25px;
            cursor: pointer;
            transition: all 0.3s ease;
            box-shadow: 0 8px 20px rgba(0,0,0,0.1);
            position: relative;
            z-index: 2;
        }

        .ai-chat-btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 12px 30px rgba(0,0,0,0.2);
            background: #f0fdf4;
        }

        /* Dashboard Styles */
        .dashboard-section {
            background: white;
            border-radius: 15px;
            padding: 30px;
            margin: 30px 0;
            box-shadow: 0 10px 40px rgba(0,0,0,0.1);
        }

        .dashboard-title {
            color: #1e40af;
            font-size: 28px;
            font-weight: bold;
            margin-bottom: 30px;
            text-align: center;
        }

        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 20px;
            margin-bottom: 40px;
        }

        .stat-card {
            background: linear-gradient(135deg, #f8fafc, #e2e8f0);
            border-radius: 15px;
            padding: 25px;
            display: flex;
            align-items: center;
            gap: 20px;
            transition: all 0.3s ease;
            border: 2px solid transparent;
        }

        .stat-card:hover {
            background: linear-gradient(135deg, #dbeafe, #bfdbfe);
            border-color: #3b82f6;
            transform: translateY(-5px);
            box-shadow: 0 15px 40px rgba(30,64,175,0.2);
        }

        .stat-icon {
            width: 60px;
            height: 60px;
            background: linear-gradient(135deg, #1e40af, #3b82f6);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 24px;
            color: white;
            flex-shrink: 0;
        }

        .stat-content {
            flex: 1;
        }

        .stat-number {
            font-size: 32px;
            font-weight: bold;
            color: #1e40af;
            line-height: 1;
            margin-bottom: 5px;
        }

        .stat-label {
            color: #6b7280;
            font-size: 14px;
            font-weight: 500;
        }

        .section-subtitle {
            color: #1e40af;
            font-size: 20px;
            font-weight: bold;
            margin-bottom: 20px;
            text-align: center;
        }

        .popular-majors-section,
        .aptitude-distribution,
        .recent-activity {
            background: #f8fafc;
            border-radius: 12px;
            padding: 25px;
            margin-bottom: 25px;
        }

        .popular-majors-chart {
            display: flex;
            flex-direction: column;
            gap: 15px;
        }

        .major-rank-item {
            display: flex;
            align-items: center;
            gap: 15px;
            background: white;
            border-radius: 10px;
            padding: 20px;
            transition: all 0.3s ease;
            border: 2px solid transparent;
        }

        .major-rank-item:hover {
            border-color: #3b82f6;
            transform: translateX(10px);
            box-shadow: 0 8px 25px rgba(30,64,175,0.15);
        }

        .rank-badge {
            width: 50px;
            height: 50px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: bold;
            font-size: 18px;
            color: white;
            flex-shrink: 0;
        }

        .rank-1 { background: linear-gradient(135deg, #fbbf24, #f59e0b); }
        .rank-2 { background: linear-gradient(135deg, #9ca3af, #6b7280); }
        .rank-3 { background: linear-gradient(135deg, #d97706, #b45309); }

        .major-info {
            flex: 1;
        }

        .major-name {
            font-size: 18px;
            font-weight: bold;
            color: #1e40af;
            margin-bottom: 5px;
        }

        .major-stats {
            color: #6b7280;
            font-size: 14px;
        }

        .major-percentage {
            font-size: 24px;
            font-weight: bold;
            color: #059669;
            text-align: right;
        }

        .distribution-chart {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 15px;
        }

        .distribution-item {
            background: white;
            border-radius: 10px;
            padding: 20px;
            text-align: center;
            transition: all 0.3s ease;
        }

        .distribution-item:hover {
            transform: scale(1.05);
            box-shadow: 0 8px 25px rgba(0,0,0,0.1);
        }

        .distribution-icon {
            font-size: 36px;
            margin-bottom: 10px;
            display: block;
        }

        .distribution-name {
            font-weight: bold;
            color: #1e40af;
            margin-bottom: 5px;
        }

        .distribution-count {
            color: #6b7280;
            font-size: 14px;
        }

        .activity-list {
            display: flex;
            flex-direction: column;
            gap: 12px;
        }

        .activity-item {
            display: flex;
            align-items: center;
            gap: 15px;
            background: white;
            border-radius: 8px;
            padding: 15px;
            transition: all 0.3s ease;
        }

        .activity-item:hover {
            background: #e0f2fe;
            transform: translateX(5px);
        }

        .activity-icon {
            width: 40px;
            height: 40px;
            background: linear-gradient(135deg, #10b981, #059669);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 16px;
            flex-shrink: 0;
        }

        .activity-content {
            flex: 1;
        }

        .activity-text {
            color: #374151;
            font-size: 14px;
            margin-bottom: 2px;
        }

        .activity-time {
            color: #9ca3af;
            font-size: 12px;
        }

        /* Top 3 Ranking Styles */
        .top-rankings {
            background: linear-gradient(135deg, #fef3c7, #fde68a);
            border-radius: 15px;
            padding: 25px;
            margin: 25px 0;
            border: 2px solid #f59e0b;
        }

        .ranking-title {
            color: #92400e;
            font-size: 22px;
            font-weight: bold;
            text-align: center;
            margin-bottom: 20px;
        }

        .ranking-list {
            display: flex;
            flex-direction: column;
            gap: 15px;
        }

        .ranking-item {
            background: white;
            border-radius: 12px;
            padding: 20px;
            display: flex;
            align-items: center;
            gap: 20px;
            box-shadow: 0 4px 15px rgba(0,0,0,0.1);
            transition: all 0.3s ease;
        }

        .ranking-item:hover {
            transform: translateY(-3px);
            box-shadow: 0 8px 25px rgba(0,0,0,0.15);
        }

        .ranking-medal {
            width: 60px;
            height: 60px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 24px;
            color: white;
            font-weight: bold;
            flex-shrink: 0;
        }

        .medal-1 { background: linear-gradient(135deg, #fbbf24, #f59e0b); }
        .medal-2 { background: linear-gradient(135deg, #9ca3af, #6b7280); }
        .medal-3 { background: linear-gradient(135deg, #d97706, #b45309); }

        .ranking-content {
            flex: 1;
        }

        .ranking-major {
            font-size: 18px;
            font-weight: bold;
            color: #1e40af;
            margin-bottom: 8px;
        }

        .ranking-description {
            color: #6b7280;
            font-size: 14px;
            line-height: 1.4;
        }

        .ranking-score {
            text-align: right;
            color: #059669;
            font-weight: bold;
        }

        .ranking-percentage {
            font-size: 24px;
            line-height: 1;
        }

        .ranking-label {
            font-size: 12px;
            opacity: 0.8;
        }

        .cta-section {
            text-align: center;
            margin: 40px 0;
        }

        .start-btn {
            background: linear-gradient(135deg, #1e40af, #3b82f6);
            color: white;
            border: none;
            padding: 40px 60px;
            font-size: 25px;
            font-weight: bold;
            border-radius: 50px;
            cursor: pointer;
            transition: all 0.3s ease;
            box-shadow: 0 10px 30px rgba(30,64,175,0.3);
            animation: glow 2s infinite alternate;
        }

        @keyframes glow {
            from { box-shadow: 0 10px 30px rgba(30,64,175,0.3); }
            to { box-shadow: 0 15px 40px rgba(30,64,175,0.5); }
        }

        .start-btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 20px 50px rgba(30,64,175,0.4);
        }

        .test-section {
            display: none;
        }

        .test-section.show {
            display: block;
        }

        .header {
            background: white;
            border-radius: 15px;
            padding: 25px;
            margin-bottom: 20px;
            box-shadow: 0 8px 32px rgba(0,0,0,0.1);
            text-align: center;
        }

        .privacy-notice {
            background: #e0f2fe;
            border: 1px solid #0288d1;
            border-radius: 8px;
            padding: 12px;
            margin: 20px 0;
            font-size: 14px;
            color: #01579b;
        }

        .section {
            background: white;
            border-radius: 15px;
            padding: 25px;
            margin-bottom: 20px;
            box-shadow: 0 8px 32px rgba(0,0,0,0.1);
        }

        .section-title {
            color: #4f46e5;
            font-size: 20px;
            font-weight: bold;
            margin-bottom: 20px;
            border-bottom: 2px solid #e5e7eb;
            padding-bottom: 10px;
        }

        .form-group {
            margin-bottom: 15px;
        }

        .form-label {
            display: block;
            font-weight: 600;
            margin-bottom: 5px;
            color: #374151;
        }

        .form-input {
            width: 100%;
            padding: 12px;
            border: 2px solid #e5e7eb;
            border-radius: 8px;
            font-size: 16px;
            transition: border-color 0.3s;
        }

        .form-input:focus {
            outline: none;
            border-color: #4f46e5;
        }

        .required {
            color: #ef4444;
        }

        .progress-bar {
            background: #e5e7eb;
            border-radius: 10px;
            height: 20px;
            margin: 20px 0;
            overflow: hidden;
        }

        .progress-fill {
            background: linear-gradient(90deg, #4f46e5, #7c3aed);
            height: 100%;
            transition: width 0.3s ease;
            border-radius: 10px;
        }

        .progress-text {
            text-align: center;
            margin-top: 10px;
            font-weight: 600;
            color: #4f46e5;
        }

        .question-group {
            margin-bottom: 30px;
        }

        .group-header {
            background: linear-gradient(135deg, #4f46e5, #7c3aed);
            color: white;
            padding: 15px 20px;
            border-radius: 10px;
            font-weight: bold;
            font-size: 18px;
            margin-bottom: 20px;
        }

        .question-item {
            background: #f8fafc;
            border: 2px solid #e5e7eb;
            border-radius: 12px;
            padding: 20px;
            margin-bottom: 15px;
            transition: all 0.3s ease;
        }

        .question-item:hover {
            border-color: #4f46e5;
            box-shadow: 0 4px 12px rgba(79, 70, 229, 0.1);
        }

        .question-text {
            font-size: 16px;
            font-weight: 500;
            margin-bottom: 15px;
            color: #374151;
        }

        .answer-area {
            display: flex;
            align-items: center;
            gap: 15px;
            flex-wrap: wrap;
        }

        .score-chips {
            display: flex;
            gap: 8px;
            flex-wrap: wrap;
        }

        .score-chip {
            width: 40px;
            height: 40px;
            border-radius: 50%;
            background: #4f46e5;
            color: white;
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: bold;
            cursor: grab;
            transition: all 0.3s ease;
            user-select: none;
        }

        .score-chip:hover {
            transform: scale(1.1);
            box-shadow: 0 4px 12px rgba(79, 70, 229, 0.3);
        }

        .score-chip.dragging {
            opacity: 0.5;
            cursor: grabbing;
        }

        .drop-zone {
            width: 60px;
            height: 60px;
            border: 3px dashed #cbd5e1;
            border-radius: 12px;
            display: flex;
            align-items: center;
            justify-content: center;
            background: #f1f5f9;
            transition: all 0.3s ease;
            position: relative;
        }

        .drop-zone.drag-over {
            border-color: #4f46e5;
            background: #eef2ff;
        }

        .drop-zone.filled {
            border-color: #10b981;
            background: #d1fae5;
        }

        .dropped-score {
            width: 50px;
            height: 50px;
            border-radius: 50%;
            background: #10b981;
            color: white;
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: bold;
            cursor: pointer;
            font-size: 18px;
            line-height: 1;
            text-align: center;
        }

        .scale-labels {
            display: flex;
            justify-content: space-between;
            margin-top: 10px;
            font-size: 12px;
            color: #6b7280;
        }

        .controls {
            display: flex;
            gap: 15px;
            flex-wrap: wrap;
            justify-content: center;
            margin: 30px 0;
        }

        .btn {
            padding: 12px 24px;
            border: none;
            border-radius: 8px;
            font-size: 16px;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
            text-decoration: none;
            display: inline-block;
        }

        .btn-primary {
            background: linear-gradient(135deg, #1e40af, #3b82f6);
            color: white;
        }

        .btn-primary:hover {
            background: linear-gradient(135deg, #1e3a8a, #2563eb);
            transform: translateY(-2px);
        }

        .btn-secondary {
            background: #6b7280;
            color: white;
        }

        .btn-secondary:hover {
            background: #4b5563;
        }

        .btn-danger {
            background: #ef4444;
            color: white;
        }

        .btn-danger:hover {
            background: #dc2626;
        }

        /* Chart Styles */
        .chart-container {
            background: white;
            border-radius: 15px;
            padding: 25px;
            margin: 20px 0;
            box-shadow: 0 8px 25px rgba(0,0,0,0.1);
        }

        .chart-title {
            color: #1e40af;
            font-size: 20px;
            font-weight: bold;
            margin-bottom: 20px;
            text-align: center;
        }

        .radar-chart {
            width: 100%;
            max-width: 400px;
            margin: 0 auto;
        }

        .bar-chart {
            display: flex;
            flex-direction: column;
            gap: 15px;
            margin: 20px 0;
        }

        .bar-item {
            display: flex;
            align-items: center;
            gap: 15px;
        }

        .bar-label {
            min-width: 120px;
            font-size: 14px;
            font-weight: 500;
            color: #374151;
        }

        .bar-container {
            flex: 1;
            height: 30px;
            background: #e5e7eb;
            border-radius: 15px;
            overflow: hidden;
            position: relative;
        }

        .bar-fill {
            height: 100%;
            background: linear-gradient(90deg, #1e40af, #3b82f6);
            border-radius: 15px;
            transition: width 1s ease-out;
            position: relative;
        }

        .bar-fill::after {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: linear-gradient(90deg, transparent, rgba(255,255,255,0.3), transparent);
            animation: shimmer 2s infinite;
        }

        @keyframes shimmer {
            0% { transform: translateX(-100%); }
            100% { transform: translateX(100%); }
        }

        .bar-value {
            min-width: 40px;
            text-align: right;
            font-weight: bold;
            color: #1e40af;
        }

        /* PDF Export Styles */
        .pdf-section {
            background: white;
            border-radius: 15px;
            padding: 25px;
            margin: 20px 0;
            box-shadow: 0 8px 25px rgba(0,0,0,0.1);
            text-align: center;
        }

        .pdf-title {
            color: #1e40af;
            font-size: 20px;
            font-weight: bold;
            margin-bottom: 15px;
        }

        .pdf-btn {
            background: linear-gradient(135deg, #059669, #10b981);
            color: white;
            border: none;
            padding: 15px 30px;
            font-size: 16px;
            font-weight: bold;
            border-radius: 25px;
            cursor: pointer;
            transition: all 0.3s ease;
            box-shadow: 0 8px 20px rgba(5,150,105,0.3);
        }

        .pdf-btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 12px 30px rgba(5,150,105,0.4);
        }

        /* Animation Classes */
        .fade-in {
            animation: fadeIn 0.5s ease-in;
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }

        .slide-in {
            animation: slideIn 0.5s ease-out;
        }

        @keyframes slideIn {
            from { transform: translateX(-100%); opacity: 0; }
            to { transform: translateX(0); opacity: 1; }
        }

        .bounce-in {
            animation: bounceIn 0.6s ease-out;
        }

        @keyframes bounceIn {
            0% { transform: scale(0.3); opacity: 0; }
            50% { transform: scale(1.05); }
            70% { transform: scale(0.9); }
            100% { transform: scale(1); opacity: 1; }
        }

        /* Success Animation */
        .success-animation {
            display: inline-block;
            animation: successPulse 0.6s ease-out;
        }

        @keyframes successPulse {
            0% { transform: scale(1); }
            50% { transform: scale(1.2); }
            100% { transform: scale(1); }
        }

        .results {
            display: none;
        }

        .results.show {
            display: block;
        }

        .result-card {
            background: linear-gradient(135deg, #10b981, #059669);
            color: white;
            border-radius: 15px;
            padding: 25px;
            margin-bottom: 20px;
            text-align: center;
        }

        .result-title {
            font-size: 24px;
            font-weight: bold;
            margin-bottom: 15px;
        }

        .recommended-majors {
            background: white;
            color: #333;
            border-radius: 10px;
            padding: 20px;
            margin: 15px 0;
        }

        .major-list {
            display: flex;
            flex-wrap: wrap;
            gap: 10px;
            justify-content: center;
        }

        .major-tag {
            background: #4f46e5;
            color: white;
            padding: 8px 16px;
            border-radius: 20px;
            font-weight: 500;
        }

        .score-breakdown {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 15px;
            margin: 20px 0;
        }

        .score-item {
            background: white;
            border-radius: 10px;
            padding: 15px;
            text-align: center;
            color: #333;
        }

        .score-value {
            font-size: 24px;
            font-weight: bold;
            color: #4f46e5;
        }

        .score-label {
            font-size: 14px;
            color: #666;
            margin-top: 5px;
        }

        .advice-section {
            background: #fef3c7;
            border: 1px solid #f59e0b;
            border-radius: 10px;
            padding: 20px;
            margin: 20px 0;
        }

        .advice-title {
            color: #92400e;
            font-weight: bold;
            margin-bottom: 10px;
        }

        .advice-text {
            color: #78350f;
            line-height: 1.6;
        }

        .accessibility-controls {
            position: fixed;
            top: 20px;
            right: 20px;
            display: flex;
            gap: 10px;
            z-index: 1000;
        }

        .accessibility-btn {
            width: 40px;
            height: 40px;
            border: none;
            border-radius: 50%;
            background: #4f46e5;
            color: white;
            cursor: pointer;
            font-size: 18px;
            transition: all 0.3s ease;
        }

        .accessibility-btn:hover {
            background: #4338ca;
            transform: scale(1.1);
        }

        /* High Contrast Mode */
        .high-contrast {
            filter: contrast(150%) brightness(1.2);
        }

        .large-text {
            font-size: 120%;
        }

        /* Mobile Responsive */
        @media (max-width: 768px) {
            .container {
                padding: 10px;
            }

            .main-title {
                font-size: 24px;
            }

            .answer-area {
                flex-direction: column;
                align-items: stretch;
            }

            .score-chips {
                justify-content: center;
            }

            .controls {
                flex-direction: column;
            }

            .btn {
                width: 100%;
            }

            .score-breakdown {
                grid-template-columns: 1fr;
            }
        }

        /* Chatbot Modal Styles */
        .chatbot-modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0,0,0,0.5);
            z-index: 10000;
            animation: fadeIn 0.3s ease;
        }

        .chatbot-modal.show {
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .chatbot-container {
            background: white;
            border-radius: 20px;
            width: 90%;
            max-width: 500px;
            height: 80%;
            max-height: 600px;
            display: flex;
            flex-direction: column;
            box-shadow: 0 20px 60px rgba(0,0,0,0.3);
            animation: slideUp 0.3s ease;
        }

        @keyframes slideUp {
            from { transform: translateY(50px); opacity: 0; }
            to { transform: translateY(0); opacity: 1; }
        }

        .chatbot-header {
            background: linear-gradient(135deg, #10b981, #059669);
            color: white;
            padding: 20px;
            border-radius: 20px 20px 0 0;
            display: flex;
            align-items: center;
            justify-content: space-between;
        }

        .chatbot-title {
            font-size: 20px;
            font-weight: bold;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .chatbot-close {
            background: none;
            border: none;
            color: white;
            font-size: 24px;
            cursor: pointer;
            padding: 5px;
            border-radius: 50%;
            transition: background 0.3s ease;
        }

        .chatbot-close:hover {
            background: rgba(255,255,255,0.2);
        }

        .chatbot-messages {
            flex: 1;
            padding: 20px;
            overflow-y: auto;
            display: flex;
            flex-direction: column;
            gap: 15px;
            background: #f8fafc;
        }

        .message {
            max-width: 80%;
            padding: 12px 16px;
            border-radius: 18px;
            font-size: 14px;
            line-height: 1.4;
            animation: messageSlide 0.3s ease;
        }

        @keyframes messageSlide {
            from { transform: translateY(20px); opacity: 0; }
            to { transform: translateY(0); opacity: 1; }
        }

        .message.bot {
            background: white;
            color: #374151;
            align-self: flex-start;
            border: 1px solid #e5e7eb;
            box-shadow: 0 2px 8px rgba(0,0,0,0.1);
        }

        .message.user {
            background: linear-gradient(135deg, #1e40af, #3b82f6);
            color: white;
            align-self: flex-end;
        }

        .message.typing {
            background: white;
            border: 1px solid #e5e7eb;
            align-self: flex-start;
            display: flex;
            align-items: center;
            gap: 8px;
        }

        .typing-dots {
            display: flex;
            gap: 4px;
        }

        .typing-dot {
            width: 8px;
            height: 8px;
            background: #6b7280;
            border-radius: 50%;
            animation: typingBounce 1.4s infinite ease-in-out;
        }

        .typing-dot:nth-child(1) { animation-delay: -0.32s; }
        .typing-dot:nth-child(2) { animation-delay: -0.16s; }

        @keyframes typingBounce {
            0%, 80%, 100% { transform: scale(0); }
            40% { transform: scale(1); }
        }

        .quick-replies {
            display: flex;
            flex-wrap: wrap;
            gap: 8px;
            margin-top: 10px;
        }

        .quick-reply {
            background: #e0f2fe;
            color: #0277bd;
            border: 1px solid #81d4fa;
            padding: 8px 12px;
            border-radius: 15px;
            font-size: 12px;
            cursor: pointer;
            transition: all 0.3s ease;
        }

        .quick-reply:hover {
            background: #b3e5fc;
            transform: scale(1.05);
        }

        .chatbot-input-area {
            padding: 20px;
            border-top: 1px solid #e5e7eb;
            background: white;
            border-radius: 0 0 20px 20px;
        }

        .chatbot-input-container {
            display: flex;
            gap: 10px;
            align-items: flex-end;
        }

        .chatbot-input {
            flex: 1;
            border: 2px solid #e5e7eb;
            border-radius: 20px;
            padding: 12px 16px;
            font-size: 14px;
            resize: none;
            max-height: 100px;
            min-height: 44px;
            transition: border-color 0.3s ease;
        }

        .chatbot-input:focus {
            outline: none;
            border-color: #10b981;
        }

        .chatbot-send {
            background: linear-gradient(135deg, #10b981, #059669);
            color: white;
            border: none;
            width: 44px;
            height: 44px;
            border-radius: 50%;
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 18px;
            transition: all 0.3s ease;
        }

        .chatbot-send:hover {
            transform: scale(1.1);
            box-shadow: 0 4px 12px rgba(16,185,129,0.3);
        }

        .chatbot-send:disabled {
            background: #9ca3af;
            cursor: not-allowed;
            transform: none;
        }

        /* Keyboard Navigation */
        .score-chip:focus,
        .drop-zone:focus,
        .dropped-score:focus {
            outline: 3px solid #fbbf24;
            outline-offset: 2px;
        }

        /* Footer Styles */
        .footer-section {
            background: linear-gradient(135deg, #1e293b, #334155);
            color: white;
            margin-top: 50px;
            padding: 40px 0 0 0;
        }

        .footer-content {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        .footer-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 30px;
            margin-bottom: 30px;
        }

        .footer-column {
            display: flex;
            flex-direction: column;
        }

        .footer-logo {
            text-align: center;
            margin-bottom: 20px;
        }

        .footer-title {
            color: #60a5fa;
            font-size: 18px;
            font-weight: bold;
            margin: 10px 0 5px 0;
        }

        .footer-subtitle {
            color: #94a3b8;
            font-size: 14px;
            margin: 0;
            font-style: italic;
        }

        .footer-heading {
            color: #60a5fa;
            font-size: 16px;
            font-weight: bold;
            margin-bottom: 15px;
            border-bottom: 2px solid #3b82f6;
            padding-bottom: 8px;
        }

        .footer-contact {
            display: flex;
            flex-direction: column;
            gap: 10px;
        }

        .contact-item {
            display: flex;
            align-items: center;
            gap: 10px;
            font-size: 14px;
            line-height: 1.5;
        }

        .contact-icon {
            font-size: 16px;
            width: 20px;
            text-align: center;
        }

        .footer-links {
            display: flex;
            flex-direction: column;
            gap: 8px;
        }

        .footer-link {
            color: #cbd5e1;
            text-decoration: none;
            font-size: 14px;
            padding: 5px 0;
            transition: all 0.3s ease;
            border-left: 3px solid transparent;
            padding-left: 10px;
        }

        .footer-link:hover {
            color: #60a5fa;
            border-left-color: #3b82f6;
            transform: translateX(5px);
        }

        .social-links {
            display: flex;
            flex-direction: column;
            gap: 8px;
        }

        .social-link {
            display: flex;
            align-items: center;
            gap: 10px;
            color: #cbd5e1;
            text-decoration: none;
            font-size: 14px;
            padding: 8px 10px;
            border-radius: 8px;
            transition: all 0.3s ease;
            border: 1px solid transparent;
        }

        .social-link:hover {
            background: rgba(59, 130, 246, 0.1);
            border-color: #3b82f6;
            color: #60a5fa;
            transform: scale(1.02);
        }

        .social-icon {
            font-size: 18px;
            width: 24px;
            text-align: center;
        }

        .footer-bottom {
            margin-top: 30px;
        }

        .footer-divider {
            height: 1px;
            background: linear-gradient(90deg, transparent, #475569, transparent);
            margin-bottom: 20px;
        }

        .footer-bottom-content {
            display: flex;
            justify-content: space-between;
            align-items: center;
            flex-wrap: wrap;
            gap: 20px;
            padding: 20px 0;
            background: rgba(15, 23, 42, 0.5);
            border-radius: 10px 10px 0 0;
        }

        .copyright {
            flex: 1;
            min-width: 250px;
        }

        .copyright p {
            margin: 5px 0;
            font-size: 13px;
            color: #94a3b8;
        }

        .developer-credit {
            font-style: italic;
            color: #60a5fa !important;
        }

        .footer-badges {
            display: flex;
            gap: 15px;
            flex-wrap: wrap;
        }

        .badge {
            display: flex;
            align-items: center;
            gap: 8px;
            background: rgba(59, 130, 246, 0.1);
            border: 1px solid #3b82f6;
            border-radius: 20px;
            padding: 8px 12px;
            font-size: 12px;
            color: #60a5fa;
            transition: all 0.3s ease;
        }

        .badge:hover {
            background: rgba(59, 130, 246, 0.2);
            transform: scale(1.05);
        }

        .badge-icon {
            font-size: 14px;
        }

        .badge-text {
            font-weight: 500;
        }

        /* Mobile Responsive for Footer */
        @media (max-width: 768px) {
            .footer-grid {
                grid-template-columns: 1fr;
                gap: 25px;
            }

            .footer-bottom-content {
                flex-direction: column;
                text-align: center;
                gap: 15px;
            }

            .footer-badges {
                justify-content: center;
            }

            .social-links {
                flex-direction: row;
                flex-wrap: wrap;
                justify-content: center;
            }

            .social-link {
                flex: 1;
                min-width: 120px;
                justify-content: center;
            }
        }
    </style>
</head>
<body>
    <div class="accessibility-controls">
        <button class="accessibility-btn" onclick="toggleContrast()" title="เปลี่ยนคอนทราสต์">🔆</button>
        <button class="accessibility-btn" onclick="toggleTextSize()" title="เปลี่ยนขนาดตัวอักษร">📝</button>
    </div>

    <div class="container">
        <!-- Landing Page -->
        <div class="landing-page" id="landingPage">
            <!-- Hero Section -->
            <div class="hero-section">
                <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTRgc3QNAMHyZ5nIRF2ATn9jOJCFG9vdmpaww&s" alt="โลโก้วิทยาลัยอาชีวศึกษาร้อยเอ็ด" style="width: 120px; height: 120px; border-radius: 50%; margin: 0 auto 20px; display: block; box-shadow: 0 10px 30px rgba(30,64,175,0.3); animation: pulse 2s infinite;" onerror="this.style.display='none'; this.nextElementSibling.style.display='flex';">
                <div class="logo-placeholder" style="display: none;">ROI</div>
                <h1 class="main-title">ระบบแนะแนวและประชาสัมพันธ์อัจฉริยะ<br>วิทยาลัยอาชีวศึกษาร้อยเอ็ด</h1>
                <p class="subtitle">"RVC Smart Career PR System"</p>
                <p class="credit">ผู้จัดทำ: นางสาวสุภาดา คำตา (ครูแผนกเทคโนโลยีสารสนเทศ วิทยาลัยอาชีวศึกษาร้อยเอ็ด)</p>
            </div>

            <!-- Introduction Content -->
            <div class="intro-content">
                <h2 class="intro-title">🎯 ค้นพบความถนัดของคุณ</h2>
                <p class="intro-text">
                    แบบทดสอบนี้จะช่วยประเมินความถนัดด้านอาชีพของคุณ เพื่อแนะนำสาขาวิชาที่เหมาะสมในวิทยาลัยอาชีวศึกษาร้อยเอ็ด 
                    ใช้เวลาเพียง 10-15 นาที คุณจะได้รับคำแนะนำสาขาที่ตรงกับความสนใจและความสามารถของคุณ
                </p>
                <p class="intro-text">
                    <strong>🔒 ความเป็นส่วนตัว:</strong> ข้อมูลของคุณจะถูกเก็บเฉพาะในอุปกรณ์นี้เท่านั้น ไม่มีการส่งข้อมูลออกไปภายนอก
                </p>
            </div>

            <!-- Features Grid -->
            <div class="features-grid">
                <div class="feature-card">
                    <div class="feature-icon">📊</div>
                    <div class="feature-title">วิเคราะห์แม่นยำ</div>
                    <div class="feature-desc">ประเมินความถนัด 7 ด้านหลัก ด้วยคำถาม 40 ข้อที่ออกแบบมาเป็นพิเศษ</div>
                </div>
                <div class="feature-card">
                    <div class="feature-icon">🎓</div>
                    <div class="feature-title">แนะนำสาขาเฉพาะ</div>
                    <div class="feature-desc">ได้รับคำแนะนำสาขาวิชาที่ตรงกับความถนัดในวิทยาลัยอาชีวศึกษาร้อยเอ็ด</div>
                </div>
                <div class="feature-card">
                    <div class="feature-icon">📱</div>
                    <div class="feature-title">ใช้งานง่าย</div>
                    <div class="feature-desc">รองรับทั้งคอมพิวเตอร์และมือถือ ลากวางหรือแตะเลือกคะแนนได้</div>
                </div>
            </div>

            <!-- Aptitude Categories -->
            <div class="aptitude-categories">
                <h2 class="categories-title">🧭 หมวดความถนัดที่ประเมิน</h2>
                <div class="categories-grid">
                    <div class="category-item">
                        <span class="category-icon">🧮</span>
                        <div class="category-name">ตรรกะ–คำนวณ</div>
                        <div class="category-majors">การบัญชี • โลจิสติกส์ • เทคโนโลยีสารสนเทศ</div>
                    </div>
                    <div class="category-item">
                        <span class="category-icon">🎨</span>
                        <div class="category-name">ศิลปะ–ออกแบบ</div>
                        <div class="category-majors">จิตรกรรม • ออกแบบ • คอมพิวเตอร์กราฟิก • แฟชั่น</div>
                    </div>
                    <div class="category-item">
                        <span class="category-icon">💻</span>
                        <div class="category-name">เทคโนโลยี</div>
                        <div class="category-majors">เทคโนโลยีสารสนเทศ • ธุรกิจดิจิทัล • คอมพิวเตอร์ธุรกิจ</div>
                    </div>
                    <div class="category-item">
                        <span class="category-icon">🏨</span>
                        <div class="category-name">การบริการ</div>
                        <div class="category-majors">การโรงแรม • การท่องเที่ยว • อาหารและโภชนาการ</div>
                    </div>
                    <div class="category-item">
                        <span class="category-icon">📢</span>
                        <div class="category-name">การสื่อสาร–การตลาด</div>
                        <div class="category-majors">การตลาด • ประชาสัมพันธ์ • ดิจิทัล</div>
                    </div>
                    <div class="category-item">
                        <span class="category-icon">💼</span>
                        <div class="category-name">ผู้ประกอบการ–ธุรกิจ</div>
                        <div class="category-majors">ธุรกิจค้าปลีก • โลจิสติกส์ • การตลาด</div>
                    </div>
                    <div class="category-item">
                        <span class="category-icon">🏠</span>
                        <div class="category-name">คหกรรม–งานฝีมือ</div>
                        <div class="category-majors">คหกรรมศาสตร์ • อาหารและโภชนาการ • แฟชั่น</div>
                    </div>
                </div>
            </div>

            <!-- Steps Section -->
            <div class="steps-section">
                <h2 class="steps-title">📋 ขั้นตอนการใช้งาน</h2>
                <div class="steps-list">
                    <div class="step-item">
                        <div class="step-number">1</div>
                        <div class="step-content">
                            <div class="step-title">กรอกข้อมูลส่วนตัว</div>
                            <div class="step-desc">ใส่ชื่อ-นามสกุล, ห้อง/ชั้น และข้อมูลเพิ่มเติม</div>
                        </div>
                    </div>
                    <div class="step-item">
                        <div class="step-number">2</div>
                        <div class="step-content">
                            <div class="step-title">ทำแบบทดสอบ 40 ข้อ</div>
                            <div class="step-desc">ลากตัวเลข 1-5 ไปวางในช่องตอบ หรือแตะเลือกบนมือถือ</div>
                        </div>
                    </div>
                    <div class="step-item">
                        <div class="step-number">3</div>
                        <div class="step-content">
                            <div class="step-title">รับผลการวิเคราะห์</div>
                            <div class="step-desc">ดูคะแนนความถนัดและสาขาที่แนะนำพร้อมคำแนะนำ</div>
                        </div>
                    </div>
                    <div class="step-item">
                        <div class="step-number">4</div>
                        <div class="step-content">
                            <div class="step-title">ดาวน์โหลดผลลัพธ์</div>
                            <div class="step-desc">บันทึกหรือพิมพ์ผลการทดสอบเพื่อเก็บไว้อ้างอิง</div>
                        </div>
                    </div>
                </div>
            </div>

            <!-- Call to Action -->
            <div class="cta-section">
                <button class="start-btn" onclick="startTest()">
                    🚀 เริ่มทำแบบทดสอบ
                </button>
                <p style="margin-top: 15px; color: #ffffff; font-size: 18px;">
                    ใช้เวลาประมาณ 10-15 นาที
                </p>
            </div>

            <!-- AI Chat Assistant Section -->
            <div class="ai-chat-section">
                <h2 class="ai-chat-title">🤖 RVC Buddy - ผู้ช่วยดิจิทัล</h2>
                <p class="ai-chat-desc">มีคำถามเกี่ยวกับสาขาวิชาหรือการสมัครเรียน? ถาม RVC Buddy ได้เลย!</p>
                <a href="https://lin.ee/KYO5QCx">
    <button class="ai-chat-btn">
        💬เริ่มแชทกับ RVC Buddy
    </button>
</a>

            </div>
        </div>

        <!-- Test Section -->
        <div class="test-section" id="testSection">
            <!-- Header -->
            <div class="header">
                <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTRgc3QNAMHyZ5nIRF2ATn9jOJCFG9vdmpaww&s" alt="โลโก้วิทยาลัยอาชีวศึกษาร้อยเอ็ด" style="width: 80px; height: 80px; border-radius: 50%; margin: 0 auto; display: block; box-shadow: 0 8px 20px rgba(30,64,175,0.3);" onerror="this.style.display='none'; this.nextElementSibling.style.display='flex';">
                <div class="logo-placeholder" style="width: 80px; height: 80px; font-size: 24px; display: none;">ROI</div>
                <h1 class="main-title" style="font-size: 28px;">ระบบแนะแนวและประชาสัมพันธ์อัจฉริยะ<br>วิทยาลัยอาชีวศึกษาร้อยเอ็ด</h1>
                <p class="subtitle">"RVC Smart Career PR System"</p>
                <p class="credit">ผู้จัดทำ: แผนกเทคโนโลยีสารสนเทศ วิทยาลัยอาชีวศึกษาร้อยเอ็ด</p>
            </div>

            <!-- Privacy Notice -->
            <div class="privacy-notice">
                🔒 ข้อมูลของคุณจะถูกเก็บเฉพาะในอุปกรณ์นี้เท่านั้น ไม่มีการส่งข้อมูลออกไปภายนอก
            </div>

            <!-- Introduction -->
            <div class="section" id="intro-section">
                <div class="section-title">บทนำ</div>
                <p>แบบทดสอบนี้จะช่วยประเมินความถนัดด้านอาชีพของคุณ เพื่อแนะนำสาขาวิชาที่เหมาะสมในวิทยาลัยอาชีวศึกษาร้อยเอ็ด</p>
                <p><strong>วิธีการทำ:</strong> ลากตัวเลข 1-5 ไปวางในช่องตอบของแต่ละข้อคำถาม หรือแตะเพื่อเลือกบนมือถือ</p>
                <div class="scale-labels">
                    <span>1 = ไม่เห็นด้วยเลย</span>
                    <span>5 = เห็นด้วยมาก</span>
                </div>
            </div>

        <!-- Profile Form -->
        <div class="section" id="profile-section">
            <div class="section-title">ข้อมูลผู้ทำแบบทดสอบ</div>
            <div class="form-group">
                <label for="fullName" class="form-label">ชื่อ-นามสกุล <span class="required">*</span></label>
                <input type="text" id="fullName" class="form-input" required>
            </div>
            <div class="form-group">
                <label for="classRoom" class="form-label">สถานศึกษา <span class="required">*</span></label>
                <input type="text" id="classRoom" class="form-input" required>
            </div>
            <div class="form-group">
                <label for="dreamJob" class="form-label">อาชีพในฝัน</label>
                <input type="text" id="dreamJob" class="form-input">
            </div>
            <div class="form-group">
                <label for="email" class="form-label">อีเมล</label>
                <input type="email" id="email" class="form-input">
            </div>
        </div>

        <!-- Progress Bar -->
        <div class="progress-bar">
            <div class="progress-fill" id="progressFill"></div>
        </div>
        <div class="progress-text" id="progressText">ตอบแล้ว 0/40 ข้อ (0%)</div>

        <!-- Questions Section -->
        <div class="section" id="questions-section">
            <div class="section-title">แบบทดสอบความถนัด</div>
            <div id="questionsContainer"></div>
        </div>

        <!-- Controls -->
        <div class="controls">
            <button class="btn btn-secondary" onclick="saveDraft()">💾 บันทึกชั่วคราว</button>
            <button class="btn btn-danger" onclick="clearAnswers()">🗑️ ล้างคำตอบ</button>
            <button class="btn btn-primary" onclick="calculateResults()">📊 คำนวณผล</button>
        </div>

        <!-- Results Section -->
        <div class="section results" id="results-section">
            <div class="result-card">
                <div class="result-title">🎉 ผลการทดสอบความถนัดด้านอาชีพ</div>
                <div class="recommended-majors">
                    <h3>สาขาที่คุณเหมาะสมที่สุด</h3>
                    <div class="major-list" id="recommendedMajors"></div>
                </div>
            </div>

            <!-- Top 3 Rankings -->
            <div class="top-rankings">
                <div class="ranking-title">🏆 อันดับ 3 สาขาที่แนะนำสำหรับคุณ</div>
                <div class="ranking-list" id="topRankings">
                    <!-- Will be populated by JavaScript -->
                </div>
            </div>

            <!-- Chart Dashboard -->
            <div class="chart-container">
                <div class="chart-title">📊 แผนภาพแสดงคะแนนความถนัด</div>
                <div class="radar-chart">
                    <svg id="radarChart" width="400" height="400" viewBox="0 0 400 400"></svg>
                </div>
            </div>

            <div class="chart-container">
                <div class="chart-title">📈 คะแนนรายหมวด</div>
                <div class="bar-chart" id="barChart"></div>
            </div>

            <div class="score-breakdown" id="scoreBreakdown"></div>

            <div class="advice-section">
                <div class="advice-title">💡 คำแนะนำสำหรับคุณ</div>
                <div class="advice-text" id="adviceText"></div>
            </div>

            <!-- PDF Export Section -->
            <div class="pdf-section">
                <div class="pdf-title">📄 ดาวน์โหลดผลการทดสอบ</div>
                <p style="color: #6b7280; margin-bottom: 15px;">
                    บันทึกผลการทดสอบเป็นไฟล์ PDF พร้อมโลโก้วิทยาลัยและข้อมูลครบถ้วน
                </p>
                <button class="pdf-btn" onclick="generatePDF()">
                    📥 ดาวน์โหลด PDF
                </button>
            </div>

            <div class="controls">
                <button class="btn btn-primary" onclick="printResults()">🖨️ พิมพ์ผล</button>
                <button class="btn btn-secondary" onclick="restartTest()">🔄 ทำแบบทดสอบใหม่</button>
                <button class="btn btn-secondary" onclick="backToLanding()">🏠 กลับหน้าแรก</button>
            </div>
        </div>
        </div>

        <!-- Footer -->
        <footer class="footer-section">
            <div class="footer-content">
                <div class="footer-grid">
                    <div class="footer-column">
                        <div class="footer-logo">
                            <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTRgc3QNAMHyZ5nIRF2ATn9jOJCFG9vdmpaww&s" alt="โลโก้วิทยาลัยอาชีวศึกษาร้อยเอ็ด" style="width: 60px; height: 60px; border-radius: 50%; margin-bottom: 15px;" onerror="this.style.display='none'; this.nextElementSibling.style.display='flex';">
                            <div class="footer-logo-placeholder" style="width: 60px; height: 60px; background: linear-gradient(135deg, #1e40af, #3b82f6); border-radius: 50%; margin-bottom: 15px; display: none; align-items: center; justify-content: center; color: white; font-weight: bold; font-size: 18px;">ROI</div>
                            <h3 class="footer-title">วิทยาลัยอาชีวศึกษาร้อยเอ็ด</h3>
                            <p class="footer-subtitle">RVC Smart Career PR System</p>
                        </div>
                    </div>
                    
                    <div class="footer-column">
                        <h4 class="footer-heading">ติดต่อเรา</h4>
                        <div class="footer-contact">
                            <div class="contact-item">
                                <span class="contact-icon">📍</span>
                                <span>123 ถนนร้อยเอ็ด อำเภอเมือง จังหวัดร้อยเอ็ด 45000</span>
                            </div>
                            <div class="contact-item">
                                <span class="contact-icon">☎️</span>
                                <span>043-123-456</span>
                            </div>
                            <div class="contact-item">
                                <span class="contact-icon">📧</span>
                                <span>info@rvc.ac.th</span>
                            </div>
                            <div class="contact-item">
                                <span class="contact-icon">🌐</span>
                                <span>www.rvc.ac.th</span>
                            </div>
                        </div>
                    </div>
                    

                    

                </div>
                
                <div class="footer-bottom">
                    <div class="footer-divider"></div>
                    <div class="footer-bottom-content">
                        <div class="copyright">
                            <p>&copy; 2024 วิทยาลัยอาชีวศึกษาร้อยเอ็ด สงวนลิขสิทธิ์</p>
                            <p class="developer-credit">พัฒนาโดย: แผนกเทคโนโลยีสารสนเทศ</p>
                        </div>
                        <div class="footer-badges">
                            <div class="badge">
                                <span class="badge-icon">🏆</span>
                                <span class="badge-text">คุณภาพการศึกษา</span>
                            </div>
                            <div class="badge">
                                <span class="badge-icon">⭐</span>
                                <span class="badge-text">มาตรฐานสากล</span>
                            </div>
                            <div class="badge">
                                <span class="badge-icon">🔒</span>
                                <span class="badge-text">ปลอดภัย 100%</span>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </footer>
    </div>

    <!-- Chatbot Modal -->
    <div class="chatbot-modal" id="chatbotModal">
        <div class="chatbot-container">
            <div class="chatbot-header">
                <div class="chatbot-title">
                    🤖 RVC Buddy
                    <span style="font-size: 14px; opacity: 0.8;">ผู้ช่วยดิจิทัล</span>
                </div>
                <button class="chatbot-close" onclick="closeChatBot()">×</button>
            </div>
            
            <div class="chatbot-messages" id="chatbotMessages">
                <!-- Messages will be added here -->
            </div>
            
            <div class="chatbot-input-area">
                <div class="chatbot-input-container">
                    <textarea 
                        class="chatbot-input" 
                        id="chatbotInput" 
                        placeholder="พิมพ์คำถามของคุณ..."
                        rows="1"
                        onkeydown="handleChatInputKeydown(event)"
                    ></textarea>
                    <button class="chatbot-send" id="chatbotSend" onclick="sendMessage()">
                        ➤
                    </button>
                </div>
            </div>
        </div>
    </div>
</body>
</html>
<script>
     // ข้อมูลคำถามและการแม็พ
        const QUESTIONS = [
            // ตรรกะ-คำนวณ (5 ข้อ)
            { id: 1, text: "ฉันชอบแก้โจทย์คณิตศาสตร์และปัญหาที่ต้องใช้ตรรกะ", group: "logic" },
            { id: 2, text: "ฉันสนใจการจัดการข้อมูลและการทำบัญชี", group: "logic" },
            { id: 3, text: "ฉันชอบวิเคราะห์ตัวเลขและหาแนวโน้ม", group: "logic" },
            { id: 4, text: "ฉันมีความแม่นยำในการคำนวณและตรวจสอบ", group: "logic" },
            { id: 5, text: "ฉันสนใจระบบการจัดการและโลจิสติกส์", group: "logic" },

            // ศิลปะ-ออกแบบ (5 ข้อ)
            { id: 6, text: "ฉันชอบวาดรูปและสร้างสรรค์งานศิลปะ", group: "art" },
            { id: 7, text: "ฉันสนใจการออกแบบและตกแต่ง", group: "art" },
            { id: 8, text: "ฉันมีความคิดสร้างสรรค์และจินตนาการดี", group: "art" },
            { id: 9, text: "ฉันชอบการออกแบบเสื้อผ้าและแฟชั่น", group: "art" },
            { id: 10, text: "ฉันสนใจคอมพิวเตอร์กราฟิกและการออกแบบดิจิทัล", group: "art" },

            // เทคโนโลยี (5 ข้อ)
            { id: 11, text: "ฉันชอบเล่นและเรียนรู้เทคโนโลยีใหม่ ๆ", group: "tech" },
            { id: 12, text: "ฉันสนใจการเขียนโปรแกรมและพัฒนาแอป", group: "tech" },
            { id: 13, text: "ฉันชอบแก้ไขปัญหาทางเทคนิค", group: "tech" },
            { id: 14, text: "ฉันสนใจธุรกิจออนไลน์และดิจิทัล", group: "tech" },
            { id: 15, text: "ฉันชอบศึกษาระบบคอมพิวเตอร์และเครือข่าย", group: "tech" },

            // การบริการ (5 ข้อ)
            { id: 16, text: "ฉันชอบดูแลและให้บริการผู้อื่น", group: "service" },
            { id: 17, text: "ฉันสนใจงานโรงแรมและการต้อนรับ", group: "service" },
            { id: 18, text: "ฉันชอบการท่องเที่ยวและแนะนำสถานที่", group: "service" },
            { id: 19, text: "ฉันสนใจการทำอาหารและโภชนาการ", group: "service" },
            { id: 20, text: "ฉันมีความอดทนและใจเย็นในการให้บริการ", group: "service" },

            // การสื่อสาร-การตลาด (5 ข้อ)
            { id: 21, text: "ฉันชอบพูดคุยและนำเสนอต่อหน้าคน", group: "marketing" },
            { id: 22, text: "ฉันสนใจการโฆษณาและประชาสัมพันธ์", group: "marketing" },
            { id: 23, text: "ฉันชอบเขียนและสร้างเนื้อหา", group: "marketing" },
            { id: 24, text: "ฉันสนใจการตลาดออนไลน์และโซเชียลมีเดีย", group: "marketing" },
            { id: 25, text: "ฉันมีความสามารถในการโน้มน้าวใจผู้อื่น", group: "marketing" },

            // ผู้ประกอบการ-ธุรกิจ (5 ข้อ)
            { id: 26, text: "ฉันชอบคิดแผนธุรกิจและหาโอกาสใหม่", group: "business" },
            { id: 27, text: "ฉันสนใจการขายและการค้า", group: "business" },
            { id: 28, text: "ฉันมีความกล้าเสี่ยงและตัดสินใจเร็ว", group: "business" },
            { id: 29, text: "ฉันชอบการจัดการทีมและเป็นผู้นำ", group: "business" },
            { id: 30, text: "ฉันสนใจการลงทุนและการเงิน", group: "business" },

            // คหกรรม-งานฝีมือ (5 ข้อ)
            { id: 31, text: "ฉันชอบทำงานฝีมือและสิ่งของใช้ในบ้าน", group: "homecraft" },
            { id: 32, text: "ฉันสนใจการจัดการบ้านและครอบครัว", group: "homecraft" },
            { id: 33, text: "ฉันชอบเย็บปักถักร้อยและงานประดิษฐ์", group: "homecraft" },
            { id: 34, text: "ฉันสนใจการทำอาหารและขนมไทย", group: "homecraft" },
            { id: 35, text: "ฉันชอบการดูแลสุขภาพและโภชนาการ", group: "homecraft" },

            // บุคลิกภาพ-เจตคติ (5 ข้อ - ไม่นับคะแนนหลัก)
            { id: 36, text: "ฉันเป็นคนมีระเบียบและชอบความเป็นระบบ", group: "personality" },
            { id: 37, text: "ฉันชอบทำงานเป็นทีมมากกว่าทำงานคนเดียว", group: "personality" },
            { id: 38, text: "ฉันมีความอดทนและไม่ย่อท้อต่ออุปสรรค", group: "personality" },
            { id: 39, text: "ฉันชอบเรียนรู้สิ่งใหม่ ๆ อยู่เสมอ", group: "personality" },
            { id: 40, text: "ฉันมีความรับผิดชอบและทำงานตรงเวลา", group: "personality" }
        ];

        // การแม็พกลุ่มคำถาม
        const GROUP_MAP = {
            logic: [1, 2, 3, 4, 5],
            art: [6, 7, 8, 9, 10],
            tech: [11, 12, 13, 14, 15],
            service: [16, 17, 18, 19, 20],
            marketing: [21, 22, 23, 24, 25],
            business: [26, 27, 28, 29, 30],
            homecraft: [31, 32, 33, 34, 35],
            personality: [36, 37, 38, 39, 40]
        };

        // การแนะนำสาขา
        const RECOMMEND = {
            "ตรรกะ–คำนวณ": ["การบัญชี", "การจัดการโลจิสติกส์", "เทคโนโลยีสารสนเทศ"],
            "ศิลปะ–ออกแบบ": ["จิตรกรรม", "ออกแบบ", "คอมพิวเตอร์กราฟิก", "แฟชั่นและสิ่งทอ"],
            "เทคโนโลยี": ["เทคโนโลยีสารสนเทศ", "เทคโนโลยีธุรกิจดิจิทัล", "คอมพิวเตอร์ธุรกิจ"],
            "การบริการ": ["การโรงแรม", "การท่องเที่ยว", "อาหารและโภชนาการ"],
            "การสื่อสาร–การตลาด": ["การตลาด", "ประชาสัมพันธ์/ดิจิทัล"],
            "ผู้ประกอบการ–ธุรกิจ": ["ธุรกิจค้าปลีก", "การจัดการโลจิสติกส์", "การตลาด"],
            "คหกรรม–งานฝีมือ": ["คหกรรมศาสตร์", "อาหารและโภชนาการ", "แฟชั่นและสิ่งทอ"]
        };

        // ชื่อกลุ่มภาษาไทย
        const GROUP_NAMES = {
            logic: "ตรรกะ–คำนวณ",
            art: "ศิลปะ–ออกแบบ",
            tech: "เทคโนโลยี",
            service: "การบริการ",
            marketing: "การสื่อสาร–การตลาด",
            business: "ผู้ประกอบการ–ธุรกิจ",
            homecraft: "คหกรรม–งานฝีมือ",
            personality: "บุคลิกภาพ–เจตคติ"
        };

        // ตัวแปรสำหรับเก็บข้อมูล
        let answers = {};
        let profile = {};

        // โหลดข้อมูลจาก localStorage เมื่อเริ่มต้น
        function loadData() {
            const savedProfile = localStorage.getItem('apt_v1_profile');
            const savedAnswers = localStorage.getItem('apt_v1_answers');
            
            if (savedProfile) {
                profile = JSON.parse(savedProfile);
                document.getElementById('fullName').value = profile.fullName || '';
                document.getElementById('classRoom').value = profile.classRoom || '';
                document.getElementById('dreamJob').value = profile.dreamJob || '';
                document.getElementById('email').value = profile.email || '';
            }
            
            if (savedAnswers) {
                answers = JSON.parse(savedAnswers);
            }
        }

        // สร้างคำถาม
        function renderQuestions() {
            const container = document.getElementById('questionsContainer');
            const groups = {};
            
            // จัดกลุ่มคำถาม
            QUESTIONS.forEach(q => {
                if (!groups[q.group]) groups[q.group] = [];
                groups[q.group].push(q);
            });

            let html = '';
            Object.keys(groups).forEach(groupKey => {
                const groupName = GROUP_NAMES[groupKey];
                html += `<div class="question-group">
                    <div class="group-header">${groupName}</div>`;
                
                groups[groupKey].forEach(question => {
                    html += `<div class="question-item">
                        <div class="question-text">${question.id}. ${question.text}</div>
                        <div class="answer-area">
                            <div class="score-chips">
                                ${[1,2,3,4,5].map(score => 
                                    `<div class="score-chip" draggable="true" 
                                          data-score="${score}" 
                                          onclick="selectScore(${question.id}, ${score})"
                                          onkeydown="handleChipKeydown(event, ${question.id}, ${score})"
                                          tabindex="0">${score}</div>`
                                ).join('')}
                            </div>
                            <div class="drop-zone" 
                                 data-question="${question.id}"
                                 onclick="clearAnswer(${question.id})"
                                 onkeydown="handleDropKeydown(event, ${question.id})"
                                 tabindex="0"
                                 role="button"
                                 aria-label="ช่องตอบสำหรับข้อ ${question.id}">
                                ${answers[question.id] ? 
                                    `<div class="dropped-score">${answers[question.id]}</div>` : 
                                    '?'
                                }
                            </div>
                        </div>
                        <div class="scale-labels">
                            <span>ไม่เห็นด้วยเลย</span>
                            <span>เห็นด้วยมาก</span>
                        </div>
                    </div>`;
                });
                html += '</div>';
            });
            
            container.innerHTML = html;
            setupDragAndDrop();
            updateProgress();
        }

        // ตั้งค่า Drag and Drop
        function setupDragAndDrop() {
            const chips = document.querySelectorAll('.score-chip');
            const dropZones = document.querySelectorAll('.drop-zone');

            chips.forEach(chip => {
                chip.addEventListener('dragstart', handleDragStart);
                chip.addEventListener('dragend', handleDragEnd);
            });

            dropZones.forEach(zone => {
                zone.addEventListener('dragover', handleDragOver);
                zone.addEventListener('drop', handleDrop);
                zone.addEventListener('dragleave', handleDragLeave);
            });
        }

        // จัดการ Drag Start
        function handleDragStart(e) {
            e.dataTransfer.setData('text/plain', e.target.dataset.score);
            e.target.classList.add('dragging');
        }

        // จัดการ Drag End
        function handleDragEnd(e) {
            e.target.classList.remove('dragging');
        }

        // จัดการ Drag Over
        function handleDragOver(e) {
            e.preventDefault();
            e.target.classList.add('drag-over');
        }

        // จัดการ Drag Leave
        function handleDragLeave(e) {
            e.target.classList.remove('drag-over');
        }

        // จัดการ Drop
        function handleDrop(e) {
            e.preventDefault();
            e.target.classList.remove('drag-over');
            
            const score = parseInt(e.dataTransfer.getData('text/plain'));
            const questionId = parseInt(e.target.dataset.question);
            
            setAnswer(questionId, score);
        }

        // เลือกคะแนนด้วยการแตะ (สำหรับมือถือ)
        function selectScore(questionId, score) {
            setAnswer(questionId, score);
        }

        // ตั้งค่าคำตอบ
        function setAnswer(questionId, score) {
            answers[questionId] = score;
            
            const dropZone = document.querySelector(`[data-question="${questionId}"]`);
            dropZone.innerHTML = `<div class="dropped-score success-animation">${score}</div>`;
            dropZone.classList.add('filled');
            
            // เล่นเสียงตอบ
            playSound('answer');
            
            updateProgress();
            saveToLocalStorage();
        }

        // ล้างคำตอบ
        function clearAnswer(questionId) {
            delete answers[questionId];
            
            const dropZone = document.querySelector(`[data-question="${questionId}"]`);
            dropZone.innerHTML = '?';
            dropZone.classList.remove('filled');
            
            updateProgress();
            saveToLocalStorage();
        }

        // อัพเดทความคืบหน้า
        function updateProgress() {
            const totalQuestions = QUESTIONS.length;
            const answeredQuestions = Object.keys(answers).length;
            const percentage = Math.round((answeredQuestions / totalQuestions) * 100);
            
            document.getElementById('progressFill').style.width = percentage + '%';
            document.getElementById('progressText').textContent = 
                `ตอบแล้ว ${answeredQuestions}/${totalQuestions} ข้อ (${percentage}%)`;
        }

        // บันทึกข้อมูลลง localStorage
        function saveToLocalStorage() {
            localStorage.setItem('apt_v1_answers', JSON.stringify(answers));
        }

        // บันทึกชั่วคราว
        function saveDraft() {
            saveProfile();
            saveToLocalStorage();
            alert('บันทึกข้อมูลเรียบร้อยแล้ว');
        }

        // บันทึกข้อมูลส่วนตัว
        function saveProfile() {
            profile = {
                fullName: document.getElementById('fullName').value,
                classRoom: document.getElementById('classRoom').value,
                dreamJob: document.getElementById('dreamJob').value,
                email: document.getElementById('email').value
            };
            localStorage.setItem('apt_v1_profile', JSON.stringify(profile));
        }

        // ล้างคำตอบทั้งหมด
        function clearAnswers() {
            if (confirm('คุณต้องการล้างคำตอบทั้งหมดใช่หรือไม่?')) {
                answers = {};
                localStorage.removeItem('apt_v1_answers');
                renderQuestions();
            }
        }

        // คำนวณผลลัพธ์
        function calculateResults() {
            // ตรวจสอบข้อมูลส่วนตัว
            const fullName = document.getElementById('fullName').value.trim();
            const classRoom = document.getElementById('classRoom').value.trim();
            
            if (!fullName || !classRoom) {
                alert('กรุณากรอกชื่อ-นามสกุล และ สถานศึกษา');
                return;
            }

            // ตรวจสอบคำตอบ
            const totalQuestions = QUESTIONS.length;
            const answeredQuestions = Object.keys(answers).length;
            
            if (answeredQuestions < totalQuestions) {
                alert(`กรุณาตอบคำถามให้ครบทั้ง ${totalQuestions} ข้อ (ตอบแล้ว ${answeredQuestions} ข้อ)`);
                return;
            }

            saveProfile();
            
            // คำนวณคะแนนรายกลุ่ม
            const scores = {};
            Object.keys(GROUP_MAP).forEach(group => {
                if (group === 'personality') return; // ไม่นับคะแนนบุคลิกภาพ
                
                scores[group] = 0;
                GROUP_MAP[group].forEach(questionId => {
                    scores[group] += answers[questionId] || 0;
                });
            });

            // หากลุ่มที่มีคะแนนสูงสุด
            const maxScore = Math.max(...Object.values(scores));
            const topGroups = Object.keys(scores).filter(group => scores[group] === maxScore);

            // รวมสาขาที่แนะนำ
            const recommendedMajors = new Set();
            topGroups.forEach(group => {
                const groupName = GROUP_NAMES[group];
                if (RECOMMEND[groupName]) {
                    RECOMMEND[groupName].forEach(major => recommendedMajors.add(major));
                }
            });

            // แสดงผลลัพธ์
            displayResults(scores, Array.from(recommendedMajors), topGroups);
            
            // บันทึกผลลัพธ์
            const result = {
                profile,
                scores,
                recommendedMajors: Array.from(recommendedMajors),
                topGroups,
                timestamp: new Date().toISOString()
            };
            localStorage.setItem('apt_v1_result', JSON.stringify(result));
        }

        // แสดงผลลัพธ์
        function displayResults(scores, recommendedMajors, topGroups) {
            // แสดงสาขาที่แนะนำ
            const majorsContainer = document.getElementById('recommendedMajors');
            majorsContainer.innerHTML = recommendedMajors.map(major => 
                `<span class="major-tag bounce-in">${major}</span>`
            ).join('');

            // สร้างกราฟ
            createRadarChart(scores);
            createBarChart(scores);

            // แสดงคะแนนรายกลุ่ม
            const scoreContainer = document.getElementById('scoreBreakdown');
            let scoreHtml = '';
            Object.keys(scores).forEach(group => {
                const score = scores[group];
                const level = getScoreLevel(score);
                scoreHtml += `
                    <div class="score-item fade-in">
                        <div class="score-value">${score}/25</div>
                        <div class="score-label">${GROUP_NAMES[group]}</div>
                        <div style="color: #666; font-size: 12px;">${level}</div>
                    </div>
                `;
            });
            scoreContainer.innerHTML = scoreHtml;

            // สร้างอันดับ Top 3
            renderTopRankings(scores, topGroups);

            // แสดงคำแนะนำ
            const adviceContainer = document.getElementById('adviceText');
            const topGroupNames = topGroups.map(group => GROUP_NAMES[group]);
            adviceContainer.innerHTML = generateAdvice(topGroupNames);

            // อัพเดทสถิติ Dashboard
            updateDashboardStats();

            // เล่นเสียงเสร็จสิ้น
            playSound('complete');

            // แสดงส่วนผลลัพธ์
            document.getElementById('results-section').classList.add('show');
            document.getElementById('results-section').scrollIntoView({ behavior: 'smooth' });
        }

        // ประเมินระดับคะแนน
        function getScoreLevel(score) {
            if (score >= 21) return 'ถนัดมาก';
            if (score >= 16) return 'ถนัด';
            if (score >= 11) return 'ปานกลาง';
            if (score >= 6) return 'ต่ำ';
            return 'ต่ำมาก';
        }

        // สร้างคำแนะนำ
        function generateAdvice(topGroups) {
            const adviceMap = {
                "ตรรกะ–คำนวณ": "คุณมีความสามารถด้านการคิดเชิงตรรกะและการคำนวณ แนะนำให้พัฒนาทักษะด้านการวิเคราะห์ข้อมูลและการใช้โปรแกรมคอมพิวเตอร์",
                "ศิลปะ–ออกแบบ": "คุณมีความคิดสร้างสรรค์และความสามารถด้านศิลปะ แนะนำให้ฝึกฝนทักษะการออกแบบและศึกษาเทรนด์ใหม่ ๆ",
                "เทคโนโลยี": "คุณมีความสนใจด้านเทคโนโลจี แนะนำให้เรียนรู้การเขียนโปรแกรมและติดตามเทคโนโลยีใหม่",
                "การบริการ": "คุณมีจิตใจในการให้บริการ แนะนำให้พัฒนาทักษะการสื่อสารและการดูแลลูกค้า",
                "การสื่อสาร–การตลาด": "คุณมีความสามารถด้านการสื่อสารและการตลาด แนะนำให้พัฒนาทักษะการนำเสนอและการใช้สื่อดิจิทัล",
                "ผู้ประกอบการ–ธุรกิจ": "คุณมีจิตวิญญาณของผู้ประกอบการ แนะนำให้ศึกษาการบริหารธุรกิจและการลงทุน",
                "คหกรรม–งานฝีมือ": "คุณมีความสามารถด้านงานฝีมือ แนะนำให้พัฒนาทักษะการทำงานด้วยมือและการจัดการบ้าน"
            };

            if (topGroups.length === 1) {
                return adviceMap[topGroups[0]] || "แนะนำให้พัฒนาตนเองในด้านที่สนใจ";
            } else {
                return `คุณมีความถนัดหลากหลายใน ${topGroups.join(', ')} แนะนำให้เลือกสาขาที่รวมความสามารถหลายด้านเข้าด้วยกัน`;
            }
        }

        // พิมพ์ผลลัพธ์
        function printResults() {
            // ตรวจสอบว่ามีผลลัพธ์หรือไม่
            const savedResult = localStorage.getItem('apt_v1_result');
            if (!savedResult) {
                alert('ไม่พบผลการทดสอบ กรุณาทำแบบทดสอบให้เสร็จสิ้นก่อน');
                return;
            }

            // เรียกใช้ฟังก์ชัน generatePDF เพื่อแสดงหน้าพิมพ์
            generatePDF();
        }

        // เริ่มทำแบบทดสอบใหม่
        function restartTest() {
            if (confirm('คุณต้องการเริ่มทำแบบทดสอบใหม่ใช่หรือไม่?')) {
                answers = {};
                localStorage.removeItem('apt_v1_answers');
                localStorage.removeItem('apt_v1_result');
                document.getElementById('results-section').classList.remove('show');
                renderQuestions();
                document.getElementById('intro-section').scrollIntoView({ behavior: 'smooth' });
            }
        }

        // จัดการคีย์บอร์ดสำหรับชิปคะแนน
        function handleChipKeydown(event, questionId, score) {
            if (event.key === 'Enter' || event.key === ' ') {
                event.preventDefault();
                selectScore(questionId, score);
            }
        }

        // จัดการคีย์บอร์ดสำหรับ drop zone
        function handleDropKeydown(event, questionId) {
            if (event.key === 'Enter' || event.key === ' ') {
                event.preventDefault();
                clearAnswer(questionId);
            }
        }

        // เปลี่ยนคอนทราสต์
        function toggleContrast() {
            document.body.classList.toggle('high-contrast');
        }

        // เปลี่ยนขนาดตัวอักษร
        function toggleTextSize() {
            document.body.classList.toggle('large-text');
        }

        // เริ่มแบบทดสอบ
        function startTest() {
            document.getElementById('landingPage').classList.add('hidden');
            document.getElementById('testSection').classList.add('show');
            document.getElementById('testSection').scrollIntoView({ behavior: 'smooth' });
            
            // เล่นเสียงเริ่มต้น
            playSound('start');
        }

        // กลับหน้าแรก
        function backToLanding() {
            document.getElementById('testSection').classList.remove('show');
            document.getElementById('landingPage').classList.remove('hidden');
            document.getElementById('landingPage').scrollIntoView({ behavior: 'smooth' });
        }

        // เล่นเสียง (จำลอง)
        function playSound(type) {
            // สร้างเสียงด้วย Web Audio API
            const audioContext = new (window.AudioContext || window.webkitAudioContext)();
            const oscillator = audioContext.createOscillator();
            const gainNode = audioContext.createGain();
            
            oscillator.connect(gainNode);
            gainNode.connect(audioContext.destination);
            
            switch(type) {
                case 'start':
                    oscillator.frequency.setValueAtTime(523.25, audioContext.currentTime); // C5
                    oscillator.frequency.setValueAtTime(659.25, audioContext.currentTime + 0.1); // E5
                    break;
                case 'answer':
                    oscillator.frequency.setValueAtTime(440, audioContext.currentTime); // A4
                    break;
                case 'complete':
                    oscillator.frequency.setValueAtTime(523.25, audioContext.currentTime); // C5
                    oscillator.frequency.setValueAtTime(659.25, audioContext.currentTime + 0.1); // E5
                    oscillator.frequency.setValueAtTime(783.99, audioContext.currentTime + 0.2); // G5
                    break;
            }
            
            gainNode.gain.setValueAtTime(0.1, audioContext.currentTime);
            gainNode.gain.exponentialRampToValueAtTime(0.01, audioContext.currentTime + 0.3);
            
            oscillator.start(audioContext.currentTime);
            oscillator.stop(audioContext.currentTime + 0.3);
        }

        // สร้างกราฟเรดาร์
        function createRadarChart(scores) {
            const svg = document.getElementById('radarChart');
            svg.innerHTML = '';
            
            const centerX = 200;
            const centerY = 200;
            const maxRadius = 150;
            const categories = Object.keys(scores);
            const maxScore = 25;
            
            // สร้างเส้นกริด
            for (let i = 1; i <= 5; i++) {
                const radius = (maxRadius / 5) * i;
                const circle = document.createElementNS('http://www.w3.org/2000/svg', 'circle');
                circle.setAttribute('cx', centerX);
                circle.setAttribute('cy', centerY);
                circle.setAttribute('r', radius);
                circle.setAttribute('fill', 'none');
                circle.setAttribute('stroke', '#e5e7eb');
                circle.setAttribute('stroke-width', '1');
                svg.appendChild(circle);
            }
            
            // สร้างเส้นแกน
            categories.forEach((category, index) => {
                const angle = (index * 2 * Math.PI) / categories.length - Math.PI / 2;
                const x = centerX + maxRadius * Math.cos(angle);
                const y = centerY + maxRadius * Math.sin(angle);
                
                const line = document.createElementNS('http://www.w3.org/2000/svg', 'line');
                line.setAttribute('x1', centerX);
                line.setAttribute('y1', centerY);
                line.setAttribute('x2', x);
                line.setAttribute('y2', y);
                line.setAttribute('stroke', '#e5e7eb');
                line.setAttribute('stroke-width', '1');
                svg.appendChild(line);
                
                // ป้ายชื่อ
                const text = document.createElementNS('http://www.w3.org/2000/svg', 'text');
                const labelX = centerX + (maxRadius + 20) * Math.cos(angle);
                const labelY = centerY + (maxRadius + 20) * Math.sin(angle);
                text.setAttribute('x', labelX);
                text.setAttribute('y', labelY);
                text.setAttribute('text-anchor', 'middle');
                text.setAttribute('dominant-baseline', 'middle');
                text.setAttribute('font-size', '12');
                text.setAttribute('fill', '#374151');
                text.textContent = GROUP_NAMES[category];
                svg.appendChild(text);
            });
            
            // สร้างพื้นที่ข้อมูล
            let pathData = '';
            categories.forEach((category, index) => {
                const angle = (index * 2 * Math.PI) / categories.length - Math.PI / 2;
                const score = scores[category] || 0;
                const radius = (score / maxScore) * maxRadius;
                const x = centerX + radius * Math.cos(angle);
                const y = centerY + radius * Math.sin(angle);
                
                if (index === 0) {
                    pathData += `M ${x} ${y}`;
                } else {
                    pathData += ` L ${x} ${y}`;
                }
                
                // จุดข้อมูล
                const circle = document.createElementNS('http://www.w3.org/2000/svg', 'circle');
                circle.setAttribute('cx', x);
                circle.setAttribute('cy', y);
                circle.setAttribute('r', '4');
                circle.setAttribute('fill', '#1e40af');
                svg.appendChild(circle);
            });
            pathData += ' Z';
            
            const path = document.createElementNS('http://www.w3.org/2000/svg', 'path');
            path.setAttribute('d', pathData);
            path.setAttribute('fill', 'rgba(30, 64, 175, 0.2)');
            path.setAttribute('stroke', '#1e40af');
            path.setAttribute('stroke-width', '2');
            svg.appendChild(path);
        }

        // สร้างกราฟแท่ง
        function createBarChart(scores) {
            const container = document.getElementById('barChart');
            container.innerHTML = '';
            
            Object.keys(scores).forEach(group => {
                const score = scores[group];
                const percentage = (score / 25) * 100;
                
                const barItem = document.createElement('div');
                barItem.className = 'bar-item';
                
                barItem.innerHTML = `
                    <div class="bar-label">${GROUP_NAMES[group]}</div>
                    <div class="bar-container">
                        <div class="bar-fill" style="width: 0%"></div>
                    </div>
                    <div class="bar-value">${score}/25</div>
                `;
                
                container.appendChild(barItem);
                
                // แอนิเมชันแท่ง
                setTimeout(() => {
                    const barFill = barItem.querySelector('.bar-fill');
                    barFill.style.width = percentage + '%';
                }, 100);
            });
        }

        // สร้าง PDF
        function generatePDF() {
            // ตรวจสอบว่ามีผลลัพธ์หรือไม่
            const savedResult = localStorage.getItem('apt_v1_result');
            if (!savedResult) {
                alert('ไม่พบผลการทดสอบ กรุณาทำแบบทดสอบให้เสร็จสิ้นก่อน');
                return;
            }

            const result = JSON.parse(savedResult);
            const { scores, recommendedMajors, topGroups } = result;

            // สร้างรายการสาขาที่แนะนำ
            const majorsHtml = recommendedMajors.map(major => 
                `<span style="display: inline-block; background: #1e40af; color: white; padding: 8px 16px; border-radius: 20px; margin: 5px; font-weight: 500;">${major}</span>`
            ).join('');

            // สร้างตารางคะแนน
            const scoresHtml = Object.keys(scores).map(group => {
                const score = scores[group];
                const level = getScoreLevel(score);
                return `
                    <div style="display: flex; justify-content: space-between; align-items: center; padding: 10px; border-bottom: 1px solid #e5e7eb;">
                        <div style="font-weight: 500;">${GROUP_NAMES[group]}</div>
                        <div style="text-align: right;">
                            <div style="font-size: 18px; font-weight: bold; color: #1e40af;">${score}/25</div>
                            <div style="font-size: 12px; color: #6b7280;">${level}</div>
                        </div>
                    </div>
                `;
            }).join('');

            // สร้างอันดับ Top 3
            const rankings = [];
            Object.keys(scores).forEach(group => {
                const score = scores[group];
                const groupName = GROUP_NAMES[group];
                const majors = RECOMMEND[groupName] || [];
                
                if (majors.length > 0) {
                    rankings.push({
                        group,
                        groupName,
                        score,
                        percentage: Math.round((score / 25) * 100),
                        majors: majors.slice(0, 2),
                        description: getAptitudeDescription(group, score)
                    });
                }
            });

            rankings.sort((a, b) => b.score - a.score);

            const rankingsHtml = rankings.slice(0, 3).map((rank, index) => {
                const medals = ['🥇', '🥈', '🥉'];
                return `
                    <div style="display: flex; align-items: center; padding: 15px; margin-bottom: 10px; border: 2px solid #e5e7eb; border-radius: 10px;">
                        <div style="font-size: 24px; margin-right: 15px;">${medals[index]}</div>
                        <div style="flex: 1;">
                            <div style="font-weight: bold; color: #1e40af; margin-bottom: 5px;">${rank.majors.join(' • ')}</div>
                            <div style="color: #6b7280; font-size: 14px;">${rank.description}</div>
                        </div>
                        <div style="text-align: right; color: #059669; font-weight: bold;">
                            <div style="font-size: 20px;">${rank.percentage}%</div>
                            <div style="font-size: 12px;">ความเหมาะสม</div>
                        </div>
                    </div>
                `;
            }).join('');

            // สร้างคำแนะนำ
            const topGroupNames = topGroups.map(group => GROUP_NAMES[group]);
            const advice = generateAdvice(topGroupNames);

            // สร้างเนื้อหา PDF ในรูปแบบ HTML
            const pdfContent = `
                <div style="font-family: Arial, sans-serif; padding: 20px; max-width: 800px; margin: 0 auto;">
                    <div style="text-align: center; margin-bottom: 30px; border-bottom: 2px solid #1e40af; padding-bottom: 20px;">
                        <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTRgc3QNAMHyZ5nIRF2ATn9jOJCFG9vdmpaww&s" alt="โลโก้วิทยาลัยอาชีวศึกษาร้อยเอ็ด" style="width: 80px; height: 80px; border-radius: 50%; margin: 0 auto 15px; display: block; box-shadow: 0 8px 20px rgba(30,64,175,0.3);" onerror="this.style.display='none'; this.nextElementSibling.style.display='flex';">
                        <div style="width: 80px; height: 80px; background: linear-gradient(135deg, #1e40af, #3b82f6); border-radius: 50%; margin: 0 auto 15px; display: none; align-items: center; justify-content: center; color: white; font-weight: bold; font-size: 24px;">ROI</div>
                        <h1 style="color: #1e40af; margin: 10px 0;">ผลการทดสอบความถนัดด้านอาชีพ</h1>
                        <h2 style="color: #374151; margin: 5px 0;">วิทยาลัยอาชีวศึกษาร้อยเอ็ด</h2>
                        <h3 style="color: #6b7280; margin: 5px 0;">"RVC Smart Career PR System"</h3>
                        <p style="color: #6b7280; font-style: italic;">ผู้จัดทำ: นางสาวสุภาดา คำตา (ครูแผนกเทคโนโลยีสารสนเทศ วิทยาลัยอาชีวศึกษาร้อยเอ็ด)</p>
                    </div>
                    
                    <div style="margin-bottom: 25px;">
                        <h3 style="color: #1e40af; border-bottom: 1px solid #e5e7eb; padding-bottom: 5px;">ข้อมูลผู้ทำแบบทดสอบ</h3>
                        <p><strong>ชื่อ-นามสกุล:</strong> ${result.profile.fullName || 'ไม่ระบุ'}</p>
                        <p><strong>สถานศึกษา:</strong> ${result.profile.classRoom || 'ไม่ระบุ'}</p>
                        <p><strong>อาชีพในฝัน:</strong> ${result.profile.dreamJob || 'ไม่ระบุ'}</p>
                        <p><strong>วันที่ทำแบบทดสอบ:</strong> ${new Date(result.timestamp).toLocaleDateString('th-TH')}</p>
                    </div>
                    
                    <div style="margin-bottom: 25px;">
                        <h3 style="color: #1e40af; border-bottom: 1px solid #e5e7eb; padding-bottom: 5px;">🏆 อันดับ 3 สาขาที่แนะนำสำหรับคุณ</h3>
                        ${rankingsHtml}
                    </div>
                    
                    <div style="margin-bottom: 25px;">
                        <h3 style="color: #1e40af; border-bottom: 1px solid #e5e7eb; padding-bottom: 5px;">📚 สาขาวิชาที่เหมาะสม</h3>
                        <div style="text-align: center; padding: 15px;">
                            ${majorsHtml}
                        </div>
                    </div>
                    
                    <div style="margin-bottom: 25px;">
                        <h3 style="color: #1e40af; border-bottom: 1px solid #e5e7eb; padding-bottom: 5px;">📊 คะแนนความถนัดรายหมวด</h3>
                        <div style="border: 1px solid #e5e7eb; border-radius: 8px; overflow: hidden;">
                            ${scoresHtml}
                        </div>
                    </div>
                    
                    <div style="margin-bottom: 25px;">
                        <h3 style="color: #1e40af; border-bottom: 1px solid #e5e7eb; padding-bottom: 5px;">💡 คำแนะนำสำหรับคุณ</h3>
                        <div style="background: #fef3c7; border: 1px solid #f59e0b; border-radius: 8px; padding: 15px; color: #78350f; line-height: 1.6;">
                            ${advice}
                        </div>
                    </div>
                    
                    <div style="text-align: center; margin-top: 30px; padding-top: 20px; border-top: 1px solid #e5e7eb; color: #6b7280; font-size: 12px;">
                        <p>วิทยาลัยอาชีวศึกษาร้อยเอ็ด | ระบบแนะแนวและประชาสัมพันธ์อัจฉริยะ "RVC Smart Career PR System"</p>
                        <p>สร้างเมื่อ: ${new Date().toLocaleString('th-TH')}</p>
                    </div>
                </div>
            `; }
</script>
