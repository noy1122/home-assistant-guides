# 🔊 **כרטיס מדיה חכם לאלקסה עם תמיכה ב-TTS ב-Home Assistant**  

כיצד **להגדיר כרטיס Lovelace מותאם אישית** שמשלב **אלכסה עם טקסט לדיבור (TTS)**, כך שתוכל לשלוח הודעות ישירות לרמקול האקו שלך.  

![Alexa Mini Media Player](images/alexa-mini-media-player.png)  

---

## 🛠️ **דרישות מקדימות**  
✅ **רמקול Alexa משולב עם `alexa_media_player`**  
✅ **התקנת `mini-media-player` דרך HACS**  
 

---

## 🔹 **שלב 1: התקנת ההרחבה `alexa_media_player`**  
כדי לשלוט ברמקולי Alexa מתוך Home Assistant, יש להתקין את `alexa_media_player` דרך HACS.  

📌 **כך תתקין את ההרחבה:**  
1️⃣ פתח **HACS** → עבור ל- **Integrations**  
2️⃣ חפש **Alexa Media Player**  
3️⃣ לחץ על **Download & Install**  
4️⃣ הפעל מחדש את Home Assistant  
5️⃣ עבור ל- **הגדרות → אינטגרציות**, הוסף את חשבון Amazon שלך **והתחבר**  

---

## 🔹 **שלב 2: התקנת `mini-media-player` עבור Lovelace**  
כדי להציג כרטיס מדיה חכם ב-Lovelace, יש להתקין את `mini-media-player` דרך HACS.  

📌 **כך תתקין את הכרטיס:**  
1️⃣ פתח **HACS** → עבור ל- **Frontend**  
2️⃣ חפש **mini-media-player**  
3️⃣ לחץ על **Download & Install**  
4️⃣ הפעל מחדש את Home Assistant  

---

## 🔹 **שלב 3: יצירת כרטיס Alexa Media Player ב-Lovelace**  
לאחר שההרחבות מותקנות, הוסף את ה-YAML הבא **ללוח הבקרה של Lovelace** כדי להציג את הכרטיס של Alexa.  

📌 **הוסף את הקוד הבא ל-Lovelace שלך:**  

```yaml
type: custom:mini-media-player
entity: media_player.noy_s_2nd_echo_dot_2
artwork: full-cover
icon: mdi:amazon
tts:
  platform: alexa
  entity_id: media_player.noy_s_2nd_echo_dot_2
```

---

## 🔹 **שלב 4: הבנת ההגדרות של הכרטיס**  

### 📌 מה הכרטיס הזה מאפשר?  
✅ **הצגת הסטטוס הנוכחי של Alexa כולל עטיפת אלבום אם מתנגנת מוזיקה**  
✅ **כפתורי שליטה בעוצמת הקול והפעלה/עצירה**  
✅ **אפשרות לשלוח טקסט לדיבור ישירות לרמקול**  

### 📌 מה צריך לשנות?  
➡️ עדכן את **`entity: media_player.noy_s_2nd_echo_dot_2`** כך שיתאים לשם של הרמקול שלך.  
➡️ ודא ש-**`platform: alexa`** מוגדר נכון עבור תמיכה ב-TTS.  
➡️ ניתן לשנות את **האייקון או הצגת העטיפה** לפי העדפה אישית.  

---

## 🔹 **שלב 5: שליחת הודעת TTS לרמקול Alexa**  
באמצעות הכרטיס הזה, ניתן להקליד טקסט, ו-Alexa תקריא את ההודעה בקול.  

📌 **כיצד להשתמש?**  
1️⃣ פתח את לוח הבקרה של Lovelace  
2️⃣ לחץ על שדה **הכנסת טקסט ב-TTS**  
3️⃣ הקלד הודעה כלשהי (למשל: "ארוחת ערב מוכנה!")  
4️⃣ Alexa תשמיע את ההודעה בקול  

---

## 🚀 **סיכום**  
✅ **חיברנו את Alexa ל-Home Assistant באמצעות `alexa_media_player`**  
✅ **התקנו את `mini-media-player` ליצירת ממשק מתקדם**  
✅ **יצרנו כרטיס Lovelace עם תמיכה ב-TTS**  
✅ **כעת ניתן לשלוח הודעות קוליות לרמקול ישירות מתוך Home Assistant!**  

---

## 📬 **שאלות או עזרה?**  
אם נתקלת בבעיה או רוצה לשפר את ההגדרות, ניתן לפתוח **Issue** או לשלוח **Pull Request**! 🚀  

🔗 **עקוב אחרי מדריכים נוספים ל-Home Assistant!**  
