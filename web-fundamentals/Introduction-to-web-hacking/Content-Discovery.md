# Content Discovery

## Task 1:
Content Discovery adalah suatu informasi yang semustinya tersembunyi atau tidak secar langsung diperlihatkan ke publik. Contohnya seperti versi lama dari website, backup files, config files, administrasi file, dan lainnya. Ada beberapa cara untuk melakukan _content discovery_ yaitu seperti dengan melakukan Manually, Automated, dan OSINT.
1. Manually
2. Automated
3. OSINT

## TASK 2: (Manual Discovery)
Robots.txt file adalah document yang memberikan informasi kepada search engines tentang file yang diizinkan untuk diperlihatkan/dikunjungi. Robots.txt file dapat dilihat dengan cara menambahkan /robots.txt di bagian belakang url website.
1. http://10.49.181.162/robots.txt

## TASK 3:
Terkadang developer meninggalkan favicon saat membuat website menggunakan framework, hal ini dapat dilihat pada bagian browser's address bar
<img width="591" height="63" alt="image" src="https://github.com/user-attachments/assets/89275c15-1bcf-4981-82c1-d42263ee9773" />
` curl https://static-labs.tryhackme.cloud/sites/favicon/images/favicon.ico | md5sum `
Dengan menggunakan Command ini, kita akan mendapatkan md5 hash value yang kemudian dapat dicari dalam OWASP favicon database https://wiki.owasp.org/index.php/OWASP_favicon_database.
1. langkah-langkah diatas merupakan jawabannya

## TASK 4: 
Sitemap.xml file merupakan kebalikan dari robots.txt file. Karena sitemap.xml file ini bertujuan untuk menaruh list dari bagian website yang dapat dikunjungi (Termasuk area yang sulit dinavigasi).
Sama seperti robots.txt file, sitemap.xml dapat dikunjungi dengan menambahkan /sitemap.xml pada bagian url website.
1. http://10.49.181.162/sitemap.xml

## Task 5:
HTTP header yang dikembalikan oleh server terkadang memberikan informasi-infromasi penting seperti OS dan versi yang digunakan atau bahkan scripting languagenya. Dengan menggunakan command curl [option -v] terhadap website target, kita bisa mendapatkan header yang dikembalikan.
1. http://10.49.181.162 -v

## Task 6:
Selain favicon, dengan menemukan framework yang digunakan website melalui comments, copyright notices atau credits. Kita bisa mencari infromasi lebih seperti melalui documentations untuk framework tersebut untuk menemukan administration default directory path dan credentials.
1. http://10.49.181.162/thm-framework (admin: admin)

## TASK 7: (OSINT)
OSINT merupakan cara untuk menemukan informasi terhadap target melalui external resources.

**Google Hacking/Dorking** 
Memanfaatkan advanced search engine features, yang memperbolehkan kita untuk memilih content secara custom. Contohnya seperti untuk mencari suatu domain name dengan menggunakan `site: filter`
<img width="867" height="411" alt="image" src="https://github.com/user-attachments/assets/ffdbc318-34e8-492e-b6dc-a55a1630a263" />
Informasi lebih tentang Google Dorking : [https://en.wikipedia.org/wiki/Google_hacking](https://en.wikipedia.org/wiki/Google_hacking)
1. site

## TASK 8: 
**Wappalyzer**
online tool dan browser extension yang menolong untuk mengidentifikasi teknologi yang digunakan sebuah website, seperti frameworks, Content Management Systems (CMS), payment processors dan lainnya.
1. Wappalyzer

## TASK 9:
**Wayback Machine** (https://archive.org/web/)
Sebuah tool yang mencari pages lama yang kemungkinan masih aktif di dalam website target. Berfungsi untuk mengaksis archived, deleted, atau web content yang telah diganti (altered).
1. https://archive.org/web/

## TASK 10:
**GitHub**
GIt adalah sebuah version control system yang mengkeeptrack pergantian files dalam sebuah project. Saat sebuah user selesai melakukan perubahan, mereka akan melakukan commit yang disertakan message lalu melakukan push kembali ke lokasi centralnya (repository). GitHub adalah versi internet dari Git. Kita bisa mencari company names atau website names dari target kita pada GitHub untuk menemukan repositories yang mereka miliki, repositories ini bisa memiliki source code, passwords, atau content penting lainnya.

## TASK 11:
**S3 Buckets**
S3 Buckets adalah storage service yang diberikan oleh Amazon AWS, storage service memungkinkan kita untuk menyimpan files hingga static website di dalam cloud. format S3 Buckets http(s)://{name}.s3.amazonaws.com. common s3 buckets name {name}-assets, {name}-www, {name}-public, {name}-private, etc.
1. .s3.amazonaws.com

## TASK 12: (Automated Discovery)
Automated discovery sendiri adalah proses penggunaan tool untuk mencari contentnya dibanding cari manual. proses ini akan mencari apakah sebuah file atau directory ada pada sebuah website dengan mengguankan wordlists. Wordlists sendiri adalah sebuah list panjang yang berisi common used words. Salah satu resource terbaik untuk wordlists adalah dari     [https://github.com/danielmiessler/SecLists]( https://github.com/danielmiessler/SecLists)

Automation Tools
Beberapa discovery tools yang available: ffuf, dirb, dan gobuster.

ffuf:
`ffuf -w /usr/share/wordlists/SecLists/Discovery/Web-Content/common.txt -u http://10.49.181.162/FUZZ`

dirb:
`dirb http://10.49.181.162/ /usr/share/wordlists/SecLists/Discovery/Web-Content/common.txt`

Gobuster:
`gobuster dir --url http://10.49.181.162/ -w /usr/share/wordlists/SecLists/Discovery/Web-Content/common.txt`

Dengan menggunakan salah satu command di atas, kita dapat mendapatkan jawaban dari task ini. Contohnya aku akan menggunakan gobuster karena gobuster merupakan salah satu tool tercepat.
`gobuster dir --url http://10.49.181.162/ -w /usr/share/wordlists/SecLists/Discovery/Web-Content/common.txt`
1. /monthly
2. /development.log
