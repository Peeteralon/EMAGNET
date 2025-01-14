# EMAGNET v3.4.3

### Before using Emagnet, please remember that with great power comes great responsibility. 

# ![f9087e00-397d-11ea-9cab-1aea419f9448](https://user-images.githubusercontent.com/26827453/167769573-375b14d2-5816-45d6-8395-82d0a7d12089.gif)

| Current Version    | News                            | Tested On                          |
| :----------------- | :-------------------------------- | :----------------------------------|
| `4.0.0`            |     |                              |
| `3.4.3`            |  More than twice as fast as the previous version    | Linux/MacOS/OpenWRT/Windows/Android                               |
| `3.4.2`            |  Support for scraping via API has been added    | Linux/MacOS/OpenWRT/Windows/Android                               |
| `3.4.1`            |  Support for SSH Tunnel/Socks5 proxy    | Linux/MacOS/OpenWRT/Windows/Android                               |
| `3.4`              |  Full support on android devices, no root required    | Linux/MacOS/OpenWRT/Windows/Android                               |

<a href="https://github.com/wuseman/EMAGNET"></a>
<img src="https://img.shields.io/github/languages/top/wuseman/emagnet.svg?color=magenta&label=Bash%2FShell"></a>
<a href="https://github.com/wuseman/EMAGNET/issues?q=is%3Aissue+is%3Aclosed">
<img src="https://img.shields.io/github/issues-closed/wuseman/emagnet.svg?color=light&label=Closed%20Issues"></a>
<a href="https://github.com/wuseman/EMAGNET/issues"></a>
<img src="https://img.shields.io/github/issues-raw/wuseman/emagnet.svg?color=orange&label=Open%20Issues"></a>
<img src="https://img.shields.io/github/last-commit/wuseman/emagnet.svg?color=darkmagenta&label=Latest%20Commit"></a>
<a href="https://twitter.com/wuseman1"></a>
<img src="https://img.shields.io/website/https/nr1.nu.svg?down_color=darkred&down_message=DOWN&label=Nr1.nu%2Femagnet&up_message=UP">
<img src="https://img.shields.io/github/license/wuseman/emagnet.svg?color=blue&label=License"></a>

## Update: 2022-05-11

For all Emagnets stargazzers! This is a bonus for now.

https://user-images.githubusercontent.com/26827453/167771364-d3bf9c15-6753-4f44-b450-b4cfd953298f.mp4

Telegram is dangerous (dangerous = when it comes to unknown groups)! 

Be careful, don't visit groups on Telegram without knowing the admin and who is watching new members.

There is no reasons, for everyone that didn't know this you will love it, there is no reason to make things more complicated than they are:

1. Choose a Telegram Group and add a simple 's' between .me/ and /groupname 
2. like: https://t.me/s/groupname - Alot of admins forgets to securing their group and have no clue about this (obviously), lets continue and dont talk this with anyone, the more ppl that will know this  the worse it gets for you and me. If you're an admin, you sucks! DOn put your users in danger because you are an idiot and do not know how to secure a simple group on telegram, lol. 
3. Don't worry! This is just a bonus (bonus = wont last forever, if any group admin will see this who did not know better, then use emagnet-v4.0.0-beta instead) - This part is just added for fun and not a real part of this project!

Don't hate the player hate the game (admin)!

### You get redirected to a link as below everywhere if you see a telegram button: 

https://t.me/spiderbot_if 

#### Copy the url in browser, add the 's' i mention above and now visit: 

https://t.me/s/spiderbot_if

Scroll until end, now execute below in browser console! 

This script will grab all urls and open a new tab in your browser with all urls on the currrent page.

```js
var x = document.querySelectorAll("a");
var myarray = []
for (var i=3; i<x.length; i++){
var nametext = x[i].textContent;
var cleantext = nametext.replace(/\s+/g, ' ').trim();
var cleanlink = x[i].href;
myarray.push([cleantext,cleanlink]);
};
function make_table() {
    var table = '<table><thead><th>Emagnet Power!</th><th>';
   for (var i=3; i<myarray.length; i++) {
            table += '<tr><td>'+ myarray[i][3] + '</td><td>'+myarray[i][1]+'</td></tr>';
    };
 
    var w = window.open("");
w.document.write(table); 
}
make_table()
```

or even better, print urls in current window and right click in console window and copy / paste! :) 

```js
var urls = document.getElementsByTagName('a');
for (url in urls) {
    console.log ( urls[url].href );
}
```

You probably know it already, im lazy - no jquery needed - autoscroll to top/bottom of page by copy and paste in console:

```js
(function smoothscroll(){
    var currentScroll = document.documentElement.scrollTop || document.body.scrollTop;
    if (currentScroll > 0) {
         window.requestAnimationFrame(smoothscroll);
         window.scrollTo (0,currentScroll - (currentScroll/5));
    }
})();
```

### End

Seriously, my skills for javascript SUCKS - Feel free to build something more cool with the above, if you do - Please contribute!

### Update: 2022-05-10 

Visit [releases](https://github.com/wuseman/EMAGNET/releases) for more info about the beta script.

Simple example how things can be done, no support will be given for this - Wait for a future release please.

Step By Step! Dirty Version! Until I get everything together into one script. 

----- `Tab 1`
```sh
git clone git@github.com:/wuseman/emagnet
cd emagnet
    
# Set time to 1 hour + 10 seconds (add more seconds if your bw is very slow)
bash emagnet.sh -t 3610
    
# Run emagnet in screen with auto spotify bruteforce enable.. 
bash emagnet.sh -q -b spotify 
    
# Or without screen if you wanna see in realtime wich account is valid and available to use
`bash emagnet.sh -b spotify 
```

----- `Tab 2` - Keep above running in background or in another tab

```sh
# Source emagnet.conf, place the line under the vERSION="4.0.0" in emagnet-v4.0.0.-beta.sh
BLINE=$(awk '/vERSION="4.0.0"/ {print NR+1}' emagnet_v4.0.0-beta.sh)
    
# Insert ". ~/emagnet/emagnet.conf" via sed or do it manually lets_pwn wherever you want
# but it must be outside any function and before the lets_pwn() { function..
# Just copy and paste BLINE above line and this line in emagnet dir and its done
sed "${BLINE}i . ~/.emagnet/emagnet.conf" ./emagnet_v4.0.0-beta.sh
    
# Now you must change folders in beta script so emagnet.sh can grab accounts to bruteforce:
sed 's/nPATH="$HOME\/emagnet-temp//nPATH="$EMAGNETHOME/.temp"/g' emagnet_v4.0.0-beta.sh
      
# Add a cronie line for emagnet beta to be executed every 60min + 10sec (36010ecs) **before** autobruter will be executed from Tab 1 (edit folder)
(crontab -l 2>/dev/null; echo "*/60 * * * * sleep 10; bash ~/scripts/emagnet_v4.0.0-beta.sh -e") | crontab -
```

----- `Result / Explanation / Summary`

Every hour `emagnet_v4.0.0-beta.sh` is executed via cronie(crontab) in background and this will download all files to .temp dir
and...10 seconds later....`emagnet.sh` is executed and will check .temp dir and if there is any accounts found emagnet will bruteforce
all these accounts in background! 
    
You personally, can take a walk while emagnet takes care of the rest!

*** 
Sorry for the mess in this README!  I have done my best to try to give an example of how you can use v3.4.3 and v4.0.0 without getting too complicated. if you still do not understand or get this example to work side by side find another hobby or use another tool until I fix it for you but there is a lot of work left so Emagnet can be adapted to everyone! 

### End of 2022-05-10 - Update

***

### Notice: 

Pastebin patched the vulnerability I previously used in order to get recent uploads from https://pastebin.com/archive, so at the moment it is not possible to get recently uploaded files, you are now limited to all syntaxes exempt the default one (95% get's uploaded as 'text' and this is removed from all recent upload lists). 

Currently working on a new way to share all recent uploads for free.

Pastebin on Twitter: 
https://twitter.com/pastebin/status/1250472977491091457

Read their terms of service here before this decision:

https://web.archive.org/web/20200410004902/https://pastebin.com/doc_terms_of_service

    4. Services Usage Limits
    You agree not to reproduce, duplicate, copy, sell, resell or exploit any portion of the Service, use of the Service, or access to the Service without Pastebin's express written permission. 

    Scraping refers to extracting data from our Website via an automated process, such as a bot or webcrawler. It does not refer to the collection of information through Pastebin's API. You may scrape the website for the following reasons:

     Researchers may scrape public, non-personal information from Pastebin for research purposes, only if any publications resulting from that research are open access.
    Archivists may scrape Pastebin for public data for archival purposes.
    You may not scrape Pastebin for spamming purposes, including for the purposes of selling Pastebin users' personal information, such as to recruiters, headhunters, and job boards.

    All use of Pastebin data gathered through scraping must comply with the Pastebin Privacy Statement. 
 
Emagnet users are archivists! __Right__?

We didn't get the recent uploads from __scrape.pastebin.com__, we used _pastebin.com/archive_, this means our usage was in compliance with the privacy statements.

Whatever, this means that the Emagnet project has ended up in a pause phase as we will not go much further until this changes, but just wait. Soon the greed will come and they will open the pro section again. They can not run this service for free for too long.

#### BBC NEWS: ["Pastebin: Running the site where hackers publicise their attacks"](https://www.bbc.com/news/technology-17524822) 

- Emagnet is the No.1 tool for fetching leaks from Pastebin

### About - Emagnet v3.4.3 (2020-07-19)

Emagnet is a very powerful tool for capturing email addresses and passwords from leaked databases uploaded on Pastebin. It's almost impossible to find leaked passwords after they're removed from the list on pastebin.com. Either they have been deleted by Pastebin's techs or the upload is just one in the crowd. To be honest it's easier to find a needle in a haystack then find outdated uploads on Pastebin.

* Parallel downloading! More than twice as fast as the previous version.
* 555 files downloaded, over ~20.000 accounts found via auto brute-force using one command that takes approximately 4.51 seconds (see proof below)
* Incredibly good results for successful attacks.
* There is __no__ other tool nearby that has more successful attempts than Emagnet.
* Emagnet is quick, easy, unique and awesome!
* Google used Emagnet's source to analyze their own site about 1year ago, this is how people are trying to attack accounts today.
* No skills needed, even your grandmother can use Emagnet!
* Bruteforce ssh targets and Microsoft Remote Desktop clients - extremely fast portscanning to choose our targets with X port open (netcat/xargs)
* Super easy to add your own tools using inotifywait with Emagnet - See script example [here](https://pastebin.com/raw/rem8bNRw)
- ./emagnet -g gmail will automate the attack for gmail/google accounts only - We skip the rest!
  - Read more on Google's security blog and automated-tools (emagnet) 
  - Even 1 year after using Emagnet to analyze Google, it is still the best tool for it's purpose (2020-07-19) (7% using 2FA)
  - If the user does not have 2FA enable, you will succeed!
  - URL To Google's security blog (This was for try 2FA security): [Google.com - Security Blog](https://security.googleblog.com/2019/05/new-research-how-effective-is-basic.html)
  - __Remember, bruteforcing accounts without the owner's approval violates the law.__

### Emagnet - v3.4.3 (ssh)
![emagnet-v3 4 3-ssh](https://user-images.githubusercontent.com/26827453/167769249-825ddb73-7b57-42cf-b21c-70d53e50a2cb.gif)

### Emagnet - v3.4.3 (spotify)
![emagnet-v3 4 3-spotify](https://user-images.githubusercontent.com/26827453/167769248-8084d3e9-bf52-4c73-95ab-a41c0eb7e2ff.gif)

### Emagnet - v3.4.3 (gmail)
![emagnet-v3 4 3-gmail](https://user-images.githubusercontent.com/26827453/167769247-5add436f-682c-4f19-b216-b8facd94dba5.gif)


### Getting Started

    git clone https://github.com/wuseman/emagnet
    chmod +x emagnet/emagnet.sh
    bash emagnet/emagnet.sh --emagnet
       
### System Requirements

- Bash     - Find more info about _bash_ [here](https://www.gnu.org/software/bash/)
- Gsed     - Find more info about _gsed_ [here](https://www.gnu.org/software/sed/)
- Gawk     - Find more info about _gawk_ [here](https://www.gnu.org/software/gawk/)
- Wget     - Find more info about _wget_ [here](https://www.gnu.org/software/wget/)
- Curl     - Find more info about _curl_ [here](https://github.com/curl/curl)

### Wiki Sections:

- [About](https://github.com/wuseman/EMAGNET/wiki/ABOUT) - 
_How everything started._
- [Previews](https://github.com/wuseman/EMAGNET/wiki/PREVIEWS) - 
_Previews can be found here._
- [Configurations-&-Installation](https://github.com/wuseman/EMAGNET/wiki/Configurations-&-Installation) - 
_Get started with spotify brute forcing - How emagnet will work with your openvpn files._
- [Regex - Tips For Search](https://github.com/wuseman/EMAGNET/wiki/Searching-&-Regex) - How to find your facebook credenticals, if they have been leaked._
- [Leaked Databases](https://github.com/wuseman/EMAGNET/wiki/Leaked-Databases) - Various Public Leaks

## Changelog

[Versions changelog](CHANGELOG.md).

## Authors: 

* **wuseman <wuseman@nr1.nu\>** 

## License

This project is licensed under the GNU General Public License v3.0 - see the [LICENSE.md](LICENSE.md) file for details

### Contact

  If you have problems, questions, ideas or suggestions please contact me on *_wuseman@nr1.nu_  - For faster contact visit Libera irc network or the webchat and type '/msg wuseman hi!' in the input bar and I will reply to you ASAP.
  
  Enter Libera's network via your own client 'chat.libera.chat:+6697 or use their new web client [here](https://web.libera.chat/).

### Notice

Attacking different kinds of accounts via Emagnet that you have not been granted permission to attack is strictly prohibited and it breaks the law. The punishment is grave and you can even get into prison in some countries just for trying to attack for intrusion. That said, it's *important* that all users are aware of this and when you have cloned or downloaded the repository it's fully up to you to take responsibility for your actions. Wuseman cannot be held responsible for the actions of any user, all users using Emagnet do so at their own responsibility. 

Developer: "All my previews where a brute force attack has been done is under controlling forms with 100% fully permissions by the owners. If you have any questions about this then you are welcome to contact me or the owner."

### Haters Gonna Hate

If you are one of these who dislikes _EMAGNET_ and believe the program has been developed for a reason that would break the law then I am not interested in your opinions, keep them to _yourself_! Emagnet does **NOT** leak any data  either to the developer(s) or anyone else. There are no statistics used to track any user so if you want to contact me to ask about them, it is completely useless since I really have no idea, and to be honest I don't care.

Feel free to read the history about Emagnet [here](https://github.com/wuseman/EMAGNET/wiki/About) and how this project started.

#### Development of Emagnet is active and it is updated frequently, please use the latest version for fixed issues/bugs.

#### \*\*Special thanks to _m1st_ for delivering legit leaks to us daily\*\*

Cheers!

### Feel free to send donations if you want to support the development of Emagnet

    Please contact me before you send a donation at: wuseman@nr1.nu

### Emagnet is a private project since 2015 and was released in June @ 2018, to be continued. 


Note to all the people that are trying to sell public leaks and steal hackers' jobs:

f*ck you! This is one reason why I started this project, I hope this project will get widely spreaded so you will earn 0.00$ on your re-edited malware shit!
