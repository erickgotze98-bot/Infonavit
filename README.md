
<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Vive Alto Génova – NuestroHogar</title>
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,700;0,900;1,700&family=Barlow:wght@300;400;500;600;700&display=swap" rel="stylesheet">
<style>
:root{
  --black:#0a0a0a; --dark:#111111; --mid:#222222;
  --gray:#888; --light:#f5f5f5; --white:#fff;
  --blue:#1a7abf; --gold:#d4a843;
  --font-serif:"Playfair Display",serif;
  --font-sans:Barlow,sans-serif;
}
*,*::before,*::after{margin:0;padding:0;box-sizing:border-box;}
html{scroll-behavior:smooth;}
body{font-family:var(--font-sans);color:var(--black);background:var(--white);overflow-x:hidden;}
img{display:block;max-width:100%;}
a{text-decoration:none;color:inherit;}

/* ── NAVBAR ── */
.nav{
  position:fixed;top:0;left:0;right:0;z-index:1000;
  display:flex;justify-content:space-between;align-items:center;
  padding:0 clamp(16px,5vw,60px);height:68px;
  background:rgba(10,10,10,.95);backdrop-filter:blur(12px);
  border-bottom:1px solid rgba(255,255,255,.06);
  transition:all .3s;
}
.nav.scrolled{height:58px;background:rgba(10,10,10,.98);}
.nav-logo{display:flex;flex-direction:column;line-height:1;}
.nav-logo .nl{color:var(--white);font-family:var(--font-serif);font-size:18px;font-weight:900;}
.nav-logo .nl span{color:var(--gold);}
.nav-logo .ns{color:rgba(255,255,255,.35);font-size:9px;letter-spacing:3px;text-transform:uppercase;margin-top:2px;}
.nav-links{display:flex;gap:28px;align-items:center;}
.nav-links a{color:rgba(255,255,255,.65);font-size:13px;font-weight:500;letter-spacing:.5px;transition:color .2s;}
.nav-links a:hover{color:var(--white);}
.nav-wa{background:var(--blue);color:var(--white)!important;padding:8px 18px;border-radius:20px;font-size:12px!important;font-weight:600!important;letter-spacing:.5px;transition:background .2s!important;}
.nav-wa:hover{background:#1565a0!important;}
.hamburger{display:none;flex-direction:column;gap:5px;cursor:pointer;padding:4px;}
.hamburger span{width:24px;height:2px;background:var(--white);border-radius:2px;transition:all .3s;}
@media(max-width:760px){
  .nav-links{display:none;position:fixed;top:68px;left:0;right:0;background:var(--dark);flex-direction:column;padding:24px;gap:20px;border-bottom:1px solid #222;}
  .nav-links.open{display:flex;}
  .hamburger{display:flex;}
}

/* ── HERO ── */
.hero{
  height:100vh;min-height:600px;position:relative;
  display:flex;align-items:center;justify-content:center;
  overflow:hidden;
}
.hero-bg{position:absolute;inset:0;background:var(--black);}
.hero-img{position:absolute;inset:0;width:100%;height:100%;object-fit:cover;opacity:.45;transition:opacity 1s;}
.hero-overlay{position:absolute;inset:0;background:linear-gradient(135deg,rgba(10,10,10,.85) 40%,rgba(10,10,10,.4));}
.hero-content{position:relative;z-index:2;text-align:center;padding:0 20px;max-width:780px;}
.hero-badge{display:inline-block;border:1px solid rgba(212,168,67,.5);color:var(--gold);font-size:10px;letter-spacing:4px;text-transform:uppercase;padding:6px 18px;border-radius:2px;margin-bottom:24px;}
.hero-title{font-family:var(--font-serif);color:var(--white);font-size:clamp(42px,8vw,82px);font-weight:900;line-height:1;margin-bottom:16px;}
.hero-title span{color:var(--gold);font-style:italic;}
.hero-sub{color:rgba(255,255,255,.55);font-size:clamp(14px,2vw,17px);font-weight:300;letter-spacing:1px;margin-bottom:40px;line-height:1.7;}
.hero-ctas{display:flex;gap:14px;justify-content:center;flex-wrap:wrap;}
.btn-primary{background:var(--blue);color:var(--white);padding:14px 32px;border-radius:2px;font-size:13px;font-weight:600;letter-spacing:1px;text-transform:uppercase;transition:all .25s;border:none;cursor:pointer;}
.btn-primary:hover{background:#1565a0;transform:translateY(-2px);}
.btn-outline{border:1px solid rgba(255,255,255,.4);color:var(--white);padding:14px 32px;border-radius:2px;font-size:13px;font-weight:600;letter-spacing:1px;text-transform:uppercase;transition:all .25s;}
.btn-outline:hover{border-color:var(--white);background:rgba(255,255,255,.08);}
.hero-scroll{position:absolute;bottom:30px;left:50%;transform:translateX(-50%);display:flex;flex-direction:column;align-items:center;gap:8px;color:rgba(255,255,255,.35);font-size:10px;letter-spacing:2px;text-transform:uppercase;}
.hero-scroll-line{width:1px;height:40px;background:linear-gradient(to bottom,rgba(255,255,255,.4),transparent);animation:scrollline 2s ease-in-out infinite;}
@keyframes scrollline{0%,100%{opacity:.3;transform:scaleY(.5);}50%{opacity:1;transform:scaleY(1);}}

/* ── SECTIONS GENERAL ── */
section{padding:clamp(60px,10vw,100px) clamp(16px,6vw,80px);}
.section-label{font-size:10px;letter-spacing:4px;text-transform:uppercase;color:var(--blue);font-weight:600;margin-bottom:12px;}
.section-title{font-family:var(--font-serif);font-size:clamp(28px,5vw,48px);font-weight:900;line-height:1.1;margin-bottom:20px;}
.section-sub{color:var(--gray);font-size:15px;line-height:1.7;max-width:560px;}
.divider{width:48px;height:3px;background:var(--gold);margin:20px 0;}

/* ── MODELOS ── */
.modelos{background:var(--light);}
.modelos-header{text-align:center;margin-bottom:50px;}
.modelos-header .section-sub{margin:0 auto;}
.modelos-grid{display:grid;gap:24px;}
@media(min-width:700px){.modelos-grid{grid-template-columns:1fr 1fr;}}
@media(min-width:1100px){.modelos-grid{grid-template-columns:1fr 1fr 1fr;}}
.modelo-card{background:var(--white);overflow:hidden;box-shadow:0 4px 30px rgba(0,0,0,.08);transition:transform .3s,box-shadow .3s;}
.modelo-card:hover{transform:translateY(-6px);box-shadow:0 12px 40px rgba(0,0,0,.14);}
.modelo-img{height:220px;overflow:hidden;}
.modelo-img img{width:100%;height:100%;object-fit:cover;transition:transform .5s;}
.modelo-card:hover .modelo-img img{transform:scale(1.06);}
.modelo-body{padding:28px;}
.modelo-tag{font-size:9px;letter-spacing:3px;text-transform:uppercase;color:var(--blue);font-weight:700;margin-bottom:8px;}
.modelo-name{font-family:var(--font-serif);font-size:28px;font-weight:900;margin-bottom:4px;}
.modelo-m2{font-size:13px;color:var(--gray);margin-bottom:16px;}
.modelo-features{display:flex;flex-direction:column;gap:8px;margin-bottom:20px;}
.modelo-feat{display:flex;align-items:center;gap:8px;font-size:13px;color:#333;}
.modelo-feat::before{content:"";width:6px;height:6px;background:var(--gold);border-radius:50%;flex-shrink:0;}
.modelo-cta{display:inline-block;background:var(--black);color:var(--white);padding:10px 22px;font-size:12px;font-weight:600;letter-spacing:1px;text-transform:uppercase;transition:background .2s;}
.modelo-cta:hover{background:var(--blue);}
.modelo-highlight{border-top:3px solid var(--gold);}

/* ── GALERÍA ── */
.galeria-header{text-align:center;margin-bottom:40px;}
.galeria-grid{display:grid;gap:4px;}
@media(min-width:500px){.galeria-grid{grid-template-columns:repeat(2,1fr);}}
@media(min-width:800px){.galeria-grid{grid-template-columns:repeat(4,1fr);}}
.gal-item{aspect-ratio:1;overflow:hidden;cursor:pointer;position:relative;}
.gal-item.featured{grid-column:span 2;grid-row:span 2;aspect-ratio:auto;}
.gal-item img{width:100%;height:100%;object-fit:cover;transition:transform .4s;}
.gal-item:hover img{transform:scale(1.07);}
.gal-overlay{position:absolute;inset:0;background:rgba(10,10,10,0);display:flex;align-items:center;justify-content:center;transition:background .3s;}
.gal-item:hover .gal-overlay{background:rgba(10,10,10,.35);}
.gal-icon{color:var(--white);font-size:28px;opacity:0;transition:opacity .3s;}
.gal-item:hover .gal-icon{opacity:1;}

/* ── LIGHTBOX ── */
.lightbox{position:fixed;inset:0;z-index:9999;background:rgba(0,0,0,.95);display:none;align-items:center;justify-content:center;flex-direction:column;}
.lightbox.open{display:flex;}
.lb-img{max-width:90vw;max-height:80vh;object-fit:contain;border:1px solid rgba(255,255,255,.1);}
.lb-label{color:rgba(255,255,255,.55);font-size:12px;letter-spacing:2px;margin-top:14px;text-transform:uppercase;}
.lb-close{position:absolute;top:20px;right:24px;color:var(--white);font-size:28px;cursor:pointer;opacity:.7;transition:opacity .2s;background:none;border:none;line-height:1;}
.lb-close:hover{opacity:1;}
.lb-nav{position:absolute;top:50%;transform:translateY(-50%);width:100%;display:flex;justify-content:space-between;padding:0 16px;pointer-events:none;}
.lb-btn{pointer-events:all;background:rgba(255,255,255,.1);border:1px solid rgba(255,255,255,.15);color:var(--white);width:44px;height:44px;border-radius:50%;font-size:18px;cursor:pointer;transition:background .2s;display:flex;align-items:center;justify-content:center;}
.lb-btn:hover{background:rgba(255,255,255,.25);}

/* ── AMENIDADES ── */
.amenidades{background:var(--dark);}
.amenidades .section-label{color:var(--gold);}
.amenidades .section-title{color:var(--white);}
.amenidades .section-sub{color:rgba(255,255,255,.45);}
.amen-grid{display:grid;gap:16px;margin-top:40px;}
@media(min-width:500px){.amen-grid{grid-template-columns:repeat(2,1fr);}}
@media(min-width:800px){.amen-grid{grid-template-columns:repeat(4,1fr);}}
.amen-card{background:rgba(255,255,255,.04);border:1px solid rgba(255,255,255,.07);padding:24px 20px;text-align:center;transition:all .3s;}
.amen-card:hover{background:rgba(255,255,255,.08);border-color:rgba(212,168,67,.3);transform:translateY(-4px);}
.amen-icon{font-size:32px;margin-bottom:12px;}
.amen-name{color:var(--white);font-size:13px;font-weight:600;margin-bottom:4px;}
.amen-desc{color:rgba(255,255,255,.38);font-size:11px;line-height:1.5;}

/* ── VIDEO ── */
.video-section{background:var(--black);text-align:center;padding:80px 20px;position:relative;overflow:hidden;}
.video-section::before{content:"";position:absolute;inset:0;background:radial-gradient(ellipse at center,rgba(26,122,191,.12) 0%,transparent 70%);}
.video-placeholder{position:relative;max-width:800px;margin:40px auto 0;aspect-ratio:16/9;background:rgba(255,255,255,.04);border:1px solid rgba(255,255,255,.08);display:flex;align-items:center;justify-content:center;flex-direction:column;gap:16px;}
.play-btn{width:72px;height:72px;background:rgba(26,122,191,.7);border-radius:50%;display:flex;align-items:center;justify-content:center;font-size:28px;color:var(--white);animation:pulse 2s ease-in-out infinite;}
@keyframes pulse{0%,100%{box-shadow:0 0 0 0 rgba(26,122,191,.4);}70%{box-shadow:0 0 0 20px rgba(26,122,191,0);}}
.video-coming{color:rgba(255,255,255,.35);font-size:12px;letter-spacing:3px;text-transform:uppercase;}
.video-section .section-label{color:var(--gold);}
.video-section .section-title{color:var(--white);}

/* ── MAPA ── */
.mapa-section{padding:0;}
.mapa-header{padding:clamp(50px,8vw,80px) clamp(16px,6vw,80px) 0;margin-bottom:30px;}
.mapa-frame{width:100%;height:420px;border:none;filter:grayscale(30%);}
.mapa-info{padding:clamp(30px,5vw,50px) clamp(16px,6vw,80px);background:var(--light);display:flex;flex-wrap:wrap;gap:30px;}
.mapa-info-item{display:flex;align-items:flex-start;gap:12px;}
.mi-icon{font-size:20px;margin-top:2px;}
.mi-label{font-size:10px;letter-spacing:2px;text-transform:uppercase;color:var(--blue);font-weight:600;margin-bottom:2px;}
.mi-val{font-size:14px;color:var(--dark);font-weight:500;line-height:1.5;}

/* ── CALCULADORA ── */
.calc-section{background:var(--light);}
.calc-wrapper{display:grid;gap:40px;margin-top:40px;}
@media(min-width:700px){.calc-wrapper{grid-template-columns:1fr 1fr;align-items:start;}}
.calc-form{background:var(--white);padding:32px;box-shadow:0 4px 24px rgba(0,0,0,.07);}
.calc-field{margin-bottom:20px;}
.calc-field label{display:block;font-size:11px;letter-spacing:2px;text-transform:uppercase;color:var(--gray);font-weight:600;margin-bottom:8px;}
.calc-field input,
.calc-field select{width:100%;padding:12px 14px;border:1px solid #e0e0e0;font-family:var(--font-sans);font-size:14px;color:var(--dark);background:var(--white);outline:none;transition:border-color .2s;border-radius:2px;}
.calc-field input:focus,
.calc-field select:focus{border-color:var(--blue);}
.calc-btn{width:100%;background:var(--black);color:var(--white);padding:14px;font-family:var(--font-sans);font-size:13px;font-weight:600;letter-spacing:2px;text-transform:uppercase;border:none;cursor:pointer;transition:background .2s;}
.calc-btn:hover{background:var(--blue);}
.calc-result{background:var(--dark);padding:32px;color:var(--white);display:none;}
.calc-result.show{display:block;}
.cr-title{font-size:11px;letter-spacing:3px;text-transform:uppercase;color:var(--gold);margin-bottom:24px;font-weight:600;}
.cr-item{margin-bottom:20px;padding-bottom:20px;border-bottom:1px solid rgba(255,255,255,.07);}
.cr-item:last-child{border-bottom:none;margin-bottom:0;}
.cr-label{font-size:11px;color:rgba(255,255,255,.4);letter-spacing:1px;text-transform:uppercase;margin-bottom:4px;}
.cr-val{font-family:var(--font-serif);font-size:28px;font-weight:700;color:var(--white);}
.cr-val span{font-size:14px;color:rgba(255,255,255,.5);font-family:var(--font-sans);font-weight:400;}
.cr-note{font-size:10px;color:rgba(255,255,255,.28);margin-top:12px;line-height:1.6;}
.calc-info{padding:28px 0;}
.ci-item{display:flex;align-items:flex-start;gap:10px;margin-bottom:16px;font-size:13px;color:#555;line-height:1.5;}
.ci-dot{width:8px;height:8px;background:var(--blue);border-radius:50%;margin-top:5px;flex-shrink:0;}

/* ── CONTACTO ── */
.contacto-section{background:var(--dark);}
.contacto-section .section-label{color:var(--gold);}
.contacto-section .section-title{color:var(--white);}
.contacto-grid{display:grid;gap:40px;margin-top:40px;}
@media(min-width:700px){.contacto-grid{grid-template-columns:1fr 1fr;}}
.contact-form{display:flex;flex-direction:column;gap:14px;}
.cf-field input,
.cf-field textarea,
.cf-field select{width:100%;padding:12px 14px;background:rgba(255,255,255,.05);border:1px solid rgba(255,255,255,.1);color:var(--white);font-family:var(--font-sans);font-size:14px;outline:none;border-radius:2px;transition:border-color .2s;}
.cf-field input::placeholder,
.cf-field textarea::placeholder{color:rgba(255,255,255,.3);}
.cf-field input:focus,
.cf-field textarea:focus,
.cf-field select:focus{border-color:var(--blue);}
.cf-field textarea{height:120px;resize:vertical;}
.cf-field select option{background:var(--dark);color:var(--white);}
.cf-submit{background:var(--blue);color:var(--white);padding:14px;border:none;font-family:var(--font-sans);font-size:13px;font-weight:600;letter-spacing:2px;text-transform:uppercase;cursor:pointer;transition:background .2s;border-radius:2px;}
.cf-submit:hover{background:#1565a0;}
.contact-info{display:flex;flex-direction:column;gap:24px;}
.ci-block .cib-label{font-size:9px;letter-spacing:3px;text-transform:uppercase;color:rgba(255,255,255,.35);margin-bottom:6px;}
.ci-block .cib-val{color:var(--white);font-size:15px;font-weight:500;line-height:1.6;}
.wa-big{display:flex;align-items:center;gap:12px;background:rgba(37,211,102,.12);border:1px solid rgba(37,211,102,.25);padding:16px 20px;border-radius:4px;margin-top:8px;cursor:pointer;transition:background .2s;}
.wa-big:hover{background:rgba(37,211,102,.2);}
.wa-big .wa-icon{font-size:28px;}
.wa-big .wa-text .wt-top{color:rgba(255,255,255,.5);font-size:10px;letter-spacing:2px;text-transform:uppercase;}
.wa-big .wa-text .wt-num{color:var(--white);font-size:18px;font-weight:700;margin-top:2px;}

/* ── FOOTER ── */
.footer{background:rgba(0,0,0,.95);border-top:1px solid rgba(255,255,255,.06);padding:clamp(30px,5vw,50px) clamp(16px,6vw,80px);}
.footer-grid{display:grid;gap:30px;margin-bottom:30px;}
@media(min-width:600px){.footer-grid{grid-template-columns:2fr 1fr 1fr;}}
.footer-logo .fl-name{font-family:var(--font-serif);color:var(--white);font-size:22px;font-weight:900;}
.footer-logo .fl-name span{color:var(--gold);}
.footer-logo .fl-sub{color:rgba(255,255,255,.28);font-size:10px;letter-spacing:3px;text-transform:uppercase;margin-top:4px;}
.footer-logo .fl-desc{color:rgba(255,255,255,.38);font-size:12px;line-height:1.7;margin-top:12px;max-width:260px;}
.footer-col h4{color:var(--white);font-size:11px;letter-spacing:2px;text-transform:uppercase;font-weight:600;margin-bottom:14px;}
.footer-col a{display:block;color:rgba(255,255,255,.38);font-size:13px;margin-bottom:8px;transition:color .2s;}
.footer-col a:hover{color:var(--white);}
.footer-bottom{border-top:1px solid rgba(255,255,255,.06);padding-top:20px;display:flex;justify-content:space-between;align-items:center;flex-wrap:wrap;gap:10px;}
.fb-copy{color:rgba(255,255,255,.25);font-size:11px;}
.fb-brand{color:rgba(255,255,255,.25);font-size:11px;letter-spacing:1px;}

/* ── WHATSAPP FAB ── */
.wa-fab{
  position:fixed;bottom:24px;right:24px;z-index:999;
  width:56px;height:56px;background:#25d366;border-radius:50%;
  display:flex;align-items:center;justify-content:center;
  font-size:26px;box-shadow:0 4px 20px rgba(37,211,102,.4);
  transition:transform .25s,box-shadow .25s;
  animation:wapulse 3s ease-in-out infinite;
}
.wa-fab:hover{transform:scale(1.1);box-shadow:0 8px 28px rgba(37,211,102,.55);}
@keyframes wapulse{0%,100%{box-shadow:0 4px 20px rgba(37,211,102,.4);}50%{box-shadow:0 4px 32px rgba(37,211,102,.65);}}

/* ── ANIMATE ON SCROLL ── */
.animate{opacity:1;transform:none;transition:opacity .7s ease,transform .7s ease;}
.js-ready .animate{opacity:0;transform:translateY(28px);}
.js-ready .animate.visible{opacity:1;transform:none;}
.animate-delay-1{transition-delay:.1s;}
.animate-delay-2{transition-delay:.2s;}
.animate-delay-3{transition-delay:.3s;}

@media(max-width:600px){
  .hero-ctas{flex-direction:column;align-items:center;}
  .btn-primary,.btn-outline{width:100%;text-align:center;}
}
</style>
</head>
<body>

<!-- NAVBAR -->
<nav class="nav" id="navbar">
  <div class="nav-logo">
    <div class="nl">Vive Alto <span>Génova</span></div>
    <div class="ns">NuestroHogar</div>
  </div>
  <div class="nav-links" id="navLinks">
    <a href="#modelos">Modelos</a>
    <a href="#galeria">Galería</a>
    <a href="#amenidades">Amenidades</a>
    <a href="#mapa">Ubicación</a>
    <a href="#calculadora">Calculadora</a>
    <a href="#contacto" class="nav-wa">📱 Contáctanos</a>
  </div>
  <div class="hamburger" id="hamburger" onclick="toggleMenu()">
    <span></span><span></span><span></span>
  </div>
</nav>

<!-- HERO -->
<section class="hero" id="inicio">
  <div class="hero-bg">
    <img class="hero-img" id="heroBg" src="data:image/jpeg;base64,/9j/4AAQSkZJRgABAQAAAQABAAD/2wBDAAgGBgcGBQgHBwcJCQgKDBUODAsLDBkSEw8VHhsgHx4bHR0hJTApISMtJB0dKjkqLTEzNjY2ICg7Pzo0PjA1NjP/2wBDAQkJCQwLDBgODhgzIh0iMzMzMzMzMzMzMzMzMzMzMzMzMzMzMzMzMzMzMzMzMzMzMzMzMzMzMzMzMzMzMzMzMzP/wAARCAKjA4QDASIAAhEBAxEB/8QAHwAAAQUBAQEBAQEAAAAAAAAAAAECAwQFBgcICQoL/8QAtRAAAgEDAwIEAwUFBAQAAAF9AQIDAAQRBRIhMUEGE1FhByJxFDKBkaEII0KxwRVS0fAkM2JyggkKFhcYGRolJicoKSo0NTY3ODk6Q0RFRkdISUpTVFVWV1hZWmNkZWZnaGlqc3R1dnd4eXqDhIWGh4iJipKTlJWWl5iZmqKjpKWmp6ipqrKztLW2t7i5usLDxMXGx8jJytLT1NXW19jZ2uHi4+Tl5ufo6erx8vP09fb3+Pn6/8QAHwEAAwEBAQEBAQEBAQAAAAAAAAECAwQFBgcICQoL/8QAtREAAgECBAQDBAcFBAQAAQJ3AAECAxEEBSExBhJBUQdhcRMiMoEIFEKRobHBCSMzUvAVYnLRChYkNOEl8RcYGRomJygpKjU2Nzg5OkNERUZHSElKU1RVVldYWVpjZGVmZ2hpanN0dXZ3eHl6goOEhYaHiImKkpOUlZaXmJmaoqOkpaanqKmqsrO0tba3uLm6wsPExcbHyMnK0tPU1dbX2Nna4uPk5ebn6Onq8vP09fb3+Pn6/9oADAMBAAIRAxEAPwCxjnn9KXGPw7UnUUoOc5rI1FJz1FJ2o/Gjq3XigAHOaUY6GgdKKAA8EGl69M0n1oHagAGM0Hpg/WkPXFL/ACoABzR3pByM0vFAAfqPcUDuKM/N680c+vSgA60emaD0FA6n2oAM0h5HvRnNGefegA7il9aaD1pelABxRmjPOabQAoo70cUE0AFJmjNJ2oADRQaTNAC0mc0ntRQA6kP0pM0maEA40hpCeOtITQA40hNNLYpCaEAuaQ0wmk3UwHZpM+tNJo/GgBaTNGaQnigA70ZpPekouA7NJSUZouAUUUd6AFzSZo60CgAooJooASigmjNABmjFJmkzQAUUhYKMnAHvUL3SDhQW/lQBN1pGIQZYgfWqj3MjDAOB7VEck5JOfrQBZe5VRhVJ9z0qB5pHGC2AewpmKMGgBM0ZNLiloAbilpQKMUAJSilxS0wExRinYoxQITbQBT6TFACcZpcClpQKAExRTqKAEGKKdRigApQOaKWgAHWlxQBzS0AJS0UtAAKUDmilA5oATHNOFLilxQAgp2KSlz3oAMUtGaSgBw4FG8U3PFGfegB+72pM+9NzSFgByaVxjsilzUe8HpShZHI2KWz6UXAdkUZz0qVLOVvvbU+pqUWaqAWJJ/Ki4FXNADMflUmr4giUjCDnuakI/ClcCiLWVjzgfU1ItmP4nz9Ktd84o6ClcCEW8S9Ix+JzTsY6AU+mnrQAZ5Ao2jpTsccUdsUgFUCjApccACigBh560P16gUp5
