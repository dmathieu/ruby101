!SLIDE small
# Appel à une méthode inexistante

    @@@ ruby
    class Conference
      def method_missing(method, *args)
        logger.warn "Méthode inconnue #{method} appelée"
      end
    end
    
    c = Conference.new
    c.fin  #=> Aucune exception n'est soulevée