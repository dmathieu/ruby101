!SLIDE small
# Itérateurs

    @@@ ruby
    jours = ['Lundi', 'Mardi', 'Mercredi',
      'Jeudi', 'Vendredi', 'Samedi', 'Dimanche']
      
    jours.each do |jour|   #=> Pour chaque jour
      puts "Un jour de la semaine : #{jour}"
    end

!SLIDE small
# Itérateurs

    @@@ ruby
    jours = {
      'Lundi' => 'Travaillé',
      'Mardi' => 'Travaillé',
      'Dimanche' => 'Non Travaillé'
    }
    
    jours.each do |jour| #=> Pour chaque clé
      puts "Le #{jour} est #{jours[jour]}"
    end

!SLIDE small
# Itérateurs

    @@@ ruby
    jours = {
      'Lundi' => 'Travaillé',
      'Mardi' => 'Travaillé',
      'Dimanche' => 'Non Travaillé'
    }
    jours.each_pair do |jour, activite| #=> Pour chaque paire
      puts "Le #{jour} est #{activite}"
    end

!SLIDE small
# Itérateurs

    @@@ ruby
    File.open('production.log') do |fichier|
        #=> Ouverture du fichier
      fichier.each_line do |ligne|
          #=> Itération sur chaque ligne
        puts ligne #=> Affichage de la ligne courante
      end
    end          #=> Fermeture automatique