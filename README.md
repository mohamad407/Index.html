<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Mohamad Asihf | Portfolio</title>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@300;400;500;600;700&family=Inter:wght@300;400;500;600&display=swap" rel="stylesheet">
    <style>
        :root {
            --bg-primary: #080810;
            --bg-secondary: #0e0e18;
            --bg-tertiary: #141420;
            --bg-elevated: #1a1a28;
            --fg-primary: #f0f0f5;
            --fg-secondary: #a8a8b8;
            --fg-muted: #606070;
            --accent: #00aaff;
            --accent-bright: #33bbff;
            --accent-dim: #0077cc;
            --accent-glow: rgba(0, 170, 255, 0.25);
            --accent-subtle: rgba(0, 170, 255, 0.08);
            --card-bg: rgba(20, 20, 32, 0.6);
            --card-border: rgba(255, 255, 255, 0.06);
            --glass-bg: rgba(255, 255, 255, 0.02);
            --danger: #ff4466;
            --danger-dim: rgba(255, 68, 102, 0.15);
            --success: #00dd88;
            --warning: #ffaa00;
            --radius-sm: 8px;
            --radius-md: 14px;
            --radius-lg: 24px;
            --radius-xl: 32px;
            --shadow-sm: 0 2px 8px rgba(0, 0, 0, 0.3);
            --shadow-md: 0 8px 32px rgba(0, 0, 0, 0.4);
            --shadow-lg: 0 16px 64px rgba(0, 0, 0, 0.5);
            --transition-fast: 0.15s ease;
            --transition-med: 0.3s cubic-bezier(0.4, 0, 0.2, 1);
            --transition-slow: 0.5s cubic-bezier(0.4, 0, 0.2, 1);
        }

        * { margin: 0; padding: 0; box-sizing: border-box; }
        html { scroll-behavior: smooth; }
        body {
            font-family: 'Inter', sans-serif;
            background: var(--bg-primary);
            color: var(--fg-primary);
            line-height: 1.7;
            overflow-x: hidden;
            min-height: 100vh;
        }

        /* Background Effects */
        .bg-effects { position: fixed; top: 0; left: 0; width: 100%; height: 100%; pointer-events: none; z-index: 0; }
        .gradient-orb { position: absolute; border-radius: 50%; filter: blur(100px); opacity: 0.4; }
        .gradient-orb-1 { width: 600px; height: 600px; background: radial-gradient(circle, rgba(0, 100, 200, 0.3) 0%, transparent 70%); top: -200px; left: -200px; animation: orbFloat1 25s ease-in-out infinite; }
        .gradient-orb-2 { width: 500px; height: 500px; background: radial-gradient(circle, rgba(0, 150, 255, 0.2) 0%, transparent 70%); bottom: -100px; right: -100px; animation: orbFloat2 30s ease-in-out infinite; }
        .gradient-orb-3 { width: 400px; height: 400px; background: radial-gradient(circle, rgba(0, 170, 255, 0.15) 0%, transparent 70%); top: 50%; left: 50%; transform: translate(-50%, -50%); animation: orbFloat3 20s ease-in-out infinite; }
        
        @keyframes orbFloat1 { 0%, 100% { transform: translate(0, 0) scale(1); } 50% { transform: translate(50px, 30px) scale(1.1); } }
        @keyframes orbFloat2 { 0%, 100% { transform: translate(0, 0) scale(1); } 50% { transform: translate(-40px, -20px) scale(1.05); } }
        @keyframes orbFloat3 { 0%, 100% { transform: translate(-50%, -50%) scale(1); } 50% { transform: translate(-50%, -50%) scale(1.15); } }

        .grid-overlay { position: absolute; top: 0; left: 0; width: 100%; height: 100%; background-image: linear-gradient(rgba(0, 170, 255, 0.02) 1px, transparent 1px), linear-gradient(90deg, rgba(0, 170, 255, 0.02) 1px, transparent 1px); background-size: 60px 60px; mask-image: radial-gradient(ellipse at center, black 0%, transparent 70%); -webkit-mask-image: radial-gradient(ellipse at center, black 0%, transparent 70%); }

        h1, h2, h3, h4, h5, h6 { font-family: 'Space Grotesk', sans-serif; font-weight: 600; letter-spacing: -0.02em; line-height: 1.2; }
        .highlight { color: var(--accent); }

        .container { max-width: 1200px; margin: 0 auto; padding: 0 clamp(20px, 5vw, 40px); }
        section { position: relative; z-index: 1; padding: 120px 0; }
        .section-header { text-align: center; margin-bottom: 80px; }
        .section-tag { display: inline-block; padding: 8px 20px; background: var(--accent-subtle); border: 1px solid rgba(0, 170, 255, 0.2); border-radius: 30px; font-size: 0.85rem; font-weight: 500; color: var(--accent); margin-bottom: 20px; letter-spacing: 0.05em; text-transform: uppercase; }
        .section-title { font-size: clamp(2.2rem, 5vw, 3.5rem); margin-bottom: 16px; }
        .section-subtitle { color: var(--fg-secondary); font-size: 1.1rem; max-width: 600px; margin: 0 auto; }

        .glass { background: var(--card-bg); backdrop-filter: blur(20px); -webkit-backdrop-filter: blur(20px); border: 1px solid var(--card-border); }
        .glass-elevated { background: rgba(30, 30, 45, 0.7); backdrop-filter: blur(30px); -webkit-backdrop-filter: blur(30px); border: 1px solid rgba(255, 255, 255, 0.08); }

        .btn { display: inline-flex; align-items: center; justify-content: center; gap: 10px; padding: 14px 28px; font-family: 'Space Grotesk', sans-serif; font-size: 0.95rem; font-weight: 500; border: none; border-radius: var(--radius-md); cursor: pointer; transition: all var(--transition-fast); text-decoration: none; position: relative; overflow: hidden; }
        .btn::before { content: ''; position: absolute; top: 0; left: 0; width: 100%; height: 100%; background: linear-gradient(135deg, rgba(255,255,255,0.1) 0%, transparent 50%); opacity: 0; transition: opacity var(--transition-fast); }
        .btn:hover::before { opacity: 1; }
        .btn-primary { background: linear-gradient(135deg, var(--accent) 0%, var(--accent-dim) 100%); color: white; box-shadow: 0 4px 24px var(--accent-glow), inset 0 1px 0 rgba(255,255,255,0.2); }
        .btn-primary:hover { transform: translateY(-3px); box-shadow: 0 8px 40px var(--accent-glow), inset 0 1px 0 rgba(255,255,255,0.2); }
        .btn-secondary { background: var(--glass-bg); color: var(--fg-primary); border: 1px solid var(--card-border); }
        .btn-secondary:hover { background: rgba(255, 255, 255, 0.06); border-color: var(--accent); color: var(--accent); }
        .btn-danger { background: var(--danger-dim); color: var(--danger); border: 1px solid rgba(255, 68, 102, 0.3); }
        .btn-danger:hover { background: var(--danger); color: white; }
        .btn-ghost { background: transparent; color: var(--fg-secondary); padding: 10px 16px; }
        .btn-ghost:hover { color: var(--accent); background: var(--accent-subtle); }
        .btn-sm { padding: 10px 18px; font-size: 0.85rem; }
        .btn-icon { width: 44px; height: 44px; padding: 0; border-radius: var(--radius-md); }

        nav { position: fixed; top: 0; left: 0; right: 0; z-index: 100; padding: 16px 0; background: rgba(8, 8, 16, 0.85); backdrop-filter: blur(20px); -webkit-backdrop-filter: blur(20px); border-bottom: 1px solid var(--card-border); transition: all var(--transition-fast); }
        nav.scrolled { padding: 12px 0; background: rgba(8, 8, 16, 0.95); }
        nav .container { display: flex; justify-content: space-between; align-items: center; }
        .logo { font-family: 'Space Grotesk', sans-serif; font-size: 1.6rem; font-weight: 700; background: linear-gradient(135deg, var(--fg-primary) 0%, var(--accent) 100%); -webkit-background-clip: text; -webkit-text-fill-color: transparent; background-clip: text; }
        .nav-links { display: flex; gap: 8px; list-style: none; }
        .nav-links a { color: var(--fg-secondary); text-decoration: none; font-size: 0.9rem; font-weight: 500; padding: 10px 18px; border-radius: var(--radius-sm); transition: all var(--transition-fast); position: relative; }
        .nav-links a:hover { color: var(--fg-primary); background: var(--glass-bg); }
        .nav-links a.active { color: var(--accent); }
        .mobile-toggle { display: none; background: none; border: none; color: var(--fg-primary); cursor: pointer; padding: 8px; }

        /* Hero */
        .hero { min-height: 100vh; display: flex; align-items: center; padding-top: 100px; }
        .hero-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 80px; align-items: center; }
        .hero-content { animation: fadeSlideUp 1s ease forwards; }
        @keyframes fadeSlideUp { from { opacity: 0; transform: translateY(40px); } to { opacity: 1; transform: translateY(0); } }
        .hero-badge { display: inline-flex; align-items: center; gap: 8px; padding: 8px 16px; background: var(--accent-subtle); border: 1px solid rgba(0, 170, 255, 0.2); border-radius: 30px; font-size: 0.85rem; color: var(--accent); margin-bottom: 24px; }
        .hero-badge::before { content: ''; width: 8px; height: 8px; background: var(--accent); border-radius: 50%; animation: pulse 2s ease-in-out infinite; }
        @keyframes pulse { 0%, 100% { opacity: 1; transform: scale(1); } 50% { opacity: 0.5; transform: scale(0.8); } }
        .hero-name { font-size: clamp(3rem, 7vw, 5rem); font-weight: 700; margin-bottom: 8px; background: linear-gradient(135deg, var(--fg-primary) 0%, var(--fg-secondary) 100%); -webkit-background-clip: text; -webkit-text-fill-color: transparent; background-clip: text; }
        .hero-title { font-size: clamp(1.1rem, 2.5vw, 1.5rem); color: var(--accent); margin-bottom: 24px; font-weight: 500; }
        .hero-intro { font-size: 1.15rem; color: var(--fg-secondary); margin-bottom: 36px; max-width: 520px; line-height: 1.8; }
        .hero-actions { display: flex; gap: 16px; flex-wrap: wrap; margin-bottom: 40px; }
        .social-links { display: flex; gap: 12px; }
        .social-link { width: 50px; height: 50px; display: flex; align-items: center; justify-content: center; background: var(--glass-bg); border: 1px solid var(--card-border); border-radius: var(--radius-md); color: var(--fg-secondary); text-decoration: none; transition: all var(--transition-fast); }
        .social-link:hover { color: var(--accent); border-color: var(--accent); background: var(--accent-subtle); transform: translateY(-4px); }
        .social-link svg { width: 22px; height: 22px; }
        .hero-visual { display: flex; justify-content: center; align-items: center; animation: fadeSlideUp 1s ease 0.2s forwards; opacity: 0; }
        .profile-wrapper { position: relative; width: 340px; height: 340px; }
        .profile-ring { position: absolute; top: -15px; left: -15px; right: -15px; bottom: -15px; border: 2px solid var(--accent); border-radius: 50%; opacity: 0.2; animation: ringPulse 4s ease-in-out infinite; }
        .profile-ring:nth-child(2) { top: -30px; left: -30px; right: -30px; bottom: -30px; opacity: 0.1; animation-delay: 1s; }
        @keyframes ringPulse { 0%, 100% { transform: scale(1); opacity: 0.2; } 50% { transform: scale(1.05); opacity: 0.05; } }
        .profile-photo { width: 100%; height: 100%; object-fit: cover; border-radius: 50%; border: 4px solid var(--accent); box-shadow: 0 0 80px var(--accent-glow); cursor: pointer; transition: all var(--transition-med); position: relative; z-index: 2; }
        .profile-photo:hover { box-shadow: 0 0 100px var(--accent-glow); }
        .profile-glow { position: absolute; top: 50%; left: 50%; width: 80%; height: 80%; transform: translate(-50%, -50%); background: radial-gradient(circle, var(--accent-glow) 0%, transparent 70%); filter: blur(40px); z-index: 1; }

        /* About */
        .about-content { max-width: 900px; margin: 0 auto; }
        .about-card { padding: 48px; border-radius: var(--radius-xl); position: relative; }
        .about-text { font-size: 1.2rem; color: var(--fg-secondary); line-height: 1.9; }
        .about-text p { margin-bottom: 20px; }
        .about-text p:last-child { margin-bottom: 0; }

        /* Education Timeline */
        .timeline { position: relative; max-width: 800px; margin: 0 auto; }
        .timeline::before { content: ''; position: absolute; left: 50%; transform: translateX(-50%); width: 3px; height: 100%; background: linear-gradient(180deg, var(--accent) 0%, var(--accent-dim) 50%, transparent 100%); border-radius: 2px; }
        .timeline-item { position: relative; width: 50%; padding: 0 50px 60px; }
        .timeline-item:nth-child(odd) { left: 0; text-align: right; }
        .timeline-item:nth-child(even) { left: 50%; text-align: left; }
        .timeline-marker { position: absolute; width: 20px; height: 20px; background: var(--bg-primary); border: 3px solid var(--accent); border-radius: 50%; top: 8px; z-index: 2; box-shadow: 0 0 20px var(--accent-glow); }
        .timeline-item:nth-child(odd) .timeline-marker { right: -10px; }
        .timeline-item:nth-child(even) .timeline-marker { left: -10px; }
        .timeline-card { padding: 28px; border-radius: var(--radius-lg); position: relative; transition: all var(--transition-med); }
        .timeline-card:hover { transform: translateY(-4px); border-color: rgba(0, 170, 255, 0.3); }
        .timeline-type { display: inline-block; padding: 6px 14px; background: var(--accent-subtle); border-radius: 20px; font-size: 0.8rem; font-weight: 600; color: var(--accent); margin-bottom: 12px; text-transform: uppercase; letter-spacing: 0.05em; }
        .timeline-card h3 { font-size: 1.3rem; margin-bottom: 8px; }
        .timeline-institution { color: var(--fg-secondary); font-size: 1rem; margin-bottom: 16px; }
        .timeline-grades { display: flex; flex-wrap: wrap; gap: 10px; }
        .timeline-item:nth-child(odd) .timeline-grades { justify-content: flex-end; }
        .grade-tag { padding: 6px 14px; background: var(--glass-bg); border: 1px solid var(--card-border); border-radius: var(--radius-sm); font-size: 0.85rem; }
        .grade-tag span { color: var(--accent); font-weight: 600; }

        /* Skills */
        .skills-categories { display: grid; grid-template-columns: repeat(auto-fit, minmax(320px, 1fr)); gap: 32px; }
        .skill-category { padding: 32px; border-radius: var(--radius-lg); transition: all var(--transition-med); }
        .skill-category:hover { border-color: rgba(0, 170, 255, 0.2); }
        .category-header { display: flex; align-items: center; gap: 14px; margin-bottom: 28px; }
        .category-icon { width: 48px; height: 48px; display: flex; align-items: center; justify-content: center; background: var(--accent-subtle); border-radius: var(--radius-md); color: var(--accent); }
        .category-icon svg { width: 24px; height: 24px; }
        .category-title { font-size: 1.2rem; font-weight: 600; }
        .skill-list { display: flex; flex-direction: column; gap: 18px; }
        .skill-item { position: relative; }
        .skill-header { display: flex; justify-content: space-between; align-items: center; margin-bottom: 10px; }
        .skill-name { font-weight: 500; color: var(--fg-primary); }
        .skill-percent { font-weight: 600; color: var(--accent); font-size: 0.9rem; }
        .skill-bar { height: 8px; background: var(--glass-bg); border-radius: 4px; overflow: hidden; position: relative; }
        .skill-fill { height: 100%; background: linear-gradient(90deg, var(--accent) 0%, var(--accent-bright) 100%); border-radius: 4px; width: 0; transition: width 1.2s cubic-bezier(0.4, 0, 0.2, 1); position: relative; }
        .skill-fill::after { content: ''; position: absolute; top: 0; left: 0; right: 0; bottom: 0; background: linear-gradient(90deg, transparent 0%, rgba(255,255,255,0.3) 50%, transparent 100%); animation: shimmer 2s infinite; }
        @keyframes shimmer { 0% { transform: translateX(-100%); } 100% { transform: translateX(100%); } }

        /* Projects */
        .projects-grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(380px, 1fr)); gap: 32px; }
        .project-card { border-radius: var(--radius-xl); overflow: hidden; transition: all var(--transition-med); position: relative; }
        .project-card:hover { transform: translateY(-8px); border-color: rgba(0, 170, 255, 0.3); box-shadow: var(--shadow-lg); }
        .project-image { width: 100%; height: 220px; object-fit: cover; border-bottom: 1px solid var(--card-border); }
        .project-placeholder { width: 100%; height: 220px; background: linear-gradient(135deg, var(--bg-tertiary) 0%, var(--bg-secondary) 100%); display: flex; align-items: center; justify-content: center; border-bottom: 1px solid var(--card-border); }
        .project-placeholder svg { width: 56px; height: 56px; color: var(--fg-muted); opacity: 0.5; }
        .project-body { padding: 28px; }
        .project-title { font-size: 1.4rem; margin-bottom: 12px; }
        .project-desc { color: var(--fg-secondary); font-size: 0.95rem; margin-bottom: 20px; line-height: 1.7; }
        .project-tech { display: flex; flex-wrap: wrap; gap: 8px; margin-bottom: 20px; }
        .tech-tag { padding: 6px 14px; background: var(--accent-subtle); border-radius: 20px; font-size: 0.8rem; color: var(--accent); font-weight: 500; }
        .project-link { display: inline-flex; align-items: center; gap: 8px; color: var(--accent); text-decoration: none; font-weight: 500; font-size: 0.9rem; transition: all var(--transition-fast); }
        .project-link:hover { gap: 12px; }

        /* Achievements */
        .achievements-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(340px, 1fr)); gap: 24px; max-width: 900px; margin: 0 auto; }
        .achievement-card { padding: 28px; border-radius: var(--radius-lg); display: flex; gap: 20px; transition: all var(--transition-med); }
        .achievement-card:hover { border-color: rgba(0, 170, 255, 0.3); transform: translateY(-4px); }
        .achievement-icon { width: 56px; height: 56px; display: flex; align-items: center; justify-content: center; background: linear-gradient(135deg, var(--accent) 0%, var(--accent-dim) 100%); border-radius: var(--radius-md); flex-shrink: 0; box-shadow: 0 4px 20px var(--accent-glow); }
        .achievement-icon svg { width: 28px; height: 28px; color: white; }
        .achievement-content h4 { font-size: 1.15rem; margin-bottom: 8px; }
        .achievement-content p { color: var(--fg-secondary); font-size: 0.95rem; }

        /* Contact */
        .contact-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 60px; max-width: 1000px; margin: 0 auto; }
        .contact-info h3 { font-size: 1.8rem; margin-bottom: 16px; }
        .contact-info p { color: var(--fg-secondary); margin-bottom: 32px; font-size: 1.05rem; }
        .contact-links { display: flex; flex-direction: column; gap: 16px; }
        .contact-item { display: flex; align-items: center; gap: 16px; padding: 18px 24px; border-radius: var(--radius-md); text-decoration: none; color: var(--fg-primary); transition: all var(--transition-fast); }
        .contact-item:hover { border-color: var(--accent); background: var(--accent-subtle); }
        .contact-item svg { width: 24px; height: 24px; color: var(--accent); flex-shrink: 0; }
        .contact-item span { color: var(--fg-secondary); }
        .contact-form-card { padding: 40px; border-radius: var(--radius-xl); }

        /* Edit Controls */
        .edit-controls { display: none; position: absolute; top: 16px; right: 16px; gap: 8px; z-index: 10; }
        .admin-mode .edit-controls { display: flex; }
        .edit-btn { width: 36px; height: 36px; border-radius: var(--radius-sm); border: none; cursor: pointer; display: flex; align-items: center; justify-content: center; transition: all var(--transition-fast); }
        .edit-btn svg { width: 16px; height: 16px; }
        .edit-btn-edit { background: var(--accent-subtle); color: var(--accent); }
        .edit-btn-edit:hover { background: var(--accent); color: white; }
        .edit-btn-delete { background: var(--danger-dim); color: var(--danger); }
        .edit-btn-delete:hover { background: var(--danger); color: white; }
        .admin-mode .glass, .admin-mode .glass-elevated, .admin-mod
