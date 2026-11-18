# CleanCore : versions

Ce dépôt ne contient **que les versions publiées** de CleanCore (Nettoyeur de PC Windows léger.). Le code source n'est pas publié ici.

| Fichier | Rôle |
|---|---|
| `CleanCore.exe` | Version portable. |
| `CleanCore-Setup.exe` | Installeur. |
| `SHA256SUMS.txt` | Empreintes SHA-256 des deux fichiers. |
| `update.txt` + `update.txt.sig` | Fichier de version **signé** : c'est lui que CleanCore lit pour proposer les mises à jour. |

Télécharge depuis les [Releases](../../releases/latest). Tu peux vérifier un fichier avec :

```powershell
Get-FileHash .\CleanCore.exe -Algorithm SHA256
```

CleanCore ne s'installe qu'une mise à jour **signée** avec la clé de publication de l'auteur, puis vérifie l'empreinte du fichier téléchargé.
Les exécutables ne sont pas signés numériquement (Windows SmartScreen peut afficher un avertissement).
