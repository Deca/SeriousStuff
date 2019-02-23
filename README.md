# SeriousStuff


try this <a href="javascript:(function(){

// Use jQuery to create a div with the text "Here is some text"
var div = $("<div id='container' class='container-fluid px-0'>"
            +"<nav id='header' class='navbar navbar-expand-lg navbar-dark bg-dark px-0'>"
            +"<div class='container'><h4 class='d-inline'>NOLIMITS INDICATORS</h4>"
            +"<button id='close' class='btn btn-warning btn-sm d-inline float-right'>Close</button></div></nav>"
             +"<div class='container container-form'><div class='row'><div class='col-12'>"
            +"<div class='form-group'><textarea row='8' class='form-control' id='indicators' name='indicators'></textarea>" 
            +"<small  class='form-text text-muted'>Insert indicators name separated by a comma</small></div>"
            +"<button type='submit' id='load' class='btn btn-primary'>Load</button>"
            +"</div></div></div>");
        

div.css({
  'position': 'absolute', 
  'top': '0px',          
  'right': '0px',          
  'border': '1px solid black', 
  'background-color': 'white',
  'width': '310px',
  'height': '240px'
});


    // Blur any active form fields.
    $(document.activeElement).blur();


    /*
      Start drag listener.
      Adapted from jQuery console bookmarklet:
      http://github.com/jaz303/jquery-console
    */

    $titleBar.on({
      mousedown: function (e) {
        var offset = $box.offset();
        dragging = [e.pageX - offset.left, e.pageY - offset.top];
       
        e.preventDefault();
      },
      mouseup: function () {
        dragging = false;
   
      }
    });

    $target.on('mousemove', function (e) {
      if (dragging) {
        $box.css({
          left: e.pageX - dragging[0],
          top: e.pageY - dragging[1]
        });
      }
    });


var mainStyle = "max-width:100px; margin: 0; padding: 5px; background-color: #abc; position: fixed; top: 90px; right:0px; z-index: 50000;";
var orig = document.body.style.cssText;

function filter(text) {
  var output = "-webkit-filter:"+text+";";
  output+="-moz-filter:"+text+";";
  output+="-ms-filter:"+text+";";
  output+="filter:"+text+";";
  return output;
}

function transform(text) {
  var output = "-webkit-transform:"+ text + ";";
    output += "-moz-transform:"+ text + ";";
    output += "-o-transform:"+ text + ";";
    output += "transform:"+ text + ";";
    return output;
}



    var style1 = document.createElement("link");
    style1.rel = "stylesheet";
    style1.href = "https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0/css/bootstrap.min.css";
    document.body.appendChild(style1);


// Append the div to the <body> tag
$('body').append(div);

 $('#container').append( content );

//$('#header').css({"background-color": "yellow", "font-size": "200%"});
$('.navbar').css({  "border-radius": "0px", "text-align":"center" });
$('h4').css({  "margin-bottom": "0px"});
$('#close').css({"float:":"right !important;"});
$('.container-form').css({"margin-top": "15px", "text-align":"center" })
$('textarea').css({  "height": "8vh"});


$('#close').click(function() {
   $('#container').remove();
});


    $("#load").click(function(event){
        event.preventDefault();
          $("#header-toolbar-indicators").trigger('click');

         setTimeout( function(){ 

                var indicators = $("textarea[name='indicators']").val().split(",");
                $.each(indicators,function(i){
                    $("div.tv-insert-study-item__title-text[title='"+ indicators[i] +"']").trigger('click'); 
                    console.log( i+ "ind : "+indicators[i]);
                });

           }  , 500 );


           setTimeout( function(){   $("div.tv-dialog__modal-body").remove(); }  , 700 );


    });


})();">indicator bookcmarklet</a>
