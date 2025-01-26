1. Creation de composant
    - php artisan make:component Name
    - php artisan make:component Name --inline
        => creation d'un seul fichier
    - php artisan make:component path/Name
2. Utilisation d'un composant blade:
    - <x-componant/>
    - <x-path.componant/>
        => Utiliser la notation kebab-case
3. Passage de donnees:
    - Ajouter une proprite public dans la classe du composant
    - Initialiser la propriete dans le constructeur
        => les proprite et methode public sont directement accessibles dans la vue du composant
    - Passer la donnee au template:
        - <x-componant :propety="$value"/>
4. Les slots:
    - slot par defaut:
        - Dans le composant:
            {{ $slot }}
        - <x-componant>donnee</x-componant>
    - slot nommé:
        - Dans le composant:
            {{ $slotName }}
        - <x-componant>
                <x-slot name="slotName">
                    data
                </x-slot>
          </x-componant>