<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>OR code generator</title>
    <link rel="stylesheet" href="ORCODE.css">
</head>

<body>
    <div class="conatiner">
        <h1 style="text-align:center"> Text and URL</h1>

        <div class="inimg">
            <input type="text" placeholder="Text or URL" id="qrText">
            <img src="images/copy.png" alt="">
        </div>

        <div class="imgbox">
            <img src="" id="qrimg">
        </div>
        <button onclick="generateqr()">Generate QR code</button>
    </div>

    <script>
        let imgbox = document.getElementById("imgbox");
        let qrimg = document.getElementById("qrimg");
        let qrText = document.getElementById("qrText")


        function generateqr() {
            if (qrText.value.length > 0) {
                qrimg.src = "https://api.qrserver.com/v1/create-qr-code/?size=150x150&data=" + qrText.value;
                imgbox.classList.add("show-img");
            }else{
                qrText.classList.add("error");
                setTimeout(()=>{
                    qrText.classList.remove("error");
                },1000);
            }

        }
    </script>
</body>

</html>
