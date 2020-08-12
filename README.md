# termuxide setup
This a quick guide to set up Termux on your Android phone without root and enable external app editing using sftp. In one case sftp is not required. The video walkthrough can be found at https://www.youtube.com/channel/UCZ1yOrvsayx55WHRplV76Kg

1. install termux - https://play.google.com/store/apps/details?id=com.termux

2. open termux and run the following commands
  a. pkg upgrade
  b. pkg install git
    i. git clone https://github.com/<repo_of_your_choice>
  c. pkg install nmap - optional
  d. pkg install open ssh - not necessary if you use codeeditor https://play.google.com/store/apps/details?id=com.rhmsoft.code
    i. whoami - copy the username
    ii. passwd <username_from_whoami>
      x. <set_your_new_password_for_sftp_access>
    ii. sshd
  e. nmap localhost - ensure that you are running an sftp server on port 8022
  f. pkg install nodejs - install the development platform of your choice but I will demonstrate a react app
    i. cd <cloned_git_repo> (or alternatively you can)   npx create-react-app appname      (and then)     cd <appname>
    ii. npm i (if you cloned a git repo)
    iii. npm start  (your react app will pop up in your browser on localhost:3000)
    
3. install your favorite Android ide
  a. In your ide you can access your files through sftp so navigate to that feature - usually in settings
    i. your credentials include the username we copied earlier using whoami
    ii. the server address is localhost
    iii. port 8022
    iv. password was set using passwd
  b. when you modify a file you must save it in your ide and upload it back into the termux root directory. Some ides do not have sftp capability - I use turbo client https://play.google.com/store/apps/details?id=turbo.client for these editors but it requires the extra setp of going back to turbo client to upload
  c. Code Editor does not require sftp at all and you can access termux files using the Open (saf) option and navigating to Termux https://play.google.com/store/apps/details?id=com.rhmsoft.code
  d. Acode is also a capable editor https://play.google.com/store/apps/details?id=com.foxdebug.acode
  e. At the time of this writing icode go unfortunatley is no longer with us.......rip (my favorite android ide) :'(
      
