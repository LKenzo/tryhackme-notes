**Walking an Application**

Beberapa built-in browser tools:
1. View Source - Menggunakan Browser untuk melihat human-readable source code dari sebuah website.
2. Inspector - Belajar untuk menginspect elements lalu membuat sebuah perubahan yang dapat membuat sebuah blocked content untuk dapat dilihat.
3. Debugger - Menginspect lalu mengkontrol flow dari sebuah Javascript page.
4. Network - melihat network request yang dilakukan dari sebuah page.

Salah satu cara untuk menemukan bagian interaktif dari sebuah website adalah dengan melakukan review secara manual pada website's Javascriptnya. Mencatat satu persatu page tentang apa saja yang dapat dilakukan oleh page tersebut.
<img width="889" height="662" alt="image" src="https://github.com/user-attachments/assets/96afbd5d-7421-4f8f-b58b-62a1c31d1350" />

Task 3:
<!--- --> merupakan comments yang biasanya ditinggalkan oleh web developer untuk membuat code mereka dapat dibaca oleh developer lainnya atau bahkan untuk notes sendiri. Kemudian ada <a> yang merupakan element pada html yang dapat menyimpan link dengan menggunakan attribute href. 

Framework adalah sebuah koleksi code yang telah dibuat, yang mempermudah developer untuk membuat fitur umum yang dibutuhkan sebuah website. Dengan membuka view page source kita terkadang dapat melihat clue framework apa yang digunakan, hingga versinya. Berfungsi untuk menemukan vulnerabilitas yang terdapat pada framework tersebut.

1. Pertama kita akan melakukan view page source terhadap target IP Address yang telah diberikan (Web Applicationnya). Kita bisa melihat sebuah comment yang terdapat di atas page sourcenya yang mengaharahkan ke page yang memiliki flagnya.
2. Kembali ke page source utama, Pada line 41 kita dapat menemukan html element <a> yang mengarhkan ke /secret-page.
3. dapat dilihat di line 45-47 dari page source utama, ada beberapa src seperti site.js atau jquery yang terismpan di dalam 1 directory yang sama yaitu assets. Dengan membuka directory assets tersebut kita dapat melihat file salah satunya adalah flag.txt.
4. Pada bagian paling bawah page source utama, terdapat sebuah comment yang beriisikan informasi tentang framework dan versi yang digunakan. Dengan membuka website yang berisi tentang informasi website tersebut dan membuka update logsnya, kita dapat menemukan vulnerability yang dapat memberikan kita flag yang terdapat dalam directory /tmp.zip.

Task 4:
Developer tools, tool kita yang berfungsi untuk membantu web developers melakukan debugging pada web applications.

**Inspector**
View page source tidak akan selalu update dengan apa yang dilihat oleh user, hal ini dikarenakna user akan melakaukan interaction yang dapat mengubah beberapa tampilan. Di sinilah _inspector_ dapat bekerja, yaitu untuk menampilkan live representationnya.

1. By inspecting the page and finding the paywall blocker div. I can make it hidden by changing the css element display: block; to display: none; and get the flag behind it.

Task 5:
**Debugger** (Sources di Google Chrome)
Salah satu developer tools yang berufungsi untuk mendebug JavaScript. Dapat digunakan Pentester untuk ngedive JavaScript code yang diguanakn web browser lebih dalam.

Javascript source code in Debugger often is hard to read because it has been obfusticated. Use the { } (double brackets) option, to make it a little more readable.

Ada fitur yang sangat berguna pada Debugger yaitu Breakpoints, yang berfungsi untuk menghentikan pengeksekusian JavaScript dan memberhentikan pengekesekusian saat ini. Dengan melakukan step-step ini, kita juga dapat mendapatkan flag yang terdapat dalam web page contact.

**Network**
Berfugnsi untuk _keep track_ semua external request yang dibuat oleh webpage.
Form yang disubmit pada background menggunakan method AJAX. AJAX adalah method untuk mengirimkan dan menerima network data dalam sebuah web application background.

1. Pertama buka network tool pada contact page, kemudian isi formnya lalu click send. Setelah melakukan send, kita akan mendapatkan POST request yang apabila kita buka dengan double click kita dapat mendapatkan flagnya.
