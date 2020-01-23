# tic-tac-toe
tic-tac-toe game


<!DOCTYPE html>
<html>
    <head>
      <title>matrix</title>
      <meta charset="utf-8">
      <meta name="viewport" content="width=device-width, initial-scale=1.0">
      <style>
  
        .container{
          display: flex;
          flex-direction: column;
          width: 23%;
          position: fixed;
          top: 35%;
          left: 35%;
        }

        .row{
          display: flex;
          justify-content: space-between;
        }

        #matrix1{
          display: flex;
          flex-direction: column;
           margin-left: 25px; 
          text-align: center;
        }

        input[type=number]{
          width: 35px;
          height: 35px;
          text-align: center;
          font-size: 20px;
        }

        input[type=number]::-webkit-inner-spin-button, 
        input[type=number]::-webkit-outer-spin-button { 
          -webkit-appearance: none; 
          margin: 0; 
        }

        .multi-sign{
          margin-top: 45px;
          margin-left: 18px;
        }

        .btn{
          width: 100px;
          height: 37px;
          margin: 28px 135px;
          background-color: #fd7230;
          color: white;
        }
  
        </style>
    
    </head>

    <body>
      <div class="container">
        <div class="row" >
          <div id="matrix1">matrix1
            <span>
              <input type="number" class="number" id="number1">
              <input type="number" class="number" id="number2">
            </span>
            <span> 
              <input type="number" class="number" id="number3">
              <input type="number" class="number" id="number4">
            </span>
          </div>
          <span class="multi-sign">X</span>
          <div id="matrix1">matrix2
            <span>
              <input type="number" class="number" id="number5">
              <input type="number" class="number" id="number6">
            </span>
            <span>
              <input type="number" class="number" id="number7">
              <input type="number" class="number" id="number8">
            </span>  
          </div>
        </div>
          <button type="button" class="btn"  onclick="showResult()">SHOW RESULT</button> 
      </div> 
        
      <script>

       function twodimentional(arrayone, arraytwo) {
       
         var result = new Array(arrayone.length);
         
         for (var i=0; i<result.length; i++) {
         	
           result[i] = new Array(arraytwo[i].length);
           for (var j=0; j< arrayone.length; j++) {

           	result[i][j] = 0
           	for (var k=0; k<arraytwo.length; k++ ) {
           		result[i][j] += arrayone[i][k] * arraytwo[k][j];
           	}
           }
         }
         return result;
       }


        function display(result) {
         
           
            for (var i= 0; i < result.length; ++i) {
              document.write(result[i].join(' ')+'<br />');
            }

               
        }

        
       function showResult() {
        var num1= document.getElementById("number1").value,
            num2= document.getElementById("number2").value,
            num3= document.getElementById("number3").value,
            num4= document.getElementById("number4").value,
            num5= document.getElementById("number5").value,
            num6= document.getElementById("number6").value,
            num7= document.getElementById("number7").value,
            num8= document.getElementById("number8").value;

			


           if(num1== null || num1 == "", 
           	  num2== null || num2 == "", 
           	  num3== null || num3 == "",
           	  num4== null || num4 == "",
           	  num5== null || num5 == "", 
           	  num6== null || num6 == "", 
           	  num7== null || num7 == "", 
           	  num8== null || num8 == "" )
            {
          		alert("missing fields");
          		return false;
            } else{
				var arrayone = [[num1,num2],[num3,num4]]
	            var arraytwo = [[num5,num6],[num7,num8]]
	            console.log(arrayone);
	            console.log(arraytwo);
	            document.write('matrix arrayone:<br />');
	            display(arrayone);
	            document.write('matrix arraytwo:<br />');
	            display(arraytwo);
	            document.write('arrayone * arraytwo :<br />');
	            display(twodimentional(arrayone,arraytwo));
	            return true;
			}
       }
      
      

      </script>
      
    </body>
</html>

