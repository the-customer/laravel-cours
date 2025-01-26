1. Introduction
2. Creation de middleware:
    - php artisan make:middleware Name
3. Les trois (3) types de middlewares:
    Il sont definis dans App/Http/Middleware/Kernel.php
    - Global Middleware : pour toute les requetes de l'application
        - Creer un middleware et ajouter le chemin dans la propriete "$middlewares" de Kernel
         Utiliser $request->has('propriete') pour tester si la requete contient une information....
        - Utiliser in_array($request->...,$array) pour tester si la requete contient une information....
        - Utiliser request()->is('routeName') pour exclure une route
    - Group Middleware:
        - Creer un middleware et ajouter le chemin dans la propriete "$middlewareGroups" de Kernel :
            - dans web
            - dans api
            - dans une nouvelle cle
        - Appeler le middleware dans un groupe de route :
            - Route::group(["middleware"=>"middlewareGroupName"],function(){...})
    - Route Middleware:
        - Meme chose que les Group Middleware mais ici, on peut pas les regrouper, chaque nom est pour un seul middleware
        - Creer un middleware et ajouter le chemin dans la propriete "$r outeMiddleware" de Kernel
        - Route::group(["middleware"=>"middlewareGroupName"],function(){...})
        - Router::verb(...)->middleware('routeMiddelewareName')