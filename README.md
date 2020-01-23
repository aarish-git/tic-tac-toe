                                       TIC-TAC-TOE GAME
                                     _____________________
				     
				     

 <!DOCTYPE html>
<html>
    <head>
        <title>Javascript TIC TAC TOE</title>
        <meta charset="utf-8">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        
        <style>
            
            *{box-sizing: border-box}
            
            .container{width: 300px;
                       overflow: hidden;
                       margin: 50px auto 0 auto;
                     }
            
            .container span{width: 100%;
                            display: block;
                            text-align: center;
                            font-family: sans-serif;
                            color: #fff;
                            font-size: 25px;
                            background: #1D5686;
                           }
            
            .container input[type=button]{float: left;
                            width: 100px;
                            height: 100px;
                            border: 1px solid #000;
                            font-size: 85px;
                            text-align: center;
                            line-height: 100px; 
                            cursor: pointer;
                          }
            
            button{background: red;
                   color: #fff;
                   font-weight: bold;
                   border: 1px solid ;
                    cursor: pointer; 
                    width: 200px;
                    height: 40px; 
                    font-size: 22px;
                    display: block;
                    margin: 10px auto}
            
            .win{background: #F9690E; color: #fff}
            
        </style>
        
    </head>
    <body>
       
        <div class="container" id="main">
            <span id="turn">Play</span>
            <!-- show X or O on div click -->
            <input type="button" class="btn" id="btn1" onclick="clickBtn('btn1')">
            <input type="button" class="btn" id="btn2" onclick="clickBtn('btn2')">
            <input type="button" class="btn" id="btn3" onclick="clickBtn('btn3')">
            <input type="button" class="btn" id="btn4" onclick="clickBtn('btn4')">
            <input type="button" class="btn" id="btn5" onclick="clickBtn('btn5')">
            <input type="button" class="btn" id="btn6" onclick="clickBtn('btn6')">
            <input type="button" class="btn" id="btn7" onclick="clickBtn('btn7')">
            <input type="button" class="btn" id="btn8" onclick="clickBtn('btn8')">
            <input type="button" class="btn" id="btn9" onclick="clickBtn('btn9')">
        </div>
        <button onclick="replay()">Play Again</button>
        
        <script>
            
            var turn = document.getElementById("turn")
            var game=1;
            var removeWin = [];
            var boxes = document.querySelectorAll("#main input");

            function clickBtn(btn){
            	// enableBoxes()
            	if(game==1) {
            		document.getElementById(btn).value="X";
            		game -=1;
            		document.getElementById(btn).disabled="disabled";
                    turn.innerHTML = "O Turn Now";
            		getWinner();
            	}else{
            		document.getElementById(btn).value="O";
            		game +=1;
            		document.getElementById(btn).disabled="disabled";
                    turn.innerHTML ="X Turn Now";
            		getWinner();	
            	}
            }    
            
            function selectWinnerBtnes(b1,b2,b3){
            	
                b1.classList.add("win");
                b2.classList.add("win");
                b3.classList.add("win");
                turn.innerHTML = b1.value + " Won Congrat";
                turn.style.fontSize = "30px";
                removeWin.push(b1)
                removeWin.push(b2)
                removeWin.push(b3)

                disableBoxes()
            }
            
            function getWinner(){
                
                var btn1 = document.getElementById("btn1"),
                    btn2 = document.getElementById("btn2"),
                    btn3 = document.getElementById("btn3"),
                    btn4 = document.getElementById("btn4"),
                    btn5 = document.getElementById("btn5"),
                    btn6 = document.getElementById("btn6"),
                    btn7 = document.getElementById("btn7"),
                    btn8 = document.getElementById("btn8"),
                    btn9 = document.getElementById("btn9");
            
            // get all posibilites
              if(btn1.value !== "" && btn1.value === btn2.value && btn1.value === btn3.value){
              	selectWinnerBtnes(btn1,btn2,btn3);
              }
         
              if(btn4.value !== "" && btn4.value === btn5.value && btn4.value === btn6.value){
				selectWinnerBtnes(btn4,btn5,btn6);              }
             
              if(btn7.value !== "" && btn7.value === btn8.value && btn7.value === btn9.value){
				selectWinnerBtnes(btn7,btn8,btn9);              }
             
              if(btn1.value !== "" && btn1.value === btn4.value && btn1.value === btn7.value){
				selectWinnerBtnes(btn1,btn4,btn7);              }
             
              if(btn2.value !== "" && btn2.value === btn5.value && btn2.value === btn8.value){
				selectWinnerBtnes(btn2,btn5,btn8);              }
             
              if(btn3.value !== "" && btn3.value === btn6.value && btn3.value === btn9.value){
				selectWinnerBtnes(btn3,btn6,btn9);              }
             
              if(btn1.value !== "" && btn1.value === btn5.value && btn1.value === btn9.value){
				selectWinnerBtnes(btn1,btn6,btn9);              }
             
              if(btn3.value !== "" && btn3.value === btn5.value && btn3.value === btn7.value){
				selectWinnerBtnes(btn3,btn5,btn7);              }
             
            }

          



            function disableBoxes(){
            	boxes.forEach(b=>b.disabled = true)
            }

            
            function replay(b1,b2,b3){
                
                boxes.forEach(b=>b.value = '')
                boxes.forEach(b=>b.disabled = '')
               	removeWin.forEach(b=>b.classList.remove("win"))  
				removeWin = []
                turn.innerHTML = "Play";
                turn.style.fontSize = "25px"; 
            }
                
            
            
        </script>
        
    </body>
</html>
