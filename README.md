/* Reset and Base Styles */
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

/* Enhanced Fonts */
@import url('https://fonts.cdnfonts.com/css/game-of-thrones');
@import url('https://fonts.googleapis.com/css2?family=Cinzel:wght@300;400;500;600;700;800&family=Playfair+Display:wght@400;500;600;700;800;900&family=Crimson+Text:wght@400;600&family=Uncial+Antiqua&display=swap');

:root {
    --primary-gold: #C9A961;
    --secondary-gold: #D4AF37;
    --accent-gold: #FFD700;
    --dark-red: #8B0000;
    --blood-red: #DC143C;
    --stark-blue: #2E5A87;
    --night-black: #0B0B0B;
    --iron-grey: #36454F;
    --parchment: #F4E4BC;
    --gradient-primary: linear-gradient(135deg, var(--primary-gold), var(--accent-gold), var(--secondary-gold));
    --gradient-dark: linear-gradient(135deg, var(--night-black), var(--iron-grey), var(--night-black));
    --shadow-gold: 0 0 30px rgba(201, 169, 97, 0.4);
    --shadow-dark: 0 10px 40px rgba(0, 0, 0, 0.8);
}

body {
    font-family: 'Playfair Display', serif;
    line-height: 1.7;
    color: #ffffff;
    background: 
        radial-gradient(ellipse at top, rgba(139, 0, 0, 0.1) 0%, transparent 50%),
        radial-gradient(ellipse at bottom, rgba(201, 169, 97, 0.05) 0%, transparent 50%),
        linear-gradient(180deg, var(--night-black) 0%, #1a1a1a 30%, #2a1a1a 70%, var(--night-black) 100%);
    background-attachment: fixed;
    overflow-x: hidden;
    font-weight: 400;
}

html {
    scroll-behavior: smooth;
}

.container {
    max-width: 1400px;
    margin: 0 auto;
    padding: 0 30px;
}

/* Luxury Navigation */
.navbar {
    position: fixed;
    top: 0;
    width: 100%;
    background: linear-gradient(180deg, 
        rgba(11, 11, 11, 0.98) 0%, 
        rgba(26, 26, 26, 0.95) 50%, 
        rgba(11, 11, 11, 0.90) 100%);
    backdrop-filter: blur(20px) saturate(180%);
    z-index: 1000;
    padding: 20px 0;
    transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
    border-bottom: 1px solid rgba(201, 169, 97, 0.2);
    box-shadow: var(--shadow-dark);
}

.navbar.scrolled {
    padding: 15px 0;
    background: linear-gradient(180deg, 
        rgba(11, 11, 11, 0.99) 0%, 
        rgba(26, 26, 26, 0.97) 50%, 
        rgba(11, 11, 11, 0.95) 100%);
}

.nav-container {
    max-width: 1400px;
    margin: 0 auto;
    padding: 0 30px;
    display: flex;
    justify-content: space-between;
    align-items: center;
}

.nav-logo {
    display: flex;
    flex-direction: column;
    align-items: center;
    position: relative;
    transform: scale(1);
    transition: transform 0.3s ease;
}

.nav-logo:hover {
    transform: scale(1.05);
}

.nav-logo h2 {
    font-family: 'Game of Thrones', 'Cinzel', serif;
    font-size: 3rem;
    font-weight: 800;
    background: var(--gradient-primary);
    background-size: 300% 300%;
    -webkit-background-clip: text;
    background-clip: text;
    -webkit-text-fill-color: transparent;
    animation: luxuryShimmer 4s ease-in-out infinite;
    filter: drop-shadow(0 0 20px rgba(201, 169, 97, 0.6));
    letter-spacing: 4px;
    margin-bottom: 5px;
    text-transform: uppercase;
}

@keyframes luxuryShimmer {
    0%, 100% { background-position: 0% 50%; }
    50% { background-position: 100% 50%; }
}

.nav-logo span {
    font-size: 1.1rem;
    color: var(--primary-gold);
    font-family: 'Cinzel', serif;
    letter-spacing: 3px;
    text-transform: uppercase;
    font-weight: 500;
}

.house-sigil {
    font-size: 2.2rem;
    margin-top: 8px;
    animation: royalFloat 5s ease-in-out infinite;
    filter: drop-shadow(0 0 15px var(--primary-gold));
}

@keyframes royalFloat {
    0%, 100% { transform: translateY(0px) rotate(0deg); }
    33% { transform: translateY(-4px) rotate(2deg); }
    66% { transform: translateY(-2px) rotate(-1deg); }
}

.nav-menu {
    display: flex;
    list-style: none;
    gap: 3rem;
    align-items: center;
}

.nav-menu a {
    color: #ffffff;
    text-decoration: none;
    font-weight: 500;
    font-family: 'Cinzel', serif;
    font-size: 1.1rem;
    transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
    position: relative;
    padding: 12px 20px;
    border-radius: 50px;
    text-transform: uppercase;
    letter-spacing: 1px;
}

.nav-menu a::before {
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    background: var(--gradient-primary);
    border-radius: 50px;
    opacity: 0;
    transform: scale(0.8);
    transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
    z-index: -1;
}

.nav-menu a:hover::before {
    opacity: 0.15;
    transform: scale(1);
}

.nav-menu a:hover {
    color: var(--accent-gold);
    transform: translateY(-2px);
    text-shadow: 0 0 10px rgba(201, 169, 97, 0.6);
}

.nav-menu a::after {
    content: '';
    position: absolute;
    bottom: 5px;
    left: 50%;
    transform: translateX(-50%);
    width: 0;
    height: 2px;
    background: var(--gradient-primary);
    transition: width 0.4s ease;
    border-radius: 2px;
}

.nav-menu a:hover::after {
    width: 70%;
}

/* Epic Hero Section */
.hero {
    height: 100vh;
    background: 
        linear-gradient(135deg, 
            rgba(11, 11, 11, 0.3) 0%, 
            rgba(139, 0, 0, 0.2) 25%, 
            rgba(201, 169, 97, 0.1) 50%, 
            rgba(139, 0, 0, 0.2) 75%, 
            rgba(11, 11, 11, 0.4) 100%),
        url('got-background.svg'),
        radial-gradient(ellipse at 30% 70%, rgba(201, 169, 97, 0.15) 0%, transparent 60%),
        radial-gradient(ellipse at 70% 30%, rgba(139, 0, 0, 0.1) 0%, transparent 60%),
        var(--gradient-dark);
    background-size: cover, cover, 150% 150%, 150% 150%, cover;
    background-position: center, center, center, center, center;
    background-attachment: fixed;
    display: flex;
    align-items: center;
    justify-content: center;
    text-align: center;
    position: relative;
    overflow: hidden;
}

.hero::before {
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: 
        radial-gradient(circle at 20% 80%, rgba(201, 169, 97, 0.1) 0%, transparent 40%),
        radial-gradient(circle at 80% 20%, rgba(139, 0, 0, 0.1) 0%, transparent 40%),
        radial-gradient(circle at 50% 50%, rgba(255, 215, 0, 0.05) 0%, transparent 30%);
    animation: mysticalAura 15s ease-in-out infinite;
    pointer-events: none;
}

@keyframes mysticalAura {
    0%, 100% { opacity: 0.8; transform: scale(1); }
    50% { opacity: 1; transform: scale(1.05); }
}

.hero-particles {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-image: 
        radial-gradient(2px 2px at 20px 30px, rgba(201, 169, 97, 0.8), transparent),
        radial-gradient(1px 1px at 40px 70px, rgba(255, 255, 255, 0.6), transparent),
        radial-gradient(3px 3px at 90px 40px, rgba(201, 169, 97, 0.9), transparent),
        radial-gradient(2px 2px at 130px 80px, rgba(255, 255, 255, 0.4), transparent),
        radial-gradient(1px 1px at 160px 30px, rgba(201, 169, 97, 0.7), transparent);
    background-repeat: repeat;
    background-size: 300px 150px;
    animation: enchantedParticles 20s linear infinite;
    opacity: 0.7;
}

@keyframes enchantedParticles {
    0% { transform: translateY(-100px) translateX(0px); }
    100% { transform: translateY(100vh) translateX(150px); }
}

.hero-content {
    z-index: 3;
    position: relative;
    max-width: 1000px;
    padding: 3rem;
    background: rgba(11, 11, 11, 0.3);
    backdrop-filter: blur(15px);
    border-radius: 30px;
    border: 1px solid rgba(201, 169, 97, 0.2);
    box-shadow: var(--shadow-dark);
}

.hero-title {
    font-family: 'Game of Thrones', 'Cinzel', serif;
    font-size: 8rem;
    font-weight: 900;
    margin-bottom: 1.5rem;
    background: linear-gradient(45deg, 
        var(--primary-gold) 0%, 
        var(--accent-gold) 25%, 
        #FFFFFF 50%, 
        var(--accent-gold) 75%, 
        var(--primary-gold) 100%);
    background-size: 300% 300%;
    -webkit-background-clip: text;
    background-clip: text;
    -webkit-text-fill-color: transparent;
    animation: epicGlow 6s ease-in-out infinite;
    filter: drop-shadow(0 0 40px rgba(201, 169, 97, 0.8));
    letter-spacing: 6px;
    text-transform: uppercase;
    line-height: 0.9;
}

@keyframes epicGlow {
    0%, 100% { 
        background-position: 0% 50%; 
        transform: scale(1);
        filter: drop-shadow(0 0 40px rgba(201, 169, 97, 0.8));
    }
    50% { 
        background-position: 100% 50%; 
        transform: scale(1.02);
        filter: drop-shadow(0 0 60px rgba(255, 215, 0, 1));
    }
}

.hero-subtitle {
    font-family: 'Game of Thrones', 'Playfair Display', serif;
    font-size: 3.5rem;
    color: rgba(255, 255, 255, 0.9);
    margin-bottom: 2rem;
    letter-spacing: 10px;
    text-transform: uppercase;
    font-weight: 600;
    text-shadow: 0 0 20px rgba(255, 255, 255, 0.3);
    animation: subtitleFloat 4s ease-in-out infinite;
}

@keyframes subtitleFloat {
    0%, 100% { transform: translateY(0px); opacity: 0.9; }
    50% { transform: translateY(-5px); opacity: 1; }
}

/* Luxury House Banner */
.house-banner {
    background: linear-gradient(135deg, 
        rgba(139, 0, 0, 0.9) 0%, 
        rgba(26, 26, 26, 0.95) 30%, 
        rgba(139, 0, 0, 0.9) 100%);
    border: 3px solid transparent;
    background-clip: padding-box;
    padding: 2.5rem 4rem;
    margin: 3rem 0;
    border-radius: 25px;
    position: relative;
    overflow: hidden;
    box-shadow: 
        var(--shadow-dark),
        inset 0 1px 0 rgba(255, 255, 255, 0.1),
        0 0 0 1px rgba(201, 169, 97, 0.3);
    backdrop-filter: blur(20px);
}

.house-banner::before {
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    background: var(--gradient-primary);
    background-size: 400% 400%;
    z-index: -1;
    margin: -3px;
    border-radius: 25px;
    animation: royalBorderPulse 6s ease-in-out infinite;
}

@keyframes royalBorderPulse {
    0%, 100% { 
        background-position: 0% 50%; 
        opacity: 0.8; 
        filter: blur(0px);
    }
    50% { 
        background-position: 100% 50%; 
        opacity: 1; 
        filter: blur(1px);
    }
}

.banner-text {
    font-family: 'Game of Thrones', 'Playfair Display', serif;
    font-size: 2.8rem;
    background: linear-gradient(45deg, 
        var(--primary-gold), 
        var(--accent-gold), 
        #FFFFFF, 
        var(--accent-gold), 
        var(--primary-gold));
    background-size: 300% 300%;
    -webkit-background-clip: text;
    background-clip: text;
    -webkit-text-fill-color: transparent;
    animation: bannerShimmer 5s ease-in-out infinite;
    text-align: center;
    font-weight: 700;
    letter-spacing: 4px;
    text-transform: uppercase;
    filter: drop-shadow(0 0 30px rgba(201, 169, 97, 0.7));
    line-height: 1.2;
}

@keyframes bannerShimmer {
    0%, 100% { background-position: 0% 50%; }
    50% { background-position: 100% 50%; }
}

.house-motto {
    font-family: 'Playfair Display', serif;
    font-size: 1.4rem;
    color: rgba(255, 255, 255, 0.8);
    text-align: center;
    font-style: italic;
    margin-top: 1rem;
    font-weight: 500;
    letter-spacing: 1px;
    text-shadow: 0 2px 10px rgba(0, 0, 0, 0.8);
}

.hero-tagline {
    font-size: 1.8rem;
    color: rgba(255, 255, 255, 0.8);
    margin-bottom: 3rem;
    font-style: italic;
    font-family: 'Playfair Display', serif;
    font-weight: 500;
    text-shadow: 0 0 15px rgba(255, 255, 255, 0.3);
    letter-spacing: 1px;
}

.hero-theme {
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 3rem;
    margin-bottom: 3rem;
    color: var(--primary-gold);
    font-size: 1.6rem;
    font-family: 'Cinzel', serif;
    font-weight: 600;
    background: rgba(11, 11, 11, 0.6);
    padding: 1.5rem 3rem;
    border-radius: 60px;
    border: 1px solid rgba(201, 169, 97, 0.3);
    backdrop-filter: blur(15px);
    box-shadow: var(--shadow-gold);
}

.hero-quote {
    font-family: 'Playfair Display', serif;
    font-size: 1.5rem;
    color: rgba(255, 255, 255, 0.9);
    margin-bottom: 4rem;
    font-style: italic;
    max-width: 700px;
    margin-left: auto;
    margin-right: auto;
    padding: 2rem 3rem;
    background: rgba(11, 11, 11, 0.4);
    border-radius: 20px;
    border-left: 5px solid var(--primary-gold);
    backdrop-filter: blur(15px);
    box-shadow: var(--shadow-dark);
    font-weight: 500;
    letter-spacing: 0.5px;
    line-height: 1.6;
}

/* Luxury Button System */
.hero-buttons {
    display: flex;
    gap: 2rem;
    justify-content: center;
    flex-wrap: wrap;
    margin-bottom: 3rem;
}

.btn {
    display: inline-flex;
    align-items: center;
    justify-content: center;
    padding: 20px 50px;
    text-decoration: none;
    border-radius: 60px;
    font-weight: 600;
    transition: all 0.5s cubic-bezier(0.4, 0, 0.2, 1);
    position: relative;
    overflow: hidden;
    text-transform: uppercase;
    letter-spacing: 2px;
    border: none;
    cursor: pointer;
    font-family: 'Cinzel', serif;
    font-size: 1.2rem;
    box-shadow: var(--shadow-dark);
    backdrop-filter: blur(10px);
    min-width: 200px;
}

.btn::before {
    content: '';
    position: absolute;
    top: 0;
    left: -100%;
    width: 100%;
    height: 100%;
    background: linear-gradient(90deg, 
        transparent, 
        rgba(255, 255, 255, 0.3), 
        transparent);
    transition: left 0.8s ease;
    z-index: 1;
}

.btn:hover::before {
    left: 100%;
}

.btn-primary {
    background: var(--gradient-primary);
    color: var(--night-black);
    border: 2px solid transparent;
    font-weight: 700;
}

.btn-primary:hover {
    transform: translateY(-5px) scale(1.05);
    box-shadow: 
        0 20px 60px rgba(201, 169, 97, 0.4),
        0 0 0 1px rgba(201, 169, 97, 0.6);
    background: linear-gradient(45deg, 
        var(--accent-gold), 
        #FFFFFF, 
        var(--accent-gold));
}

.btn-secondary {
    background: rgba(201, 169, 97, 0.1);
    color: var(--primary-gold);
    border: 2px solid var(--primary-gold);
}

.btn-secondary:hover {
    background: var(--gradient-primary);
    color: var(--night-black);
    transform: translateY(-5px) scale(1.05);
    box-shadow: 
        0 20px 60px rgba(201, 169, 97, 0.3),
        0 0 0 1px rgba(201, 169, 97, 0.6);
}

.scroll-indicator {
    position: absolute;
    bottom: 50px;
    left: 50%;
    transform: translateX(-50%);
    color: var(--primary-gold);
    text-align: center;
}

.scroll-arrow {
    width: 3px;
    height: 40px;
    background: var(--gradient-primary);
    position: relative;
    animation: scrollPulse 3s infinite;
    border-radius: 3px;
    margin: 0 auto;
}

.scroll-arrow::after {
    content: '';
    position: absolute;
    bottom: -12px;
    left: -8px;
    width: 0;
    height: 0;
    border-left: 8px solid transparent;
    border-right: 8px solid transparent;
    border-top: 12px solid var(--primary-gold);
}

@keyframes scrollPulse {
    0%, 100% { opacity: 0.4; transform: translateY(0px); }
    50% { opacity: 1; transform: translateY(10px); }
}

/* Enhanced Section Headers */
.section-header {
    text-align: center;
    margin-bottom: 5rem;
    position: relative;
}

.section-header h2 {
    font-family: 'Game of Thrones', 'Playfair Display', serif;
    font-size: 4.5rem;
    color: var(--primary-gold);
    margin-bottom: 2rem;
    position: relative;
    letter-spacing: 3px;
    font-weight: 800;
    text-transform: uppercase;
    background: var(--gradient-primary);
    background-size: 200% 200%;
    -webkit-background-clip: text;
    background-clip: text;
    -webkit-text-fill-color: transparent;
    animation: headerShimmer 4s ease-in-out infinite;
    filter: drop-shadow(0 0 20px rgba(201, 169, 97, 0.6));
}

@keyframes headerShimmer {
    0%, 100% { background-position: 0% 50%; }
    50% { background-position: 100% 50%; }
}

.section-header h2::after {
    content: '';
    position: absolute;
    bottom: -15px;
    left: 50%;
    transform: translateX(-50%);
    width: 150px;
    height: 4px;
    background: var(--gradient-primary);
    border-radius: 2px;
    box-shadow: var(--shadow-gold);
}

.section-header p {
    font-size: 1.4rem;
    color: rgba(255, 255, 255, 0.8);
    max-width: 700px;
    margin: 0 auto;
    font-family: 'Playfair Display', serif;
    font-weight: 500;
    line-height: 1.6;
    letter-spacing: 0.5px;
}

/* Premium About Section - Great Houses */
.about {
    padding: 150px 0;
    background: 
        linear-gradient(135deg, 
            rgba(11, 11, 11, 0.8) 0%, 
            rgba(139, 0, 0, 0.15) 25%, 
            rgba(201, 169, 97, 0.1) 50%, 
            rgba(139, 0, 0, 0.15) 75%, 
            rgba(11, 11, 11, 0.8) 100%),
        radial-gradient(ellipse at 20% 80%, rgba(201, 169, 97, 0.1) 0%, transparent 50%),
        radial-gradient(ellipse at 80% 20%, rgba(139, 0, 0, 0.1) 0%, transparent 50%);
    position: relative;
    overflow: hidden;
}

.about::before {
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    background: url('got-background.svg');
    background-size: cover;
    background-position: center;
    opacity: 0.1;
    animation: backgroundFloat 20s ease-in-out infinite;
}

@keyframes backgroundFloat {
    0%, 100% { transform: scale(1) translate(0, 0); }
    50% { transform: scale(1.05) translate(-2%, 2%); }
}

.about-content {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(400px, 1fr));
    gap: 4rem;
    margin-top: 3rem;
    position: relative;
    z-index: 2;
}

.about-card {
    background: linear-gradient(135deg, 
        rgba(11, 11, 11, 0.8) 0%, 
        rgba(26, 26, 26, 0.9) 50%, 
        rgba(11, 11, 11, 0.8) 100%);
    backdrop-filter: blur(20px) saturate(180%);
    border-radius: 30px;
    padding: 3rem;
    position: relative;
    overflow: hidden;
    transition: all 0.6s cubic-bezier(0.4, 0, 0.2, 1);
    border: 1px solid rgba(201, 169, 97, 0.2);
    box-shadow: var(--shadow-dark);
}

.about-card::before {
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    background: var(--gradient-primary);
    opacity: 0;
    transition: all 0.6s ease;
    border-radius: 30px;
    z-index: -1;
}

.about-card:hover::before {
    opacity: 0.05;
}

.about-card:hover {
    transform: translateY(-15px) scale(1.02);
    box-shadow: 
        0 30px 80px rgba(0, 0, 0, 0.6),
        0 0 0 1px rgba(201, 169, 97, 0.4),
        var(--shadow-gold);
    border-color: rgba(201, 169, 97, 0.4);
}

.house-stark {
    border-left: 5px solid var(--stark-blue);
}

.house-stark:hover {
    box-shadow: 
        0 30px 80px rgba(0, 0, 0, 0.6),
        0 0 40px rgba(46, 90, 135, 0.3),
        0 0 0 1px rgba(46, 90, 135, 0.4);
}

.house-targaryen {
    border-left: 5px solid var(--blood-red);
}

.house-targaryen:hover {
    box-shadow: 
        0 30px 80px rgba(0, 0, 0, 0.6),
        0 0 40px rgba(220, 20, 60, 0.3),
        0 0 0 1px rgba(220, 20, 60, 0.4);
}

.house-lannister {
    border-left: 5px solid var(--accent-gold);
}

.house-lannister:hover {
    box-shadow: 
        0 30px 80px rgba(0, 0, 0, 0.6),
        0 0 40px rgba(255, 215, 0, 0.3),
        0 0 0 1px rgba(255, 215, 0, 0.4);
}

.about-card h3 {
    font-family: 'Game of Thrones', 'Playfair Display', serif;
    font-size: 2.5rem;
    color: var(--primary-gold);
    margin-bottom: 1rem;
    font-weight: 700;
    letter-spacing: 2px;
    text-transform: uppercase;
    background: var(--gradient-primary);
    background-size: 200% 200%;
    -webkit-background-clip: text;
    background-clip: text;
    -webkit-text-fill-color: transparent;
    animation: cardTitleShimmer 3s ease-in-out infinite;
}

@keyframes cardTitleShimmer {
    0%, 100% { background-position: 0% 50%; }
    50% { background-position: 100% 50%; }
}

.house-motto {
    font-family: 'Playfair Display', serif;
    font-size: 1.3rem;
    color: var(--primary-gold);
    text-align: center;
    font-style: italic;
    margin: 1.5rem 0;
    font-weight: 600;
    letter-spacing: 1px;
    padding: 1rem;
    background: rgba(201, 169, 97, 0.1);
    border-radius: 15px;
    border: 1px solid rgba(201, 169, 97, 0.2);
}

.about-card p {
    font-size: 1.2rem;
    line-height: 1.8;
    color: rgba(255, 255, 255, 0.9);
    font-family: 'Playfair Display', serif;
    font-weight: 400;
    letter-spacing: 0.5px;
}

/* Enhanced 3D House Sigils */
.house-sigil-3d {
    width: 100px;
    height: 100px;
    margin: 0 auto 2rem;
    position: relative;
    animation: luxurySigilFloat 6s ease-in-out infinite;
    filter: drop-shadow(0 0 20px rgba(201, 169, 97, 0.4));
}

@keyframes luxurySigilFloat {
    0%, 100% { 
        transform: translateY(0px) rotate(0deg) scale(1); 
        filter: drop-shadow(0 0 20px rgba(201, 169, 97, 0.4));
    }
    33% { 
        transform: translateY(-8px) rotate(2deg) scale(1.05); 
        filter: drop-shadow(0 0 30px rgba(201, 169, 97, 0.6));
    }
    66% { 
        transform: translateY(-4px) rotate(-1deg) scale(1.02); 
        filter: drop-shadow(0 0 25px rgba(201, 169, 97, 0.5));
    }
}

.stark-wolf::before {
    content: '';
    position: absolute;
    width: 100%;
    height: 100%;
    background: linear-gradient(135deg, 
        var(--stark-blue) 0%, 
        #4A90E2 30%, 
        #87CEEB 50%, 
        #4A90E2 70%, 
        var(--stark-blue) 100%);
    clip-path: polygon(50% 5%, 65% 15%, 85% 10%, 95% 30%, 90% 45%, 95% 60%, 85% 80%, 65% 85%, 50% 95%, 35% 85%, 15% 80%, 5% 60%, 10% 45%, 5% 30%, 15% 10%, 35% 15%);
    animation: wolfBreath 4s ease-in-out infinite;
    border-radius: 15px;
}

.stark-wolf::after {
    content: '';
    position: absolute;
    width: 12px;
    height: 12px;
    background: radial-gradient(circle, var(--accent-gold), #FFA500);
    border-radius: 50%;
    top: 35%;
    left: 42%;
    animation: wolfEyeGlow 3s ease-in-out infinite;
    box-shadow: 
        2px 0 0 var(--accent-gold),
        0 0 15px rgba(255, 215, 0, 0.6);
}

@keyframes wolfBreath {
    0%, 100% { 
        filter: drop-shadow(0 0 15px var(--stark-blue)) brightness(1);
        transform: scale(1);
    }
    50% { 
        filter: drop-shadow(0 0 25px #4A90E2) brightness(1.1);
        transform: scale(1.02);
    }
}

@keyframes wolfEyeGlow {
    0%, 100% { 
        opacity: 1; 
        transform: scale(1);
        box-shadow: 2px 0 0 var(--accent-gold), 0 0 15px rgba(255, 215, 0, 0.6);
    }
    50% { 
        opacity: 0.7; 
        transform: scale(1.3);
        box-shadow: 2px 0 0 var(--accent-gold), 0 0 25px rgba(255, 215, 0, 0.9);
    }
}

.targaryen-dragon::before {
    content: '';
    position: absolute;
    width: 100%;
    height: 100%;
    background: linear-gradient(135deg, 
        var(--dark-red) 0%, 
        var(--blood-red) 25%, 
        #FF4500 50%, 
        var(--blood-red) 75%, 
        var(--dark-red) 100%);
    clip-path: polygon(25% 5%, 45% 15%, 65% 8%, 85% 25%, 92% 45%, 85% 65%, 65% 82%, 70% 95%, 50% 100%, 30% 95%, 35% 82%, 15% 65%, 8% 45%, 15% 25%);
    animation: dragonPower 5s ease-in-out infinite;
    border-radius: 15px;
}

.targaryen-dragon::after {
    content: '';
    position: absolute;
    width: 20px;
    height: 12px;
    background: linear-gradient(90deg, 
        var(--accent-gold), 
        #FF6347, 
        var(--accent-gold));
    top: 65%;
    left: 25%;
    clip-path: polygon(0% 50%, 30% 0%, 100% 20%, 80% 100%);
    animation: dragonFlameEnhanced 4s ease-in-out infinite;
    filter: drop-shadow(0 0 10px #FF4500);
}

@keyframes dragonPower {
    0%, 100% { 
        filter: drop-shadow(0 0 15px var(--dark-red)) brightness(1);
        transform: scale(1);
    }
    50% { 
        filter: drop-shadow(0 0 30px var(--blood-red)) brightness(1.2);
        transform: scale(1.03);
    }
}

@keyframes dragonFlameEnhanced {
    0%, 100% { 
        opacity: 0.8; 
        transform: scaleX(1) scaleY(1);
        filter: drop-shadow(0 0 10px #FF4500);
    }
    50% { 
        opacity: 1; 
        transform: scaleX(1.4) scaleY(1.2);
        filter: drop-shadow(0 0 20px #FF6347);
    }
}

.lannister-lion::before {
    content: '';
    position: absolute;
    width: 100%;
    height: 100%;
    background: linear-gradient(135deg, 
        var(--secondary-gold) 0%, 
        var(--accent-gold) 25%, 
        #FFED4A 50%, 
        var(--accent-gold) 75%, 
        var(--secondary-gold) 100%);
    clip-path: polygon(35% 8%, 50% 2%, 65% 8%, 82% 20%, 88% 40%, 82% 60%, 70% 78%, 60% 88%, 50% 98%, 40% 88%, 30% 78%, 18% 60%, 12% 40%, 18% 20%);
    animation: lionMajesty 4s ease-in-out infinite;
    border-radius: 15px;
}

.lannister-lion::after {
    content: '';
    position: absolute;
    width: 25px;
    height: 8px;
    background: linear-gradient(90deg, #8B4513, #CD853F, #D2B48C);
    top: 45%;
    left: 50%;
    transform: translateX(-50%);
    clip-path: polygon(0% 0%, 100% 0%, 85% 100%, 15% 100%);
    filter: drop-shadow(0 0 5px #8B4513);
}

@keyframes lionMajesty {
    0%, 100% { 
        filter: drop-shadow(0 0 15px var(--secondary-gold)) brightness(1);
        transform: scale(1);
    }
    50% { 
        filter: drop-shadow(0 0 25px var(--accent-gold)) brightness(1.15);
        transform: scale(1.02);
    }
}

/* Enhanced 3D Icons for Navigation and Cards */
.castle-3d, .sword-3d, .scroll-3d, .crown-3d, .clock-3d, .shield-3d {
    width: 24px;
    height: 24px;
    position: relative;
    display: inline-block;
    margin-right: 10px;
    vertical-align: middle;
}

.castle-3d::before {
    content: '';
    position: absolute;
    width: 100%;
    height: 70%;
    background: linear-gradient(135deg, var(--iron-grey), #708090, var(--iron-grey));
    bottom: 0;
    clip-path: polygon(15% 100%, 15% 70%, 10% 70%, 10% 40%, 20% 40%, 20% 20%, 35% 20%, 35% 0%, 65% 0%, 65% 20%, 80% 20%, 80% 40%, 90% 40%, 90% 70%, 85% 70%, 85% 100%);
    animation: castlePresence 4s ease-in-out infinite;
}

@keyframes castlePresence {
    0%, 100% { filter: drop-shadow(0 0 5px var(--iron-grey)); }
    50% { filter: drop-shadow(0 0 10px #708090); }
}

.sword-3d::before {
    content: '';
    position: absolute;
    width: 3px;
    height: 18px;
    background: linear-gradient(180deg, #E5E5E5, #C0C0C0, #A8A8A8);
    left: 50%;
    transform: translateX(-50%);
    filter: drop-shadow(0 0 3px #C0C0C0);
}

.sword-3d::after {
    content: '';
    position: absolute;
    width: 12px;
    height: 4px;
    background: linear-gradient(90deg, #8B4513, #CD853F, #8B4513);
    left: 50%;
    top: 16px;
    transform: translateX(-50%);
    border-radius: 2px;
}

.scroll-3d::before {
    content: '';
    position: absolute;
    width: 18px;
    height: 20px;
    background: linear-gradient(135deg, var(--parchment), #F5DEB3, #DEB887);
    border-radius: 3px;
    left: 50%;
    transform: translateX(-50%);
    box-shadow: inset 1px 0 2px rgba(0,0,0,0.1), inset -1px 0 2px rgba(0,0,0,0.1);
}

.scroll-3d::after {
    content: '';
    position: absolute;
    width: 14px;
    height: 1px;
    background: #8B4513;
    top: 25%;
    left: 50%;
    transform: translateX(-50%);
    box-shadow: 0 4px 0 #8B4513, 0 8px 0 #8B4513;
}

.crown-3d::before {
    content: '';
    position: absolute;
    width: 100%;
    height: 100%;
    background: var(--gradient-primary);
    clip-path: polygon(0% 100%, 12% 30%, 20% 100%, 30% 15%, 40% 100%, 50% 5%, 60% 100%, 70% 15%, 80% 100%, 88% 30%, 100% 100%);
    animation: crownMajesty 3s ease-in-out infinite;
}

@keyframes crownMajesty {
    0%, 100% { 
        filter: drop-shadow(0 0 8px var(--primary-gold));
        transform: scale(1);
    }
    50% { 
        filter: drop-shadow(0 0 15px var(--accent-gold));
        transform: scale(1.05);
    }
}

.clock-3d::before {
    content: '';
    position: absolute;
    width: 20px;
    height: 20px;
    background: linear-gradient(135deg, var(--iron-grey), #708090);
    border-radius: 50%;
    left: 50%;
    top: 50%;
    transform: translate(-50%, -50%);
    border: 2px solid var(--primary-gold);
}

.clock-3d::after {
    content: '';
    position: absolute;
    width: 2px;
    height: 8px;
    background: var(--primary-gold);
    left: 50%;
    top: 50%;
    transform: translate(-50%, -100%);
    transform-origin: bottom;
    animation: clockTick 4s linear infinite;
}

@keyframes clockTick {
    from { transform: translate(-50%, -100%) rotate(0deg); }
    to { transform: translate(-50%, -100%) rotate(360deg); }
}

.shield-3d::before {
    content: '';
    position: absolute;
    width: 100%;
    height: 100%;
    background: linear-gradient(135deg, var(--iron-grey), #708090, var(--iron-grey));
    clip-path: polygon(50% 0%, 100% 25%, 85% 100%, 15% 100%, 0% 25%);
    filter: drop-shadow(0 0 5px var(--iron-grey));
}

.shield-3d::after {
    content: '';
    position: absolute;
    width: 12px;
    height: 2px;
    background: var(--primary-gold);
    top: 40%;
    left: 50%;
    transform: translateX(-50%);
}

/* Enhanced 3D Card Icons */
.code-icon-3d, .fire-icon-3d, .crown-icon-3d {
    width: 80px;
    height: 60px;
    position: relative;
    margin: 0 auto 1.5rem;
}

.code-icon-3d::before {
    content: '</>';
    position: absolute;
    font-size: 2.5rem;
    color: var(--primary-gold);
    font-family: 'Courier New', monospace;
    font-weight: bold;
    left: 50%;
    top: 50%;
    transform: translate(-50%, -50%);
    text-shadow: 0 0 15px var(--primary-gold);
    animation: codeGlow 3s ease-in-out infinite;
}

@keyframes codeGlow {
    0%, 100% { 
        text-shadow: 0 0 15px var(--primary-gold);
        transform: translate(-50%, -50%) scale(1);
    }
    50% { 
        text-shadow: 0 0 25px var(--accent-gold);
        transform: translate(-50%, -50%) scale(1.05);
    }
}

.fire-icon-3d::before {
    content: '';
    position: absolute;
    width: 100%;
    height: 100%;
    background: linear-gradient(180deg, #FF4500, #FF6347, var(--accent-gold));
    clip-path: polygon(50% 0%, 60% 30%, 75% 25%, 80% 50%, 70% 65%, 80% 80%, 50% 100%, 20% 80%, 30% 65%, 20% 50%, 25% 25%, 40% 30%);
    animation: fireFlickerEnhanced 3s ease-in-out infinite;
}

@keyframes fireFlickerEnhanced {
    0%, 100% { 
        transform: scale(1) rotate(0deg); 
        filter: brightness(1) drop-shadow(0 0 10px #FF4500);
    }
    25% { 
        transform: scale(1.08) rotate(2deg); 
        filter: brightness(1.3) drop-shadow(0 0 20px #FF6347);
    }
    75% { 
        transform: scale(0.95) rotate(-1deg); 
        filter: brightness(0.9) drop-shadow(0 0 15px #FF4500);
    }
}

.crown-icon-3d::before {
    content: '';
    position: absolute;
    width: 100%;
    height: 70%;
    background: var(--gradient-primary);
    clip-path: polygon(0% 100%, 12% 30%, 20% 100%, 30% 15%, 40% 100%, 50% 5%, 60% 100%, 70% 15%, 80% 100%, 88% 30%, 100% 100%);
    animation: crownMajesty 4s ease-in-out infinite;
    top: 15%;
}

/* Rules Section 3D Elements */
.royal-seal-3d {
    width: 60px;
    height: 60px;
    margin: 1rem auto;
    position: relative;
}

.royal-seal-3d::before {
    content: '';
    position: absolute;
    width: 100%;
    height: 100%;
    background: linear-gradient(135deg, #FFD700, #FFA500, #DAA520);
    border-radius: 50%;
    filter: drop-shadow(0 0 15px #FFD700);
    animation: sealRotate 8s linear infinite;
}

.royal-seal-3d::after {
    content: '';
    position: absolute;
    width: 30px;
    height: 20px;
    background: linear-gradient(135deg, #8B4513, #CD853F);
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    clip-path: polygon(0% 100%, 15% 30%, 25% 100%, 35% 20%, 45% 100%, 50% 10%, 55% 100%, 65% 20%, 75% 100%, 85% 30%, 100% 100%);
}

@keyframes sealRotate {
    from { transform: rotate(0deg); }
    to { transform: rotate(360deg); }
}

.rule-scroll-3d {
    width: 40px;
    height: 50px;
    margin: 1rem auto;
    position: relative;
}

.rule-scroll-3d::before {
    content: '';
    position: absolute;
    width: 100%;
    height: 100%;
    background: linear-gradient(180deg, #F5DEB3, #DEB887, #D2B48C);
    border-radius: 5px;
    box-shadow: inset 2px 0 4px rgba(0,0,0,0.2), inset -2px 0 4px rgba(0,0,0,0.2);
}

.rule-scroll-3d::after {
    content: '';
    position: absolute;
    width: 30px;
    height: 2px;
    background: #8B4513;
    top: 20%;
    left: 50%;
    transform: translateX(-50%);
    box-shadow: 0 8px 0 #8B4513, 0 16px 0 #8B4513;
}

.hourglass-3d {
    width: 30px;
    height: 50px;
    margin: 1rem auto;
    position: relative;
}

.hourglass-3d::before {
    content: '';
    position: absolute;
    width: 100%;
    height: 48%;
    background: linear-gradient(135deg, #8B4513, #CD853F);
    top: 0;
    clip-path: polygon(0% 0%, 100% 0%, 80% 100%, 20% 100%);
}

.hourglass-3d::after {
    content: '';
    position: absolute;
    width: 100%;
    height: 48%;
    background: linear-gradient(135deg, #8B4513, #CD853F);
    bottom: 0;
    clip-path: polygon(20% 0%, 80% 0%, 100% 100%, 0% 100%);
}

.sword-cross-3d {
    width: 40px;
    height: 40px;
    margin: 1rem auto;
    position: relative;
}

.sword-cross-3d::before {
    content: '';
    position: absolute;
    width: 4px;
    height: 35px;
    background: linear-gradient(180deg, #C0C0C0, #8B8B8B);
    left: 50%;
    top: 50%;
    transform: translate(-50%, -50%);
}

.sword-cross-3d::after {
    content: '';
    position: absolute;
    width: 25px;
    height: 4px;
    background: linear-gradient(90deg, #C0C0C0, #8B8B8B);
    left: 50%;
    top: 30%;
    transform: translate(-50%, -50%);
}

.dragon-egg-3d {
    width: 35px;
    height: 45px;
    margin: 1rem auto;
    position: relative;
}

.dragon-egg-3d::before {
    content: '';
    position: absolute;
    width: 100%;
    height: 100%;
    background: linear-gradient(135deg, #2F4F4F, #696969, #2F4F4F);
    border-radius: 50% 50% 50% 50% / 60% 60% 40% 40%;
    animation: eggGlow 4s ease-in-out infinite;
}

.dragon-egg-3d::after {
    content: '';
    position: absolute;
    width: 20px;
    height: 25px;
    background: linear-gradient(135deg, #8B0000, #DC143C);
    border-radius: 50% 50% 50% 50% / 60% 60% 40% 40%;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    opacity: 0.7;
    animation: eggPulse 3s ease-in-out infinite;
}

@keyframes eggGlow {
    0%, 100% { filter: drop-shadow(0 0 8px #2F4F4F); }
    50% { filter: drop-shadow(0 0 15px #696969); }
}

@keyframes eggPulse {
    0%, 100% { opacity: 0.7; transform: translate(-50%, -50%) scale(1); }
    50% { opacity: 1; transform: translate(-50%, -50%) scale(1.1); }
}

/* Prize Section 3D Elements */
.iron-throne-prize {
    width: 80px;
    height: 100px;
    margin: 0 auto;
    position: relative;
}

.iron-throne-prize::before {
    content: '';
    position: absolute;
    width: 100%;
    height: 80%;
    background: linear-gradient(135deg, #2F2F2F, #696969, #1C1C1C);
    bottom: 0;
    clip-path: polygon(15% 100%, 10% 70%, 5% 50%, 15% 30%, 25% 15%, 35% 5%, 50% 0%, 65% 5%, 75% 15%, 85% 30%, 95% 50%, 90% 70%, 85% 100%);
    animation: thronePresence 5s ease-in-out infinite;
}

.iron-throne-prize::after {
    content: '';
    position: absolute;
    width: 40px;
    height: 25px;
    background: linear-gradient(45deg, #1C1C1C, #2F2F2F);
    bottom: 0;
    left: 50%;
    transform: translateX(-50%);
    clip-path: polygon(0% 100%, 100% 100%, 85% 0%, 15% 0%);
}

@keyframes thronePresence {
    0%, 100% { filter: drop-shadow(0 0 10px #2F2F2F); }
    50% { filter: drop-shadow(0 0 20px #696969) brightness(1.1); }
}

.hand-pin-3d {
    width: 50px;
    height: 60px;
    margin: 0 auto;
    position: relative;
}

.hand-pin-3d::before {
    content: '';
    position: absolute;
    width: 35px;
    height: 40px;
    background: linear-gradient(135deg, #C0C0C0, #E5E5E5, #A8A8A8);
    top: 10px;
    left: 50%;
    transform: translateX(-50%);
    clip-path: polygon(40% 0%, 60% 0%, 100% 40%, 100% 60%, 90% 100%, 10% 100%, 0% 60%, 0% 40%);
    filter: drop-shadow(0 0 8px #C0C0C0);
}

.hand-pin-3d::after {
    content: '';
    position: absolute;
    width: 15px;
    height: 15px;
    background: linear-gradient(135deg, #FFD700, #FFA500);
    border-radius: 50%;
    top: 25px;
    left: 50%;
    transform: translateX(-50%);
}

.nights-watch-shield {
    width: 50px;
    height: 60px;
    margin: 0 auto;
    position: relative;
}

.nights-watch-shield::before {
    content: '';
    position: absolute;
    width: 100%;
    height: 100%;
    background: linear-gradient(135deg, #1C1C1C, #2F2F2F, #0A0A0A);
    clip-path: polygon(50% 0%, 100% 38%, 82% 100%, 18% 100%, 0% 38%);
    filter: drop-shadow(0 0 8px #1C1C1C);
}

.nights-watch-shield::after {
    content: '';
    position: absolute;
    width: 30px;
    height: 2px;
    background: #C0C0C0;
    top: 40%;
    left: 50%;
    transform: translateX(-50%);
    box-shadow: 0 8px 0 #C0C0C0;
}

/* Luxury Rules Section */
.rules {
    padding: 150px 0;
    background: 
        linear-gradient(135deg, 
            rgba(11, 11, 11, 0.9) 0%, 
            rgba(26, 26, 26, 0.8) 50%, 
            rgba(11, 11, 11, 0.9) 100%),
        radial-gradient(ellipse at 30% 70%, rgba(139, 0, 0, 0.1) 0%, transparent 50%),
        radial-gradient(ellipse at 70% 30%, rgba(201, 169, 97, 0.08) 0%, transparent 50%);
    position: relative;
    overflow: hidden;
}

.rules::before {
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    background: 
        linear-gradient(45deg, transparent 30%, rgba(201, 169, 97, 0.03) 50%, transparent 70%),
        linear-gradient(-45deg, transparent 30%, rgba(139, 0, 0, 0.03) 50%, transparent 70%);
    animation: rulePattern 15s linear infinite;
}

@keyframes rulePattern {
    0% { transform: translateX(-100px) translateY(-100px); }
    100% { transform: translateX(100px) translateY(100px); }
}

.rules-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
    gap: 3rem;
    margin-top: 4rem;
    position: relative;
    z-index: 2;
}

.rule-card {
    background: linear-gradient(135deg, 
        rgba(11, 11, 11, 0.9) 0%, 
        rgba(26, 26, 26, 0.95) 50%, 
        rgba(11, 11, 11, 0.9) 100%);
    backdrop-filter: blur(20px) saturate(180%);
    border-radius: 25px;
    padding: 3rem 2.5rem;
    position: relative;
    overflow: hidden;
    transition: all 0.6s cubic-bezier(0.4, 0, 0.2, 1);
    border: 1px solid rgba(201, 169, 97, 0.2);
    box-shadow: var(--shadow-dark);
    text-align: center;
}

.rule-card::before {
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    background: var(--gradient-primary);
    opacity: 0;
    transition: all 0.6s ease;
    border-radius: 25px;
    z-index: -1;
}

.rule-card:hover::before {
    opacity: 0.03;
}

.rule-card:hover {
    transform: translateY(-10px) scale(1.02);
    box-shadow: 
        0 25px 60px rgba(0, 0, 0, 0.4),
        0 0 0 1px rgba(201, 169, 97, 0.3),
        var(--shadow-gold);
    border-color: rgba(201, 169, 97, 0.4);
}

.rule-number {
    position: absolute;
    top: -15px;
    right: 20px;
    background: var(--gradient-primary);
    color: var(--night-black);
    width: 40px;
    height: 40px;
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    font-family: 'Cinzel', serif;
    font-weight: 700;
    font-size: 1.2rem;
    box-shadow: 
        0 5px 15px rgba(201, 169, 97, 0.3),
        inset 0 1px 0 rgba(255, 255, 255, 0.2);
}

.rule-card h3 {
    font-family: 'Playfair Display', serif;
    font-size: 1.8rem;
    color: var(--primary-gold);
    margin: 1.5rem 0 1rem;
    font-weight: 700;
    letter-spacing: 1px;
}

.rule-card p {
    font-size: 1.1rem;
    line-height: 1.7;
    color: rgba(255, 255, 255, 0.9);
    font-family: 'Playfair Display', serif;
    margin-bottom: 1.5rem;
    font-weight: 400;
}

.rule-quote {
    font-family: 'Playfair Display', serif;
    font-size: 1rem;
    color: var(--primary-gold);
    font-style: italic;
    font-weight: 500;
    padding: 1rem;
    background: rgba(201, 169, 97, 0.1);
    border-radius: 15px;
    border-left: 3px solid var(--primary-gold);
}

/* Premium Prizes Section */
.prizes {
    padding: 150px 0;
    background: 
        linear-gradient(135deg, 
            rgba(139, 0, 0, 0.15) 0%, 
            rgba(11, 11, 11, 0.8) 25%, 
            rgba(201, 169, 97, 0.1) 50%, 
            rgba(11, 11, 11, 0.8) 75%, 
            rgba(139, 0, 0, 0.15) 100%),
        radial-gradient(ellipse at 25% 75%, rgba(201, 169, 97, 0.1) 0%, transparent 50%),
        radial-gradient(ellipse at 75% 25%, rgba(139, 0, 0, 0.1) 0%, transparent 50%);
    position: relative;
    overflow: hidden;
}

.prizes::before {
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    background: 
        repeating-linear-gradient(
            45deg,
            transparent,
            transparent 50px,
            rgba(201, 169, 97, 0.02) 50px,
            rgba(201, 169, 97, 0.02) 100px
        );
    animation: prizePattern 20s linear infinite;
}

@keyframes prizePattern {
    0% { transform: translateX(-100px); }
    100% { transform: translateX(100px); }
}

.prizes-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(380px, 1fr));
    gap: 4rem;
    margin-top: 4rem;
    position: relative;
    z-index: 2;
}

.prize-card {
    background: linear-gradient(135deg, 
        rgba(11, 11, 11, 0.95) 0%, 
        rgba(26, 26, 26, 0.98) 50%, 
        rgba(11, 11, 11, 0.95) 100%);
    backdrop-filter: blur(25px) saturate(200%);
    border-radius: 30px;
    padding: 3.5rem 3rem;
    position: relative;
    overflow: hidden;
    transition: all 0.7s cubic-bezier(0.4, 0, 0.2, 1);
    border: 2px solid transparent;
    box-shadow: var(--shadow-dark);
    text-align: center;
}

.prize-card::before {
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    border-radius: 30px;
    padding: 2px;
    background: var(--gradient-primary);
    mask: linear-gradient(#fff 0 0) content-box, linear-gradient(#fff 0 0);
    mask-composite: exclude;
    opacity: 0.6;
    transition: opacity 0.6s ease;
}

.prize-card:hover::before {
    opacity: 1;
}

.prize-card:hover {
    transform: translateY(-15px) scale(1.03);
    box-shadow: 
        0 35px 80px rgba(0, 0, 0, 0.5),
        var(--shadow-gold);
}

.prize-card.gold {
    border-image: linear-gradient(45deg, var(--accent-gold), #FFFFFF, var(--accent-gold)) 1;
}

.prize-card.gold:hover {
    box-shadow: 
        0 35px 80px rgba(0, 0, 0, 0.5),
        0 0 50px rgba(255, 215, 0, 0.4);
}

.prize-card.silver {
    border-image: linear-gradient(45deg, #C0C0C0, #E5E5E5, #C0C0C0) 1;
}

.prize-card.silver:hover {
    box-shadow: 
        0 35px 80px rgba(0, 0, 0, 0.5),
        0 0 50px rgba(192, 192, 192, 0.3);
}

.prize-card.bronze {
    border-image: linear-gradient(45deg, #CD7F32, #D2691E, #CD7F32) 1;
}

.prize-card.bronze:hover {
    box-shadow: 
        0 35px 80px rgba(0, 0, 0, 0.5),
        0 0 50px rgba(205, 127, 50, 0.3);
}

.house-banner-small {
    background: var(--gradient-primary);
    color: var(--night-black);
    padding: 0.8rem 1.5rem;
    border-radius: 20px;
    font-family: 'Cinzel', serif;
    font-weight: 700;
    font-size: 0.9rem;
    letter-spacing: 1px;
    margin-bottom: 2rem;
    display: inline-block;
    box-shadow: 
        0 5px 15px rgba(201, 169, 97, 0.3),
        inset 0 1px 0 rgba(255, 255, 255, 0.2);
}

.prize-crown {
    margin: 2rem 0;
    display: flex;
    justify-content: center;
    align-items: center;
    height: 120px;
}

.prize-card h3 {
    font-family: 'Game of Thrones', 'Playfair Display', serif;
    font-size: 2.2rem;
    color: var(--primary-gold);
    margin-bottom: 1rem;
    font-weight: 700;
    letter-spacing: 1px;
    text-transform: uppercase;
}

.prize-amount {
    font-family: 'Playfair Display', serif;
    font-size: 3rem;
    font-weight: 800;
    background: var(--gradient-primary);
    background-size: 200% 200%;
    -webkit-background-clip: text;
    background-clip: text;
    -webkit-text-fill-color: transparent;
    animation: prizeShimmer 4s ease-in-out infinite;
    margin-bottom: 1rem;
}

@keyframes prizeShimmer {
    0%, 100% { background-position: 0% 50%; }
    50% { background-position: 100% 50%; }
}

.throne-quote {
    font-family: 'Playfair Display', serif;
    font-size: 1.1rem;
    color: rgba(255, 255, 255, 0.8);
    font-style: italic;
    margin-bottom: 2rem;
    font-weight: 500;
}

.prize-benefits {
    list-style: none;
    padding: 0;
    margin: 0;
}

.prize-benefits li {
    padding: 0.8rem 0;
    border-bottom: 1px solid rgba(201, 169, 97, 0.2);
    font-family: 'Playfair Display', serif;
    font-size: 1.1rem;
    color: rgba(255, 255, 255, 0.9);
    position: relative;
    padding-left: 2rem;
}

.prize-benefits li::before {
    content: '♦';
    position: absolute;
    left: 0;
    color: var(--primary-gold);
    font-size: 1.2rem;
}

.prize-benefits li:last-child {
    border-bottom: none;
}

/* About Section - Houses */
.about {
    padding: 120px 0;
    background: 
        linear-gradient(135deg, #0a0a0a 0%, #1a1a1a 50%, #0a0a0a 100%),
        radial-gradient(circle at 25% 25%, rgba(70, 130, 180, 0.1) 0%, transparent 50%),
        radial-gradient(circle at 75% 75%, rgba(220, 20, 60, 0.1) 0%, transparent 50%);
    position: relative;
}

.about::before {
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    background: url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 100 100"><defs><pattern id="grain" width="100" height="100" patternUnits="userSpaceOnUse"><circle cx="25" cy="25" r="1" fill="rgba(255,255,255,0.02)"/><circle cx="75" cy="75" r="1" fill="rgba(255,255,255,0.01)"/></pattern></defs><rect width="100" height="100" fill="url(%23grain)"/></svg>');
    opacity: 0.5;
    pointer-events: none;
}

.about-content {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(380px, 1fr));
    gap: 3rem;
    position: relative;
    z-index: 2;
}

.about-card {
    background: linear-gradient(145deg, rgba(26, 26, 26, 0.9), rgba(15, 15, 15, 0.9));
    padding: 3rem;
    border-radius: 25px;
    text-align: center;
    transition: all 0.4s ease;
    border: 2px solid rgba(212, 175, 55, 0.3);
    position: relative;
    overflow: hidden;
    backdrop-filter: blur(10px);
    box-shadow: 0 15px 35px rgba(0, 0, 0, 0.5);
}

.about-card::before {
    content: '';
    position: absolute;
    top: -2px;
    left: -2px;
    right: -2px;
    bottom: -2px;
    background: linear-gradient(45deg, transparent, rgba(212, 175, 55, 0.5), transparent);
    border-radius: 25px;
    z-index: -1;
    opacity: 0;
    transition: opacity 0.4s ease;
}

.about-card:hover::before {
    opacity: 1;
}

.about-card:hover {
    transform: translateY(-15px) scale(1.02);
    box-shadow: 0 25px 50px rgba(212, 175, 55, 0.3);
}

.house-stark {
    border-color: #4682B4;
    background: linear-gradient(145deg, rgba(26, 26, 46, 0.9), rgba(22, 33, 62, 0.9));
}

.house-stark::before {
    background: linear-gradient(45deg, transparent, rgba(70, 130, 180, 0.5), transparent);
}

.house-targaryen {
    border-color: #DC143C;
    background: linear-gradient(145deg, rgba(45, 20, 20, 0.9), rgba(26, 14, 14, 0.9));
}

.house-targaryen::before {
    background: linear-gradient(45deg, transparent, rgba(220, 20, 60, 0.5), transparent);
}

.house-lannister {
    border-color: #FFD700;
    background: linear-gradient(145deg, rgba(45, 36, 20, 0.9), rgba(26, 26, 14, 0.9));
}

.house-lannister::before {
    background: linear-gradient(45deg, transparent, rgba(255, 215, 0, 0.5), transparent);
}

.about-card .house-sigil {
    font-size: 2rem;
    margin-top: 5px;
    animation: dragonBreath 4s ease-in-out infinite;
    filter: drop-shadow(0 0 10px #d4af37);
}

/* 3D GOT Elements */
.dragon-3d {
    width: 40px;
    height: 30px;
    position: relative;
    margin-top: 10px;
}

.dragon-3d::before {
    content: '';
    position: absolute;
    width: 100%;
    height: 100%;
    background: linear-gradient(135deg, #d4af37, #ffd700, #d4af37);
    clip-path: polygon(0% 50%, 25% 0%, 50% 30%, 75% 0%, 100% 50%, 75% 100%, 50% 70%, 25% 100%);
    animation: dragonWings 3s ease-in-out infinite;
    filter: drop-shadow(0 0 8px #d4af37);
}

@keyframes dragonWings {
    0%, 100% { transform: scale(1) rotate(0deg); }
    50% { transform: scale(1.1) rotate(2deg); }
}

.nav-icon {
    display: inline-block;
    width: 16px;
    height: 16px;
    margin-right: 8px;
    position: relative;
}

.castle-icon::before {
    content: '';
    position: absolute;
    width: 100%;
    height: 100%;
    background: linear-gradient(45deg, #d4af37, #ffd700);
    clip-path: polygon(0% 100%, 20% 60%, 35% 100%, 50% 40%, 65% 100%, 80% 60%, 100% 100%);
}

.sword-icon::before {
    content: '';
    position: absolute;
    width: 2px;
    height: 14px;
    background: linear-gradient(180deg, #d4af37, #8B7355);
    left: 50%;
    transform: translateX(-50%);
}

.sword-icon::after {
    content: '';
    position: absolute;
    width: 8px;
    height: 3px;
    background: #8B7355;
    left: 50%;
    top: 12px;
    transform: translateX(-50%);
}

.scroll-icon::before {
    content: '';
    position: absolute;
    width: 12px;
    height: 14px;
    background: linear-gradient(180deg, #D2B48C, #8B7355);
    border-radius: 2px;
    left: 50%;
    transform: translateX(-50%);
}

.crown-icon::before {
    content: '';
    position: absolute;
    width: 14px;
    height: 8px;
    background: linear-gradient(45deg, #FFD700, #d4af37);
    clip-path: polygon(0% 100%, 20% 30%, 40% 100%, 50% 20%, 60% 100%, 80% 30%, 100% 100%);
    left: 50%;
    transform: translateX(-50%);
}

.clock-icon::before {
    content: '';
    position: absolute;
    width: 14px;
    height: 14px;
    border: 2px solid #d4af37;
    border-radius: 50%;
    left: 50%;
    transform: translateX(-50%);
}

.clock-icon::after {
    content: '';
    position: absolute;
    width: 1px;
    height: 5px;
    background: #d4af37;
    left: 50%;
    top: 2px;
    transform: translateX(-50%);
}

.shield-icon::before {
    content: '';
    position: absolute;
    width: 12px;
    height: 14px;
    background: linear-gradient(45deg, #C0C0C0, #8B8B8B);
    clip-path: polygon(50% 0%, 100% 38%, 82% 100%, 18% 100%, 0% 38%);
    left: 50%;
    transform: translateX(-50%);
}

.about-card .card-icon {
    font-size: 3.5rem;
    color: #d4af37;
    margin-bottom: 1.5rem;
    filter: drop-shadow(0 0 10px #d4af37);
}

.about-card h3 {
    font-family: 'Game of Thrones', 'Cinzel', serif;
    font-size: 1.8rem;
    margin-bottom: 0.8rem;
    color: #d4af37;
    text-shadow: 0 2px 4px rgba(0, 0, 0, 0.8);
}

.house-motto {
    font-family: 'Cinzel', serif;
    font-size: 1.1rem;
    color: #d4af37;
    font-style: italic;
    margin-bottom: 1.5rem;
    border-bottom: 1px solid rgba(212, 175, 55, 0.3);
    padding-bottom: 1rem;
    text-shadow: 0 1px 2px rgba(0, 0, 0, 0.8);
}

.about-card p {
    color: #ccc;
    line-height: 1.8;
    font-size: 1.1rem;
    text-shadow: 0 1px 2px rgba(0, 0, 0, 0.8);
}

/* Rules Section */
.rules {
    padding: 100px 0;
    background: linear-gradient(135deg, #0a0a0a 0%, #2d1414 50%, #0a0a0a 100%);
}

.rules-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
    gap: 2rem;
}

.rule-card {
    background: linear-gradient(145deg, #1a1a1a, #0f0f0f);
    padding: 2.5rem;
    border-radius: 20px;
    text-align: center;
    transition: all 0.3s ease;
    border: 2px solid rgba(212, 175, 55, 0.3);
    position: relative;
    overflow: hidden;
}

.rule-card::before {
    content: '';
    position: absolute;
    top: -2px;
    left: -2px;
    right: -2px;
    bottom: -2px;
    background: linear-gradient(45deg, #d4af37, transparent, #d4af37);
    border-radius: 20px;
    z-index: -1;
    opacity: 0;
    transition: opacity 0.3s ease;
}

.rule-card:hover::before {
    opacity: 1;
}

.rule-card:hover {
    transform: translateY(-10px) scale(1.02);
    box-shadow: 0 20px 40px rgba(212, 175, 55, 0.3);
}

.rule-number {
    font-family: 'Game of Thrones', 'Cinzel', serif;
    font-size: 4rem;
    font-weight: 700;
    color: #d4af37;
    margin-bottom: 1rem;
    text-shadow: 0 0 20px rgba(212, 175, 55, 0.5);
}

.rule-scroll {
    font-size: 2rem;
    margin-bottom: 1rem;
    animation: float 3s ease-in-out infinite;
}

.rule-card h3 {
    font-family: 'Game of Thrones', 'Cinzel', serif;
    font-size: 1.4rem;
    margin-bottom: 1rem;
    color: #fff;
}

.rule-card p {
    color: #ccc;
    line-height: 1.6;
    margin-bottom: 1rem;
}

.rule-quote {
    font-family: 'Cinzel', serif;
    font-style: italic;
    color: #d4af37;
    font-size: 0.9rem;
    border-top: 1px solid rgba(212, 175, 55, 0.3);
    padding-top: 1rem;
}

/* Prizes Section */
.prizes {
    padding: 100px 0;
    background: linear-gradient(135deg, #1a1a1a 0%, #0a0a0a 100%);
}

.prizes-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
    gap: 2rem;
    align-items: start;
}

.prize-card {
    background: linear-gradient(145deg, #1a1a1a, #0f0f0f);
    padding: 2.5rem;
    border-radius: 25px;
    text-align: center;
    transition: all 0.3s ease;
    position: relative;
    overflow: hidden;
}

.house-banner-small {
    background: linear-gradient(135deg, #8B0000, #000000);
    color: #d4af37;
    padding: 0.5rem 1rem;
    border-radius: 20px;
    font-family: 'Game of Thrones', 'Cinzel', serif;
    font-size: 0.8rem;
    margin-bottom: 1rem;
    border: 1px solid #d4af37;
    letter-spacing: 1px;
}

.prize-card.gold {
    border: 3px solid #ffd700;
    transform: scale(1.05);
    background: linear-gradient(145deg, #2a2a1a, #1a1a0f);
}

.prize-card.silver {
    border: 3px solid #c0c0c0;
    background: linear-gradient(145deg, #2a2a2a, #1a1a1a);
}

.prize-card.bronze {
    border: 3px solid #cd7f32;
    background: linear-gradient(145deg, #2a1a1a, #1a0f0f);
}

.prize-card:hover {
    transform: translateY(-15px) scale(1.03);
    box-shadow: 0 30px 60px rgba(212, 175, 55, 0.4);
}

.prize-card.gold:hover {
    transform: translateY(-15px) scale(1.08);
    box-shadow: 0 30px 60px rgba(255, 215, 0, 0.5);
}

.prize-crown {
    font-size: 5rem;
    margin-bottom: 1rem;
}

.prize-card.gold .prize-crown {
    color: #ffd700;
    animation: crownGlow 2s ease-in-out infinite;
}

@keyframes crownGlow {
    0%, 100% { text-shadow: 0 0 20px rgba(255, 215, 0, 0.5); }
    50% { text-shadow: 0 0 30px rgba(255, 215, 0, 0.8); }
}

.prize-card.silver .prize-crown {
    color: #c0c0c0;
}

.prize-card.bronze .prize-crown {
    color: #cd7f32;
}

.prize-card h3 {
    font-family: 'Game of Thrones', 'Cinzel', serif;
    font-size: 1.8rem;
    margin-bottom: 1rem;
    color: #d4af37;
}

.prize-amount {
    font-family: 'Game of Thrones', 'Cinzel', serif;
    font-size: 3rem;
    font-weight: 700;
    color: #fff;
    margin-bottom: 1rem;
    text-shadow: 0 0 15px rgba(212, 175, 55, 0.5);
}

.throne-quote {
    font-family: 'Cinzel', serif;
    font-style: italic;
    color: #999;
    margin-bottom: 2rem;
    font-size: 1rem;
    border-bottom: 1px solid rgba(212, 175, 55, 0.3);
    padding-bottom: 1rem;
}

.prize-benefits {
    list-style: none;
    color: #ccc;
}

.prize-benefits li {
    padding: 0.7rem 0;
    position: relative;
    font-size: 1.1rem;
    border-bottom: 1px solid rgba(255, 255, 255, 0.1);
}

.prize-benefits li:last-child {
    border-bottom: none;
}

/* Schedule Section */
.schedule {
    padding: 100px 0;
    background: #0a0a0a;
}

.timeline {
    position: relative;
    max-width: 800px;
    margin: 0 auto;
}

.timeline::before {
    content: '';
    position: absolute;
    left: 50%;
    top: 0;
    bottom: 0;
    width: 2px;
    background: #d4af37;
    transform: translateX(-50%);
}

.timeline-item {
    position: relative;
    margin-bottom: 3rem;
    display: flex;
    align-items: center;
}

.timeline-item:nth-child(odd) {
    flex-direction: row-reverse;
}

.timeline-item:nth-child(odd) .timeline-content {
    text-align: right;
    margin-right: 2rem;
}

.timeline-item:nth-child(even) .timeline-content {
    margin-left: 2rem;
}

.timeline-date {
    background: #d4af37;
    color: #000;
    padding: 1rem;
    border-radius: 50%;
    font-weight: 700;
    font-family: 'Cinzel', serif;
    min-width: 80px;
    text-align: center;
    position: relative;
    z-index: 2;
}

.timeline-content {
    background: linear-gradient(145deg, #1a1a1a, #0f0f0f);
    padding: 2rem;
    border-radius: 15px;
    border: 1px solid rgba(212, 175, 55, 0.1);
    flex: 1;
    max-width: 350px;
}

.timeline-content h3 {
    font-family: 'Cinzel', serif;
    color: #d4af37;
    margin-bottom: 0.5rem;
}

.timeline-content p {
    color: #ccc;
    margin-bottom: 0.5rem;
}

.time {
    color: #999;
    font-size: 0.9rem;
    font-weight: 600;
}

/* Register Section */
.register {
    padding: 100px 0;
    background: linear-gradient(135deg, #1a1a1a 0%, #0a0a0a 100%);
}

.register-content {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 4rem;
    align-items: start;
}

.register-info h3 {
    font-family: 'Cinzel', serif;
    font-size: 2rem;
    color: #d4af37;
    margin-bottom: 2rem;
}

.info-item {
    display: flex;
    align-items: center;
    gap: 1rem;
    margin-bottom: 2rem;
    padding: 1rem;
    background: linear-gradient(145deg, #1a1a1a, #0f0f0f);
    border-radius: 10px;
    border: 1px solid rgba(212, 175, 55, 0.1);
}

.info-item i {
    font-size: 2rem;
    color: #d4af37;
    min-width: 40px;
}

.info-item h4 {
    color: #d4af37;
    margin-bottom: 0.5rem;
    font-family: 'Cinzel', serif;
}

.info-item p {
    color: #ccc;
}

.register-form {
    background: linear-gradient(145deg, #1a1a1a, #0f0f0f);
    padding: 2rem;
    border-radius: 20px;
    border: 1px solid rgba(212, 175, 55, 0.1);
}

.register-form h3 {
    font-family: 'Cinzel', serif;
    font-size: 1.8rem;
    color: #d4af37;
    margin-bottom: 2rem;
    text-align: center;
}

.form-group {
    margin-bottom: 1.5rem;
}

.form-group input,
.form-group select,
.form-group textarea {
    width: 100%;
    padding: 1rem;
    background: rgba(0, 0, 0, 0.5);
    border: 1px solid rgba(212, 175, 55, 0.3);
    border-radius: 8px;
    color: #fff;
    font-family: 'Crimson Text', serif;
    font-size: 1rem;
    transition: all 0.3s ease;
}

.form-group input:focus,
.form-group select:focus,
.form-group textarea:focus {
    outline: none;
    border-color: #d4af37;
    box-shadow: 0 0 10px rgba(212, 175, 55, 0.3);
}

.form-group input::placeholder,
.form-group textarea::placeholder {
    color: #999;
}

/* Footer */
.footer {
    background: #000;
    padding: 3rem 0 1rem;
    border-top: 1px solid rgba(212, 175, 55, 0.3);
}

.footer-content {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    gap: 2rem;
    margin-bottom: 2rem;
}

.footer-section h3,
.footer-section h4 {
    font-family: 'Cinzel', serif;
    color: #d4af37;
    margin-bottom: 1rem;
}

.footer-section p,
.footer-section li {
    color: #ccc;
    margin-bottom: 0.5rem;
}

.footer-section ul {
    list-style: none;
}

.footer-section a {
    color: #ccc;
    text-decoration: none;
    transition: color 0.3s ease;
}

.footer-section a:hover {
    color: #d4af37;
}

.social-links {
    display: flex;
    gap: 1rem;
    margin-top: 1rem;
}

.social-links a {
    display: flex;
    align-items: center;
    justify-content: center;
    width: 40px;
    height: 40px;
    background: rgba(212, 175, 55, 0.1);
    border-radius: 50%;
    color: #d4af37;
    transition: all 0.3s ease;
}

.social-links a:hover {
    background: #d4af37;
    color: #000;
    transform: translateY(-2px);
}

.footer-bottom {
    text-align: center;
    padding-top: 2rem;
    border-top: 1px solid rgba(212, 175, 55, 0.1);
    color: #999;
}

/* Responsive Design */
@media (max-width: 768px) {
    .hamburger {
        display: flex;
    }
    
    .nav-menu {
        position: fixed;
        left: -100%;
        top: 70px;
        flex-direction: column;
        background-color: rgba(0, 0, 0, 0.95);
        width: 100%;
        text-align: center;
        transition: 0.3s;
        backdrop-filter: blur(10px);
        padding: 2rem 0;
    }
    
    .nav-menu.active {
        left: 0;
    }
    
    .hero-title {
        font-size: 3rem;
    }
    
    .hero-subtitle {
        font-size: 1.5rem;
    }
    
    .hero-buttons {
        flex-direction: column;
        align-items: center;
    }
    
    .section-header h2 {
        font-size: 2rem;
    }
    
    .register-content {
        grid-template-columns: 1fr;
        gap: 2rem;
    }
    
    .timeline::before {
        left: 30px;
    }
    
    .timeline-item {
        flex-direction: column;
        align-items: flex-start;
        padding-left: 70px;
    }
    
    .timeline-item:nth-child(odd) {
        flex-direction: column;
    }
    
    .timeline-item:nth-child(odd) .timeline-content,
    .timeline-item:nth-child(even) .timeline-content {
        text-align: left;
        margin: 0;
        margin-top: 1rem;
    }
    
    .timeline-date {
        position: absolute;
        left: 0;
        min-width: 60px;
        font-size: 0.8rem;
        padding: 0.8rem;
    }
    
    .prizes-grid {
        grid-template-columns: 1fr;
    }
    
    .prize-card.gold {
        transform: none;
        order: -1;
    }
}

@media (max-width: 480px) {
    .hero-title {
        font-size: 2.5rem;
    }
    
    .container {
        padding: 0 15px;
    }
    
    .about-content {
        grid-template-columns: 1fr;
    }
    
    .rules-grid {
        grid-template-columns: 1fr;
    }
}

/* Custom Scrollbar */
::-webkit-scrollbar {
    width: 8px;
}

::-webkit-scrollbar-track {
    background: #0a0a0a;
}

::-webkit-scrollbar-thumb {
    background: #d4af37;
    border-radius: 4px;
}

::-webkit-scrollbar-thumb:hover {
    background: #ffd700;
}
