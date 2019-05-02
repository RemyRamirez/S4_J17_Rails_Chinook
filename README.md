# S4_J17_Rails_Chinook

Maintenant que ta BDD est prête, tu vas répondre aux questions ci-dessous :
a) Niveau facile

    Quel est le nombre total d'objets Album contenus dans la base (sans regarder les id bien sûr) ?
        Album.count
        ==> 347
    Qui est l'auteur de la chanson "White Room" ?
        u = Track.find_by(title: "White Room")
        u.artist
        ==> Eric Clapton
    Quelle chanson dure exactement 188133 milliseconds ?
        u = Track.find_by(duration: 188133)
        u.title
        ==> "Perfect"
    Quel groupe a sorti l'album "Use Your Illusion II" ?
        u = Album.find_by(title: "Use Your Illusion II")
        u.artist
        ==> "Guns N Roses"

b) Niveau Moyen

    Combien y a t'il d'albums dont le titre contient "Great" ? (indice) 
    Album.where("title like ?", "%Great%").count
    ==> 13
    
    Supprime tous les albums dont le nom contient "music".
    u = Album.where("title like ?", "%music%")
    u[1].destroy

    Combien y a t'il d'albums écrits par AC/DC ?
    Album.where("artist like ?", "%AC/DC%").count
    ==> 2

    Combien de chanson durent exactement 158589 millisecondes ?
    Track.where("duration like ?", 158589).count
    ==> 0

c) Niveau Difficile

Pour ces questions, tu vas devoir effectuer des boucles dans la console Rails. C'est peu commun mais c'est faisable, tout comme dans IRB.

    - puts en console tous les titres de AC/DC.
    0.upto(u.size-1) { |index| puts u[index].title }

For Those About To Rock We Salute You
Let There Be Rock
 => 0

    - puts en console tous les titres de l'album "Let There Be Rock".
    - Calcule le prix total de cet album ainsi que sa durée totale.
    - Calcule le coût de l'intégralité de la discographie de "Deep Purple".
    - Modifie (via une boucle) tous les titres de "Eric Clapton" afin qu'ils soient affichés avec "Britney Spears" en artist.
