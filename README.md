# EternityMenu-VIP Self Bypass

Just an reversed module of an mod menu of Grand Theft Auto V protected using Themida and an Auth based on glitch: https://support.glitch.com/t/how-to-create-your-own-auth-system-with-glitch-and-c-for-your-desktop-app/7196


# Requirements
* HTTP Debugger Pro
* IDA Pro 7.2
* The DLL of the menu
* Injector
* Scylla Dumper
* Cheat Engine

# How to bypass
1) **First inject the module DLL in GTA5.exe using Xenos or some other injectors.**
2) **After open Cheat Engine, attach GTA5.exe processes, and select module desiderated.**
3) **Now if you did all steps, open Scylla Dumper, select GTA5.exe process and pick the module desiderated and dump it.**
4) **Import that module into IDA Pro 7.2, and go check the correct response code for the failed check.**

![Step Number 4](https://imgur.com/3LLjYBZ.png)

5) **Now find the correct response value using strings and checking the asm code.**

![Step Number 5](https://imgur.com/0jMtUMA.png)

6) **Now go check where is going to call the website auth url, so the url of website like here.**

![Step Number 6](https://imgur.com/Dh8ZHHD.png)

7) **Now its the time to open the network debugger, now i will use HTTP Debugger Pro, remember to use SSL Certificates for grabbing requests.**
8) **Now lets find the request with the URL we found before using IDA Pro 7.2, so the request is going to do is connected to the domain "x.com/auth?parameter1=username&parameter2=password&parameter3=hwid. Something like that."

** That is how the request will appear in the menu when you will try to login with that menu. **

![Step Number 8](https://imgur.com/QY45F5s.png)

9) **Now if we go to the raw text of the response content we will see our response and on request we can see the parameters like in the url.**

![Step Number 9](https://imgur.com/WeivQn9.png)

10) **Now we need rendirect that request and rendirect the response to 127.0.0.1 and modify the response content to the response we found in ida so that is "authorised"**.

**Here we are going to change our request and set the response to the valid one so like i've buyed VIP. You must change the url paramters with the username and password
you want to use in login, you can do it random one.**

![Step Number 10](https://imgur.com/bnZujFg.png)

11) **After enabling the rule up ^, you just need go in game and use the credentials you used in the parameters of autoreply URL.**
12) **Enjoy that is all, if you want some proof about that, check under here.**

HERE PROOFS: https://imgur.com/a/PQyxuV6
