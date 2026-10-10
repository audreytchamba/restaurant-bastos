# ROADMAP — Site web Heritage (Bastos, Yaounde)

## Instructions pour Claude (a lire avant toute action)

Tu es le developpeur unique de ce projet. Tu travailles seul, de maniere autonome,
en suivant les etapes ci-dessous dans l'ordre. Tu ne demandes pas confirmation
avant chaque petite decision technique : tu avances, tu documentes tes choix dans
la section "Journal" en bas de ce fichier, et tu ne poses une question a Audrey
que si tu es bloque par une information qu'elle seule peut donner (exemple :
un vrai numero de telephone, une adresse email).

Regle n°1 : avant de commencer, lis entierement ce fichier, surtout la section
"Etat d'avancement" en bas, pour savoir exactement ou le projet en est.

Regle n°2 : des qu'une etape est terminee et testee, coche sa case ci-dessous
et ecris 3 a 5 lignes dans le Journal (ce qui a ete fait, les choix techniques,
ce qu'il reste a faire). C'est ce qui te permet, dans une future conversation,
de reprendre sans tout relire.

Regle n°3 : fais les choses toi-meme. N'ecris pas "voici le code, a toi de
l'integrer" : cree ou modifie directement les fichiers du projet. Lance les
commandes necessaires (npm install, tests, etc.) et corrige les erreurs sans
attendre qu'Audrey te les retranscrive, sauf si tu n'as pas la main sur le
terminal — dans ce cas donne la commande exacte a copier-coller.

Regle n°4 : a la fin de CHAQUE etape, meme si tu pourrais continuer, arrete-toi,
mets a jour ce fichier, et dis a Audrey en une phrase ce qui est fait et quelle
est la prochaine etape. Elle decide quand enchainer.

Regle n°5 (securite) : c'est le domaine d'Audrey, pas seulement le tien.
Applique les bonnes pratiques par defaut (requetes parametrees, mots de passe
haches avec bcrypt, validation des entrees, pas de secret en dur dans le code,
protection CSRF sur /admin). A l'etape Audit, explique-lui clairement CE QUE tu
as verifie et pourquoi, pour qu'elle puisse te challenger.

---

## Contexte du projet

Site vitrine + commande en ligne pour un restaurant fictif-portfolio nomme
Heritage, situe a Bastos, Yaounde, Cameroun. Cuisine locale (poulet/poisson
grille, ndole, taro) et occidentale (burgers, pizzas, tacos). Ambiance
conviviale, soiree karaoke le vendredi.

Objectif : projet de portfolio pour demarcher des clients freelance a Yaounde.
Le restaurant Heritage existe reellement mais n'a pas encore de site : ce
projet sert d'abord de demo a lui presenter, pas un site deja commande par lui.

Stack : Node.js + Express (backend), HTML/CSS/JS (frontend), SQLite (donnees),
Nodemailer (email). Pas de compte client. Mobile-first.

---

## Etat d'avancement

- [ ] Etape 0 — Initialisation du projet (structure de dossiers, package.json,
      serveur Express minimal qui repond "OK", connexion SQLite, premieres
      tables : plats, categories)
- [ ] Etape 1 — Page d'accueil (banniere, accroche "Cuisine locale et
      internationale au coeur de Bastos", points forts, infos pratiques,
      adresse/horaires/telephone/carte, footer Facebook/Instagram)
- [ ] Etape 2 — Page Menu (plats par categories : Grillades, Plats locaux,
      Occidental, Boissons ; filtres par categorie ; tri par prix ; fiche
      plat avec photo/nom/description/prix/bouton "Ajouter au panier")
- [ ] Etape 3 — Panier (icone fixe avec compteur, volet ou page panier,
      quantites modifiables, total automatique, bouton "Commander")
- [ ] Etape 4 — Commande version A : formulaire (nom, telephone, date/heure
      souhaitees) qui genere un lien WhatsApp pre-rempli avec le recapitulatif
- [ ] Etape 5 — Commande version B : meme formulaire, envoi automatique d'un
      email a l'administrateur via Nodemailer avec le detail de la commande
- [ ] Etape 6 — Interface /admin : connexion securisee (bcrypt, session,
      CSRF, limitation des tentatives), liste des plats, ajout/modification/
      suppression, changement de prix, upload de photo, bouton
      "epuise/disponible", gestion des categories, utilisable sur telephone
- [ ] Etape 7 — Audit de securite : relecture complete du code par Claude,
      rapport ecrit des points verifies et des risques residuels, pour
      qu'Audrey puisse tester elle-meme les points cles
- [ ] Etape 8 — Finitions : design responsive verifie sur mobile, README
      clair, captures d'ecran pour le portfolio Upwork, courte video de demo

---

## Journal (rempli par Claude au fur et a mesure)

<!-- Exemple de format a respecter :
### Etape 0 — termine le 2026-10-11
- Structure : /src, /public, /db. Express + better-sqlite3 choisis (plus
  simple que sqlite3 async pour ce projet).
- Tables creees : dishes (id, name, description, price, category, photo_url,
  available), categories (id, name).
- Prochaine etape : Etape 1 (page d'accueil).
→
