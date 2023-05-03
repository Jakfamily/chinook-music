# README

creation d'une db artiste 
creation d'une db track
manipulation db afin de repondre au quizz 

quiz sur db 

-Quel est le nombre total d'objets Album contenus dans la base (sans regarder les id bien sûr) ?347
-Qui est l'auteur de la chanson "White Room" ? eric clapton
-Quelle chanson dure exactement 188133 milliseconds ? perfect de jhon morisette
-Quel groupe a sorti l'album "Use Your Illusion II" ? existe pas 

-Combien y a t'il d'albums dont le titre contient "Great" ? where("title like ?","%great%").count = 13
-Supprime tous les albums dont le nom contient "music"Album.where("name LIKE ?", "%music%").destroy_all
-Combien y a t'il d'albums écrits par AC/DC ? Album.where("artist like ?","%AC/DC%").count = 2
-Combien de chanson durent exactement 158589 millisecondes ? Track.find_by(duration:158589) = 0

-puts en console tous les titres de AC/DC.

acdc_tracks = Track.where(artist: "AC/DC")
acdc_tracks.each do |track|
  puts track.title
end

-puts en console tous les titres de l'album "Let There Be Rock".

rock_tracks = Track.where(album: "Let There Be Rock")
rock_tracks.each do |track|
  puts track.title
end

-Calcule le prix total de cet album ainsi que sa durée totale.

album_tracks = Track.where(album: "Let There Be Rock")
total_price = 0
total_duration = 0

album_tracks.each do |track|
  total_price += track.price
  total_duration += track.duration
end

puts "Le prix total de l'album est : #{total_price} euros"
puts "La durée totale de l'album est : #{total_duration} millisecondes" = 7.92 prix / 2453259 miliseconde

-Calcule le coût de l'intégralité de la discographie de "Deep Purple".

deep_purple_tracks = Track.where(artist: "Deep Purple")
total_cost = 0

deep_purple_tracks.each do |track|
  total_cost += track.price
end

puts "Le coût total de la discographie de Deep Purple est de : #{total_cost} euros" = 99.08

-Modifie (via une boucle) tous les titres de "Eric Clapton" afin qu'ils soient affichés avec "Britney Spears" en artist.

tracks = Track.where(artist: "Eric Clapton")

tracks.each do |track|
  track.artist = "Britney Spears"
  track.save
end



