<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Vive Alto Génova – NuestroHogar</title>
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,700;0,900;1,700&family=Barlow:wght@300;400;500;600;700&display=swap" rel="stylesheet">
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
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
  position:fixed;top:0;left:0;right:0;z-index:100;
  background:rgba(10,10,10,0.95);backdrop-filter:blur(10px);
  border-bottom:1px solid rgba(255,255,255,0.1);
  transition:all 0.4s ease;
}
.nav-container{
  max-width:1400px;margin:0 auto;padding:1.25rem 2rem;
  display:flex;justify-content:between;align-items:center;
}
.nav-logo{
  font-family:var(--font-serif);font-size:1.5rem;font-weight:700;color:var(--white);
  letter-spacing:0.5px;
}
.nav-logo span{color:var(--gold);font-weight:300;font-family:var(--font-sans);font-size:0.9rem;letter-spacing:2px;margin-left:8px;text-transform:uppercase;}
.nav-menu{display:flex;gap:2.5rem;list-style:none;}
.nav-link{color:var(--gray);font-size:0.85rem;font-weight:500;text-transform:uppercase;letter-spacing:1.5px;transition:color 0.3s;}
.nav-link:hover,.nav-link.active{color:var(--white);}
.nav-btn{
  background:var(--gold);color:var(--black);padding:0.6rem 1.25rem;
  font-size:0.8rem;font-weight:600;text-transform:uppercase;letter-spacing:1px;
  border-radius:0;transition:all 0.3s;
}
.nav-btn:hover{background:var(--white);transform:translateY(-2px);}
.nav-toggle{display:none;color:var(--white);font-size:1.5rem;cursor:pointer;}

/* ── HERO ── */
.hero{
  height:100vh;position:relative;background:var(--black);
  display:flex;align-items:center;padding:0 10%;overflow:hidden;
}
.hero-bg{
  position:absolute;top:0;left:0;width:100%;height:100%;
  background:linear-gradient(90deg, rgba(10,10,10,0.85) 30%, rgba(10,10,10,0.2) 100%), url('https://images.unsplash.com/photo-1600585154340-be6161a56a0c?auto=format&fit=crop&w=1920&q=80') center/cover no-repeat;
  z-index:1;
}
.hero-content{position:relative;z-index:2;max-width:700px;color:var(--white);opacity:0;transform:translateY(30px);animation:fadeInUp 1s 0.3s forwards;}
.hero-tag{color:var(--gold);font-size:0.9rem;font-weight:600;text-transform:uppercase;letter-spacing:3px;margin-bottom:1rem;display:block;}
.hero-title{font-family:var(--font-serif);font-size:4rem;line-height:1.1;margin-bottom:1.5rem;font-weight:700;}
.hero-p{color:rgba(255,255,255,0.7);font-size:1.1rem;font-weight:300;margin-bottom:2.5rem;max-width:550px;}

/* ── BUTTONS ── */
.btn-group{display:flex;gap:1.5rem;align-items:center;}
.btn-p{
  background:var(--gold);color:var(--black);padding:1rem 2rem;
  font-size:0.85rem;font-weight:600;text-transform:uppercase;letter-spacing:1.5px;
  transition:all 0.3s;display:inline-block;
}
.btn-p:hover{background:var(--white);transform:translateY(-3px);box-shadow:0 10px 20px rgba(0,0,0,0.2);}
.btn-s{
  border:1px solid rgba(255,255,255,0.3);color:var(--white);padding:1rem 2rem;
  font-size:0.85rem;font-weight:600;text-transform:uppercase;letter-spacing:1.5px;
  transition:all 0.3s;display:inline-block;
}
.btn-s:hover{background:rgba(255,255,255,0.1);border-color:var(--white);transform:translateY(-3px);}

/* ── SECTIONS GENERAL ── */
section{padding:8rem 2rem;position:relative;}
.container{max-width:1300px;margin:0 auto;}
.sec-header{max-width:600px;margin-bottom:5rem;opacity:0;transform:translateY(30px);transition:all 0.8s ease;}
.sec-header.show{opacity:1;transform:translateY(0);}
.sec-tag{color:var(--blue);font-size:0.85rem;font-weight:600;text-transform:uppercase;letter-spacing:2px;display:block;margin-bottom:0.75rem;}
.sec-title{font-family:var(--font-serif);font-size:2.5rem;color:var(--dark);font-weight:700;}

/* ── DESCRIPCIÓN ── */
.desc-grid{display:grid;grid-template-columns:1.1fr 0.9fr;gap:5rem;align-items:center;}
.desc-text p{font-size:1.1rem;color:var(--mid);font-weight:300;margin-bottom:1.5rem;line-height:1.8;}
.desc-text p strong{font-weight:600;color:var(--black);}
.desc-img{position:relative;padding-bottom:120%;overflow:hidden;background:var(--light);}
.desc-img img{position:absolute;top:0;left:0;width:100%;height:100%;object-fit:cover;transition:transform 0.8s;}
.desc-img:hover img{transform:scale(1.05);}

/* ── AMENIDADES ── */
.amenities{background:var(--light);}
.amenities-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(280px,1fr));gap:2px;background:rgba(0,0,0,0.05);}
.amenity-card{background:var(--white);padding:4rem 3rem;text-align:left;transition:all 0.4s;}
.amenity-card:hover{background:var(--dark);color:var(--white);}
.am-num{font-size:0.85rem;color:var(--gray);display:block;margin-bottom:2rem;font-weight:500;letter-spacing:1px;}
.amenity-card i{font-size:2.5rem;color:var(--blue);margin-bottom:1.5rem;transition:color 0.4s;}
.amenity-card:hover i{color:var(--gold);}
.amenity-card h3{font-family:var(--font-serif);font-size:1.4rem;margin-bottom:1rem;font-weight:700;}
.amenity-card p{font-size:0.95rem;color:var(--gray);font-weight:300;line-height:1.6;}
.amenity-card:hover p{color:rgba(255,255,255,0.6);}

/* ── MODELOS ── */
.models-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(350px,1fr));gap:3rem;}
.model-card{background:var(--white);border:1px solid rgba(0,0,0,0.05);overflow:hidden;transition:all 0.4s;}
.model-card:hover{transform:translateY(-10px);box-shadow:0 20px 40px rgba(0,0,0,0.05);}
.model-img{position:relative;padding-bottom:75%;overflow:hidden;background:var(--light);}
.model-img img{position:absolute;top:0;left:0;width:100%;height:100%;object-fit:cover;}
.model-info{padding:2.5rem;}
.model-info h3{font-family:var(--font-serif);font-size:1.75rem;margin-bottom:0.5rem;}
.model-info .price{color:var(--blue);font-weight:600;font-size:1.2rem;margin-bottom:1.5rem;display:block;}
.model-specs{display:grid;grid-template-columns:repeat(3,1fr);gap:1rem;padding-top:1.5rem;border-top:1px solid rgba(0,0,0,0.05);text-align:center;}
.spec-item i{font-size:1.2rem;color:var(--gray);margin-bottom:0.5rem;display:block;}
.spec-item span{font-size:0.85rem;color:var(--mid);font-weight:500;}

/* ── SIMULADOR ── */
.calc-sec{background:var(--dark);color:var(--white);}
.calc-sec .sec-title{color:var(--white);}
.calc-sec .sec-tag{color:var(--gold);}
.calc-grid{display:grid;grid-template-columns:1fr 1fr;gap:5rem;align-items:start;}
.calc-form{background:rgba(255,255,255,0.03);border:1px solid rgba(255,255,255,0.05);padding:3.5rem;}
.input-field{margin-bottom:2rem;}
.input-field label{display:block;font-size:0.8rem;text-transform:uppercase;letter-spacing:1.5px;color:rgba(255,255,255,0.5);margin-bottom:0.75rem;font-weight:500;}
.input-field input, .input-field select{
  width:100%;background:rgba(255,255,255,0.05);border:1px solid rgba(255,255,255,0.1);
  padding:1rem;color:var(--white);font-size:1rem;font-family:var(--font-sans);transition:all 0.3s;
}
.input-field input:focus, .input-field select:focus{outline:none;border-color:var(--gold);background:rgba(255,255,255,0.08);}
.calc-btn{
  width:100%;background:var(--gold);color:var(--black);border:none;padding:1.2rem;
  font-size:0.9rem;font-weight:600;text-transform:uppercase;letter-spacing:1.5px;cursor:pointer;transition:all 0.3s;
}
.calc-btn:hover{background:var(--white);transform:translateY(-2px);}
.calc-result{
  background:var(--white);color:var(--black);padding:4rem;height:100%;
  display:flex;flex-direction:column;justify-content:center;opacity:0;transform:translateX(30px);transition:all 0.6s ease;
}
.calc-result.show{opacity:1;transform:translateX(0);}
.res-title{font-size:0.85rem;text-transform:uppercase;letter-spacing:2px;color:var(--gray);margin-bottom:2rem;display:block;font-weight:600;}
.res-amount{font-family:var(--font-serif);font-size:3.5rem;font-weight:700;color:var(--dark);line-height:1;margin-bottom:0.5rem;}
.res-pago{font-size:2rem;font-weight:600;color:var(--blue);margin-bottom:2.5rem;}
.res-pago span{font-size:1rem;color:var(--gray);font-weight:400;}
.res-data{display:flex;justify-content:between;padding:1rem 0;border-top:1px solid rgba(0,0,0,0.05);font-size:0.95rem;}
.res-data span:last-child{font-weight:600;}
.res-note{font-size:0.8rem;color:var(--gray);margin-top:2rem;line-height:1.5;font-weight:300;}

/* ── CONTACTO / FORM ── */
.contact-grid{display:grid;grid-template-columns:0.9fr 1.1fr;gap:6rem;}
.info-box h3{font-family:var(--font-serif);font-size:1.8rem;margin-bottom:1.5rem;}
.info-box p{color:var(--mid);font-weight:300;margin-bottom:3rem;font-size:1.05rem;line-height:1.7;}
.info-item{display:flex;gap:1.5rem;margin-bottom:2rem;align-items:start;}
.info-item i{font-size:1.2rem;color:var(--blue);margin-top:0.25rem;}
.info-item h4{font-size:0.85rem;text-transform:uppercase;letter-spacing:1px;color:var(--gray);margin-bottom:0.25rem;}
.info-item p{font-size:1.05rem;color:var(--black);margin-bottom:0;}
.c-form{display:grid;grid-template-columns:1fr 1fr;gap:1.5rem;}
.cf-field{display:flex;flex-direction:column;}
.cf-field.full{grid-column:span 2;}
.cf-field label{font-size:0.75rem;text-transform:uppercase;letter-spacing:1px;color:var(--gray);margin-bottom:0.5rem;font-weight:600;}
.cf-field input, .cf-field select, .cf-field textarea{
  padding:1rem;background:var(--light);border:1px solid transparent;font-family:var(--font-sans);font-size:0.95rem;transition:all 0.3s;
}
.cf-field input:focus, .cf-field select:focus, .cf-field textarea:focus{outline:none;border-color:var(--blue);background:var(--white);box-shadow:0 5px 15px rgba(0,0,0,0.02);}
.cf-btn{
  grid-column:span 2;background:var(--dark);color:var(--white);border:none;padding:1.2rem;
  font-size:0.85rem;font-weight:600;text-transform:uppercase;letter-spacing:1.5px;cursor:pointer;transition:all 0.3s;
}
.cf-btn:hover{background:var(--blue);transform:translateY(-2px);}

/* ── FOOTER ── */
footer{background:var(--black);color:rgba(255,255,255,0.4);padding:4rem 2rem;text-align:center;border-top:1px solid rgba(255,255,255,0.05);font-size:0.9rem;font-weight:300;}

/* ── WHATSAPP BOTÓN FLOTANTE ── */
.whatsapp-float {
  position:fixed;bottom:30px;right:30px;background:#25d366;color:white;
  width:60px;height:60px;border-radius:50%;text-align:center;font-size:30px;
  box-shadow:0 5px 15px rgba(0,0,0,0.3);z-index:999;display:flex;align-items:center;
  justify-content:center;transition:all 0.3s ease;
}
.whatsapp-float:hover {transform:scale(1.1);background:#20ba5a;}

/* ── ANIMATIONS ── */
@keyframes fadeInUp{to{opacity:1;transform:translateY(0);}}

/* ── RESPONSIVE ── */
@media(max-width:1024px){
  .desc-grid, .calc-grid, .contact-grid{grid-template-columns:1fr;gap:4rem;}
  .hero-title{font-size:3rem;}
  .nav-menu{display:none;}
  .nav-toggle{display:block;}
}
@media(max-width:768px){
  section{padding:5rem 1.5rem;}
  .hero{padding:0 5%;}
  .hero-title{font-size:2.5rem;}
  .c-form{grid-template-columns:1fr;}
  .cf-field.full{grid-column:span 1;}
  .calc-form, .calc-result{padding:2rem;}
}
</style>
</head>
<body>

<nav class="nav">
  <div class="nav-container">
    <a href="#" class="nav-logo">NuestroHogar<span>Vive Alto Génova</span></a>
    <ul class="nav-menu">
      <li><a href="#" class="nav-link active">Inicio</a></li>
      <li><a href="#detalles" class="nav-link">Desarrollo</a></li>
      <li><a href="#amenidades" class="nav-link">Amenidades</a></li>
      <li><a href="#modelos" class="nav-link">Modelos</a></li>
      <li><a href="#simulador" class="nav-link">Cotizador</a></li>
    </ul>
    <a href="#contacto" class="nav-btn">Agendar Cita</a>
    <div class="nav-toggle"><i class="fa-solid fa-bars"></i></div>
  </div>
</nav>

<section class="hero">
  <div class="hero-bg"></div>
  <div class="hero-content">
    <span class="hero-tag">Preventa Exclusiva</span>
    <h1 class="hero-title">El espacio ideal para comenzar tu historia</h1>
    <p class="hero-p">Descubre un concepto residencial diseñado para superar tus expectativas. Ubicación privilegiada, amenidades premium y la plusvalía que tu patrimonio merece.</p>
    <div class="btn-group">
      <a href="#contacto" class="btn-p">Quiero Información</a>
      <a href="#simulador" class="btn-s">Calcular Crédito</a>
    </div>
  </div>
</section>

<section id="detalles">
  <div class="container desc-grid">
    <div class="desc-text sec-header">
      <span class="sec-tag">El Desarrollo</span>
      <h2 class="sec-title">Un santuario de tranquilidad y modernidad</h2>
      <br>
      <p><strong>Vive Alto Génova</strong> es la fusión perfecta entre diseño arquitectónico contemporáneo y funcionalidad. Pensado para familias que buscan elevar su calidad de vida, ofrece un entorno seguro, armónico y conectado con las principales vías de la ciudad.</p>
      <p>Cada rincón ha sido planificado meticulosamente para aprovechar la luz natural, ofreciendo amplios espacios interiores que brindan el confort y la privacidad que tú y los tuyos necesitan.</p>
    </div>
    <div class="desc-img">
      <img src="https://images.unsplash.com/photo-1600596542815-ffad4c1539a9?auto=format&fit=crop&w=800&q=80" alt="Residencial">
    </div>
  </div>
</section>

<section id="amenidades" class="amenities">
  <div class="container">
    <div class="sec-header">
      <span class="sec-tag">Lifestyle</span>
      <h2 class="sec-title">Amenidades que transforman tus días</h2>
    </div>
    <div class="amenities-grid">
      <div class="amenity-card">
        <span class="am-num">01 /</span>
        <i class="fa-solid fa-shield-halved"></i>
        <h3>Seguridad 24/7</h3>
        <p>Acceso controlado automatizado y personal de vigilancia para tu total tranquilidad.</p>
      </div>
      <div class="amenity-card">
        <span class="am-num">02 /</span>
        <i class="fa-solid fa-tree"></i>
        <h3>Áreas Verdes</h3>
        <p>Espacios arbolados, parques infantiles y senderos diseñados para conectar con la naturaleza.</p>
      </div>
      <div class="amenity-card">
        <span class="am-num">03 /</span>
        <i class="fa-solid fa-dumbbell"></i>
        <h3>Gimnasio</h3>
        <p>Equipamiento moderno para tus rutinas diarias sin necesidad de salir de tu hogar.</p>
      </div>
      <div class="amenity-card">
        <span class="am-num">04 /</span>
        <i class="fa-solid fa-mug-hot"></i>
        <h3>Club House</h3>
        <p>Un salón de eventos exclusivo para celebraciones familiares y reuniones sociales.</p>
      </div>
    </div>
  </div>
</section>

<section id="modelos">
  <div class="container">
    <div class="sec-header">
      <span class="sec-tag">Residencias</span>
      <h2 class="sec-title">Encuentra tu prototipo ideal</h2>
    </div>
    <div class="models-grid">
      <div class="model-card">
        <div class="model-img">
          <img src="https://images.unsplash.com/photo-1600607687939-ce8a6c25118c?auto=format&fit=crop&w=600&q=80" alt="Modelo Verona">
        </div>
        <div class="model-info">
          <h3>Prototipo Verona</h3>
          <span class="price">Desde $1,850,000 MXN</span>
          <div class="model-specs">
            <div class="spec-item"><i class="fa-solid fa-bed"></i><span>3 Rec.</span></div>
            <div class="spec-item"><i class="fa-solid fa-bath"></i><span>2.5 Baños</span></div>
            <div class="spec-item"><i class="fa-solid fa-car"></i><span>2 Estac.</span></div>
          </div>
        </div>
      </div>
      <div class="model-card">
        <div class="model-img">
          <img src="https://images.unsplash.com/photo-1600210492486-724fe5c67fb0?auto=format&fit=crop&w=600&q=80" alt="Modelo Florencia">
        </div>
        <div class="model-info">
          <h3>Prototipo Florencia</h3>
          <span class="price">Desde $2,240,000 MXN</span>
          <div class="model-specs">
            <div class="spec-item"><i class="fa-solid fa-bed"></i><span>4 Rec.</span></div>
            <div class="spec-item"><i class="fa-solid fa-bath"></i><span>3 Baños</span></div>
            <div class="spec-item"><i class="fa-solid fa-car"></i><span>2 Estac.</span></div>
          </div>
        </div>
      </div>
    </div>
  </div>
</section>

<section id="simulador" class="calc-sec">
  <div class="container calc-grid">
    <div class="calc-form">
      <span class="sec-tag">Financiamiento</span>
      <h2 class="sec-title">Simulador de Crédito</h2>
      <br><br>
      <div class="input-field">
        <label>Tipo de Crédito</label>
        <select id="tipoCredito">
          <option value="infonavit">Infonavit Tradicional</option>
          <option value="bancario">Crédito Bancario Hipotecario</option>
          <option value="cofinavit">Cofinavit</option>
        </select>
      </div>
      <div class="input-field">
        <label>Precio de la Vivienda (MXN)</label>
        <input type="number" id="valPropiedad" value="1850000">
      </div>
      <div class="input-field">
        <label>Plazo del Crédito</label>
        <select id="plazo">
          <option value="20">20 Años</option>
          <option value="15">15 Años</option>
          <option value="30">30 Años</option>
        </select>
      </div>
      <button class="calc-btn" onclick="calcularHipoteca()">Calcular mensualidad estimada</button>
    </div>
    
    <div class="calc-result" id="calcResult">
      <span class="res-title">Tu Presupuesto Estimado</span>
      <div class="res-amount" id="crCredito">$ 0,000,000</div>
      <div class="res-pago" id="crPago">$ 0,000 <span>/ mes</span></div>
      <div class="res-data"><span>Tasa de interés Anual</span><span id="crTasa">10.45 %</span></div>
      <div class="res-data"><span>Equivalente aproximado</span><span id="crVSM">0.00 VSM</span></div>
      <p class="res-note" id="crNote">Ingresa los datos del formulario y presiona calcular para ver la estimación de tu crédito hipotecario.</p>
    </div>
  </div>
</section>

<section id="contacto">
  <div class="container contact-grid">
    <div class="info-box">
      <span class="sec-tag">Contacto</span>
      <h2 class="sec-title">¿Listo para conocer tu próximo hogar?</h2>
      <p>Agenda una visita guiada para conocer nuestras casas muestra y recibir una asesoría financiera personalizada sin costo alguno.</p>
      <div class="info-item">
        <i class="fa-solid fa-location-dot"></i>
        <div>
          <h4>Ubicación</h4>
          <p>Av. Génova Residencial #405, Sector Premium</p>
        </div>
      </div>
      <div class="info-item">
        <i class="fa-solid fa-phone"></i>
        <div>
          <h4>Teléfono de Ventas</h4>
          <p>+52 220 618 3849</p>
        </div>
      </div>
    </div>
    
    <div class="contact-form">
      <div class="c-form">
        <div class="cf-field">
          <label>Nombre Completo</label>
          <input type="text" placeholder="Ej. Juan Pérez">
        </div>
        <div class="cf-field">
          <label>Teléfono</label>
          <input type="tel" placeholder="10 dígitos">
        </div>
        <div class="cf-field full">
          <label>Prototipo de Interés</label>
          <select>
            <option>Modelo Verona</option>
            <option>Modelo Florencia</option>
            <option>Solo asesoría de crédito</option>
          </select>
        </div>
        <div class="cf-field full">
          <label>Mensaje adicional</label>
          <textarea rows="4" placeholder="¿Tienes alguna duda en específico?"></textarea>
        </div>
        <button class="cf-btn" onclick="enviarWA()">Enviar Mensaje por 
