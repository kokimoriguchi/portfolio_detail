# シフト管理アプリ

## table(third)

### employees table

| column     | date-type  | NULL | key | default | AUTO INCREMENT |
| ---------- | ---------- | ---- | --- | ------- | -------------- |
| id         | INT(11)    | NO   | PK  |         | YES            |
| store_id   | INT(11)    | NO   | FK  |         |                |
| is_manager | BOOLEAN    | NO   |     |         |                |
| name       | CHAR(50)   | NO   |     |         |                |
| number     | INT(11)    | NO   | UNI |         |                |
| password   | BIGINT(20) | NO   | UNI |         |                |

<!-- ### managers table

| column   | date-type  | NULL | key | default | AUTO INCREMENT |
| -------- | ---------- | ---- | --- | ------- | -------------- |
| id       | INT(11)    | NO   | PK  |         | YES            |
| store_id | INT(11)    | NO   | FK  |         |                |
| name     | CHAR(50)   | NO   |     |         |                |
| number   | INT(11)    | NO   | UNI |         |                |
| password | BIGINT(20) | NO   | UNI |         |                | -->

### employer_shift table

| column        | date-type | NULL | key | default | AUTO INCREMENT |
| ------------- | --------- | ---- | --- | ------- | -------------- |
| id            | INT(11)   | NO   | PK  |         | YES            |
| employer_id   | INT(11)   | NO   | FK  |         |                |
| shift_data_id | INT(11)   | NO   | FK  |         |                |

### shift_dates table

| column        | date-type | NULL | key | default | AUTO INCREMENT |
| ------------- | --------- | ---- | --- | ------- | -------------- |
| id            | INT(11)   | NO   | PK  |         | YES            |
| work_day      | DATE      | NO   |     |         |                |
| is_attendance | BOOLEAN   | NO   |     |         |                |

### shift_time table

| column        | date-type | NULL | key | default | AUTO INCREMENT |
| ------------- | --------- | ---- | --- | ------- | -------------- |
| shift_date_id | INT(11)   | NO   |     |         |                |
| start_time    | TIME      | NO   |     |         |                |
| end_time      | TIME      | NO   |     |         |                |

### approve_month table

| column        | date-type | NULL | key | default | AUTO INCREMENT |
| ------------- | --------- | ---- | --- | ------- | -------------- |
| id            | INT(11)   | NO   | PK  |         | YES            |
| is_approve    | BOOLEAN   | NO   |     |         |                |
| shift_time_id | INT(11)   | NO   | FK  |         |                |

<!-- ### all_shift table
| column            | date-type | NULL | key | default | AUTO INCREMENT |
| ----------------- | --------- | ---- | --- | ------- | -------------- |
| id                | INT(11)   | NO   | PK  |         | YES            |
| employer_shift_id | INT(11)   | NO   | FK  |         |                |

### decided_shift table
| column                 | date-type | NULL | key | default | AUTO INCREMENT |
| ---------------------- | --------- | ---- | --- | ------- | -------------- |
| id                     | INT(11)   | NO   | PK  |         | YES            |
| all_temporary_shift_id | INT(11)   | NO   | FK  |         |                | -->

### departments table

| column      | date-type | NULL | key | default | AUTO INCREMENT |
| ----------- | --------- | ---- | --- | ------- | -------------- |
| id          | INT(11)   | NO   | PK  |         | YES            |
| employer_id | INT(11)   | NO   | FK  |         |                |
| name        | CHAR(50)  | NO   |     |         |                |

### skills table

| column | date-type | NULL | key | default | AUTO INCREMENT |
| ------ | --------- | ---- | --- | ------- | -------------- |
| id     | INT(11)   | NO   | PK  |         | YES            |
| name   | CHAR(50)  | NO   |     |         |                |

### employer_skills table

| column      | date-type | NULL | key | default | AUTO INCREMENT |
| ----------- | --------- | ---- | --- | ------- | -------------- |
| id          | INT(11)   | NO   | PK  |         | YES            |
| employer_id | INT(11)   | NO   | FK  |         |                |
| skill_id    | INT(11)   | NO   | FK  |         |                |

### stores table

| column   | date-type | NULL | key | default | AUTO INCREMENT |
| -------- | --------- | ---- | --- | ------- | -------------- |
| id       | INT(11)   | NO   | PRI |         | YES            |
| number   | INT(5)    | NO   |     |         |                |
| password | INT(11)   | NO   | UNI |         |                |
| name     | CHAR(50)  | NO   |     |         |                |

### information

| column   | date-type    | NULL | key | default | AUTO INCREMENT |
| -------- | ------------ | ---- | --- | ------- | -------------- |
| id       | INT(11)      | NO   | PRI |         | YES            |
| store_id | INT(11)      | NO   | FK  |         |                |
| content  | VARCHAR(255) |      |     |         |                |
