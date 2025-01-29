# 🛒 רשימת קניות חכמה ב-Home Assistant  
🚀 **הוספת מוצרים לרשימת הקניות בלחיצה אחת באמצעות כפתורים עם תמונות ושמות מוצרים!**  

מדריך זה ידריך אותך כיצד ליצור **רשימת קניות חכמה ב-Home Assistant** עם **כפתורי מוצרים מותאמים אישית**, כולל **תמונות מקומיות**.  
כל לחיצה על מוצר **תוסיף אותו ישירות לרשימת הקניות** ב-Home Assistant.  

---

## **🛠️ דרישות מקדימות**  
✅ **הפעלת רכיב `shopping_list` ב-Home Assistant**  
✅ **התקנת `custom:button-card` דרך HACS**  
✅ **העלאת תמונות מוצרים לתיקיית `/local/`**  

---

## **🔹 שלב 1: הפעלת רשימת הקניות (`shopping_list`)**  
📌 ודא שרכיב רשימת הקניות **פעיל** ב-`configuration.yaml`:  

```yaml  
shopping_list:  
```  

💡 **לאחר ההוספה, יש לבצע ריסטארט ל-Home Assistant!**  

---

## **🔹 שלב 2: יצירת כפתורים להוספת מוצרים**  
כעת ניצור **כפתורים עם תמונות ושמות** שיאפשרו לך להוסיף מוצרים לרשימת הקניות בלחיצה אחת.

📌 **הוסף את הקוד הבא ל-Lovelace YAML:**  

```yaml  
type: grid  
title: "רשימת קניות"  
columns: 2  
square: false  
cards:  
  - type: custom:button-card  
    name: "חלב"  
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
        name: חלב  

  - type: custom:button-card  
    name: "לחם"  
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
        name: לחם  

  - type: custom:button-card  
    name: "ביצים"  
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
        name: ביצים  
```  

📌 **מה הקוד עושה?**  
✅ **כל כפתור מציג תמונה של המוצר עם שם מתחת**  
✅ **בלחיצה, המוצר נוסף לרשימת הקניות אוטומטית**  
✅ **התמונות מאוחסנות מקומית בתיקיית `/local/`**  
✅ **השמות מוצגים בגופן מודגש בצבע שחור**  

---

## **🔹 שלב 3: הצגת רשימת הקניות בלוח הבקרה**  
כדי להציג את רשימת הקניות בצורה ברורה, הוסף את הכרטיס הבא ל-Lovelace:  

```yaml  
type: shopping-list  
title: "רשימת הקניות שלי"  
```  

📌 **כל מוצר שנוסף יופיע באופן אוטומטי בראש הרשימה!**  

---

## **🔹 שלב 4: שיפור עיצוב הממשק**  
כדי לארגן את הממשק בצורה נוחה, נשתמש ב`vertical-stack` כדי **להציג את הכפתורים מעל הרשימה**:  

```yaml  
type: vertical-stack  
cards:  
  - type: grid  
    title: "הוספת מוצרים בלחיצה"  
    columns: 2  
    square: false  
    cards:  
      - (הכפתורים שהוספת קודם)  

  - type: shopping-list  
    title: "רשימת הקניות"  
```  

📌 **מה היתרונות של עיצוב זה?**  
✅ **כפתורי ההוספה מופיעים בראש הדף**  
✅ **הרשימה מוצגת מתחת לכפתורים**  
✅ **ניתן להוסיף מוצרים ולראות אותם מיד ברשימה**  

---

## **🔹 שלב 5: העלאת תמונות מקומיות**  
כדי שהתמונות יוצגו בצורה תקינה, יש **להעלות אותן ידנית** לתיקייה `/local/`.  

1️⃣ **גש לתיקיית `/config/www/` ב-Home Assistant**  
2️⃣ **העלה את התמונות (למשל: `milk.png`, `bread.png`, `eggs.png`)**  
3️⃣ **בצע ריסטארט ל-Home Assistant כדי לטעון את התמונות**  

💡 **לאחר מכן, הכפתורים יציגו את התמונות והשמות באופן אוטומטי!**  

---

## **🚀 סיכום**
✅ **לחיצה על כפתור מוצר מוסיפה אותו לרשימת הקניות**  
✅ **כפתורים מעוצבים עם תמונות מקומיות ושמות מתחת**  
✅ **המוצרים החדשים מופיעים בראש הרשימה**  
✅ **שימוש בפריסה נוחה עם `grid` ו-`shopping-list`**  

📬 **יש שאלות או שיפורים? ספרו בתגובות!**  
📸 **שתפו צילום מסך של רשימת הקניות שלכם!**  

---

### **📌 שלב 3: עדכון ה-README הראשי**
ב-`README.md` הראשי, הוסף הפניה לגרסה בעברית:  
```md
## 📌 Available Guides  
1. **[Smart Shopping List](shopping-list/README.md)** – Manage your shopping list with product buttons and images.  
   - 🇮🇱 [מדריך בעברית](shopping-list/he/README.md)  
