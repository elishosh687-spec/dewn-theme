# 🎨 תהליך עיצוב אתר עם Cursor AI - מדריך שלב אחר שלב

## ⚠️ חשוב: הכל חייב להיות ב-Liquid!

**כל הקוד שתכתוב חייב להיות ב-Shopify Liquid בלבד:**
- ✅ **Sections** - קבצי `.liquid` בתיקיית `sections/`
- ✅ **Blocks** - קבצי `.liquid` בתיקיית `blocks/`
- ✅ **Snippets** - קבצי `.liquid` בתיקיית `snippets/`
- ✅ **CSS** - בתוך `{% stylesheet %}` או `{% style %}` tags
- ✅ **JavaScript** - בתוך `{% javascript %}` tags

**לא להשתמש ב:**
- ❌ React, Vue, או frameworks אחרים
- ❌ TypeScript או שפות אחרות
- ❌ CSS frameworks חיצוניים (רק CSS טהור)
- ❌ Build tools מורכבים

**למה?** כי הכל עולה ל-Shopify (Dawn theme), שמבין רק Liquid!

**הזרימה:**
1. `design.json` - מדריך עיצובי בלבד (לא קוד!)
2. → Liquid Sections/Blocks/Snippets - הקוד האמיתי
3. → Shopify Theme - התוצאה הסופית

---

## שלב 1: הנדסה לאחור של העיצוב (The Design Analysis)

### מטרה: ליצור "DNA עיצובי" מדויק במקום תיאורים מעורפלים

### תהליך:

1. **מציאת מקור השראה**
   - מצא אתר או אפליקציה שנראים בדיוק כמו שאתה רוצה
   - דוגמאות: Apple, מותגי תינוקות יוקרתיים, אתרים מובילים בתחום
   - צלם מסך של אלמנטים מרכזיים (כפתורים, כרטיסי מוצר, כותרות, טפסים)

2. **יצירת ה-DNA העיצובי (design.json)**
   - תן ל-Cursor את צילום המסך
   - **השתמש בפרומפט הבא:**
   
   ```
   Deeply analyse the design of the attached screenshot to create a design.json file in this Shopify Liquid theme project that describes the style and design of every UI component needed in a design system at a high level like a creative director. Capture high level guidelines for structure, spacing, fonts, colours, design style and design principles so I can use this file as the design guidelines for my Shopify theme. The goal with this file is to instruct AI to be able to replicate this look easily when building Liquid sections, snippets, and templates.
   ```
   
   - שמור את הקובץ בשם: `design.json`

3. **מה לחלץ ל-JSON:**
   ```json
   {
     "colors": {
       "primary": "#hexcode",
       "secondary": "#hexcode",
       "background": "#hexcode",
       "text": "#hexcode"
     },
     "typography": {
       "fontFamily": "...",
       "fontSizes": {...},
       "fontWeights": {...},
       "lineHeights": {...}
     },
     "spacing": {
       "base": "8px",
       "small": "4px",
       "medium": "16px",
       "large": "24px",
       "xlarge": "32px"
     },
     "borders": {
       "radius": "12px",
       "width": "1px",
       "style": "solid"
     },
     "shadows": {...},
     "transitions": {...}
   }
   ```

### למה JSON?
- AI זוכר ערכים מספריים ב-JSON טוב יותר מתיאורים בטקסט
- קל לעדכן ולשמור עקביות
- ניתן לעדכן פעם אחת ולהשתמש בכל האתר

---

## שלב 2: בניית "דף הראיות" (The Component Showcase)

### מטרה: לבדוק שה-AI הבין את ה"שפה" העיצובית לפני בניית האתר המלא

### תהליך:

1. **יצירת דף מעבדה**
   - בקש מ-Cursor: "צור לי Section ב-Liquid שמכיל את כל הרכיבים הבסיסיים לפי ה-design.json"
   - רכיבים לכלול:
     - כפתור (Button)
     - שדה טקסט (Input)
     - כותרת (Heading)
     - כרטיס מוצר (Product Card)
     - קישור (Link)
     - רשימה (List)

2. **הביקורת והתיקון**
   - בדוק אם הכל נראה נכון
   - **חשוב:** אם משהו לא נראה נכון, תקן את ה-`design.json` ולא את הקוד!
   - למה? כך התיקון יהיה קבוע לכל האתר
   - חזור על התהליך עד שהכל נראה מושלם

### דוגמת פרומפט:
```
צור לי Section בשם "component-showcase.liquid" שמכיל את כל הרכיבים הבסיסיים 
לפי ה-design.json: כפתור, שדה טקסט, כותרת H1-H3, כרטיס מוצר, קישור, ורשימה.
השתמש בקובץ design.json כנקודת ייחוס לכל העיצוב.
חשוב: כתוב הכל ב-Liquid בלבד - Sections חייבות להיות קבצי .liquid עם Liquid syntax!
```

---

## שלב 3: הרכבת האתר (The Production Phase)

### מטרה: לבנות את החלקים האמיתיים של האתר עם עקביות מלאה

### תהליך:

1. **עבודה עם הקשר (Context)**
   - בכל פעם שאתה מבקש Section חדש, ציין ל-Cursor להשתמש ב-`design.json`
   - דוגמה: "צור Icon Bar Section לפי ה-design.json"

2. **הפרומפט הבסיסי לכל Section חדש:**
   ```
   צור לי Section בשם [שם ה-section] שמכיל [תיאור הפונקציונליות].
   השתמש בקובץ design.json כנקודת ייחוס לכל העיצוב, הצבעים, המרווחים והטיפוגרפיה.
   חשוב: כתוב הכל ב-Shopify Liquid בלבד - קובץ .liquid עם Liquid syntax, לא React או Vue!
   ```

3. **פרומפט מתקדם לבניית Sections/דפים:**
   ```
   Let's create a [תיאור ה-Section/הדף] following the design style outlined in @design.json. 
   Build this as a Shopify Liquid Section file (.liquid) in the sections/ folder. 
   IMPORTANT: Write ONLY Liquid code - no React, Vue, or other frameworks!
   
   Include:
   - Proper {% stylesheet %} or {% style %} blocks for CSS using design.json values
   - {% schema %} block with appropriate settings
   - Use section.id for unique CSS classes
   - Follow Shopify Liquid best practices and syntax
   - Ensure all colors, typography, spacing, borders, and shadows match design.json exactly
   - Make it responsive using design.json breakpoints
   - All code must be valid Shopify Liquid that will work on Dawn theme
   ```

3. **התוצאה:**
   - כל רכיב חדש ייראה כאילו הוא חלק מאותו מותג
   - אותם רווחים, צבעים, וסגנונות
   - ללא מאמץ ידני של העתקה-הדבקה

---

## 📋 תבנית עבודה מהירה

### כשאתה מתחיל פרויקט חדש:

1. ✅ מצא השראה וצלם מסכים
2. ✅ צור `design.json` עם כל המאפיינים
3. ✅ צור Component Showcase Section
4. ✅ בדוק ותקן את ה-`design.json` אם צריך
5. ✅ התחל לבנות Sections אמיתיים

### כשאתה יוצר Section חדש:

```
צור לי Section בשם [שם] שמכיל [תיאור].
השתמש ב-design.json כנקודת ייחוס.
חשוב: כתוב הכל ב-Liquid בלבד - קובץ .liquid עם Liquid syntax!
```

---

## 💡 טיפים חשובים

- **תמיד תקן את ה-JSON, לא את הקוד** - כך התיקון יהיה קבוע
- **שמור את ה-design.json בתיקיית הפרויקט** - כך Cursor יוכל לגשת אליו בקלות
- **עדכן את ה-design.json כשאתה מוצא משהו חדש** - זה ה-DNA של האתר שלך
- **השתמש ב-Component Showcase לבדיקות** - זה חוסך זמן בבנייה
- **⚠️ כל הקוד חייב להיות Liquid בלבד!** - Shopify לא מבין React, Vue, או שפות אחרות
- **השתמש ב-{% stylesheet %} ו-{% javascript %} tags** - לא קבצים חיצוניים
- **עקוב אחרי Liquid syntax** - `{{ }}` ל-output, `{% %}` ל-logic
- **Sections = קבצי .liquid** - לא .jsx, .vue, או קבצים אחרים

## 📝 פרומפטים מומלצים מותאמים ל-Shopify

### פרומפט לחילוץ design.json:
```
Deeply analyse the design of the attached screenshot to create a design.json file in this Shopify Liquid theme project that describes the style and design of every UI component needed in a design system at a high level like a creative director. Capture high level guidelines for structure, spacing, fonts, colours, design style and design principles so I can use this file as the design guidelines for my Shopify theme. The goal with this file is to instruct AI to be able to replicate this look easily when building Liquid sections, snippets, and templates.
```

### פרומפט לבניית Shopify Liquid Section:
```
Let's create a [תיאור ה-Section] following the design style outlined in @design.json. 
Build this as a Shopify Liquid Section file (.liquid) in the sections/ folder. 
IMPORTANT: Write ONLY Liquid code - no React, Vue, or other frameworks!

Include:
- Proper {% stylesheet %} or {% style %} blocks for CSS using design.json values
- {% schema %} block with appropriate settings
- Use section.id for unique CSS classes
- Follow Shopify Liquid best practices and syntax
- Ensure all colors, typography, spacing, borders, and shadows match design.json exactly
- Make it responsive using design.json breakpoints
- All code must be valid Shopify Liquid that will work on Dawn theme
```

### פרומפט לבניית Shopify Block:
```
Create a Shopify Liquid block file (.liquid) in the blocks/ folder named [שם].liquid 
that [תיאור הפונקציונליות]. 
IMPORTANT: Write ONLY Liquid code - this is for Shopify, not React/Vue!

Follow the design.json for all styling values. 
Include:
- {% doc %} tag at the top
- {% stylesheet %} or {% style %} blocks for CSS
- {% schema %} block with settings
- {{ block.shopify_attributes }} in the HTML
- Ensure it's reusable and follows Shopify Liquid conventions
```

### פרומפט לבניית Shopify Snippet:
```
Create a Shopify Liquid snippet in the snippets/ folder named [שם].liquid 
that [תיאור הפונקציונליות]. 
IMPORTANT: Write ONLY Liquid code - snippets are pure Liquid, no frameworks!

Follow the design.json for all styling values. 
Include:
- {% doc %} tag at the top with @param documentation
- {% stylesheet %} or {% style %} blocks if needed
- Use {% render %} to accept parameters
- Ensure it's reusable and follows Shopify Liquid conventions
```

### פרומפט ליצירת design-system.json מתקדם:
```
In this Shopify theme project, update the design.json file to include comprehensive styling guidelines for all components (sections, snippets, templates). Outline exact styling specifications for colors, typography, spacing, borders, shadows, transitions, and breakpoints. Include component-specific guidelines for buttons, product cards, navigation, headers, footers, and other Shopify theme elements. The goal is to create a comprehensive guide for AI to follow when building new Liquid sections, snippets, and templates in this Shopify theme.
```

---

## 🎯 סיכום

במקום לתאר במילים "אני רוצה אתר יפה", אנחנו:
1. **מחלצים** את ה-DNA העיצובי ל-JSON (מדריך עיצובי בלבד)
2. **בודקים** שהכל נכון ב-Component Showcase (ב-Liquid!)
3. **בונים** את האתר עם עקביות מלאה (Sections/Blocks/Snippets ב-Liquid)

**התוצאה:** אתר שנראה מקצועי ועקבי, ללא מאמץ ידני!

**זכור:** הכל חייב להיות ב-Shopify Liquid - זה השפה היחידה ש-Shopify מבין!

