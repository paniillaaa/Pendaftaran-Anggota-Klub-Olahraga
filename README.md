# Pendaftaran-Anggota-Klub-Olahraga

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Formulir Pendaftaran Anggota Klub Olahraga</title>
    <link rel="stylesheet" href="fani.css" />
    <style>
        body {
            background-color: beige;
            background-image: url('abiid.jpg');
            background-size: cover;
            background-position: center;
            background-repeat: no-repeat;
            padding: 20px;
            font-family: Arial, sans-serif;
            text-align: center;
        }
        header {
            background-color: rgba(191, 202, 216, 0.8); /* Warna latar header transparan */
            color: rgba(0, 0, 0, 0.8); /* Semi-transparent text */
            padding: 10px;
        }
        h1 {
            margin: 0; /* Remove default margin */
            padding: 0; /* Remove default padding */
            opacity: 0.8; /* Adjust transparency */
        }
        form {
            display: inline-block;
            text-align: left;
            padding: 20px;
            position: relative; /* Untuk menempatkan pseudo-element */
        }
        form::before {
            content: "";
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background-color: rgba(0, 0, 255, 0.2); /* Warna biru transparan */
            border-radius: 10px; /* Agar berbentuk melengkung */
            z-index: -1; /* Untuk memastikan pseudo-element berada di bawah form */
        }
        fieldset {
            border: none;
            padding: 0;
            margin: 0;
        }
        label {
            display: block;
            margin-bottom: 5px;
        }
        input[type="text"],
        input[type="email"],
        input[type="tel"],
        input[type="date"],
        input[type="url"],
        textarea,
        select {
            width: calc(50% - 10px);
            padding: 8px;
            margin-bottom: 10px;
            border: 1px solid #ccc;
            border-radius: 4px;
            box-sizing: border-box;
        }
        input[type="radio"],
        input[type="checkbox"] {
            margin-right: 5px;
            margin-bottom: 5px;
            transform: scale(0.8); /* Mengubah ukuran checkbox */
        }
        input[type="submit"],
        input[type="reset"] {
            background-color: #4CAF50;
            color: white;
            padding: 10px 20px;
            border: none;
            border-radius: 4px;
            cursor: pointer;
        }
        input[type="submit"]:hover,
        input[type="reset"]:hover {
            background-color: #45a049;
        }
        .availability-checkboxes label {
            display: inline-block;
            width: 45%;
            margin-bottom: 10px;
        }
    </style>
</head>
<body>
    <header>
        <h1>Pendaftaran Anggota Klub Olahraga</h1>
        <p>Pengisian Formulir Pendaftaran Klub Olahraga</p>
    </header>
    <form>
        <h2>Pengisian Data Diri Calon Anggota</h2>
        <fieldset>
            <legend>Data Pribadi</legend>
            <label for="fullname">Nama Lengkap:</label>
            <input type="text" id="fullname" name="fullname" required>
            
            <label for="email">Alamat Email:</label>
            <input type="email" id="email" name="email" required>
            
            <label for="phone">Nomor Telepon:</label>
            <input type="tel" id="phone" name="phone" required>
            
            <label for="birthdate">Tanggal Lahir:</label>
            <input type="date" id="birthdate" name="birthdate" required>
            
            <div>
                <label>Jenis Kelamin:</label><br>
                <input type="radio" id="wanita" name="gender" value="wanita" required>
                <label for="wanita">Perempuan</label><br>
                <input type="radio" id="laki-laki" name="gender" value="laki-laki" required>
                <label for="laki-laki">Laki-laki</label>
            </div>
            
            <label for="address">Alamat Rumah:</label>
            <textarea id="address" name="address" required></textarea>
            
            <label for="city">Kota:</label>
            <input type="text" id="city" name="city" required>
            
            <label for="zipcode">Kode Pos:</label>
            <input type="text" id="zipcode" name="zipcode" required>
            
            <label for="sports">Cabang Olahraga Pilihan:</label>
            <select id="sports" name="sports" required>
                <option value="soccer">Sepak Bola</option>
                <option value="basketball">Bola Basket</option>
                <option value="volleyball">Bola Voli</option>
                <option value="badminton">Bulutangkis</option>
            </select>
            
            <label for="history">Riwayat Olahraga Sebelumnya:</label>
            <textarea id="history" name="history"></textarea>
            
            <div class="availability-checkboxes">
                <label for="senin"><input type="checkbox" id="senin" name="availability" value="Senin"> Senin</label>
                <label for="selasa"><input type="checkbox" id="selasa" name="availability" value="Selasa"> Selasa</label><br>
                <label for="rabu"><input type="checkbox" id="rabu" name="availability" value="Rabu"> Rabu</label>
                <label for="kamis"><input type="checkbox" id="kamis" name="availability" value="Kamis"> Kamis</label><br>
                <label for="jumat"><input type="checkbox" id="jumat" name="availability" value="Jumat"> Jumat</label>
                <label for="sabtu"><input type="checkbox" id="sabtu" name="availability" value="Sabtu"> Sabtu</label><br>
                <label for="minggu"><input type="checkbox" id="minggu" name="availability" value="Minggu"> Minggu</label>
            </div>
            
            <label for="instagram">Instagram:</label>
            <input type="url" id="instagram" name="instagram" placeholder="https://www.instagram.com/">
            
            <label for="twitter">Twitter:</label>
            <input type="url" id="twitter" name="twitter" placeholder="https://www.twitter.com/">
            
            <label for="facebook">Facebook:</label>
            <input type="url" id="facebook" name="facebook" placeholder="https://www.facebook.com/">
            
            <br><br>
            <input type="reset" value="Reset">
            <input type="submit" value="Daftar">
        </fieldset>
    </form>
    <script>
        function toggleAvailability(day) {
            var availabilityInput = document.getElementById(day);
            availabilityInput.checked = !availabilityInput.checked;
            if (availabilityInput.checked) {
                availabilityInput.style.backgroundColor = "#4CAF50"; // Warna hijau ketika dipilih
            } else {
                availabilityInput.style.backgroundColor = ""; // Kosongkan warna ketika tidak dipilih
            }
        }
    </script>
</body>
</html>
