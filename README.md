<!DOCTYPE html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Sigara Bağımlılık Testi</title>
    <style>
        body {
            font-family: "Times New Roman", serif;
            background-color: #000000; /* Arka plan siyah */
            color: white; /* Yazı rengi beyaz */
            margin: 0;
            padding: 0;
        }
        .container {
            max-width: 600px;
            margin: auto;
            padding: 20px;
            text-align: left;
        }
        .question {
            margin: 15px 0;
        }
        button {
            margin-top: 20px;
            padding: 10px 20px;
            font-size: 16px;
            cursor: pointer;
            background-color: #444444; /* Buton arka plan rengi */
            color: white;
            border: none;
            border-radius: 5px;
        }
        button:hover {
            background-color: #555555; /* Buton hover efekti */
        }
    </style>
</head>
<body>
    <div class="container">
        <h2>Sigara Bağımlılık Testi</h2>
        <p>Bu test sigara bağımlılığınızı ölçmek için hazırlanmıştır. Soruları dikkatlice cevaplayın.</p>
        
        <form id="testForm">
            <div class="question">
                <label>1. Uyandıktan ne kadar sonra ilk sigaranızı içiyorsunuz?</label><br>
                <input type="radio" name="q1" value="3"> İlk 5 dakika içinde<br>
                <input type="radio" name="q1" value="2"> 6-30 dakika içinde<br>
                <input type="radio" name="q1" value="1"> 31-60 dakika içinde<br>
                <input type="radio" name="q1" value="0"> 60 dakikadan sonra
            </div>
            
            <div class="question">
                <label>2. Sigara içmenin yasak olduğu yerlerde, sigara içmemek zor geliyor mu?</label><br>
                <input type="radio" name="q2" value="1"> Evet<br>
                <input type="radio" name="q2" value="0"> Hayır
            </div>
            
            <div class="question">
                <label>3. Hangi sigarayı bırakmak sizin için daha zor?</label><br>
                <input type="radio" name="q3" value="1"> Sabah ilk sigaram<br>
                <input type="radio" name="q3" value="0"> Diğerleri
            </div>
            
            <div class="question">
                <label>4. Her gün ortalama kaç adet sigara içiyorsunuz?</label><br>
                <input type="radio" name="q4" value="0"> 10 veya daha az<br>
                <input type="radio" name="q4" value="1"> 11-20<br>
                <input type="radio" name="q4" value="2"> 21-30<br>
                <input type="radio" name="q4" value="3"> 31 ve üzeri
            </div>
            
            <div class="question">
                <label>5. Uyandığınız ilk saat içinde, günün diğer saatlerinden daha fazla sigara içiyor musunuz?</label><br>
                <input type="radio" name="q5" value="1"> Evet<br>
                <input type="radio" name="q5" value="0"> Hayır
            </div>
            
            <div class="question">
                <label>6. Hasta olduğunuz günlerde bile sigara içiyor musunuz?</label><br>
                <input type="radio" name="q6" value="1"> Evet<br>
                <input type="radio" name="q6" value="0"> Hayır
            </div>
            
            <button type="button" onclick="calculateScore()">Sonucu Gör</button>
        </form>
        
        <h3 id="result"></h3>
    </div>
    
    <script>
        function calculateScore() {
            let totalScore = 0;
            for (let i = 1; i <= 6; i++) {
                let selected = document.querySelector('input[name="q' + i + '"]:checked');
                if (selected) {
                    totalScore += parseInt(selected.value);
                }
            }
            
            let resultText = "";
            if (totalScore >= 8) {
                resultText = "Yüksek derecede bağımlısınız. Bir uzmana danışmalısınız.";
            } else if (totalScore >= 5) {
                resultText = "Orta seviyede bağımlısınız. Sigarayı bırakmayı düşünebilirsiniz.";
            } else {
                resultText = "Düşük bağımlılık seviyeniz var. Sigarayı bırakmak sizin için daha kolay olabilir.";
            }
            
            document.getElementById("result").innerText = "Puanınız: " + totalScore + " - " + resultText;
        }
    </script>
</body>
</html>
