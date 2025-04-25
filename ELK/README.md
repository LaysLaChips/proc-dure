# Installation de Kibana (Linux 64-bit)

Bienvenue dans cette procédure d'installation rapide et professionnelle de **Kibana** sur une distribution Linux 64 bits.

## Prérequis
- Serveur Linux (Debian/Ubuntu ou équivalent)
- Elasticsearch 8.x installé et en cours d'exécution

---

## Étapes d'installation

### 1. Télécharger Kibana
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

### 4. Se placer dans le dossier Kibana
```bash
cd kibana-8.17.2/
```

### 5. Lancer Kibana
```bash
./bin/kibana
```

---

## Configuration du premier lancement

Après avoir démarré Kibana pour la première fois, il sera nécessaire de générer un token d'enrôlement (enrollment token) depuis la machine où Elasticsearch est installé.

### 1. Sur la machine Elasticsearch, générer un token pour Kibana
```bash
sudo /usr/share/elasticsearch/bin/elasticsearch-create-enrollment-token -s kibana
```

### 2. Copier le token généré
Le token ressemblera à une chaîne de caractères longue et unique.

### 3. Dans Kibana
Lors de la première connexion à Kibana via navigateur (par défaut [http://localhost:5601](http://localhost:5601)), il vous sera demandé de saisir ce token pour l'enrôlement.

Une fois validé, Kibana sera correctement connecté à votre instance Elasticsearch.

---

## Informations utiles
- Site officiel Kibana : [elastic.co/kibana](https://www.elastic.co/kibana/)
- Documentation Elastic Stack : [elastic.co/guide](https://www.elastic.co/guide/en/kibana/current/index.html)

---

**Fin de la procédure**
