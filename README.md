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
you can know when you browse and click f12 seeing the web code in the windowform,
it contains HTML5 CSS javaScript jQuery php and so on......,
but we can clean noise by python,at its simplest,pandas can help us get html label "table" contents
I use very easy sample code below:<br>
<code>
import pandas as pd<br></code>
<br><code>url="http://stockq.org/market/asia.php"</code>
<br><code>data = pd.read_html(url)</code>
<br><code>data[7:][0]</code>
<img src="https://github.com/Ming-Xuan/GalaxyMing/blob/master/%E7%B6%B2%E9%A0%81%E7%88%AC.JPG" >
you can see my implentation in my md and how I let it visualize.<br>
"https://github.com/Ming-Xuan/GalaxyMing/blob/master/%E7%88%AC%E8%9F%B2.md" <br>
My visualize result is below:
<img src="https://github.com/Ming-Xuan/GalaxyMing/blob/master/%E8%82%A1%E5%B8%82%E6%8C%87%E6%95%B8.png" >
 Last I wii show you how I do portfolio selection:<br>
Example
Portfolio Selection Optimization
Please arbitrarily pick “Five” assets (including riskless or risky assets) in any negotiable
securities market (Taiwan or any other country) in 2016-2019. If you would like to achieve a 7%
expected returns, what’s the allocated percentage of each asset in your portfolio? Given your
budget is 100%, use Markowitz’s Mean-Variance Model (1952, 1959) to solve the problem.
<br>
This Problem I use Markowitz's Mean-Variance Model to solve it.
This model use mean and variance to evaluate performance.
Assuming that portfolio P1 has a higher expected return and lower variance than another portfolio P2 (that is, E1>E2 and σ21<σ22), then we call P1 dominates P2.

We call P1 dominate P2 in minimum variance sense if σ1<σ2.
Comment:
1. The above strict inequality> can be replaced by a weaker inequality ≥.
2. The above three efficient investment portfolios (absolute efficient, efficient in variance sense, efficient in expected return sense) are generally called efficient, and no distinction is made. Incidentally, this type of efficient portfolio will fall on the so-called efficient frontier. Interested readers can refer to related books on general investment theory or asset allocation theory, and I won’t repeat them here.

You can see my Portfolio implementation in my makedown.
https://github.com/Ming-Xuan/GalaxyMing/blob/master/profitlio.md


<br><br><br>
In order to ensure profit, I chose the top five stocks with the highest net profit after tax in Taiwan for analysis. I expect that the profit of the investment can exceed the fixed deposit and the fund. If I will order about 10%, the stock is For high-risk investments, it is believed that the requirement for high profitability will not be unreasonable because the risk assumed is already very large.<br>
<img src="https://github.com/Ming-Xuan/GalaxyMing/blob/master/%E6%8A%95%E8%B3%87%E7%B5%84%E5%90%88.JPG" >
TSMC investment 15%
Hon Hai invests 85% to make a profit of more than 7%.



Reference:
https://ch-hsieh.blogspot.com/2016/12/markowitzs-mean-variance.html
https://www.stockfeel.com.tw/%E9%97%9C%E6%96%BC%E6%8A%95%E8%B3%87%E7%B5%84%E5%90%88%EF%BC%8C%E4%BD%A0%E9%9C%80%E8%A6%81%E7%9F%A5%E9%81%93%E7%9A%843%E4%BB%B6%E4%BA%8B/
https://zh.wikipedia.org/wiki/%E6%8A%95%E8%B3%87%E7%B5%84%E5%90%88

