1. Creation d'un formulaire html
    - Erreur 419 : Page expired
    - VerifyCsrftoken.php (middleware)
        $except = ['*']
2. CSRF token
    - @csrf
    - $request->all()
        => Pour verifier les donnees soumises
3. Validation des champs
    - $request->validate([
        "field1" => "validation1|validation2|,...",
        "field2" => "validation1|validation2|,...",
    ])
    - $request->validate([
        "field1" => ["validation1","validation2",...],
        "field2" => ["validation1","validation2",...],
    ])
    - @if($errors->any())
        @foreach($errors->all() as $error)
        => Afficher les erreurs dans les vues
4. Autres validations
6. Redefinir les messages de validations par defaut
    a. Dans le controleur : en passant un tableau comme deuxieme argument de la methode $request->validate()
    b. Dans une classe dediee a la requete 
        - php artisan make:request ModelRequest