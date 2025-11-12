# 🎉 Backend Flask - Migration Terminée !

## ✅ Ce qui a été fait

### 1. **Backend Flask créé** (`backend-flask/`)
- ✅ Serveur Flask minimal avec SQLAlchemy + SQLite
- ✅ 6 endpoints d'API fonctionnels
- ✅ JWT pour l'authentification
- ✅ Envoi d'emails 2FA (avec fallback console)
- ✅ CORS activé pour le frontend

### 2. **Endpoints API implémentés**

| Endpoint | Méthode | Description | Status |
|----------|---------|-------------|--------|
| `/api/register` | POST | Inscription + création profil | ✅ |
| `/api/login` | POST | Connexion + envoi code 2FA | ✅ |
| `/api/verify-2fa` | POST | Vérification code 2FA | ✅ |
| `/api/resend-2fa` | POST | Renvoyer code 2FA | ✅ |
| `/api/users/me` | GET | Récupérer profil utilisateur | ✅ |
| `/api/users/me` | PUT | Modifier profil + mot de passe | ✅ |
| `/api/upload` | POST | Upload fichier (CV) | ✅ |

### 3. **Frontend mis à jour**
- ✅ Fichier `lib/api-config.ts` créé avec URLs Flask
- ✅ Toutes les pages pointent vers `http://127.0.0.1:5000`
- ✅ Register, Login, 2FA, Settings, CVUploader utilisent Flask

### 4. **Structure du backend**

```
backend-flask/
├── .env                    # Configuration (SQLite, JWT, Email)
├── .env.example           # Template de configuration
├── .venv/                 # Virtual environment Python
├── app.py                 # Serveur Flask principal
├── models.py              # Modèles SQLAlchemy (User, StudentProfile, etc.)
├── utils.py               # Utilitaires (JWT, bcrypt, email)
├── requirements.txt       # Dépendances Python
├── start.bat              # Script de démarrage Windows
├── run.ps1                # Script PowerShell (alternatif)
├── README.md              # Documentation
└── uploads/cvs/           # Dossier pour les CV uploadés
```

### 5. **Base de données SQLite**
- ✅ `dev_flask.db` créé automatiquement
- ✅ Tables : User, StudentProfile, CompanyProfile
- ✅ Aucune configuration nécessaire !

---

## 🚀 Démarrage

### Option 1 : Fichier batch (Recommandé)
Double-cliquez sur `start.bat` ou :
```bash
cd c:\Users\HAZEM\tunilink\tunilink-web\backend-flask
start.bat
```

### Option 2 : PowerShell
```powershell
cd c:\Users\HAZEM\tunilink\tunilink-web\backend-flask
./run.ps1
```

### Option 3 : Manuel
```powershell
cd c:\Users\HAZEM\tunilink\tunilink-web\backend-flask
.\.venv\Scripts\Activate.ps1
python app.py
```

Le serveur Flask démarrera sur **http://127.0.0.1:5000** 🎯

---

## 🧪 Test Complet

### 1. Démarrer le backend Flask
```bash
backend-flask/start.bat
```
✅ Serveur Flask : http://127.0.0.1:5000

### 2. Démarrer le frontend Next.js
```powershell
cd c:\Users\HAZEM\tunilink\tunilink-web
npm run dev
```
✅ Frontend : http://localhost:3000

### 3. Tester le flux complet

#### A. Inscription
1. Ouvrir http://localhost:3000/register
2. Remplir le formulaire
3. Cliquer "Créer mon compte"
4. ✅ **Résultat** : Compte créé, email de bienvenue (ou console Flask)

#### B. Connexion + 2FA
1. Ouvrir http://localhost:3000/login
2. Se connecter avec email/mot de passe
3. ✅ **Résultat** : Code 2FA envoyé par email (ou affiché dans la console Flask)
4. Copier le code depuis la console Flask (format : `📧 (dev) email to xxx: Votre code : 123456`)
5. Entrer le code sur http://localhost:3000/2fa
6. ✅ **Résultat** : Redirection vers Dashboard

#### C. Settings - Modifier profil
1. Aller sur http://localhost:3000/settings
2. Onglet "Profil" : Modifier nom/téléphone
3. Cliquer "Enregistrer"
4. ✅ **Résultat** : Message de succès, données en DB

#### D. Settings - Changer mot de passe
1. Onglet "Sécurité"
2. Entrer ancien + nouveau mot de passe
3. Cliquer "Enregistrer"
4. ✅ **Résultat** : Mot de passe changé

#### E. Upload CV
1. Dans Settings > Profil
2. Cliquer sur zone d'upload
3. Sélectionner PDF/DOC/DOCX
4. ✅ **Résultat** : Fichier dans `backend-flask/uploads/cvs/`

---

## 📧 Configuration Email (Optionnel)

Le code 2FA s'affiche dans la console Flask par défaut.

**Pour recevoir les vrais emails :**

1. Créer un mot de passe d'application Gmail : https://myaccount.google.com/security
2. Modifier `backend-flask/.env` :
   ```env
   EMAIL_USER=votre-email@gmail.com
   EMAIL_PASSWORD=votre-mot-de-passe-app-16-chars
   ```
3. Redémarrer Flask

---

## 🔧 Configuration

### Fichier `.env` (backend-flask/)
```env
# Base de données
DATABASE_URL=sqlite:///./dev_flask.db

# JWT
JWT_SECRET=forstek_secret_key_change_in_production
ACCESS_TOKEN_EXPIRES_MINUTES=15
REFRESH_TOKEN_EXPIRES_DAYS=7

# Email (optionnel)
EMAIL_HOST=smtp.gmail.com
EMAIL_PORT=587
EMAIL_USER=
EMAIL_PASSWORD=
EMAIL_FROM=Forstek <noreply@forstek.tn>

# Serveur
APP_HOST=127.0.0.1
APP_PORT=5000
```

---

## 📊 Base de Données

### Voir les données
Le fichier SQLite est : `backend-flask/dev_flask.db`

Vous pouvez utiliser :
- DB Browser for SQLite : https://sqlitebrowser.org/
- VS Code extension : SQLite Viewer
- Python : 
  ```python
  import sqlite3
  conn = sqlite3.connect('dev_flask.db')
  cursor = conn.cursor()
  cursor.execute("SELECT * FROM user")
  print(cursor.fetchall())
  ```

---

## 🎯 Différences Next.js vs Flask

| Aspect | Next.js (ancien) | Flask (nouveau) |
|--------|------------------|-----------------|
| **Framework** | Next.js API Routes | Flask REST API |
| **Port** | 3000 (même serveur) | 5000 (serveur séparé) |
| **ORM** | Prisma | SQLAlchemy |
| **Base** | SQLite (Prisma) | SQLite (SQLAlchemy) |
| **Routes** | `/api/auth/*` | `/api/*` |
| **Démarrage** | `npm run dev` | `python app.py` |

---

## 🚨 Troubleshooting

### Serveur Flask ne démarre pas
```powershell
# Vérifier que Python est installé
python --version

# Réinstaller les dépendances
cd backend-flask
pip install -r requirements.txt
```

### Erreur CORS
Vérifiez que Flask-CORS est bien installé :
```powershell
pip install Flask-Cors
```

### Base de données corrompue
Supprimez et recréez :
```powershell
rm dev_flask.db
python app.py  # Recréé automatiquement
```

### Code 2FA non reçu
Les codes s'affichent dans la **console Flask** :
```
📧 (dev) email to user@email.com: Votre code : 123456
```

---

## ✅ Résumé Final

🎉 **Migration Flask terminée avec succès !**

- ✅ Backend Flask fonctionnel (6 endpoints)
- ✅ Frontend connecté à Flask
- ✅ Authentification 2FA opérationnelle
- ✅ Settings sauvegardent en base
- ✅ Upload CV fonctionnel
- ✅ Base SQLite zéro-config
- ✅ Scripts de démarrage (start.bat, run.ps1)

**Prêt pour les tests ! 🚀**

---

## 📝 Prochaines étapes (optionnel)

1. Configurer Gmail pour vrais emails 2FA
2. Ajouter endpoints pour Jobs, Applications, Forum
3. Migrer vers PostgreSQL (production)
4. Déployer Flask sur un serveur (Heroku, Render, etc.)
5. Ajouter tests unitaires (pytest)

---

**💡 Note** : Le backend Flask est dans un dossier séparé et **n'est pas pushé sur GitHub** (comme demandé). Le frontend continue d'être versionné normalement.
