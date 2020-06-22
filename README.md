# GalaxyMing
# Portfolio
**A portfolio is a grouping of financial assets such as stocks, bonds, commodities, currencies and cash equivalents, as well as their fund counterparts, including mutual, exchange-traded and closed funds**
 
 
Two Objects(You should consider your risk tolerance and expected value)

<ol>
<li>Max Expected returns</li>
<li>Min Risk</li>
</ol>
<b>"Don,t Put Your Egg In One Basket"</b><br>
Portfolio of two assets to give an example
<table>
 <tr>
  <th></th><th>Expected retuen</th><th>Risk </th> <th>Weight</th>
 </tr>
 <tr>
  <th>Asset1</th><th>E(r1)</th><th>σ1 </th> <th>w</th>
 </tr>
 <tr>
  <th>Asset2</th><th>E(r2)</th><th>σ2 </th> <th>1-w</th>
 </tr>
</table>
 <br>
<img src="https://github.com/Ming-Xuan/GalaxyMing/blob/master/%E5%85%AC%E5%BC%8F%E6%A8%99%E6%BA%96.gif" >
<img src="https://github.com/Ming-Xuan/GalaxyMing/blob/master/%E5%85%AC%E5%BC%8F1.png?raw=true" >
<img src="https://github.com/Ming-Xuan/GalaxyMing/blob/master/%E5%85%AC%E5%BC%8F2.png" >



<img src="https://github.com/Ming-Xuan/GalaxyMing/blob/master/%E5%85%AC%E5%BC%8F3.png" >

<table>
 <tr>
  <th></th><th>Expected retuen</th><th>Risk </th> 
 </tr>
 <tr>
  <th>Asset1</th><th>0.14</th><th>0.2 </th> 
 </tr>
 <tr>
  <th>Asset2</th><th>0.2</th><th>0.08</th> 
 </tr>
 <tr>
  <th>Correlation Coefficient</th>
  <th colspan="2">0.6</th>
 </tr>
</table>
<img src="https://github.com/Ming-Xuan/GalaxyMing/blob/master/%E6%8E%A8%E5%80%92.JPG" >
<b>When you invest your assets,must consider three issue.</b>
<ol>
<li>Risk Tolerance</li>
<li>
Asset price fluctuations</li>
 <li>
Characteristics of major markets</li>
</ol>
<img src="https://github.com/Ming-Xuan/GalaxyMing/blob/master/risk.png" >
When you Browse your favorite stock,you can use python help you get important information<br>
you can know when you browse and click f12,you can see the web code in the windowform,
it contains HTML5 CSS javaScript jQuery php and so on......,
but we can clean noise by python,at its simplest,pandas can help us get html label (<table></table>) contents
I use very easy sample code below:<br>
<code>
import pandas as pd<br></code>
<br><code>url="http://stockq.org/market/asia.php"</code>
<br><code>data = pd.read_html(url)</code>
<br><code>data[7:][0]</code>
<img src="https://github.com/Ming-Xuan/GalaxyMing/blob/master/%E7%B6%B2%E9%A0%81%E7%88%AC.JPG" >
"https://github.com/Ming-Xuan/GalaxyMing/blob/master/%E7%88%AC%E8%9F%B2.md" 

