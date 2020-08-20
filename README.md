# MySQL Cheat Sheet
MySQL Cheat Sheet with the most needed stuff..










## Restart/Start/Stop/Status
```bash
# Start
sudo /etc/init.d/mysql start

# Stop
sudo /etc/init.d/mysql stop

# Restart / reload configs:
sudo /etc/init.d/mysql restart

# Check run status:
sudo /etc/init.d/mysql status
```




## Show current mysql processes
```bash
sudo mysql -e 'show processlist'
```




<br />
<br />


 _____________________________________________________
 _____________________________________________________


<br />
<br />


## Import big SQL file via console
```bash
mysql -h 127.0.0.1 -P 3306 -uroot -pyourpasswordhere youtube < "Y:\youtube\disk1_mysql.sql"
```


<br />
<br />


 _____________________________________________________
 _____________________________________________________


<br />
<br />

## Change password (XAMPP)

If you want to reset or change xampp mysql password, or have forgot the password for accessing phpMyAdmin then just follow the below step to reset the password or change the password.

 
<br />
<br />

You can do this by two methods.

 
<br />
<br />

Method 1
<br />
The easiest way is to use the security console, which you can access at http://localhost/security/
This “console” creates a password for the MySQL user “root” and is adjusting the phpMyAdmin configuration.
<br />
- http://localhost/security/xamppsecurity.php

 


Method 2<br />
With the “XAMPP Shell” (command prompt) you can also reset the password. Open the shell and execute this command
mysqladmin.exe -u root password NEWPASSWORDHERE
<br /><br />


Of course, your password should not be “NEWPASSWORDHERE”, too. In the next step you must adjust the phpMyAdmin configuration for this new password. In the file “C:\xampp\phpMyAdmin\config.inc.php” change the lines:<br />
$cfg['Servers'][$i]['user']     = 'root';<br />
$cfg['Servers'][$i]['password'] = '';<br />

<br /><br />
To:
$cfg['Servers'][$i]['user']     = 'root';<br />
$cfg['Servers'][$i]['password'] = 'newpassword';<br />

 <br /><br />

Instead in the XAMPP Shell, you can also change the password with phpMyAdmin, and then adjust the phpMyAdmin configuration.






<br />
<br />


 _____________________________________________________
 _____________________________________________________


<br />
<br />

# SQL Queries


## Create Table
```sql
CREATE TABLE `scrap`.`logs` ( `id` INT(11) NOT NULL AUTO_INCREMENT , `used` INT(11) NOT NULL DEFAULT '0' , `namespalte` TEXT CHARACTER SET utf8 COLLATE utf8_general_ci NOT NULL , PRIMARY KEY (`id`)) ENGINE = InnoDB CHARSET=utf8 COLLATE utf8_general_ci;
```

## Create Column
```sql
ALTER TABLE `export_p` ADD `p_URL` TEXT CHARACTER SET utf8 COLLATE utf8_general_ci NOT NULL ;
```

## Delete rows which contains specific text
```sql
DELETE FROM wp_posts where
post_content like '%ice.com%'
OR
post_content like '%green.com%'
OR
post_content like '%blue.com%'
```


## Replace text in column
```sql
// method 1
UPDATE `wp_posts` SET `post_content` = REPLACE(`post_content`, 'http://', 'https://')

/method 2
update youtube.importname set namespalte = replace(namespalte, '►HD & UNCUT◄ ็็็็็', '►HD & UNCUT◄')
```


## Insert text into column
```sql
insert into title (namespalte) values ('✖ LOST FOOTAGE OF UNBELIEVEABLE UNDERWATER SCENES! ✖')
```


## Update empty columns
```sql
UPDATE import SET text = 'https://www.tuneprotect.com/motor-easy-buy/' WHERE text IS NULL OR text = ''
```




<br />
<br />


 _____________________________________________________
 _____________________________________________________


<br />
<br />



# Node.js



## Import array into row
```javascript
let array = [
single_item_ARRAY[0],
t33n.temprankingNUMBER.toString(),
t33n.URL
]

var query = "INSERT INTO single_item_url (text, ranking, search_url) VALUES (?,?,?)"
connection.query(query, array, function (e, r, f){   });
```



## Find specific column
```javascript
let query = "Select * from single_item_url where text = ?";
connection.query(query, single_item_ARRAY[0], function (e, r, f){ });
```


## Update column with specific text
```javascript
let query = 'UPDATE ' + mysql_database + '.single_item_url SET used = 1 WHERE single_item_url.text = ?';
connection.query(query, t33n.ORIGINAL, function (e, r, f){ });
```





<br />
<br />


 _____________________________________________________
 _____________________________________________________


<br />
<br />





# Performance

## MySQL Performance Checker
```bash
wget http://mysqltuner.pl/ -O mysqltuner.pl
perl mysqltuner.pl
```

## Change table engine for real big text inside of columns
```bash
ALTER TABLE `users`  ROW_FORMAT=DYNAMIC;
ALTER TABLE `users`   ENGINE=MyISAM;
```


