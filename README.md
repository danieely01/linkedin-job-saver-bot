# LinkedIn Job Saver Bot - Selenium Automation

Egy Python alapú automatizációs bot, amely a Selenium WebDriver segítségével bejelentkezik a LinkedInre, rákeres egy megadott pozícióra (pl. Junior Python Developer), végiggörgeti a találatokat, és automatikusan elmenti a releváns álláshirdetéseket.

## 🚀 Főbb funkciók és működés
* **Objektumorientált Tervezés (OOP):** A bot teljes logikája egy jól strukturált `LinkedIn` osztályba van szervezve, könnyen példányosítható és bővíthető.
* **Böngésző-automatizálás (Selenium):** A DOM elemek dinamikus azonosítása és interakciók (kattintások, szövegbevitel) XPath, CSS Selector és ID alapján.
* **Dinamikus görgetés (Lazy Loading kezelése):** Mivel a LinkedIn dinamikusan tölti be a tartalmakat, a bot JavaScript injektálással (`execute_script`) szimulálja a felhasználói görgetést a hirdetések betöltéséhez.
* **Kivételkezelés:** A `NoSuchElementException` beépített lekezelése garantálja, hogy a szkript ne fagyjon le, ha egy adott DOM elem ideiglenesen nem található.
* **Biztonság:** Az érzékeny bejelentkezési adatok (email, jelszó) környezeti változókból (`os.environ`) töltődnek be.

## 🛠 Alkalmazott Technológiák
* **Nyelv:** Python 3
* **Keretrendszer:** Selenium WebDriver
* **Egyéb modulok:** `time`, `os`

## 💻 Használat és Futtatás

A program futtatásához a Selenium csomag telepítése, valamint a megfelelő WebDriver (pl. ChromeDriver) megléte szükséges a rendszer `PATH` változójában.

**1. Függőségek telepítése:**
Futtasd az alábbi parancsot a terminálban:

    pip install selenium

**2. Környezeti változók beállítása:**
A futtatás előtt be kell állítani az operációs rendszerben a hitelesítő adatokat:
* `MAIL`: A LinkedIn profilhoz tartozó email cím.
* `PASSWORD`: A LinkedIn jelszó.
* `PATH`: A letöltött WebDriver (pl. `chromedriver.exe`) elérési útvonala.

**3. Testreszabás:**
A `__init__` metódusban található `self.URL` változó átírásával bármilyen konkrét LinkedIn keresési URL megadható (szűrve lokációra, kulcsszavakra, stb.).
