!SLIDE small
# Identificateurs

    @@@ ruby
    message = "Bonjour tout le monde" #=> Variable locale
    
    $message = "Bonjour tout le monde" #=> Variables globale
    $LOAD_PATH
    
    Message = "Bonjour tout le monde" #=> Constantes
    MA_CONSTANTE = "Bonjour tout le monde"

!SLIDE small
# "Littéraux"

    @@@ ruby
    1      #=> Nombres
    1.3
    
    "Bonjour tout le monde" #=> Chaine de caractères
    
    "Salut #{nom}" #=> Interpolation de variable
    
    [1, 2, 3, 'hello'] #=> Liste / Tableau
    
    { :présentation => 'Ruby 101', :orateur => 'Damien'}
    #=> Tableau Associatif

!SLIDE small
# Structures conditionnelles

    @@@ ruby
    if reponse == 42
      puts "Mais quelle était la question ?"
    else
      puts "#{reponse} n'est pas une bonne réponse"
    end
    
    puts "Pas suffisamment agé" unless age >= 18
    
    puts reponse == 42 ? "Good !" : "Bad !"

!SLIDE small
# Structures conditionnelles

    @@@ ruby
    case version
      when '1.8.7'
        puts "Vous devriez mettre Ruby à jour"
      when /^1\.9\d/
        puts "Cool, on est à jour !"
      else
        puts "Faut vraiment upgrader la ;-)"

!SLIDE small
# Gestion des exceptions

    @@@ ruby
    begin
      f = File.open('ﬁchier.txt')     #=> Le code à exécuter
      texte = f.readline
      puts "L'en-tête du ﬁchier est : #{texte}"
    rescue Errno::ENOENT => e        #=> Interception d'une erreur
      puts "Il n'y a pas de tel ﬁchier !"
    rescue NoMethodError => e        #=> Interception d'une erreur
      puts "Le ﬁchier n'a probablement pas pu être ouvert"
      return false
    rescue SyntaxError => e          #=> Interception d'une erreur
      puts "Une erreur du développeur ? (#{e.message})"
      raise e                        #=> Soulèvement d'une exception
    ensure                           #=> Code exécuté quoi qu'il arrive
      f.close if f.respond_to? :close
    end