# Today I learned 

## Will post stuff I learn during my day to day life

- Mounting a drive, instead of using UI, going to files and clicking files.

### steps

- create a folder using command `mkdir /media/sharma/X`
- find all the disks available using `sudo fdisk -l`
- mount the disk at folder using `sudo mount /dev/sda6 /media/sharma/X`

---

- What are first class citizen in programming language?

- Any type, object, entity which has all opertaion generally available to other entities, like being passed as argument, returned from function, modified and assigned an value.

---

- How to copy the data from redis server to local redis server?

- Although there are SAVE and BIGSAVE command, but still their is cool way to do.
- go to local redis server and run this command `redis-cli slaveof IP-ADDRESS-OF-OLD-SERVER 6379`
- wait for a while, it will cooy all data, you won't be able to make changes/connect while copy is in progress.
- So after this is complete run this command `redis-cli slaveof no one`
- now we have entire database copied to our local server.

---

- Connecting to redis cli?

- redis-cli -h IP_ADDR_OF_BOX -p 6379

---

- Never use `keys p_*` in production, it will block the incomming call while computation.

- Use SCAN is recommended for production, so you can use something like:  
  `SCAN 0 COUNT 100 MATCH p_*`

---

- Never add column with some default value to a table in production, it blocks incoming request.

- NEVER DO THIS

```
-- read & write block until it is fully rewritten(which could take hours)
ALTER TABLE name ADD COLUMN last_update timestamptz DEFAULT now();

```

- DO THIS INSTEAD (batch update)

```
ALTER TABLE name ADD COLUMN last_update timestamptz;

do {
 numOfRowsUpdated = executeUpdate(
   "UPDATE name SET last_update = ? " +
   "WHERE id IN (SELECT id FROM name WHERE last_update IS NULL LIMIT 5000)",
   now);
} while (numOfRowsUpdate > 0);


```

---

