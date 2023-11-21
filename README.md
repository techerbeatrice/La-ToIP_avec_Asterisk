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

