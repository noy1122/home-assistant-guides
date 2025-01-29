# 🛒 Smart Shopping List in Home Assistant  
🚀 **Easily manage your shopping list with one-click product buttons in Lovelace!**  

This guide will walk you through creating a **smart shopping list** with **image-based product buttons**.  
Tapping a product **automatically adds it to the shopping list** in Home Assistant.  

---

## **🛠️ Requirements**  
✅ **`shopping_list` integration enabled**  
✅ **Lovelace YAML mode enabled**  
✅ **`custom:button-card` installed via HACS**  
✅ **Local images for products (`/local/` directory)**  

---

## **🔹 Step 1: Enable Shopping List Integration**  
📌 Ensure the **Shopping List** integration is enabled in `configuration.yaml`:  

```yaml
shopping_list:  
```

💡 **Restart Home Assistant after adding this!**  

---

## **🔹 Step 2: Add Product Buttons**  
Now, let's create **image-based product buttons** that allow you to add items to the shopping list with a single tap.

📌 **Add this to your Lovelace YAML:**  

```yaml 
type: grid  
title: "Shopping List"  
columns: 2  
square: false  
cards:  
  - type: custom:button-card  
    name: "Milk"  
    entity_picture: /local/milk.png  
    show_entity_picture: true  
    show_name: true  
    styles:  
      name:  
        - font-size: 14px  
        - font-weight: bold  
        - color: black  
    tap_action:  
      action: call-service  
      service: shopping_list.add_item  
      data:  
        name: Milk  

  - type: custom:button-card  
    name: "Bread"  
    entity_picture: /local/bread.png  
    show_entity_picture: true  
    show_name: true  
    styles:  
      name:  
        - font-size: 14px  
        - font-weight: bold  
        - color: black  
    tap_action:  
      action: call-service  
      service: shopping_list.add_item  
      data:  
        name: Bread  

  - type: custom:button-card  
    name: "Eggs"  
    entity_picture: /local/eggs.png  
    show_entity_picture: true  
    show_name: true  
    styles:  
      name:  
        - font-size: 14px  
        - font-weight: bold  
        - color: black  
    tap_action:  
      action: call-service  
      service: shopping_list.add_item  
      data:  
        name: Eggs  
```

📌 **How it works?**  
✅ **Each button displays a product image with a name below**  
✅ **Tapping it automatically adds the item to the shopping list**  
✅ **Images are stored locally in `/local/`**  
✅ **Text is styled in bold black font for clarity**  

---

## **🔹 Step 3: Display the Shopping List in Lovelace**  
To display the shopping list, add this card to Lovelace:  

```yaml  
type: shopping-list  
title: "My Shopping List"  
```

📌 **Newly added items will automatically appear at the top!**  

---

## **🔹 Step 4: Improve the UI Layout**  
To make the interface more user-friendly, we use a **vertical-stack** layout to place the buttons above the shopping list.  

```yaml 
type: vertical-stack  
cards:  
  - type: grid  
    title: "Quick Add Items"  
    columns: 2  
    square: false  
    cards:  
      - (Insert product buttons here)  

  - type: shopping-list  
    title: "Shopping List"  
```

📌 **Why use this layout?**  
✅ **The product buttons appear at the top**  
✅ **The shopping list is displayed below**  
✅ **You can quickly add and view items in one place**  

---

## **🔹 Step 5: Upload Local Images**  
To ensure images are displayed correctly, upload them manually to `/local/`.  

1️⃣ **Navigate to `/config/www/` in your Home Assistant directory**  
2️⃣ **Upload product images (e.g., `milk.png`, `bread.png`, `eggs.png`)**  
3️⃣ **Restart Home Assistant to refresh the images**  

💡 **Now, your buttons will automatically show product images and names!**  

---

## **🚀 Summary**  
✅ **Tap a product to add it to your shopping list**  
✅ **Uses local images for a clean UI**  
✅ **New items appear at the top of the list**  
✅ **Optimized layout with `grid` and `shopping-list`**  

📬 **Have questions or suggestions? Let us know in the comments!**  
📸 **Share your setup with screenshots!**  

---

