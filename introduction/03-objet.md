!SLIDE small
# (presque) tout est objet

    @@@ ruby
    -42.abs              #=> Renvoie 42
    -42.class            #=> Renvoie Fixnum

    string = "hello world"
    string.upcase        #=> Renvoie "HELLO WORLD"

!SLIDE small
    nil.class            #=> Renvoie NilClass
    true.class           #=> Renvoie TrueClass
    false.class          #=> Renvoie FalseClass
    nil.nil?             #=> Renvoie true


!SLIDE small
# Déclaration d'une classe

    @@@ ruby
    class Conference
      attr_accessor :name, :duration
      def initialize(name, duration=10)
        @name, @duration = name, duration
      end

      def to_s
        "#{name} qui dure #{duration.to_s} minutes"
      end
    end
    conf = Conference.new 'Ruby101', 40
    conf.to_s      #=> Retourne "Ruby101 qui dure 40 minutes"

!SLIDE small
# Héritage

    @@@ ruby
    class Ruby101 < Conference

      def to_s
        "#{super} le #{Date.today}"
      end
    end

    course = Ruby101.new 'Ruby 101', 40
    course.to_s
    #=> Retourne "Ruby 101 qui dure 40 minutes le 2011-12-12"
