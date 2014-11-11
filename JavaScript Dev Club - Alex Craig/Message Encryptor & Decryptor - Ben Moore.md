Hey guys, I thought I'd share with you a quick project I've been working on this evening. It's basically a program that takes an input from the user, checks to see if it needs to be encrypted or decrypted, and displays the output.

Here's the source code, feel free to tweak it (it offers very basic encryption currently) or do whatever you'd like with it!

    //characters that can be encrypted
             var characters = ['a','b','c','d','e','f','g','h','i','j','k','l','m','n','o','p','q','r','s','t','u','v','w','x','y','z', '1', '2','3','4','5','6','7','8','9', '0', ',',';','.','?','!','$','@','#','%','^','&','*','(',')','-', '_', '+','=', ' '];
            
            
            //check to see if input is already encrypted
            var check = function(text) {
             var search = text.search('1#@1');
             
             if (search === -1) {
                encrypt(text);
             } else {
                
                text = text.replace("!#@1");
                decrypt(text);
             }   
            };
            
            
            
            //if it is not encrypted, encrypt!
            var encrypt = function(text) {
            var output = "";
            
                for (var i = 0; i < text.length; i++) {
                   for (var x = 0; x < characters.length; x++) {
                        if (text[i] === characters[x]) {
                            output+= x;
                        }
                   }
                   output+= ".";
                }
                
                //this is a "stamp" to tell the program that this string has been encrypted.
                output+="1#@1";
                
                alert(output);
            
            };
            
            
            
            //if it is encrypted, decrypt!
            var decrypt = function(tx) {
                var output = "";
                
                var text = tx.split(".");
            
                for (var i = 0; i < text.length; i++) {
                   for (var x = 0; x < characters.length; x++) {
                        var val = x.toString();
                        if (text[i] === val) {
                            output+= characters[x];
                        }
                   }
                   
                }

                alert(output);
            };
            
            
            //get input from user
             var text = prompt("Enter the message.");
            check(text);

Thanks for being awesome! ;)