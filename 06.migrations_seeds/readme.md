1. Configuration de la connexion à la base de données
2. Creation de fichier de migration
3. Les types de donnees d'une table
4. Commandes de migration a savoir
    - php artisan migrate:reset 
        => supprimer toutes les tables
    - php artisan migrate:rollback 
        => Annuler la derniere action
    - php artisan migrate --path=/database/migrations/nom_fichier.php
        => Migrer un fichier cible
    - php artisan migrate:refresh
        => Supprimer les tables et les recreer (effacer les donnees des tables, cas pratique: ajout de colonne apres migration)
5. Ajout de nouvelle colonne à une table
    - php artisan make:migration addColumnToTablename --table=tableName
6. Ajout de fausse donnees par Seeders
    - php artisan make:seeder ModelSeeder
        => Creer le fichier seeder
    - DB::table("tableName")->insert([
        'colonne'   => Str::random(20),
        ...
    ])
    - $this->call(ModelSeeder::class)
    - php artisan db:seed