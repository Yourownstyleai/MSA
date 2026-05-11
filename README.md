[index.html](https://github.com/user-attachments/files/27585431/index.html)
<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>mystyle_advice — Asesoría Personal con IA</title>
<link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,300;0,400;0,600;0,700;1,300;1,400&family=Jost:wght@300;400;500;600&display=swap" rel="stylesheet"/>
<style>
:root {
  --rose:    #c4a09a;
  --rose-lt: #e8d5d2;
  --rose-dk: #8a5e58;
  --brown:   #4a3728;
  --brown-lt:#7a6050;
  --cream:   #faf6f3;
  --cream-dk:#f0e8e3;
  --ink:     #2a1e18;
  --muted:   #9a8880;
  --white:   #ffffff;
  --border:  #e0d4ce;
  --gold:    #b8956a;
  --success: #4a7c59;
  --stripe:  #635bff;
}
*{margin:0;padding:0;box-sizing:border-box;}
html{scroll-behavior:smooth;}
body{
  background:var(--cream);
  color:var(--ink);
  font-family:'Jost',sans-serif;
  font-weight:300;
  min-height:100vh;
  overflow-x:hidden;
}

/* ── Screens ── */
.screen{display:none;min-height:100vh;}
.screen.active{display:block;}

/* ══════════════════════════════════════════════
   WELCOME SCREEN
══════════════════════════════════════════════ */
#screen-welcome{
  background: linear-gradient(160deg, #fdf8f5 0%, #f0e4de 50%, #fdf6f2 100%);
  display:flex; flex-direction:column; align-items:center;
  justify-content:center; padding:40px 24px; text-align:center;
  position:relative; overflow:hidden;
}
#screen-welcome::before{
  content:'';position:absolute;top:-80px;right:-80px;
  width:320px;height:320px;
  background:radial-gradient(circle, rgba(196,160,154,0.2), transparent 70%);
  border-radius:50%;
}
#screen-welcome::after{
  content:'';position:absolute;bottom:-60px;left:-60px;
  width:240px;height:240px;
  background:radial-gradient(circle, rgba(196,160,154,0.15), transparent 70%);
  border-radius:50%;
}
.welcome-logo{
  width:140px;height:140px;border-radius:50%;
  object-fit:cover;
  border:2px solid var(--rose-lt);
  box-shadow:0 8px 40px rgba(196,160,154,0.25);
  margin-bottom:24px;
  position:relative;z-index:1;
}
.welcome-brand{
  font-family:'Cormorant Garamond',serif;
  font-size:13px;letter-spacing:5px;color:var(--rose);
  font-weight:400;margin-bottom:8px;text-transform:uppercase;
  position:relative;z-index:1;
}
.welcome-title{
  font-family:'Cormorant Garamond',serif;
  font-size:34px;font-weight:600;color:var(--brown);
  line-height:1.15;margin-bottom:10px;
  position:relative;z-index:1;
}
.welcome-sub{
  font-size:13px;color:var(--muted);line-height:1.7;
  max-width:320px;margin:0 auto 36px;
  position:relative;z-index:1;
}
.gender-row{
  display:grid;grid-template-columns:1fr 1fr;gap:12px;
  width:100%;max-width:340px;margin-bottom:20px;
  position:relative;z-index:1;
}
.gender-btn{
  padding:18px 10px;border:1.5px solid var(--border);
  border-radius:16px;background:var(--white);
  cursor:pointer;transition:all 0.25s;
  font-family:'Cormorant Garamond',serif;
}
.gender-btn:hover{border-color:var(--rose);box-shadow:0 4px 20px rgba(196,160,154,0.2);}
.gender-btn .g-icon{font-size:28px;margin-bottom:6px;}
.gender-btn .g-label{font-size:16px;color:var(--brown);font-weight:600;}
.gender-btn .g-sub{font-size:10px;color:var(--muted);letter-spacing:1px;margin-top:2px;}
.free-badge{
  background:rgba(196,160,154,0.12);border:1px solid rgba(196,160,154,0.3);
  border-radius:20px;padding:8px 18px;
  font-size:11px;color:var(--rose-dk);font-weight:500;
  letter-spacing:0.5px;
  position:relative;z-index:1;
}

/* ══════════════════════════════════════════════
   MAIN APP
══════════════════════════════════════════════ */
#screen-app{display:none;flex-direction:column;}
#screen-app.active{display:flex;}

/* ── App Header ── */
.app-header{
  background:var(--brown);
  padding:16px 20px 0;
  position:sticky;top:0;z-index:200;
  box-shadow:0 2px 20px rgba(42,30,24,0.15);
}
.app-header-top{
  display:flex;align-items:center;gap:10px;margin-bottom:14px;
}
.app-logo-sm{
  width:32px;height:32px;border-radius:50%;
  object-fit:cover;border:1px solid rgba(196,160,154,0.4);
}
.app-brand{
  font-family:'Cormorant Garamond',serif;
  font-size:16px;color:var(--white);font-weight:600;
  letter-spacing:0.5px;
}
.app-gender-tag{
  margin-left:auto;
  background:rgba(196,160,154,0.2);border:1px solid rgba(196,160,154,0.35);
  color:var(--rose-lt);border-radius:20px;
  padding:3px 10px;font-size:10px;letter-spacing:1px;font-weight:500;
  cursor:pointer;
}
.nav-tabs{display:flex;overflow-x:auto;gap:0;scrollbar-width:none;}
.nav-tabs::-webkit-scrollbar{display:none;}
.nav-tab{
  flex-shrink:0;padding:10px 14px;border:none;cursor:pointer;
  background:transparent;color:rgba(255,255,255,0.45);
  font-size:11px;font-weight:500;letter-spacing:0.3px;
  border-bottom:2px solid transparent;
  transition:all 0.2s;font-family:'Jost',sans-serif;
  white-space:nowrap;
}
.nav-tab.active{color:var(--rose-lt);border-bottom-color:var(--rose);}

/* ── Panel ── */
.panel{display:none;padding:24px 18px 80px;}
.panel.active{display:block;}

/* ── Section title ── */
.stitle{
  font-size:9px;letter-spacing:3.5px;color:var(--muted);
  font-weight:600;margin-bottom:12px;text-transform:uppercase;
}

/* ── Upload card ── */
.upload-card{
  background:var(--brown);border-radius:20px;
  padding:24px 20px;margin-bottom:20px;position:relative;overflow:hidden;
}
.upload-card::after{
  content:'';position:absolute;top:-30px;right:-30px;
  width:120px;height:120px;
  background:rgba(196,160,154,0.1);border-radius:50%;
}
.upload-card .card-eyebrow{
  font-size:9px;letter-spacing:4px;color:var(--rose);
  font-weight:600;margin-bottom:4px;
}
.upload-card h2{
  font-family:'Cormorant Garamond',serif;
  font-size:22px;color:var(--white);margin-bottom:6px;
}
.upload-card p{font-size:11px;color:rgba(255,255,255,0.5);line-height:1.6;margin-bottom:18px;}

.upload-zone{
  border:1.5px dashed rgba(196,160,154,0.5);border-radius:14px;
  padding:28px 16px;text-align:center;cursor:pointer;
  transition:all 0.2s;position:relative;background:rgba(255,255,255,0.04);
}
.upload-zone:hover,.upload-zone.drag{
  border-color:var(--rose);background:rgba(196,160,154,0.07);
}
.upload-zone input{position:absolute;inset:0;opacity:0;cursor:pointer;}
.upload-zone .uz-icon{font-size:28px;margin-bottom:8px;}
.upload-zone h4{
  font-family:'Cormorant Garamond',serif;
  font-size:16px;color:var(--white);margin-bottom:3px;
}
.upload-zone p{font-size:10px;color:rgba(255,255,255,0.4);}

.preview-wrap{position:relative;border-radius:14px;overflow:hidden;margin-bottom:20px;display:none;}
.preview-wrap img{width:100%;max-height:300px;object-fit:cover;display:block;}
.preview-overlay{
  position:absolute;bottom:0;left:0;right:0;
  background:linear-gradient(transparent,rgba(42,30,24,0.85));
  padding:30px 14px 14px;
  display:flex;justify-content:space-between;align-items:flex-end;
}
.preview-badge{font-size:9px;letter-spacing:2px;color:var(--rose-lt);font-weight:600;}
.btn-change{
  background:var(--rose);color:var(--white);
  border:none;border-radius:20px;padding:5px 12px;
  font-size:9px;font-weight:600;cursor:pointer;letter-spacing:1px;
}

/* ── Module selector ── */
.modules-grid{
  display:grid;grid-template-columns:1fr 1fr;gap:8px;margin-bottom:20px;
}
.module-chip{
  border:1.5px solid var(--border);border-radius:12px;
  padding:12px 12px;cursor:pointer;
  background:var(--white);transition:all 0.2s;
  display:flex;align-items:center;gap:8px;
}
.module-chip.selected{
  border-color:var(--rose);
  background:rgba(196,160,154,0.07);
}
.module-chip input{width:14px;height:14px;accent-color:var(--rose);flex-shrink:0;}
.module-chip .mc-info .mc-name{font-size:11px;font-weight:600;color:var(--brown);}
.module-chip .mc-info .mc-sub{font-size:9px;color:var(--muted);margin-top:1px;}

/* ── Progress ── */
.progress-steps{display:flex;flex-direction:column;gap:8px;margin:20px 0;}
.pstep{
  display:flex;gap:12px;align-items:center;
  padding:12px 14px;border-radius:12px;
  background:var(--white);border:1px solid var(--border);transition:all 0.3s;
}
.pstep.active{border-color:var(--rose);background:rgba(196,160,154,0.05);}
.pstep.done{border-color:var(--success);background:rgba(74,124,89,0.04);}
.pstep-dot{
  width:28px;height:28px;min-width:28px;border-radius:50%;
  background:var(--border);display:flex;align-items:center;
  justify-content:center;font-size:11px;font-weight:700;
  color:var(--muted);transition:all 0.3s;
}
.pstep.active .pstep-dot{background:var(--rose);color:var(--white);animation:ripple 1.4s infinite;}
.pstep.done .pstep-dot{background:var(--success);color:var(--white);}
.pstep-label{font-size:11px;font-weight:500;color:var(--muted);}
.pstep.active .pstep-label,.pstep.done .pstep-label{color:var(--ink);}
@keyframes ripple{
  0%,100%{box-shadow:0 0 0 0 rgba(196,160,154,0.45);}
  50%{box-shadow:0 0 0 8px rgba(196,160,154,0);}
}

/* ── Results ── */
.res-hero{
  background:var(--brown);border-radius:18px;
  padding:22px 18px;margin-bottom:18px;
}
.res-hero .eyebrow{font-size:9px;letter-spacing:4px;color:var(--rose);font-weight:600;margin-bottom:4px;}
.res-hero h3{font-family:'Cormorant Garamond',serif;font-size:22px;color:var(--white);margin-bottom:10px;}
.badge-row{display:flex;gap:6px;flex-wrap:wrap;}
.badge{
  background:rgba(196,160,154,0.18);border:1px solid rgba(196,160,154,0.35);
  color:var(--rose-lt);border-radius:20px;
  padding:4px 11px;font-size:9px;font-weight:600;letter-spacing:0.5px;
}

.info-card{
  background:var(--white);border:1px solid var(--border);
  border-radius:14px;padding:14px 16px;margin-bottom:10px;
}
.info-card .ic-label{
  font-size:9px;letter-spacing:2.5px;color:var(--rose);
  font-weight:600;margin-bottom:6px;
}
.info-card p{font-size:12px;color:#444;line-height:1.7;}

/* ── Image grid ── */
.img-grid{display:grid;grid-template-columns:1fr 1fr;gap:10px;margin-bottom:18px;}
.img-card{border-radius:14px;overflow:hidden;border:1px solid var(--border);position:relative;}
.img-card img{width:100%;aspect-ratio:3/4;object-fit:cover;display:block;}
.img-card .img-lbl{
  position:absolute;bottom:0;left:0;right:0;
  background:linear-gradient(transparent,rgba(42,30,24,0.85));
  color:var(--white);font-size:9px;font-weight:600;
  padding:24px 10px 10px;letter-spacing:0.5px;
}
.img-placeholder{
  aspect-ratio:3/4;display:flex;flex-direction:column;
  align-items:center;justify-content:center;gap:6px;
  background:var(--cream-dk);border-radius:14px;
  border:1px dashed var(--border);
}
.img-placeholder .spin{font-size:20px;animation:spin 1s linear infinite;}
.img-placeholder p{font-size:9px;color:var(--muted);text-align:center;padding:0 8px;}
@keyframes spin{to{transform:rotate(360deg);}}

/* ── Color chips ── */
.color-grid{
  display:grid;grid-template-columns:repeat(4,1fr);gap:8px;margin:14px 0;
}
.c-chip{border-radius:10px;overflow:hidden;border:1px solid rgba(0,0,0,0.08);}
.c-chip .c-swatch{height:44px;}
.c-chip .c-name{font-size:9px;font-weight:600;color:var(--ink);padding:5px 6px;background:var(--white);text-align:center;line-height:1.3;}

/* ── Buttons ── */
.btn{
  width:100%;padding:15px;
  background:var(--rose);color:var(--white);
  border:none;border-radius:14px;
  font-size:13px;font-weight:600;cursor:pointer;
  font-family:'Jost',sans-serif;letter-spacing:0.5px;
  transition:all 0.2s;
}
.btn:hover{background:var(--rose-dk);transform:translateY(-1px);}
.btn:disabled{opacity:0.45;cursor:not-allowed;transform:none;}
.btn-outline{
  background:transparent;border:1.5px solid var(--rose);
  color:var(--rose);margin-top:10px;
}
.btn-stripe{background:var(--stripe);}
.btn-stripe:hover{background:#4f46e5;}

/* ── Error / Notice ── */
.err{
  background:rgba(192,57,43,0.07);border:1px solid rgba(192,57,43,0.2);
  border-radius:10px;padding:11px 14px;margin-bottom:14px;
  font-size:11px;color:#c0392b;display:none;
}
.notice{
  background:rgba(196,160,154,0.1);border:1px solid rgba(196,160,154,0.25);
  border-radius:10px;padding:11px 14px;margin-bottom:16px;
  font-size:11px;color:var(--brown-lt);line-height:1.6;
}
.notice strong{color:var(--rose-dk);}

/* ══════════════════════════════════════════════
   PRICING SCREEN
══════════════════════════════════════════════ */
#screen-pricing{
  background:linear-gradient(160deg,#fdf8f5,#f0e4de 60%,#fdf6f2);
  padding:0 0 60px;
}
.pricing-hero{
  background:var(--brown);padding:40px 24px 32px;
  text-align:center;position:relative;overflow:hidden;
}
.pricing-hero::after{
  content:'';position:absolute;bottom:-40px;left:50%;transform:translateX(-50%);
  width:300px;height:80px;
  background:radial-gradient(ellipse,rgba(196,160,154,0.15),transparent);
}
.pricing-hero img{width:60px;height:60px;border-radius:50%;object-fit:cover;margin-bottom:12px;}
.pricing-hero .ph-eyebrow{font-size:9px;letter-spacing:4px;color:var(--rose);font-weight:600;margin-bottom:6px;}
.pricing-hero h1{
  font-family:'Cormorant Garamond',serif;
  font-size:30px;color:var(--white);margin-bottom:8px;
}
.pricing-hero p{font-size:12px;color:rgba(255,255,255,0.5);line-height:1.6;}

.pricing-body{padding:28px 18px;}

.free-counter{
  background:var(--white);border:1px solid var(--border);
  border-radius:16px;padding:18px;margin-bottom:20px;
  display:flex;align-items:center;gap:14px;
}
.counter-ring{
  width:56px;height:56px;min-width:56px;border-radius:50%;
  background:conic-gradient(var(--rose) calc(var(--pct,65)*1%), var(--cream-dk) 0);
  display:flex;align-items:center;justify-content:center;
  position:relative;
}
.counter-ring::after{
  content:'';position:absolute;
  width:40px;height:40px;border-radius:50%;background:var(--white);
}
.counter-num{
  position:relative;z-index:1;
  font-family:'Cormorant Garamond',serif;
  font-size:16px;font-weight:700;color:var(--rose-dk);
}
.counter-info h4{font-size:13px;font-weight:600;color:var(--brown);margin-bottom:2px;}
.counter-info p{font-size:11px;color:var(--muted);}

.plan-card{
  border-radius:20px;padding:22px 18px;margin-bottom:14px;
}
.plan-free{background:var(--white);border:1.5px solid var(--border);}
.plan-month{background:var(--brown);}
.plan-year{
  background:linear-gradient(135deg,var(--rose-dk),var(--brown));
  position:relative;overflow:hidden;
}
.plan-year::before{
  content:'MÁS POPULAR';
  position:absolute;top:14px;right:-22px;
  background:var(--rose);color:var(--white);
  font-size:8px;font-weight:700;letter-spacing:2px;
  padding:4px 32px;transform:rotate(45deg);
}
.plan-eyebrow{font-size:9px;letter-spacing:3px;font-weight:600;margin-bottom:4px;}
.plan-free .plan-eyebrow{color:var(--rose);}
.plan-month .plan-eyebrow,.plan-year .plan-eyebrow{color:var(--rose-lt);}
.plan-price{
  font-family:'Cormorant Garamond',serif;
  font-size:38px;font-weight:700;line-height:1;margin-bottom:4px;
}
.plan-free .plan-price{color:var(--brown);}
.plan-month .plan-price,.plan-year .plan-price{color:var(--white);}
.plan-note{font-size:11px;margin-bottom:14px;}
.plan-free .plan-note{color:var(--muted);}
.plan-month .plan-note,.plan-year .plan-note{color:rgba(255,255,255,0.55);}
.plan-features{list-style:none;}
.plan-features li{
  font-size:11px;padding:6px 0;
  border-bottom:1px solid rgba(0,0,0,0.05);
  display:flex;gap:8px;align-items:flex-start;
}
.plan-free .plan-features li{color:#555;border-bottom-color:var(--border);}
.plan-month .plan-features li,.plan-year .plan-features li{
  color:rgba(255,255,255,0.75);
  border-bottom-color:rgba(255,255,255,0.08);
}
.plan-features li::before{content:'✓';font-weight:700;flex-shrink:0;}
.plan-free .plan-features li::before{color:var(--rose);}
.plan-month .plan-features li::before,.plan-year .plan-features li::before{color:var(--rose-lt);}

.plan-btn{
  width:100%;padding:13px;border:none;border-radius:12px;
  font-size:12px;font-weight:600;cursor:pointer;
  font-family:'Jost',sans-serif;letter-spacing:0.5px;
  margin-top:14px;transition:all 0.2s;
}
.plan-free .plan-btn{background:var(--rose);color:var(--white);}
.plan-month .plan-btn{background:var(--rose);color:var(--white);}
.plan-year .plan-btn{background:rgba(255,255,255,0.15);color:var(--white);border:1px solid rgba(255,255,255,0.25);}
.plan-year .plan-btn:hover{background:rgba(255,255,255,0.25);}

.referral-card{
  background:var(--white);border:1.5px solid rgba(196,160,154,0.4);
  border-radius:18px;padding:20px 18px;margin-bottom:14px;
}
.referral-card h3{
  font-family:'Cormorant Garamond',serif;
  font-size:20px;color:var(--brown);margin-bottom:6px;
}
.referral-card p{font-size:11px;color:var(--muted);line-height:1.7;margin-bottom:14px;}
.share-btn{
  display:flex;align-items:center;gap:10px;
  background:linear-gradient(135deg,#e1306c,#fd1d1d,#fcb045);
  color:var(--white);border:none;border-radius:12px;
  padding:13px 16px;width:100%;cursor:pointer;
  font-family:'Jost',sans-serif;font-size:12px;font-weight:600;
  transition:opacity 0.2s;
}
.share-btn:hover{opacity:0.9;}
.share-icon{font-size:16px;}

/* ══════════════════════════════════════════════
   INPUT FIELD
══════════════════════════════════════════════ */
.field label{
  display:block;font-size:9px;letter-spacing:2.5px;
  color:var(--rose);font-weight:600;margin-bottom:6px;
}
.field input{
  width:100%;padding:12px 14px;
  border:1.5px solid var(--border);border-radius:12px;
  background:var(--white);color:var(--ink);
  font-size:13px;font-family:'Jost',sans-serif;
  outline:none;transition:border 0.2s;
}
.field input:focus{border-color:var(--rose);}
.field input::placeholder{color:var(--muted);}
.field{margin-bottom:14px;}

/* ── Responsive fine-tuning ── */
@media(min-width:480px){
  .screen{max-width:480px;margin:0 auto;}
  #screen-welcome{min-height:100vh;}
}
</style>
</head>
<body>

<!-- ══════════════════════════════════════════════
     WELCOME SCREEN
══════════════════════════════════════════════ -->
<div id="screen-welcome" class="screen active">
  <img src="data:image/jpeg;base64,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igBc0UUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFAB//Z" 
       alt="mystyle_advice" class="welcome-logo"/>
  <div class="welcome-brand">mystyle_advice</div>
  <h1 class="welcome-title">Tu asesoría<br/>de imagen personal</h1>
  <p class="welcome-sub">Peinados · Colorimetría · Outfits · Labiales · Gafas · Joyería · Vídeo</p>

  <div class="gender-row">
    <div class="gender-btn" onclick="startApp('mujer')">
      <div class="g-icon">👩</div>
      <div class="g-label">Mujer</div>
      <div class="g-sub">ASESORÍA FEMENINA</div>
    </div>
    <div class="gender-btn" onclick="startApp('hombre')">
      <div class="g-icon">👨</div>
      <div class="g-label">Hombre</div>
      <div class="g-sub">ASESORÍA MASCULINA</div>
    </div>
  </div>

  <div class="free-badge">🎁 100 primeros análisis completamente gratis</div>

  <div style="margin-top:16px;">
    <span style="font-size:11px;color:var(--muted);cursor:pointer;text-decoration:underline;" onclick="showPricing()">Ver planes y precios →</span>
  </div>
</div>

<!-- ══════════════════════════════════════════════
     APP SCREEN
══════════════════════════════════════════════ -->
<div id="screen-app" class="screen">
  <div class="app-header">
    <div class="app-header-top">
      <img src="data:image/jpeg;base64,/9j/4AAQSkZJRgABAQAAAQABAAD/2wBDAAUDBAQEAwUEBAQFBQUGBwwIBwcHBw8LCwkMEQ8SEhEPERETFhwXExQaFRERGCEYGh0dHx8fExciJCIeJBweHx7/2wBDAQUFBQcGBw4ICA4eFBEUHh4eHh4eHh4eHh4eHh4eHh4eHh4eHh4eHh4eHh4eHh4eHh4eHh4eHh4eHh4eHh4eHh7/wAARCAEsASwDASIAAhEBAxEB/8QAHwAAAQUBAQEBAQEAAAAAAAAAAAECAwQFBgcICQoL/8QAtRAAAgEDAwIEAwUFBAQAAAF9AQIDAAQRBRIhMUEGE1FhByJxFDKBkaEII0KxwRVS0fAkM2JyggkKFhcYGRolJicoKSo0NTY3ODk6Q0RFRkdISUpTVFVWV1hZWmNkZWZnaGlqc3R1dnd4eXqDhIWGh4iJipKTlJWWl5iZmqKjpKWmp6ipqrKztLW2t7i5usLDxMXGx8jJytLT1NXW19jZ2uHi4+Tl5ufo6erx8vP09fb3+Pn6/8QAHwEAAwEBAQEBAQEBAQAAAAAAAAECAwQFBgcICQoL/8QAtREAAgECBAQDBAcFBAQAAQJ3AAECAxEEBSExBhJBUQdhcRMiMoEIFEKRobHBCSMzUvAVYnLRChYkNOEl8RcYGRomJygpKjU2Nzg5OkNERUZHSElKU1RVVldYWVpjZGVmZ2hpanN0dXZ3eHl6goOEhYaHiImKkpOUlZaXmJmaoqOkpaanqKmqsrO0tba3uLm6wsPExcbHyMnK0tPU1dbX2Nna4uPk5ebn6Onq8vP09fb3+Pn6/9oADAMBAAIRAxEAPwD61FLSUVkbC0UlFAC0CkooAXpRSUUgFoFJRQAoopKXNAB3o60ZqG6uba1Tfczxwr6uwFDGlcmorHOv20pK6fa3d83rFGQv/fRo8/xDP/qrGztB6zSl2/IUuZF+zfXQ2KBWP9h1yU/vtcEQ9ILcD9TQdEd/9drOpv8ASUL/ACFF32Dlj/MbGD6GjnuKxx4ftj1vNSPv9qNL/YMIHyahqaH2uSaV32Dlh3/A16Kxv7IvUOYNfv19pArj9aXyfEUP+rvbG6A7SwlD+Yp3fYORPZmxSVkf2nqdvn7bosrKOr20gkH5daltNd0u4k8pboRS9PLmBjb9aOZA6cjTopOoBHI7UUzMWkoooAKWkooAWkoooAWg0lFABSikooAD1ooooAKKKKACiiigAooooAKBRiigAooqpqWo2tggM7ku33IkGXc+wobGk27It1m32s2dtL9nQvdXXaCAbm/HsPxqybfVdV5vJG0+0P8Aywib964/2m7fQVpWFjaWEXlWkCRKeuByfqepqdXsXaMd9TOEeu3/ADLLHpcJ/hj+eX8T0FTWuh6dC/mvCbmb/nrcNvb9eK06KfKuoOo9loCgBcAYA6AdKKKKZAUe1HaigQClpKKAFpKWigBKhu7S1vE2XVvFMP8AbUH9amooY02tjGbRJLY79I1Ce0P/AAzc+ZEfwPSkGrXlia+06VIe8lwpRf8APyrZorO9ivaO2mtjltQ8Q6JCPLFyt1L/AM84B5jfo3FJZtq+p/LpWnfZIT/y2usDP0T/ABrqFRVGFUD6CnUc3YPZt/FIytG0XT7LbLHDvuB1mkO5/wDH0FXTS0VDdzRKysgooopiCiiigAooooAKKKKACiiigBaO1JRQAUtJRQAGiikJAHJA+poAWg0lFABzRRRTAKKKKQBRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABSUGkzQAZpM0ZpM0ALmlBpM0Z5oAdSE0maM0ALmkzRmjNAC5ozSZozQA7NGaM0UAFFGKM0AKBmjFGaM0ABFJiiigBc0UUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFAB//Z"
           alt="logo" class="app-logo-sm"/>
      <span class="app-brand">mystyle_advice</span>
      <span class="app-gender-tag" id="genderTag" onclick="goWelcome()">♀ MUJER ↩</span>
    </div>
    <div class="nav-tabs" id="navTabs">
      <button class="nav-tab active" onclick="showPanel('panel-inicio')">✦ Inicio</button>
      <button class="nav-tab" onclick="showPanel('panel-peinados')">✂️ Peinados</button>
      <button class="nav-tab" onclick="showPanel('panel-color')">🎨 Color</button>
      <button class="nav-tab" onclick="showPanel('panel-ropa')">👗 Ropa</button>
      <button class="nav-tab" onclick="showPanel('panel-labial')">💄 Labial</button>
      <button class="nav-tab" onclick="showPanel('panel-gafas')">👓 Gafas</button>
      <button class="nav-tab" onclick="showPanel('panel-joyeria')">💍 Joyería</button>
      <button class="nav-tab" onclick="showPanel('panel-video')">📹 Vídeo</button>
      <button class="nav-tab" onclick="showPricing()">⭐ Planes</button>
    </div>
  </div>

  <!-- Panel: Inicio -->
  <div id="panel-inicio" class="panel active">
    <div class="upload-card">
      <div class="card-eyebrow">PASO 1</div>
      <h2>Sube tu foto</h2>
      <p>Foto de frente, buena luz natural. Sin filtros. Sin gafas de sol.</p>
      <div class="upload-zone" id="uploadZone"
           ondrop="handleDrop(event)" ondragover="ev(event,true)" ondragleave="ev(event,false)">
        <input type="file" id="fileInput" accept="image/*" onchange="handleFile(event)"/>
        <div class="uz-icon">📷</div>
        <h4>Toca para subir</h4>
        <p>JPG · PNG · HEIC</p>
      </div>
    </div>

    <div class="preview-wrap" id="previewWrap">
      <img id="previewImg" src="" alt="preview"/>
      <div class="preview-overlay">
        <span class="preview-badge">✓ FOTO LISTA</span>
        <button class="btn-change" onclick="resetPhoto()">Cambiar</button>
      </div>
    </div>

    <div class="stitle">ELIGE TU ANÁLISIS</div>
    <div class="modules-grid" id="modulesGrid">
      <label class="module-chip selected">
        <input type="checkbox" checked onchange="toggleChip(this)"/> 
        <div class="mc-info"><div class="mc-name">✂️ Peinados</div><div class="mc-sub">Top 6 cortes</div></div>
      </label>
      <label class="module-chip selected">
        <input type="checkbox" checked onchange="toggleChip(this)"/>
        <div class="mc-info"><div class="mc-name">🎨 Colorimetría</div><div class="mc-sub">Paleta personal</div></div>
      </label>
      <label class="module-chip selected">
        <input type="checkbox" checked onchange="toggleChip(this)"/>
        <div class="mc-info"><div class="mc-name">👗 Estilismo</div><div class="mc-sub">4 looks completos</div></div>
      </label>
      <label class="module-chip">
        <input type="checkbox" onchange="toggleChip(this)"/>
        <div class="mc-info"><div class="mc-name">💄 Labial</div><div class="mc-sub">8 tonos</div></div>
      </label>
      <label class="module-chip">
        <input type="checkbox" onchange="toggleChip(this)"/>
        <div class="mc-info"><div class="mc-name">👓 Gafas</div><div class="mc-sub">6 monturas</div></div>
      </label>
      <label class="module-chip">
        <input type="checkbox" onchange="toggleChip(this)"/>
        <div class="mc-info"><div class="mc-name">💍 Joyería</div><div class="mc-sub">Pendientes y collares</div></div>
      </label>
      <label class="module-chip">
        <input type="checkbox" onchange="toggleChip(this)"/>
        <div class="mc-info"><div class="mc-name">📹 Vídeo</div><div class="mc-sub">Colores en cámara</div></div>
      </label>
    </div>

    <div class="field">
      <label>TU API KEY DE OPENAI (para generar imágenes)</label>
      <input type="password" id="apiKey" placeholder="sk-proj-..." oninput="checkReady()"/>
    </div>

    <div class="notice">
      <strong>💡 Consejo:</strong> Para mejores resultados usa una foto de frente con luz natural, fondo neutro y sin filtros. La IA analizará tu rostro, subtono de piel y complexión.
    </div>

    <div class="err" id="errMsg"></div>

    <button class="btn" id="analyzeBtn" onclick="startAnalysis()" disabled>
      Analizar con IA ✦
    </button>

    <div id="progressWrap" style="display:none;">
      <div class="progress-steps">
        <div class="pstep" id="ps1"><div class="pstep-dot">1</div><div class="pstep-label">Analizando tu rostro con IA</div></div>
        <div class="pstep" id="ps2"><div class="pstep-dot">2</div><div class="pstep-label">Generando imágenes de peinados</div></div>
        <div class="pstep" id="ps3"><div class="pstep-dot">3</div><div class="pstep-label">Creando paleta de colorimetría</div></div>
        <div class="pstep" id="ps4"><div class="pstep-dot">4</div><div class="pstep-label">Generando outfits personalizados</div></div>
        <div class="pstep" id="ps5"><div class="pstep-dot">✓</div><div class="pstep-label">Informe completo listo</div></div>
      </div>
    </div>
  </div>

  <!-- Panel: Peinados -->
  <div id="panel-peinados" class="panel">
    <div id="peinados-empty" style="text-align:center;padding:60px 20px;">
      <div style="font-size:40px;margin-bottom:12px;">✂️</div>
      <div style="font-family:'Cormorant Garamond',serif;font-size:20px;color:var(--brown);margin-bottom:6px;">Análisis de Peinados</div>
      <div style="font-size:11px;color:var(--muted);">Sube una foto y lanza el análisis</div>
    </div>
    <div id="peinados-result" style="display:none;">
      <div class="res-hero">
        <div class="eyebrow">ANÁLISIS FACIAL · PEINADOS</div>
        <h3 id="p-rostro">—</h3>
        <div class="badge-row" id="p-tags"></div>
      </div>
      <div class="stitle">TOP CORTES RECOMENDADOS</div>
      <div class="img-grid" id="grid-peinados"></div>
      <div class="info-card">
        <div class="ic-label">CONSEJO DEL ESTILISTA</div>
        <p id="p-consejo">—</p>
      </div>
      <div class="stitle" style="margin-top:16px;">CORTES A EVITAR</div>
      <div id="p-evitar"></div>
    </div>
  </div>

  <!-- Panel: Color -->
  <div id="panel-color" class="panel">
    <div id="color-empty" style="text-align:center;padding:60px 20px;">
      <div style="font-size:40px;margin-bottom:12px;">🎨</div>
      <div style="font-family:'Cormorant Garamond',serif;font-size:20px;color:var(--brown);margin-bottom:6px;">Colorimetría Personal</div>
      <div style="font-size:11px;color:var(--muted);">Sube una foto y lanza el análisis</div>
    </div>
    <div id="color-result" style="display:none;">
      <div class="res-hero">
        <div class="eyebrow">COLORIMETRÍA · ESTACIÓN CROMÁTICA</div>
        <h3 id="c-estacion">—</h3>
        <div class="badge-row" id="c-tags"></div>
      </div>
      <div class="stitle">PALETA DE COLORES FAVORECEDORES</div>
      <div class="color-grid" id="c-favgrid"></div>
      <div class="stitle">NEUTROS RECOMENDADOS</div>
      <div class="color-grid" id="c-neutgrid"></div>
      <div class="stitle">COLORES A EVITAR</div>
      <div class="color-grid" id="c-evitgrid"></div>
      <div class="info-card">
        <div class="ic-label">METALES QUE TE FAVORECEN</div>
        <p id="c-metales">—</p>
      </div>
      <div class="img-grid" id="grid-color"></div>
    </div>
  </div>

  <!-- Panel: Ropa -->
  <div id="panel-ropa" class="panel">
    <div id="ropa-empty" style="text-align:center;padding:60px 20px;">
      <div style="font-size:40px;margin-bottom:12px;">👗</div>
      <div style="font-family:'Cormorant Garamond',serif;font-size:20px;color:var(--brown);margin-bottom:6px;">Estilismo de Ropa</div>
      <div style="font-size:11px;color:var(--muted);">Sube una foto y lanza el análisis</div>
    </div>
    <div id="ropa-result" style="display:none;">
      <div class="res-hero">
        <div class="eyebrow">ESTILISMO · FIGURA CORPORAL</div>
        <h3 id="r-figura">—</h3>
        <div class="badge-row" id="r-tags"></div>
      </div>
      <div class="stitle">4 LOOKS GENERADOS PARA TI</div>
      <div class="img-grid" id="grid-ropa"></div>
      <div class="stitle" style="margin-top:16px;">PRENDAS CLAVE</div>
      <div id="r-prendas"></div>
      <div class="info-card" style="margin-top:12px;">
        <div class="ic-label">ERRORES A EVITAR</div>
        <p id="r-errores">—</p>
      </div>
    </div>
  </div>

  <!-- Panel: Labial -->
  <div id="panel-labial" class="panel">
    <div style="text-align:center;padding:60px 20px;">
      <div style="font-size:40px;margin-bottom:12px;">💄</div>
      <div style="font-family:'Cormorant Garamond',serif;font-size:20px;color:var(--brown);margin-bottom:6px;">Tonos de Labial</div>
      <div style="font-size:11px;color:var(--muted);margin-bottom:20px;">Incluido en el análisis completo</div>
      <button class="btn" style="max-width:240px;margin:0 auto;" onclick="showPanel('panel-inicio')">Volver al inicio</button>
    </div>
  </div>

  <!-- Panel: Gafas -->
  <div id="panel-gafas" class="panel">
    <div style="text-align:center;padding:60px 20px;">
      <div style="font-size:40px;margin-bottom:12px;">👓</div>
      <div style="font-family:'Cormorant Garamond',serif;font-size:20px;color:var(--brown);margin-bottom:6px;">Gafas y Monturas</div>
      <div style="font-size:11px;color:var(--muted);margin-bottom:20px;">Incluido en el análisis completo</div>
      <button class="btn" style="max-width:240px;margin:0 auto;" onclick="showPanel('panel-inicio')">Volver al inicio</button>
    </div>
  </div>

  <!-- Panel: Joyería -->
  <div id="panel-joyeria" class="panel">
    <div style="text-align:center;padding:60px 20px;">
      <div style="font-size:40px;margin-bottom:12px;">💍</div>
      <div style="font-family:'Cormorant Garamond',serif;font-size:20px;color:var(--brown);margin-bottom:6px;">Pendientes y Collares</div>
      <div style="font-size:11px;color:var(--muted);margin-bottom:20px;">Incluido en el análisis completo</div>
      <button class="btn" style="max-width:240px;margin:0 auto;" onclick="showPanel('panel-inicio')">Volver al inicio</button>
    </div>
  </div>

  <!-- Panel: Video -->
  <div id="panel-video" class="panel">
    <div style="text-align:center;padding:60px 20px;">
      <div style="font-size:40px;margin-bottom:12px;">📹</div>
      <div style="font-family:'Cormorant Garamond',serif;font-size:20px;color:var(--brown);margin-bottom:6px;">Colores para Vídeo</div>
      <div style="font-size:11px;color:var(--muted);margin-bottom:20px;">Incluido en el análisis completo</div>
      <button class="btn" style="max-width:240px;margin:0 auto;" onclick="showPanel('panel-inicio')">Volver al inicio</button>
    </div>
  </div>
</div>

<!-- ══════════════════════════════════════════════
     PRICING SCREEN
══════════════════════════════════════════════ -->
<div id="screen-pricing" class="screen">
  <div class="pricing-hero">
    <img src="data:image/jpeg;base64,/9j/4AAQSkZJRgABAQAAAQABAAD/2wBDAAUDBAQEAwUEBAQFBQUGBwwIBwcHBw8LCwkMEQ8SEhEPERETFhwXExQaFRERGCEYGh0dHx8fExciJCIeJBweHx7/2wBDAQUFBQcGBw4ICA4eFBEUHh4eHh4eHh4eHh4eHh4eHh4eHh4eHh4eHh4eHh4eHh4eHh4eHh4eHh4eHh4eHh4eHh7/wAARCAEsASwDASIAAhEBAxEB/8QAHwAAAQUBAQEBAQEAAAAAAAAAAAECAwQFBgcICQoL/8QAtRAAAgEDAwIEAwUFBAQAAAF9AQIDAAQRBRIhMUEGE1FhByJxFDKBkaEII0KxwRVS0fAkM2JyggkKFhcYGRolJicoKSo0NTY3ODk6Q0RFRkdISUpTVFVWV1hZWmNkZWZnaGlqc3R1dnd4eXqDhIWGh4iJipKTlJWWl5iZmqKjpKWmp6ipqrKztLW2t7i5usLDxMXGx8jJytLT1NXW19jZ2uHi4+Tl5ufo6erx8vP09fb3+Pn6/8QAHwEAAwEBAQEBAQEBAQAAAAAAAAECAwQFBgcICQoL/8QAtREAAgECBAQDBAcFBAQAAQJ3AAECAxEEBSExBhJBUQdhcRMiMoEIFEKRobHBCSMzUvAVYnLRChYkNOEl8RcYGRomJygpKjU2Nzg5OkNERUZHSElKU1RVVldYWVpjZGVmZ2hpanN0dXZ3eHl6goOEhYaHiImKkpOUlZaXmJmaoqOkpaanqKmqsrO0tba3uLm6wsPExcbHyMnK0tPU1dbX2Nna4uPk5ebn6Onq8vP09fb3+Pn6/9oADAMBAAIRAxEAPwD61FLSUVkbC0UlFAC0CkooAXpRSUUgFoFJRQAoopKXNAB3o60ZqG6uba1Tfczxwr6uwFDGlcmorHOv20pK6fa3d83rFGQv/fRo8/xDP/qrGztB6zSl2/IUuZF+zfXQ2KBWP9h1yU/vtcEQ9ILcD9TQdEd/9drOpv8ASUL/ACFF32Dlj/MbGD6GjnuKxx4ftj1vNSPv9qNL/YMIHyahqaH2uSaV32Dlh3/A16Kxv7IvUOYNfv19pArj9aXyfEUP+rvbG6A7SwlD+Yp3fYORPZmxSVkf2nqdvn7bosrKOr20gkH5daltNd0u4k8pboRS9PLmBjb9aOZA6cjTopOoBHI7UUzMWkoooAKWkooAWkoooAWg0lFABSikooAD1ooooAKKKKACiiigAooooAKBRiigAooqpqWo2tggM7ku33IkGXc+wobGk27It1m32s2dtL9nQvdXXaCAbm/HsPxqybfVdV5vJG0+0P8Aywib964/2m7fQVpWFjaWEXlWkCRKeuByfqepqdXsXaMd9TOEeu3/ADLLHpcJ/hj+eX8T0FTWuh6dC/mvCbmb/nrcNvb9eK06KfKuoOo9loCgBcAYA6AdKKKKZAUe1HaigQClpKKAFpKWigBKhu7S1vE2XVvFMP8AbUH9amooY02tjGbRJLY79I1Ce0P/AAzc+ZEfwPSkGrXlia+06VIe8lwpRf8APyrZorO9ivaO2mtjltQ8Q6JCPLFyt1L/AM84B5jfo3FJZtq+p/LpWnfZIT/y2usDP0T/ABrqFRVGFUD6CnUc3YPZt/FIytG0XT7LbLHDvuB1mkO5/wDH0FXTS0VDdzRKysgooopiCiiigAooooAKKKKACiiigBaO1JRQAUtJRQAGiikJAHJA+poAWg0lFABzRRRTAKKKKQBRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABSUGkzQAZpM0ZpM0ALmlBpM0Z5oAdSE0maM0ALmkzRmjNAC5ozSZozQA7NGaM0UAFFGKM0AKBmjFGaM0ABFJiiigBc0UUUAFFFFAB//Z"
         alt="logo"/>
    <div class="ph-eyebrow">MYSTYLE_ADVICE</div>
    <h1>Planes & Precios</h1>
    <p>Asesoría de imagen personal con IA.<br/>Resultados reales, en segundos.</p>
  </div>

  <div class="pricing-body">

    <!-- Free counter -->
    <div class="free-counter">
      <div class="counter-ring" style="--pct:65;">
        <span class="counter-num">65</span>
      </div>
      <div class="counter-info">
        <h4>Plazas gratuitas disponibles</h4>
        <p>De 100 plazas totales · Primeras 100 personas gratis</p>
      </div>
    </div>

    <!-- Plan Gratis -->
    <div class="plan-card plan-free">
      <div class="plan-eyebrow">GRATIS</div>
      <div class="plan-price">0€</div>
      <div class="plan-note">Primeras 100 personas · Sin tarjeta</div>
      <ul class="plan-features">
        <li>1 análisis completo gratuito</li>
        <li>Peinados + Colorimetría + Outfits</li>
        <li>Imágenes generadas con IA</li>
        <li>Descarga de resultados</li>
      </ul>
      <button class="plan-btn" onclick="goWelcome()">Empezar gratis →</button>
    </div>

    <!-- Plan Mensual -->
    <div class="plan-card plan-month">
      <div class="plan-eyebrow">MENSUAL</div>
      <div class="plan-price">9,95€</div>
      <div class="plan-note">al mes · Cancela cuando quieras</div>
      <ul class="plan-features">
        <li>Análisis ilimitados</li>
        <li>7 módulos completos (peinados, color, ropa, labial, gafas, joyería, vídeo)</li>
        <li>Imágenes fotorrealistas con IA</li>
        <li>Descarga PDF del informe</li>
        <li>Novedades y tendencias</li>
      </ul>
      <button class="plan-btn btn-stripe" onclick="goStripe('monthly')">Suscribirse con Stripe →</button>
    </div>

    <!-- Plan Anual -->
    <div class="plan-card plan-year">
      <div class="plan-eyebrow">ANUAL</div>
      <div class="plan-price">59,95€</div>
      <div class="plan-note">al año · Ahorra 59,45€ vs mensual</div>
      <ul class="plan-features">
        <li>3 asesorías completas al año</li>
        <li>7 módulos completos</li>
        <li>Descuentos exclusivos en tiendas de moda</li>
        <li>Newsletter de tendencias mensuales</li>
        <li>50% descuento indefinido en análisis extra</li>
        <li>Acceso prioritario a nuevas funciones</li>
      </ul>
      <button class="plan-btn" onclick="goStripe('annual')">Mejor opción → Contratar</button>
    </div>

    <!-- Referral -->
    <div class="referral-card">
      <h3>🎁 Comparte y ahorra 50%</h3>
      <p>Comparte tus resultados en Instagram etiquetando a <strong>@mystyle_advice</strong> e invita a 5 amigas/amigos. Obtén el <strong>50% de descuento permanente</strong> en tu suscripción.</p>
      <button class="share-btn" onclick="shareInstagram()">
        <span class="share-icon">📸</span>
        Compartir en Instagram y obtener 50%
      </button>
    </div>

    <button class="btn btn-outline" onclick="goBack()" style="margin-top:10px;">← Volver</button>
  </div>
</div>

<script>
// ─── State ────────────────────────────────────────────────────────────────────
let gender = 'mujer';
let photoB64 = null;
let results = {};

// ─── Navigation ───────────────────────────────────────────────────────────────
function showScreen(id){
  document.querySelectorAll('.screen').forEach(s=>s.classList.remove('active'));
  const s=document.getElementById('screen-'+id);
  s.classList.add('active');
}
function startApp(g){
  gender=g;
  document.getElementById('genderTag').textContent=(g==='mujer'?'♀ MUJER':'♂ HOMBRE')+' ↩';
  showScreen('app');
}
function goWelcome(){ showScreen('welcome'); }
function showPricing(){ showScreen('pricing'); }
function goBack(){
  if(document.getElementById('screen-app').classList.contains('active')) showScreen('welcome');
  else showScreen('app');
}
function showPanel(id){
  document.querySelectorAll('.panel').forEach(p=>p.classList.remove('active'));
  document.getElementById(id).classList.add('active');
  document.querySelectorAll('.nav-tab').forEach((t,i)=>{
    const panels=['panel-inicio','panel-peinados','panel-color','panel-ropa',
                  'panel-labial','panel-gafas','panel-joyeria','panel-video',null];
    t.classList.toggle('active',panels[i]===id);
  });
}

// ─── Upload ───────────────────────────────────────────────────────────────────
function ev(e,drag){e.preventDefault();document.getElementById('uploadZone').classList.toggle('drag',drag);}
function handleDrop(e){e.preventDefault();document.getElementById('uploadZone').classList.remove('drag');const f=e.dataTransfer.files[0];if(f)processFile(f);}
function handleFile(e){if(e.target.files[0])processFile(e.target.files[0]);}
function processFile(f){
  const r=new FileReader();
  r.onload=e=>{
    photoB64=e.target.result.split(',')[1];
    document.getElementById('previewImg').src=e.target.result;
    document.getElementById('uploadZone').style.display='none';
    document.getElementById('previewWrap').style.display='block';
    checkReady();
  };
  r.readAsDataURL(f);
}
function resetPhoto(){
  photoB64=null;
  document.getElementById('uploadZone').style.display='block';
  document.getElementById('previewWrap').style.display='none';
  document.getElementById('fileInput').value='';
  checkReady();
}
function checkReady(){
  const k=document.getElementById('apiKey').value.trim();
  document.getElementById('analyzeBtn').disabled=!(k&&photoB64);
}
function toggleChip(cb){cb.closest('.module-chip').classList.toggle('selected',cb.checked);}

// ─── Analysis ─────────────────────────────────────────────────────────────────
function setStep(n){
  for(let i=1;i<=5;i++){
    const el=document.getElementById('ps'+i);
    el.classList.remove('active','done');
    if(i<n)el.classList.add('done');
    else if(i===n)el.classList.add('active');
  }
}
function showErr(msg){const e=document.getElementById('errMsg');e.textContent='⚠️ '+msg;e.style.display='block';}
function hideErr(){document.getElementById('errMsg').style.display='none';}

async function startAnalysis(){
  const apiKey=document.getElementById('apiKey').value.trim();
  if(!apiKey||!photoB64)return;
  hideErr();
  document.getElementById('analyzeBtn').disabled=true;
  document.getElementById('progressWrap').style.display='block';

  const chips=[...document.querySelectorAll('.module-chip input')];
  const doPeinados=chips[0].checked, doColor=chips[1].checked, doRopa=chips[2].checked;

  try{
    setStep(1);
    const facial=await analyzeFacial();
    results.facial=facial;

    setStep(2);
    let pImgs=[];
    if(doPeinados) pImgs=await genImgs(apiKey, buildPeinadoPrompts(facial));

    setStep(3);
    let cImgs=[];
    if(doColor) cImgs=await genImgs(apiKey, buildColorPrompts(facial));

    setStep(4);
    let rImgs=[];
    if(doRopa) rImgs=await genImgs(apiKey, buildRopaPrompts(facial));

    setStep(5);
    renderResults(facial,pImgs,cImgs,rImgs,doPeinados,doColor,doRopa);
    setTimeout(()=>{showPanel(doPeinados?'panel-peinados':doColor?'panel-color':'panel-ropa');},700);

  }catch(e){
    console.error(e);
    showErr(e.message||'Error en el análisis. Verifica tu API key.');
    document.getElementById('analyzeBtn').disabled=false;
  }
}

async function analyzeFacial(){
  const genero=gender==='mujer'?'woman':'man';
  const prompt=`Analyze this ${genero}'s face and respond ONLY with valid JSON, no markdown:
{
  "forma_rostro":"oval/redondo/cuadrado/rectangular/triangular/diamante",
  "subtono":"frío/cálido/neutro",
  "estacion":"Invierno frío/Verano suave/Otoño profundo/Primavera cálida",
  "complexion":"brief physical build description in Spanish",
  "cabello":"hair color and texture in Spanish",
  "ojos":"eye color and shape in Spanish",
  "piel":"skin tone description in Spanish",
  "colores_favorecen":["c1","c2","c3","c4","c5","c6"],
  "colores_hex":["#hex1","#hex2","#hex3","#hex4","#hex5","#hex6"],
  "neutros":["n1","n2","n3","n4"],
  "neutros_hex":["#nh1","#nh2","#nh3","#nh4"],
  "colores_evitar":["e1","e2","e3"],
  "evitar_hex":["#eh1","#eh2","#eh3"],
  "metales":"recommended metals in Spanish",
  "peinados_top3":["hairstyle 1 in Spanish","hairstyle 2","hairstyle 3"],
  "peinados_evitar":["avoid 1 in Spanish","avoid 2"],
  "estilos_ropa":["style 1 in Spanish","style 2","style 3","style 4"],
  "figura":"body figure type in Spanish",
  "consejo_peinado":"2-line hairstyle advice in Spanish",
  "prendas_clave":["garment 1 in Spanish","garment 2","garment 3","garment 4"],
  "errores_estilismo":"2-line styling mistakes to avoid in Spanish"
}`;

  const resp=await fetch('https://api.anthropic.com/v1/messages',{
    method:'POST',
    headers:{'Content-Type':'application/json'},
    body:JSON.stringify({
      model:'claude-sonnet-4-20250514',
      max_tokens:1200,
      messages:[{role:'user',content:[
        {type:'image',source:{type:'base64',media_type:'image/jpeg',data:photoB64}},
        {type:'text',text:prompt}
      ]}]
    })
  });
  if(!resp.ok) throw new Error('Error Claude API: '+resp.status);
  const d=await resp.json();
  if(d.error) throw new Error('Claude: '+d.error.message);
  const txt=d.content?.find(b=>b.type==='text')?.text||'';
  const m=txt.match(/\{[\s\S]*\}/);
  if(!m) throw new Error('No se pudo parsear el análisis facial');
  return JSON.parse(m[0]);
}

async function genImgs(apiKey, prompts){
  const results=[];
  for(const p of prompts){
    try{
      const resp=await fetch('https://api.openai.com/v1/images/generations',{
        method:'POST',
        headers:{'Content-Type':'application/json','Authorization':'Bearer '+apiKey},
        body:JSON.stringify({model:'dall-e-3',prompt:p.prompt,n:1,size:'1024x1792',quality:'standard',response_format:'url'})
      });
      if(!resp.ok){const e=await resp.json();results.push({label:p.label,url:null,error:e.error?.message});continue;}
      const d=await resp.json();
      results.push({label:p.label,url:d.data?.[0]?.url||null});
    }catch(e){results.push({label:p.label,url:null,error:e.message});}
  }
  return results;
}

function buildPeinadoPrompts(f){
  const base=`Hyperrealistic editorial portrait of a ${gender==='mujer'?'woman':'man"}, ${f.piel}, ${f.ojos} eyes. Face shape: ${f.forma_rostro}. Hair: ${f.cabello}. Studio lighting, neutral background, premium fashion magazine quality, ultra detailed.`;
  return f.peinados_top3.map(p=>({label:p,prompt:`${base} Wearing hairstyle: ${p}. Natural expression, slight smile. High fashion editorial.`}));
}
function buildColorPrompts(f){
  return[
    {label:f.estacion,prompt:`Hyperrealistic portrait of a ${gender==='mujer'?'woman':'man'}, ${f.piel}. Wearing clothing in colors: ${f.colores_favorecen.slice(0,3).join(', ')}. ${f.estacion} color season. Studio lighting, fashion editorial, clean background.`},
    {label:'Paleta favorecedora',prompt:`Full body photo of a ${gender==='mujer'?'woman':'man'}, ${f.piel}. Outfit in ${f.colores_favorecen[0]} and ${f.colores_favorecen[1]}. Professional styling, editorial quality.`}
  ];
}
function buildRopaPrompts(f){
  return f.estilos_ropa.slice(0,4).map(e=>({label:e,prompt:`Hyperrealistic full body fashion photo of a ${gender==='mujer'?'woman':'man'}, ${f.piel}, ${f.figura} figure. Wearing complete ${e} outfit. Colors: ${f.colores_favorecen.slice(0,2).join(' and ')}. Premium fashion editorial, neutral background, 8k.`}));
}

// ─── Render ───────────────────────────────────────────────────────────────────
function renderResults(facial,pImgs,cImgs,rImgs,doPeinados,doColor,doRopa){
  // Peinados
  if(doPeinados){
    document.getElementById('peinados-empty').style.display='none';
    document.getElementById('peinados-result').style.display='block';
    document.getElementById('p-rostro').textContent='Rostro '+facial.forma_rostro;
    document.getElementById('p-consejo').textContent=facial.consejo_peinado;
    const pt=document.getElementById('p-tags');
    pt.innerHTML='';
    [facial.estacion,'Subtono '+facial.subtono].forEach(t=>{const s=document.createElement('span');s.className='badge';s.textContent=t;pt.appendChild(s);});
    renderGrid('grid-peinados',pImgs);
    const pe=document.getElementById('p-evitar');
    pe.innerHTML=(facial.peinados_evitar||[]).map(p=>`<div class="info-card" style="border-left:3px solid var(--rose);"><div class="ic-label">EVITAR</div><p>✗ ${p}</p></div>`).join('');
  }
  // Color
  if(doColor){
    document.getElementById('color-empty').style.display='none';
    document.getElementById('color-result').style.display='block';
    document.getElementById('c-estacion').textContent=facial.estacion;
    document.getElementById('c-metales').textContent=facial.metales;
    const ct=document.getElementById('c-tags');
    ct.innerHTML='';
    ['Subtono '+facial.subtono,'Piel '+facial.piel].forEach(t=>{const s=document.createElement('span');s.className='badge';s.textContent=t;ct.appendChild(s);});
    renderColorGrid('c-favgrid',facial.colores_favorecen,facial.colores_hex);
    renderColorGrid('c-neutgrid',facial.neutros,facial.neutros_hex);
    renderColorGrid('c-evitgrid',facial.colores_evitar,facial.evitar_hex);
    renderGrid('grid-color',cImgs);
  }
  // Ropa
  if(doRopa){
    document.getElementById('ropa-empty').style.display='none';
    document.getElementById('ropa-result').style.display='block';
    document.getElementById('r-figura').textContent='Figura '+facial.figura;
    document.getElementById('r-errores').textContent=facial.errores_estilismo;
    const rt=document.getElementById('r-tags');
    rt.innerHTML='';
    [facial.estilo_base||facial.estilos_ropa?.[0]||'Smart Casual'].forEach(t=>{const s=document.createElement('span');s.className='badge';s.textContent=t;rt.appendChild(s);});
    renderGrid('grid-ropa',rImgs);
    const rp=document.getElementById('r-prendas');
    rp.innerHTML=(facial.prendas_clave||[]).map(p=>`<div class="info-card" style="margin-bottom:6px;"><div class="ic-label">PRENDA CLAVE</div><p>📌 ${p}</p></div>`).join('');
  }
}

function renderGrid(id,imgs){
  const g=document.getElementById(id);g.innerHTML='';
  imgs.forEach(img=>{
    const d=document.createElement('div');
    if(img.url){
      d.className='img-card';
      d.innerHTML=`<img src="${img.url}" alt="${img.label}" loading="lazy"/><div class="img-lbl">${img.label}</div>`;
    }else{
      d.className='img-placeholder';
      d.innerHTML=`<span>⚠️</span><p>${img.label}<br/><small>${img.error||'No generada'}</small></p>`;
    }
    g.appendChild(d);
  });
}

function renderColorGrid(id,names,hexes){
  const g=document.getElementById(id);if(!g)return;g.innerHTML='';
  (hexes||[]).forEach((h,i)=>{
    const d=document.createElement('div');d.className='c-chip';
    d.innerHTML=`<div class="c-swatch" style="background:${h}"></div><div class="c-name">${(names||[])[i]||h}</div>`;
    g.appendChild(d);
  });
}

// ─── Stripe & Share ───────────────────────────────────────────────────────────
function goStripe(plan){
  // Replace with your real Stripe payment links
  const urls={
    monthly:'https://buy.stripe.com/MONTHLY_LINK',
    annual:'https://buy.stripe.com/ANNUAL_LINK'
  };
  alert('🔗 Integra aquí tu link de Stripe:\n'+urls[plan]+'\n\nCrea tus links en dashboard.stripe.com → Payment Links');
}

function shareInstagram(){
  const text='¡Acabo de hacer mi asesoría de imagen personal con IA en @mystyle_advice! 🌟✨ Peinados, colorimetría y outfits personalizados. ¡Es increíble! 👗💄 Pruébalo gratis → mystyleadvice.com\n\n#mystyleadvice #asesoriadeimagenIA #moda #estilo';
  if(navigator.share){
    navigator.share({text,url:'https://mystyleadvice.com'}).catch(()=>{});
  }else{
    window.open('https://www.instagram.com/mystyle_advice','_blank');
    navigator.clipboard?.writeText(text).then(()=>alert('✓ Texto copiado. Pégalo en tu historia de Instagram y etiqueta @mystyle_advice'));
  }
}
</script>
</body>
</html>
