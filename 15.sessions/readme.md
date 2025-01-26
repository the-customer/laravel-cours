0. Config:
    - config/session.php
1. Recuperer les donnees de la session:
    - Toutes les donnees:
        - session()->all()
        - Request $request->session()->all()
    - Une donnee ciblee:
        - session()->get('keyName')
        - Request $request->session()->get('keyName')
2. Mettre une donnee dans la session:
    - $request->session()->put('key','value')
    - $request->session()->put(['key' => 'value'])
    - session(['key' => 'value'])
3. Supprimer une donnee de la session:
    - $request->session()->forget('key')
    -  session()->forget('key')
        => Supprimer une donnee
    - $request->session()->forget(['key1','key2',...])
        => Supprimer plusieurs donnees
    - $request->session()->flush()
    - session()->flush()
        => Supprimer toutes les donnees de la session
4. Flash session:
    - $request->session()->flash('key','value')
    - session()->flash('key','value')