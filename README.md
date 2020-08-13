# termuxide setup
##### This a quick guide to set up Termux on your Android phone without root and enable external app editing using sftp. In one case sftp is not required. The video walkthrough can be found at my [YoutTube Channel](https://www.youtube.com/channel/UCZ1yOrvsayx55WHRplV76Kg)

#### 1. Install [Termux](https://play.google.com/store/apps/details?id=com.termux)

#### 1. Open termux and run the following commands:
  
  * `pkg upgrade`
  * `pkg install git`
    * `git clone https://github.com/<repo_of_your_choice>` 
  * `pkg install nmap`  _optional_
  * `pkg install open ssh`  _not necessary if you use_ [Code Editor](https://play.google.com/store/apps/details?id=com.rhmsoft.code)
    * `whoami`  _copy the username_
    * `passwd <username_from_whoami>`
      * _set your new password for sftp access_
    * `sshd`
      * `nmap localhost`  _ensure that you are running an sftp server on port 8022_
  * `pkg install nodejs`  _install the development platform of your choice but I will demonstrate a react app_
    * `cd <cloned_git_repo>` _or alternatively you can_  `npx create-react-app appname`  _and then_  `cd <appname>`
    * `npm i` _if you cloned a git repo_
    * `npm start`  _your react app will pop up in your browser on localhost:3000_
#### 3. Install your favorite Android IDE/Text Editor
  
  * In your ide you can access your files through sftp so navigate to that feature _usually in settings_
    * your credentials include the username we copied earlier using `whoami`
    * the server address is __localhost__
    * port __8022__
    * password was set using `passwd <username_from_whoami>`
  * When you modify a file you must save it in your ide and upload it back into the termux root directory. Some IDEs do not have sftp capability - I use  [Turbo Client](https://play.google.com/store/apps/details?id=turbo.client) for these editors but it requires the extra step of going back to turbo client to upload
  * [Code Editor](https://play.google.com/store/apps/details?id=com.rhmsoft.code) does not require sftp at all and you can access termux files using the Open (saf) option and navigating to Termux 
  * [Acode](https://play.google.com/store/apps/details?id=com.foxdebug.acode) is also a capable editor 
  * At the time of this writing [I\<code\> Go](https://play.google.com/store/apps/developer?id=TwoSevenTwo+Development) unfortunatley is no longer with us.......rip _my favorite android ide_ :'( <img src='https://dl1.cbsistatic.com/i/2019/06/10/2edbc819-b1ca-4d82-bd05-280579e09e71/3944ca6412e93e6c89648125b36fdafa/imgingest-7322281283442131209.png' width='50'>
      
