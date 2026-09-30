---
type: reference
date: 2026-09-30
tags: [growth, instagram, cockpit, meta-suite, analyse]
related: ["[[projects/growth/analyses/2026-09-30-instagram-donnees-meta-suite]]", "[[projects/growth/data/instagram/meta-suite/README]]", "[[projects/growth/seo-geo-aeo/README]]"]
---

# Cockpit Instagram : état au 2026-09-30 (session cloud)

> Écrit par Claude (Sonnet 5.5, session cloud) après lecture du dossier
> `projects/growth/data/instagram/meta-suite/` (commit 91187f4). **(m)** mesuré par Meta,
> **(c)** calculé par moi, **(h)** hypothèse. Le cockpit est un Artifact privé
> (https://claude.ai/artifact/LaZMTo6tdNaY24Z36ASwPT), données Meta embarquées dans la page.

## 1. Intégrité des données : recalcul depuis la série quotidienne

Les totaux de l'analyse du 30/09 sont **confirmés** (m, somme des 273 lignes) : vues 252 087,
interactions 9 487, clics sur le lien 1 679, visites du profil 5 571, followers en plus 702.
Fenêtre 02 au 29/09 (c) : 57 171 vues, 1 452 interactions, 154 followers, **1 733 visites du
profil** et **742 clics** (le 777 de l'analyse est le total du mois de septembre, pas des
28 jours). Ratio clics ÷ visites : juillet 6 %, août 61 %, septembre 43 %, sur 28 jours 43 %.

La couverture des non-followers est bien de 96 % : 17 257 contre 744 followers (m, vue
d'ensemble 28 jours), soit 95,9 % (c).

## 2. Corrections à apporter à l'analyse du 30/09 et au README des données

1. **Doublons de crosspost restants.** Le filtre `rang_doublon = principal` garde deux lignes
   pour le reel du 07/08 (416 et 4 059 vues) et deux pour le carrousel du 03/07 (204 et
   1 776 vues). Après dédoublonnage (ligne aux vues les plus élevées) il reste **26 reels et
   9 carrousels**, non 27 et 10, et 160 stories. La médiane des reels hors hit passe de
   1 291 à 1 414 vues, celle avec hit de 1 414 à 1 478 (c).
2. **Le reel Drip Bags du 20/08 est probablement en grande partie payé (h).** Deux publicités
   portent le titre « NOS DRIP BAGS ENFIN DISPO » : 49,85 € (15 255 vues payées, 630 visites du
   profil) et 42,53 € (10 978 vues payées, 409 visites). Si elles visent ce reel, 26,2 K de ses
   34,1 K vues sont payées et ≈ 7,9 K organiques (c). L'analyse ne retient qu'un boost (15,3 K).
   **À confirmer dans Ads Manager** : quelle publication chaque publicité vise, et à quelles dates.
3. **L'écart des 166,9 likes est en grande partie levé.** Meta Business Suite donne **81,8 likes
   en moyenne** (médiane 47,5) sur les 12 derniers contenus au 28/08 (c), dont 478 pour le reel du
   20/08, près de la moitié du total. Le benchmark public (Apify) en donne 166,9 : écart de
   ≈ 1 021 likes sur 12 contenus. Hypothèse (h) : le décompte public inclut des likes venus des
   publicités. Ma première lecture (« moyenne gonflée par des posts boostés ») est à nuancer :
   c'est surtout un contenu très vu, en partie payé.

## 3. Analyse par thème (petits échantillons, h)

35 contenus (26 reels, 9 carrousels), classés par légende, hors reel du 20/08 :

| Thème | n | Vues médianes | Interactions médianes |
|---|---:|---:|---:|
| Démystifier (« NON, … », machine, pressé) | 4 | 3 640 | 65 |
| Méthode et recette | 4 | 1 409 | 38 |
| Produit en situation (drip bags, voyage) | 8 | 1 150 | 56 |
| Terroir, coulisses, lieux | 9 | 1 230 | 58 |
| Parole du fondateur, prix et valeur | 9 | 1 174 | 49 |

- Aucun jour ni aucune heure ne ressort : 18 contenus sur 35 sortent entre 18 h et 20 h (n trop petit
  ailleurs), et les jours forts (jeudi, lundi) sont portés par un ou deux contenus boostés.
- La durée moyenne de lecture explique peu les vues : corrélation de rang 0,25 sur 25 reels.
- Le thème « démystifier » a la meilleure médiane mais sur 4 contenus : **anecdote**, pas signal.
- Les carrousels de récit fondateur (17/09 : 171 interactions, 10 partages ; 24/09 : 137
  interactions, 18 partages) dépassent nettement les reels du même thème (30 à 56 interactions,
  sauf « prix et valeur » du 06/09 à 5,7 K vues). Le carrousel du 17/09 a reçu 2 943 vues payées.

## 4. Ce que contient le cockpit (version 2)

- Accueil : entonnoir sur 28 jours (couverture, visites du profil, clics Linktree, visites du
  site et emails affichés **manquants**), 8 recommandations au format constat, action, preuve
  attendue, confiance.
- Onglet Instagram : bandeau, série quotidienne 2026 avec 4 repères (drop de mai, reel du 20/08,
  boost n°2, boost du 17/09 carrousel), entonnoir mensuel, tableau des 195 contenus filtrable et
  triable, thèmes, part organique et payante, 5 publicités, section « quoi booster et à quel
  budget » (candidats, estimateur de visites, registre), audience, alertes, limites.
- Autres onglets : GEO, SEO, AEO, Actions, Carnet (saisie enregistrée dans la base de l'Artifact).

## 5. Ce qui manque

- Ce qui suit le clic : Linktree, site, panier, achat, email. Aucun GA4, aucun pixel Meta.
- Détail par contenu avant le 13/06 (drop de mai). Le repère « drop de mai » du graphique est un
  pic déduit (10 au 16/05), à confirmer.
- Rétention des reels, meilleurs horaires.
- Pour les seuils d'alerte : validation de Nicolas (9 indicateurs proposés).

## Ce que je fais maintenant

1. Publication de la version 2 du cockpit et mise à jour de sa base (actions, décisions).
2. Demande à la session locale (jarvis-21) : dans Ads Manager, lire pour les deux publicités
   « NOS DRIP BAGS ENFIN DISPO » la publication visée, les dates de début et de fin et le
   détail des résultats ; idem pour la publicité « Interactions » de 99,89 € (publication non
   identifiée) et pour la date de la publicité « stocks » (drop de mai).
3. Questions restantes à Nicolas : seuils d'alerte à valider, règle de boost et budget de test,
   lien direct avec UTM à la place du Linktree, catégorie et bio du profil, forme définitive du
   cockpit (Artifact seul ou avec Looker Studio pour GA4 et Search Console après la bascule).
