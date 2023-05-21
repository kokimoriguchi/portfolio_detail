# シフト管理アプリ
## table(first)
### employees table
| column            | date-type  | NULL | key | default | AUTO INCREMENT |
| ----------------- | ---------- | ---- | --- | ------- | -------------- |
| id                | INT(11)    | NO   | PK  |         | YES            |
| employer_name     | CHAR(50)   | NO   |     |         |                |
| employer_number   | INT(11)    | NO   | UNI |         |                |
| employer_skill    | CHAR(50)   | YES  |     |         |                |
| employer_password | BIGINT(20) | NO   | UNI |         |                |

### managers table
| column           | date-type  | NULL | key | default | AUTO INCREMENT |
| ---------------- | ---------- | ---- | --- | ------- | -------------- |
| id               | INT(11)    | NO   | PK  |         | YES            |
| manager_name     | CHAR(50)   | NO   |     |         |                |
| manager_number   | INT(11)    | NO   | UNI |         |                |
| manager_password | BIGINT(20) | NO   | UNI |         |                |

### employer_shift table
| column      | date-type | NULL | key | default | AUTO INCREMENT |
| ----------- | --------- | ---- | --- | ------- | -------------- |
| id          | INT(11)   | NO   | PK  |         | YES            |
| employer_id | INT(11)   | NO   | FK  |         |                |
| work_day    | DATE      | YES  |     |         |                |
| start_time  | TIME      | YES  |     |         |                |
| finish_time | TIME      | YES  |     |         |                |


### all_temporary_shift table
| column            | date-type | NULL | key | default | AUTO INCREMENT |
| ----------------- | --------- | ---- | --- | ------- | -------------- |
| id                | INT(11)   | NO   | PK  |         | YES            |
| employer_shift_id | INT(11)   | NO   | FK  |         |                |

### all_decided_shift table
| column                 | date-type | NULL | key | default | AUTO INCREMENT |
| ---------------------- | --------- | ---- | --- | ------- | -------------- |
| id                     | INT(11)   | NO   | PR  |         | YES            |
| all_temporary_shift_id | INT(11)   | NO   | FK  |         |                |

### category table
| column        | date-type | NULL | key | default | AUTO INCREMENT |
| ------------- | --------- | ---- | --- | ------- | -------------- |
| id            | INT(11)   | NO   | PRI |         | YES            |
| employer_id   | INT(11)   | NO   | FK  |         |                |
| category_name | CHAR(11)  | NO   |     |         |                |

### store_number table
| column         | date-type | NULL | key | default | AUTO INCREMENT |
| -------------- | --------- | ---- | --- | ------- | -------------- |
| id             | INT(11)   | NO   | PRI |         | YES            |
| store_number   | INT(5)    | NO   |     |         |                |
| store_password | INT(11)   | NO   | UNI |         |                |
