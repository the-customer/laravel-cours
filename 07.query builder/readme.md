1. Recuperer les donnees de la base:
    - DB::table("tableName")->get()
        => Recuperer toutes donnees d'une table
    - DB::table("tableName")->find(id)
        => Recuperer une donnees par son id
    - DB::table("tableName")->first()
        => Recuperer le premier resultat
2. Recuperer les donnees de certaines colonnes
    - DB::table("tableName")->pluck("columnName")
3. La clause WHERE
    - DB::table("tableName")->where("columnName","operator","value")->get()
4. Inserer des donnees dans la base
    - DB::table("tableName")->insert(["columnName"=>value,...])
    - DB::table("tableName")->insert([
        ["columnName"=>value,...],
        ["columnName"=>value,...],
    ])
5. Mettre a jour un enregistrement
    - DB::table("tableName")->where("columnName","operator","value")->update([
        "column"    => value
    ])
6. Supprimer un enregistrement
    - DB::table("tableName")->where("columnName","operator","value")->delete()
    - DB::table("tableName")->delete(id) 
6. Jointure
    - DB::table("tableName1")->join("tableName2","tablename1.column","=","tableName2.column")->get()
    - DB::table("tableName1")->join("tableName2","tablename1.column","=","tableName2.column")
    ->select("tableName1.*")
    ->get()
7. Les fonctions d'agrégation
    - DB::table("tableName")->count()
    - DB::table("tableName")->sum("columnName")
    - DB::table("tableName")->avg ("columnName")
    - DB::table("tableName")->max ("columnName")
    - DB::table("tableName")->min ("columnName")
