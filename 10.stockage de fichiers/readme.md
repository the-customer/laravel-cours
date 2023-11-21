
1. Configuration de stockage : stockage/app/public
    - config/filesustems.php
        => Pour voir la configuration
    - FILESYSTEM_DISK=public
        => dans le fichier .env
2. Formulaire d'ajout de fichier
    - enctype="multipart/form-data"
    - @csrf
    - ImageController
        - methode: upload
3. Formulaire d'ajout de fichier : logique metier
    - $request->file('imageName')
        => Recuperer l'image
    - $request->imageName->store('/')
        => Stocke l'image dans storage/app/public, on peut changer le chemin.
        Ex : $request->imageName->store('/images')
    - $request->imageName->storeAs('/images','newImageName.extension')
        => Changer le nom de l'image
4. Storage link:
    - <img src ='{{ asset("storage/app/public/images/imageName.extension") }}' /> ❌
        => Pour afficher l'image dans une vue, NE MARCHE PAS car il faut relier le dossier
        storage au dossier public 
    - php artisan storage:link 
        => SymLink ou Symbolic link
    - <img src ='{{ asset("/storage/images/imageName.extension") }}' /> ✅
5. Supprimer une image du stockage:
    - Storage::delete('/images/imageName.extension')
    OU BIEN 
    - Storage::disk('public')->delete('/images/imageName.extension')
    OU
    - File::delete(storage_path('/app/public/images/imageName.extension'))
    OU
    - unlink(storage_path('/app/public/images/imageName.extension'))

6. Validation:
    - required
    - min:taille (en KO)
    - max:taille (en KO)
    - mimes:png,jpg,... OU BIEN image
