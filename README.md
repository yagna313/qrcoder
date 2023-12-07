# qrcoder
index.html
<!DOCTYPE html>
<html>
    <head>
        <meta name="viewport" content="width-device-width, initial-scale=1.0">
        <title> Qr code generater using html css and java script</title>
        <link rel="stylesheet" href="style.css">
    </head>
    <body>
        <div class="container">
            <p> Enter your text or URL</p>
            <input type="text" placeholder="text or URL" id="qrText">
            <div id="imgBox">
                <img src="" id="qrimage">

            </div>

            <button onclick="GenerateQR()">Generate QR Code</button>
        </div>
        <script>
            let imgBox = document.getElementById("imgBox");  
            let qrimage = document.getElementById("qrimage");
            let qrText = document.getElementById("qrText");      

           function GenerateQR(){
               qrimage.src ="https://api.qrserver.com/v1/create-qr-code/?size=150x150&data=" + qrText.value;
              imgBox.classList.add("show-img");
            }
            
        </script>
    </body>
</html>
style.css
*{
    margin: 0;
    padding: 0;
    font-family: sans-serif;
    box-sizing: border-box;
}
body {
    background-color: #262a2f;

}
.container {
    width: 400px;
    padding: 25px 35px;
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%,-50%);
    background: #fff;
    border-radius: 10px;
}
.container p{
    font-weight: 600;
    font-size: 15px;
    margin-bottom: 8px;

}
.container input{
    width: 100%;
    height: 50px;
    border: 1px solid #494eea;
    outline: 0;
    padding: 10px;
    margin: 10px 0 20px;
    border-radius: 5px ;
}
.container button{
    width: 100%;
    height: 50px;
    background-color: #494eea;
    color: #fff;
    border: 0;
    outline: 0;
    border-radius: 5px;
    box-shadow: 0 10px 10px rgba(0, 0, 0, 0.1);
    cursor: pointer;
    margin: 20px 0;
    font-weight: 500;
} 
#imgBox{
    width: 200px;
    border-radius: 5px;
    max-height: 0;
    overflow: hidden;
    transition: max-height 1s;
}
#imgBox img{
    width: 100%;
    padding: 10px;
}
#imgBox.show-img{
    max-height: 300px;
    margin: 10px auto;
    border: 1px solid #d1d1d1;

}
