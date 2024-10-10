# FreelanceHours

A PHP project using Laravel.

## Schema

![Database schema](./.github/images/db-schema.png)

<details>
<summary>
Open to see <a href="dbdiagram.io">dbdiagram.io</a> script
</summary>

```
Table users {
  id int [primary key, increment]
  name string
  email string
  avatar string
  rating int
}

Table projects {
  id int [primary key, increment]
  title string
  description text
  created_at datetime
  ends_at datetime
  status string
  tech_stack json
  created_by fk [ref: < users.id]
}

Table proposals {
  id int [primary key, increment]
  email string
  hours int
  project_id fk [ref: < projects.id]
}
```

</details>

## Important commands

1. To drop all tables and recreate migrations

`php artisan migrate:fresh`

2. To seed database

`php artisan db:seed`

3. To do 1 and 2 steps at the same time

`php artisan migrate:fresh --seed`
