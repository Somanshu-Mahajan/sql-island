This repository contains my step-by-step solutions for the [SQL Island](https://www.sql-island.com/) interactive SQL learning game.

This repository includes:
- 🧠 Conversation prompts from the game
- ❓ The questions/challenges
- 🧾 My solutions (SQL queries)

Schema:
- VILLAGE (villageid, name, chief)
- INHABITANT (personid, name, villageid, gender, job, gold, state)
- ITEM (item, owner)

#### 💬 You: Oh dear, what happened? It seems that I am the only survivor of the air crash. Wow, there are some villages on this island.
> SELECT * FROM village<br>
> Output:
<table border="1" cellpadding="8" cellspacing="0" style="border-collapse: collapse; text-align: left;">
  <thead>
    <tr style="background-color: #f2f2f2;">
      <th>villageid</th>
      <th>name</th>
      <th>chief</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>1</td>
      <td>Monkeycity</td>
      <td>1</td>
    </tr>
    <tr>
      <td>2</td>
      <td>Cucumbertown</td>
      <td>6</td>
    </tr>
    <tr>
      <td>3</td>
      <td>Onionville</td>
      <td>13</td>
    </tr>
  </tbody>
</table>

#### 💬 You: It seems there are a few people living in these villages. How can I see a list of all inhabitants?
```sql
SELECT * FROM INHABITANT;
```
> Output:
<table border="1" cellpadding="8" cellspacing="0" style="border-collapse: collapse; text-align: left;">
  <thead>
    <tr style="background-color: #f2f2f2;">
      <th>personid</th>
      <th>name</th>
      <th>villageid</th>
      <th>gender</th>
      <th>job</th>
      <th>gold</th>
      <th>state</th>
    </tr>
  </thead>
  <tbody>
    <tr><td>1</td><td>Paul Bakerman</td><td>1</td><td>m</td><td>baker</td><td>850</td><td>friendly</td></tr>
    <tr><td>2</td><td>Ernest Perry</td><td>3</td><td>m</td><td>weaponsmith</td><td>280</td><td>friendly</td></tr>
    <tr><td>3</td><td>Rita Ox</td><td>1</td><td>f</td><td>baker</td><td>350</td><td>friendly</td></tr>
    <tr><td>4</td><td>Carl Ox</td><td>1</td><td>m</td><td>merchant</td><td>250</td><td>friendly</td></tr>
    <tr><td>5</td><td>Dirty Dieter</td><td>3</td><td>m</td><td>smith</td><td>650</td><td>evil</td></tr>
    <tr><td>6</td><td>Gerry Slaughterer</td><td>2</td><td>m</td><td>butcher</td><td>4850</td><td>evil</td></tr>
    <tr><td>7</td><td>Peter Slaughterer</td><td>3</td><td>m</td><td>butcher</td><td>3250</td><td>evil</td></tr>
    <tr><td>8</td><td>Arthur Tailor</td><td>2</td><td>m</td><td>pilot</td><td>490</td><td>kidnapped</td></tr>
    <tr><td>9</td><td>Tiffany Drummer</td><td>1</td><td>f</td><td>baker</td><td>550</td><td>evil</td></tr>
    <tr><td>10</td><td>Peter Drummer</td><td>1</td><td>m</td><td>smith</td><td>600</td><td>friendly</td></tr>
    <tr><td>11</td><td>Dirty Diane</td><td>3</td><td>f</td><td>farmer</td><td>10</td><td>evil</td></tr>
    <tr><td>12</td><td>Otto Alexander</td><td>2</td><td>m</td><td>dealer</td><td>680</td><td>friendly</td></tr>
    <tr><td>13</td><td>Fred Dix</td><td>3</td><td>m</td><td>author</td><td>420</td><td>friendly</td></tr>
    <tr><td>14</td><td>Enrico Carpenter</td><td>3</td><td>m</td><td>weaponsmith</td><td>510</td><td>evil</td></tr>
    <tr><td>15</td><td>Helen Grasshead</td><td>2</td><td>f</td><td>dealer</td><td>680</td><td>friendly</td></tr>
    <tr><td>16</td><td>Ivy Hatter</td><td>1</td><td>f</td><td>dealer</td><td>770</td><td>evil</td></tr>
    <tr><td>17</td><td>Edward Grasshead</td><td>3</td><td>m</td><td>butcher</td><td>990</td><td>friendly</td></tr>
    <tr><td>18</td><td>Ryan Horse</td><td>3</td><td>m</td><td>blacksmith</td><td>390</td><td>friendly</td></tr>
    <tr><td>19</td><td>Ann Meaty</td><td>2</td><td>f</td><td>butcher</td><td>2280</td><td>friendly</td></tr>
  </tbody>
</table>

#### You: Woah, so many people!
<code>SELECT * FROM INHABITANT;</code>
<br>
<code>SELECT * FROM INHABITANT WHERE state = 'friendly';</code>
<br>
<code>SELECT * FROM INHABITANT WHERE state = 'friendly' and job = 'weaponsmith';</code>
<br>
<code>SELECT * FROM INHABITANT WHERE state = 'friendly' and job LIKE '%smith';</code>
<br>
<code>SELECT personid FROM INHABITANT WHERE name = 'Stranger';</code>
<br>
<code>SELECT gold FROM INHABITANT WHERE name = 'Stranger';</code>
<br>
<code>SELECT * FROM ITEM WHERE owner IS NULL;</code>
<br>
<code>UPDATE ITEM SET owner = (SELECT personid FROM INHABITANT WHERE name = 'Stranger') WHERE owner IS NULL;</code><br>
 or<br>
<code>UPDATE ITEM SET owner = 20 WHERE owner IS NULL;</code>
<br>
<code>SELECT * FROM ITEM WHERE owner = (SELECT personid FROM INHABITANT WHERE name = 'Stranger');</code><br>
or<br>
<code>SELECT * FROM ITEM WHERE owner = 20;</code>
<br>
<code>SELECT * FROM INHABITANT WHERE state = 'friendly' AND job IN ('dealer', 'merchant');</code><br>
or<br>
<code>SELECT * FROM INHABITANT WHERE state = 'friendly' AND job = 'dealer' OR job = 'merchant';</code>
<br>
<code>UPDATE ITEM SET owner = 15 WHERE item IN ('ring', 'teapot');</code><br>
or<br>
<code>UPDATE ITEM SET owner = 15 WHERE item = 'ring' OR item = 'teapot';</code>
<br>
<code>UPDATE INHABITANT SET name = 'SOMANSHU' WHERE name = 'Stranger';</code><br>
or<br>
<code>UPDATE INHABITANT SET name = 'SOMANSHU' WHERE personid = 20</code>
<br>
<code>SELECT * FROM INHABITANT WHERE job = 'baker' ORDER BY gold DESC;</code>
<br>
<code>SELECT * FROM INHABITANT WHERE job = 'pilot';</code>
<br>
<code>SELECT i.name FROM INHABITANT i INNER JOIN VILLAGE v ON i.personid = v.chief WHERE v.name = 'Onionville';</code>
<br>
<code>SELECT COUNT(*) FROM INHABITANT i INNER JOIN VILLAGE v ON i.villageid = v.villageid WHERE v.name = 'Onionville' AND i.gender = 'f';</code>
<br>
<code>SELECT i.name FROM INHABITANT i INNER JOIN VILLAGE v ON i.villageid = v.villageid WHERE v.name = 'Onionville' AND i.gender = 'f';</code>
<br>
<code>SELECT SUM(gold) FROM INHABITANT WHERE job IN ('baker', 'dealer', 'merchant'); </code>
<br>
<code>SELECT state, AVG(gold) FROM INHABITANT GROUP BY state;</code>
<br>
<code></code>
<br>
<code></code>
<br>
<code></code>
<br>
<code></code>
<br>
<code></code>
<br>
<code></code>
<br>
<code></code>
<br>
<code></code>
<br>
<code></code>
<br>
<code></code>
<br>
<code></code>
<br>
<code></code>
<br>
<code></code>
<br>
<code></code>
<br>
<code></code>
<br>
<code></code>
<br>
<code></code>
<br>
<code></code>
<br>
<code></code>
<br>
<code></code>
<br>
<code></code>
<br>
<code></code>
<br>
<code></code>
<br>

<code></code>
<br>
