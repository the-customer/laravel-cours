1. Redirection:
    - return redirect('/routePath')
    ou
    - return redirect()->route('routeName')
    ou
    - return redirect()->back()
2. Reponse JSON :
    - return response()->json($data)
    ou
    - return response($data)
3. Fichier a telecharger:
    - return response()->download(public_path('/storage/images/...'))