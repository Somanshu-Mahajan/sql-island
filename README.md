This repository contains my step-by-step solutions for the [SQL Island](https://www.sql-island.com/) interactive SQL learning game.<br>
NDchkaQLUr<br>
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

#### You: Damn! No mon, no fun. There has to be another option to earn gold other than going to work. Maybe I could collect ownerless items and sell them! Can I make a list of all items that don't belong to anyone? (Hint: You can recognize ownerless items by: WHERE owner IS NULL)
```sql
SELECT * FROM ITEM WHERE owner IS NULL;
```
<table>
  <thead>
    <tr><th>item</th><th>owner</th></tr>
  </thead>
  <tbody>
    <tr><td>teapot</td><td>null</td></tr>
    <tr><td>ring</td><td>null</td></tr>
    <tr><td>coffee cup</td><td>null</td></tr>
    <tr><td>bucket</td><td>null</td></tr>
    <tr><td>carton</td><td>null</td></tr>
    <tr><td>lightbulb</td><td>null</td></tr>
  </tbody>
</table>

#### You: So much cool stuff!
#### You: Yay, a coffee cup. Let's collect it!
> UPDATE item SET owner = 20 WHERE item = 'coffee cup'
#### You: Do you know a trick how to collect all the ownerless items?
```sql
UPDATE ITEM SET owner = 20 WHERE owner IS NULL;
```
#### You: Now list all of the items I have!
```sql
SELECT * FROM ITEM WHERE owner = 20;
```
> Output:
<table>
  <thead>
    <tr><th>item</th><th>owner</th></tr>
  </thead>
  <tbody>
    <tr><td>teapot</td><td>20</td></tr>
    <tr><td>ring</td><td>20</td></tr>
    <tr><td>coffee cup</td><td>20</td></tr>
    <tr><td>bucket</td><td>20</td></tr>
    <tr><td>carton</td><td>20</td></tr>
    <tr><td>lightbulb</td><td>20</td></tr>
  </tbody>
</table>

#### You: Find a friendly inhabitant who is either a dealer or a merchant. Maybe they want to buy some of my items. (Hint: When you use both AND and OR, don't forget to put brackets correctly!)
```sql
SELECT * FROM INHABITANT WHERE job IN ('dealer', 'merchant') AND state = 'friendly';
```
> Output:
<table>
  <thead>
    <tr><th>personid</th><th>name</th><th>villageid</th><th>gender</th><th>job</th><th>gold</th><th>state</th></tr>
  </thead>
  <tbody>
    <tr><td>4</td><td>Carl Ox</td><td>1</td><td>m</td><td>merchant</td><td>250</td><td>friendly</td></tr>
    <tr><td>12</td><td>Otto Alexander</td><td>2</td><td>m</td><td>dealer</td><td>680</td><td>friendly</td></tr>
    <tr><td>15</td><td>Helen Grasshead</td><td>2</td><td>f</td><td>dealer</td><td>680</td><td>friendly</td></tr>
  </tbody>
</table>

#### Helen Grasshead(dealer): I'd like to get the ring and the teapot. The rest is nothing but scrap. Please give me the two items. My personid is 15.
```sql
UPDATE ITEM SET owner = 15 WHERE item IN ('ring', 'teapot');
```
#### Helen Grasshead(dealer): Thank you!
#### Helen Grasshead(dealer): Here, some gold!
> UPDATE inhabitant SET gold = gold + 120 WHERE personid = 20

#### You: Unfortunately, that's not enough gold to buy a sword. Seems like I do have to work after all. Maybe it's not a bad idea to change my name from Stranger to my real name before I will apply for a job.
```sql
UPDATE INHABITANT SET name = 'Somanshu' WHERE personid = 20;
```
#### You: Since baking is one of my hobbies, why not find a baker who I can work for? (Hint: List all bakers and use 'ORDER BY gold' to sort the results. 'ORDER BY gold DESC' is even better because then the richest baker is on top.)
```sql
SELECT * FROM INHABITANT WHERE job = 'baker' ORDER BY gold DESC;
```
> Output:
<table>
  <thead>
    <tr><th>personid</th><th>name</th><th>villageid</th><th>gender</th><th>job</th><th>gold</th><th>state</th></tr>
  </thead>
  <tbody>
    <tr><td>1</td><td>Paul Bakerman</td><td>1</td><td>m</td><td>baker</td><td>850</td><td>friendly</td></tr>
    <tr><td>9</td><td>Tiffany Drummer</td><td>1</td><td>f</td><td>baker</td><td>550</td><td>evil</td></tr>
    <tr><td>3</td><td>Rita Ox</td><td>1</td><td>f</td><td>baker</td><td>350</td><td>friendly</td></tr>
  </tbody>
</table>

#### You: Aha, Paul! I know him!
#### Paul: Hi, you again! So, Somanshu is your name. I saw you want to work as a baker? Okay! You will be paid 1 gold for 100 bread rolls.
#### You: (8 hours later...) Here, I made ten thousand bread rolls! I quit! This should be enough money to buy a sword. Let's see what happens with my gold balance.
> UPDATE inhabitant SET gold = gold + 100 - 150 WHERE personid = 20
#### Edward: Here's your new sword, Somonsho! Now you can go everywhere.
> INSERT INTO item (item, owner) VALUES ('sword', 20)
#### You: My name is Somanshu! Thanks anyway!
#### You: Is there a pilot on this island by any chance? He could fly me home.
```sql
SELECT * FROM INHABITANT WHERE job = 'pilot';
```
> Output:
<table>
  <thead>
    <tr><th>personid</th><th>name</th><th>villageid</th><th>gender</th><th>job</th><th>gold</th><th>state</th></tr>
  </thead>
  <tbody>
    <tr><td>8</td><td>Arthur Tailor</td><td>2</td><td>m</td><td>pilot</td><td>490</td><td>kidnapped</td></tr>
  </tbody>
</table>

#### You: Oh no, his state is 'kidnapped'.
#### Edward: Horrible, the pilot is held captive by Dirty Dieter! I will show you a trick how to find out the name of the village where Dirty Dieter lives.
> SELECT village.name FROM village, inhabitant WHERE village.villageid = inhabitant.villageid AND inhabitant.name = 'Dirty Dieter'
> Output: 
<table>
  <thead>
    <tr><th>name</th></tr>
  </thead>
  <tbody>
    <tr><td>Onionville</td></tr>
  </tbody>
</table>

#### Edward: The expression presented here is called a join. It combines the information of the inhabitant table with information of the village table by matching villageid values.
#### You: Thanks for the hint! I can use the join to find out the chief's name of the village Onionville. (Hint: In the column 'chief' in the village table, the personid of the chief is stored).
```sql
SELECT i.name FROM INHABITANT i INNER JOIN VILLAGE v ON v.chief = i.personid WHERE v.name = 'Onionville';
```
> Output:
<table>
  <thead>
    <tr><th>name</th></tr>
  </thead>
  <tbody>
    <tr><td>Fred Dix</td></tr>
  </tbody>
</table>

#### You: I've got it! I will visit Fred and ask him about Dirty Dieter and the pilot.
#### You: Um, how many inhabitants does Onionville have?
> SELECT COUNT(*) FROM inhabitant, village WHERE village.villageid = inhabitant.villageid AND village.name = 'Onionville'
> Output:
<table>
  <thead>
    <tr><th>COUNT(*)</th></tr>
  </thead>
  <tbody>
    <tr><td>8</td></tr>
  </tbody>
</table>

#### Fred Dix(Chief of Onionville): Hello Somanshu, the pilot is held captive by Dirty Dieter in his sister's house. Shall I tell you how many women there are in Onionville? Nah, you can figure it out by yourself! (Hint: Women show up as gender = 'f')
```sql
SELECT COUNT(*) FROM INHABITANT i INNER JOIN VILLAGE v ON v.villageid = i.villageid WHERE v.name = 'Onionville' AND gender = 'f';
```
> Output:
<table>
  <thead>
    <tr><th>COUNT(*)</th></tr>
  </thead>
  <tbody>
    <tr><td>1</td></tr>
  </tbody>
</table>

#### You: Oh, only one woman. What's her name?
```sql
SELECT i.name FROM INHABITANT i INNER JOIN VILLAGE v ON v.villageid = i.villageid WHERE v.name = 'Onionville' AND gender = 'f';
```
> Output:
<table>
  <thead>
    <tr><th>name</th></tr>
  </thead>
  <tbody>
    <tr><td>Dirty Diane</td></tr>
  </tbody>
</table>

#### You: Let's go!
#### Dirty Dieter: Somanshu, if you hand me over the entire property of our nearby village Cucumbertown, I will release the pilot. I will show you now what this property consists of.
> SELECT SUM(inhabitant.gold) FROM inhabitant, village WHERE village.villageid = inhabitant.villageid AND village.name = 'Cucumbertown'
> Output:
<table>
  <thead>
    <tr><th>SUM(inhabitant.gold)</th></tr>
  </thead>
  <tbody>
    <tr><td>8980</td></tr>
  </tbody>
</table>

#### You: Oh no, baking bread alone can't solve my problems. If I continue working and selling items though, I could earn more gold than the worth of gold inventories of all bakers, dealers and merchants together. How much gold is that?
```sql
SELECT SUM(gold) FROM INHABITANT WHERE job IN ('baker', 'dealer' ,'merchant');
```
> Output:
<table>
  <thead>
    <tr><th>SUM(gold)</th></tr>
  </thead>
  <tbody>
    <tr><td>4130</td></tr>
  </tbody>
</table>

#### You: That's not enough.
#### You: Let's have a look at how much average gold people own, depending on their job.
> SELECT job, SUM(inhabitant.gold), AVG(inhabitant.gold) FROM inhabitant GROUP BY job ORDER BY AVG(inhabitant.gold)
> Output:
<table>
  <thead>
    <tr><th>job</th><th>SUM(inhabitant.gold)</th><th>AVG(inhabitant.gold)</th></tr>
  </thead>
  <tbody>
    <tr><td>farmer</td><td>10</td><td>10.0</td></tr>
    <tr><td>?</td><td>70</td><td>70.0</td></tr>
    <tr><td>merchant</td><td>250</td><td>250.0</td></tr>
    <tr><td>blacksmith</td><td>390</td><td>390.0</td></tr>
    <tr><td>weaponsmith</td><td>790</td><td>395.0</td></tr>
    <tr><td>author</td><td>420</td><td>420.0</td></tr>
    <tr><td>pilot</td><td>490</td><td>490.0</td></tr>
    <tr><td>baker</td><td>1750</td><td>583.333333333333</td></tr>
    <tr><td>smith</td><td>1250</td><td>625.0</td></tr>
    <tr><td>dealer</td><td>2130</td><td>710.0</td></tr>
    <tr><td>butcher</td><td>11370</td><td>2842.5</td></tr>
  </tbody>
</table>

#### You: Very interesting: For some reason, butchers own the most gold. How much gold do different inhabitants have on average, depending on their state (friendly, ...)?
```sql
SELECT state, AVG(gold) FROM INHABITANT GROUP BY state;
```
> Output:
<table>
  <thead>
    <tr><th>state</th><th>AVG(gold)</th></tr>
  </thead>
  <tbody>
    <tr><td>?</td><td>70.0</td></tr>
    <tr><td>evil</td><td>1512.85714285714</td></tr>
    <tr><td>friendly</td><td>706.363636363636</td></tr>
    <tr><td>kidnapped</td><td>490.0</td></tr>
  </tbody>
</table>

#### You: Ok, so the only way is to mug the villains.
#### You: Or I might as well go ahead and just kill Dirty Dieter with my sword!
> DELETE FROM inhabitant WHERE name = 'Dirty Dieter'

#### Dirty Diane: Heeeey! Now I'm very angry! What will you do next, Somanshu?
```sql
DELETE FROM INHABITANT WHERE name = 'Dirty Diane';
```

#### You: Yeah! Now I release the pilot!
```sql
UPDATE INHABITANT SET state = 'friendly' WHERE state = 'kidnapped';
```

#### Pilot: Thank's for releasing me, Somanshu! I will fly you home!
#### You: I take my sword, some gold and lots of useless items with me as a souvenir. What a big adventure!
> UPDATE inhabitant SET state = 'emigrated' WHERE personid = 20

### The game is over. Get your certificate of completion now! If you want to change the name on the certificate, use an UPDATE command on the inhabitants table.












