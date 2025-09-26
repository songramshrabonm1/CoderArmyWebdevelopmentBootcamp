# Internet Working

[How to Access Website](#how-to-access-website)


## IP Address (Internet Protocol) 

ধরেন আপনি আপনার GF/Crush এর কাছে উপহার পাঠাতে চাচ্ছেন,  এখন আপনি যদি উপহার পাঠাতে চান তাহলে  যার কাছে উপহার পাঠাবেন তার address আমার জানতে হবে । 
<br><br>
ঠিক তেমনভাবে আমরা যখন একটা কম্পিউটার থেকে আরেকটা কম্পিউটারের সাথে যোগাযোগ করতে চাই বা কাউকে মেসেজ দিতে চাই তাহলেও তো আমরা যে কম্পিউটারে মেসেজ দিতে চাচ্ছি সেই কম্পিউটারের Address আমাদের জানতে হবে । আর এই কম্পিউটারের Address টাকেই বলা হয় IP Adress (Internet Protocol) .  

![alt text](image.png)


## How To Access Website & Concept Of DNS 

Computer এর এই IP Address টা Permanent নয় , এইটা এক এক সময় এক একটা হতে পারে । আমরা যখন Internet এর সাথে connect হয় তখন এই IP Adress change হতে পারে । আর এই IP Address Provide করে ISP (Internent Service Provider) .  
<br>
computer যখন internet এর সাথে connect হয় ISP (Internet Service Provider) একটা IP Address দেয় আমাদের Device কে Unique ভাবে Identify করার জন্য। 
<br><br>
এটা এমন হতে পারে  computer_A কে যে ip address টা দিয়েছে internet service provider (isp) এটা আবার অন্য কোনো computer এ ও দিতে পারে যখন এই computer_a disconnected হয়ে যাবে Internet থেকে। 
<br><br>
এখন ধরি আমি একটা website visit করতে চাচ্ছি কিন্তু এই ওয়েবসাইট টা একটা server এ আছে । [Server মানে একটা computer (Virtual Computer)] . এখন সমস্যা হলো আমরা কিছুক্ষন আগে দেখেছি আমরা যদি একটা কম্পিউটার সাথে আরেকটা কম্পিউটারের যোগাযোগ করাতে চাই তাহলে আমাদের ip address এর দরকার হয় (মানে ঐ কম্পিউটার টার Address) ।
<br><br>
এখন আমি যে website টা visit করতে চাচ্ছি তার name লিখে আমার browser এ search দিলে কিন্তু চলে আসছে but এটা কিভাবে । আমরা তো ঐ কম্পিউটারের IP Address টা জানি না । সেটা আসে  DNS (Domain Name System) এর থেকে । DNS এ প্রতিটা ওয়েবসাইটের ip address থাকে । <br> 

আমরা যখন www.programmingHero.com / www.google.come লিখে search/Request  দেই তখন প্রথম DNS এ গিয়ে এই Domain Name গুলোর IP Address খুঁজে বের করে । <br>

এখন আমরা যখন এই ওয়েবসাইটের IP Address দিয়ে সার্ভারে request পাঠাবো আর এই সার্ভারটা আমাকে আমার request এ response পাঠাবে এই ওয়েবসাইট টা হিসেবে,  আর অবশেষে website আমার browser এ show করবে  । 

![alt text](image-1.png)


## In Depth Of Dns 


first of all আমরা যখন একটা website search দেই browser এ ,  browser প্রথম check করে এখানে এই website এর IP Address আছে কিনা । 

যদি না থাকে তাহলে তা খুজে Recursive Server এখানেও না থাকলে তা খুজা শুরু করে প্রথম Root Server এ । 

![alt text](image-2.png)

World এ 13 টা Root Server আছে যে Root server আমার ডিভাইসের কাছাকাছি তার কাছে খুজে। Root server Detect করে আমার এই website টা কিধরণের .com নাকি .in । এগুলো Detect করার পর সে পাঠায় Recursive Server এর কাছে। Recursive server  আবার পাঠায় TLD Server এর কাছে । 
<br><br>
এখন browser থেকে যে website search দেওয়া হয়েছে সেটা যদি .com হয় তাহলে TLD SERVER এর .com  server  এ খুজা শুরু করে সেও final answer দেয় না  সে  আবার পাঠায় Authoritive Server । then finally found the ip_address your website . 


# Problem In Data Address And Mac Address 

MAC - MEDIA ACCESS CONTROL (Permanent Address)
<br>
ধরি আমার মোবাইল থেকে আমার ig তে ঢুকে আমার আর আমার ফ্রেণ্ডের মেসেজ দেখার জন্য request পাঠিয়েছি  intagram server এ ।
<br>
এখন আমরা জানি isp server যে আমাদের ডিভাইসে ip_address টা দেয় সেটা permanent না । 
<br>
আমাদের ডিভাইস যদি internet থেকে disconnected হয় তখন আমাদের ডিভাইস থেকে isp IP Address  নিয়ে নেয় । 
<br>
এখন ধরি আমি req পাঠিয়ে দিলাম আর req পাঠানোর moment এ আমার internet disconnected হয়ে গিয়েছে আর আমার এই ip_appdress অন্য কারোর মোবাইলে সেট হয়ে গিয়েছে এখন কি req কি অন্য কারোর মোবাইলে চলে আসবে - **না** 
<br><br>
কারন আমাদের ip address permanent না কিন্তু আমাদের প্রত্যেকটা device এ নিজিস্ব mac address আছে সেটা permanent Address আর তা change হয় না এর জন্য request পাঠানোর সময় ip address   + mac address (permanent address ) দিয়ে request পাঠায় আর sender request send করার সময় ip address + mac address দুইটাই পাঠায় তাই এই সমস্যা আমরা face করি না ip_address change হলেও । 
![alt text](image-3.png)


## What Is Port Number 
<br>
আমরা তো জানলাম আমরা যখন কোন সার্ভারে request পাঠায় তখন তা আমাদের Ip address + Mac Address পাঠায় সার্ভারে । 
 এখন আমি যদি কোন ব্রাউজারের থেকে request পাঠায় আর আমাদের ব্রাউজারে একটা tab এ Instagram আরেকটা তে Youtube server । এখন  সার্ভার যখন আমাদের  ব্রাউজারে request অনুযায়ী reply দিবে তখন সে কি করে বুঝবে browser এ কোন ট্যাবে এই রেকুয়েস্ট টা রান করবো । এর জন্য দরকার হয় port number . আমরা যখন request দেই তখন তা ip_address + mac_address + port number দেয় আর এই port number এর কারনে বুঝতে পারে সার্ভার কোন tab এ run করবে website . 

![alt text](image-4.png)

 # IPv4 Vs IPv6 

আমরা তো জেনেছি আমাদের প্রতিটা Device এ Unique IP Address থাকে। এই IP Address দুই ধরনের হতে পারে 
1. IPv4
2. IPv6
<br>
**IPv4** যা ৩২ বিটের হয়ে থাকে আর প্রতিটা বিট ০ বা ১ নিতে পারে। যা total ২^৩২ (4.3 Billion)  টা IP Address Generate করতে পারে। কিন্তু বর্তমানে Device মাত্র 4.3 billion এ সীমাবদ্ব নয় এখন আর বেশি Device আছে আর প্রতিটা ডিভাইস এর  যদি একই সময়ে IP Address এর প্রয়োজন হয় তার জন্য তৈরি করা হয়েছে IPV6 যা Total 16 * 8  = 128 bit হতে পারে আর total 2^128 = (340 Undecillion)  unique IP Address generate করতে পারে । 

 ![alt text](image-5.png)
 

## Mac Address 

একটা device এ mac address একটা হয় না । একটা ডিভাইসে যত ভাবে share option থাকে তত টা mac address থাকে । 

যা ৪৮ বিটের হয় । ২ টা ২ টা করে থাকে । 

