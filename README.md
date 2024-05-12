# Mission 3

## Part 1

[Скринкаст Части 1](https://drive.google.com/file/d/12hhRtusqev9At3hAhvL1_aM-lkvuJI0K/view?usp=drive_link)

## Part2

[Скринкаст Части 2](https://drive.google.com/file/d/12hhRtusqev9At3hAhvL1_aM-lkvuJI0K/view?usp=drive_link)

## Part3
**1**
```
SELECT 
  DISTINCT username 
FROM 
  users
```

**2**
```
SELECT 
  u.username, 
  COUNT (m.from) number_of_sent_messages 
FROM 
  messages m 
  LEFT JOIN users u ON m.from = u.id 
GROUP BY 
  u.username
```

**3**
```
SELECT 
  u.username, 
  COUNT (m.id) number_of_recieved_messages 
FROM 
  messages m 
  LEFT JOIN users u ON m.to = u.id 
GROUP BY 
  u.username 
ORDER BY 
  number_of_recieved_messages DESC 
LIMIT 
  1
```

**4**
```
SELECT 
  AVG(messages_count) AS average_of_sent_messages 
FROM 
  (
    SELECT 
      COUNT(text) AS messages_count 
    FROM 
      messages 
    GROUP BY 
      "from"
  ) f1
```
