# EPITA 2026 - Programmation par Contraintes
## Liste des sujets de projet

Ce document presente 33 sujets de projet pour le cours de Programmation par Contraintes.
Chaque sujet inclut une description, des references, des approches suggerees et les technologies pertinentes.

---


## 1. Optimisation de plannings infirmiers avec assistance LLM

### Description du probleme et contexte
La confection de horaires de travail pour le personnel infirmier (nurse rostering) est un probleme d'optimisation combinatoire complexe. Les contraintes incluent la legislation du travail, les competences du personnel, les preferences et l'equite. Ce sujet propose d'integrer des LLM (via MCP ou function calling) pour assister dans la formulation des contraintes et l'explication des solutions.

### References
- Burke et al. - A Multi-Objective Meta-Heuristic for Nurse Rostering - 2004
- Laborie - IBM ILOG CP Optimizer for scheduling - 2018
- SolverMax - OR-Tools Nurse Rostering Example
- Soon.works - LLM-assisted Constraint Programming - 2023

### Approches suggerees
- Modelisation CP avec contraintes globales (sequence, stretch, cumulative)
- Integration LLM pour l'analyse des demandes et generation de contraintes
- Optimisation multi-objectifs (minimiser couts, maximiser satisfaction)
- Exploration avec Metaheuristiques (recuit simule, algorithmes genetiques)

### Technologies pertinentes
Python, OR-Tools CP-SAT, OpenAI API/LM Studio, MCP Server

---

## 2. Probleme d'echange de reins (Kidney Exchange)

### Description du probleme et contexte
Le kidney exchange problem consiste a trouver des cycles de donneurs-receveurs incompatibles pour maximiser le nombre de transplantations. C'est un probleme de matching dans des graphes orientes avec contraintes de poids et de longueurs de cycles. Ce sujet est un classique de la RO avec un reel impact social.

### References
- Roth, Sonmez, Unver - Kidney Exchange - American Economic Review - 2007
- Abraham, Blum, Sandholm - Clearing Algorithms for Barter Exchange Markets - EC 2007
- Wikipedia - Optimal kidney exchange problem
- jamestrimble/kidney_solver (GitHub)

### Approches suggerees
- Modelisation comme graphe oriente avec cycles disjoints
- CP avec contraintes de circuit Hamiltonien limite
- Programmation lineaire en nombres entiers
- Algorithmes de clearing (approche iterative)

### Technologies pertinentes
Python, OR-Tools CP-SAT, NetworkX, PuLP

---

## 3. Ordonnancement de production (Job-Shop Scheduling)

### Description du probleme et contexte
Le Job-Shop Scheduling Problem (JSP) consiste a ordonnancer N jobs sur M machines, chaque job ayant un ordre de operations predefini. L'objectif est de minimiser le makespan (temps total d'achevement). C'est un probleme NP-difficile avec de nombreuses applications industrielles.

### References
- sysid blog - Job Shop Scheduling with CP-SAT
- IBM CP Optimizer Documentation
- Carlier and Pinson - An Algorithm for Job-Shop Scheduling - 1982
- Beck et al. - A Constraint-Guided Search Method for JSP - 2004

### Approches suggerees
- Modelisation CP avec intervalles et contraintes de precedence
- Disjunctive constraints pour les ressources machines
- Heuristiques de branchement (LNS, Large Neighborhood Search)
- Comparaison avec metaheuristiques (genetique, recuit)

### Technologies pertinentes
Python, OR-Tools CP-SAT, CPM (Critical Path Method)

---

## 4. Equilibrage de chaine d'assemblage (Assembly Line Balancing)

### Description du probleme et contexte
L'Assembly Line Balancing Problem (SALBP) vise a repartir les taches de production entre les stations de travail tout en respectant les contraintes de precedence et en minimisant le nombre de stations. C'est un probleme classique en gestion de production avec de nombreuses variantes.

### References
- Hexaly - SALBP Benchmark Documentation
- Scholl and Becker - State-of-the-art exact and heuristic solution procedures - 2006

### Approches suggerees
- Modelisation CP avec precedence constraints
- Minimisation du nombre de stations (SALBP-1)
- Minimisation du temps de cycle (SALBP-2)
- Variantes : U-lines, paralleles, mixed-model

### Technologies pertinentes
Python, OR-Tools CP-SAT, Hexaly

---

## 5. Tournees de vehicules (VRP) / Optimisation de tournees vertes

### Description du probleme et contexte
Le Vehicle Routing Problem (VRP) consiste a determiner les routes optimales pour une flotte de vehicules devant servir des clients. Les variantes incluent les contraintes de capacite, de fenetres de temps, et les objectifs ecologiques (minimisation emissions CO2).

### References
- PyVRP Documentation
- Toth and Vigo - The Vehicle Routing Problem - 2014
- Haddadene et al. - Electric VRP - 2016
- Shaw - Using Constraint Programming - 1998

### Approches suggerees
- Modelisation CP avec routes comme sequences
- Contraintes de capacite et fenetres de temps
- VRP electrique : autonomie, stations de recharge
- Column Generation et LNS pour grandes instances

### Technologies pertinentes
Python, OR-Tools Routing, PyVRP, NetworkX

---

## 6. Conception de chaine logistique (Supply Chain Network Design)

### Description du probleme et contexte
La conception de reseau logistique implique de localiser les installations (usines, entrepots) et de determiner les flux de marchandises pour minimiser les couts tout en satisfaisant la demande. C'est un probleme de localisation-allocation avec contraintes de capacite.

### References
- Ozgur and Polat - Supply Chain Network Design - 2016
- Sabharwal et al. - Formulating Fixed-Charge Network Design - 2023
- Dotoli et al. - Multi-Objective Optimization - 2005

### Approches suggerees
- Modelisation p-median et p-center avec CP
- Contraintes de capacite et de service
- Multi-objectifs : cout vs robustesse vs emissions
- Analyse de sensibilite et scenarios

### Technologies pertinentes
Python, OR-Tools CP-SAT, PuLP, GeoPandas

---

## 7. Calendriers universitaires / Planification d'emploi du temps

### Description du probleme et contexte
La confection d'horaires universitaires (timetabling) implique d'assigner des cours a des salles et des creneaux horaires en evitant les conflits. Les contraintes incluent les preferences des enseignants, la capacite des salles, et la repartition equitable des cours.

### References
- CLP (Constraint Logic Programming) Timetabling Paper
- UniTime Documentation and PhD Thesis
- Goltz et al. - University Timetabling with CP - 1999
- Schaus - Constraint Programming for Timetabling - 2014

### Approches suggerees
- Modelisation CP avec variables d'assignation
- Contraintes AllDifferent et table
- Soft constraints et penalites
- Metaheuristiques pour grandes instances

### Technologies pertinentes
Python, OR-Tools CP-SAT, pyschedule

---

## 8. Calendrier sportif (Sports Tournament Scheduling)

### Description du probleme et contexte
L'ordonnancement de tournois sportifs consiste a planifier les rencontres entre equipes en respectant les contraintes de distance, de repos, et d'equite. Les variantes incluent les championnats round-robin et les tournois a elimination.

### References
- Regin - Modeling and Solving Sports Timetabling - 2008
- Schaerf - Scheduling Sports Tournaments - 1999
- ITC (International Timetabling Competition) 2021

### Approches suggerees
- Modelisation CP avec pattern-based approach
- Contraintes de carry-over et d'equite
- Optimisation des trajets et couts de deplacement
- Decomposition : phases + finales

### Technologies pertinentes
Python, OR-Tools CP-SAT, pulp

---

## 9. Variantes avancees du Sudoku par contraintes

### Description du probleme et contexte
Le Sudoku standard est un classique de la CP. Ce sujet explore des variantes plus complexes : Killer (regions avec sommes), Samurai (grilles imbriquees), Diagonal, et autres. L'objectif est de generaliser la modelisation pour differentes regles.

### References
- Simonis - Sudoku as a Constraint Problem - 2005
- Norvig - Solving Every Sudoku Puzzle - 2006
- Cracking The Cryptic (YouTube channel)

### Approches suggerees
- Modelisation CP avec table et AllDifferent
- Extension pour contraintes arithmetiques (Killer)
- Decomposition pour grilles imbriquees (Samurai)
- Generation et difficulte automatique

### Technologies pertinentes
Python, OR-Tools CP-SAT, Z3

---

## 10. Solveur de Wordle par CSP (et LLM)

### Description du probleme et contexte
Wordle est un jeu de mots ou il faut deviner un mot de 5 lettres en 6 essais. La resolution par CSP consiste a trouver tous les mots compatibles avec les indices (vertes/jaunes). L'integration LLM permet de filtrer par vraisemblance lexicale.

### References
- Asim - Solving Wordle with CP - 2022
- hakank.org - OR-Tools Wordle solver
- OpenAI Function Calling Documentation

### Approches suggerees
- Modelisation CSP avec contraintes sur les lettres
- Filtrage par dictionnaire (WordNet, solutions lexicales)
- LLM pour ranking des mots probables
- Optimisation de la strategie de premier mot

### Technologies pertinentes
Python, OR-Tools CP-SAT, NLTK/WordNet, OpenAI API

---

## 11. Resolution automatique du Demineur par contraintes

### Description du probleme et contexte
Le Demineur (Minesweeper) est un jeu de logique ou il faut deduire la position des mines a partir des indices numeriques. La modelisation CSP permet de resoudre les situations deterministes et de guider les choix probabilistes.

### References
- Bayer and Snyder - Minesweeper is NP-Complete - 2013
- Kaye - Minesweeper is NP-Complete - 2000
- jgesc/Minesweeper_CSP (GitHub)

### Approches suggerees
- Modelisation CSP avec contraintes de somme
- Identification de configurations deterministes
- Strategies probabilistes pour les cas ambigus
- Integration avec reinforcement learning

### Technologies pertinentes
Python, OR-Tools CP-SAT, Z3, NumPy

---

## 12. Construction de mots-croises par contraintes

### Description du probleme et contexte
La generation de mots-croises consiste a remplir une grille avec des mots valides en respectant les intersections et les definitions. C'est un probleme de satisfaction de contraintes avec une base de donnees lexicale.

### References
- pedtsr.ca - Crossword Generation with CP - 2023
- SolverMax Crossword Example
- Gervet - Constraint Programming for Crosswords - 1995
- Wikipedia - Crossword -

### Approches suggerees
- Modelisation CSP avec contraintes d'intersection
- Pre-traitement de la base de donnees lexicale
- Generation de grilles avec themes
- Difficulty estimation et indices

### Technologies pertinentes
Python, OR-Tools CP-SAT, NLTK/WordNet

---

## 13. Probleme des mariages stables et School Choice

### Description du probleme et contexte
Le Stable Marriage Problem consiste a former des couples stables entre deux ensembles d'agents avec des preferences ordonnees. Les applications incluent l'affectation des etudiants aux ecoles (School Choice) et aux programmes de residency medicale.

### References
- Manlove - Stable Marriage with CP - 2008
- Gale and Shapley - College Admissions - 1962
- Gusfield and Irving - The Stable Marriage Problem - 1989

### Approches suggerees
- Algorithme de Gale-Shapley (deferred acceptance)
- Modelisation CP avec contraintes de stabilite
- Variants : incomplete preferences, ties, couples
- Optimisation du welfare social

### Technologies pertinentes
Python, OR-Tools CP-SAT, NetworkX

---

## 14. Coloration de graphe et de carte (Graph/Map Coloring)

### Description du probleme et contexte
La coloration de graphe consiste a assigner des couleurs aux sommets de sorte que les sommets adjacents aient des couleurs differentes. Les applications incluent la coloration de cartes (theoreme des 4 couleurs) et l'ordonnancement avec conflits.

### References
- AIMMS - CP Tutorial for Graph Coloring
- phabe.ch - Graph Coloring with CP-SAT - 2019
- Applegate and Cook - Chromatic Number Calculation - 1989

### Approches suggerees
- Modelisation CP avec contraintes AllDifferent
- Branchement sur les sommets (DSATUR heuristic)
- Pre-coloration et contraintes de symetrie
- Application : timetabling et frequences radio

### Technologies pertinentes
Python, OR-Tools CP-SAT, NetworkX

---

## 15. Composition musicale assistee par contraintes

### Description du probleme et contexte
La composition musicale peut etre formulee comme un probleme de satisfaction de contraintes : harmonie, rythme, contrepoint, structure. La CP permet de generer des pieces musicales respectant des criteres esthetiques et theoriques.

### References
- Anders - Constraint Programming for Music Composition - Wiley 2012
- IJCAI 2024 Tutorial on CP for Music
- Pachet and Roy - FlowComposer - 2014
- Truchet and Assayag - OpenMusic - 2016

### Approches suggerees
- Modelisation CP avec contraintes d'harmonie
- Generation melodique avec contour et intervalles
- Integration avec MIDI et synthesis audio
- Interactive constraint programming

### Technologies pertinentes
Python, OR-Tools CP-SAT, music21, MIDIUtil

---

## 16. Assistant de planification conversationnel (LLM + CSP)

### Description du probleme et contexte
Un assistant de planification conversationnel combine un LLM pour l'interaction en langage naturel et un solveur CP pour la resolution des contraintes. Le LLM extrait les preferences, le solveur trouve des solutions, le LLM explique et itere.

### References
- OpenAI Function Calling Documentation
- Soon.works - LLM-assisted Constraint Programming - 2023
- Xu et al. - Conversational Planning - 2023
- MCP (Model Context Protocol) Specification
- Pipeline : LLM -> extraction -> CP -> LLM -> feedback
- Definition d'un schema de contraintes structure

### Approches suggerees
- Integration via MCP ou function calling
- Cas d'usage : voyage, repas, evenements

### Technologies pertinentes
Python, OR-Tools CP-SAT, OpenAI API/LM Studio, FastAPI

---

## 17. Configuration de produit par contraintes

### Description du probleme et contexte
La configuration de produit consiste a selectionner des options (composants, features) pour construire un produit valide. Les contraintes de compatibilite et de prerequisites rendent ce probleme ideal pour la CP.

### References
- foohardt/or-tools-product-configurator (GitHub)
- Mittal and Frayman - Product Configuration - 1989
- Hotz - Configuration as CSP - 2014

### Approches suggerees
- Modelisation CSP avec variables de configuration
- Contraintes de compatibilite et de prerequisites
- Propagation des choix et explication
- Integration avec interface web

### Technologies pertinentes
Python, OR-Tools CP-SAT, Flask/FastAPI

---

## 18. Optimisation de portefeuille financier sous contraintes

### Description du probleme et contexte
L'optimisation de portefeuille (Markowitz) vise a maximiser le rendement pour un niveau de risque donne. Les contraintes incluent les limites de poids, les secteurs, et les couts de transaction. C'est un probleme quadratique avec contraintes lineaires.

### References
- Markowitz - Portfolio Selection - 1952
- StackOverflow - CP-SAT for Portfolio Optimization
- Michalewicz - Genetic Algorithms for Finance - 2000

### Approches suggerees
- Modelisation CP avec objectif de rendement
- Contraintes de budget, de poids, de diversification
- Linearisation de la variance (approximation)
- Backtesting et scenario analysis

### Technologies pertinentes
Python, OR-Tools CP-SAT, pandas, yfinance

---

## 19. Planification urbaine et placement d'infrastructures

### Description du probleme et contexte
La planification urbaine implique de localiser des infrastructures (ecoles, hopitaux, transports) pour maximiser l'accessibilite tout en minimisant les couts. Les contraintes incluent la capacite, la distance, et les preferences des residents.

### References
- IBM CP Optimizer Urban Planning Examples
- Chabrier - Facility Location Problems - 2006
- CACIC 2017 - Urban Planning with CP

### Approches suggerees
- Modelisation p-median et p-center
- Contraintes de capacite et de couverture
- Multi-objectifs : accessibilite vs cout vs equite
- Integration avec donnees geospatiales

### Technologies pertinentes
Python, OR-Tools CP-SAT, GeoPandas, OSMnx

---

## 20. Tournees de livraison vertes (Electric VRP)

### Description du probleme et contexte
Le Electric VRP etend le VRP classique avec des vehicules electriques ayant des contraintes d'autonomie et des besoins de recharge. L'objectif est de minimiser les emissions et le cout energetique.

### References
- Booth and Beck - Electric VRP with CP - 2018
- Shaw - VRP with Constraint Programming - 1998
- OR-Tools Routing Documentation

### Approches suggerees
- Modelisation CP avec contraintes d'energie
- Stations de recharge : localisation et scheduling
- Optimisation multi-objectifs (distance + energie)
- Scenario avec flotte mixte (electrique + thermique)

### Technologies pertinentes
Python, OR-Tools Routing, PyVRP

---

## 21. Jeux de strategie par CSP (Quoridor, Hex, etc.)

### Description du probleme et contexte
Les jeux de strategie comme Quoridor (barrieres et deplacements) et Hex (connexion de bordes) peuvent etre resolus ou analyses par CSP. La modelisation permet de trouver des strategies gagnantes et d'explorer l'espace de jeu.

### References
- Quoridor Rules (Gigamic)
- AAAI Workshop on Board Games
- Schaeffer - Games, Puzzles, and Computation - 2008

### Approches suggerees
- Modelisation CSP avec contraintes de mouvement
- Recherche de strategie gagnante (retrograde analysis)
- Generation de puzzles et niveaux
- Integration avec IA classique (minimax, MCTS)

### Technologies pertinentes
Python, OR-Tools CP-SAT, Z3, pygame

---

## 22. Allocation de ressources cloud (VM Scheduling)

### Description du probleme et contexte
Le placement de machines virtuelles (VM) sur des serveurs physiques vise a optimiser l'utilisation des ressources (CPU, RAM) tout en respectant les contraintes de capacite et de localisation. C'est un probleme de bin packing avec contraintes.

### References
- Zhang - VM Resource Allocation with CP - VCRA-CP
- Van et al. - VM Selection as CSP

### Approches suggerees
- Modelisation bin packing avec CP
- Contraintes de capacite et d'affinite
- Minimisation du nombre de serveurs actifs
- Dynamic allocation et migration

### Technologies pertinentes
Python, OR-Tools CP-SAT, pulp

---

## 23. Planification multi-robots dans un entrepot

### Description du probleme et contexte
La planification multi-robots (MAPF - Multi-Agent Path Finding) consiste a coordonner les deplacements de plusieurs robots dans un espace partage. Les contraintes incluent l'evitement de collision et l'optimisation du temps total.

### References
- Booth - MAPF with CP - ICAPS 2016
- Wang et al. - MAPF Survey - AAMAS 2019

### Approches suggerees
- Modelisation CSP avec contraintes spatiales et temporelles
- Conflict-Based Search (CBS) et CP
- Decomposition : planification individuelle + coordination
- Application : entrepots, usines 4.0

### Technologies pertinentes
Python, OR-Tools CP-SAT, NetworkX

---

## 24. Planification de trajectoire robotique sous contraintes

### Description du probleme et contexte
La planification de trajectoire (path planning) pour robots mobiles implique de trouver un chemin executable en respectant les contraintes cinematiques et dynamiques. Les environnements dynamiques ajoutent de la complexite.

### References
- Wang et al. - Path Planning Survey - AAMAS 2019
- Lopez et al. - Robot Motion Planning - ICAPS 2012

### Approches suggerees
- Modelisation CSP avec discretisation espace-temps
- Contraintes de collision et de cinematique
- Integration avec A* et RRT
- Application : robots mobiles, bras robotiques

### Technologies pertinentes
Python, OR-Tools CP-SAT, Shapely, ROS

---

## 25. Verification de contrats intelligents (blockchain) par contraintes

### Description du probleme et contexte
La verification formelle de smart contracts (Ethereum) utilise SMT solvers comme Z3 pour detecter les vulnerabilites (re-entrancy, overflow). La modelisation des contraintes d'execution permet une analyse statique rigoureuse.

### References
- Luu et al. - Oyente - CCS 2016
- Solidity SMTChecker Documentation
- Zellic - WETH Audit - 2020
- FlawCheck - Smart Contract Verification - 2020

### Approches suggerees
- Modelisation SMT avec Z3
- Detection de re-entrancy, integer overflow, access control
- Symbolic execution des smart contracts
- Integration avec outils de dev (Hardhat, Foundry)

### Technologies pertinentes
Python, Z3 SMT Solver, Solidity, Slither

---

## 26. Selection de transactions dans un bloc blockchain

### Description du probleme et contexte
La selection de transactions pour un bloc blockchain est un probleme de knapsack avec contraintes de taille et de frais (gas). Les mineurs/selecteurs doivent maximiser les frais tout en respectant les limites de bloc.

### References
- Bonneau et al. - On Bitcoin Mining - CITP 2014
- Narayanan et al. - Bitcoin and Cryptocurrency Technologies
- Arxiv - MEV and Transaction Ordering - 2024

### Approches suggerees
- Modelisation knapsack avec CP-SAT
- Contraintes de taille et de gas
- Extension : ordering des transactions (MEV)
- Comparaison avec heuristiques gloutonnes

### Technologies pertinentes
Python, OR-Tools CP-SAT, web3.py

---

## 27. Optimisation energetique de centres de donnees (Green Scheduling)

### Description du probleme et contexte
L'optimisation energetique des data centers vise a reduire la consommation electrique en regroupant les charges sur moins de serveurs (consolidation) et en utilisant les energies renouvelables. Les contraintes incluent la performance et le refroidissement.

### References
- Kishore et al. - Green Scheduling - IEEE 2018
- Google - Carbon Intelligent Computing
- OR StackExchange - Data Center Optimization

### Approches suggerees
- Modelisation CP avec contraintes de placement
- Minimisation de la consommation (PUE)
- Integration avec les prix de l'electricite
- Dynamic workload management

### Technologies pertinentes
Python, OR-Tools CP-SAT, pulp

---

## 28. Affectation d'etudiants a des projets/stages

### Description du probleme et contexte
L'affectation d'etudiants a des projets ou stages implique de matcher les preferences des etudiants avec les offres des entreprises, tout en respectant les capacites et la diversite. C'est une extension du probleme des mariages stables.

### References
- Gent - Stable Marriage for Student Allocation - CP
- Manlove - Student-Project Allocation Problem - SPA-P

### Approches suggerees
- Modelisation CP avec preferences
- Extension du Stable Marriage Algorithm
- Contraintes de capacite et de diversite
- Optimisation du welfare global

### Technologies pertinentes
Python, OR-Tools CP-SAT, NetworkX

---

## 29. Generation automatique de cas de test logiciel par contraintes

### Description du probleme et contexte
La generation de cas de test par execution symbolique (symbolic execution) consiste a explorer les chemins d'execution d'un programme en resolvant les contraintes sur les entrees. Z3 et autres SMT solvers sont utilises pour generer des inputs.

### References
- Cadar et al. - KLEE - OSDI 2008
- Godefroid et al. - DART - PLDI 2005
- VerificationGlasses Tutorial
- Symbolic execution avec Z3

### Approches suggerees
- Generation de inputs pour atteindre du code
- Detection de bugs et vulnerabilites
- Integration avec CI/CD

### Technologies pertinentes
Python, Z3 SMT Solver, angr, triton

---

## 30. Placement de services en edge computing avec contraintes de latence

### Description du probleme et contexte
Le placement de services en edge computing consiste a deployer des applications sur des noeuds de calcul distribues pour minimiser la latence et la consommation de bande passante. Les contraintes incluent les ressources et la localisation.

### References
- Zhang - Edge Placement with CP - ENPP
- Guyonet et al. - Edge Resource Allocation - CP 2021
- Azure Edge Zones Documentation

### Approches suggerees
- Modelisation p-median avec contraintes de ressources
- Optimisation multi-objectifs (latence + cout)
- Dynamic placement et migration
- Integration avec Kubernetes

### Technologies pertinentes
Python, OR-Tools CP-SAT, Kubernetes API

---

## 31. Ordonnancement de missions satellites

### Description du probleme et contexte
Le satellite scheduling problem consiste a planifier les prises de vue et les communications de satellites en respectant les contraintes orbitales, energetiques et de priorite. C'est un probleme de scheduling avec fenetres de temps.

### References
- Frank et al. - EUROPA - NASA
- Jussien - Satellite Scheduling with CP - ONERA 2015
- DIMACS Challenge 1998

### Approches suggerees
- Modelisation CP avec intervalles et fenetres de temps
- Contraintes orbitales et energetiques
- Multi-satellites et constellations
- Optimisation de la valeur scientifique

### Technologies pertinentes
Python, OR-Tools CP-SAT, Skyfield (astronomy)

---

## 32. Planification d'itineraires touristiques personnalises (TTDP/Orienteering)

### Description du probleme et contexte
Le Tourist Trip Design Problem (TTDP) consiste a selectionner et ordonnancer des points d'interet pour maximiser la satisfaction du touriste tout en respectant les contraintes de temps, de budget et de localisation. C'est une variante du Orienteering Problem.

### References
- Vu et al. - Branch-and-Check for TTDP
- Souffriau et al. - TTDP Survey
- Vansteenwegen et al. - Orienteering Problem Survey
- Wikipedia - Orienteering Problem -

### Approches suggerees
- Modelisation CP avec scores et durees
- Contraintes de temps et de budget
- Personnalisation par preferences utilisateur
- Integration avec donnees geospatiales (OSM)

### Technologies pertinentes
Python, OR-Tools CP-SAT, OSMnx, pandas

---

## 33. Cryptanalyse d'un chiffre par substitution (decryptage automatise)

### Description du probleme et contexte
La cryptanalyse de chiffres par substitution monoalphabetique consiste a retrouver la clef de chiffrement en analysant la distribution des lettres et les motifs du texte. La modelisation CSP permet de combiner des contraintes linguistiques et statistiques.

### References
- Cornell - Cryptanalysis with CSP - BOOM 2001
- Lucks - Cryptanalysis and CP - Crypto 1988
- Wikipedia - Substitution cipher -

### Approches suggerees
- Modelisation CSP avec contraintes de permutation
- Frequences des lettres et bigrammes
- Dictionnaire et motifs de mots
- Integration avec NLP (language models)

### Technologies pertinentes
Python, OR-Tools CP-SAT, NLTK, frequency analysis

---

