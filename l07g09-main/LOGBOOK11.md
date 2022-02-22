## Lab Environment
        - dockps
                fbbd09df52e7  www-10.9.0.80
                48270b888767  mysql-10.9.0.6

        - added to /etc/hosts
                10.9.0.80 www.bank32.com
                10.9.0.80 www.magalhaes2022.com
                10.9.0.80 www.zeferino2022.com


## Lab Tasks

# Task 1 : Becoming a certificate Authority (CA) 
        - openssl x509 -in ca.crt -text -noout
                https://drive.google.com/file/d/13Tvr7VKo-nDbpODGb6oF8AEHZDKWZKsj/view?usp=sharing
                https://drive.google.com/file/d/1KB03hPQqMgU6EI3QDdw9lfgSJT-Ile_H/view?usp=sharing 

        - openssl rsa -in ca.key -text -noout
                https://drive.google.com/file/d/1O8r4BDu24rT0SRLZeLrUNrT5pO6mWxf-/view?usp=sharing

	- What part of the certificate indicates this is a CA’s certificate?
                We know that this certificate is from a root CA since we can check this by determining if the certificate is self-signed.

        - What part of the certificate indicates this is a self-signed certificate?
                The fact that the certificate's Issuer(Issuer: CN = www.modelCA.com, O = Model CA LTD., C = US) is the same as the entity which the certificate is getting issued for(Subject: CN = www.   modelCA.com, O = Model CA LTD., C = US)

        - In the RSA algorithm, we have a public exponent e, a private exponent d, a modulus n, and two secret numbers p and q, such that n = pq. Please identify the values for these elements in your certificate and key files.
                e ==  Exponent: 65537 (0x10001)
                d ==privateExponent:
	                1f:2c:c5:b5:9e:3b:b4:17:9a:a6:4c:c1:27:8f:05:
                        49:1d:af:5b:73:85:1c:bb:ec:d0:b8:8a:54:79:1b:
                        a2:c5:b8:54:c1:84:3e:39:f3:d5:5d:20:70:d3:44:
                        37:99:81:6e:94:c4:e0:43:f5:33:e1:2d:02:a5:ec:
                        50:a4:89:4b:7c:6c:1f:66:51:cb:0e:f8:b6:ac:b0:
                        ca:66:42:27:d0:0c:72:3f:c6:13:c7:7f:d3:a2:d7:
                        5c:8c:08:90:d2:08:08:13:e9:9b:41:70:3b:83:9f:
                        62:72:27:ce:bb:7d:67:91:98:0b:3c:20:2f:d9:51:
                        68:b2:6f:7c:48:77:8e:74:da:3b:43:27:bb:6d:50:
                        ea:f9:43:98:9c:db:7d:af:0a:b6:1d:69:87:d4:8e:
                        6b:56:4d:a6:66:a2:14:9f:09:43:97:04:28:bd:0c:
                        88:ba:1a:38:25:e1:42:a3:91:79:c4:28:ca:65:3c:
                        16:f1:20:c3:4b:56:58:92:b1:0b:75:e2:77:29:d2:
                        52:5c:82:95:4f:bf:bd:af:39:7e:36:05:27:77:f6:
                        8b:1e:34:4e:6f:25:85:9f:70:1e:6d:68:a5:7a:cf:
                        f0:30:61:09:26:ab:f0:14:00:84:e5:40:1a:60:39:
                        f5:47:c6:c3:e2:9c:8f:93:06:15:31:41:95:cd:02:
                        2b:cc:a1:c2:de:4f:a5:73:d9:2b:36:69:76:d0:23:
                        58:58:b5:7b:55:e8:c9:f0:0c:30:5f:c3:03:f5:4e:
                        b7:79:71:83:68:6d:70:2c:94:a0:a5:7c:f6:ec:e9:
                        84:61:78:04:e5:72:8b:ef:35:38:a8:f9:0d:10:24:
                        c7:53:8d:b9:ca:98:aa:9a:e8:d2:df:50:7f:a6:60:
                        63:f9:2d:75:9f:dd:cb:ee:02:d4:73:0a:fd:36:27:
                        9f:d4:ce:b5:d7:7a:53:e8:c0:4a:65:64:89:e4:b3:
                        05:ac:68:b5:42:ce:a5:dc:9e:fa:b3:d6:8b:49:14:
                        94:df:eb:7d:02:9c:2e:08:c9:45:fe:f0:35:f5:55:
                        28:06:32:9f:43:0a:75:7b:0a:6a:42:34:c1:a1:c6:
                        91:98:46:5e:5e:42:e9:b1:12:76:de:53:3e:b3:b8:
                        8c:4b:d6:13:73:c4:3b:0c:59:55:84:02:30:db:a6:
                        70:79:69:42:a1:63:b2:4b:b8:70:d7:4a:8d:95:e9:
                        d2:b1:dc:75:59:69:07:f6:97:a9:25:45:bb:1d:95:
                        ac:84:db:e5:da:84:11:a7:90:26:d1:d6:de:db:51:
                        e5:21:30:ea:87:9e:24:88:03:48:14:27:16:7b:2b:
                        5a:af:75:55:2f:5b:49:b7:06:b4:b4:93:b7:56:89:
                        5d:d1

                n == modulus:
                        00:cb:60:17:b5:7c:a4:fb:da:a9:41:11:5d:87:9f:
                        b2:54:fb:fc:5c:03:e3:43:0b:d0:01:c4:72:b2:c5:
                        d9:df:ed:1e:b1:82:58:29:f3:1b:73:f8:9a:e2:13:
                        64:ba:e2:36:20:ac:8e:38:63:9f:c5:db:a2:1d:f0:
                        c9:2c:ec:1f:31:05:8b:97:12:bc:19:18:33:ec:c5:
                        53:34:1d:10:83:c0:4c:b5:f3:e0:e6:4d:75:25:d5:
                        5e:04:0f:d3:e2:b5:c3:cf:fd:30:58:59:95:9b:b2:
                        32:d0:7d:06:64:b0:a6:6d:f5:49:90:7d:de:c5:12:
                        3a:0c:d6:e0:1d:26:ad:c3:de:fd:e9:d0:79:77:3c:
                        32:f9:12:c5:14:a7:11:57:92:89:3a:90:05:06:ba:
                        cb:8d:c0:ee:06:f0:43:8f:b3:4b:3d:b9:f7:88:91:
                        48:c5:ea:5d:1e:d6:31:73:26:fd:d7:ad:4c:0e:04:
                        23:fc:76:a3:ea:7e:bd:ff:50:1b:ad:9c:c4:a6:de:
                        59:80:0b:f3:33:fe:4b:42:fe:4c:13:c3:21:85:b6:
                        0c:9d:b4:dc:b2:77:aa:7f:d8:98:d7:9f:8c:b0:05:
                        70:40:6d:b5:87:00:14:26:87:47:1e:ac:e6:8f:04:
                        8b:60:d3:ea:7b:e1:a2:c9:ea:3a:9d:ab:ab:fc:17:
                        3d:56:d0:7c:48:39:75:50:66:84:c6:6f:59:0f:bd:
                        44:89:94:a8:e1:6d:dc:1d:dd:e8:3a:5f:c8:47:08:
                        88:5f:a5:dd:96:33:bc:d2:39:28:69:9c:96:d2:ce:
                        37:8d:cd:81:1b:5c:0f:99:15:2a:de:25:51:da:16:
                        af:c9:ea:49:5b:f7:b9:34:a5:15:8c:01:5b:ae:2d:
                        e4:35:bb:fa:1f:08:97:fa:e6:49:01:c2:b7:2c:51:
                        d2:14:fe:60:af:5b:81:af:ff:4d:19:e7:1a:93:55:
                        15:4b:6b:b1:c9:2e:2e:a5:5b:9f:d9:6e:93:52:0f:
                        22:a9:07:71:cf:29:8e:78:f1:63:2c:20:ad:44:c0:
                        36:11:3e:67:3d:f2:2f:24:a9:93:c8:08:67:d7:f6:
                        33:c6:7e:f5:57:52:f9:49:a3:2f:5a:59:2b:22:b6:
                        68:87:47:56:7f:60:77:b4:26:62:aa:cc:4a:d1:1f:
                        5e:8a:ad:ec:f1:8c:31:5b:8c:b8:b5:f3:32:62:9c:
                        87:7b:8e:79:8e:05:cd:5b:16:89:da:b2:1a:a8:f0:
                        ed:09:58:7d:01:3f:b6:7d:e1:3c:eb:70:d4:1a:d5:
                        f1:e1:e8:55:7e:4a:4d:6e:09:c8:dd:48:d3:02:38:
                        d0:c9:1f:49:6e:64:52:cb:dd:28:d6:76:75:71:39:
                        96:e0:2f
                
                p == prime1:
                        00:ea:f1:43:0c:47:de:10:72:03:8a:96:21:30:e6:
                        1a:a5:a4:94:dd:d2:88:8f:e2:a6:d4:b4:81:52:4a:
                        1e:78:2c:d1:0b:c7:e8:f7:9e:ef:44:ab:6b:18:31:
                        5d:9a:cd:c8:cd:2d:ec:5a:58:b4:d9:f3:cd:b9:80:
                        ec:b4:ff:f2:20:4a:14:6f:95:a1:f0:0f:21:af:4c:
                        27:3d:98:ab:6f:2e:2f:1e:d4:39:86:e7:11:38:7a:
                        9e:5a:2a:a5:01:5b:66:04:dd:bf:67:e2:6a:e5:d0:
                        90:f2:37:75:df:0e:83:a1:a7:22:1f:16:dc:c4:e6:
                        63:37:17:f3:10:68:23:0c:ff:9b:cd:68:94:01:91:
                        3b:ae:c2:f7:b0:ef:f8:e2:5d:86:53:75:6a:c0:f7:
                        d2:3d:3d:7a:e0:d3:e3:54:9b:9d:df:4f:b0:91:69:
                        f8:40:7f:ed:49:dd:b7:5c:eb:46:99:d2:ff:87:78:
                        b9:82:72:d4:b1:14:e1:6a:74:3d:0b:75:64:f4:be:
                        de:ac:ff:70:5c:96:c8:2c:9c:b5:57:fe:2f:77:b2:
                        05:69:fe:27:f3:ed:55:92:c4:f8:3e:ff:59:84:ad:
                        c8:08:c2:90:de:f9:0d:a1:1e:ac:a2:66:97:95:41:
                        eb:a2:98:0c:fe:29:4b:75:f0:1e:73:74:fc:6e:82:
                        af:bd
                
                q == prime2:
                        00:dd:9a:86:c7:b1:25:cc:80:5c:76:a8:9a:35:e0:
                        55:0a:b2:0a:1e:7b:a5:e5:f2:67:0d:35:36:7d:8d:
                        62:5a:5c:b4:cc:32:76:54:04:60:24:e9:b6:74:b9:
                        dc:21:76:c4:1f:7c:2a:c6:1b:18:ac:b8:0d:74:6d:
                        69:8f:0f:af:a7:f9:36:3c:a6:3e:f9:01:25:6b:7b:
                        19:69:4b:9e:2c:35:75:a6:f8:c5:6f:0c:30:11:51:
                        9a:4e:6c:19:2d:a6:fe:1d:30:3a:99:bf:a4:81:15:
                        45:1d:86:b7:ed:6d:46:cc:0a:fa:9d:7b:90:28:8c:
                        f3:cc:29:9f:65:50:1c:60:dd:4c:f1:82:d8:75:60:
                        c2:b8:65:cd:ef:0b:e2:e9:01:38:29:12:55:cd:1b:
                        40:12:6c:50:53:54:8b:41:e1:f8:4a:19:7e:e9:89:
                        63:70:fd:6c:ae:ff:22:21:45:31:9a:e7:69:45:59:
                        f6:e3:5e:14:a2:46:bc:4d:50:89:6c:c6:17:61:91:
                        73:dc:8e:10:42:a9:29:11:62:1e:58:8f:57:4b:09:
                        1e:10:39:5d:56:56:6d:fc:5e:33:de:c3:de:28:ba:
                        af:bc:40:ee:52:b2:33:4c:e4:b2:38:0d:a7:ca:7f:
                        fc:a8:44:9a:83:8e:a4:12:33:45:b6:d9:37:04:3e:
                        88:5b



# Task 2: Generating a Certificate Request for Your Web Server

        - openssl req -in server.csr -text -noout: https://drive.google.com/file/d/1roZz7HlsfZsJtXvdiEUVzOREFLCp4JsA/view?usp=sharing
        - openssl rsa -in server.key -text -noout: https://drive.google.com/file/d/1WMRFideoisqHSJaFdO9fclN0IPNY4AZi/view?usp=sharing 
        - Adding alternative names: https://drive.google.com/file/d/1z68r4wYwx8YXbgddSUzNm8SV4fJT6YgW/view?usp=sharing 

        - https://drive.google.com/file/d/1cLlOoy8zwF4pmhBVj2gIQfyVqXyxLfUr/view?usp=sharing


# Task 3: Generating a Certificate for your server 

        - Terminal after signed: https://drive.google.com/file/d/1ioFX4Z3pVmx-OfUnqFKxr3IzReMzH9t7/view?usp=sharing
 
        - Cert's decoded content: https://drive.google.com/file/d/1fBrij-RyAdztZmflGJjp4C3PdILamzRN/view?usp=sharing


# Task 4: Deploying Certificate in an Apache-Based HTTPS Website

        - We had to put our files in the container's correct dir. We achieved this by creating new files with nano and setting their content to be the same as our files.

        - File creation process in correct dirs : https://drive.google.com/file/d/12vEiKoOWIzGk5RT5GpfjRfTaFIEwiaTU/view?usp=sharing

        - Apache’s configuration file: https://drive.google.com/file/d/1iT1lOzv4Se2u9kait-Jz1l1fKtRf4dIp/view?usp=sharing

        - Start and warning: https://drive.google.com/file/d/1uMTwo1Nmyod1u2H_FSNAYvaZ4s3Y9JKv/view?usp=sharing

        - Site warning : https://drive.google.com/file/d/1Mas50a4TjfaRx97uD7wFofszHIhii5Tl/view?usp=sharing

        - 404 (we continued regardless): https://drive.google.com/file/d/1I_CT1F25Ny1xtvRJ1UrqbiCR38F1FpFc/view?usp=sharing

        - When http is used: https://drive.google.com/file/d/1P5ea_X8F80VjvD9umL3_RwSqrKzo8Hdk/view?usp=sharing

        - Adding our CA certificate to Firefox: https://drive.google.com/file/d/1Au9G3g6p-XRwTjRfl7liD5pbOC3t6qgU/view?usp=sharing 

        - Viewing the website: https://drive.google.com/file/d/1NjdZ1rv0KFYq4u_x8mRIi-QhgtLohFVD/view?usp=sharing 

        - We needed to add our certificate to the web explorer so that our CA can verficiate and validate the web pages that we are trying to use, otherwise the https doesn't work.


# Task 5: Launching a Man-In-The_Middle Attack

        - Website configuration: https://drive.google.com/file/d/1j6yLP85wSrhvtLbqvc4KOmZQrcYrXjIZ/view?usp=sharing

        - Website: https://drive.google.com/file/d/17hj_ywKHr_b6SHE6C5Gt8Hl85n1xBrJp/view?usp=sharing 

        - We managed to steal the HTTPS user's request and turned the website that we wanted to visit (Facebook) in our website by redirecting it to our IP address. Now, everything the victim tries to visit www.facebook.com, she will visit our malicioues web server instead.


# Task 6: Launching a Man-In-The-Middle Attack with a Compromised CA

        - First thing to do is  to generate a certeficate request for our web server: https://drive.google.com/file/d/1nb1WzHoDZJlFq_n0veW14s8o-8GYS5L8/view?usp=sharing 

        - We were now able to enter the site withou any warning that it might be dangerous: https://drive.google.com/file/d/12Gf24i0HdlYG5tPhhEMruD1-3yLZeNQ1/view?usp=sharing 
  
