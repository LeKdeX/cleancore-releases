<div align="center">

<img src="assets/icon.png" alt="CleanCore" width="96">

# CleanCore

**Un nettoyeur de PC Windows qui fait une seule chose : libérer de l'espace disque.**<br>
Sans publicité, sans abonnement, sans compte.

[![Dernière version](https://img.shields.io/github/v/release/LeKdeX/cleancore-releases?color=0a7b9c&label=version)](https://github.com/LeKdeX/cleancore-releases/releases/latest)
[![Téléchargements](https://img.shields.io/github/downloads/LeKdeX/cleancore-releases/total?color=0a7b9c)](https://github.com/LeKdeX/cleancore-releases/releases)
![Windows 10 / 11](https://img.shields.io/badge/Windows-10%20%7C%2011-0a7b9c)

[![Télécharger la version portable](https://img.shields.io/badge/T%C3%A9l%C3%A9charger-Version_portable_(.exe)-0a7b9c?style=for-the-badge)](https://github.com/LeKdeX/cleancore-releases/releases/latest/download/CleanCore.exe)
&nbsp;
[![Télécharger l'installeur](https://img.shields.io/badge/T%C3%A9l%C3%A9charger-Installeur_(Setup.exe)-25272b?style=for-the-badge)](https://github.com/LeKdeX/cleancore-releases/releases/latest/download/CleanCore-Setup.exe)

<img src="docs/screenshot.png" alt="Capture d'écran de CleanCore" width="860">

</div>

## Pourquoi CleanCore

- **Ultra léger** : moins de 10 Mo de mémoire et 0 % de CPU au repos. Un seul fichier de 7 Mo.
- **Lisible d'un coup d'œil** : une barre colorée montre quelle catégorie pèse le plus, avec sa part en pourcentage.
- **Prudent** : tu vois ce qui sera supprimé avant de confirmer, et les fichiers récents sont épargnés.
- **Sobre** : aucune télémétrie, aucun service en tâche de fond. Une seule connexion réseau : la recherche d'une nouvelle version au démarrage, désactivable.

## Téléchargement

| Fichier | Pour qui |
|---|---|
| [**CleanCore.exe**](https://github.com/LeKdeX/cleancore-releases/releases/latest/download/CleanCore.exe) | **Version portable.** Tu double-cliques, c'est lancé. Pour le retirer, supprime le fichier. |
| [**CleanCore-Setup.exe**](https://github.com/LeKdeX/cleancore-releases/releases/latest/download/CleanCore-Setup.exe) | **Installeur.** Ajoute un raccourci dans le menu Démarrer et une désinstallation depuis les paramètres Windows. |

Toutes les versions sont dans les [Releases](https://github.com/LeKdeX/cleancore-releases/releases). CleanCore demande les droits administrateur, nécessaires pour nettoyer `Windows\Temp` et les mises à jour Windows.

## Ce qui est nettoyé

| Catégorie | Dossiers |
|---|---|
| Fichiers temporaires | `%TEMP%`, `Windows\Temp` |
| Cache des navigateurs | Chrome, Edge, Firefox |
| Résidus de Windows Update | `SoftwareDistribution\Download` |
| Miniatures et cache des icônes | `thumbcache_*`, `iconcache_*` |
| Journaux et rapports d'erreurs | WER, minidumps, CrashDumps |
| Caches graphiques (shaders) | DirectX, NVIDIA, AMD |
| Corbeille *(définitif, décochée par défaut)* | Tous les lecteurs |

## Mises à jour

Au démarrage, CleanCore regarde s'il existe une nouvelle version et affiche un bandeau avec un bouton **Mettre à jour**. Rien n'est installé sans ton clic. Seule une version **signée** par l'auteur est acceptée, puis l'empreinte du fichier téléchargé est contrôlée avant de remplacer quoi que ce soit. La recherche se désactive avec l'interrupteur **Chercher les mises à jour au démarrage**.

## Sécurité et vérification

- Les liens et jonctions sont refusés : chaque suppression revérifie le chemin réel du fichier, et les dossiers système ne sont jamais ciblés.
- Chaque Release contient `SHA256SUMS.txt` pour contrôler ton téléchargement :

```powershell
Get-FileHash .\CleanCore.exe -Algorithm SHA256
```

- Les fichiers de cette Release : `CleanCore.exe`, `CleanCore-Setup.exe`, `SHA256SUMS.txt`, et `update.txt` avec sa signature `update.txt.sig` (c'est ce que CleanCore lit pour proposer une mise à jour).

## Questions fréquentes

**Windows affiche « Windows a protégé votre ordinateur ». C'est normal ?**
Oui. Les exécutables ne sont pas signés numériquement, un certificat de signature étant payant. Clique sur *Informations complémentaires*, puis *Exécuter quand même*, après avoir comparé l'empreinte avec `SHA256SUMS.txt`.

**Pourquoi la catégorie « Caches graphiques » peut-elle être énorme ?**
Les pilotes graphiques stockent les shaders compilés des jeux. Ce cache se recrée tout seul, avec un léger ralentissement au premier lancement de chaque jeu.

**Pourquoi tout n'est pas supprimé ?**
Les fichiers utilisés à cet instant par Windows ou un programme ouvert ne peuvent pas être effacés. Ferme les navigateurs avant de nettoyer pour libérer plus d'espace.

---

Ce dépôt ne contient que les versions publiées. Le code source n'est pas publié ici.
