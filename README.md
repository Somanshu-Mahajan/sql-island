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
#### You: Man! I'm hungry. I will go and find a butcher to ask for some free sausages.
> SELECT * FROM inhabitant WHERE job = 'butcher'<br>
> Output:
<table>
  <thead>
    <tr>
      <th>personid</th><th>name</th><th>villageid</th><th>gender</th><th>job</th><th>gold</th><th>state</th>
    </tr>
  </thead>
  <tbody>
    <tr><td>6</td><td>Gerry Slaughterer</td><td>2</td><td>m</td><td>butcher</td><td>4850</td><td>evil</td></tr>
    <tr><td>7</td><td>Peter Slaughterer</td><td>3</td><td>m</td><td>butcher</td><td>3250</td><td>evil</td></tr>
    <tr><td>17</td><td>Edward Grasshead</td><td>3</td><td>m</td><td>butcher</td><td>990</td><td>friendly</td></tr>
    <tr><td>19</td><td>Ann Meaty</td><td>2</td><td>f</td><td>butcher</td><td>2280</td><td>friendly</td></tr>
  </tbody>
</table>

#### Edward Grasshead(Butcher): There you are! Enjoy your meal! But take care of yourself. As long as you are unarmed, stay away from villains. Not everyone on this island is friendly.
#### You: Thank you, Edward! Okay, let's see who is friendly on this island...

```sql
SELECT * FROM INHABITANT WHERE state = 'friendly';
```
> Output:
<table>
  <thead>
    <tr>
      <th>personid</th><th>name</th><th>villageid</th><th>gender</th><th>job</th><th>gold</th><th>state</th>
    </tr>
  </thead>
  <tbody>
    <tr><td>1</td><td>Paul Bakerman</td><td>1</td><td>m</td><td>baker</td><td>850</td><td>friendly</td></tr>
    <tr><td>2</td><td>Ernest Perry</td><td>3</td><td>m</td><td>weaponsmith</td><td>280</td><td>friendly</td></tr>
    <tr><td>3</td><td>Rita Ox</td><td>1</td><td>f</td><td>baker</td><td>350</td><td>friendly</td></tr>
    <tr><td>4</td><td>Carl Ox</td><td>1</td><td>m</td><td>merchant</td><td>250</td><td>friendly</td></tr>
    <tr><td>10</td><td>Peter Drummer</td><td>1</td><td>m</td><td>smith</td><td>600</td><td>friendly</td></tr>
    <tr><td>12</td><td>Otto Alexander</td><td>2</td><td>m</td><td>dealer</td><td>680</td><td>friendly</td></tr>
    <tr><td>13</td><td>Fred Dix</td><td>3</td><td>m</td><td>author</td><td>420</td><td>friendly</td></tr>
    <tr><td>15</td><td>Helen Grasshead</td><td>2</td><td>f</td><td>dealer</td><td>680</td><td>friendly</td></tr>
    <tr><td>17</td><td>Edward Grasshead</td><td>3</td><td>m</td><td>butcher</td><td>990</td><td>friendly</td></tr>
    <tr><td>18</td><td>Ryan Horse</td><td>3</td><td>m</td><td>blacksmith</td><td>390</td><td>friendly</td></tr>
    <tr><td>19</td><td>Ann Meaty</td><td>2</td><td>f</td><td>butcher</td><td>2280</td><td>friendly</td></tr>
  </tbody>
</table>

#### You: There is no way around getting a sword for myself. I will now try to find a friendly weaponsmith to forge me one. (Hint: You can combine predicates in the WHERE clause with AND)
```sql
SELECT * FROM INHABITANT WHERE job = 'weaponsmith' AND state = 'friendly';
```
> Output:
<table>
  <thead>
    <tr>
      <th>personid</th><th>name</th><th>villageid</th><th>gender</th><th>job</th><th>gold</th><th>state</th>
    </tr>
  </thead>
  <tbody>
    <tr><td>2</td><td>Ernest Perry</td><td>3</td><td>m</td><td>weaponsmith</td><td>280</td><td>friendly</td></tr>
  </tbody>
</table>

#### You: Oh, that does not look good. Maybe other friendly smiths can help you out, e.g. a blacksmith. Try out: job LIKE '%smith' to find all inhabitants whose job ends with 'smith' (% is a wildcard for any number of characters).
```sql
SELECT * FROM INHABITANT WHERE job LIKE '%smith' AND state = 'friendly';
```
> Output:
<table>
  <thead>
    <tr>
      <th>personid</th><th>name</th><th>villageid</th><th>gender</th><th>job</th><th>gold</th><th>state</th>
    </tr>
  </thead>
  <tbody>
    <tr><td>2</td><td>Ernest Perry</td><td>3</td><td>m</td><td>weaponsmith</td><td>280</td><td>friendly</td></tr>
    <tr><td>10</td><td>Peter Drummer</td><td>1</td><td>m</td><td>smith</td><td>600</td><td>friendly</td></tr>
    <tr><td>18</td><td>Ryan Horse</td><td>3</td><td>m</td><td>blacksmith</td><td>390</td><td>friendly</td></tr>
  </tbody>
</table>

#### You: That looks better! I will go and visit those smiths.
#### Paul: Hi stranger! Where are you going? I'm Paul, I'm the major of Monkeycity. I will go ahead and register you as a citizen.
> INSERT INTO inhabitant (name, villageid, gender, job, gold, state) VALUES ('Stranger', 1, '?', '?', 0, '?')
#### You: No need to call me stranger! What's my personid? (Hint: Use a SELECT query without an asterisk. In former queries, the * stands for: all columns. Instead of the star, you can also address one or more columns (seperated by a comma) and you will only get the columns you need.)
```sql
SELECT personid FROM INHABITANT WHERE name = 'Stranger';
```
> Output:
<table>
  <thead>
    <tr>
      <th>personid</th>
    </tr>
  </thead>
  <tbody>
    <tr><td>20</td></tr>
  </tbody>
</table>

#### You: Hi Ernest! How much is a sword?
#### Ernest: I can offer to make you a sword for 150 gold. That's the cheapest you will find! How much gold do you have?
```sql
SELECT gold FROM INHABITANT WHERE personid = 20;
```
> Output:
<table>
  <thead>
    <tr>
      <th>gold</th>
    </tr>
  </thead>
  <tbody>
    <tr><td>0</td></tr>
  </tbody>
</table>
