<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>GlassCraft Pro — Premium Glass Works</title>
<link href="https://fonts.googleapis.com/css2?family=Syne:wght@400;600;700;800&family=Plus+Jakarta+Sans:wght@300;400;500;600&display=swap" rel="stylesheet"/>
<style>
:root {
  --bg: #06080d;
  --bg2: #0a0f18;
  --card: #0d1420;
  --cyan: #22d3ee;
  --cyan2: #06b6d4;
  --gold: #f59e0b;
  --gold2: #fbbf24;
  --violet: #a78bfa;
  --green: #34d399;
  --pink: #f472b6;
  --text: #e2e8f0;
  --muted: #64748b;
  --border: rgba(255,255,255,0.07);
  --white: #f8fafc;
}

*, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
html { scroll-behavior: smooth; }
body {
  background: var(--bg);
  color: var(--text);
  font-family: 'Plus Jakarta Sans', sans-serif;
  font-weight: 400;
  overflow-x: hidden;
}

/* SCROLLBAR */
::-webkit-scrollbar { width: 6px; }
::-webkit-scrollbar-track { background: var(--bg); }
::-webkit-scrollbar-thumb { background: var(--cyan2); border-radius: 3px; }

/* ── NAV ── */
nav {
  position: fixed; top: 0; left: 0; right: 0; z-index: 200;
  padding: 1.2rem 6%;
  display: flex; align-items: center; justify-content: space-between;
  background: rgba(6,8,13,0.85);
  backdrop-filter: blur(24px);
  border-bottom: 1px solid var(--border);
}
.logo {
  font-family: 'Syne', sans-serif;
  font-size: 1.4rem; font-weight: 800;
  background: linear-gradient(90deg, var(--cyan), var(--gold));
  -webkit-background-clip: text; -webkit-text-fill-color: transparent;
  background-clip: text;
  text-decoration: none; letter-spacing: -0.02em;
}
nav ul { list-style: none; display: flex; gap: 2rem; align-items: center; }
nav ul a {
  color: #94a3b8; text-decoration: none;
  font-size: 0.82rem; font-weight: 500; letter-spacing: 0.06em;
  text-transform: uppercase; transition: color 0.3s;
}
nav ul a:hover { color: var(--cyan); }
.nav-btn {
  background: linear-gradient(135deg, var(--cyan), var(--cyan2)) !important;
  color: #06080d !important;
  padding: 0.55rem 1.4rem; border-radius: 6px;
  font-weight: 600 !important; font-size: 0.8rem !important;
  transition: transform 0.2s, box-shadow 0.2s !important;
}
.nav-btn:hover { transform: translateY(-2px) !important; box-shadow: 0 8px 20px rgba(34,211,238,0.35) !important; }

/* ── HERO ── */
.hero {
  min-height: 100vh;
  display: flex; align-items: center;
  padding: 9rem 6% 5rem;
  position: relative; overflow: hidden;
}
.hero-bg {
  position: absolute; inset: 0;
  background:
    radial-gradient(ellipse 70% 60% at 80% 30%, rgba(34,211,238,0.07) 0%, transparent 55%),
    radial-gradient(ellipse 50% 70% at 15% 80%, rgba(167,139,250,0.06) 0%, transparent 55%),
    radial-gradient(ellipse 40% 50% at 60% 70%, rgba(245,158,11,0.04) 0%, transparent 50%);
}
/* Animated grid lines */
.hero-grid {
  position: absolute; inset: 0;
  background-image:
    linear-gradient(rgba(34,211,238,0.04) 1px, transparent 1px),
    linear-gradient(90deg, rgba(34,211,238,0.04) 1px, transparent 1px);
  background-size: 60px 60px;
  mask-image: radial-gradient(ellipse 80% 80% at 50% 50%, black 20%, transparent 80%);
}
.hero-content { position: relative; z-index: 2; max-width: 720px; }
.hero-pill {
  display: inline-flex; align-items: center; gap: 0.6rem;
  background: rgba(34,211,238,0.08);
  border: 1px solid rgba(34,211,238,0.25);
  padding: 0.45rem 1.1rem; border-radius: 100px;
  font-size: 0.75rem; font-weight: 600; letter-spacing: 0.12em;
  text-transform: uppercase; color: var(--cyan);
  margin-bottom: 2rem; animation: fadeUp 0.8s ease both;
}
.hero-pill span { width: 6px; height: 6px; background: var(--cyan); border-radius: 50%; animation: pulse 2s infinite; }
@keyframes pulse { 0%,100%{opacity:1;transform:scale(1)} 50%{opacity:0.4;transform:scale(0.7)} }
h1 {
  font-family: 'Syne', sans-serif;
  font-size: clamp(2.8rem, 6.5vw, 5rem);
  font-weight: 800; line-height: 1.05;
  color: var(--white); letter-spacing: -0.03em;
  margin-bottom: 1.5rem;
  animation: fadeUp 0.8s 0.15s ease both;
}
h1 .grad1 {
  background: linear-gradient(135deg, var(--cyan) 0%, var(--violet) 100%);
  -webkit-background-clip: text; -webkit-text-fill-color: transparent; background-clip: text;
}
h1 .grad2 {
  background: linear-gradient(135deg, var(--gold) 0%, var(--pink) 100%);
  -webkit-background-clip: text; -webkit-text-fill-color: transparent; background-clip: text;
}
.hero-sub {
  font-size: 1.1rem; color: #94a3b8; line-height: 1.75;
  max-width: 560px; margin-bottom: 2.5rem;
  animation: fadeUp 0.8s 0.3s ease both;
}
.hero-actions { display: flex; gap: 1rem; flex-wrap: wrap; animation: fadeUp 0.8s 0.45s ease both; }
.btn-cyan {
  background: linear-gradient(135deg, var(--cyan), #0891b2);
  color: #06080d; padding: 0.9rem 2rem;
  font-size: 0.9rem; font-weight: 700; font-family: 'Plus Jakarta Sans', sans-serif;
  border: none; border-radius: 8px; cursor: pointer;
  text-decoration: none; display: inline-flex; align-items: center; gap: 0.5rem;
  transition: all 0.3s; letter-spacing: 0.02em;
}
.btn-cyan:hover { transform: translateY(-3px); box-shadow: 0 12px 30px rgba(34,211,238,0.4); }
.btn-gold {
  background: linear-gradient(135deg, var(--gold), #d97706);
  color: #06080d; padding: 0.9rem 2rem;
  font-size: 0.9rem; font-weight: 700; font-family: 'Plus Jakarta Sans', sans-serif;
  border: none; border-radius: 8px; cursor: pointer;
  text-decoration: none; display: inline-flex; align-items: center; gap: 0.5rem;
  transition: all 0.3s;
}
.btn-gold:hover { transform: translateY(-3px); box-shadow: 0 12px 30px rgba(245,158,11,0.4); }
.btn-ghost {
  background: transparent; color: #94a3b8;
  padding: 0.9rem 2rem; font-size: 0.9rem; font-weight: 500;
  font-family: 'Plus Jakarta Sans', sans-serif;
  border: 1px solid var(--border); border-radius: 8px; cursor: pointer;
  text-decoration: none; display: inline-flex; align-items: center; gap: 0.5rem;
  transition: all 0.3s;
  backdrop-filter: blur(10px);
}
.btn-ghost:hover { border-color: var(--cyan); color: var(--cyan); transform: translateY(-2px); }

@keyframes fadeUp { from{opacity:0;transform:translateY(30px)} to{opacity:1;transform:translateY(0)} }

/* ── STATS ── */
.stats-bar {
  background: var(--bg2);
  border-top: 1px solid var(--border);
  border-bottom: 1px solid var(--border);
  padding: 2.5rem 6%;
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 1rem;
}
.stat {
  text-align: center;
  padding: 1.5rem;
  border-right: 1px solid var(--border);
}
.stat:last-child { border-right: none; }
.stat-num {
  font-family: 'Syne', sans-serif;
  font-size: 2.4rem; font-weight: 800; line-height: 1;
}
.stat-num.c { background: linear-gradient(135deg,var(--cyan),#0891b2); -webkit-background-clip:text; -webkit-text-fill-color:transparent; background-clip:text; }
.stat-num.g { background: linear-gradient(135deg,var(--gold),#d97706); -webkit-background-clip:text; -webkit-text-fill-color:transparent; background-clip:text; }
.stat-num.v { background: linear-gradient(135deg,var(--violet),#7c3aed); -webkit-background-clip:text; -webkit-text-fill-color:transparent; background-clip:text; }
.stat-num.p { background: linear-gradient(135deg,var(--green),#059669); -webkit-background-clip:text; -webkit-text-fill-color:transparent; background-clip:text; }
.stat-label { font-size: 0.75rem; color: var(--muted); text-transform: uppercase; letter-spacing: 0.12em; margin-top: 0.4rem; }

/* ── WHAT WE DO ── */
.work-section { padding: 7rem 6%; background: var(--bg); }
.section-header { margin-bottom: 4rem; }
.section-tag {
  display: inline-flex; align-items: center; gap: 0.5rem;
  font-size: 0.72rem; font-weight: 700;
  text-transform: uppercase; letter-spacing: 0.18em;
  color: var(--cyan); margin-bottom: 1rem;
}
.section-tag::before { content: ''; width: 24px; height: 2px; background: var(--cyan); border-radius: 2px; }
h2 {
  font-family: 'Syne', sans-serif;
  font-size: clamp(2rem, 3.5vw, 2.8rem);
  font-weight: 800; color: var(--white);
  letter-spacing: -0.03em; line-height: 1.15;
}
h2 span {
  background: linear-gradient(135deg, var(--gold), var(--pink));
  -webkit-background-clip: text; -webkit-text-fill-color: transparent; background-clip: text;
}
.section-sub { color: var(--muted); font-size: 1rem; line-height: 1.7; margin-top: 0.8rem; max-width: 600px; }

/* Services grid */
.services-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 1.5px;
  background: var(--border);
  border: 1px solid var(--border);
  border-radius: 16px;
  overflow: hidden;
}
.svc {
  background: var(--card);
  padding: 2.4rem 2rem;
  position: relative; overflow: hidden;
  transition: background 0.35s;
  cursor: default;
}
.svc::after {
  content: '';
  position: absolute; bottom: 0; left: 0; right: 0;
  height: 3px;
  transform: scaleX(0); transform-origin: left;
  transition: transform 0.35s;
  border-radius: 0;
}
.svc.c1::after { background: linear-gradient(90deg, var(--cyan), var(--violet)); }
.svc.c2::after { background: linear-gradient(90deg, var(--gold), var(--pink)); }
.svc.c3::after { background: linear-gradient(90deg, var(--green), var(--cyan)); }
.svc.c4::after { background: linear-gradient(90deg, var(--violet), var(--pink)); }
.svc.c5::after { background: linear-gradient(90deg, var(--pink), var(--gold)); }
.svc.c6::after { background: linear-gradient(90deg, var(--cyan), var(--green)); }
.svc.c7::after { background: linear-gradient(90deg, var(--gold), var(--cyan)); }
.svc.c8::after { background: linear-gradient(90deg, var(--violet), var(--green)); }
.svc.c9::after { background: linear-gradient(90deg, var(--pink), var(--cyan)); }
.svc:hover { background: #111d2e; }
.svc:hover::after { transform: scaleX(1); }
.svc-icon {
  font-size: 2.2rem; margin-bottom: 1.2rem;
  display: block; line-height: 1;
}
.svc h3 {
  font-family: 'Syne', sans-serif;
  font-size: 1.1rem; font-weight: 700;
  color: var(--white); margin-bottom: 0.7rem; letter-spacing: -0.01em;
}
.svc p { font-size: 0.85rem; color: var(--muted); line-height: 1.7; }
.svc-tags {
  display: flex; flex-wrap: wrap; gap: 0.4rem; margin-top: 1.2rem;
}
.tag {
  font-size: 0.68rem; font-weight: 600; letter-spacing: 0.06em;
  padding: 0.25rem 0.65rem; border-radius: 100px;
  text-transform: uppercase;
}
.tag.teal { background: rgba(34,211,238,0.1); color: var(--cyan); border: 1px solid rgba(34,211,238,0.2); }
.tag.gold { background: rgba(245,158,11,0.1); color: var(--gold); border: 1px solid rgba(245,158,11,0.2); }
.tag.violet { background: rgba(167,139,250,0.1); color: var(--violet); border: 1px solid rgba(167,139,250,0.2); }
.tag.green { background: rgba(52,211,153,0.1); color: var(--green); border: 1px solid rgba(52,211,153,0.2); }
.tag.pink { background: rgba(244,114,182,0.1); color: var(--pink); border: 1px solid rgba(244,114,182,0.2); }

/* ── PORTFOLIO / WORK ── */
.portfolio-section { padding: 7rem 6%; background: var(--bg2); }
.portfolio-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 1rem;
  margin-top: 3rem;
}
.port-card {
  background: var(--card);
  border: 1px solid var(--border);
  border-radius: 12px;
  overflow: hidden;
  transition: transform 0.3s, box-shadow 0.3s;
  cursor: pointer;
}
.port-card:hover { transform: translateY(-6px); box-shadow: 0 20px 50px rgba(0,0,0,0.4); }
.port-visual {
  height: 200px;
  display: flex; align-items: center; justify-content: center;
  font-size: 5rem; position: relative; overflow: hidden;
}
.port-visual span { position: relative; z-index: 2; filter: drop-shadow(0 4px 12px rgba(0,0,0,0.5)); }
.port-visual::before {
  content: ''; position: absolute; inset: 0;
}
.pv1::before { background: linear-gradient(135deg, rgba(34,211,238,0.15), rgba(6,182,212,0.08)); }
.pv2::before { background: linear-gradient(135deg, rgba(245,158,11,0.15), rgba(251,191,36,0.08)); }
.pv3::before { background: linear-gradient(135deg, rgba(167,139,250,0.15), rgba(124,58,237,0.08)); }
.pv4::before { background: linear-gradient(135deg, rgba(52,211,153,0.15), rgba(5,150,105,0.08)); }
.pv5::before { background: linear-gradient(135deg, rgba(244,114,182,0.15), rgba(219,39,119,0.08)); }
.pv6::before { background: linear-gradient(135deg, rgba(34,211,238,0.12), rgba(167,139,250,0.12)); }
.port-body { padding: 1.4rem 1.5rem; }
.port-cat {
  font-size: 0.67rem; font-weight: 700; letter-spacing: 0.14em;
  text-transform: uppercase; margin-bottom: 0.5rem;
}
.port-title { font-family: 'Syne', sans-serif; font-size: 1rem; font-weight: 700; color: var(--white); margin-bottom: 0.6rem; }
.port-desc { font-size: 0.82rem; color: var(--muted); line-height: 1.65; }

/* ── VIEW WORK GITHUB BUTTON SECTION ── */
.github-section {
  padding: 5rem 6%;
  background: var(--bg);
  display: flex; align-items: center; justify-content: space-between;
  gap: 3rem; flex-wrap: wrap;
}
.github-left h2 { margin-bottom: 0.8rem; }
.github-left p { color: var(--muted); font-size: 1rem; line-height: 1.7; max-width: 520px; }
.github-right {
  display: flex; flex-direction: column; gap: 1rem; align-items: center;
  background: var(--card);
  border: 1px solid rgba(34,211,238,0.2);
  border-radius: 16px;
  padding: 2.5rem 3rem;
  text-align: center;
  min-width: 300px;
  position: relative; overflow: hidden;
}
.github-right::before {
  content: '';
  position: absolute; top: 0; left: 0; right: 0; height: 3px;
  background: linear-gradient(90deg, var(--cyan), var(--violet), var(--gold));
}
.github-icon { font-size: 3rem; margin-bottom: 0.5rem; }
.github-right h3 { font-family: 'Syne', sans-serif; font-size: 1.2rem; font-weight: 700; color: var(--white); }
.github-right p { font-size: 0.82rem; color: var(--muted); margin: 0.4rem 0 1.2rem; }
.btn-github {
  display: inline-flex; align-items: center; gap: 0.8rem;
  background: linear-gradient(135deg, var(--cyan), var(--violet));
  color: var(--white); padding: 0.85rem 2rem;
  font-size: 0.88rem; font-weight: 700;
  font-family: 'Plus Jakarta Sans', sans-serif;
  border-radius: 8px; text-decoration: none;
  transition: all 0.3s; border: none; cursor: pointer;
  letter-spacing: 0.02em;
}
.btn-github:hover { transform: translateY(-3px); box-shadow: 0 12px 30px rgba(34,211,238,0.35); }
.btn-github svg { width: 18px; height: 18px; fill: currentColor; }
.photo-count {
  display: flex; align-items: center; gap: 0.4rem;
  font-size: 0.75rem; color: var(--muted);
}
.photo-count::before { content: '📷'; }

/* ── WHY CHOOSE US ── */
.why-section { padding: 7rem 6%; background: var(--bg2); }
.why-grid {
  display: grid; grid-template-columns: repeat(4, 1fr);
  gap: 1.5px; background: var(--border);
  border: 1px solid var(--border); border-radius: 16px; overflow: hidden;
  margin-top: 3.5rem;
}
.why-card { background: var(--card); padding: 2.5rem 2rem; transition: background 0.3s; }
.why-card:hover { background: #111d2e; }
.why-num {
  font-family: 'Syne', sans-serif;
  font-size: 3.5rem; font-weight: 800; line-height: 1;
  opacity: 0.08; margin-bottom: 1rem; color: var(--white);
}
.why-icon { font-size: 2rem; margin-bottom: 1rem; display: block; }
.why-card h3 {
  font-family: 'Syne', sans-serif; font-size: 1rem; font-weight: 700;
  color: var(--white); margin-bottom: 0.6rem;
}
.why-card p { font-size: 0.83rem; color: var(--muted); line-height: 1.7; }

/* ── TESTIMONIALS ── */
.testi-section { padding: 7rem 6%; background: var(--bg); }
.testi-grid { display: grid; grid-template-columns: repeat(3, 1fr); gap: 1.5rem; margin-top: 3rem; }
.testi {
  background: var(--card); border: 1px solid var(--border);
  border-radius: 16px; padding: 2rem;
  position: relative; overflow: hidden;
  transition: border-color 0.3s, transform 0.3s;
}
.testi:hover { border-color: rgba(34,211,238,0.3); transform: translateY(-4px); }
.testi-top {
  position: absolute; top: 0; left: 0; right: 0; height: 3px;
}
.testi:nth-child(1) .testi-top { background: linear-gradient(90deg, var(--cyan), var(--violet)); }
.testi:nth-child(2) .testi-top { background: linear-gradient(90deg, var(--gold), var(--pink)); }
.testi:nth-child(3) .testi-top { background: linear-gradient(90deg, var(--green), var(--cyan)); }
.stars { font-size: 0.85rem; color: var(--gold); letter-spacing: 0.05em; margin-bottom: 1rem; }
.testi blockquote { font-size: 0.92rem; color: #cbd5e1; line-height: 1.75; font-style: italic; margin-bottom: 1.5rem; }
.testi-author { display: flex; align-items: center; gap: 0.9rem; }
.testi-av {
  width: 40px; height: 40px; border-radius: 50%;
  display: flex; align-items: center; justify-content: center;
  font-family: 'Syne', sans-serif; font-size: 1rem; font-weight: 800; color: #06080d;
}
.av1 { background: linear-gradient(135deg, var(--cyan), var(--cyan2)); }
.av2 { background: linear-gradient(135deg, var(--gold), var(--gold2)); }
.av3 { background: linear-gradient(135deg, var(--violet), #7c3aed); }
.author-name { font-size: 0.85rem; font-weight: 600; color: var(--white); }
.author-role { font-size: 0.73rem; color: var(--muted); margin-top: 0.15rem; }

/* ── CONTACT ── */
.contact-section {
  padding: 7rem 6%; background: var(--bg2);
  display: grid; grid-template-columns: 1fr 1fr; gap: 5rem; align-items: start;
}
.contact-left .section-tag { margin-bottom: 1.2rem; }
.contact-left p { color: var(--muted); font-size: 0.95rem; line-height: 1.75; margin: 1rem 0 2.5rem; }
.contact-items { display: flex; flex-direction: column; gap: 1.2rem; }
.ci { display: flex; align-items: flex-start; gap: 1rem; }
.ci-icon {
  width: 44px; height: 44px; border-radius: 10px;
  display: flex; align-items: center; justify-content: center;
  font-size: 1.1rem; flex-shrink: 0;
}
.ci-icon.c { background: rgba(34,211,238,0.1); border: 1px solid rgba(34,211,238,0.2); }
.ci-icon.g { background: rgba(245,158,11,0.1); border: 1px solid rgba(245,158,11,0.2); }
.ci-icon.v { background: rgba(167,139,250,0.1); border: 1px solid rgba(167,139,250,0.2); }
.ci-icon.p { background: rgba(52,211,153,0.1); border: 1px solid rgba(52,211,153,0.2); }
.ci-text strong { display: block; font-size: 0.82rem; font-weight: 600; color: var(--white); }
.ci-text span { font-size: 0.82rem; color: var(--muted); }
.contact-form-box {
  background: var(--card);
  border: 1px solid var(--border);
  border-radius: 20px; padding: 2.5rem;
  position: relative; overflow: hidden;
}
.contact-form-box::before {
  content: ''; position: absolute; top: 0; left: 0; right: 0; height: 3px;
  background: linear-gradient(90deg, var(--cyan), var(--violet), var(--gold));
}
.form-title { font-family: 'Syne', sans-serif; font-size: 1.2rem; font-weight: 700; color: var(--white); margin-bottom: 1.8rem; }
.form-row { display: grid; grid-template-columns: 1fr 1fr; gap: 1rem; }
.fg { display: flex; flex-direction: column; gap: 0.45rem; margin-bottom: 1rem; }
.fg label { font-size: 0.72rem; font-weight: 600; text-transform: uppercase; letter-spacing: 0.1em; color: var(--muted); }
.fg input, .fg select, .fg textarea {
  background: rgba(255,255,255,0.03);
  border: 1px solid var(--border);
  border-radius: 8px; padding: 0.8rem 1rem;
  color: var(--text); font-family: 'Plus Jakarta Sans', sans-serif;
  font-size: 0.88rem; outline: none;
  transition: border-color 0.3s, box-shadow 0.3s;
  resize: vertical;
}
.fg input:focus, .fg select:focus, .fg textarea:focus {
  border-color: var(--cyan);
  box-shadow: 0 0 0 3px rgba(34,211,238,0.1);
}
.fg select option { background: #111d2e; }
.form-submit {
  width: 100%; padding: 1rem;
  background: linear-gradient(135deg, var(--cyan), #0891b2);
  color: #06080d; font-size: 0.9rem; font-weight: 700;
  font-family: 'Plus Jakarta Sans', sans-serif;
  border: none; border-radius: 8px; cursor: pointer;
  letter-spacing: 0.04em; text-transform: uppercase;
  transition: all 0.3s; margin-top: 0.5rem;
}
.form-submit:hover { transform: translateY(-2px); box-shadow: 0 10px 25px rgba(34,211,238,0.35); }

/* ── FOOTER ── */
footer {
  background: var(--bg); border-top: 1px solid var(--border);
  padding: 2.5rem 6%;
  display: flex; justify-content: space-between; align-item