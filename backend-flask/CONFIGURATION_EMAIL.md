# 📧 Configuration Email Professionnelle - Forstek

## 🎯 Pourquoi Brevo ?

- ✅ **300 emails gratuits par jour** (9000/mois)
- ✅ **Sans carte bancaire**
- ✅ **Configuration simple**
- ✅ **Emails HTML professionnels**
- ✅ **Statistiques d'envoi**

---

## 🚀 Configuration en 5 minutes

### Étape 1 : Créer un compte Brevo (2 min)

1. Allez sur **https://www.brevo.com/**
2. Cliquez sur **"Sign up free"**
3. Remplissez avec :
   - Email : Votre email professionnel
   - Mot de passe : Fort et sécurisé
4. **Vérifiez votre email** (cliquez sur le lien reçu)

---

### Étape 2 : Obtenir les identifiants SMTP (2 min)

1. Une fois connecté à Brevo, cliquez sur votre nom en haut à droite
2. Allez dans **"SMTP & API"**
3. Sous la section **SMTP**, vous verrez :
   ```
   Server: smtp-relay.brevo.com
   Port: 587
   Login: votre-email@example.com
   ```
4. Cliquez sur **"Create a new SMTP key"**
5. Donnez-lui un nom : `Forstek Backend`
6. **COPIEZ** la clé qui apparaît (elle ressemble à : `xsmtpsib-a1b2c3d4...`)
   
   ⚠️ **IMPORTANT** : Sauvegardez cette clé, vous ne pourrez plus la revoir !

---

### Étape 3 : Configurer le fichier .env (1 min)

1. Ouvrez le fichier : `backend-flask\.env`

2. Trouvez la section Email et modifiez :
   ```env
   EMAIL_HOST=smtp-relay.brevo.com
   EMAIL_PORT=587
   EMAIL_USER=votre-email@example.com
   EMAIL_PASSWORD=votre_cle_smtp_copiee
   EMAIL_FROM=Forstek <noreply@forstek.tn>
   ```

3. Remplacez :
   - `votre-email@example.com` → Votre email Brevo
   - `votre_cle_smtp_copiee` → La clé SMTP que vous avez copiée

**Exemple :**
```env
EMAIL_HOST=smtp-relay.brevo.com
EMAIL_PORT=587
EMAIL_USER=hazem@forstek.tn
EMAIL_PASSWORD=xsmtpsib-a1b2c3d4e5f6g7h8i9j0k1l2m3n4o5p6-AbCdEfGhIjKlMnOp
EMAIL_FROM=Forstek <noreply@forstek.tn>
```

4. **Sauvegardez** le fichier

---

### Étape 4 : Redémarrer Flask

Pour que les changements prennent effet :

```powershell
# Arrêter Flask (fermez la fenêtre CMD de Flask)
# OU dans PowerShell :
taskkill /F /IM python.exe

# Redémarrer Flask
cd backend-flask
.\start.bat
```

---

## ✅ Test de Configuration

### Test 1 : Inscription d'un nouvel utilisateur

1. Allez sur http://localhost:3000/register
2. Inscrivez-vous avec **VOTRE VRAI EMAIL**
3. Vérifiez votre boîte mail → Vous devriez recevoir un email professionnel ! 📧

### Test 2 : Connexion avec 2FA

1. Allez sur http://localhost:3000/login
2. Connectez-vous
3. Vérifiez votre boîte mail → Code 2FA reçu ! 🔐

---

## 🎨 À quoi ressemble l'email ?

L'email envoyé est **professionnel** avec :
- 🎨 Design moderne avec dégradé bleu/violet Forstek
- 🔢 Code affiché en grand au centre
- 📱 Responsive (s'adapte sur mobile)
- 🛡️ Message de sécurité inclus

---

## 🔍 Dépannage

### ❌ "Authentication failed"
- Vérifiez que la clé SMTP est correcte
- Vérifiez que l'email correspond à celui de Brevo
- Recréez une nouvelle clé SMTP si nécessaire

### ❌ "Connection refused"
- Vérifiez que le port est bien `587`
- Vérifiez que `smtp-relay.brevo.com` est correct

### ❌ "Email not received"
- Vérifiez le dossier SPAM/Courrier indésirable
- Attendez 1-2 minutes (délai d'envoi)
- Regardez les logs Flask pour voir si l'email a été envoyé

### ✅ Voir les logs d'envoi
Dans la console Flask, vous verrez :
```
✅ Email envoyé à user@example.com avec le code 123456
```

---

## 📊 Statistiques d'envoi

Sur Brevo, vous pouvez voir :
- Nombre d'emails envoyés
- Taux d'ouverture
- Emails en erreur
- Historique complet

---

## 🚀 Mise en production

Quand vous déployez Forstek en production :

1. **Domaine personnalisé** : Configurez `@forstek.tn` au lieu de `noreply@forstek.tn`
2. **Augmentez la limite** : 300 emails/jour = ~9000/mois gratuit
3. **Plan payant** : Si besoin de plus, Brevo est très abordable

---

## 🆘 Support

- **Documentation Brevo** : https://help.brevo.com/
- **Support Brevo** : Via le chat sur brevo.com
- **Alternative** : Si Brevo ne fonctionne pas, on peut configurer SendGrid ou Mailgun

---

## 🎉 Félicitations !

Votre système d'authentification 2FA est maintenant **professionnel** ! 🚀

Chaque utilisateur recevra son code par email instantanément.
