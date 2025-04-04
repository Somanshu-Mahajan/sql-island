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
<code>UPDATE INHABITANT SET name = 'SOMANSHU' WHERE name = 'Stranger';</code<br>
or<br>
<code>UPDATE INHABITANT SET name = 'SOMANSHU' WHERE personid = 20</code>
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
