# Installation d'Elasticsearch et Kibana (Debian/Ubuntu)

Bienvenue dans cette procédure d'installation rapide et efficace d'Elasticsearch et de Kibana sur une distribution Debian ou Ubuntu.

## Prérequis
Assurez-vous que votre système est à jour et que vous avez un accès root ou sudo.

---

## Installation d'Elasticsearch

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

## Installation de Kibana

### 1. Télécharger le paquet Kibana 64 bits
```bash
curl -O https://artifacts.elastic.co/downloads/kibana/kibana-8.17.2-linux-x86_64.tar.gz
```

### 2. Vérifier l'intégrité du fichier
```bash
curl https://artifacts.elastic.co/downloads/kibana/kibana-8.17.2-linux-x86_64.tar.gz.sha512 | shasum -a 512 -c -
```

### 3. Extraire l'archive
```bash
tar -xzf kibana-8.17.2-linux-x86_64.tar.gz
```

### 4. Se placer dans le répertoire de Kibana
```bash
cd kibana-8.17.2/
```

### 5. Lancer Kibana
```bash
./bin/kibana
```

---

## Post-installation

Pour tester Kibana, ouvrez votre navigateur et accédez à :
```
http://localhost:5601
```

Vous devriez voir l'interface de connexion de Kibana.

---

## Informations Complémentaires

- Site officiel d'Elastic : [elastic.co](https://www.elastic.co/)
- Documentation officielle d'Elasticsearch : [Elastic Docs - Elasticsearch](https://www.elastic.co/guide/en/elasticsearch/reference/current/index.html)
- Documentation officielle de Kibana : [Elastic Docs - Kibana](https://www.elastic.co/guide/en/kibana/current/index.html)

---

**Merci d'utiliser cette procédure !**
