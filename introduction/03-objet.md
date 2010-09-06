!SLIDE small
# (presque) tout est objet

    @@@ ruby
    -42.abs              #=> Renvoie 42
    -42.class            #=> Renvoie Fixnum
    
    string = "hello world"
    string.upcase        #=> Renvoie "HELLO WORLD"
    puts string          #=> Affiche "hello world"
    string.upcase!       #=> Renvoie "HELLO WORLD"
    puts string          #=> Affiche "HELLO WORLD"
    
    nil.class            #=> Renvoie NilClass
    true.class           #=> Renvoie TrueClass
    false.class          #=> Renvoie FalseClass
    nil.nil?             #=> Renvoie true
    

!SLIDE small
# Déclaration d'une classe

    @@@ ruby
    class Conference
      
      def initialize(name, duration=10)
        @name, @duration = name, duration
      end
      
      def name
        @name
      end
      
      def duration
        @duration
      end
      
      def to_s
        "#{name} qui dure #{duration.to_s} minutes"
      end
    end
    
    conf = Conference.new 'JDLL', 40
    conf.to_s      #=> Retourne "JDLL qui dure 40 minutes"

!SLIDE small
# Héritage

    @@@ ruby
    class JDLL < Conference
      
      def to_s
        "#{super} le 16 octobre"
      end
    end
    
    
    
    jdll = JDLL.new 'Ruby 101', 40
    jdll.to_s
    #=> Retourne "Ruby 101 qui dure 40 minutes le 16 octobre"