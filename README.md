# byanca-romantico
<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Carta para Byanca ❤️</title>

    <style>
        body {
            margin: 0;
            background: #0a0a0a;
            font-family: 'Georgia', serif;
            color: #fff;
            overflow-x: hidden;
        }

        /* Canvas das partículas */
        #particles {
            position: fixed;
            top: 0;
            left: 0;
            width: 100vw;
            height: 100vh;
            z-index: -1;
            background: transparent;
        }

        header {
            text-align: center;
            padding: 80px 20px 40px;
        }

        h1 {
            font-size: 3.2rem;
            color: #ff1b1b;
            letter-spacing: 2px;
            text-shadow: 0 0 10px #ff1b1b;
        }

        .carta {
            background: rgba(0,0,0,0.65);
            border-left: 4px solid #ff1b1b;
            padding: 35px;
            margin: 40px auto;
            max-width: 750px;
            border-radius: 10px;
            font-size: 1.3rem;
            line-height: 1.9;
            backdrop-filter: blur(6px);
        }

        .memorias {
            margin-top: 60px;
            text-align: center;
        }

        .memorias h2 {
            color: #ff1b1b;
            margin-bottom: 20px;
            font-size: 2rem;
            text-shadow: 0 0 8px #780000;
        }

        .memorias p {
            font-size: 1.1rem;
            color: #ccc;
        }

        .media-item {
            margin-top: 25px;
        }

        footer {
            text-align: center;
            padding: 40px 20px;
            color: #777;
            margin-top: 60px;
        }

        .assinatura {
            text-align: right;
            margin-top: 30px;
            font-style: italic;
            color: #ff1b1b;
        }
    </style>
</head>
<body>

<!-- Canvas para partículas -->
<canvas id="particles"></canvas>

<header>
    <h1>Para Byanca ❤️</h1>
</header>

<div class="carta">
    <p>
        Byanca,
        <br><br>
        Acho lindo como algumas pessoas entram na nossa vida de forma tão inesperada…  
        e ainda assim conseguem tocar a gente de um jeito tão leve e tão verdadeiro.  
        A gente se conhece há tão pouco tempo, mas você tem sido uma das melhores coisas que me aconteceram, mesmo em meio a tudo que estou passando.
        <br><br>
        É estranho — no bom sentido — como sua presença trouxe calma.  
        Como se, mesmo sem pressa, mesmo sem pressão, existisse algo especial acontecendo aqui.
        <br><br>
        Não sei exatamente onde isso vai dar, mas sei que…  
        com carinho, respeito e verdade, a gente só tem a crescer juntos.
        <br><br>
        E eu quero que você saiba:  
        você tem sido luz.  
        E eu gosto muito do que estamos construindo, sem pressa e sem expectativas exageradas… apenas sendo quem somos.
    </p>

    <p class="assinatura">
        — Com carinho.
    </p>
</div>

<div class="memorias">
    <h2>Nossas Memórias (para adicionar depois)</h2>
    <p>Você pode colocar fotos e vídeos aqui. Basta substituir os arquivos no código.</p>

    <div class="media-item">
        <!-- EXEMPLO DE FOTO -->
        <img src="sua-foto-aqui.jpg" width="60%" style="border-radius:10px; display:none;">
    </div>

    <div class="media-item">
        <!-- EXEMPLO DE VÍDEO -->
        <video src="seu-video-aqui.mp4" width="60%" controls style="border-radius:10px; display:none;"></video>
    </div>
</div>


<footer>
    © 2025 — Feito especialmente para Byanca ❤️  
</footer>


<!-- SCRIPT DAS PARTÍCULAS -->
<script>
    const canvas = document.getElementById("particles");
    const ctx = canvas.getContext("2d");

    canvas.width = window.innerWidth;
    canvas.height = window.innerHeight;

    let particles = [];

    class Particle {
        constructor() {
            this.x = Math.random() * canvas.width;
            this.y = Math.random() * canvas.height;
            this.size = Math.random() * 2 + 0.5;
            this.speedX = (Math.random() - 0.5) * 0.4;
            this.speedY = (Math.random() - 0.5) * 0.4;
            this.opacity = Math.random() * 0.5 + 0.2;
        }

        draw() {
            ctx.fillStyle = `rgba(255, 0, 0, ${this.opacity})`;
            ctx.beginPath();
            ctx.arc(this.x, this.y, this.size, 0, Math.PI * 2);
            ctx.fill();
        }

        update() {
            this.x += this.speedX;
            this.y += this.speedY;

            // reposiciona quando sai da tela
            if (this.x < 0 || this.x > canvas.width) this.speedX *= -1;
            if (this.y < 0 || this.y > canvas.height) this.speedY *= -1;
        }
    }

    function initParticles() {
        particles = [];
        let count = 120; // partículas sutis
        for (let i = 0; i < count; i++) {
            particles.push(new Particle());
        }
    }

    function animate() {
        ctx.clearRect(0, 0, canvas.width, canvas.height);
        particles.forEach(p => {
            p.update();
            p.draw();
        });
        requestAnimationFrame(animate);
    }

    window.addEventListener("resize", () => {
        canvas.width = window.innerWidth;
        canvas.height = window.innerHeight;
        initParticles();
    });

    initParticles();
    animate();
</script>

</body>
</html>
