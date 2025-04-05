This repository contains my step-by-step solutions for the [SQL Island](https://www.sql-island.com/) interactive SQL learning game.

This repository includes:
- 🧠 Conversation prompts from the game
- ❓ The questions/challenges
- 🧾 My solutions (SQL queries)

Schema:
- VILLAGE (villageid, name, chief)
- INHABITANT (personid, name, villageid, gender, job, gold, state)
- ITEM (item, owner)

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
