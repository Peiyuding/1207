<!DOCTYPE html>
<html lang="zh-TW">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>建築構造與施工測驗</title>
    <style>
        body { font-family: Arial, sans-serif; margin: 20px; }
        .question { margin-bottom: 15px; }
        button { margin-top: 20px; padding: 10px; font-size: 16px; }
    </style>
</head>
<body>
    <h2>建築構造與施工測驗</h2>
    <form id="quizForm">
        <script>
            let questions = [
                { q: "下列有關鋼材一般力學性能特性之描述何者錯誤？", options: ["鋼材降伏強度愈高，伸長率趨於愈低", "鋼材降伏強度愈高，降伏比趨於愈高", "鋼材降伏強度愈低，鋼板厚度方向斷面縮率趨於愈高", "鋼材降伏強度愈低，應變硬化趨於顯著"], answer: "C" },
                { q: "關於建築物減排實現方式來說，下列敘述何者錯誤？", options: ["蘊含能源可以透過優化建築結構來減少材料使用", "幾乎所有蘊含碳排放在建築物的初始建造階段發生", "運營能源的節約可透過節能電器與絕緣材料來實現", "運營能源節約可以透過減少材料使用來降低"], answer: "D" }
            ];
            
            let answers = {
                "q1": "C", "q2": "D", "q3": "B", "q4": "C", "q5": "D", "q6": "A", "q7": "C", "q8": "D",
                "q9": "A", "q10": "B", "q11": "C", "q12": "D", "q13": "A", "q14": "B", "q15": "C", "q16": "D",
                "q17": "A", "q18": "B", "q19": "C", "q20": "D", "q21": "A", "q22": "B", "q23": "C", "q24": "D",
                "q25": "A", "q26": "B", "q27": "C", "q28": "D", "q29": "A", "q30": "B", "q31": "C", "q32": "D",
                "q33": "A", "q34": "B", "q35": "C", "q36": "D", "q37": "A", "q38": "B", "q39": "C", "q40": "D"
            };
            
            let formHTML = "";
            for (let i = 1; i <= 80; i++) {
                let qKey = "q" + i;
                formHTML += `<div class='question'><p>${i}. 題目內容...</p>`;
                ["A", "B", "C", "D"].forEach(opt => {
                    formHTML += `<label><input type='radio' name='${qKey}' value='${opt}'> ${opt} 選項內容</label><br>`;
                });
                formHTML += "</div>";
            }
            
            document.write(formHTML + `<button type='button' onclick='submitQuiz()'>提交測驗</button>`);
        </script>
    </form>
    <p id="result"></p>
    
    <script>
        function submitQuiz() {
            let score = 0;
            let totalQuestions = Object.keys(answers).length;
            
            for (let key in answers) {
                let selected = document.querySelector(`input[name="${key}"]:checked`);
                if (selected && selected.value === answers[key]) {
                    score++;
                }
            }
            
            document.getElementById("result").innerText = `你的得分：${score} / ${totalQuestions}`;
        }
    </script>
</body>
</html>
