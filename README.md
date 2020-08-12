# termuxide setup
### This a quick guide to set up Termux on your Android phone without root and enable external app editing using sftp. In one case sftp is not required. The video walkthrough can be found at my [YoutTube Channel](https://www.youtube.com/channel/UCZ1yOrvsayx55WHRplV76Kg)

1. install [Termux](https://play.google.com/store/apps/details?id=com.termux)
1. open termux and run the following commands
* pkg upgrade
* pkg install git
**'' git clone https://github.com/<repo_of_your_choice> ''
* pkg install nmap - optional
* pkg install open ssh - not necessary if you use [Code Editor](https://play.google.com/store/apps/details?id=com.rhmsoft.code)
** whoami - copy the username
** passwd <username_from_whoami>
*** <set_your_new_password_for_sftp_access>
** sshd
*** nmap localhost - ensure that you are running an sftp server on port 8022
* pkg install nodejs - install the development platform of your choice but I will demonstrate a react app
** cd <cloned_git_repo> (or alternatively you can)   npx create-react-app appname      (and then)     cd <appname>
** npm i (if you cloned a git repo)
** npm start  (your react app will pop up in your browser on localhost:3000)
1. install your favorite Android ide
  * In your ide you can access your files through sftp so navigate to that feature - usually in settings
  ** your credentials include the username we copied earlier using whoami
  ** the server address is localhost
  ** port 8022
  ** password was set using passwd
  * when you modify a file you must save it in your ide and upload it back into the termux root directory. Some ides do not have sftp capability - I use  [Turbo Client](https://play.google.com/store/apps/details?id=turbo.client) for these editors but it requires the extra step of going back to turbo client to upload
  * [Code Editor](https://play.google.com/store/apps/details?id=com.rhmsoft.code) does not require sftp at all and you can access termux files using the Open (saf) option and navigating to Termux 
  * [Acode](https://play.google.com/store/apps/details?id=com.foxdebug.acode) is also a capable editor 
  * At the time of this writing [I\<code\> Go](https://play.google.com/store/apps/developer?id=TwoSevenTwo+Development) unfortunatley is no longer with us.......rip (my favorite android ide) :'(
      
