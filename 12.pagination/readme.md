- Dans le controller : 
    - $data = Model::paginate(nPerPage)
- Dans la vue:
    - {{ $data->links() }}
- Dans AppServiceProvider: dans la methode boot:
    Paginator::userBoostrap()
        => Rendre le rendue plus cool