# Imba Chiken 
<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Онлайн-заказ еды</title>

    <style>
        body {
            margin: 0;
            font-family: Arial, sans-serif;
            background: #f7f7f7;
        }
        header {
            background: #ff4d4d;
            padding: 15px;
            color: white;
            text-align: center;
            font-size: 22px;
        }
        nav {
            background: #333;
            padding: 10px;
            display: flex;
            justify-content: center;
        }
        nav a {
            color: white;
            margin: 0 15px;
            text-decoration: none;
            font-size: 18px;
        }
        .menu {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 15px;
            padding: 15px;
        }
        .item {
            background: white;
            padding: 15px;
            border-radius: 10px;
            box-shadow: 0 2px 6px rgba(0,0,0,0.1);
            text-align: center;
        }
        .item img {
            width: 100%;
            border-radius: 10px;
        }
        .btn {
            background: #ff4d4d;
            padding: 10px;
            color: white;
            border: none;
            width: 100%;
            border-radius: 6px;
            cursor: pointer;
            margin-top: 10px;
        }
        #cart {
            position: fixed;
            bottom: 0;
            width: 100%;
            background: white;
            padding: 15px;
            border-top: 2px solid #ddd;
        }
        #checkout {
            background: #28a745;
            padding: 10px;
            color: white;
            width: 100%;
            border: none;
            border-radius: 6px;
            margin-top: 10px;
            cursor: pointer;
        }
    </style>
</head>

<body>

<header>Онлайн заказ — Ваша точка</header>

<nav>
    <a href="index.html">Меню</a>
    <a href="contacts.html">Контакты</a>
</nav>

<div class="menu">

    <div class="item">
        <img src="https://images.unsplash.com/photo-1606755962773-0c3f4a59e4a8?auto=format&w=600">
        <h3>Чизбургер</h3>
        <p>1600 тг</p>
        <button class="btn" onclick="addToCart('Чизбургер', 1600)">Добавить</button>
    </div>

    <div class="item">
        <img src="https://images.unsplash.com/photo-1601924582971-b7e8e1f1a3ed?auto=format&w=600">
        <h3>Пицца Маргарита</h3>
        <p>3500 тг</p>
        <button class="btn" onclick="addToCart('Пицца Маргарита', 3500)">Добавить</button>
    </div>

    <div class="item">
        <img src="https://images.unsplash.com/photo-1542838369-3e5374213964?auto=format&w=600">
        <h3>Картофель фри</h3>
        <p>750 тг</p>
        <button class="btn" onclick="addToCart('Картофель фри', 750)">Добавить</button>
    </div>

    <div class="item">
        <img src="https://images.unsplash.com/photo-1626082927389-6f3a0cc3726e?auto=format&w=600">
        <h3>Шаурма фирменная</h3>
        <p>1900 тг</p>
        <button class="btn" onclick="addToCart('Шаурма фирменная', 1900)">Добавить</button>
    </div>

</div>

<div id="cart">
    <h3>Корзина: <span id="total">0</span> тг</h3>
    <button id="checkout" onclick="makeOrder()">Оформить заказ</button>
</div>

<script>
    let total = 0;
    let order = [];

    function addToCart(name, price) {
        total += price;
        order.push({name, price});
        document.getElementById("total").innerText = total;
    }

    function makeOrder() {
        let text = "📦 Новый заказ:\n\n";
        order.forEach(item => {
            text += item.name + " — " + item.price + " тг\n";
        });
        text += "\nИтого: " + total + " тг";

        alert(text);

        total = 0;
        order = [];
        document.getElementById("total").innerText = 0;
    }
</script>

</body>
</html>
<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Контакты</title>

    <style>
        body {
            margin: 0;
            font-family: Arial, sans-serif;
            background: #fafafa;
        }
        header {
            background: #ff4d4d;
            padding: 15px;
            color: white;
            text-align: center;
            font-size: 22px;
        }
        nav {
            background: #333;
            padding: 10px;
            display: flex;
            justify-content: center;
        }
        nav a {
            color: white;
            margin: 0 15px;
            text-decoration: none;
            font-size: 18px;
        }
        .box {
            padding: 20px;
        }
        .map {
            width: 100%;
            height: 300px;
            border: none;
            border-radius: 10px;
        }
    </style>
</head>

<body>

<header>Контакты и адрес</header>

<nav>
    <a href="index.html">Меню</a>
    <a href="contacts.html">Контакты</a>
</nav>

<div class="box">
    <h2>Наш адрес:</h2>
    <p><b>📍 г. Алматы, ул. Примерная 12</b></p>

    <h2>Телефон:</h2>
    <p><b>📞 +7 777 000 00 00</b></p>

    <h2>Часы работы:</h2>
    <p>🕒 10:00 — 23:00</p>

    <h2>Карта:</h2>
    <iframe 
        class="map"
        src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d2668.997!2d76.934!3d43.238!2m3!"
        allowfullscreen="">
    </iframe>
</div>

</body>
</html>
  

