# シフト管理アプリ

## table(second)

### employees table

| column     | date-type  | NULL | key | default | AUTO INCREMENT |
| ---------- | ---------- | ---- | --- | ------- | -------------- |
| id         | INT(11)    | NO   | PK  |         | YES            |
| manager_id | INT(11)    | NO   | FK  |         |                |
| name       | CHAR(50)   | NO   |     |         |                |
| number     | INT(11)    | NO   | UNI |         |                |
| password   | BIGINT(20) | NO   | UNI |         |                |

### managers table

| column   | date-type  | NULL | key | default | AUTO INCREMENT |
| -------- | ---------- | ---- | --- | ------- | -------------- |
| id       | INT(11)    | NO   | PK  |         | YES            |
| store_id | INT(11)    | NO   | FK  |         |                |
| name     | CHAR(50)   | NO   |     |         |                |
| number   | INT(11)    | NO   | UNI |         |                |
| password | BIGINT(20) | NO   | UNI |         |                |

### employer_shift table

| column        | date-type | NULL | key | default | AUTO INCREMENT |
| ------------- | --------- | ---- | --- | ------- | -------------- |
| id            | INT(11)   | NO   | PK  |         | YES            |
| employer_id   | INT(11)   | NO   | FK  |         |                |
| shift_data_id | INT(11)   | NO   | FK  |         |                |

### shift_dates table

| column     | date-type | NULL | key | default | AUTO INCREMENT |
| ---------- | --------- | ---- | --- | ------- | -------------- |
| id         | INT(11)   | NO   | PK  |         | YES            |
| work_day   | DATE      | YES  |     |         |                |
| start_time | TIME      | YES  |     |         |                |
| end_time   | TIME      | YES  |     |         |                |
| type       | CHAR(11)  | YES  |     |         |                |

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
