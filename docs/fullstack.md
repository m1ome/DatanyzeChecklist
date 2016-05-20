# Questions for "Fullstack developer"

## 1. Programming
1.1 Let's imagine that you have some sort of **cached** information, will it be enough this code to re-validate it:

```php
$information = Cache::get('user');
if (!$information->isValid()) {
    $information = Database::get('user');
    Cache::set('user', $information);
    return $information;
} else {
    return $information;
}
```

If not please provide some other code that will do this as well. You can use someting like pseudo-code for it, just like in example.

1.2 You have an atomic resource (API in e.g.) that will block you if you request it with more that one connection. What are possible solutions do you have to crawl this resource?

1.3 What is public/private/protected in PHP? Describe a difference between them.

1.4 What is const/let/var in Javascript? Describe a difference between them.

## 2. Database
2.1 What do you know about isolation layers in databases? What is this? What the difference between them?

2.2 Let's say we have a slow query how can we know what indexes it uses?

2.3 Let's imagine we have a two databases:
+ **User** (id, name)
+ **Messages** (user_from_id, user_to_id, message, time)

We have a query that return 100 last messages between two user, in e.g.:
```sql
SELECT message FROM Messages WHERE user_from_id = ? AND user_to_id = ? ORDER BY LIMIT 0, 100
```

And at some point (let's say we start have a 10+ mil users) this query is starting to lag heavily. How can we fix this? Why is this happening?

## 3. Security 
3.1 Can you tell about: XSS, CSRF, SQL injection, man-in-the-middle. In brief.

3.2 What for CSRF-token are used?