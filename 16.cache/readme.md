0. cache vs session:
    - portée
    - accessibilité
    - performance
1. Installation du debug bar: 
    - lien : https://github.com/barryvdh/laravel-debugbar
    - composer require barryvdh/laravel-debugbar --dev
    - php artisan vendor:publish --provider="Barryvdh\Debugbar\ServiceProvider"

2. Charger des donnees dans la cache:
    - $datas = Cache::remember('cacheName',durationInSecond, function(){
        return dataFromDataBase (ex: Article::all() ou Article::paginate(5) ou Article::with('..')->paginate())
    });
        => les donnees sont maintenant dans le cache (storage/framework/cache/data/..)