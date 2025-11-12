# Mode Développement - Forstek Backend

## 🔐 Authentification à Deux Facteurs (2FA)

### Comment ça fonctionne ?

En mode développement, l'envoi d'emails n'est **PAS** configuré. Les codes 2FA sont affichés directement dans la **console Flask** (fenêtre PowerShell/CMD).

### 📋 Étapes pour se connecter :

1. **Démarrez Flask** :
   ```powershell
   cd backend-flask
   .\.venv\Scripts\python.exe app.py
   ```

2. **Sur le site** (http://localhost:3000/login) :
   - Entrez votre email et mot de passe
   - Cliquez sur "Se connecter"
   - Vous serez redirigé vers la page 2FA

3. **Dans la console Flask**, vous verrez :
   ```
   ============================================================
   📧 CODE 2FA (MODE DÉVELOPPEMENT)
   ============================================================
   👤 Destinataire: John Doe (user@example.com)
   🔐 Message: Votre code : 123456
   ============================================================
   ```

4. **Copiez le code à 6 chiffres** (ex: `123456`)

5. **Retournez sur le site** et entrez le code dans les 6 cases

6. **Validez** → Vous serez connecté ! ✅

---

## 📧 Configuration Email (Optionnelle)

Si vous voulez recevoir de vrais emails, configurez le fichier `.env` :

```env
# Configuration Email
EMAIL_HOST=smtp.gmail.com
EMAIL_PORT=587
EMAIL_USER=votre.email@gmail.com
EMAIL_PASSWORD=votre_mot_de_passe_app
EMAIL_FROM=noreply@forstek.tn
```

### Pour Gmail :
1. Activez l'authentification à 2 facteurs sur votre compte Google
2. Générez un "Mot de passe d'application" : https://myaccount.google.com/apppasswords
3. Utilisez ce mot de passe dans `EMAIL_PASSWORD`

---

## 🚀 Quick Start

```powershell
# Terminal 1 - Backend Flask
cd backend-flask
.\.venv\Scripts\python.exe app.py

# Terminal 2 - Frontend Next.js
npm run dev
```

**Important** : Gardez toujours la fenêtre Flask visible pour voir les codes 2FA !

---

## 🐛 Troubleshooting

### "Je ne vois pas le code 2FA"
- ✅ Vérifiez que Flask tourne dans un terminal visible
- ✅ Regardez bien la console Flask, pas celle de Next.js
- ✅ Le code apparaît entre des lignes de `===`

### "Le code ne fonctionne pas"
- ✅ Vérifiez que vous utilisez le dernier code généré
- ✅ Le code doit avoir 6 chiffres
- ✅ Ne pas confondre 0 (zéro) et O (lettre)

### "La page 2FA ne se charge pas"
- ✅ Vérifiez que Flask tourne sur le port 5000
- ✅ Vérifiez que vous vous êtes bien connecté avant
- ✅ Videz le cache du navigateur (Ctrl + Shift + R)

---

## 📝 Notes

- **Les codes 2FA sont valides indéfiniment** en mode développement (pas d'expiration)
- **Plusieurs tentatives** sont autorisées
- **Le bouton "Renvoyer le code"** génère un nouveau code
