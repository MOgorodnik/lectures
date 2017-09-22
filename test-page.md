# CSS селекторы

---

1. Универсальный  
   &gt;&gt;&gt; - **\***  
   [Пример.](https://codepen.io/MOgorodnik/pen/xXOeJM)

2. Селекторы идентификатора и класса \(id, class\)  
   [**\#X and .X**](https://codepen.io/MOgorodnik/pen/YrGxvo)

3. Селектор потомков  
   [**X Y**](https://codepen.io/MOgorodnik/pen/BwLdEQ)

4. Селектор псевдоклассов  
   [**X:visited и X:link**](https://codepen.io/MOgorodnik/pen/BwLdXp), **X:checked, X\(:first-child / :first-of-type / :nth-child / :target ect.\), input:valid/invalid/required.**

5. Смежный и сестринский селекторы  
   [**X + Y, X~Y**](https://codepen.io/MOgorodnik/pen/ZXpXOq)** **

6. Дочерний селектор  
   [**X &gt; Y**](https://codepen.io/MOgorodnik/pen/XejegQ)

7. Селекторы атрибутов  
   **X\[href="foo"\] **- строгое соответствие**  
   X\[href\*="somesing"\] **-  искомое значение может находиться в любой части атрибута  
   **X\[href^="http"\] **- указываем начальное значение атрибута**  
   X\[href$=".jpg"\] **- указываем конец значения атрибута  
   **X\[data-\*="foo"\] **- используя пользовательские атрибуты  
   **X\[foo~="bar"\] **-  Знак _~_ \(тильда\) позволяет нам выбирать атрибуты со значениями, разделенными пробелами

8. Селекторы псевдоэлементов  
   **X:before, X:after, ::first-letter, ::first-line, ::selection**

9. "Селектор отрицания"  
   **X:not\(selector\)**



