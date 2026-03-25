<template>
  <div class="site">

    <!-- ─── NAV ─── -->
    <nav class="nav" :class="{ scrolled: navScrolled }">
      <div class="nav-inner">
        <a href="#hero" class="nav-logo">
          <span class="logo-c">C</span><span class="logo-dash">-</span><span class="logo-team">TEAM</span>
          <span class="logo-media">MEDIA</span>
        </a>
        <ul class="nav-links">
          <li><a href="#about">About</a></li>
          <li><a href="#services">Services</a></li>
          <li><a href="#gallery">Gallery</a></li>
          <li><a href="#clients">Clients</a></li>
          <li><a href="#contact" class="nav-cta">Get Quote</a></li>
        </ul>
        <button class="hamburger" @click="menuOpen = !menuOpen" :class="{ open: menuOpen }">
          <span></span><span></span><span></span>
        </button>
      </div>
      <div class="mobile-menu" :class="{ open: menuOpen }">
        <a href="#about"    @click="menuOpen=false">About</a>
        <a href="#services" @click="menuOpen=false">Services</a>
        <a href="#gallery"  @click="menuOpen=false">Gallery</a>
        <a href="#clients"  @click="menuOpen=false">Clients</a>
        <a href="#contact"  @click="menuOpen=false">Get Quote</a>
      </div>
    </nav>

    <!-- ─── HERO ─── -->
    <section id="hero" class="hero">
      <div class="hero-bg">
        <!-- PHOTO SLOT: hero-bg-img — replace src with generated image -->
        <!-- PROMPT: Dramatic wide-angle night photograph of a busy South Indian commercial street (Coimbatore style) with multiple glowing LED and flex signboards in red and white, motion blur of traffic, cinematic lighting, 16:9, photorealistic -->
        <img class="hero-bg-img" src="assets/hero.png" alt="C-Team Media signage" />
        <div class="hero-overlay"></div>
        <div class="hero-grid-lines"></div>
      </div>
      <div class="hero-content">
        <p class="hero-eyebrow reveal">Est. 1999 &nbsp;·&nbsp; Coimbatore, Tamil Nadu</p>
        <h1 class="hero-title reveal">
          <span class="title-line">THE WORLD</span>
          <span class="title-line accent">OF ADVERTISING</span>
        </h1>
        <p class="hero-sub reveal">The Complete Signage Solution &amp; Event Organiser</p>
        <div class="hero-actions reveal">
          <a href="#services" class="btn-primary">Explore Services</a>
          <a href="#contact"  class="btn-outline">Contact Us</a>
        </div>
      </div>
      <div class="hero-scroll-hint">
        <span class="scroll-line"></span>
        <span class="scroll-label">scroll</span>
      </div>
    </section>

    <!-- ─── STATS TICKER ─── -->
    <div class="stats-ticker">
      <div class="ticker-inner">
        <div class="stat" v-for="s in stats" :key="s.label">
          <span class="stat-num">{{ s.value }}</span>
          <span class="stat-label">{{ s.label }}</span>
        </div>
        <div class="ticker-divider" v-for="n in 3" :key="'d'+n">★</div>
        <div class="stat" v-for="s in stats" :key="'r'+s.label">
          <span class="stat-num">{{ s.value }}</span>
          <span class="stat-label">{{ s.label }}</span>
        </div>
      </div>
    </div>

    <!-- ─── ABOUT ─── -->
    <section id="about" class="about section-pad">
      <div class="container about-grid">
        <div class="about-media reveal-left">
          <!-- PHOTO SLOT: about-office -->
          <!-- PROMPT: Modern corporate office interior with "C-TEAM MEDIA – The World of Advertising" signage on a dark feature wall, stone-textured accent wall, professional lighting, warm tones, editorial magazine style, no people -->
          <div class="about-img-wrap">
            <div class="about-img-placeholder">
              <span class="placeholder-label">Office Photo</span>
              <span class="placeholder-hint">Replace with office interior photo</span>
            </div>
            <div class="about-badge">
              <span class="badge-num">25<sup>+</sup></span>
              <span class="badge-text">Years of Excellence</span>
            </div>
          </div>
        </div>
        <div class="about-text reveal-right">
          <span class="section-tag">About Us</span>
          <h2 class="section-title">Shaping Your<br><em>Idea</em> into Reality</h2>
          <p class="about-body">
            Founded in 1999 as <strong>Digital World</strong>, we pioneered screen printing and outdoor
            advertising across South India. Our sister concern <strong>C-Team Media</strong> expanded
            the vision into a large-scale signage powerhouse — with a team of <strong>60+ professionals</strong>
            under two dedicated managers, delivering impactful branding across Tamil Nadu, Kerala and Karnataka.
          </p>
          <ul class="about-pillars">
            <li v-for="p in pillars" :key="p.icon">
              <span class="pillar-icon">{{ p.icon }}</span>
              <span>{{ p.text }}</span>
            </li>
          </ul>
          <a href="#contact" class="btn-primary">Work With Us</a>
        </div>
      </div>
    </section>

    <!-- ─── SERVICES ─── -->
    <section id="services" class="services section-pad">
      <div class="container">
        <div class="section-head reveal">
          <span class="section-tag">What We Do</span>
          <h2 class="section-title">Complete Range of<br><em>Signage Products</em></h2>
        </div>
        <div class="services-grid">
          <div class="service-card reveal" v-for="(s, i) in services" :key="s.title"
               :style="{ '--delay': i * 60 + 'ms' }">
            <div class="service-icon">{{ s.icon }}</div>
            <h3>{{ s.title }}</h3>
            <p>{{ s.desc }}</p>
            <div class="service-hover-line"></div>
          </div>
        </div>
      </div>
    </section>

    <!-- ─── PRODUCTION CAPACITY BAND ─── -->
    <div class="capacity-band">
      <div class="capacity-inner">
        <div class="cap-item">
          <strong>250</strong> Front-Lit Boards / Day
        </div>
        <div class="cap-sep">|</div>
        <div class="cap-item">
          <strong>100</strong> Back-Lit Boards / Day
        </div>
        <div class="cap-sep">|</div>
        <div class="cap-item">
          <strong>10,000 Sqft</strong> Digital Print / Day
        </div>
        <div class="cap-sep">|</div>
        <div class="cap-item">Operations across <strong>3 States</strong>
        </div>
      </div>
    </div>

    <!-- ─── GALLERY ─── -->
    <section id="gallery" class="gallery-section section-pad">
      <div class="container">
        <div class="section-head reveal">
          <span class="section-tag">Our Work</span>
          <h2 class="section-title">Projects &amp;<br><em>Portfolio</em></h2>
        </div>

        <!-- Filter Tabs -->
        <div class="gallery-filters reveal">
          <button
            v-for="f in galleryFilters"
            :key="f"
            class="filter-btn"
            :class="{ active: activeFilter === f }"
            @click="activeFilter = f">
            {{ f }}
          </button>
        </div>

        <!-- Gallery Grid -->
        <div class="gallery-grid">
          <div
            class="gallery-item reveal"
            v-for="(item, i) in filteredGallery"
            :key="item.id"
            :class="item.size"
            :style="{ '--delay': (i % 6) * 80 + 'ms' }"
            @click="openLightbox(item)">
            <div class="gallery-img-wrap">
              <!-- PHOTO SLOT: each gallery item -->
              <div class="gallery-placeholder">
                <span class="gp-num">{{ String(i+1).padStart(2,'0') }}</span>
                <span class="gp-label">{{ item.label }}</span>
                <span class="gp-hint">{{ item.prompt }}</span>
              </div>
              <div class="gallery-overlay">
                <span class="gallery-view-icon">+</span>
                <span class="gallery-cat">{{ item.cat }}</span>
                <p class="gallery-caption">{{ item.label }}</p>
              </div>
            </div>
          </div>
        </div>
      </div>

      <!-- Lightbox -->
      <Transition name="fade">
        <div class="lightbox" v-if="lightboxItem" @click.self="lightboxItem = null">
          <button class="lb-close" @click="lightboxItem = null">✕</button>
          <div class="lb-content">
            <div class="lb-img-wrap">
              <div class="lb-placeholder">
                <span>{{ lightboxItem.label }}</span>
              </div>
            </div>
            <div class="lb-meta">
              <span class="lb-cat">{{ lightboxItem.cat }}</span>
              <h3>{{ lightboxItem.label }}</h3>
              <p>{{ lightboxItem.prompt }}</p>
            </div>
          </div>
        </div>
      </Transition>
    </section>

    <!-- ─── VIDEO SECTION ─── -->
    <section class="video-section section-pad">
      <div class="container">
        <div class="section-head reveal">
          <span class="section-tag">In Action</span>
          <h2 class="section-title">See How We<br><em>Bring Ideas to Life</em></h2>
        </div>
        <div class="video-grid">
          <div class="video-card reveal primary-video">
            <!-- VIDEO SLOT 1: Brand Reel -->
            <!-- PROMPT: 30-second corporate brand reel for C-Team Media. Opens with timelapse of a massive glow sign board being installed on a building facade at dusk. Cut to printing machines in action (ALLWIN Flex Machine). Cut to 3D letter fabrication in workshop. Cut to completed illuminated signboard glowing at night. End with C-Team Media logo reveal on red background. Cinematic, bold music, red/dark color grade. -->
            <div class="video-placeholder">
              <div class="play-btn">▶</div>
              <div class="video-meta">
                <span class="vid-tag">Brand Reel · 0:30</span>
                <h3>The World of Advertising</h3>
                <p>Replace with: 30-sec brand reel showing signage installation, printing in action, and 3D letter fabrication</p>
              </div>
            </div>
          </div>
          <div class="video-side-stack">
            <div class="video-card reveal small-video">
              <!-- VIDEO SLOT 2: Printing Process -->
              <!-- PROMPT: 15-second timelapse video. ALLWIN Flex printing machine printing a large-format banner. Paper rolling out with vibrant red Vodafone branding. Worker collecting finished print. Bright factory lighting, satisfying process video style. -->
              <div class="video-placeholder small">
                <div class="play-btn sm">▶</div>
                <div class="video-meta">
                  <span class="vid-tag">Process · 0:15</span>
                  <h3>Printing in Action</h3>
                  <p>Timelapse of flex printing machine producing large-format output</p>
                </div>
              </div>
            </div>
            <div class="video-card reveal small-video">
              <!-- VIDEO SLOT 3: Event Highlight -->
              <!-- PROMPT: 20-second event highlight reel. Large stage setup with LED screen backdrop and colored stage lighting. Chenda melam (traditional Kerala drums) performers at a store opening. Ribbon cutting ceremony with balloons in red/black/white. Cut to wide aerial view of outdoor event tent. Energetic, celebratory mood. -->
              <div class="video-placeholder small">
                <div class="play-btn sm">▶</div>
                <div class="video-meta">
                  <span class="vid-tag">Events · 0:20</span>
                  <h3>Event Management</h3>
                  <p>Highlight reel of corporate events, store launches and stage setups</p>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- ─── CLIENTS MARQUEE ─── -->
    <section id="clients" class="clients-section section-pad">
      <div class="container">
        <div class="section-head reveal">
          <span class="section-tag">Trusted By</span>
          <h2 class="section-title">Our <em>Clients</em></h2>
        </div>
      </div>
      <div class="marquee-wrap">
        <div class="marquee-track">
          <div class="client-chip" v-for="c in [...clients, ...clients]" :key="c + Math.random()">
            {{ c }}
          </div>
        </div>
      </div>
    </section>

    <!-- ─── CONTACT ─── -->
    <section id="contact" class="contact-section section-pad">
      <div class="container contact-grid">
        <div class="contact-info reveal-left">
          <span class="section-tag">Get In Touch</span>
          <h2 class="section-title">Let's Build<br><em>Something Bold</em></h2>
          <ul class="contact-details">
            <li>
              <span class="cd-icon">📍</span>
              <span>12, Kanya Nagar, Kandhakonnar Layout,<br>TVS Nagar Road, Koundampalayam,<br>Coimbatore – 641030, Tamil Nadu</span>
            </li>
            <li>
              <span class="cd-icon">📞</span>
              <span>0422-2404540 &nbsp;|&nbsp; +91 99439 76001</span>
            </li>
            <li>
              <span class="cd-icon">✉</span>
              <span>cteammedia@gmail.com</span>
            </li>
            <li>
              <span class="cd-icon">🗺</span>
              <span>Operations: Tamil Nadu · Kerala · Karnataka</span>
            </li>
          </ul>
        </div>
        <div class="contact-form reveal-right">
          <form @submit.prevent="submitForm">
            <div class="form-row">
              <div class="form-group">
                <label>Name</label>
                <input type="text" v-model="form.name" placeholder="Your full name" required />
              </div>
              <div class="form-group">
                <label>Phone</label>
                <input type="tel" v-model="form.phone" placeholder="+91 XXXXX XXXXX" />
              </div>
            </div>
            <div class="form-group">
              <label>Email</label>
              <input type="email" v-model="form.email" placeholder="your@email.com" required />
            </div>
            <div class="form-group">
              <label>Service Required</label>
              <select v-model="form.service">
                <option value="">Select a service…</option>
                <option v-for="s in services" :key="s.title" :value="s.title">{{ s.title }}</option>
              </select>
            </div>
            <div class="form-group">
              <label>Message</label>
              <textarea v-model="form.message" rows="4" placeholder="Tell us about your project…"></textarea>
            </div>
            <button type="submit" class="btn-primary full">Send Enquiry →</button>
          </form>
        </div>
      </div>
    </section>

    <!-- ─── FOOTER ─── -->
    <footer class="footer">
      <div class="container footer-inner">
        <div class="footer-brand">
          <span class="nav-logo">
            <span class="logo-c">C</span><span class="logo-dash">-</span><span class="logo-team">TEAM</span>
            <span class="logo-media">MEDIA</span>
          </span>
          <p>The Complete Signage Solution &amp; Event Organiser</p>
        </div>
        <div class="footer-links">
          <a href="#about">About</a>
          <a href="#services">Services</a>
          <a href="#gallery">Gallery</a>
          <a href="#clients">Clients</a>
          <a href="#contact">Contact</a>
        </div>
        <p class="footer-copy">© 2025 C-Team Media. All rights reserved.</p>
      </div>
    </footer>

  </div>
</template>

<script setup>
import { ref, computed, onMounted, onUnmounted } from 'vue'

/* ── Nav scroll state ── */
const navScrolled = ref(false)
const menuOpen = ref(false)
const onScroll = () => { navScrolled.value = window.scrollY > 60 }
onMounted(() => window.addEventListener('scroll', onScroll))
onUnmounted(() => window.removeEventListener('scroll', onScroll))

/* ── Stats ── */
const stats = [
  { value: '25+',     label: 'Years Experience' },
  { value: '60+',     label: 'Team Members' },
  { value: '3',       label: 'States Covered' },
  { value: '250',     label: 'Boards / Day' },
  { value: '10K Sqft',label: 'Print Capacity / Day' },
  { value: '1999',    label: 'Founded' },
]

/* ── About pillars ── */
const pillars = [
  { icon: '🏆', text: 'ISO-quality large-format digital printing' },
  { icon: '⚡', text: 'Express production — 250 boards per day' },
  { icon: '🗺',  text: 'Pan-South India installation teams' },
  { icon: '🎨', text: 'In-house creative design & concepts' },
]

/* ── Services ── */
const services = [
  { icon: '💡', title: 'Glow Sign Boards',      desc: 'Front-lit and backlit LED glow boards for shops, malls and corporate buildings.' },
  { icon: '🔳', title: 'ACP Boards',             desc: 'Aluminium Composite Panel boards for durable, premium building signage.' },
  { icon: '🔤', title: '3D Letters',             desc: 'Custom fabricated metal and acrylic 3D letters for brand facades.' },
  { icon: '📺', title: 'LED Boards',             desc: 'High-brightness LED display boards for indoor and outdoor advertising.' },
  { icon: '🚗', title: 'Vehicle Branding',       desc: 'Full-wrap and partial vehicle branding using eco-solvent vinyl.' },
  { icon: '🖨', title: 'Flex & Vinyl Printing',  desc: 'Large-format flex, backlit, one-way vision and solvent vinyl printing at 10,000 Sqft/day.' },
  { icon: '🏪', title: 'In-Shop Branding',       desc: 'Complete interior brand experience — from wall murals to point-of-sale displays.' },
  { icon: '🏗',  title: 'Fabrication & Erection', desc: 'End-to-end steel fabrication and professional signage installation services.' },
  { icon: '🎪', title: 'Events & Promotions',    desc: 'Corporate events, product launches, stage setup and outdoor advertising promotions.' },
  { icon: '🔍', title: 'Road & Safety Signs',    desc: 'Retro-reflective road signs, safety boards and directional signage.' },
  { icon: '🖼',  title: 'Wall Painting',          desc: 'Premium wall mural painting for brand communication at scale.' },
  { icon: '✏️', title: 'Creative Design',        desc: 'In-house creative team for concept development and visual identity.' },
]

/* ── Gallery ── */
const galleryFilters = ['All', 'Signage', 'Printing', 'Events', 'In-Shop']
const activeFilter = ref('All')

const galleryItems = [
  { id:1,  cat:'Signage',  size:'tall',    label:'LED Glow Sign Board',        prompt:'Photorealistic glowing red LED signboard on modern building facade at night, Coimbatore, India' },
  { id:2,  cat:'Signage',  size:'',        label:'ACP Board Installation',     prompt:'Workers installing large aluminium composite panel signboard on commercial building, daytime, South India' },
  { id:3,  cat:'Events',   size:'wide',    label:'Corporate Event Stage',      prompt:'Grand illuminated stage setup with LED screen backdrop, colored spotlights, red and black theme, South Indian corporate event' },
  { id:4,  cat:'Printing', size:'',        label:'ALLWIN Flex Machine',        prompt:'ALLWIN 1024i flex printing machine printing large-format vivid banner, factory floor, industrial photography' },
  { id:5,  cat:'In-Shop',  size:'',        label:'Sony Center Branding',       prompt:'Sony Center retail store facade at night with glowing 3D Sony letters and backlit display panels' },
  { id:6,  cat:'Signage',  size:'',        label:'3D Letter Fabrication',      prompt:'Shiny stainless steel 3D letters spelling a brand name mounted on a stone wall, dramatic lighting, closeup' },
  { id:7,  cat:'Events',   size:'',        label:'Store Opening Ceremony',     prompt:'Ribbon cutting ceremony at a new store opening with red/black/white balloons arch, South India' },
  { id:8,  cat:'Printing', size:'tall',    label:'HP Latex Eco Machine',       prompt:'HP Latex Eco 3rd generation wide-format printing machine producing a vivid photo-quality banner' },
  { id:9,  cat:'Signage',  size:'',        label:'Neon Light Board',           prompt:'Neon glow sign Samsung Galaxy S10+ backlit board on building at night, blue and white neon lights' },
  { id:10, cat:'In-Shop',  size:'wide',    label:'Vodafone Store Interior',    prompt:'Vodafone store interior full wrap branding — red walls, M-Pesa poster, ZooZoo mascot standee, South India' },
  { id:11, cat:'Signage',  size:'',        label:'Road Sign Installation',     prompt:'Worker installing retro-reflective road directional sign on metal pole, daytime, India highway' },
  { id:12, cat:'Printing', size:'',        label:'Lamination Machine',         prompt:'Industrial lamination machine processing a large-format print, close-up of rollers, vivid output emerging' },
  { id:13, cat:'Events',   size:'',        label:'Chenda Melam Event',         prompt:'Traditional Kerala Chenda Melam drummers performing at a corporate store launch event, red/black balloon arch behind them' },
  { id:14, cat:'In-Shop',  size:'',        label:'LG Best Shop Facade',        prompt:'LG Best Shop building exterior with large red ACP cladding and 3D LG logo, LED lighting, evening' },
  { id:15, cat:'Signage',  size:'',        label:'Vehicle Branding Wrap',      prompt:'Fully wrapped yellow Tata Ace mini truck with C-Team Media branding, fleet of vehicles in parking lot' },
  { id:16, cat:'Printing', size:'',        label:'Large Format Vinyl Print',   prompt:'Large-format eco-solvent vinyl print of a hotel billboard graphic coming off printer, vivid colors, closeup' },
  { id:17, cat:'Signage',  size:'wide',    label:'Building Sign at Dusk',      prompt:'Wide-angle dusk shot of illuminated multi-brand commercial building facade with multiple glow sign boards, Coimbatore streetscape' },
  { id:18, cat:'Events',   size:'',        label:'Event Stage Lighting',       prompt:'Empty grand event stage with dramatic purple and white beam lighting, truss structure, LED screen, awaiting performance' },
]

const filteredGallery = computed(() =>
  activeFilter.value === 'All'
    ? galleryItems
    : galleryItems.filter(i => i.cat === activeFilter.value)
)

const lightboxItem = ref(null)
const openLightbox = (item) => { lightboxItem.value = item }

/* ── Clients ── */
const clients = [
  'ITC', 'Vodafone', 'Paragon', 'Crompton', 'Sony', 'LG', 'Gulf',
  'Ashirvad Pipes', 'Johnson Tiles', 'Kosamattam Finance', 'Dulux',
  'Muthoot Finance', 'ACC Cement', 'Murugappa', 'ENI Lubricants',
  'Crusoe', 'EKKI Pumps', 'Shanthi Feeds', 'Poomer',
]

/* ── Contact form ── */
const form = ref({ name:'', phone:'', email:'', service:'', message:'' })
const submitForm = () => {
  const mailto = `mailto:cteammedia@gmail.com?subject=Enquiry from ${form.value.name}&body=Name: ${form.value.name}%0APhone: ${form.value.phone}%0AEmail: ${form.value.email}%0AService: ${form.value.service}%0AMessage: ${form.value.message}`
  window.location.href = mailto
}

/* ── Scroll reveal ── */
onMounted(() => {
  const els = document.querySelectorAll('.reveal, .reveal-left, .reveal-right')
  const io = new IntersectionObserver((entries) => {
    entries.forEach(e => { if (e.isIntersecting) { e.target.classList.add('in'); io.unobserve(e.target) }})
  }, { threshold: 0.12 })
  els.forEach(el => io.observe(el))
})
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Bebas+Neue&family=DM+Sans:ital,wght@0,300;0,400;0,500;0,600;1,400&display=swap');

/* ── Reset & Base ── */
*, *::before, *::after { margin:0; padding:0; box-sizing:border-box; }
:root {
  --red:     #D42B2B;
  --red-dk:  #A81F1F;
  --dark:    #111113;
  --dark2:   #1A1A1E;
  --dark3:   #242428;
  --mid:     #3A3A40;
  --muted:   #7A7A85;
  --light:   #F0EFEB;
  --white:   #FFFFFF;
  --display: 'Bebas Neue', sans-serif;
  --body:    'DM Sans', sans-serif;
}
html { scroll-behavior:smooth; }
body { background:var(--dark); color:var(--white); font-family:var(--body); overflow-x:hidden; }
a { text-decoration:none; color:inherit; }
img { display:block; width:100%; object-fit:cover; }
button { cursor:pointer; border:none; background:none; font-family:var(--body); }

/* ── Utility ── */
.container { max-width:1200px; margin:0 auto; padding:0 24px; }
.section-pad { padding:100px 0; }
.section-tag { font-size:.72rem; font-weight:600; letter-spacing:.2em; text-transform:uppercase; color:var(--red); display:block; margin-bottom:12px; }
.section-title { font-family:var(--display); font-size:clamp(2.4rem,5vw,3.6rem); line-height:1.05; margin-bottom:32px; }
.section-title em { color:var(--red); font-style:normal; }
.section-head { text-align:center; }
.btn-primary { display:inline-block; background:var(--red); color:var(--white); padding:14px 36px; font-weight:600; font-size:.95rem; letter-spacing:.06em; border-radius:2px; transition:background .2s, transform .15s; }
.btn-primary:hover { background:var(--red-dk); transform:translateY(-2px); }
.btn-primary.full { width:100%; text-align:center; }
.btn-outline { display:inline-block; border:2px solid rgba(255,255,255,.35); color:var(--white); padding:14px 36px; font-weight:500; border-radius:2px; transition:border-color .2s, background .2s; }
.btn-outline:hover { border-color:var(--white); background:rgba(255,255,255,.08); }

/* ── Reveal Animations ── */
.reveal        { opacity:0; transform:translateY(30px); transition:opacity .65s ease, transform .65s ease; }
.reveal.in     { opacity:1; transform:translateY(0); transition-delay:var(--delay, 0ms); }
.reveal-left   { opacity:0; transform:translateX(-40px); transition:opacity .7s ease, transform .7s ease; }
.reveal-left.in{ opacity:1; transform:translateX(0); }
.reveal-right  { opacity:0; transform:translateX(40px); transition:opacity .7s ease, transform .7s ease; }
.reveal-right.in{ opacity:1; transform:translateX(0); }

/* ── NAV ── */
.nav { position:fixed; top:0; left:0; right:0; z-index:1000; transition:background .3s, padding .3s; padding:8px 0; }
.nav.scrolled { background:rgba(17,17,19,.92); backdrop-filter:blur(14px); border-bottom:1px solid rgba(255,255,255,.06); }
.nav-inner { max-width:1200px; margin:0 auto; padding:0 24px; display:flex; align-items:center; justify-content:space-between; height:64px; }
.nav-logo { display:flex; align-items:baseline; gap:0; font-family:var(--display); font-size:1.5rem; letter-spacing:.05em; }
.logo-c    { color:var(--red); }
.logo-dash { color:var(--red); }
.logo-team { color:var(--white); margin:0 6px 0 1px; }
.logo-media{ color:var(--muted); font-size:1rem; }
.nav-links { display:flex; gap:32px; align-items:center; list-style:none; }
.nav-links a { font-size:.88rem; font-weight:500; letter-spacing:.05em; color:rgba(255,255,255,.7); transition:color .2s; }
.nav-links a:hover { color:var(--white); }
.nav-cta { background:var(--red); color:var(--white) !important; padding:10px 22px; border-radius:2px; }
.nav-cta:hover { background:var(--red-dk); }
.hamburger { display:none; flex-direction:column; gap:5px; padding:4px; }
.hamburger span { width:24px; height:2px; background:var(--white); transition:.3s; border-radius:1px; }
.hamburger.open span:nth-child(1) { transform:translateY(7px) rotate(45deg); }
.hamburger.open span:nth-child(2) { opacity:0; }
.hamburger.open span:nth-child(3) { transform:translateY(-7px) rotate(-45deg); }
.mobile-menu { display:none; flex-direction:column; background:var(--dark2); border-top:1px solid var(--mid); padding:16px 24px 24px; gap:16px; }
.mobile-menu a { font-size:1rem; font-weight:500; color:rgba(255,255,255,.8); }
@media(max-width:768px) {
  .nav-links { display:none; }
  .hamburger { display:flex; }
  .mobile-menu.open { display:flex; }
}

/* ── HERO ── */
.hero { position:relative; height:100vh; min-height:600px; display:flex; align-items:center; overflow:hidden; }
.hero-bg { position:absolute; inset:0; }
.hero-bg-img { width:100%; height:100%; object-fit:cover; object-position:center; filter:brightness(.45) saturate(1.1); }
.hero-overlay { position:absolute; inset:0; background:linear-gradient(135deg, rgba(17,17,19,.85) 0%, rgba(212,43,43,.15) 50%, rgba(17,17,19,.7) 100%); }
.hero-grid-lines { position:absolute; inset:0; background-image:linear-gradient(rgba(255,255,255,.03) 1px, transparent 1px), linear-gradient(90deg, rgba(255,255,255,.03) 1px, transparent 1px); background-size:60px 60px; }
.hero-content { position:relative; z-index:2; max-width:1200px; margin:0 auto; padding:0 24px; }
.hero-eyebrow { font-size:.78rem; font-weight:500; letter-spacing:.22em; text-transform:uppercase; color:var(--red); margin-bottom:20px; opacity:0; animation:fadeUp .8s .3s forwards; }
.hero-title { font-family:var(--display); font-size:clamp(4rem,10vw,8.5rem); line-height:.96; margin-bottom:24px; }
.title-line { display:block; opacity:0; animation:fadeUp .8s forwards; }
.title-line:nth-child(1) { animation-delay:.5s; }
.title-line:nth-child(2) { animation-delay:.7s; }
.title-line.accent { color:var(--red); }
.hero-sub { font-size:clamp(.95rem,2vw,1.25rem); color:rgba(255,255,255,.65); margin-bottom:40px; letter-spacing:.04em; opacity:0; animation:fadeUp .8s .9s forwards; }
.hero-actions { display:flex; gap:16px; flex-wrap:wrap; opacity:0; animation:fadeUp .8s 1.1s forwards; }
.hero-scroll-hint { position:absolute; bottom:40px; left:50%; transform:translateX(-50%); display:flex; flex-direction:column; align-items:center; gap:8px; z-index:2; }
.scroll-line { width:1px; height:48px; background:linear-gradient(to bottom, rgba(255,255,255,.6), transparent); animation:scrollPulse 2s infinite; }
.scroll-label { font-size:.65rem; letter-spacing:.18em; text-transform:uppercase; color:rgba(255,255,255,.4); }
@keyframes fadeUp { from{opacity:0;transform:translateY(24px)} to{opacity:1;transform:translateY(0)} }
@keyframes scrollPulse { 0%,100%{opacity:.3} 50%{opacity:1} }

/* ── STATS TICKER ── */
.stats-ticker { background:var(--red); overflow:hidden; padding:14px 0; }
.ticker-inner { display:flex; gap:0; width:max-content; animation:tickerMove 28s linear infinite; }
.stat { display:flex; flex-direction:column; align-items:center; padding:0 40px; border-right:1px solid rgba(255,255,255,.25); }
.stat-num { font-family:var(--display); font-size:1.7rem; line-height:1; color:var(--white); }
.stat-label { font-size:.65rem; letter-spacing:.14em; text-transform:uppercase; color:rgba(255,255,255,.7); margin-top:2px; }
.ticker-divider { display:flex; align-items:center; padding:0 28px; color:rgba(255,255,255,.4); font-size:.8rem; }
@keyframes tickerMove { from{transform:translateX(0)} to{transform:translateX(-50%)} }

/* ── ABOUT ── */
.about { background:var(--dark2); }
.about-grid { display:grid; grid-template-columns:1fr 1fr; gap:72px; align-items:center; }
.about-img-wrap { position:relative; }
.about-img-placeholder { width:100%; aspect-ratio:4/5; background:var(--dark3); border:2px dashed var(--mid); border-radius:4px; display:flex; flex-direction:column; align-items:center; justify-content:center; gap:8px; }
.placeholder-label { font-family:var(--display); font-size:1.4rem; color:var(--muted); }
.placeholder-hint   { font-size:.8rem; color:var(--mid); text-align:center; padding:0 16px; }
.about-badge { position:absolute; bottom:-20px; right:-20px; background:var(--red); padding:20px 24px; text-align:center; }
.badge-num { font-family:var(--display); font-size:2.6rem; display:block; line-height:1; }
.badge-num sup { font-size:1.2rem; }
.badge-text { font-size:.7rem; letter-spacing:.12em; text-transform:uppercase; color:rgba(255,255,255,.8); }
.about-body { color:rgba(255,255,255,.7); line-height:1.8; margin-bottom:28px; }
.about-body strong { color:var(--white); }
.about-pillars { list-style:none; display:flex; flex-direction:column; gap:10px; margin-bottom:36px; }
.about-pillars li { display:flex; align-items:center; gap:12px; font-size:.9rem; color:rgba(255,255,255,.75); }
.pillar-icon { font-size:1.1rem; }
@media(max-width:900px) { .about-grid { grid-template-columns:1fr; gap:40px; } .about-badge { right:0; } }

/* ── SERVICES ── */
.services { background:var(--dark); }
.services-grid { display:grid; grid-template-columns:repeat(auto-fill, minmax(260px, 1fr)); gap:2px; margin-top:56px; }
.service-card { background:var(--dark3); padding:36px 28px; position:relative; overflow:hidden; transition:background .25s; }
.service-card:hover { background:var(--dark2); }
.service-hover-line { position:absolute; bottom:0; left:0; width:0; height:3px; background:var(--red); transition:width .35s; }
.service-card:hover .service-hover-line { width:100%; }
.service-icon { font-size:2rem; margin-bottom:16px; display:block; }
.service-card h3 { font-family:var(--display); font-size:1.3rem; letter-spacing:.03em; margin-bottom:10px; }
.service-card p { font-size:.85rem; color:rgba(255,255,255,.55); line-height:1.7; }

/* ── CAPACITY BAND ── */
.capacity-band { background:var(--dark2); border-top:1px solid var(--mid); border-bottom:1px solid var(--mid); }
.capacity-inner { max-width:1200px; margin:0 auto; padding:32px 24px; display:flex; flex-wrap:wrap; align-items:center; justify-content:center; gap:16px; text-align:center; }
.cap-item { font-size:.9rem; color:rgba(255,255,255,.65); padding:0 24px; }
.cap-item strong { color:var(--red); font-size:1.2rem; }
.cap-sep { color:var(--mid); font-size:1.2rem; }

/* ── GALLERY ── */
.gallery-section { background:var(--dark2); }
.gallery-filters { display:flex; gap:8px; flex-wrap:wrap; justify-content:center; margin:40px 0 32px; }
.filter-btn { padding:9px 22px; border:1.5px solid var(--mid); color:rgba(255,255,255,.6); font-size:.82rem; font-weight:500; letter-spacing:.06em; border-radius:2px; transition:.2s; }
.filter-btn:hover, .filter-btn.active { background:var(--red); border-color:var(--red); color:var(--white); }
.gallery-grid { display:grid; grid-template-columns:repeat(4, 1fr); grid-auto-rows:220px; gap:4px; }
.gallery-item { overflow:hidden; cursor:pointer; }
.gallery-item.tall  { grid-row:span 2; }
.gallery-item.wide  { grid-column:span 2; }
.gallery-img-wrap { position:relative; width:100%; height:100%; }
.gallery-placeholder { position:absolute; inset:0; background:var(--dark3); border:1px dashed var(--mid); display:flex; flex-direction:column; align-items:center; justify-content:center; gap:6px; padding:16px; }
.gp-num   { font-family:var(--display); font-size:2.2rem; color:var(--mid); }
.gp-label { font-size:.8rem; font-weight:600; color:var(--muted); text-align:center; }
.gp-hint  { font-size:.65rem; color:var(--mid); text-align:center; line-height:1.4; display:none; }
.gallery-placeholder:hover .gp-hint { display:block; }
.gallery-overlay { position:absolute; inset:0; background:rgba(212,43,43,.85); display:flex; flex-direction:column; align-items:center; justify-content:center; gap:8px; opacity:0; transition:opacity .3s; }
.gallery-img-wrap:hover .gallery-overlay { opacity:1; }
.gallery-view-icon { font-size:2.8rem; font-weight:300; color:var(--white); line-height:1; }
.gallery-cat { font-size:.65rem; letter-spacing:.16em; text-transform:uppercase; color:rgba(255,255,255,.75); }
.gallery-caption { font-family:var(--display); font-size:1.2rem; color:var(--white); text-align:center; padding:0 12px; }
@media(max-width:900px) { .gallery-grid { grid-template-columns:repeat(2,1fr); } }
@media(max-width:540px) { .gallery-grid { grid-template-columns:1fr; } .gallery-item.wide,.gallery-item.tall { grid-column:span 1; grid-row:span 1; } }

/* ── LIGHTBOX ── */
.lightbox { position:fixed; inset:0; background:rgba(0,0,0,.9); z-index:2000; display:flex; align-items:center; justify-content:center; padding:24px; }
.lb-close { position:absolute; top:24px; right:28px; font-size:1.4rem; color:rgba(255,255,255,.6); transition:color .2s; z-index:2001; }
.lb-close:hover { color:var(--white); }
.lb-content { display:grid; grid-template-columns:1fr 300px; max-width:900px; width:100%; background:var(--dark2); overflow:hidden; }
.lb-img-wrap { aspect-ratio:16/9; }
.lb-placeholder { width:100%; height:100%; background:var(--dark3); display:flex; align-items:center; justify-content:center; font-family:var(--display); font-size:1.4rem; color:var(--muted); padding:24px; text-align:center; }
.lb-meta { padding:32px 24px; }
.lb-cat { font-size:.65rem; letter-spacing:.16em; text-transform:uppercase; color:var(--red); }
.lb-meta h3 { font-family:var(--display); font-size:1.8rem; margin:10px 0 12px; }
.lb-meta p  { font-size:.82rem; color:rgba(255,255,255,.55); line-height:1.7; }
@media(max-width:700px) { .lb-content { grid-template-columns:1fr; } }
.fade-enter-active, .fade-leave-active { transition:opacity .3s; }
.fade-enter-from, .fade-leave-to { opacity:0; }

/* ── VIDEO SECTION ── */
.video-section { background:var(--dark); }
.video-grid { display:grid; grid-template-columns:1.6fr 1fr; gap:4px; margin-top:56px; }
.video-card { overflow:hidden; }
.video-placeholder { background:var(--dark3); border:1px dashed var(--mid); display:flex; flex-direction:column; align-items:center; justify-content:center; gap:20px; padding:56px 32px; min-height:320px; text-align:center; transition:background .2s; cursor:pointer; }
.video-placeholder:hover { background:var(--dark2); }
.video-placeholder.small { min-height:156px; padding:28px 24px; flex-direction:row; text-align:left; gap:16px; }
.play-btn { width:64px; height:64px; border-radius:50%; border:2px solid var(--red); display:flex; align-items:center; justify-content:center; font-size:1.2rem; color:var(--red); flex-shrink:0; transition:.2s; }
.play-btn.sm { width:44px; height:44px; font-size:.9rem; }
.video-placeholder:hover .play-btn { background:var(--red); color:var(--white); }
.vid-tag { font-size:.65rem; letter-spacing:.14em; text-transform:uppercase; color:var(--red); }
.video-meta h3 { font-family:var(--display); font-size:1.5rem; margin:6px 0 8px; }
.video-meta p  { font-size:.78rem; color:rgba(255,255,255,.45); line-height:1.6; }
.video-side-stack { display:flex; flex-direction:column; gap:4px; }
@media(max-width:768px) { .video-grid { grid-template-columns:1fr; } }

/* ── CLIENTS MARQUEE ── */
.clients-section { background:var(--dark2); }
.marquee-wrap { overflow:hidden; margin-top:48px; padding:24px 0; border-top:1px solid var(--mid); border-bottom:1px solid var(--mid); }
.marquee-track { display:flex; gap:0; width:max-content; animation:marqueeScroll 30s linear infinite; }
.marquee-track:hover { animation-play-state:paused; }
.client-chip { padding:12px 36px; border-right:1px solid var(--mid); font-family:var(--display); font-size:1.1rem; letter-spacing:.08em; color:rgba(255,255,255,.45); white-space:nowrap; transition:color .2s; }
.client-chip:hover { color:var(--white); }
@keyframes marqueeScroll { from{transform:translateX(0)} to{transform:translateX(-50%)} }

/* ── CONTACT ── */
.contact-section { background:var(--dark); }
.contact-grid { display:grid; grid-template-columns:1fr 1.2fr; gap:72px; align-items:start; }
.contact-details { list-style:none; display:flex; flex-direction:column; gap:20px; margin-bottom:40px; }
.contact-details li { display:flex; gap:14px; font-size:.9rem; color:rgba(255,255,255,.7); line-height:1.6; }
.cd-icon { font-size:1.1rem; flex-shrink:0; margin-top:2px; }
.contact-form { background:var(--dark3); padding:40px 36px; }
.form-row { display:grid; grid-template-columns:1fr 1fr; gap:16px; }
.form-group { display:flex; flex-direction:column; gap:6px; margin-bottom:16px; }
.form-group label { font-size:.75rem; font-weight:600; letter-spacing:.1em; text-transform:uppercase; color:rgba(255,255,255,.5); }
.form-group input,
.form-group select,
.form-group textarea { background:var(--dark2); border:1.5px solid var(--mid); color:var(--white); padding:12px 14px; font-family:var(--body); font-size:.9rem; border-radius:2px; outline:none; transition:border-color .2s; resize:vertical; }
.form-group input:focus,
.form-group select:focus,
.form-group textarea:focus { border-color:var(--red); }
.form-group select option { background:var(--dark2); }
@media(max-width:900px) { .contact-grid { grid-template-columns:1fr; gap:40px; } .form-row { grid-template-columns:1fr; } }

/* ── FOOTER ── */
.footer { background:var(--dark2); border-top:1px solid var(--mid); padding:48px 0 28px; }
.footer-inner { display:flex; flex-direction:column; align-items:center; gap:24px; text-align:center; }
.footer-brand p { font-size:.85rem; color:var(--muted); margin-top:8px; }
.footer-links { display:flex; gap:28px; flex-wrap:wrap; justify-content:center; }
.footer-links a { font-size:.82rem; color:var(--muted); transition:color .2s; }
.footer-links a:hover { color:var(--white); }
.footer-copy { font-size:.75rem; color:var(--mid); }
</style>