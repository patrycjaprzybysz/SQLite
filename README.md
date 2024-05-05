# SQLite - tutorial

## 2 - Core features 


### 2.1

```
select * from penguins
```
![image](https://github.com/patrycjaprzybysz/SQLite/assets/100605325/ccb1679c-159b-4af1-ade9-c4c5f20d6d73)

### 2.2

```
select
    species,
    island,
    sex
from little_penguins;
```
![image](https://github.com/patrycjaprzybysz/SQLite/assets/100605325/d2b4e893-8bb6-465f-8d42-1f44f6ddfd37)

### 2.3

```
select
    species,
    sex,
    island
from little_penguins
order by island asc, sex desc;
```
![image](https://github.com/patrycjaprzybysz/SQLite/assets/100605325/0970a330-efc8-4fa5-b51e-e15816e6b4b8)

### 2.4

```
select
    species,
    sex,
    island
from penguins
order by species, sex, island
limit 10;
```
![image](https://github.com/patrycjaprzybysz/SQLite/assets/100605325/a6e56374-b8aa-41bc-aaef-fa7387d5c2fc)

### 2.5

```
select
    species,
    sex,
    island
from penguins
order by species, sex, island
limit 10 offset 3;
```
![image](https://github.com/patrycjaprzybysz/SQLite/assets/100605325/d29efd77-497e-4b91-8031-a3d85490b67b)


### 2.6

```
select distinct
    species,
    sex,
    island
from penguins;
```
![image](https://github.com/patrycjaprzybysz/SQLite/assets/100605325/4a7f7487-1a27-471d-a4e5-01d750b7a95d)

### 2.7

```
select distinct
    species,
    sex,
    island
from penguins
where island = 'Biscoe';
```
![image](https://github.com/patrycjaprzybysz/SQLite/assets/100605325/c8de052f-228e-4d9d-8f70-790b6946bdbe)

### 2.8

```
select
    flipper_length_mm / 10.0,
    body_mass_g / 1000.0
from penguins
limit 3;
```
![image](https://github.com/patrycjaprzybysz/SQLite/assets/100605325/c9766ae6-e46d-4f9c-af51-fe729247e51f)


### 2.9

```
select
    flipper_length_mm / 10.0 as flipper_cm,
    body_mass_g / 1000.0 as weight_kg,
    island as where_found
from penguins
limit 3;
```
![image](https://github.com/patrycjaprzybysz/SQLite/assets/100605325/5db73404-b4ad-4d50-aa59-02f51fadd1b6)

### 2.10

```
select
    flipper_length_mm / 10.0 as flipper_cm,
    body_mass_g / 1000.0 as weight_kg,
    island as where_found
from penguins
limit 5;
```
![image](https://github.com/patrycjaprzybysz/SQLite/assets/100605325/294ce8a7-9b0d-4066-8ed0-5530f7a8013c)

### 2.11

```
select distinct
    species,
    sex,
    island
from penguins
where island = 'Biscoe';
```
![image](https://github.com/patrycjaprzybysz/SQLite/assets/100605325/b2cdccdd-e18b-46ba-8213-749e67a2e4d3)

### 2.12

```
select distinct
    species,
    sex,
    island
from penguins
where island = 'Biscoe' and sex != 'FEMALE';
```
![image](https://github.com/patrycjaprzybysz/SQLite/assets/100605325/345e94bb-0014-4a89-823e-59b5db2e8cbb)

### 2.13

```
select null = null;

```
![image](https://github.com/patrycjaprzybysz/SQLite/assets/100605325/5fdfa247-f785-4c45-944d-a2481b06419d)

### 2.14

```
select
    species,
    sex,
    island
from penguins
where sex is null;
```
![image](https://github.com/patrycjaprzybysz/SQLite/assets/100605325/1522b3c4-ca63-4d5a-b760-8e853c849801)

### 2.15

```
select sum(body_mass_g) as total_mass
from penguins;
```
![image](https://github.com/patrycjaprzybysz/SQLite/assets/100605325/4602b44a-76e0-4701-8171-1ddcd9705d50)

### 2.16

```
select
    max(bill_length_mm) as longest_bill,
    min(flipper_length_mm) as shortest_flipper,
    avg(bill_length_mm) / avg(bill_depth_mm) as weird_ratio
from penguins;
```
![image](https://github.com/patrycjaprzybysz/SQLite/assets/100605325/45413bb4-1e1d-4ce8-8089-11e5fa8b50ce)

### 2.17

```
select
    count(*) as count_star,
    count(sex) as count_specific,
    count(distinct sex) as count_distinct
from penguins;
```
![image](https://github.com/patrycjaprzybysz/SQLite/assets/100605325/13656bb4-3753-4040-b93c-a57f5ca17a69)

### 2.18

```
select avg(body_mass_g) as average_mass_g
from penguins
group by sex;
```
![image](https://github.com/patrycjaprzybysz/SQLite/assets/100605325/00d38a65-e3a1-498b-8de1-b10253c66bdc)

### 2.19

```
select
    sex,
    avg(body_mass_g) as average_mass_g
from penguins
group by sex;
```
![image](https://github.com/patrycjaprzybysz/SQLite/assets/100605325/4eb93ef1-d944-4ee0-a862-a21f79ed5ed7)

### 2.20

```
select
    sex,
    body_mass_g
from penguins
group by sex;
```
![image](https://github.com/patrycjaprzybysz/SQLite/assets/100605325/48c6cf85-ce6d-401e-9162-0ae618ee3ad0)

### 2.21

```
select
    sex,
    avg(body_mass_g) as average_mass_g
from penguins
group by sex
having average_mass_g > 4000.0;
```
![image](https://github.com/patrycjaprzybysz/SQLite/assets/100605325/3e58702a-5fb8-4972-8843-f23e76f44dc9)

### 2.22

```
select
    sex,
    round(avg(body_mass_g), 1) as average_mass_g
from penguins
group by sex
having average_mass_g > 4000.0;
```
![image](https://github.com/patrycjaprzybysz/SQLite/assets/100605325/232e2cf4-98e0-497e-a7bf-976c4a3f33a7)

### 2.23

```
select
    sex,
    round(
        avg(body_mass_g) filter (where body_mass_g < 4000.0),
        1
    ) as average_mass_g
from penguins
group by sex;
```
![image](https://github.com/patrycjaprzybysz/SQLite/assets/100605325/9eedd200-e6aa-4bb7-9573-aaf544475ab1)

### 2.24 Creating in-memory database

```
create table job (
    name text not null,
    billable real not null
);
create table work (
    person text not null,
    job text not null
);
```
### 2.25 Inserting data

```
insert into job values
('calibrate', 1.5),
('clean', 0.5);
insert into work values
('mik', 'calibrate'),
('mik', 'clean'),
('mik', 'complain'),
('po', 'clean'),
('po', 'complain'),
('tay', 'complain');
```


### 2.26 updating rows

```
update work
set person = 'tae'
where person = 'tay';
```


### 2.27

```
delete from work
where person = 'tae';

select * from work;
```
![image](https://github.com/patrycjaprzybysz/SQLite/assets/100605325/221d1660-c98a-461d-bf25-bf14dabacf55)


### 2.28

```
create table backup (
    person text not null,
    job text not null
);

insert into backup
select
    person,
    job
from work
where person = 'tae';

delete from work
where person = 'tae';

select * from backup;
```

### 2.29

```
select *
from work cross join job;
```
![image](https://github.com/patrycjaprzybysz/SQLite/assets/100605325/56069e81-ffa3-406e-8627-1df7831f0af7)



### 2.30

```
select *
from work inner join job
    on work.job = job.name;
```
![image](https://github.com/patrycjaprzybysz/SQLite/assets/100605325/65cda02f-cced-4801-b7bc-a499b9ba21f2)

### 2.31

```
select
    work.person,
    sum(job.billable) as pay
from work inner join job
    on work.job = job.name
group by work.person;
```

![image](https://github.com/patrycjaprzybysz/SQLite/assets/100605325/ccdab28b-991e-48fc-9eb8-9aa4a6a72f93)


### 2.32

```
select *
from work left join job
    on work.job = job.name;
```
![image](https://github.com/patrycjaprzybysz/SQLite/assets/100605325/2db402e1-0770-4139-b089-bac92bb793b0)

### 2.33

```
select
    work.person,
    sum(job.billable) as pay
from work left join job
    on work.job = job.name
group by work.person;
```
![image](https://github.com/patrycjaprzybysz/SQLite/assets/100605325/915ae2b1-f19f-4b2b-9ebd-d8cbb7ea7191)

### 2.34

```
select
    work.person,
    coalesce(sum(job.billable), 0.0) as pay
from work left join job
    on work.job = job.name
group by work.person;
```
![image](https://github.com/patrycjaprzybysz/SQLite/assets/100605325/2b149897-7260-4838-ba73-a9fbbb31160d)

### 2.35

```
create table sizee (
    s text not null
);
insert into sizee values ('light'), ('heavy');

create table weightt (
    w text not null
);

select * from sizee full outer join weightt;
```
![image](https://github.com/patrycjaprzybysz/SQLite/assets/100605325/08b9e1ac-871c-4c45-aec3-5e1ffe3ed0a4)

## 3 - Tools

### 3.1

```
select distinct person
from work
where job != 'calibrate';
```
![image](https://github.com/patrycjaprzybysz/SQLite/assets/100605325/4633bf04-074a-4c60-bd44-df3a0a03fa63)

### 3.2

```
select *
from work
where person not in ('mik', 'tay');
```
![image](https://github.com/patrycjaprzybysz/SQLite/assets/100605325/5a4a7832-464e-4828-b0a0-8c234e9fea47)

### 3.3

```
select distinct person
from work
where person not in (
    select distinct person
    from work
    where job = 'calibrate'
);
```
![image](https://github.com/patrycjaprzybysz/SQLite/assets/100605325/87ee944e-8e78-4d17-8c9e-f4e45a726e89)

### 3.4

```
create table lab_equipment (
    size real not null,
    color text not null,
    num integer not null,
    primary key (size, color)
);

insert into lab_equipment values
(1.5, 'blue', 2),
(1.5, 'green', 1),
(2.5, 'blue', 1);

select * from lab_equipment;

insert into lab_equipment values
(1.5, 'green', 2);
```
![image](https://github.com/patrycjaprzybysz/SQLite/assets/100605325/623b4939-83a2-4e77-9dc0-1ba7f4a2b551)

### 3.5

```
create table person (
    ident integer primary key autoincrement,
    name text not null
);
insert into person values
(null, 'mik'),
(null, 'po'),
(null, 'tay');
select * from person;
insert into person values (1, 'prevented');
```
![image](https://github.com/patrycjaprzybysz/SQLite/assets/100605325/158d6b53-8829-47ea-a733-3b92c8cfab07)

### 3.6

```
select * from sqlite_sequence;
```
![image](https://github.com/patrycjaprzybysz/SQLite/assets/100605325/f0848401-6520-4a10-a3e0-c6282a71f395)

### 3.7

```
alter table job
add ident integer not null default -1;

update job
set ident = 1
where name = 'calibrate';

update job
set ident = 2
where name = 'clean';

select * from job;
```
![image](https://github.com/patrycjaprzybysz/SQLite/assets/100605325/64e995dc-f1b0-46f5-a6aa-96adaf8f712f)

### 3.8

```
create table new_work (
    person_id integer not null,
    job_id integer not null,
    foreign key (person_id) references person (ident),
    foreign key (job_id) references job (ident)
);

insert into new_work
select
    person.ident as person_id,
    job.ident as job_id
from
    (person inner join work on person.name = work.person)
    inner join job on job.name = work.job;
select * from new_work;
```
![image](https://github.com/patrycjaprzybysz/SQLite/assets/100605325/961dc5b6-e249-4a1b-b154-6f0d7431db34)

### 3.9

```
drop table work;
alter table new_work rename to work;
CREATE TABLE job (
    ident integer primary key autoincrement,
    name text not null,
    billable real not null
);
CREATE TABLE sqlite_sequence(name,seq);
CREATE TABLE person (
    ident integer primary key autoincrement,
    name text not null
);
CREATE TABLE IF NOT EXISTS "work" (
    person_id integer not null,
    job_id integer not null,
    foreign key(person_id) references person(ident),
    foreign key(job_id) references job(ident)
);
```
![image](https://github.com/patrycjaprzybysz/SQLite/assets/100605325/46bfa9d0-32d9-46f3-bd77-036521ecda84)

### 3.10

```
select body_mass_g
from penguins
where
    body_mass_g > (
        select avg(body_mass_g)
        from penguins
    )
limit 5;
```
![image](https://github.com/patrycjaprzybysz/SQLite/assets/100605325/e6c604b7-13dd-40be-9baf-7f408a19f4db)

### 3.11

```
select
    penguins.species,
    penguins.body_mass_g,
    round(averaged.avg_mass_g, 1) as avg_mass_g
from penguins inner join (
    select
        species,
        avg(body_mass_g) as avg_mass_g
    from penguins
    group by species
) as averaged
    on penguins.species = averaged.species
where penguins.body_mass_g > averaged.avg_mass_g
limit 5;
```
![image](https://github.com/patrycjaprzybysz/SQLite/assets/100605325/a26e9880-93a8-45ea-a072-ceab26642254)


### 3.12

```
with grouped as (
    select
        species,
        avg(body_mass_g) as avg_mass_g
    from penguins
    group by species
)

select
    penguins.species,
    penguins.body_mass_g,
    round(grouped.avg_mass_g, 1) as avg_mass_g
from penguins inner join grouped
where penguins.body_mass_g > grouped.avg_mass_g
limit 5;

select
    penguins.species,
    penguins.body_mass_g,
    round(grouped.avg_mass_g, 1) as avg_mass_g
from penguins inner join grouped
where penguins.body_mass_g > grouped.avg_mass_g
limit 5;
```
![image](https://github.com/patrycjaprzybysz/SQLite/assets/100605325/140df9b9-7bd1-4ad9-8375-8a1f73e1da6c)

### 3.13

```
explain query plan
select
    species,
    avg(body_mass_g)
from penguins
group by species;
```
![image](https://github.com/patrycjaprzybysz/SQLite/assets/100605325/0c85906c-fcfb-42b5-8c57-570e9e3a5b16)

### 3.14

```
select
    rowid,
    species,
    island
from penguins
limit 5;
```
![image](https://github.com/patrycjaprzybysz/SQLite/assets/100605325/0fa81be7-aa8a-4532-a37b-1201c5aed266)


### 3.15

```
with sized_penguins as (
    select
        species,
        iif(
            body_mass_g < 3500,
            'small',
            'large'
        ) as size
    from penguins
    where body_mass_g is not null
)

select
    species,
    size,
    count(*) as num
from sized_penguins
group by species, size
order by species, num;
```
![image](https://github.com/patrycjaprzybysz/SQLite/assets/100605325/81d2f77d-6aa4-41c6-b875-3ea396143188)

### 3.16

```
with sized_penguins as (
    select
        species,
        case
            when body_mass_g < 3500 then 'small'
            when body_mass_g < 5000 then 'medium'
            else 'large'
        end as size
    from penguins
    where body_mass_g is not null
)

select
    species,
    size,
    count(*) as num
from sized_penguins
group by species, size
order by species, num;
```
![image](https://github.com/patrycjaprzybysz/SQLite/assets/100605325/772ca0d8-988c-436a-b178-722ff1df8e0b)

### 3.17

```
with sized_penguins as (
    select
        species,
        case
            when body_mass_g between 3500 and 5000 then 'normal'
            else 'abnormal'
        end as size
    from penguins
    where body_mass_g is not null
)

select
    species,
    size,
    count(*) as num
from sized_penguins
group by species, size
order by species, num;
```
![image](https://github.com/patrycjaprzybysz/SQLite/assets/100605325/03a146e8-18ba-422c-b256-d69cc83b8be4)

### 3.18

```
select * from staff;
```
![image](https://github.com/patrycjaprzybysz/SQLite/assets/100605325/aa5e6989-be29-497f-8e1a-7864a221a9a2)

### 3.19

```
select
    personal,
    family
from staff
where personal like '%ya%';
```
![image](https://github.com/patrycjaprzybysz/SQLite/assets/100605325/f7533f1b-2669-42f7-a998-697ca5410923)

### 3.20

```
select * from (
    select * from (select * from experiment order by started asc limit 5)
    union all
    select * from (select * from experiment order by started desc limit 5)
)
order by started asc;
```
![image](https://github.com/patrycjaprzybysz/SQLite/assets/100605325/be8706d3-4889-4571-9648-4058ee319991)


### 3.21

```
select
    personal,
    family,
    dept,
    age
from staff
where dept = 'mb'
intersect
select
    personal,
    family,
    dept,
    age from staff
where age < 50;
```
![image](https://github.com/patrycjaprzybysz/SQLite/assets/100605325/d6e8d7e4-02ed-47c8-86ec-a5a0b61572ed)

### 3.22

```
select
    personal,
    family,
    dept,
    age
from staff
where dept = 'mb'
except
    select
        personal,
        family,
        dept,
        age from staff
    where age < 50;
```
![image](https://github.com/patrycjaprzybysz/SQLite/assets/100605325/0731af4f-4f78-4603-add1-5d33108feaee)

### 3.23

```
with decorated as (
    select random() as rand,
    personal || ' ' || family as name
    from staff
)

select
    rand,
    abs(rand) % 10 as selector,
    name
from decorated
where selector < 5;
```
![image](https://github.com/patrycjaprzybysz/SQLite/assets/100605325/97c1634f-abc8-4567-9080-173f3ca66371)

### 3.24

```
explain query plan
select filename
from plate
where filename like '%07%';

create index plate_file on plate(filename);

explain query plan
select filename
from plate
where filename like '%07%';
```
![image](https://github.com/patrycjaprzybysz/SQLite/assets/100605325/794d0cd4-7f15-4de0-b87a-2d3391515ea4)

### 3.25

```
select value from generate_series(1, 5);
```

### 3.26

```
create table temp (
    num integer not null
);
insert into temp values (1), (5);
select value from generate_series (
    (select min(num) from temp),
    (select max(num) from temp)
);
```

### 3.27

```
select date((select julianday(min(started)) from experiment) + value) as some_day
from (
    select value from generate_series(
        (select 0),
        (select julianday(max(started)) - julianday(min(started)) from experiment)
    )
)
limit 5;
```

### 3.28

```
with
-- complete sequence of days with 0 as placeholder for number of experiments
all_days as (
    select
        date((select julianday(min(started)) from experiment) + value) as some_day,
        0 as zeroes
    from (
        select value from generate_series(
            (select 0),
            (select count(*) - 1 from experiment)
        )
    )
),

-- sequence of actual days with actual number of experiments started
actual_days as (
    select
        started,
        count(started) as num_exp
    from experiment
    group by started
)

-- combined by joining on day and taking actual number (if available) or zero
select
    all_days.some_day as day,
    coalesce(actual_days.num_exp, all_days.zeroes) as num_exp
from
    all_days left join actual_days on all_days.some_day = actual_days.started
limit 5;
```

### 3.29

```
with person as (
    select
        ident,
        personal || ' ' || family as name
    from staff
)

select
    left_person.name,
    right_person.name
from person as left_person inner join person as right_person
limit 10;
```
![image](https://github.com/patrycjaprzybysz/SQLite/assets/100605325/f1e15d97-94b2-40af-b847-5133b84663c0)

### 3.30

```
with person as (
    select
        ident,
        personal || ' ' || family as name
    from staff
)

select
    left_person.name,
    right_person.name
from person as left_person inner join person as right_person
on left_person.ident < right_person.ident
where left_person.ident <= 4 and right_person.ident <= 4;
```
![image](https://github.com/patrycjaprzybysz/SQLite/assets/100605325/72e429fb-280d-412c-8448-a4b5e3033231)

### 3.31

```
with
person as (
    select
        ident,
        personal || ' ' || family as name
    from staff
),

together as (
    select
        left_perf.staff as left_staff,
        right_perf.staff as right_staff
    from performed as left_perf inner join performed as right_perf
        on left_perf.experiment = right_perf.experiment
    where left_staff < right_staff
)

select
    left_person.name as person_1,
    right_person.name as person_2
from person as left_person inner join person as right_person join together
    on left_person.ident = left_staff and right_person.ident = right_staff;
```
![image](https://github.com/patrycjaprzybysz/SQLite/assets/100605325/69007a60-9e96-48c8-9c62-08f554da3ac7)

### 3.32

```
select
    name,
    building
from department
where
    exists (
        select 1
        from staff
        where dept = department.ident
    )
order by name;
```
![image](https://github.com/patrycjaprzybysz/SQLite/assets/100605325/b65ad202-4424-4de3-9551-356a3f8d9299)

### 3.33

```
select
    name,
    building
from department
where
    not exists (
        select 1
        from staff
        where dept = department.ident
    )
order by name;
```
![image](https://github.com/patrycjaprzybysz/SQLite/assets/100605325/94ab819f-4fc8-4fae-a905-921750eadf2d)

### 3.34

```
select distinct
    department.name as name,
    department.building as building
from department inner join staff
    on department.ident = staff.dept
order by name;
```
![image](https://github.com/patrycjaprzybysz/SQLite/assets/100605325/9081b0f1-66c3-4b24-b953-793ac28248fc)


### 3.35

```
with ym_num as (
    select
        strftime('%Y-%m', started) as ym,
        count(*) as num
    from experiment
    group by ym
)

select
    ym,
    lag(num) over (order by ym) as prev_num,
    num,
    lead(num) over (order by ym) as next_num
from ym_num
order by ym;
```
![image](https://github.com/patrycjaprzybysz/SQLite/assets/100605325/02731d21-9eee-4a28-abeb-eb1a8fcfb094)


### 3.36

```
with ym_num as (
    select
        strftime('%Y-%m', started) as ym,
        count(*) as num
    from experiment
    group by ym
)

select
    ym,
    num,
    sum(num) over (order by ym) as num_done,
    (sum(num) over (order by ym) * 1.00) / (select sum(num) from ym_num) as completed_progress,
    cume_dist() over (order by ym) as linear_progress
from ym_num
order by ym;
```
![image](https://github.com/patrycjaprzybysz/SQLite/assets/100605325/ffdea3d5-14b3-43c4-97da-f06f1601b836)

### 3.37

```
explain query plan
with ym_num as (
    select
        strftime('%Y-%m', started) as ym,
        count(*) as num
    from experiment
    group by ym
)
select
    ym,
    num,
    sum(num) over (order by ym) as num_done,
    cume_dist() over (order by ym) as progress
from ym_num
order by ym;
```
![image](https://github.com/patrycjaprzybysz/SQLite/assets/100605325/798fb19e-cae3-42b4-9135-2ed073b4747f)

### 3.38

```
with y_m_num as (
    select
        strftime('%Y', started) as year,
        strftime('%m', started) as month,
        count(*) as num
    from experiment
    group by year, month
)

select
    year,
    month,
    num,
    sum(num) over (partition by year order by month) as num_done
from y_m_num
order by year, month;
```
![image](https://github.com/patrycjaprzybysz/SQLite/assets/100605325/0537d8a1-581c-45f9-8f4b-e176d34ee998)

## 4 - Advanced Features

### 4.1

```
create table images (
    name text not null,
    content blob
);

insert into images (name, content) values
('biohazard', readfile('img/biohazard.png')),
('crush', readfile('img/crush.png')),
('fire', readfile('img/fire.png')),
('radioactive', readfile('img/radioactive.png')),
('tripping', readfile('img/tripping.png'));

select
    name,
    length(content)
from images;
```

### 4.2

```
.schema
```
![image](https://github.com/patrycjaprzybysz/SQLite/assets/100605325/190a4333-d2c8-4a34-a87b-d6a312f47455)

### 4.3

```
select * from machine;
```
![image](https://github.com/patrycjaprzybysz/SQLite/assets/100605325/b909f2b9-6e58-4791-83f3-cc993804a4a9)

### 4.4

```
select
    details->'$.acquired' as single_arrow,
    details->>'$.acquired' as double_arrow
from machine;
```
![image](https://github.com/patrycjaprzybysz/SQLite/assets/100605325/13893c82-f7d3-4eb4-a1d0-0a729b050f1b)

### 4.5

```
select
    ident,
    json_array_length(log->'$') as length,
    log->'$[0]' as first
from usage;
```
![image](https://github.com/patrycjaprzybysz/SQLite/assets/100605325/b543bbfd-a499-4584-9c5d-3d548bede221)

### 4.6

```
select
    ident,
    json_each.key as key,
    json_each.value as value
from usage, json_each(usage.log)
limit 10;
```
![image](https://github.com/patrycjaprzybysz/SQLite/assets/100605325/3f8c1840-c306-4287-8a6e-0a0a07dbcf8d)

### 4.7

```
select
    ident,
    log->'$[#-1].machine' as final
from usage
limit 5;
```
![image](https://github.com/patrycjaprzybysz/SQLite/assets/100605325/c4e93d97-4702-4b29-952a-38040a9451ce)

### 4.8

```
select
    ident,
    name,
    json_set(details, '$.sold', json_quote('2024-01-25')) as updated
from machine;
```
![image](https://github.com/patrycjaprzybysz/SQLite/assets/100605325/0bebdf1d-46e3-47e1-982e-f8706d571f20)

### 4.9

```
select
    species,
    count(*) as num
from penguins
group by species;
```
![image](https://github.com/patrycjaprzybysz/SQLite/assets/100605325/34a96b9a-7230-47f4-9160-3dae01d3b7eb)

### 4.10

```
alter table penguins
add active integer not null default 1;

update penguins
set active = iif(species = 'Adelie', 0, 1);
select
    species,
    count(*) as num
from penguins
where active
group by species;
```
![image](https://github.com/patrycjaprzybysz/SQLite/assets/100605325/54a8c0f5-b29f-4995-94c6-a18c68b858be)

### 4.11

```
drop table if exists penguins;
.mode csv penguins
.import misc/penguins.csv penguins
update penguins set species = null where species = '';
update penguins set island = null where island = '';
update penguins set bill_length_mm = null where bill_length_mm = '';
update penguins set bill_depth_mm = null where bill_depth_mm = '';
update penguins set flipper_length_mm = null where flipper_length_mm = '';
update penguins set body_mass_g = null where body_mass_g = '';
update penguins set sex = null where sex = '';
```

### 4.12

```
create view if not exists
active_penguins (
    species,
    island,
    bill_length_mm,
    bill_depth_mm,
    flipper_length_mm,
    body_mass_g,
    sex
) as
select
    species,
    island,
    bill_length_mm,
    bill_depth_mm,
    flipper_length_mm,
    body_mass_g,
    sex
from penguins
where active;

select
    species,
    count(*) as num
from active_penguins
group by species;
```
![image](https://github.com/patrycjaprzybysz/SQLite/assets/100605325/7ba7bd51-91ce-4e43-899d-5e5797158e49)

### 4.13

```
create table job (
    name text not null,
    billable real not null
);
insert into job values
('calibrate', 1.5),
('clean', 0.5);
select * from job;
```
![image](https://github.com/patrycjaprzybysz/SQLite/assets/100605325/5239f968-ab0e-4647-bcc3-f36a560d1d46)

### 4.14

```
create table job (
    name text not null,
    billable real not null,
    check (billable > 0.0)
);
insert into job values ('calibrate', 1.5);
insert into job values ('reset', -0.5);
select * from job;
```
![image](https://github.com/patrycjaprzybysz/SQLite/assets/100605325/c08948ca-0586-4b54-b35e-7f11fb5d6b51)

### 4.15

```
create table job (
    name text not null,
    billable real not null,
    check (billable > 0.0)
);

insert into job values ('calibrate', 1.5);

begin transaction;
insert into job values ('clean', 0.5);
rollback;

select * from job;
```
![image](https://github.com/patrycjaprzybysz/SQLite/assets/100605325/27219b23-d3c2-4dc9-97cf-8a1b28683399)

### 4.16

```
create table job (
    name text not null,
    billable real not null,
    check (billable > 0.0) on conflict rollback
);

insert into job values
    ('calibrate', 1.5);
insert into job values
    ('clean', 0.5),
    ('reset', -0.5);

select * from job;
```
![image](https://github.com/patrycjaprzybysz/SQLite/assets/100605325/cf943460-a22f-40e6-a68b-c59ed5ef2128)

### 4.17

```
create table job (
    name text not null,
    billable real not null,
    check (billable > 0.0)
);

insert or rollback into job values
('calibrate', 1.5);
insert or rollback into job values
('clean', 0.5),
('reset', -0.5);

select * from job;
```
![image](https://github.com/patrycjaprzybysz/SQLite/assets/100605325/d73a2169-ce81-4a0b-a219-cdc45131f300)

### 4.18

```
create table jobs_done (
    person text unique,
    num integer default 0
);

insert into jobs_done values
('zia', 1);
.print 'after first'
select * from jobs_done;
.print


insert into jobs_done values
('zia', 1);
.print 'after failed'
select * from jobs_done;

insert into jobs_done values
('zia', 1)
on conflict(person) do update set num = num + 1;
.print '\nafter upsert'
select * from jobs_done;
```
![image](https://github.com/patrycjaprzybysz/SQLite/assets/100605325/9d38c99a-821f-4dba-9d84-4ccb84fafad2)

### 4.19

```
-- Track hours of lab work.
create table job2 (
    person text not null,
    reported real not null check (reported >= 0.0)
);

-- Explicitly store per-person total rather than using sum().
create table total (
    person text unique not null,
    hours real
);

-- Initialize totals.
insert into total values
('gene', 0.0),
('august', 0.0);

-- Define a trigger.
create trigger total_trigger
before insert on job2
begin
    -- Check that the person exists.
    select case
        when not exists (select 1 from total where person = new.person)
        then raise(rollback, 'Unknown person ')
    end;
    -- Update their total hours (or fail if non-negative constraint violated).
    update total
    set hours = hours + new.reported
    where total.person = new.person;
end;
```
![image](https://github.com/patrycjaprzybysz/SQLite/assets/100605325/d241ab38-616d-4fe0-a539-b76a2dfd2144)


### 4.20

```
insert into job2 values
('gene', 1.5),
('august', 0.5),
('gene', 1.0);
```
![image](https://github.com/patrycjaprzybysz/SQLite/assets/100605325/ea895c13-e908-4e65-817a-3ce6b1dcaf1f)

### 4.21

```
insert into job2 values
('gene', 1.0),
('august', -1.0);
```
![image](https://github.com/patrycjaprzybysz/SQLite/assets/100605325/d046a0c6-3a12-4677-b989-25a3ade8b309)

### 4.22

```
create table lineage (
    parent text not null,
    child text not null
);
insert into lineage values
('Arturo', 'Clemente'),
('Darío', 'Clemente'),
('Clemente', 'Homero'),
('Clemente', 'Ivonne'),
('Ivonne', 'Lourdes'),
('Soledad', 'Lourdes'),
('Lourdes', 'Santiago');
```
```
select * from lineage;
```
![image](https://github.com/patrycjaprzybysz/SQLite/assets/100605325/b9b32ce4-2669-498a-bac3-b39dd1e43f47)

### 4.23

```
with recursive descendent as (
    select
        'Clemente' as person,
        0 as generations
    union all
    select
        lineage.child as person,
        descendent.generations + 1 as generations
    from descendent inner join lineage
        on descendent.person = lineage.parent
)

select
    person,
    generations
from descendent;
```
![image](https://github.com/patrycjaprzybysz/SQLite/assets/100605325/7f31fba8-fe7a-4a08-be2b-b89ceb7442f0)

### 4.24

```
create temporary table bi_contact (
    left text,
    right text
);

insert into bi_contact
select
    left, right from contact
    union all
    select right, left from contact
;
```
![image](https://github.com/patrycjaprzybysz/SQLite/assets/100605325/bc727de9-f6ba-4fa0-bc55-e81f434f2ed7)

### 4.25

```
select
    left.name as left_name,
    left.ident as left_ident,
    right.name as right_name,
    right.ident as right_ident,
    min(left.ident, right.ident) as new_ident
from
    (person as left join bi_contact on left.name = bi_contact.left)
    join person as right on bi_contact.right = right.name;
```
![image](https://github.com/patrycjaprzybysz/SQLite/assets/100605325/e0760627-3770-447f-874d-5b652c1b9871)

### 4.26

```
with recursive labeled as (
    select
        person.name as name,
        person.ident as label
    from
        person
    union -- not 'union all'
    select
        person.name as name,
        labeled.label as label
    from
        (person join bi_contact on person.name = bi_contact.left)
        join labeled on bi_contact.right = labeled.name
    where labeled.label < person.ident
)
select name, min(label) as group_id
from labeled
group by name
order by label, name;
```
![image](https://github.com/patrycjaprzybysz/SQLite/assets/100605325/2cfadb9c-1aa9-454f-a2b5-ad134c9e6abd)

## 5 - Python

### 5.1

```
import sqlite3

db_path = 'C:/Users/patip/Desktop/sql-tutorial/db/penguins-python5.db'
connection = sqlite3.connect(db_path)
cursor = connection.execute("select count(*) from penguins;")
rows = cursor.fetchall()
print(rows)
```
![image](https://github.com/patrycjaprzybysz/SQLite/assets/100605325/d93330ee-b7e2-43e6-b380-860803477f20)

### 5.2

```
import sqlite3
import sys

db_path = 'C:/Users/patip/Desktop/sql-tutorial/db/penguins-python5.db'
connection = sqlite3.connect(db_path)
cursor = connection.cursor()
cursor = cursor.execute("select species, island from penguins limit 5;")
while row := cursor.fetchone():
    print(row)
```
![image](https://github.com/patrycjaprzybysz/SQLite/assets/100605325/ddd2c5ec-1316-450a-835f-d6508be2bef6)

### 5.3

```
import sqlite3

connection = sqlite3.connect(":memory:")
cursor = connection.cursor()
cursor.execute("create table example(num integer);")

cursor.execute("insert into example values (10), (20);")
print("after insertion", cursor.execute("select * from example;").fetchall())

cursor.execute("delete from example where num < 15;")
print("after deletion", cursor.execute("select * from example;").fetchall())
```
![image](https://github.com/patrycjaprzybysz/SQLite/assets/100605325/f0e7f4c3-8a0f-4657-8ffc-d53337af526b)

### 5.4

```
import sqlite3

connection = sqlite3.connect(":memory:")
cursor = connection.cursor()
cursor.execute("create table example(num integer);")

cursor.executemany("insert into example values (?);", [(10,), (20,)])
print("after insertion", cursor.execute("select * from example;").fetchall())
```
![image](https://github.com/patrycjaprzybysz/SQLite/assets/100605325/fd52171b-c7a7-4904-980f-400efb043f7f)

### 5.5

```
import sqlite3

SETUP = """\
drop table if exists example;
create table example(num integer);
insert into example values (10), (20);
"""

connection = sqlite3.connect(":memory:")
cursor = connection.cursor()
cursor.executescript(SETUP)
print("after insertion", cursor.execute("select * from example;").fetchall())
```
![image](https://github.com/patrycjaprzybysz/SQLite/assets/100605325/387ec27e-c7d7-4d1d-a4b2-3bc961c0fbca)

### 5.6

```
import sqlite3

SETUP = """\
create table example(num integer check(num > 0));
insert into example values (10);
insert into example values (-1);
insert into example values (20);
"""

connection = sqlite3.connect(":memory:")
cursor = connection.cursor()
try:
    cursor.executescript(SETUP)
except sqlite3.Error as exc:
    print(f"SQLite exception: {exc}")
print("after execution", cursor.execute("select * from example;").fetchall())
```
![image](https://github.com/patrycjaprzybysz/SQLite/assets/100605325/dafec6f7-10da-42ac-80b3-d79bcc3d2562)

### 5.7

```
import sqlite3

SETUP = """\
create table example(num integer);
insert into example values (-10), (10), (20), (30);
"""


def clip(value):
    if value < 0:
        return 0
    if value > 20:
        return 20
    return value


connection = sqlite3.connect(":memory:")
connection.create_function("clip", 1, clip)
cursor = connection.cursor()
cursor.executescript(SETUP)
for row in cursor.execute("select num, clip(num) from example;").fetchall():
    print(row)
```
![image](https://github.com/patrycjaprzybysz/SQLite/assets/100605325/7d9222b2-3db0-4bd9-bfa9-3405ff2d60de)

### 5.8

```
from datetime import date
import sqlite3


# Convert date to ISO-formatted string when writing to database
def _adapt_date_iso(val):
    return val.isoformat()


sqlite3.register_adapter(date, _adapt_date_iso)


# Convert ISO-formatted string to date when reading from database
def _convert_date(val):
    return date.fromisoformat(val.decode())


sqlite3.register_converter("date", _convert_date)

SETUP = """\
create table events(
    happened date not null,
    description text not null
);
"""

connection = sqlite3.connect(":memory:", detect_types=sqlite3.PARSE_DECLTYPES)
cursor = connection.cursor()
cursor.execute(SETUP)

cursor.executemany(
    "insert into events values (?, ?);",
    [(date(2024, 1, 10), "started tutorial"), (date(2024, 1, 29), "finished tutorial")],
)

for row in cursor.execute("select * from events;").fetchall():
    print(row)
```
![image](https://github.com/patrycjaprzybysz/SQLite/assets/100605325/3d94d9ce-df24-4ed1-945c-94c7e60f7585)

### 5.9

```
import pandas as pd
import sqlite3
import sys

db_path = 'C:/Users/patip/Desktop/sql-tutorial/db/penguins-python5.db'
connection = sqlite3.connect(db_path)
query = "select species, count(*) as num from penguins group by species;"
df = pd.read_sql(query, connection)
print(df)
```
![image](https://github.com/patrycjaprzybysz/SQLite/assets/100605325/cf8742f6-648f-46ea-94f6-f5320d9c2ec5)

### 5.10

```
import polars as pl
import sys

db_path = 'C:/Users/patip/Desktop/sql-tutorial/db/penguins.db'
uri = "sqlite:///{db_path}"
query = "select species, count(*) as num from penguins group by species;"
df = pl.read_database_uri(query, uri, engine="adbc")
print(df)
```
![image](https://github.com/patrycjaprzybysz/SQLite/assets/100605325/6a13018a-0773-4a6c-ac40-f2e2fa677b77)

### 5.11

```
from sqlmodel import Field, Session, SQLModel, create_engine, select
import sys


class Department(SQLModel, table=True):
    ident: str = Field(default=None, primary_key=True)
    name: str
    building: str


db_uri = "sqlite:///C:/Users/patip/Desktop/sql-tutorial/db/assays.db"
engine = create_engine(db_uri)
with Session(engine) as session:
    statement = select(Department)
    for result in session.exec(statement).all():
        print(result)
```
![image](https://github.com/patrycjaprzybysz/SQLite/assets/100605325/4866bfc9-a906-4726-b277-946b1a091512)

### 5.12

```
from typing import Optional
from sqlmodel import Field, Session, SQLModel, create_engine, select


class Staff(SQLModel, table=True):
    ident: str = Field(default=None, primary_key=True)
    personal: str
    family: str
    dept: Optional[str] = Field(default=None, foreign_key="department.ident")
    age: int

class Department(SQLModel, table=True):
    ident: str = Field(default=None, primary_key=True)
    name: str
    building: str

db_uri = "sqlite:///C:/Users/patip/Desktop/sql-tutorial/db/assays.db"
engine = create_engine(db_uri)
SQLModel.metadata.create_all(engine)
with Session(engine) as session:
    statement = select(Department, Staff).where(Staff.dept == Department.ident)
    for dept, staff in session.exec(statement):
        print(f"{dept.name}: {staff.personal} {staff.family}")
```
![image](https://github.com/patrycjaprzybysz/SQLite/assets/100605325/fd4767e7-444c-4c80-8810-908ea7f1c559)

