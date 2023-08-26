class Product:
    def __init__(self, name, price):
        self.name = name
        self.price = price

class ShoppingCart:
    def __init__(self):
        self.items = []

    def add_item(self, product):
        self.items.append(product)
        print(f"{product.name} sepete eklendi.")

    def view_cart(self):
        if not self.items:
            print("Sepetiniz boş.")
        else:
            print("Sepet İçeriği:")
            for item in self.items:
                print(f"{item.name}: {item.price} TL")
    
    def calculate_total(self):
        total = sum(item.price for item in self.items)
        print(f"Toplam Fiyat: {total} TL")

def main():
    cart = ShoppingCart()

    while True:
        print("\nNe yapmak istersiniz?")
        print("1. Ürün Ekle")
        print("2. Sepeti Görüntüle")
        print("3. Toplam Fiyatı Hesapla")
        print("4. Çıkış")
        choice = input("Seçiminizi yapın: ")

        if choice == "1":
            product_name = input("Ürün adını girin: ")
            product_price = float(input("Ürün fiyatını girin: "))
            product = Product(product_name, product_price)
            cart.add_item(product)
        elif choice == "2":
            cart.view_cart()
        elif choice == "3":
            cart.calculate_total()
        elif choice == "4":
            print("Programdan çıkılıyor...")
            break
        else:
            print("Geçersiz seçim. Lütfen tekrar deneyin.")

if __name__ == "__main__":
    main()
