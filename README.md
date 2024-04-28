# PrettyConsoleCommand
Follow the described steps to get a better looking console command, in particular to work with git

- trouver une font compatible pour terminal avec des glyphes, comme ici : https://github.com/ryanoasis/nerd-fonts
- aller dans Release
- download l'archive qui nous intéresse
- installer TOUTES LES FONTS DE L'ARCHIVE
- ouvrir le cmd
- à côté du + pour un nouvel onglet, la flèche permet d'accéder aux options
- paramétrer un nouveau profil par défaut pour lancer l'exe de gitbash et utiliser notre nouvelle font (en passant par appearance)

- s'assurer que Winget est installé (utiliser cette commande sur le powershell : winget) SINON : microsoft store, chercher winget et installer app installer
- aller ici https://ohmyposh.dev/ -> Get Started -> Installation -> Windows -> utiliser cette commande dans le powershell :
  winget install JanDeDobbeleer.OhMyPosh -s winget
- Fermer et réouvrir le powershell et utiliser la commande :
oh-my-posh
- Puis la commande : oh-my-posh init pwsh --config "$env:POSH_THEMES_PATH\jandedobbeleer.omp.json" | Invoke-Expression
- Sur le site, catégorie Theme (commande powershell Get-PoshThemes) et chercher un thème sympa
- ctrl+clic sur le theme qui nous intéresse
- Tout en bas de la console (il vaut mieux avoir une version récente du powershell pour s'éviter une erreur, $PSVersionTable pour connaitre notre version actuelle)
- POUR METTRE A JOUR LE POWERSHELL SI BESOIN (si version 5.1 sur Win11 par exemple...) -> winget search Microsoft.PowerShell -> winget install --id Microsoft.Powershell --source winget
  !!! Le nouveau powershell peux exister en parallèle du premier, il faut donc s'assurer d'utiliser le bon avant de passer à la suite !!!

To change your theme, adjust the init script in C:\Users\USERNAME\Documents\WindowsPowerShell\Microsoft.PowerShell_profile.ps1.
Example:
oh-my-posh init pwsh --config 'C:\Users\USERNAME\AppData\Local\Programs\oh-my-posh\themes\THEME_NAME_FROM_THE_FOLDER_INDICATED.omp.json' | Invoke-Expression

- Il faut maintenant s'assurer que cette modification soit toujours effective si on relance le shell
- Onglet Prompt sur le site puis la commande : notepad++ $PROFILE (notepad++ est une variable d'environnement ici), si erreur alors cette commande d'abord : New-Item -Path $PROFILE -Type File -Force
- Copier la commande précédente dans ce fichier : oh-my-posh init pwsh --config 'C:\Users\USERNAME\AppData\Local\Programs\oh-my-posh\themes\THEME_NAME_FROM_THE_FOLDER_INDICATED.omp.json' | Invoke-Expression
- . $PROFILE

- ET ça c'est pour le windows powershell, sur le site il y a ce qu'il faut pour ajouter sur les autres shell dans la catégorie prompt pour faire pareil sur bash par exemple
- Pour bash, ouvrir un bash puis faire cette commande : 
notepad++ ~/.bashrc  (créer si n'existe pas)

Add the following to ~/.bashrc (could be ~/.profile or ~/.bash_profile depending on your environment):

eval "$(oh-my-posh init bash)"

Once added, reload your profile for the changes to take effect.

exec bash

Or, when using ~/.profile.

. ~/.profile
