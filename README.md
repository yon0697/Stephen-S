<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Stephen S</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.4/css/all.min.css" integrity="sha512-MY95wDmZbULsGh7unYMj0hIYbZiMjeaM5K7Al5NSP2YjKpN/3/7q3kZ5nAwEMb+1fy0N+XGK/XUawVvOV0Zqew==" crossorigin="anonymous" referrerpolicy="no-referrer" />
    <style>
        body {
            font-family: 'Arial', sans-serif;
            margin: 0;
            padding: 0;
            background-color: #0c0f16;
            color: #fff;
            display: flex;
            justify-content: flex-start;
            align-items: flex-start;
            flex-direction: column;
            min-height: 100vh; /* Menjamin halaman selalu penuh tinggi */
        }
        .sidebar {
            background-color: #2f3136;
            width: 250px;
            height: 100vh;
            position: fixed;
            left: 0;
            top: 0;
            padding: 20px 0;
            box-sizing: border-box;
            z-index: 1000;
            overflow-y: auto; /* Menambahkan overflow-y untuk scrollbar jika konten lebih panjang */
            display: flex;
            flex-direction: column;
            align-items: center;
        }
        .sidebar img {
            width: 80px; /* Mengurangi ukuran gambar */
            height: 80px; /* Mengurangi ukuran gambar */
            border-radius: 50%;
            object-fit: cover; /* Memastikan gambar tidak terdistorsi */
            margin-bottom: 10px;
        }
        .sidebar h2 {
            color: #fff;
            margin-bottom: 5px;
            font-size: 1.5em;
            text-align: center;
        }
        .sidebar p {
            font-size: 0.9em;
            text-align: center;
            margin-bottom: 15px;
            color: #b9bbbe;
        }
        .sidebar .status {
            display: flex;
            align-items: center;
            justify-content: center;
            margin-bottom: 10px; /* Mengurangi jarak dari bawah */
        }
        .sidebar .status span {
            color: #43b581;
            font-size: 0.8em;
            margin-left: 5px;
        }
        .sidebar .social-icons {
            margin-top: auto;
            display: flex;
            justify-content: center;
            align-items: center;
            width: 100%;
            margin-bottom: 30px;
        }
        .sidebar .social-icons a {
            display: inline-block;
            text-decoration: none;
            color: #b9bbbe;
            font-size: 1.2em;
            margin: 0 10px;
            transition: color 0.3s;
        }
        .sidebar .social-icons a:hover {
            color: #fff;
        }
        .sidebar nav {
            width: 100%;
            margin-top: auto;
        }
        .sidebar nav ul {
            list-style-type: none;
            padding: 0;
            margin: 0;
            text-align: center;
            margin-top: 0; /* Mengurangi jarak dari atas */
        }
        .sidebar nav ul li {
            margin-bottom: 10px;
            position: relative;
        }
        .sidebar nav ul li a {
            color: #b9bbbe;
            text-decoration: none;
            font-size: 1em;
            transition: color 0.3s;
            display: block;
            padding: 10px 20px;
            border-radius: 5px;
        }
        .sidebar nav ul li a:hover {
            color: #fff;
            background-color: #7289da;
        }
        .sidebar nav ul li.active a {
            color: #fff;
            background-color: #7289da;
        }
        .sidebar nav ul li::before {
            content: '';
            position: absolute;
            top: 50%;
            left: 0;
            transform: translateY(-50%);
            width: 4px;
            height: 0;
            background-color: transparent;
            transition: height 0.3s;
        }
        .sidebar nav ul li:hover::before,
        .sidebar nav ul li.active::before {
            height: 100%;
            background-color: #7289da;
        }
        .sidebar .online-menu {
            margin-top: 10px; /* Menambahkan jarak di atas menu */
        }
        .content {
            margin-left: 250px; /* Adjusted for sidebar width */
            padding: 80px 20px;
            color: #fff;
            width: calc(100% - 250px); /* Adjusted for sidebar width */
            box-sizing: border-box;
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr)); /* Changed minmax value */
            grid-gap: 20px;
        }
        .custom-card {
            background-color: #2f3136;
            padding: 15px;
            border-radius: 8px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
            transition: transform 0.3s ease;
            height: 100%; /* Ensuring cards are equal height */
            width: 100%; /* Controlling card width */
            max-width: 300px; /* Limiting maximum width */
            position: relative;
            overflow: hidden;
            display: flex;
            flex-direction: column;
            align-items: center; /* Centering content vertically */
            text-align: center; /* Centering text */
        }
        .custom-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(114, 137, 218, 0.2);
            z-index: -1;
            opacity: 0;
            transition: opacity 0.3s ease;
        }
        .custom-card:hover::before {
            opacity: 1;
        }
        .custom-card:hover {
            transform: translateY(-5px); /* Hover effect */
        }
        .custom-card h3 {
            color: #fff;
            font-size: 1em; /* Adjusted font size */
            margin-bottom: 10px;
        }
        .custom-card p {
            color: #b9bbbe;
            font-size: 0.8em; /* Adjusted font size */
            line-height: 1.5;
            margin-bottom: 10px; /* Increased margin bottom */
        }
        .custom-card a {
            color: #7289da; /* Warna teks link */
            text-decoration: none;
            transition: color 0.3s;
            position: relative;
        }

        .custom-card a:hover {
            color: #fff; /* Warna teks saat hover */
        }
        .footer {
            background-color: #2f3136;
            color: #b9bbbe;
            padding: 20px 0;
            width: 100%;
            text-align: center;
            margin-top: auto;
        }
	</meta>
    </style>
</head>
<body>
    <div class="sidebar">
        <img src="https://via.placeholder.com/150" alt="Profile Picture">
        <h2>Stephen S</h2>
        <p>Game Streamer</p>
        <div class="status">
            <i class="fas fa-circle"></i>
            <span>RF EPIC OFFICIAL STREAMER</span>
        </div>
        <nav>
            <ul class="online-menu">
                <li class="active"><a href="#">Home</a></li>
                <li><a href="https://www.instagram.com/stephen.sin8/">Instagram</a></li>
                <li><a href="https://www.youtube.com/@stephen.s8">Youtube</a></li>
                <li><a href="https://www.tiktok.com/@stephen.sin8">Tiktok</a></li>
		<p><p> ---Support Me--- </p></p>
                <li><a href="https://saweria.co/StephenSin">Saweria</a></li>
            </ul>
        </nav>
        <div class="social-icons">
            <a href="https://www.instagram.com/stephen.sin8/" target="_blank"><i class="fab fa-instagram"></i></a>
            <a href="https://www.youtube.com/@stephen.s8" target="_blank"><i class="fab fa-youtube"></i></a>
            <a href="C:\Users\User\Desktop\My_Pages\tiktok.png" target="_blank"><i class="fab fa-tiktok"></i></a>
        </div>
    </div>
    <div class="content">
        <div class="custom-card">
            <img src="Epic_logo.gif" alt="RF EPIC Image" style="width: 100%; height: auto;">
            <h3>RF EPIC</h3>
            <p>Embark on an epic adventure in RF EPIC, a new version of the classic MMORPG RF Online.</p>
            <a href="https://www.epicfullpvp.com" target="_blank">Join Now</a>
        </div>
    </div>
    <footer class="footer">
        &copy; 2024 Stephen S. All rights reserved.
    </footer>
</body>
</html>
