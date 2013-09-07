Rails Coding Guidelines
=======================

Everyone has their own preferences to coding style. Here are mine. This may be partially influenced by [this style guide](https://github.com/bbatsov/rails-style-guide).

ActiveRecord Models
-------------------

````ruby
class Model < ActiveRecord::Base
  # all mixins
  extend Something
  include Something


  # other stuff (often mixins in disguise)
  acts_as_taggable
  paginates
  
  
  # constants
  DAY_OF_WEEK = %w(sun mon tue wed thu fri sat)


  # associations
  belongs_to :onceler
  has_many :thneeds


  # delegates
  delegate :ethics, :to => :onceler
  
  
  # validations
  validates :email, presence: true


  # scopes (beginning with the default scope if it exists)
  default_scope { order 'name' }
  scope :red, -> { where(:color => 'red') }
  
   
  # attr macros
  attr_accessor :inst_var
  
   
  # callback macros
  after_save :write_history


  # class methods (using self, not class name)
  def self.method
  end


  # instance methods
  def instance_method
  end
  
  
  # protected methods
  protected
  def foo
  end
  
  
  # private methods
  private
  def bar
  end
end
````
