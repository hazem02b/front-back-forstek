# 🎯 MODE CONSOLE - Guide d'utilisation

## ✅ Configuration actuelle

- **Mode** : Console (les codes 2FA s'affichent dans la console Flask)
- **Raison** : Brevo nécessite une vérification complète du compte
- **Solution future** : Une fois Brevo activé, les emails seront envoyés automatiquement

---

## 🚀 Comment utiliser l'application MAINTENANT

### 1️⃣ Inscription (Créer votre compte)

**URL** : http://localhost:3000/register

Remplissez :
- **Email** : `hazembellili80@gmail.com` (ou n'importe quel email)
- **Nom** : `Hazem Bellili`
- **Mot de passe** : **CRÉEZ LE VÔTRE** (ex: `MonPass123!`)
- **Type** : Étudiant ou Entreprise

⚠️ **IMPORTANT** : Notez bien votre mot de passe !

---

### 2️⃣ Connexion

**URL** : http://localhost:3000/login

Utilisez :
- **Email** : L'email que vous avez utilisé lors de l'inscription
- **Mot de passe** : Le mot de passe que vous avez créé

---

### 3️⃣ Code 2FA (Mode Console)

Après la connexion :

1. **Vous serez redirigé** vers la page 2FA
2. **NE PAS** vérifier votre email (le code n'est pas envoyé)
3. **REGARDEZ** la fenêtre CMD Flask (celle qui vient de s'ouvrir)
4. **Vous verrez** un message comme ceci :

```
============================================================
📧 CODE 2FA (MODE DÉVELOPPEMENT)
============================================================
👤 Destinataire: Hazem Bellili (hazembellili80@gmail.com)
🔐 Message: Votre code : 123456
============================================================
```

5. **Copiez le code** (ex: `123456`)
6. **Entrez-le** sur la page 2FA
7. **Validez** ✅

---

### 4️⃣ Après la connexion

Une fois le code validé, vous êtes connecté ! Vous pouvez :

- **Accéder au Dashboard** : http://localhost:3000/dashboard
- **Modifier votre profil** : http://localhost:3000/settings
- **Uploader votre CV** (pour les étudiants)
- **Naviguer** dans toute l'application

---

## 🔄 Renvoi du code 2FA

Si le code expire ou si vous voulez un nouveau code :

1. Sur la page 2FA, cliquez sur **"Renvoyer le code"**
2. Un **nouveau code** apparaîtra dans la console Flask
3. Copiez et entrez ce nouveau code

---

## 📋 Fenêtres à garder ouvertes

- ✅ **Fenêtre CMD Flask** : Pour voir les codes 2FA
- ✅ **Navigateur** : Pour utiliser l'application
- ✅ (Optionnel) **Terminal Next.js** : S'il est séparé

---

## 🎉 Quand Brevo sera activé

Une fois que votre compte Brevo sera complètement vérifié et actif :

1. Les codes 2FA seront **automatiquement envoyés par email**
2. Vous n'aurez **plus besoin** de regarder la console Flask
3. L'expérience sera **comme une vraie application professionnelle**

Pour vérifier si Brevo fonctionne plus tard :
```bash
cd "c:\Users\HAZEM\tunilink\tunilink-web\backend-flask"
.\.venv\Scripts\python.exe test_new_key.py
```

---

## 🆘 En cas de problème

### Problème : Je ne vois pas le code dans la console
**Solution** : Vérifiez que la fenêtre CMD Flask est bien ouverte

### Problème : "Invalid credentials" lors de la connexion
**Solution** : Vous avez oublié votre mot de passe. Exécutez :
```bash
cd "c:\Users\HAZEM\tunilink\tunilink-web\backend-flask"
.\.venv\Scripts\python.exe delete_my_accounts.py
```
Puis réinscrivez-vous.

### Problème : Le code 2FA ne fonctionne pas
**Solution** : Le code a peut-être expiré. Demandez un nouveau code via "Renvoyer le code".

---

## 📞 Résumé rapide

1. **Inscription** → http://localhost:3000/register
2. **Connexion** → http://localhost:3000/login
3. **Code 2FA** → Regardez la console Flask (fenêtre CMD)
4. **Entrez le code** → Sur la page 2FA
5. **Profitez !** → Utilisez l'application normalement

---

**Bon développement ! 🚀**
