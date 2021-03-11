let damier = function(height,width){
            let isPlayer1 = true;
            let $play = $("<div id=play> Au tour du joueur 1<div/>");
            $play.css({
                "position" : "fixed",
                "right" : "0",
                "font-size": "5vw",
            })
            $('body').append($play);
            for(let j = 0;j < height;j++){
                for(let i = 0;i<width;i++){
                    let $quote = $("<div id =" + j + i + ">&nbsp;&nbsp;</div>");
                    $('body').append($quote);
                    $quote
                        .css({
                            "font-size": "20px",
                            "display": "inline-block",
                            "border": "1px solid",
                            "padding" : "5px",
                            "cursor" : "pointer"
                        })
                        .mouseenter(function(){
                        $(this).css({
                            "background-color": "lightgrey"
                        });
                    })
                        .mouseleave(function(){
                        $(this).css({
                            "background-color": ""
                        });
                    })
                        .click(function(){
                        if(isPlayer1){
                            isPlayer1 = !isPlayer1;
                            $('#' + j + i).empty().append("x");
                            $('#play').empty().append("Au tour du joueur 2");

                        }
                        else if(!isPlayer1){
                            isPlayer1 = !isPlayer1;
                            $('#' + j + i).empty().append("o");
                            $('#play').empty().append("Au tour du joueur 1");
                        }});
                    }
            let $br = $("<br/>")
            $('body').append($br);
            }
        }    
            damier(10,15);
