1. Selezionare tutti gli studenti iscritti al Corso di Laurea in Economia

SELECT `students`.`name`, `students`.`surname`, `students`.`date_of_birth`,`students`.`email`, `degrees`.`name`
FROM `students`
JOIN `degrees`
ON `degrees`.`id`= `students`.`degree_id`
WHERE `degrees`.`name`= 'Corso di Laurea in Economia';

2. Selezionare tutti i Corsi di Laurea Magistrale del Dipartimento di
Neuroscienze

SELECT `departments`.`name`, `departments`.`email`, `degrees`.`name`,`degrees`.`level`
FROM `departments`
JOIN `degrees`
ON `degrees`.`department_id` = `departments`.`id`
WHERE `departments`.`name`= 'Dipartimento di Neuroscienze' AND `degrees`.`name`LIKE '%Corso di Laurea Magistrale%';

3. Selezionare tutti i corsi in cui insegna Fulvio Amato (id=44)

SELECT  `teachers`.`name`, `teachers`.`surname`,`courses`.`name`
FROM `courses`
JOIN `course_teacher`
ON `course_teacher`.`course_id` = `courses`.`id`
JOIN `teachers`
ON `course_teacher`.`teacher_id` = `teachers`.`id`
WHERE `teachers`.`id` = 44;

4. Selezionare tutti gli studenti con i dati relativi al corso di laurea a cui
sono iscritti e il relativo dipartimento, in ordine alfabetico per cognome e
nome
5. Selezionare tutti i corsi di laurea con i relativi corsi e insegnanti
6. Selezionare tutti i docenti che insegnano nel Dipartimento di
Matematica (54)
7. BONUS: Selezionare per ogni studente il numero di tentativi sostenuti
per ogni esame, stampando anche il voto massimo. Successivamente,
filtrare i tentativi con voto minimo 18.