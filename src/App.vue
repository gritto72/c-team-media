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
        <!--
          ✅ REPLACE THIS IMAGE when ready:
          Prompt → "Dramatic wide-angle night photo of busy South Indian commercial
          street with glowing LED flex signboards in red and white, cinematic motion
          blur traffic, 16:9 photorealistic"
          1. Save image as: src/assets/hero.jpg
          2. Change src below to: @/assets/hero.jpg
        -->
        <img
          class="hero-bg-img"
          src="https://images.unsplash.com/photo-1567521464027-f127ff144326?w=1800&q=80"
          alt="C-Team Media – The World of Advertising"
        />
        <div class="hero-overlay"></div>
        <div class="hero-grid-lines"></div>
      </div>
      <div class="hero-content">
        <p class="hero-eyebrow">Est. 1999 &nbsp;·&nbsp; Coimbatore, Tamil Nadu</p>
        <h1 class="hero-title">
          <span class="title-line">THE WORLD</span>
          <span class="title-line accent">OF ADVERTISING</span>
        </h1>
        <p class="hero-sub">The Complete Signage Solution &amp; Event Organiser</p>
        <div class="hero-actions">
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
        <template v-for="n in 2" :key="n">
          <div class="stat" v-for="s in stats" :key="n + s.label">
            <span class="stat-num">{{ s.value }}</span>
            <span class="stat-label">{{ s.label }}</span>
          </div>
          <span class="ticker-star">★</span>
        </template>
      </div>
    </div>

    <!-- ─── ABOUT ─── -->
    <section id="about" class="about section-pad">
      <div class="container about-grid">
        <div class="about-media">
          <!--
            ✅ REPLACE with actual office photo:
            Prompt → "Modern corporate office interior with C-TEAM MEDIA signage
            on dark feature wall, stone-textured accent wall, warm editorial lighting, no people"
            1. Save as: src/assets/office.jpg
            2. Change src to: @/assets/office.jpg
          -->
          <div class="about-img-wrap">
            <img
              class="about-img"
              src="https://images.unsplash.com/photo-1497366216548-37526070297c?w=800&q=80"
              alt="C-Team Media office interior"
            />
            <div class="about-badge">
              <span class="badge-num">25<sup>+</sup></span>
              <span class="badge-text">Years of Excellence</span>
            </div>
          </div>
        </div>

        <div class="about-text">
          <span class="section-tag">About Us</span>
          <h2 class="section-title">Shaping Your<br><em>Idea</em> into Reality</h2>
          <p class="about-body">
            Founded in 1999 as <strong>Digital World</strong>, we pioneered screen printing and outdoor
            advertising across South India. Our sister concern <strong>C-Team Media</strong> expanded
            the vision into a large-scale signage powerhouse — with a team of <strong>60+ professionals</strong>
            under two dedicated managers, delivering impactful branding across Tamil Nadu, Kerala and Karnataka.
          </p>
          <ul class="about-pillars">
            <li v-for="p in pillars" :key="p.text">
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
        <div class="section-head">
          <span class="section-tag">What We Do</span>
          <h2 class="section-title">Complete Range of<br><em>Signage Products</em></h2>
        </div>
        <div class="services-grid">
          <div
            class="service-card"
            v-for="s in services"
            :key="s.title">
            <div class="service-icon">{{ s.icon }}</div>
            <h3>{{ s.title }}</h3>
            <p>{{ s.desc }}</p>
            <div class="service-hover-line"></div>
          </div>
        </div>
      </div>
    </section>

    <!-- ─── CAPACITY BAND ─── -->
    <div class="capacity-band">
      <div class="capacity-inner">
        <div class="cap-item"><strong>250</strong> Front-Lit Boards / Day</div>
        <div class="cap-sep">|</div>
        <div class="cap-item"><strong>100</strong> Back-Lit Boards / Day</div>
        <div class="cap-sep">|</div>
        <div class="cap-item"><strong>10,000 Sqft</strong> Digital Print / Day</div>
        <div class="cap-sep">|</div>
        <div class="cap-item">Operations across <strong>3 States</strong></div>
      </div>
    </div>

    <!-- ─── GALLERY ─── -->
    <section id="gallery" class="gallery-section section-pad">
      <div class="container">
        <div class="section-head">
          <span class="section-tag">Our Work</span>
          <h2 class="section-title">Projects &amp;<br><em>Portfolio</em></h2>
        </div>

        <div class="gallery-filters">
          <button
            v-for="f in galleryFilters"
            :key="f"
            class="filter-btn"
            :class="{ active: activeFilter === f }"
            @click="activeFilter = f">
            {{ f }}
          </button>
        </div>

        <div class="gallery-grid">
          <div
            class="gallery-item"
            v-for="item in filteredGallery"
            :key="item.id"
            :class="item.size"
            @click="openLightbox(item)">
            <div class="gallery-img-wrap">
              <img :src="item.img" :alt="item.label" loading="lazy" />
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
      <transition name="lb-fade">
        <div class="lightbox" v-if="lightboxItem" @click.self="lightboxItem = null">
          <button class="lb-close" @click="lightboxItem = null">✕</button>
          <div class="lb-content">
            <div class="lb-img-wrap">
              <img :src="lightboxItem.img" :alt="lightboxItem.label" />
            </div>
            <div class="lb-meta">
              <span class="lb-cat">{{ lightboxItem.cat }}</span>
              <h3>{{ lightboxItem.label }}</h3>
              <p class="lb-note">📷 Replace with actual project photo.</p>
              <p class="lb-prompt">{{ lightboxItem.prompt }}</p>
            </div>
          </div>
        </div>
      </transition>
    </section>

    <!-- ─── VIDEO SECTION ─── -->
    <section class="video-section section-pad">
      <div class="container">
        <div class="section-head">
          <span class="section-tag">In Action</span>
          <h2 class="section-title">See How We<br><em>Bring Ideas to Life</em></h2>
        </div>

        <div class="video-grid">
          <!-- Primary brand reel -->
          <div class="video-card primary-video">
            <!--
              ✅ REPLACE with real video:
              <video autoplay muted loop playsinline class="vbg">
                <source src="@/assets/brand-reel.mp4" type="video/mp4" />
              </video>
              Prompt → "30-sec brand reel: timelapse glow sign install at dusk →
              ALLWIN flex printing machine → 3D letter workshop → illuminated
              signboard night reveal → C-Team Media logo on red. Cinematic."
            -->
            <div class="vid-thumb">
              <img src="https://images.unsplash.com/photo-1504711434969-e33886168f5c?w=1200&q=80" alt="Brand reel" />
              <div class="vid-overlay">
                <div class="play-circle">▶</div>
                <div class="vid-info">
                  <span class="vid-tag">Brand Reel · 0:30</span>
                  <h3>The World of Advertising</h3>
                  <p>Replace: signage install → printing → 3D letters → night reveal</p>
                </div>
              </div>
            </div>
          </div>

          <div class="video-side-stack">
            <!-- Process video -->
            <div class="video-card small-video">
              <!--
                ✅ REPLACE with process video:
                Prompt → "15-sec timelapse ALLWIN Flex printing machine producing
                large-format Vodafone banner. Worker collecting finished print."
              -->
              <div class="vid-thumb">
                <img src="https://images.unsplash.com/photo-1558618666-fcd25c85cd64?w=800&q=80" alt="Printing" />
                <div class="vid-overlay small">
                  <div class="play-circle sm">▶</div>
                  <div class="vid-info">
                    <span class="vid-tag">Process · 0:15</span>
                    <h3>Printing in Action</h3>
                    <p>Replace: flex printing machine producing large-format output</p>
                  </div>
                </div>
              </div>
            </div>

            <!-- Events video -->
            <div class="video-card small-video">
              <!--
                ✅ REPLACE with events video:
                Prompt → "20-sec: LED stage backdrop + Chenda Melam performers +
                ribbon cutting red/black/white balloons. Energetic, celebratory."
              -->
              <div class="vid-thumb">
                <img src="https://images.unsplash.com/photo-1492684223066-81342ee5ff30?w=800&q=80" alt="Events" />
                <div class="vid-overlay small">
                  <div class="play-circle sm">▶</div>
                  <div class="vid-info">
                    <span class="vid-tag">Events · 0:20</span>
                    <h3>Event Management</h3>
                    <p>Replace: corporate events, store launches, stage setups</p>
                  </div>
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
        <div class="section-head">
          <span class="section-tag">Trusted By</span>
          <h2 class="section-title">Our <em>Clients</em></h2>
        </div>
      </div>
      <div class="marquee-wrap">
        <div class="marquee-track">
          <span class="client-chip" v-for="(c, i) in [...clients, ...clients]" :key="i">{{ c }}</span>
        </div>
      </div>
    </section>

    <!-- ─── CONTACT ─── -->
    <section id="contact" class="contact-section section-pad">
      <div class="container contact-grid">
        <div class="contact-info">
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
              <span class="cd-icon">✉️</span>
              <a href="mailto:cteammedia@gmail.com">cteammedia@gmail.com</a>
            </li>
            <li>
              <span class="cd-icon">🗺️</span>
              <span>Tamil Nadu · Kerala · Karnataka</span>
            </li>
          </ul>
        </div>

        <div class="contact-form">
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
            <span class="logo-c">C</span><span class="logo-dash">-</span>
            <span class="logo-team">TEAM</span><span class="logo-media">MEDIA</span>
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

const navScrolled = ref(false)
const menuOpen    = ref(false)
const onScroll    = () => { navScrolled.value = window.scrollY > 60 }
onMounted(()  => window.addEventListener('scroll', onScroll))
onUnmounted(() => window.removeEventListener('scroll', onScroll))

const stats = [
  { value:'25+',      label:'Years Experience' },
  { value:'60+',      label:'Team Members' },
  { value:'3 States', label:'Operations' },
  { value:'250/Day',  label:'Boards Produced' },
  { value:'10K Sqft', label:'Print/Day' },
  { value:'1999',     label:'Founded' },
]

const pillars = [
  { icon:'🏆', text:'ISO-quality large-format digital printing' },
  { icon:'⚡', text:'Express production — 250 boards per day' },
  { icon:'🗺️', text:'Pan-South India installation teams' },
  { icon:'🎨', text:'In-house creative design & concepts' },
]

const services = [
  { icon:'💡', title:'Glow Sign Boards',       desc:'Front-lit and backlit LED glow boards for shops, malls and corporate buildings.' },
  { icon:'🔳', title:'ACP Boards',              desc:'Aluminium Composite Panel boards for durable, premium building signage.' },
  { icon:'🔤', title:'3D Letters',              desc:'Custom fabricated metal and acrylic 3D letters for brand facades.' },
  { icon:'📺', title:'LED Boards',              desc:'High-brightness LED display boards for indoor and outdoor advertising.' },
  { icon:'🚗', title:'Vehicle Branding',        desc:'Full-wrap and partial vehicle branding using eco-solvent vinyl.' },
  { icon:'🖨️', title:'Flex & Vinyl Printing',   desc:'Large-format flex, backlit, one-way vision and solvent vinyl printing.' },
  { icon:'🏪', title:'In-Shop Branding',        desc:'Complete interior brand experience — wall murals to point-of-sale displays.' },
  { icon:'🏗️', title:'Fabrication & Erection', desc:'End-to-end steel fabrication and professional signage installation.' },
  { icon:'🎪', title:'Events & Promotions',     desc:'Corporate events, product launches, stage setup and outdoor promotions.' },
  { icon:'🔍', title:'Road & Safety Signs',     desc:'Retro-reflective road signs, safety boards and directional signage.' },
  { icon:'🖼️', title:'Wall Painting',           desc:'Premium wall mural painting for brand communication at scale.' },
  { icon:'✏️', title:'Creative Design',         desc:'In-house creative team for concept development and visual identity.' },
]

const galleryFilters = ['All','Signage','Printing','Events','In-Shop']
const activeFilter   = ref('All')

// ─── Gallery items ───────────────────────────────────────────────────────────
// Each item uses a contextual Unsplash placeholder.
// ✅ REPLACE each img URL with your actual project photo saved in src/assets/
// e.g.: img: new URL('@/assets/gallery/glow-sign.jpg', import.meta.url).href
const galleryItems = [
  { id:1,  cat:'Signage',  size:'tall', label:'LED Glow Sign Board',
    img:'https://images.unsplash.com/photo-1596003906949-67221c37965c?w=600&q=80',
    prompt:'Photorealistic glowing red LED signboard on modern building facade at night' },
  { id:2,  cat:'Signage',  size:'',     label:'ACP Board Installation',
    img:'https://images.unsplash.com/photo-1617881770125-6fb0d039ecf2?w=600&q=80',
    prompt:'Workers installing large aluminium composite panel signboard on commercial building' },
  { id:3,  cat:'Events',   size:'wide', label:'Corporate Event Stage',
    img:'https://images.unsplash.com/photo-1540575467063-178a50c2df87?w=1200&q=80',
    prompt:'Grand illuminated stage setup with LED screen backdrop, red/black theme, South India' },
  { id:4,  cat:'Printing', size:'',     label:'ALLWIN Flex Machine',
    img:'https://images.unsplash.com/photo-1586281380349-632531db7ed4?w=600&q=80',
    prompt:'ALLWIN 1024i flex printing machine printing large-format vivid banner, factory floor' },
  { id:5,  cat:'In-Shop',  size:'',     label:'Sony Center Branding',
    img:'https://images.unsplash.com/photo-1581291518857-4e27b48ff24e?w=600&q=80',
    prompt:'Sony Center retail store facade at night with glowing 3D letters and backlit panels' },
  { id:6,  cat:'Signage',  size:'',     label:'3D Letter Fabrication',
    img:'https://images.unsplash.com/photo-1558618666-fcd25c85cd64?w=600&q=80',
    prompt:'Shiny stainless steel 3D letters mounted on stone wall, dramatic lighting, closeup' },
  { id:7,  cat:'Events',   size:'',     label:'Store Opening Ceremony',
    img:'https://images.unsplash.com/photo-1533174072545-7a4b6ad7a6c3?w=600&q=80',
    prompt:'Ribbon cutting ceremony at a new store opening with red/black/white balloon arch' },
  { id:8,  cat:'Printing', size:'tall', label:'HP Latex Eco Machine',
    img:'https://images.unsplash.com/photo-1562654501-a0ccc0fc3fb1?w=600&q=80',
    prompt:'HP Latex Eco 3rd generation wide-format printing machine producing vivid banner' },
  { id:9,  cat:'Signage',  size:'',     label:'Neon Light Board',
    img:'https://images.unsplash.com/photo-1567521464027-f127ff144326?w=600&q=80',
    prompt:'Neon glow Samsung Galaxy sign on building at night, blue and white neon' },
  { id:10, cat:'In-Shop',  size:'wide', label:'Vodafone Store Interior',
    img:'https://images.unsplash.com/photo-1497366216548-37526070297c?w=1200&q=80',
    prompt:'Vodafone store interior full wrap branding — red walls, M-Pesa poster' },
  { id:11, cat:'Signage',  size:'',     label:'Road Sign Installation',
    img:'https://images.unsplash.com/photo-1504711434969-e33886168f5c?w=600&q=80',
    prompt:'Worker installing retro-reflective road directional sign on metal pole, India highway' },
  { id:12, cat:'Printing', size:'',     label:'Lamination Machine',
    img:'https://images.unsplash.com/photo-1603302576837-37561b2e2302?w=600&q=80',
    prompt:'Industrial lamination machine processing large-format print, closeup of rollers' },
  { id:13, cat:'Events',   size:'',     label:'Chenda Melam Event',
    img:'https://images.unsplash.com/photo-1492684223066-81342ee5ff30?w=600&q=80',
    prompt:'Traditional Kerala Chenda Melam drummers performing at a corporate store launch' },
  { id:14, cat:'In-Shop',  size:'',     label:'LG Best Shop Facade',
    img:'https://images.unsplash.com/photo-1441986300917-64674bd600d8?w=600&q=80',
    prompt:'LG Best Shop building exterior with red ACP cladding and 3D LG logo, evening' },
  { id:15, cat:'Signage',  size:'',     label:'Vehicle Fleet Branding',
    img:'https://images.unsplash.com/photo-1449965408869-eaa3f722e40d?w=600&q=80',
    prompt:'Fully wrapped C-Team Media branded Tata Ace trucks in parking lot, fleet shot' },
  { id:16, cat:'Printing', size:'',     label:'Large Format Vinyl Print',
    img:'https://images.unsplash.com/photo-1611532736597-de2d4265fba3?w=600&q=80',
    prompt:'Large-format eco-solvent vinyl print coming off printer, vivid colors, closeup' },
  { id:17, cat:'Signage',  size:'wide', label:'Building Sign at Dusk',
    img:'https://images.unsplash.com/photo-1486325212027-8081e485255e?w=1200&q=80',
    prompt:'Wide-angle dusk shot of commercial building facade with multiple glow sign boards' },
  { id:18, cat:'Events',   size:'',     label:'Event Stage Lighting',
    img:'https://images.unsplash.com/photo-1470229722913-7c0e2dbbafd3?w=600&q=80',
    prompt:'Empty grand event stage with dramatic purple/white beam lighting, truss, LED screen' },
]

const filteredGallery = computed(() =>
  activeFilter.value === 'All'
    ? galleryItems
    : galleryItems.filter(i => i.cat === activeFilter.value)
)

const lightboxItem = ref(null)
const openLightbox = (item) => { lightboxItem.value = item }

const clients = [
  'ITC','Vodafone','Paragon','Crompton','Sony','LG','Gulf',
  'Ashirvad Pipes','Johnson Tiles','Kosamattam Finance','Dulux',
  'Muthoot Finance','ACC Cement','Murugappa','ENI','EKKI Pumps',
]

const form = ref({ name:'', phone:'', email:'', service:'', message:'' })
const submitForm = () => {
  const b = `Name: ${form.value.name}%0APhone: ${form.value.phone}%0AEmail: ${form.value.email}%0AService: ${form.value.service}%0AMessage: ${form.value.message}`
  window.location.href = `mailto:cteammedia@gmail.com?subject=Enquiry from ${form.value.name}&body=${b}`
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Bebas+Neue&family=DM+Sans:ital,wght@0,300;0,400;0,500;0,600;1,400&display=swap');

*,*::before,*::after{margin:0;padding:0;box-sizing:border-box}
:root{
  --red:#D42B2B;--red-dk:#A81F1F;
  --dark:#111113;--dark2:#1A1A1E;--dark3:#242428;
  --mid:#3A3A40;--muted:#7A7A85;--white:#FFFFFF;
  --display:'Bebas Neue',sans-serif;
  --body:'DM Sans',sans-serif;
}
html{scroll-behavior:smooth}
body{background:var(--dark);color:var(--white);font-family:var(--body);overflow-x:hidden}
a{text-decoration:none;color:inherit}
img{display:block;width:100%;object-fit:cover}
button{cursor:pointer;border:none;background:none;font-family:var(--body)}

.container{max-width:1200px;margin:0 auto;padding:0 24px}
.section-pad{padding:100px 0}
.section-tag{font-size:.72rem;font-weight:600;letter-spacing:.2em;text-transform:uppercase;color:var(--red);display:block;margin-bottom:12px}
.section-title{font-family:var(--display);font-size:clamp(2.4rem,5vw,3.6rem);line-height:1.05;margin-bottom:32px}
.section-title em{color:var(--red);font-style:normal}
.section-head{text-align:center}
.btn-primary{display:inline-block;background:var(--red);color:var(--white);padding:14px 36px;font-weight:600;font-size:.95rem;letter-spacing:.06em;border-radius:2px;transition:background .2s,transform .15s;cursor:pointer;border:none;font-family:var(--body)}
.btn-primary:hover{background:var(--red-dk);transform:translateY(-2px)}
.btn-primary.full{width:100%;text-align:center;display:block}
.btn-outline{display:inline-block;border:2px solid rgba(255,255,255,.35);color:var(--white);padding:14px 36px;font-weight:500;border-radius:2px;transition:border-color .2s,background .2s}
.btn-outline:hover{border-color:var(--white);background:rgba(255,255,255,.08)}

/* NAV */
.nav{position:fixed;top:0;left:0;right:0;z-index:1000;transition:background .3s}
.nav.scrolled{background:rgba(17,17,19,.94);backdrop-filter:blur(14px);border-bottom:1px solid rgba(255,255,255,.06)}
.nav-inner{max-width:1200px;margin:0 auto;padding:0 24px;display:flex;align-items:center;justify-content:space-between;height:68px}
.nav-logo{display:flex;align-items:baseline;font-family:var(--display);font-size:1.5rem;letter-spacing:.05em}
.logo-c,.logo-dash{color:var(--red)}
.logo-team{color:var(--white);margin:0 5px 0 1px}
.logo-media{color:var(--muted);font-size:.95rem}
.nav-links{display:flex;gap:32px;align-items:center;list-style:none}
.nav-links a{font-size:.88rem;font-weight:500;color:rgba(255,255,255,.7);transition:color .2s}
.nav-links a:hover{color:var(--white)}
.nav-cta{background:var(--red)!important;color:var(--white)!important;padding:9px 22px!important;border-radius:2px}
.nav-cta:hover{background:var(--red-dk)!important}
.hamburger{display:none;flex-direction:column;gap:5px;padding:4px}
.hamburger span{width:24px;height:2px;background:var(--white);transition:.3s;border-radius:1px;display:block}
.hamburger.open span:nth-child(1){transform:translateY(7px) rotate(45deg)}
.hamburger.open span:nth-child(2){opacity:0}
.hamburger.open span:nth-child(3){transform:translateY(-7px) rotate(-45deg)}
.mobile-menu{display:none;flex-direction:column;background:var(--dark2);border-top:1px solid var(--mid);padding:16px 24px 24px;gap:16px}
.mobile-menu a{font-size:1rem;font-weight:500;color:rgba(255,255,255,.8)}
@media(max-width:768px){.nav-links{display:none}.hamburger{display:flex}.mobile-menu.open{display:flex}}

/* HERO */
.hero{position:relative;height:100vh;min-height:600px;display:flex;align-items:center;overflow:hidden}
.hero-bg{position:absolute;inset:0}
.hero-bg-img{width:100%;height:100%;object-fit:cover;filter:brightness(.42) saturate(1.1)}
.hero-overlay{position:absolute;inset:0;background:linear-gradient(135deg,rgba(17,17,19,.85) 0%,rgba(212,43,43,.12) 50%,rgba(17,17,19,.7) 100%)}
.hero-grid-lines{position:absolute;inset:0;background-image:linear-gradient(rgba(255,255,255,.025) 1px,transparent 1px),linear-gradient(90deg,rgba(255,255,255,.025) 1px,transparent 1px);background-size:60px 60px}
.hero-content{position:relative;z-index:2;max-width:1200px;margin:0 auto;padding:0 24px}
.hero-eyebrow{font-size:.78rem;font-weight:500;letter-spacing:.22em;text-transform:uppercase;color:var(--red);margin-bottom:20px;animation:fadeUp .8s .3s both}
.hero-title{font-family:var(--display);font-size:clamp(4rem,10vw,8.5rem);line-height:.96;margin-bottom:24px}
.title-line{display:block;animation:fadeUp .8s both}
.title-line:nth-child(1){animation-delay:.5s}
.title-line:nth-child(2){animation-delay:.7s}
.title-line.accent{color:var(--red)}
.hero-sub{font-size:clamp(.95rem,2vw,1.25rem);color:rgba(255,255,255,.6);margin-bottom:40px;letter-spacing:.04em;animation:fadeUp .8s .9s both}
.hero-actions{display:flex;gap:16px;flex-wrap:wrap;animation:fadeUp .8s 1.1s both}
.hero-scroll-hint{position:absolute;bottom:40px;left:50%;transform:translateX(-50%);display:flex;flex-direction:column;align-items:center;gap:8px;z-index:2}
.scroll-line{width:1px;height:48px;background:linear-gradient(to bottom,rgba(255,255,255,.5),transparent);animation:scrollPulse 2s infinite}
.scroll-label{font-size:.65rem;letter-spacing:.18em;text-transform:uppercase;color:rgba(255,255,255,.35)}
@keyframes fadeUp{from{opacity:0;transform:translateY(24px)}to{opacity:1;transform:translateY(0)}}
@keyframes scrollPulse{0%,100%{opacity:.3}50%{opacity:1}}

/* STATS TICKER */
.stats-ticker{background:var(--red);overflow:hidden;padding:12px 0}
.ticker-inner{display:flex;width:max-content;animation:tickerMove 30s linear infinite}
.stat{display:flex;flex-direction:column;align-items:center;padding:4px 36px;border-right:1px solid rgba(255,255,255,.22)}
.stat-num{font-family:var(--display);font-size:1.6rem;line-height:1}
.stat-label{font-size:.62rem;letter-spacing:.12em;text-transform:uppercase;color:rgba(255,255,255,.72);margin-top:2px}
.ticker-star{display:flex;align-items:center;padding:0 24px;color:rgba(255,255,255,.35);font-size:.75rem}
@keyframes tickerMove{from{transform:translateX(0)}to{transform:translateX(-50%)}}

/* ABOUT */
.about{background:var(--dark2)}
.about-grid{display:grid;grid-template-columns:1fr 1fr;gap:72px;align-items:center}
.about-img-wrap{position:relative}
.about-img{width:100%;aspect-ratio:4/5;object-fit:cover;border-radius:4px}
.about-badge{position:absolute;bottom:-20px;right:-20px;background:var(--red);padding:20px 24px;text-align:center}
.badge-num{font-family:var(--display);font-size:2.6rem;display:block;line-height:1}
.badge-num sup{font-size:1.2rem}
.badge-text{font-size:.7rem;letter-spacing:.12em;text-transform:uppercase;color:rgba(255,255,255,.8)}
.about-body{color:rgba(255,255,255,.7);line-height:1.8;margin-bottom:28px}
.about-body strong{color:var(--white)}
.about-pillars{list-style:none;display:flex;flex-direction:column;gap:10px;margin-bottom:36px}
.about-pillars li{display:flex;align-items:center;gap:12px;font-size:.9rem;color:rgba(255,255,255,.75)}
.pillar-icon{font-size:1.1rem}
@media(max-width:900px){.about-grid{grid-template-columns:1fr;gap:48px}.about-badge{right:0}}

/* SERVICES */
.services{background:var(--dark)}
.services-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(260px,1fr));gap:2px;margin-top:56px}
.service-card{background:var(--dark3);padding:36px 28px;position:relative;overflow:hidden;transition:background .25s}
.service-card:hover{background:var(--dark2)}
.service-hover-line{position:absolute;bottom:0;left:0;width:0;height:3px;background:var(--red);transition:width .35s}
.service-card:hover .service-hover-line{width:100%}
.service-icon{font-size:2rem;margin-bottom:16px}
.service-card h3{font-family:var(--display);font-size:1.3rem;letter-spacing:.03em;margin-bottom:10px}
.service-card p{font-size:.85rem;color:rgba(255,255,255,.55);line-height:1.7}

/* CAPACITY BAND */
.capacity-band{background:var(--dark2);border-top:1px solid var(--mid);border-bottom:1px solid var(--mid)}
.capacity-inner{max-width:1200px;margin:0 auto;padding:28px 24px;display:flex;flex-wrap:wrap;align-items:center;justify-content:center;gap:12px;text-align:center}
.cap-item{font-size:.9rem;color:rgba(255,255,255,.6);padding:0 20px}
.cap-item strong{color:var(--red);font-size:1.15rem}
.cap-sep{color:var(--mid)}

/* GALLERY */
.gallery-section{background:var(--dark2)}
.gallery-filters{display:flex;gap:8px;flex-wrap:wrap;justify-content:center;margin:40px 0 32px}
.filter-btn{padding:9px 22px;border:1.5px solid var(--mid);background:none;color:rgba(255,255,255,.6);font-size:.82rem;font-weight:500;letter-spacing:.06em;border-radius:2px;cursor:pointer;transition:.2s;font-family:var(--body)}
.filter-btn:hover,.filter-btn.active{background:var(--red);border-color:var(--red);color:var(--white)}
.gallery-grid{display:grid;grid-template-columns:repeat(4,1fr);grid-auto-rows:220px;gap:4px}
.gallery-item{overflow:hidden;cursor:pointer}
.gallery-item.tall{grid-row:span 2}
.gallery-item.wide{grid-column:span 2}
.gallery-img-wrap{position:relative;width:100%;height:100%}
.gallery-img-wrap img{width:100%;height:100%;object-fit:cover;transition:transform .5s ease}
.gallery-item:hover .gallery-img-wrap img{transform:scale(1.06)}
.gallery-overlay{position:absolute;inset:0;background:rgba(212,43,43,.88);display:flex;flex-direction:column;align-items:center;justify-content:center;gap:6px;opacity:0;transition:opacity .3s}
.gallery-img-wrap:hover .gallery-overlay{opacity:1}
.gallery-view-icon{font-size:2.8rem;font-weight:300;color:var(--white);line-height:1}
.gallery-cat{font-size:.65rem;letter-spacing:.16em;text-transform:uppercase;color:rgba(255,255,255,.75)}
.gallery-caption{font-family:var(--display);font-size:1.2rem;color:var(--white);text-align:center;padding:0 12px}
@media(max-width:900px){.gallery-grid{grid-template-columns:repeat(2,1fr)}}
@media(max-width:540px){.gallery-grid{grid-template-columns:1fr}.gallery-item.wide,.gallery-item.tall{grid-column:span 1;grid-row:span 1}}

/* LIGHTBOX */
.lightbox{position:fixed;inset:0;background:rgba(0,0,0,.92);z-index:2000;display:flex;align-items:center;justify-content:center;padding:24px}
.lb-close{position:fixed;top:24px;right:28px;font-size:1.6rem;color:rgba(255,255,255,.55);transition:color .2s;z-index:2001;background:none;border:none;cursor:pointer;line-height:1}
.lb-close:hover{color:var(--white)}
.lb-content{display:grid;grid-template-columns:1fr 300px;max-width:960px;width:100%;background:var(--dark2);overflow:hidden;border-radius:2px}
.lb-img-wrap{overflow:hidden}
.lb-img-wrap img{width:100%;height:100%;object-fit:cover}
.lb-meta{padding:36px 28px;display:flex;flex-direction:column;justify-content:center;gap:8px}
.lb-cat{font-size:.65rem;letter-spacing:.16em;text-transform:uppercase;color:var(--red)}
.lb-meta h3{font-family:var(--display);font-size:1.8rem}
.lb-note{font-size:.82rem;color:rgba(255,255,255,.5)}
.lb-prompt{font-size:.75rem;color:rgba(255,255,255,.28);font-style:italic;line-height:1.6}
@media(max-width:700px){.lb-content{grid-template-columns:1fr}}
.lb-fade-enter-active,.lb-fade-leave-active{transition:opacity .3s}
.lb-fade-enter-from,.lb-fade-leave-to{opacity:0}

/* VIDEO SECTION */
.video-section{background:var(--dark)}
.video-grid{display:grid;grid-template-columns:1.6fr 1fr;gap:4px;margin-top:56px}
.video-card{overflow:hidden}
.vid-thumb{position:relative;overflow:hidden;cursor:pointer}
.primary-video .vid-thumb{min-height:360px}
.small-video .vid-thumb{min-height:178px}
.vid-thumb img{width:100%;height:100%;object-fit:cover;filter:brightness(.4);transition:filter .3s}
.vid-thumb:hover img{filter:brightness(.28)}
.vid-overlay{position:absolute;inset:0;display:flex;flex-direction:column;align-items:center;justify-content:center;gap:16px;padding:32px}
.vid-overlay.small{flex-direction:row;align-items:center;justify-content:flex-start;padding:20px 24px;gap:16px}
.play-circle{width:64px;height:64px;border-radius:50%;border:2px solid var(--red);display:flex;align-items:center;justify-content:center;font-size:1.3rem;color:var(--red);flex-shrink:0;background:rgba(212,43,43,.12);transition:.25s}
.play-circle.sm{width:44px;height:44px;font-size:.95rem}
.vid-thumb:hover .play-circle{background:var(--red);color:var(--white)}
.vid-tag{font-size:.65rem;letter-spacing:.14em;text-transform:uppercase;color:var(--red)}
.vid-info{text-align:center}
.vid-overlay.small .vid-info{text-align:left}
.vid-info h3{font-family:var(--display);font-size:1.5rem;margin:6px 0}
.vid-info p{font-size:.75rem;color:rgba(255,255,255,.38);line-height:1.5}
.video-side-stack{display:flex;flex-direction:column;gap:4px}
@media(max-width:768px){.video-grid{grid-template-columns:1fr}}

/* CLIENTS */
.clients-section{background:var(--dark2)}
.marquee-wrap{overflow:hidden;margin-top:48px;padding:20px 0;border-top:1px solid var(--mid);border-bottom:1px solid var(--mid)}
.marquee-track{display:flex;width:max-content;animation:marqueeScroll 32s linear infinite}
.marquee-track:hover{animation-play-state:paused}
.client-chip{padding:10px 32px;border-right:1px solid var(--mid);font-family:var(--display);font-size:1.1rem;letter-spacing:.08em;color:rgba(255,255,255,.42);white-space:nowrap;transition:color .2s;cursor:default}
.client-chip:hover{color:var(--white)}
@keyframes marqueeScroll{from{transform:translateX(0)}to{transform:translateX(-50%)}}

/* CONTACT */
.contact-section{background:var(--dark)}
.contact-grid{display:grid;grid-template-columns:1fr 1.25fr;gap:72px;align-items:start}
.contact-details{list-style:none;display:flex;flex-direction:column;gap:20px;margin-bottom:40px}
.contact-details li{display:flex;gap:14px;font-size:.9rem;color:rgba(255,255,255,.7);line-height:1.65}
.contact-details a{color:rgba(255,255,255,.7);transition:color .2s}
.contact-details a:hover{color:var(--red)}
.cd-icon{font-size:1.1rem;flex-shrink:0;margin-top:2px}
.contact-form{background:var(--dark3);padding:40px 36px;border-radius:2px}
.form-row{display:grid;grid-template-columns:1fr 1fr;gap:16px}
.form-group{display:flex;flex-direction:column;gap:6px;margin-bottom:16px}
.form-group label{font-size:.72rem;font-weight:600;letter-spacing:.1em;text-transform:uppercase;color:rgba(255,255,255,.45)}
.form-group input,.form-group select,.form-group textarea{background:var(--dark2);border:1.5px solid var(--mid);color:var(--white);padding:12px 14px;font-family:var(--body);font-size:.9rem;border-radius:2px;outline:none;transition:border-color .2s;resize:vertical}
.form-group input:focus,.form-group select:focus,.form-group textarea:focus{border-color:var(--red)}
.form-group select option{background:var(--dark2)}
@media(max-width:900px){.contact-grid{grid-template-columns:1fr;gap:40px}.form-row{grid-template-columns:1fr}}

/* FOOTER */
.footer{background:var(--dark2);border-top:1px solid var(--mid);padding:48px 0 28px}
.footer-inner{display:flex;flex-direction:column;align-items:center;gap:24px;text-align:center}
.footer-brand p{font-size:.85rem;color:var(--muted);margin-top:8px}
.footer-links{display:flex;gap:28px;flex-wrap:wrap;justify-content:center}
.footer-links a{font-size:.82rem;color:var(--muted);transition:color .2s}
.footer-links a:hover{color:var(--white)}
.footer-copy{font-size:.75rem;color:var(--mid)}
</style>