<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Primer proyecto js</title>
    <link rel="stylesheet" href="./css/style.css">
    
</head>
<body>
    <div class="container">
        <div class="calculator dark">
            <div class="theme-toggler active">
                <i class="toggler-icon"></i>
            </div> 
            <div class="display-screen">
                <div id="display"></div>
            </div>
            <div class="buttons">
                <table>
                    <tr>
                        <td><button class="btn-operator" id="clear">C</button></td>
                        <td><button class="btn-operator" id="/">/</button></td>
                        <td><button class="btn-operator" id="*">X</button></td>
                        <td><button class="btn-operator" id="backspace"><</button></td>

                    </tr>
                    <tr>
                        <td><button class="btn-number" id="7">7</button></td>
                        <td><button class="btn-number" id="8">8</button></td>
                        <td><button class="btn-number" id="9">9</button></td>
                        <td><button class="btn-operator" id="-">-</button></td>
                    </tr>
                    <tr>
                        <td><button class="btn-number" id="4">4</button></td>
                        <td><button class="btn-number" id="5">5</button></td>
                        <td><button class="btn-number" id="6">6</button></td>
                        <td><button class="btn-operator" id="+">+</button></td>
                    </tr>
                    <tr>
                        <td><button class="btn-number" id="1">1</button></td>
                        <td><button class="btn-number" id="2">2</button></td>
                        <td><button class="btn-number" id="3">3</button></td>
                        <td rowspan="2"><button class="btn-equal" id="equal">=</button></td>
                    </tr>
                    <tr>
                    <td><button class="btn-number" id=".">.</button></td>
                    <td><button class="btn-number" id="0">0</button></td>
                    <td><button class="btn-number" id="00">00</button></td>
                    </tr>    
                </table>
            </div>
    </div>
    <script src="script.js"></script>
</body>
</html>

<!-- Javascript-->
const display= document.querySelector("#display")
const buttons= document.querySelectorAll("button")

buttons.forEach((item)=>{
    item.onclick=()=>{
        if(item.id=="clear"){

            display.innerText="";
        }else if(item.id=="backspace"){
            let string = display.innerText.toString();
            display.innerText=string.substr(0,string.lenght-1);

        }else if(display.innerText !=""&& item.id=="equal"){
            display.innerText= eval(display.innerText)
            
        }else if(display.innerText=="" && item.id=="equal"){
            display.innerText="Null";
            setTimeout(()=>(display.innerHTML=""), 2000);

        } else{
            display.innerText+=item.id;

        }
    }
})

const themeToggleBtn = document.querySelector('.theme-toggler');
const toggleIcon = document.querySelector('toggler-icon')
const calculator = document.querySelector('.calculator')
let isDark=true;
themeToggleBtn.onclick = () =>{
    calculator.classList.toggle('dark')
    themeToggleBtn.classList.toggle("active")
    isDark=!isDark;
};
