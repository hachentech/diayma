#Boutique Diayma

Question 6 -
Lors de l’exploitation on constate ces deux bugs suivants :
-	La traduction en espagnol n’est pas fonctionnelle l’option est disponible mais ne marche pas
-	Le calcul du total ne tient pas compte de la quantité dès qu’on commande 2 ou plus item du même article


Question 8 — Parcours avant l’affichage des produits

Un namespace regroupe les classes du programme. Une classe décrit un objet. Une méthode réalise une action. Un constructeur est une méthode appelée lorsqu’un objet est créé.

1. Namespace « P2FixAnAppDotNetCode », classe « Program » : la méthode « Main » démarre l’application et appelle « BuildWebHost ».

2. Namespace « P2FixAnAppDotNetCode », classe « Startup » : le constructeur reçoit la configuration. « ConfigureServices » enregistre les services. « Configure » prépare le pipeline web et la route d’accueil.

3. Namespace « P2FixAnAppDotNetCode.Controllers », classe « ProductController » : la méthode « Index » demande la liste des produits à « ProductService.GetAllProducts() ».

4. Namespace « P2FixAnAppDotNetCode.Models.Services », classe « ProductService » : la méthode « GetAllProducts » demande les produits au dépôt.

5. Namespace « P2FixAnAppDotNetCode.Models.Repositories », classe « ProductRepository » : la méthode « GetAllProducts » garde les produits en stock et les trie par nom. La liste revient ensuite au contrôleur.

6. La vue Razor « Views/Product/Index.cshtml » parcourt la liste et construit le tableau des produits. La mise en page appelle aussi « CartSummaryViewComponent.Invoke() » pour afficher le résumé du panier. Cette classe se trouve dans le namespace « P2FixAnAppDotNetCode.Components ».

Pour observer l’exécution, j’utilise trois commandes. Le pas à pas détaillé (F11) entre dans la méthode appelée, par exemple pour suivre le passage du service au dépôt. Le pas à pas principal (F10) exécute la ligne courante sans ouvrir la méthode appelée. Le pas à pas sortant (Maj+F11) termine la méthode en cours et revient à celle qui l’a appelée.