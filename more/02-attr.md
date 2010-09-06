!SLIDE bullets incremental
# attr_*

* attr_accessor
* attr_reader
* attr_writer

!SLIDE small
# attr_accessor

    @@@ ruby
    class Conference
      attr_accessor  :name
      
    end
    
    c = Conference.new
    c.name   #=> nil
    c.name = 'JDLL'
    c.name   #=> 'JDLL'

!SLIDE small
# attr_reader

    @@@ ruby
    class Conference
      attr_reader  :name
      
      def initialize(name)
        @name = name
      end
    end
    
    c = Conference.new('JDLL')
    c.name   #=> JDLL
    c.name = 'JDLL' #=> NoMethodError

!SLIDE small
# attr_writer

    @@@ ruby
    class Conference
      attr_writer   :name
      
      def to_s
        "Nous sommes à #{@name}"
      end
    end
    
    c = Conference.new
    c.name = "JDLL"
    c.name #=> NoMethodError
    c.to_s #=> "Nous sommes à JDLL"