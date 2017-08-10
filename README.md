
http://solveme.kr/probs/8/b2244354123a0d89ab828c5e5837b385/

When trying to access the page you get a basic auth login form, if changing the HTTP request method to a method that doesn't exists something weird happens.
This is the answer from the server:

plato:cwCZtyglMC5so

archimedes:cwF.rVNTH56tM

pythagoras:cwUS7L9aCpoVo

socrates:cw5pDVBUZ.vSc

aristoteles:cwpAFgzFGU9t. 

```
<?php
    error_reporting(0);
    require("lib.php");
    if($_SERVER['REQUEST_METHOD'] === "GET")
        echo("The flag is \"".__FLAG__."\".<hr>"); 
    else
        echo(nl2br(file_get_contents(".htpasswd"))."<hr>");
    highlight_file(__FILE__); 
```    
Ok, so now I have the username and the hashed password(DES), so i guess I just need to crack a hash and login to get the flag, and yes, it was that easy :)
