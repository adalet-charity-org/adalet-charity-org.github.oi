<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Adalet Charity Organisation</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,400;0,600;1,400&family=DM+Sans:wght@300;400;500&display=swap" rel="stylesheet">
<style>
*{margin:0;padding:0;box-sizing:border-box}
:root{
  --ink:#1a1a18;--ink2:#4a4a44;--ink3:#888880;
  --sand:#f5f0e8;--sand2:#ede8dc;
  --teal:#0f6e56;--teal2:#1d9e75;--teal-light:#e1f5ee;
  --gold:#ba7517;--gold-light:#faeeda;
  --white:#ffffff;--border:#d3d1c7;
}
html{scroll-behavior:smooth}
body{font-family:'DM Sans',sans-serif;background:var(--white);color:var(--ink);overflow-x:hidden}

/* NAV */
nav{position:fixed;top:0;left:0;right:0;z-index:100;background:rgba(255,255,255,0.95);backdrop-filter:blur(8px);border-bottom:1px solid var(--border);padding:0 2rem}
.nav-inner{max-width:1100px;margin:0 auto;display:flex;align-items:center;justify-content:space-between;height:64px}
.nav-logo{font-family:'Cormorant Garamond',serif;font-size:1.25rem;font-weight:600;color:var(--teal);letter-spacing:0.02em;text-decoration:none}
.nav-logo span{color:var(--gold)}
.nav-links{display:flex;gap:2rem;list-style:none}
.nav-links a{font-size:0.85rem;font-weight:400;color:var(--ink2);text-decoration:none;letter-spacing:0.05em;text-transform:uppercase;transition:color 0.2s}
.nav-links a:hover{color:var(--teal)}
.nav-cta{background:var(--teal);color:var(--white)!important;padding:0.5rem 1.25rem;border-radius:2px;font-weight:500!important}
.nav-cta:hover{background:#085041!important;color:var(--white)!important}

/* HERO */
.hero{padding:140px 2rem 100px;background:var(--sand);min-height:90vh;display:flex;align-items:center;position:relative;overflow:hidden}
.hero::before{content:'';position:absolute;top:-60px;right:-80px;width:500px;height:500px;border-radius:50%;background:var(--teal-light);opacity:0.5;z-index:0}
.hero::after{content:'';position:absolute;bottom:-100px;left:10%;width:300px;height:300px;border-radius:50%;background:var(--gold-light);opacity:0.4;z-index:0}
.hero-inner{max-width:1100px;margin:0 auto;display:grid;grid-template-columns:1fr 1fr;gap:4rem;align-items:center;position:relative;z-index:1}
.hero-tag{font-size:0.75rem;letter-spacing:0.15em;text-transform:uppercase;color:var(--teal);font-weight:500;margin-bottom:1.25rem;display:flex;align-items:center;gap:0.5rem}
.hero-tag::before{content:'';display:inline-block;width:24px;height:1px;background:var(--teal)}
.hero h1{font-family:'Cormorant Garamond',serif;font-size:clamp(2.6rem,5vw,4rem);font-weight:600;line-height:1.1;color:var(--ink);margin-bottom:1.5rem}
.hero h1 em{color:var(--teal);font-style:italic}
.hero p{font-size:1.05rem;line-height:1.75;color:var(--ink2);margin-bottom:2rem;max-width:480px}
.hero-btns{display:flex;gap:1rem;flex-wrap:wrap}
.btn-primary{background:var(--teal);color:var(--white);padding:0.85rem 2rem;border:none;font-family:'DM Sans',sans-serif;font-size:0.9rem;font-weight:500;cursor:pointer;border-radius:2px;text-decoration:none;display:inline-block;transition:background 0.2s}
.btn-primary:hover{background:#085041}
.btn-outline{background:transparent;color:var(--teal);padding:0.85rem 2rem;border:1.5px solid var(--teal);font-family:'DM Sans',sans-serif;font-size:0.9rem;font-weight:500;cursor:pointer;border-radius:2px;text-decoration:none;display:inline-block;transition:all 0.2s}
.btn-outline:hover{background:var(--teal);color:var(--white)}
.hero-stats{display:grid;grid-template-columns:1fr 1fr;gap:1.5rem}
.stat-card{background:var(--white);border:1px solid var(--border);border-radius:4px;padding:1.75rem 1.5rem;border-left:3px solid var(--teal)}
.stat-num{font-family:'Cormorant Garamond',serif;font-size:2.8rem;font-weight:600;color:var(--teal);line-height:1}
.stat-label{font-size:0.8rem;color:var(--ink2);margin-top:0.4rem;letter-spacing:0.05em;text-transform:uppercase}

/* SECTIONS */
section{padding:90px 2rem}
.section-inner{max-width:1100px;margin:0 auto}
.section-tag{font-size:0.72rem;letter-spacing:0.18em;text-transform:uppercase;color:var(--teal);font-weight:500;margin-bottom:0.75rem}
.section-title{font-family:'Cormorant Garamond',serif;font-size:clamp(2rem,3.5vw,2.8rem);font-weight:600;color:var(--ink);margin-bottom:1rem;line-height:1.2}
.section-sub{font-size:1rem;color:var(--ink2);line-height:1.7;max-width:580px}
.divider{width:40px;height:2px;background:var(--gold);margin:1.25rem 0 2.5rem}

/* ABOUT */
.about{background:var(--white)}
.about-grid{display:grid;grid-template-columns:1fr 1fr;gap:5rem;align-items:start;margin-top:3rem}
.about-text p{font-size:1rem;line-height:1.8;color:var(--ink2);margin-bottom:1.25rem}
.about-pillars{display:flex;flex-direction:column;gap:1rem}
.pillar{display:flex;gap:1rem;align-items:flex-start;padding:1.25rem;border:1px solid var(--border);border-radius:4px;transition:border-color 0.2s}
.pillar:hover{border-color:var(--teal)}
.pillar-icon{width:40px;height:40px;background:var(--teal-light);border-radius:50%;display:flex;align-items:center;justify-content:center;flex-shrink:0;font-size:1.1rem}
.pillar h4{font-size:0.95rem;font-weight:500;color:var(--ink);margin-bottom:0.25rem}
.pillar p{font-size:0.85rem;color:var(--ink2);line-height:1.6}

/* PROJECTS */
.projects{background:var(--sand)}
.projects-header{display:flex;justify-content:space-between;align-items:flex-end;margin-bottom:3rem;flex-wrap:wrap;gap:1rem}
.project-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:1.5rem}
.project-card{background:var(--white);border:1px solid var(--border);border-radius:4px;overflow:hidden;transition:transform 0.2s,box-shadow 0.2s}
.project-card:hover{transform:translateY(-4px);box-shadow:0 12px 32px rgba(15,110,86,0.1)}
.project-card-img{height:160px;display:flex;align-items:center;justify-content:center;font-size:2.5rem}
.water{background:linear-gradient(135deg,#e1f5ee,#9fe1cb)}
.sadaqah{background:linear-gradient(135deg,#faeeda,#fac775)}
.food{background:linear-gradient(135deg,#fbeaf0,#f4c0d1)}
.kurban{background:linear-gradient(135deg,#e6f1fb,#b5d4f4)}
.madrasa{background:linear-gradient(135deg,#eaf3de,#c0dd97)}
.ramadan{background:linear-gradient(135deg,#faeeda,#ef9f27)}
.project-card-body{padding:1.5rem}
.project-card-tag{font-size:0.7rem;letter-spacing:0.12em;text-transform:uppercase;color:var(--teal);font-weight:500;margin-bottom:0.5rem}
.project-card h3{font-family:'Cormorant Garamond',serif;font-size:1.35rem;font-weight:600;color:var(--ink);margin-bottom:0.5rem}
.project-card p{font-size:0.85rem;color:var(--ink2);line-height:1.65}
.project-count{font-size:0.75rem;color:var(--teal);font-weight:500;margin-top:0.75rem}

/* IMPACT */
.impact{background:var(--teal)}
.impact .section-tag{color:rgba(255,255,255,0.65)}
.impact .section-title{color:var(--white)}
.impact .section-sub{color:rgba(255,255,255,0.75)}
.impact .divider{background:var(--gold-light)}
.impact-grid{display:grid;grid-template-columns:repeat(4,1fr);gap:2rem;margin-top:3rem}
.impact-num{font-family:'Cormorant Garamond',serif;font-size:3.5rem;font-weight:600;color:var(--white);line-height:1}
.impact-unit{font-size:1.5rem;color:rgba(255,255,255,0.6)}
.impact-label{font-size:0.8rem;color:rgba(255,255,255,0.65);margin-top:0.5rem;letter-spacing:0.05em;text-transform:uppercase;line-height:1.4}
.impact-sep{width:1px;background:rgba(255,255,255,0.15)}

/* MISSION VISION */
.mv{background:var(--white)}
.mv-grid{display:grid;grid-template-columns:1fr 1fr;gap:2rem;margin-top:2.5rem}
.mv-card{padding:2.5rem;border:1px solid var(--border);border-radius:4px;border-top:3px solid}
.mv-card.mission{border-top-color:var(--teal)}
.mv-card.vision{border-top-color:var(--gold)}
.mv-card h3{font-family:'Cormorant Garamond',serif;font-size:1.6rem;font-weight:600;color:var(--ink);margin-bottom:1rem}
.mv-card p{font-size:0.95rem;color:var(--ink2);line-height:1.8}

/* WHO WE ARE */
.who{background:var(--sand)}
.who-grid{display:grid;grid-template-columns:1fr 1fr;gap:5rem;align-items:center;margin-top:3rem}
.who-img{background:var(--teal-light);border-radius:4px;height:420px;display:flex;align-items:center;justify-content:center;font-size:5rem;position:relative;overflow:hidden}
.who-img::after{content:"Ghana's Western Region";position:absolute;bottom:1rem;left:1rem;right:1rem;background:rgba(15,110,86,0.85);color:white;font-size:0.8rem;padding:0.6rem 1rem;border-radius:2px;letter-spacing:0.05em;text-transform:uppercase}
.who-text p{font-size:1rem;line-height:1.8;color:var(--ink2);margin-bottom:1.25rem}
.who-highlights{display:grid;grid-template-columns:1fr 1fr;gap:0.75rem;margin-top:1.5rem}
.highlight{background:var(--white);border:1px solid var(--border);border-radius:2px;padding:0.9rem 1rem;font-size:0.82rem;color:var(--ink2);line-height:1.5}
.highlight strong{display:block;color:var(--ink);font-weight:500;margin-bottom:0.2rem}

/* DONATE */
.donate{background:var(--sand)}
.donate-inner{max-width:1100px;margin:0 auto}
.donate-grid{display:grid;grid-template-columns:1fr 1fr;gap:4rem;align-items:start;margin-top:3rem}
.donate-why p{font-size:1rem;line-height:1.8;color:var(--ink2);margin-bottom:1.25rem}
.donate-why ul{list-style:none;display:flex;flex-direction:column;gap:0.75rem;margin-top:0.5rem}
.donate-why li{display:flex;gap:0.75rem;align-items:flex-start;font-size:0.9rem;color:var(--ink2);line-height:1.6}
.donate-why li::before{content:'✓';color:var(--teal);font-weight:500;flex-shrink:0;margin-top:0.05rem}
.bank-card{background:var(--ink);border-radius:6px;overflow:hidden;box-shadow:0 20px 48px rgba(15,110,86,0.15)}
.bank-card-header{background:var(--teal);padding:1.5rem 2rem;display:flex;align-items:center;gap:1rem}
.bank-logo{width:44px;height:44px;background:rgba(255,255,255,0.15);border-radius:50%;display:flex;align-items:center;justify-content:center;font-size:1.2rem;flex-shrink:0}
.bank-card-header-text strong{display:block;color:var(--white);font-size:1rem;font-weight:500}
.bank-card-header-text span{color:rgba(255,255,255,0.65);font-size:0.8rem}
.bank-card-body{padding:0 2rem 2rem}
.bank-row{display:flex;justify-content:space-between;align-items:center;padding:1rem 0;border-bottom:1px solid rgba(255,255,255,0.07)}
.bank-row:last-child{border-bottom:none}
.bank-row-label{font-size:0.72rem;letter-spacing:0.1em;text-transform:uppercase;color:rgba(255,255,255,0.4)}
.bank-row-value{font-size:0.92rem;color:rgba(255,255,255,0.88);font-weight:400;text-align:right;display:flex;align-items:center;gap:0.5rem}
.bank-row-value.mono{font-family:monospace;font-size:1rem;letter-spacing:0.05em;color:var(--white)}
.copy-btn{background:rgba(255,255,255,0.08);border:none;border-radius:2px;padding:0.25rem 0.6rem;font-size:0.7rem;color:rgba(255,255,255,0.5);cursor:pointer;transition:all 0.2s;font-family:'DM Sans',sans-serif}
.copy-btn:hover{background:rgba(29,158,117,0.3);color:var(--teal2)}
.copy-btn.copied{background:rgba(29,158,117,0.2);color:var(--teal2)}
.bank-card-note{background:rgba(29,158,117,0.12);border-left:2px solid var(--teal2);margin:0 2rem 2rem;padding:0.85rem 1rem;border-radius:0 2px 2px 0}
.bank-card-note p{font-size:0.8rem;color:rgba(255,255,255,0.55);line-height:1.6}
.bank-card-note strong{color:rgba(255,255,255,0.75)}

/* CONTACT */
.contact{background:var(--ink)}
.contact .section-tag{color:var(--teal2)}
.contact .section-title{color:var(--white)}
.contact .section-sub{color:rgba(255,255,255,0.6)}
.contact .divider{background:var(--gold)}
.contact-grid{display:grid;grid-template-columns:1fr 1fr;gap:5rem;margin-top:3rem;align-items:start}
.contact-details{display:flex;flex-direction:column;gap:1.5rem}
.contact-item{display:flex;gap:1rem;align-items:flex-start}
.contact-icon{width:36px;height:36px;border:1px solid rgba(255,255,255,0.15);border-radius:50%;display:flex;align-items:center;justify-content:center;flex-shrink:0;font-size:0.9rem}
.contact-item-text strong{display:block;font-size:0.75rem;letter-spacing:0.1em;text-transform:uppercase;color:rgba(255,255,255,0.4);margin-bottom:0.25rem}
.contact-item-text span{color:rgba(255,255,255,0.85);font-size:0.95rem;line-height:1.5}
.contact-form{display:flex;flex-direction:column;gap:1rem}
.contact-form input,.contact-form textarea{background:rgba(255,255,255,0.06);border:1px solid rgba(255,255,255,0.15);border-radius:2px;padding:0.85rem 1rem;font-family:'DM Sans',sans-serif;font-size:0.9rem;color:var(--white);outline:none;transition:border-color 0.2s;width:100%}
.contact-form input::placeholder,.contact-form textarea::placeholder{color:rgba(255,255,255,0.3)}
.contact-form input:focus,.contact-form textarea:focus{border-color:var(--teal2)}
.contact-form textarea{height:120px;resize:vertical}
.contact-form button{background:var(--teal);color:var(--white);border:none;padding:0.9rem 2rem;font-family:'DM Sans',sans-serif;font-size:0.9rem;font-weight:500;cursor:pointer;border-radius:2px;transition:background 0.2s;align-self:flex-start}
.contact-form button:hover{background:var(--teal2)}

/* FOOTER */
footer{background:#0f0f0d;padding:2.5rem 2rem;text-align:center;border-top:1px solid rgba(255,255,255,0.06)}
footer p{font-size:0.8rem;color:rgba(255,255,255,0.3);line-height:1.7}
footer a{color:var(--teal2);text-decoration:none}

/* ANIMATIONS */
.fade-up{opacity:0;transform:translateY(24px);transition:opacity 0.7s ease,transform 0.7s ease}
.fade-up.visible{opacity:1;transform:none}

/* RESPONSIVE */
@media(max-width:768px){
  .hero-inner,.about-grid,.who-grid,.donate-grid,.contact-grid,.mv-grid{grid-template-columns:1fr;gap:2.5rem}
  .project-grid{grid-template-columns:1fr}
  .impact-grid{grid-template-columns:1fr 1fr}
  .impact-sep{display:none}
  .nav-links{display:none}
  .hero{padding:100px 1.5rem 60px;min-height:auto}
  section{padding:60px 1.5rem}
}
</style>
</head>
<body>

<!-- NAVIGATION -->
<nav>
  <div class="nav-inner">
    <a href="#home" class="nav-logo">Adalet <span>Charity</span></a>
    <ul class="nav-links">
      <li><a href="#about">About</a></li>
      <li><a href="#projects">Projects</a></li>
      <li><a href="#impact">Impact</a></li>
      <li><a href="#donate">Donate</a></li>
      <li><a href="#contact">Contact</a></li>
      <li><a href="#donate" class="nav-cta">Give Now</a></li>
    </ul>
  </div>
</nav>

<!-- HERO -->
<section class="hero" id="home">
  <div class="hero-inner">
    <div>
      <div class="hero-tag">Nkroful, Western Region &middot; Ghana</div>
      <h1>Serving the <em>Unseen</em><br>Communities of Ghana</h1>
      <p>Adalet Charity Organisation brings clean water, food security, and educational support to rural communities in Ghana's Western Region — the people that larger organisations too often miss.</p>
      <div class="hero-btns">
        <a href="#donate" class="btn-primary">Donate Now</a>
        <a href="#projects" class="btn-outline">Our Projects</a>
      </div>
    </div>
    <div class="hero-stats">
      <div class="stat-card"><div class="stat-num">5+</div><div class="stat-label">Borehole Wells Constructed</div></div>
      <div class="stat-card"><div class="stat-num">100s</div><div class="stat-label">Families Reached Each Year</div></div>
      <div class="stat-card"><div class="stat-num">4</div><div class="stat-label">Active Programme Areas</div></div>
      <div class="stat-card"><div class="stat-num">WR</div><div class="stat-label">Western Region, Ghana Focus</div></div>
    </div>
  </div>
</section>

<!-- ABOUT -->
<section class="about" id="about">
  <div class="section-inner">
    <div class="section-tag">Who We Are</div>
    <h2 class="section-title">A Charity Born From<br>a Gap in Coverage</h2>
    <div class="divider"></div>
    <div class="about-grid fade-up">
      <div class="about-text">
        <p>Adalet Charity Organisation was founded with a clear observation: the vast majority of NGOs operating in Ghana concentrate their efforts in major cities, leaving rural populations — including orphans, widows, and the economically marginalised — without access to basic services.</p>
        <p>We are based in Nkroful, Western Region, and operate at the grassroots level. Our name, "Adalet" — meaning <em>justice</em> — reflects our founding conviction that every person, regardless of where they live, deserves access to clean water, food, and education.</p>
        <p>Through partnerships with international donors and a commitment to transparency, we execute projects that create lasting, generational impact in the communities we serve.</p>
      </div>
      <div class="about-pillars">
        <div class="pillar">
          <div class="pillar-icon">💧</div>
          <div><h4>Clean Water Access</h4><p>We construct solar-powered borehole wells in communities without reliable water infrastructure, improving health and freeing women and children from long daily walks.</p></div>
        </div>
        <div class="pillar">
          <div class="pillar-icon">🌙</div>
          <div><h4>Food Security</h4><p>During Ramadan and Eid ul-Adha, we distribute essential food packages and facilitate sacrificial programmes to ensure no family goes without during sacred seasons.</p></div>
        </div>
        <div class="pillar">
          <div class="pillar-icon">📖</div>
          <div><h4>Education &amp; Faith</h4><p>Our Madrasa Programme provides religious education and our renovation works restore community learning spaces, giving children access to quality instruction.</p></div>
        </div>
        <div class="pillar">
          <div class="pillar-icon">🤝</div>
          <div><h4>Sadaqatul Jariyah</h4><p>Every project we execute is structured as a continuous charity — benefits that outlive the initial investment and compound over generations for the community.</p></div>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- PROJECTS -->
<section class="projects" id="projects">
  <div class="section-inner">
    <div class="projects-header">
      <div>
        <div class="section-tag">What We Do</div>
        <h2 class="section-title">Our Programmes</h2>
        <div class="divider"></div>
      </div>
      <a href="#donate" class="btn-outline">Fund a Project</a>
    </div>
    <div class="project-grid fade-up">
      <div class="project-card">
        <div class="project-card-img water">💧</div>
        <div class="project-card-body">
          <div class="project-card-tag">Water &amp; Sanitation</div>
          <h3>Borehole Water Wells</h3>
          <p>We construct hand-pump and solar-powered borehole wells providing year-round clean water to rural villages. Each well is named in honour of the donor family.</p>
          <div class="project-count">&#10003; 5 Wells Completed &mdash; Ecdad-&#305; Osman, Abdurrahman, Abdullah I &amp; II, &#350;ehitler</div>
        </div>
      </div>
      <div class="project-card">
        <div class="project-card-img sadaqah">🕌</div>
        <div class="project-card-body">
          <div class="project-card-tag">Continuous Charity</div>
          <h3>Sadaqatul Jariyah</h3>
          <p>Ongoing charity projects including facility renovation works and community infrastructure that generate rewards for donors and benefit the community indefinitely.</p>
          <div class="project-count">&#10003; Renovation Works &middot; Community Spaces</div>
        </div>
      </div>
      <div class="project-card">
        <div class="project-card-img madrasa">📖</div>
        <div class="project-card-body">
          <div class="project-card-tag">Education</div>
          <h3>Madrasa Programme</h3>
          <p>Supporting Islamic education in underserved rural communities, providing structured learning for children who would otherwise have no access to faith-based schooling.</p>
          <div class="project-count">&#10003; Active in Western Region Communities</div>
        </div>
      </div>
      <div class="project-card">
        <div class="project-card-img ramadan">🌙</div>
        <div class="project-card-body">
          <div class="project-card-tag">Food Security</div>
          <h3>Ramadan Programmes</h3>
          <p>Each Ramadan, we distribute food packages to families in need, ensuring they can observe the sacred month with dignity and sustenance.</p>
          <div class="project-count">&#10003; Annual Distribution &mdash; Western Region</div>
        </div>
      </div>
      <div class="project-card">
        <div class="project-card-img kurban">🐄</div>
        <div class="project-card-body">
          <div class="project-card-tag">Eid ul-Adha</div>
          <h3>Kurban Programme</h3>
          <p>Facilitating the sacrifice of livestock during Eid ul-Adha and distributing meat to households who would otherwise not have access during the holiday.</p>
          <div class="project-count">&#10003; Annual Programme &mdash; Community Wide</div>
        </div>
      </div>
      <div class="project-card">
        <div class="project-card-img food">🏗️</div>
        <div class="project-card-body">
          <div class="project-card-tag">Infrastructure</div>
          <h3>Community Renovation</h3>
          <p>Restoring and upgrading community facilities including mosques and learning centres to create better, safer spaces for worship, learning, and communal activity.</p>
          <div class="project-count">&#10003; Multiple Sites Restored</div>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- IMPACT -->
<section class="impact" id="impact">
  <div class="section-inner">
    <div class="section-tag">Our Reach</div>
    <h2 class="section-title">Impact By the Numbers</h2>
    <div class="divider"></div>
    <p class="section-sub">Every figure represents a real community, a real family, and a life made measurably better through the generosity of our donors and the dedication of our team on the ground.</p>
    <div class="impact-grid fade-up">
      <div><div class="impact-num">5<span class="impact-unit">+</span></div><div class="impact-label">Borehole Wells<br>Constructed</div></div>
      <div class="impact-sep"></div>
      <div><div class="impact-num">100s</div><div class="impact-label">Families Served<br>Annually</div></div>
      <div class="impact-sep"></div>
      <div><div class="impact-num">6</div><div class="impact-label">Programme Types<br>Running</div></div>
      <div class="impact-sep"></div>
      <div><div class="impact-num">WR</div><div class="impact-label">Western Region<br>Focus Area</div></div>
    </div>
  </div>
</section>

<!-- MISSION & VISION -->
<section class="mv">
  <div class="section-inner">
    <div class="section-tag">Guiding Principles</div>
    <h2 class="section-title">Mission &amp; Vision</h2>
    <div class="divider"></div>
    <div class="mv-grid fade-up">
      <div class="mv-card mission">
        <h3>Our Mission</h3>
        <p>To foster sustainable development in rural Ghana by providing underserved communities with access to clean water, nutritional support, and educational resources &mdash; with a particular focus on orphans, widows, and those marginalised by economic hardship.</p>
        <br>
        <p>We achieve this through borehole construction, seasonal food distribution, Islamic education programmes, and community infrastructure projects, all delivered with transparency and care.</p>
      </div>
      <div class="mv-card vision">
        <h3>Our Vision</h3>
        <p>A Ghana where no rural community is invisible &mdash; where every village has clean water to drink, every child has a place to learn, and every family can observe sacred seasons with dignity and abundance.</p>
        <br>
        <p>We envision Adalet Charity as a trusted bridge between generous donors around the world and the communities in Ghana's Western Region who need them most.</p>
      </div>
    </div>
  </div>
</section>

<!-- WHO WE ARE -->
<section class="who">
  <div class="section-inner">
    <div class="who-grid fade-up">
      <div class="who-img">🇬🇭</div>
      <div>
        <div class="section-tag">Our Story</div>
        <h2 class="section-title">Rooted in the<br>Community We Serve</h2>
        <div class="divider"></div>
        <div class="who-text">
          <p>Adalet Charity Organisation was founded in Nkroful, Ghana's Western Region, with a mission driven by firsthand knowledge of rural neglect. While urban centres were well-served by established charities, rural villages and their vulnerable populations were consistently overlooked.</p>
          <p>We are a registered NGO headquartered at Essiama Tarkwa Road, P.O. Box 10, Nkroful. Our team operates on the ground in the communities we serve, ensuring accountability and genuine impact.</p>
        </div>
        <div class="who-highlights">
          <div class="highlight"><strong>Location</strong>Nkroful, Western Region, Ghana</div>
          <div class="highlight"><strong>Language</strong>English &middot; Turkish &middot; French</div>
          <div class="highlight"><strong>Focus</strong>Rural underserved communities</div>
          <div class="highlight"><strong>Approach</strong>Sadaqatul Jariyah model</div>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- DONATE -->
<section class="donate" id="donate">
  <div class="donate-inner">
    <div class="section-tag">Support Our Work</div>
    <h2 class="section-title">Make a Direct Donation</h2>
    <div class="divider"></div>
    <p class="section-sub">Your contribution funds clean water, food relief, and education for rural communities in Ghana. Every dollar is accounted for and delivered with care.</p>
    <div class="donate-grid fade-up">
      <div class="donate-why">
        <p>We accept international bank transfers directly to our verified CAL Bank account in Ghana. All donations are acknowledged and you will receive a record of how your funds are deployed.</p>
        <p>You may designate your donation to a specific programme &mdash; a named water well, a Ramadan food package, a Madrasa scholarship &mdash; and we will honour that designation.</p>
        <ul>
          <li>Name a borehole well after a loved one (Sadaqatul Jariyah)</li>
          <li>Sponsor a full Ramadan food distribution</li>
          <li>Fund a child's Madrasa education for a year</li>
          <li>Contribute to a community renovation project</li>
          <li>Support our Kurban (Eid ul-Adha) meat programme</li>
        </ul>
        <p style="margin-top:1.5rem;font-size:0.85rem;color:var(--ink3)">After transferring, please send your name and reference to <strong style="color:var(--teal)">adaletcharityorg@gmail.com</strong> or WhatsApp <strong style="color:var(--teal)">+233 555 819 061</strong> so we can acknowledge your gift.</p>
      </div>
      <div>
        <div class="bank-card">
          <div class="bank-card-header">
            <div class="bank-logo">🏦</div>
            <div class="bank-card-header-text">
              <strong>CAL Bank &mdash; Essiama Branch</strong>
              <span>International Wire Transfer &middot; USD Account</span>
            </div>
          </div>
          <div class="bank-card-body">
            <div class="bank-row">
              <span class="bank-row-label">Account Name</span>
              <span class="bank-row-value">ADALET CHARITY ORGANISATION LBG</span>
            </div>
            <div class="bank-row">
              <span class="bank-row-label">Account Number</span>
              <span class="bank-row-value mono">1400006724894 <button class="copy-btn" onclick="copyField('1400006724894','acc-btn')" id="acc-btn">Copy</button></span>
            </div>
            <div class="bank-row">
              <span class="bank-row-label">SWIFT / BIC Code</span>
              <span class="bank-row-value mono">ACCCGHACXXX <button class="copy-btn" onclick="copyField('ACCCGHACXXX','swift-btn')" id="swift-btn">Copy</button></span>
            </div>
            <div class="bank-row">
              <span class="bank-row-label">Bank Name</span>
              <span class="bank-row-value">CAL Bank Limited</span>
            </div>
            <div class="bank-row">
              <span class="bank-row-label">Branch</span>
              <span class="bank-row-value">Essiama Branch, Ghana</span>
            </div>
            <div class="bank-row">
              <span class="bank-row-label">Currency</span>
              <span class="bank-row-value" style="color:#ef9f27;font-weight:500">USD &mdash; United States Dollar</span>
            </div>
          </div>
          <div class="bank-card-note">
            <p><strong>Reference your transfer:</strong> Please include your name and the programme you wish to support (e.g. "Water Well &mdash; [Your Name]") in the transfer reference field.</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- CONTACT -->
<section class="contact" id="contact">
  <div class="section-inner">
    <div class="section-tag">Get In Touch</div>
    <h2 class="section-title">Partner With Us</h2>
    <div class="divider"></div>
    <p class="section-sub">Whether you wish to fund a water well, sponsor a Ramadan programme, or simply learn more about our work, we welcome your message.</p>
    <div class="contact-grid fade-up">
      <div class="contact-details">
        <div class="contact-item">
          <div class="contact-icon">📞</div>
          <div class="contact-item-text"><strong>Mobile / WhatsApp</strong><span>+233 555 819 061</span></div>
        </div>
        <div class="contact-item">
          <div class="contact-icon">✉️</div>
          <div class="contact-item-text"><strong>Email</strong><span>adaletcharityorg@gmail.com</span></div>
        </div>
        <div class="contact-item">
          <div class="contact-icon">📍</div>
          <div class="contact-item-text"><strong>Address</strong><span>Essiama Tarkwa Road<br>P.O. Box 10, Nkroful<br>Western Region, Ghana</span></div>
        </div>
        <div class="contact-item">
          <div class="contact-icon">🌐</div>
          <div class="contact-item-text"><strong>Languages</strong><span>English &middot; Turkish (TR) &middot; French (FR)</span></div>
        </div>
      </div>
      <form class="contact-form" onsubmit="handleSubmit(event)">
        <input type="text" placeholder="Your Full Name" required>
        <input type="email" placeholder="Email Address" required>
        <input type="text" placeholder="Subject (e.g. Water Well Sponsorship)">
        <textarea placeholder="Your message..."></textarea>
        <button type="submit">Send Message &rarr;</button>
      </form>
    </div>
  </div>
</section>

<!-- FOOTER -->
<footer>
  <p>
    &copy; 2025 Adalet Charity Organisation &middot; Nkroful, Western Region, Ghana<br>
    <a href="mailto:adaletcharityorg@gmail.com">adaletcharityorg@gmail.com</a> &middot; +233 555 819 061<br>
    <em style="color:rgba(255,255,255,0.2);font-size:0.75rem">Serving those who are unseen, in the name of justice &mdash; &#1593;&#1583;&#1575;&#1604;&#1578;</em>
  </p>
</footer>

<script>
  document.querySelectorAll('a[href^="#"]').forEach(a => {
    a.addEventListener('click', e => {
      e.preventDefault();
      const target = document.querySelector(a.getAttribute('href'));
      if (target) target.scrollIntoView({ behavior: 'smooth' });
    });
  });

  const observer = new IntersectionObserver(entries => {
    entries.forEach(e => { if (e.isIntersecting) e.target.classList.add('visible'); });
  }, { threshold: 0.1 });
  document.querySelectorAll('.fade-up').forEach(el => observer.observe(el));

  function handleSubmit(e) {
    e.preventDefault();
    const btn = e.target.querySelector('button');
    btn.textContent = 'Message Sent \u2713';
    btn.style.background = '#085041';
    setTimeout(() => { btn.textContent = 'Send Message \u2192'; btn.style.background = ''; e.target.reset(); }, 3000);
  }

  function copyField(text, btnId) {
    navigator.clipboard.writeText(text).then(() => {
      const btn = document.getElementById(btnId);
      btn.textContent = 'Copied!';
      btn.classList.add('copied');
      setTimeout(() => { btn.textContent = 'Copy'; btn.classList.remove('copied'); }, 2000);
    });
  }
</script>
</body>
</html>
