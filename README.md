#  Projet Banque – Django & MongoDB

Application bancaire sécurisée développée en **Django** avec **MongoDB** comme base NoSQL.  
Elle permet la gestion :

-  des utilisateurs  
-  des comptes bancaires  
-  des transferts d’argent  
-  des logs de sécurité  
-  d’un panneau de supervision administrateur  

Projet réalisé dans le cadre d’un exercice sur la sécurité applicative.

---

#  Installation & Lancement

## 1️ Cloner le projet depuis GitHub
Assurez-vous d’être sur la branche **main** :

voici le lien vers le github https://github.com/dynanoir/Djanpay
```bash
ensuite rentrer dans un dossier vide 
git clone https://github.com/dynanoir/Djanpay.git
cd Projet-Django-MongoDB-Banque


2️ Créer et activer l’environnement virtuel
🔹 Mac / Linux
python3 -m venv venv
source venv/bin/activate

🔹 Windows
python -m venv venv
venv\Scripts\activate

3️ Installer les dépendances
cd .\bank_projects\
pip install -r requirements.txt


Si besoin :

pip install django djongo pymongo python-dotenv

4️ Configuration du fichier .env ( NE PAS LE METTRE SUR GITHUB)

Créez un fichier :

bank_projects/.env


Et remplissez-le à partir de :

📄 .env.example
et mettre la secret key donner 

5️ Appliquer les migrations Django
cd bank_projects
python manage.py makemigrations
python manage.py migrate

6️ Restaurer la base de données MongoDB 
Dézipper :
unzip export_bdd.zip -d ~/

Restaurer :
mongorestore --db=djanpay --dir=.


 La base est prête !

7️ Lancer le serveur Django
python manage.py runserver


Accéder à l’application :
 http://127.0.0.1:8000/

 Accès administrateur (Superuser Django)

Créer un superuser :

python manage.py createsuperuser


Il vous demandera :

un nom d’utilisateur

un email

un mot de passe sécurisé

Mot de passe recommandé :

✔ minimum 12 caractères
✔ majuscule
✔ minuscule
✔ chiffre
✔ symbole

 Accès admin : http://127.0.0.1:8000/django-admin/

 Connexion utilisateur

Pour simplifier la démonstration, les comptes ont la forme :

prenom : prenom1234!


 À n'utiliser QUE pour des tests.
 En production ce serait strictement interdit.

 Structure du projet
Projet-Django-MongoDB-Banque/
│
├── venv/                     
├── bank_projects/
│   ├── core/                # App bancaire principale
│   ├── bank_project/        # Configuration globale Django
│   ├── manage.py
│   ├── .env                 # Variables privées (non versionnées)
│   ├── .env.example
│
└── requirements.txt

