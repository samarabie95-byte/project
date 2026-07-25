# project
This is tclass User:
    def __init__(self, name, email):
        self.name = name
        self.email = email
        self.is_active = True

    def deactivate(self):
        self.is_active = False

    def activate(self):
        self.is_active = True


class Product:
    shop_name = "Shop Wave"

    def __init__(self, name, price):
        self.name = name
        self.price = price
        self.in_stock = True

    def apply_discount(self, percent):
        self.price = self.price - (self.price * percent / 100)

    def describe(self):
        status = "In Stock" if self.in_stock else "Out of Stock"
        return f"[{Product.shop_name}] {self.name}: ${self.price:.2f} ({status})"


user1 = User("Samaa", "samaa@example.com")
user2 = User("Omar", "omar@example.com")
user3 = User("Nour", "nour@example.com")

user1.is_active = False

prod1 = Product("Laptop", 1200.0)
prod2 = Product("Smartphone", 800.0)
prod3 = Product("Headphones", 150.0)
prod4 = Product("Smartwatch", 250.0)

prod4.in_stock = False

for product in [prod1, prod2, prod3, prod4]:
    print(product.describe())

print(user1.is_active)
user1.deactivate()
print(user1.is_active)

print(prod3.price)
prod3.apply_discount(15)
print(prod3.price)est 
