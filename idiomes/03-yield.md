!SLIDE small
# yield

    @@@ ruby
    class Conference
      attr_accessor   :name, :duration
      
      def initialize
        yield(self) if block_given?
      end
    end
    
    c = Conference.new do |conf|
      conf.name = 'JDLL'
      conf.duration = 40
    end

!SLIDE small
# yield

    @@@ ruby
    class Conference
      attr_accessor :name, :duration
      
      def initialize(&block)
        block.call(self) unless block.nil?
      end
    end
    
    c = Conference.new do |conf|
      conf.name = 'JDLL'
      conf.duration = 40
    end