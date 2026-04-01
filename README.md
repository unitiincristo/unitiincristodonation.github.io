<!DOCTYPE html>
<html lang="it">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Sostieni la nostra Comunità - Uniti In Cristo</title>
    <style>
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background-color: #000000; /* Sfondo pagina totalmente nero */
            margin: 0;
            padding: 0;
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
        }
        .card {
            background-color: #1a1a1a; /* Sfondo centrale grigio scuro */
            width: 100%;
            max-width: 400px;
            border-radius: 20px;
            overflow: hidden;
            box-shadow: 0 10px 30px rgba(0,0,0,0.5);
            text-align: center;
            padding: 40px 25px; /* Aumentato padding superiore */
            border: none;
        }
        
        /* Contenitore del logo circolare staccato dai bordi */
        .logo-container {
            display: flex;
            justify-content: center;
            margin-bottom: 30px;
        }
        
        /* Maschera circolare per l'immagine rettangolare */
        .circular-logo {
            width: 120px; /* Dimensione del cerchio */
            height: 120px;
            border-radius: 50%; /* Questa è la 'magia' che crea il cerchio */
            background-image: url('copertina.jpg'); /* INSERISCI QUI IL NOME DEL TUO FILE IMMAGINE */
            background-size: cover; /* Centra l'immagine rettangolare nel cerchio */
            background-position: center;
            box-shadow: 0 4px 10px rgba(0,0,0,0.5);
            border: 2px solid #333; /* Un piccolo bordo scuro per definire il cerchio */
        }
        
        .content {
            padding: 0;
        }
        h1 {
            font-size: 26px;
            color: #ffffff;
            margin: 0 0 10px 0;
            /* Rimosso text-transform: uppercase; */
            letter-spacing: 1px;
            font-weight: bold;
        }
        h2 {
            font-size: 15px;
            color: #aaaaaa; /* Grigio più scuro per sottotitolo */
            margin-bottom: 40px;
            font-weight: 300;
        }
        
        .btn {
            display: flex;
            align-items: center;
            justify-content: center;
            width: 100%;
            padding: 16px 0;
            margin-bottom: 15px;
            border-radius: 12px;
            text-decoration: none;
            font-weight: bold;
            font-size: 16px;
            transition: all 0.3s ease;
            border: none;
            cursor: pointer;
        }
        .btn:hover {
            transform: translateY(-2px);
            filter: brightness(1.1);
        }
        
        /* PayPal: Colore Originale */
        .btn-paypal {
            background-color: #0070ba;
            color: white;
        }
        
        /* Bonifico: Stile Palette (Bianco su Grigio Scuro) */
        .btn-bank {
            background-color: #333333;
            color: #ffffff;
        }
        
        .btn img {
            width: 22px;
            height: 22px;
            margin-right: 12px;
        }
        
        .iban-container {
            margin-top: 30px;
            padding: 15px;
            background-color: rgba(255, 255, 255, 0.03); /* Sfondo ultra-leggero per l'IBAN */
            border-radius: 12px;
            border: 1px solid rgba(255, 255, 255, 0.05);
        }
        .iban-text {
            font-family: 'Courier New', Courier, monospace;
            font-size: 14px;
            display: block;
            margin-bottom: 8px;
            color: #ffffff;
            letter-spacing: 1px;
            word-break: break-all;
        }
        .copy-hint {
            font-size: 11px;
            color: #888;
        }
    </style>
</head>
<body>

<div class="card">
    <div class="logo-container">
        <div class="circular-logo"></div>
    </div>
    
    <div class="content">
        <h1>Uniti In Cristo</h1>
        <h2>Dona ora</h2>

        <a href="https://paypal.me/unitincristo" target="_blank" class="btn btn-paypal">
            <img src="https://img.icons8.com/color/48/000000/paypal.png" alt="PayPal">
            PayPal
        </a>

        <button onclick="copyData()" class="btn btn-bank">
            <img src="https://img.icons8.com/metro/26/ffffff/bank.png" alt="Bonifico">
            Bonifico
        </button>

        <div class="iban-container">
            <strong class="iban-text" id="ibanText">IT79 T076 0112 1000 0104 9342 510</strong>
            <span class="copy-hint" id="copyHint">
                BIC: BPPIITRRXXX<br>
                Intestatario: ASSOCIAZIONE CRISTIANA EVANGELICA IN CRISTO
            </span>
        </div>
    </div>
</div>

<script>
    function copyData() {
        const iban = document.getElementById('ibanText').innerText;
        const name = "ASSOCIAZIONE CRISTIANA EVANGELICA IN CRISTO";
        const bic = "BPPIITRRXXX";
        
        // Copia IBAN pulito (senza spazi) e intestatario
        const fullData = "Intestatario: " + name + "\nIBAN: " + iban + "\nBIC: " + bic;
        
        navigator.clipboard.writeText(fullData).then(() => {
            alert("Dati bancari copiati negli appunti!\n\nOra puoi incollarli nella tua app bancaria.");
        });
    }
</script>

</body>
</html>
