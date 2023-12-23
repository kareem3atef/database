# Design Document


## Scope

* it helps Doctors for tracking the medical record for the patients
* when the `patient` have a `claim` he goes to the `hospital` and get checked by a `doctor` then the doctor `diagnose` him and describ some `drugs` to him
* 

## Functional Requirements

* CRUD operations for all the entites in the database

## Representation


### Entities
The database includes the following entities:

#### patient

the `patients` table includes
* `id` integer , autoincremental , and the primary key of the table
* `notional_id` 
* `fisrt_name` can not be null
* `second_name`
* `third_name`
* `fourth_name`
* `age`
* `date_birth`
* `gender` (m ,f)
* `birth_place`
* `residency`
* `job`
* `somker` (y , n)
* `alcoholic` (y , n)
* `nationality`
* `religion`
* `fnm_relativity` (y , n)

#### past_history

the `past` table includes
* `id` primary key , auto incremental
* `patient_id` foreign key references to the patient
* `type` IN (نقل دم ، عملية ، أدوية مزمنة ، حساسية)
* `description`


#### chronic disease

the `chronic_diseases` table includes
* `id` integer , autoincremental and the primary key of the table
* `name`

#### drugs
the `drugs` table includes
* `id` primary key
* `name`


#### claim

the `claims` table includes
* `id` integer , autoincremental and the primary key of the table
* `patient_id` foreign key references to the patints who claims
* `name` can not be null
* `start_date`
* `type`
* `amount`


#### doctor
the `doctors` table includes 
* `id` integer , primary key
* `national id`
* `first_name`
* `last_name`
* `role`
* `date_of_birth`
* `age`




### Relationships




## Optimizations

indexes are created on the `songs name` and `artists name` and `albums name` to speed the retrieval of them

view created to
* aggregate the likes of songs , albums `likes_songs` , `likes_albums` , `playlists`
* simplify the relation between the artist and the song `songs_artist`
* partitioning the songs by the year
 --on creating haha--


## Limitations

* the schema assume that the songs inserted are not heavy operation beacuse of the index
