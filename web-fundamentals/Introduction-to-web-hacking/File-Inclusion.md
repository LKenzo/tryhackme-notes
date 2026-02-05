# File Inclusion

## Task 1
Get Requests mengirimkan user input ke dalam search enginennya. https://www.google.com/search?q=TryHackMe. File inclusion ini terjadi saat PHP ditulis dan diimplementasikan seacara tidak benar. Inti dari masalahnya adalah _Input Validation_. Dari file inclusion ini, attacker dapat mengambil data, seperti code, credentials, atau bahkan RCE (Gain Remote Command Execution) apabila attacker sampai dapat menulis file.

## Task 3 (Path Traversal)
Directory traversal membuat attacker dapat membaca operating system resources. Path traversel vulnerabilities terjadi saat input user dikirim ke fungsi seperti file_get_contents dalam php [read more on that](https://www.php.net/manual/en/function.file-get-contents.php). 
<img width="1596" height="684" alt="image" src="https://github.com/user-attachments/assets/d9249058-917a-4817-82be-87652d243f90" />

Kita bisa mencoba megnecheck suatu URL paramater by adding payloads. Path traversal attack atau dot-dot-slash attack, mempergunakan fungsi jalan ke directory selanjutnya dengan menggunakan `../`, input ex. `http://webapp.thm/get.php?file=../../../../etc/passwd`

Common OS files to use while testing
<img width="892" height="799" alt="image" src="https://github.com/user-attachments/assets/69a80177-80f6-46f9-a579-413ac6b4db0b" />

## Task 4 (Local File Inclusion - LFI)
LFI attacks adalah penyerangan yang terjadi akibat kekukrangan pengetahuan developer terhadap security. function php seperti **include, require, include_once dan require_once** sering berkontribusi ke vulneribilitas pada web. 
#1. Kiranya diberikan 2 opsi pilihan, EN dan AR
<img width="850" height="164" alt="image" src="https://github.com/user-attachments/assets/4a8fff01-f5ff-4660-a24a-84e60989719e" />
menggunakan GET requets via url param lang. Call ini dapat dilakukan dengan HTTP request seperti ini, `http://webapp.thm/index.php?lang=EN.php`, EN.php adalah file yang ada di directory.

Kita bisa gunakan request diatas untuk mengambil file penting seperti /etc/passwd. `http://webapp.thm/get.php?file=/etc/passwd`.

#2. 
