1. Exemple d'introduction pour comprendre la nomenclature:
    - php artisan make:model ModelName
        => Le nom du model doit reprendre le nom de la table au SINGULIER en pascal case. exemple 1: php artisan make:model Article
    - Article::all()
        => Recuperer tous les Article
        => Remarque : php artisan make:model MyArticle.
        Remarque: MyArticle::all() -> Erreur
        - protected $table = 'articles' -> ✅
2. Recuperation d'enregistrements de la base:
    - Model::all() <=> DB::table('tableName')->get()
    - Model::find(id) => Page Blache si id n'existe pas ✅
    - Model::findOrFail(id) => Page 404 si id n'existe pas ❌
3. Utilistion de la clause WHERE:
    - Model::where("column","operator","value")->get()
    - Model::where(....)->where(...)->where(...)...->get()
    - Model::where(....)->orWhere(...)->get()
4. Inserer des donnees dans la base:
    - object->save()
5. Metre a jour une donnee de la base:
    - a. recuperer l'enregistrement a modifier
    - b. Modifier les champs cibles
    - c. object->save()
6. Supprimer un enregistrement:
    - Model::find(id)->delete()
7. Mass Assignment
    - $fillable
    - $guarded
8. Soft Delete :
    a. Dans le model:
        - use SoftDeletes (Trait)
    b. Ajouter la colonne deleted_at: (migration)
        - $table->softDeletes () vs $table->dropsoftDeletes()
    c. Supprimer:
        - Model::find(id)->delete()
9. Recuperer un enregistrement supprimé:
    - Model::onlyTrashed()->get()
10. Restaurer un enregistrement supprimé:
    - Model::withTrashed()->find(id)->restore()
11. Suppression totale:
    - Model::withTrashed()->find(id)->forceDelete()
12. Factories:
    - php artisan make:factory ModelFactory
    - fake:
        - fake()->title() ou $this->faker()->...
        - fake()->sentence()
        - fake()->paragraph()
        - fake()->date()
        - fake()->firstName()
        - fake()->lastName()
        - fake()->email()
        - fake()->dateTime()
        - fake()->name()
        - fake()->numberBetween(min,max)
        - fake()->imageUrl()
        - rand(min,max)
    - DatabaseSeeder:
        - Model::factory(number)->create()
    - php artisan db:seed

