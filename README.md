# Fruitmarket-shop-GUI
```
import tkinter as tk
from tkinter import messagebox
products={"strawberry":2.00,
 "mango":3.00,
 "banana":1.50,
 "raspberry":0.50,
}
carts=[]
#add item to the cart
def add_cart(item, price):
    carts.append(price)
    Fruitmarket.insert(tk.END,f"{item}-${price}")
    Pricetotal()
#Update total price
def Pricetotal():
    total = sum(carts)
    total_label.config(text=f"Total: ${total}")


#Checkout function
def checkout():
    if not carts:
        messagebox.showwarning("Cart Empty", "Your cart is empty!")
    else:
        messagebox.showinfo("Checkout", f"Purchase successful!\nTotal paid: ${sum(carts)}")
        carts.clear()
        Fruitmarket.delete(0,tk.END)
        total()
        root = tk.Tk()
        root.title("Fruitmarket")
        root.geometry("500x400")
        root.resizable(False,False)
        title = tk.Label(root, text="Python Store",font=("Arial, 20, "bold"))
        title.pack(pady=10)
        total_label = tk.Label(root,text="Total: $0", font=("Arial", 14, "bold"))
        total_label.pack(pady=5)
        root.mainloop()
```
