!SLIDE small
# Idiomes

    @@@ ruby
    def method(options)    #=> Un seul argument, un hash
      options = { :param1 => 'valeur par défaut' }
          #=> Des valeurs par défaut
      options.merge! params   #=> Que l'on remplace
    end

!SLIDE small
# Idiomes

    @@@ ruby
    method( {:param1 => 'valeur1', :param2 => 'valeur2'} )
    
    method( :param1 => 'valeur1', :param2 => 'valeur2' )
    
    method	:param1 => 'valeur1', :param2 => 'valeur2'

!SLIDE small
# Idiomes

    @@@ ruby
    obj.delete_at(1).gsub(/e/, 'r').upcase
        #=> Chainage des méthodes
        #=> Ruby renvoyant la dernière expression évaluée