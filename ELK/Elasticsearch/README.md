# Installation d'Elasticsearch (Debian/Ubuntu)

Bienvenue dans cette procédure d'installation rapide et efficace d'Elasticsearch sur une distribution Debian ou Ubuntu.

## Prérequis
Assurez-vous que votre système est à jour et que vous avez un accès root ou sudo.

---

## Étapes d'installation

### 1. Mise à jour du système
```bash
sudo apt update && sudo apt upgrade -y
```

### 2. Installer sudo (si nécessaire)
```bash
apt install sudo
```

### 3. Installer wget
```bash
sudo apt install wget -y
```

### 4. Installer GPG
```bash
sudo apt install gnupg -y
```

### 5. Ajouter la clé GPG d'Elasticsearch
```bash
wget -qO - https://artifacts.elastic.co/GPG-KEY-elasticsearch | sudo gpg --dearmor -o /usr/share/keyrings/elasticsearch-keyring.gpg
```

### 6. Installer apt-transport-https
```bash
sudo apt-get install apt-transport-https
```

### 7. Ajouter le dépôt APT d'Elasticsearch
```bash
echo "deb [signed-by=/usr/share/keyrings/elasticsearch-keyring.gpg] https://artifacts.elastic.co/packages/8.x/apt stable main" | sudo tee /etc/apt/sources.list.d/elastic-8.x.list
```

### 8. Installer Elasticsearch
```bash
sudo apt-get update && sudo apt-get install elasticsearch
```

### 9. Démarrer Elasticsearch
```bash
sudo systemctl start elasticsearch
```

### 10. Vérifier que le service fonctionne
```bash
sudo systemctl status elasticsearch
```

### 11. Activer Elasticsearch au démarrage
```bash
sudo systemctl enable elasticsearch
```

---

## Post-installation

Pour tester l'installation :
```bash
curl -X GET "localhost:9200/"
```
Vous devriez obtenir une réponse JSON contenant les informations de votre instance Elasticsearch.

---

## Informations Complémentaires

- Site officiel d'Elastic : [elastic.co](https://www.elastic.co/)
- Documentation officielle d'Elasticsearch : [Elastic Docs](https://www.elastic.co/guide/en/elasticsearch/reference/current/index.html)

---

**Merci d'utiliser cette procédure !**
