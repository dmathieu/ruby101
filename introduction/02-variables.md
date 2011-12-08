!SLIDE small
# Identificateurs

    @@@ ruby
    message = "Bonjour tout le monde" #=> Variable locale

    $message = "Bonjour tout le monde"#=> Variable globale
    $LOAD_PATH

    Message = "Bonjour tout le monde" #=> Constante
    MA_CONSTANTE = "Bonjour tout le monde"

!SLIDE small
# "Littéraux"

    @@@ ruby
    1      #=> Nombres
    1.3

    "Bonjour tout le monde" #=> Chaine de caractères

    "Salut #{nom}" #=> Interpolation de variable

    [1, 2, 3, 'hello'] #=> Liste / Tableau

    { :présentation => 'Ruby 101',
      :orateur => 'Damien'} #=> Tableau Associatif

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
