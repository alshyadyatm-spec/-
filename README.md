# -
لعبة عبارة عن مصمم ازياء
<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Mini Nikki Designer</title>
<style>
  body {
    font-family: Arial, sans-serif;
    text-align: center;
    background: #ffe6f0;
    margin: 0;
    padding: 0;
  }
  h1 { color: #d63384; }
  .designer {
    margin: 20px auto;
    padding: 20px;
    background: #fff0f5;
    border-radius: 15px;
    width: 300px;
  }
  button, select {
    margin: 10px 0;
    padding: 10px;
    font-size: 16px;
    border-radius: 10px;
    border: 1px solid #d63384;
    cursor: pointer;
  }
  img {
    width: 150px;
    margin-top: 10px;
    border-radius: 10px;
  }
  #result {
    margin-top: 15px;
    font-size: 18px;
    color: #d63384;
  }
</style>
</head>
<body>
<h1>Mini Nikki Designer</h1>
<div class="designer">
  <label>اختاري نوع القماش:</label><br>
  <select id="fabric">
    <option value="حرير">حرير</option>
    <option value="قطن">قطن</option>
    <option value="دانتيل">دانتيل</option>
  </select><br>

  <label>اختاري اللون:</label><br>
  <select id="color">
    <option value="أحمر">أحمر</option>
    <option value="أزرق">أزرق</option>
    <option value="وردي">وردي</option>
  </select><br>

  <label>اختاري القصّة:</label><br>
  <select id="style">
    <option value="فستان">فستان</option>
    <option value="بلوزة">بلوزة</option>
    <option value="تنورة">تنورة</option>
  </select><br>

  <button onclick="createDesign()">اعرض التصميم</button>

  <div id="result"></div>
  <img id="model" src="https://via.placeholder.com/150" alt="عارضة">
</div>

<audio id="bgMusic" autoplay loop>
  <source src="https://www.soundhelix.com/examples/mp3/SoundHelix-Song-1.mp3" type="audio/mpeg">
</audio>

<script>
function createDesign() {
  const fabric = document.getElementById('fabric').value;
  const color = document.getElementById('color').value;
  const style = document.getElementById('style').value;

  // تغيير صورة العارضة (مثال بسيط)
  const img = document.getElementById('model');
  img.src = `https://via.placeholder.com/150/${color === 'أحمر' ? 'ff6666' : color === 'أزرق' ? '6699ff' : 'ff99cc'}/ffffff?text=${style}`;

  // عرض النتيجة
  document.getElementById('result').innerText = `قماش: ${fabric}, لون: ${color}, قصّة: ${style} 🌟`;
}
</script>
</body>
</html>
