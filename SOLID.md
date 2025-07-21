class Order
  attr_accessor :items 

  def initialize(items)
    @items = items
  end
end

class Print
  def print_order(items)
    @items.each do |item|
      puts "Item: #{item.name} - Price: #{item.price}"
    end
  end
end

class Calculate_total
  def calculate(items)
    total = 0
    @items.each do |item|
      total += item.price
    end
    total
  end
  def discont
    total = total * 0.1
  end    
end


class Email
  def send_confirmation(email)
    # Lógica para enviar un correo electrónico de confirmación
    puts "Email enviado a #{email}"
  end
end


class Item
  attr_accessor :name, :price

  def initialize(name, price)
    @name = name
    @price = price
  end
end
