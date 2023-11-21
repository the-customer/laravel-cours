1. OneToOne:
    - $this->hasOne(Model::class) 
        => la cle etrangere est dans l'autre table
    - $this->hasOne(Model::class,foreign,local)
2. OneToOne Inverse: 
    - $this->belongsTo(Model::class) 
        => la cle etrangere est dans cette table 
3. OneToMany:
    - $this->hasMany(Model::class) 
    - $this->belongsTo(Model::class) 
        => ajouter la relation dans l'autre Model
4. ManyToMany:
    - $this->belongsToMany(Model::class)
        Ex:
            article <-> tag
    - $articleObj->relationName()->attach($tagObj | tagIdArray)

