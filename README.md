# La ToIP avec Asterisk   
___

![image](https://github.com/techerbeatrice/La-ToIP_avec_Asterisk/assets/138071140/77933219-1740-4d3a-8592-f8cf1ce1bfa0)

____

#  🔬 Téléchargement des sources et installation des dépendances       

Au préalable, faire les mises à jour de paquets avec **apt update && apt upgrade -y** puis installer asterisk avec la commande **apt policy asterisk**    

![image](https://github.com/techerbeatrice/La-ToIP_avec_Asterisk/assets/138071140/d1134d21-8816-4429-8edf-9f6105730f59)

___

Installe les bibliothèques nécessaires pour la compilation d'une installation personnalisée d'Asterisk   

**sudo add-apt-repository universe**  
**sudo apt -y install git curl wget libnewt-dev libssl-dev libncurses5-dev subversion libsqlite3-dev build-essential libjansson-dev libxml2-dev  uuid-dev**   

![image](https://github.com/techerbeatrice/La-ToIP_avec_Asterisk/assets/138071140/035cfd1b-ec57-4b2e-ae69-1fc3cb5ad8ea)

![image](https://github.com/techerbeatrice/La-ToIP_avec_Asterisk/assets/138071140/f1ad8840-e65b-44ce-b694-962204242b2b)

____     

Une fois le dossier décompressé, place-toi dedans et télécharge les bibliothèques de codecs en exécutant le script **get_mp3_source.sh** qui est sous **/contrib/scripts**      

![image](https://github.com/techerbeatrice/La-ToIP_avec_Asterisk/assets/138071140/a70a0c8c-e291-4d28-9b04-b886cf0bb59b)

![image](https://github.com/techerbeatrice/La-ToIP_avec_Asterisk/assets/138071140/a8eb198f-8ed8-4018-b4b3-cff5ba43b0e4)

![image](https://github.com/techerbeatrice/La-ToIP_avec_Asterisk/assets/138071140/2c16ecef-edce-43f7-ac23-4bb9620096cb)

![image](https://github.com/techerbeatrice/La-ToIP_avec_Asterisk/assets/138071140/e5d40d99-fa88-467d-b9d0-95b032abbdfc)

![image](https://github.com/techerbeatrice/La-ToIP_avec_Asterisk/assets/138071140/779f7ece-7db3-485a-8556-cb08f97ea2d2)

___

#  ⚙️ Compilation à partir des sources   

Toujours à la racine du dossier téléchargé, lance la commande **./configure**   

![image](https://github.com/techerbeatrice/La-ToIP_avec_Asterisk/assets/138071140/37cb62bc-5064-475d-af97-226e0cf1c935)

Il est possible qu'il manque le paquet **libedit**, exécute la commande **sudo apt install libedit-dev** puis relance le **./configure**     

![image](https://github.com/techerbeatrice/La-ToIP_avec_Asterisk/assets/138071140/28e0f195-cfb2-4dc7-a2bf-6b81bd97fce9) 

![image](https://github.com/techerbeatrice/La-ToIP_avec_Asterisk/assets/138071140/81f1157e-889d-4e1a-aa07-39889f1c950c)

![image](https://github.com/techerbeatrice/La-ToIP_avec_Asterisk/assets/138071140/3560a6d1-e433-4059-b9ef-9a3e24c3fe2a)

![image](https://github.com/techerbeatrice/La-ToIP_avec_Asterisk/assets/138071140/02f6eaa5-d010-4f11-bcef-f11eff415729)

____    

Pour ouvrir le menu de configuration, exécute la commande **make menuselect**      
La commande **make menuselect** va créer une interface graphique en mode texte. Elle te permet de configurer les options de compilation d'Asterisk.   
En te déplaçant dans cette interface avec le clavier, tu peux sélectionner les modules et les fonctionnalités à inclure pour l'installation.   
N’hésite pas à modifier les options qui te sont proposées pour faire des tests.  

![image](https://github.com/techerbeatrice/La-ToIP_avec_Asterisk/assets/138071140/10a11c57-aa97-4cc9-b6ab-81e0e13ac901)

![image](https://github.com/techerbeatrice/La-ToIP_avec_Asterisk/assets/138071140/d3d7097f-72b3-400d-9bc8-e8811b47421a)

____

Voici les fonctionnalités à sélectionner :    

Dans le module **Add-ons**, sélectionne les **4 fonctionnalités** :   
**chan_mobile**       
**chan_ooh323**      
**format_mp3**      
**res_config_mysql**      
Dans le module **Core Sound Packages**, sélectionne les **9 fonctionnalités en français FR**, puis les mêmes mais **en anglais EN**       
Dans le module **Music On Hold file Packages**, sélectionne les **4 premières fonctionnalités**     
Dans le module **Extras Sound Packages**, sélectionne les **4 même fonctionnalités** que dans **Music On Hold file Packages**, mais en **EN et FR**    

![image](https://github.com/techerbeatrice/La-ToIP_avec_Asterisk/assets/138071140/7abc238a-bc4d-4d6c-86ea-f2a56c558df4)

![image](https://github.com/techerbeatrice/La-ToIP_avec_Asterisk/assets/138071140/f54e3706-237d-4fe5-a2c6-653d55f81497)

![image](https://github.com/techerbeatrice/La-ToIP_avec_Asterisk/assets/138071140/3054d598-c1a6-4e94-b0b2-5b0cb963cc44)

![image](https://github.com/techerbeatrice/La-ToIP_avec_Asterisk/assets/138071140/99e4c6a5-f48f-4b44-90c2-20094bba3ed7)

![image](https://github.com/techerbeatrice/La-ToIP_avec_Asterisk/assets/138071140/ea15e392-7bd4-4121-aeb4-fe2d5e8c4c1e)

_____

Quand tu as terminé, sélectionne **SAVE & EXIT** et lance ensuite la commande **make** dans le terminal      

Ici **make** va créer l'image d'installation compilée avec la configuration que tu as choisie   
La création dure un certain temps    

![image](https://github.com/techerbeatrice/La-ToIP_avec_Asterisk/assets/138071140/4a92c8e8-465f-4a4d-8295-8799f0f1c0d4)

______

# 🔬 Installation   

Comme tu peux le voir à l'écran, lance la commande **sudo make install** pour démarrer l'installation 

![image](https://github.com/techerbeatrice/La-ToIP_avec_Asterisk/assets/138071140/7dd9b03f-b977-4127-8ab1-09f198cfec44)

![image](https://github.com/techerbeatrice/La-ToIP_avec_Asterisk/assets/138071140/9e35aac2-a882-4c2b-b64a-7b4c7e469079)


![image](https://github.com/techerbeatrice/La-ToIP_avec_Asterisk/assets/138071140/61d4bca6-765e-420c-a0f0-057a3ec0247d)

____

# 👉 Gestion des droits d'accès   

Créer un **groupe asterisk** avec la commande **sudo groupadd asterisk**         
Créer un utilisateur avec les paramètres suivants :   
Nom : **asterisk**    
Type d'utilisateur : **système (avec l'option -r)**     
Dossier de travail : **/var/lib/asterisk**  avec la commande ** avec **sudo useradd -r -g asterisk -d /var/lib/asterisk -s /bin/false asterisk**     
Groupe principal : **asterisk**   
Pour permettre à Asterisk d'accéder aux périphériques audio et aux ports de communication, ajoute l'utilisateur **asterisk**  aux groupes **audio et dialout** avec la commande **sudo usermod -aG audio,dialout asterisk**  

![image](https://github.com/techerbeatrice/La-ToIP_avec_Asterisk/assets/138071140/10dd4fa5-44ce-412a-92bf-2024fe2f460b)

___

Pour tous les fichiers et répertoires de la liste ci-dessous, **change le propriétaire et le groupe à asterisk** et **change les permissions** pour que l'utilisateur **asterisk** ait accès **en RWE (Read, Write, Execute)** tandis que les autres utilisateurs ne  peuvent y **accéder qu'en RW**     
**/etc/asterisk**    
**/var/lib/asterisk**   
**/var/log/asterisk**   
**/var/spool/asterisk**   
**/usr/lib/asterisk**  
avec la commande **sudo chown -R asterisk:asterisk /etc/asterisk /var/lib/asterisk /var/log/asterisk /var/spool/asterisk /usr/lib/asterisk**   et  **sudo chmod -R 0700 /etc/asterisk /var/lib/asterisk /var/log/asterisk /var/spool/asterisk /usr/lib/asterisk**   

Pour les fichiers et répertoires sous **/var/run/asterisk**, change les permissions pour que l'utilisateur asterisk ait **accès en RWE (Read, Write, Execute)** tandis que les autres utilisateurs ne peuvent y **accéder qu'en RW**  avec les commandes :   
**sudo chown -R asterisk:asterisk /var/run/asterisk**   
**sudo chmod -R 0700 /var/run/asterisk**   

![image](https://github.com/techerbeatrice/La-ToIP_avec_Asterisk/assets/138071140/2c0adb09-b05d-42c2-85bc-d5a79635a53b)

____

![image](https://github.com/techerbeatrice/La-ToIP_avec_Asterisk/assets/138071140/0b97c094-8911-4634-98d1-4305b157bcd8)

___

![image](https://github.com/techerbeatrice/La-ToIP_avec_Asterisk/assets/138071140/cf9d964a-b455-4833-b601-0df8ac21021d)

modifier le fichier de configuration **sip.conf**  


