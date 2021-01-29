### Takeaway challenge

#### Running the program in IRB
- Require Menu.rb / BillCalculator.rb / Print.rb
- Create an instance of Menu
- Methods to use on your instance of Menu:
  - .print_all - prints all dishes
  - .select(:dish1=>quantity, :dish2=>quantity) - This is where you add your order.  It must be a hash format and grouped by dish (i.e. :Hamburger=>5 not :Hamburger=>1, :Hamburger=>1 etc)
  - .print_my_dishes - shows dishes you have selected)
  - .my_total(integer) - Enter total.  If total is correct then the order is placed

#### Code Example
```
λ irb
irb(main):001:0> require './lib/Menu.rb'
=> true
irb(main):002:0> require './lib/Print.rb'
=> true
irb(main):003:0> require './lib/BillCalculator.rb'
=> true
irb(main):004:0> my_meal = Menu.new
=> #<Menu:0x0000000006eb38a8 @dishes=nil, @printer=#<Print:0x0000000006eb3880>, @bill=#<BillCalculator:0x0000000006eb3858 @meal_options={:Hamburger=>5, :Pizza=>6, ...
irb(main):005:0> my_meal.print_all
Dish: Hamburger, Price: £5
Dish: Pizza, Price: £6
Dish: Pasta, Price: £4
Dish: Fish_and_chips, Price: £5
Dish: Salad, Price: £3
Dish: Lamb_Shank, Price: £7
=> {:Hamburger=>5, :Pizza=>6, :Pasta=>4, :Fish_and_chips=>5, :Salad=>3, :Lamb_Shank=>7}
irb(main):006:0> my_meal.select(:Hamburger=>3, :Pasta=>2)
=> {:Hamburger=>3, :Pasta=>2}
irb(main):007:0> my_meal.print_my_dishes
=> ["Hamburger (£5) x 3 = £15", "Pasta (£4) x 2 = £8"]
irb(main):008:0> my_meal.my_total(23)
=> "Amount given is correct.  Food ordered"
```

#### Edge Cases
- Dish given must be Symbol e.g. {Hamburger=>3} or for multiple orders {Hamburger=>3, Pizza=>5}
- Quantity must be an integer not a string e.g. {Hamburger=>5} not {Hamburger=>"5"}
- Order must be Given in a hash {Hamburger=>5} not an array or string.

#### Future features
- Improve ease of inputting order

#### Coverage
COVERAGE: 100.00% -- 109/109 lines in 6 files

#### Tech used
- Ruby
- Rspec
- Bundle

#### Original challenge
- [Link to repo](https://github.com/makersacademy/takeaway-challenge)
