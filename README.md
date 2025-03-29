<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Воссоединение с Анной - Дарк Фэнтези</title>
    <style>
        body {
            background-color: #333;
            color: white;
            font-family: Arial, sans-serif;
            text-align: center;
            margin: 0;
            padding: 0;
        }
        canvas {
            border: 1px solid #fff;
        }
    </style>
</head>
<body>
    <h1>Воссоединение с Анной</h1>
    <canvas id="gameCanvas" width="800" height="600"></canvas>
    <script>
        // Получаем ссылку на канвас и контекст
        const canvas = document.getElementById('gameCanvas');
        const ctx = canvas.getContext('2d');

        // Настройки шрифтов
        ctx.font = "30px Arial";
        ctx.fillStyle = "#fff";

        // Начальные параметры
        let level = 1;
        let answer = "Тень";

        // Рисуем текст на экране
        function drawText(text, x, y) {
            ctx.fillText(text, x, y);
        }

        // Основная логика игры
        function gameLoop() {
            ctx.clearRect(0, 0, canvas.width, canvas.height);  // Очищаем экран

            if (level === 1) {
                // Загадка на уровне 1
                drawText("Загадка: Что может быть как огонь, но не сжигает?", 50, 100);
                drawText("Введите ответ:", 50, 200);
                drawText("Тень", 50, 250);
                setTimeout(() => {
                    if (prompt("Введите ответ:") === answer) {
                        level = 2;  // Переход к следующему уровню
                        showMessage("Правильный ответ! Дверь открыта...");
                    } else {
                        showMessage("Неправильный ответ. Попробуй снова.");
                    }
                }, 1000);
            }

            if (level === 2) {
                // Переход на следующий уровень
                drawText("Ты нашел Анну!", 250,
