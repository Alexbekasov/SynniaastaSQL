# SynniaastaSQL

-- Distinct - naitab ainult 1 kordus
Select distinct synniaasta
from laps
where synniaasta>2000;
--Between
-- lapsed mis on sündinud (2000-2005)
Select nimi, synniaasta
From laps
where synniaasta >= 2000 AND synniaasta <= 2005

Select nimi, synniaasta
From laps
where synniaasta between 2000 AND synniaasta 2005
--LIKE
-- naita lapsed, kelle nimi algab A tähega
-- % kõik võimalikud sümboolid
-- sisaldab A täht - '%A%'
Select nimi
from laps
where nimi like 'A%';
-- Täpsem määratud tähtede arv _
Select nimi
from laps
where nimi like '_a__'; -- Example: Sash (because there's 4 _)
--AND/OR
Select nimi, synnilinn
from laps
where nimi like 'A%'
OR synnilinn like 'Tartu';

Select nimi, synnilinn
from laps
where nimi like 'A%'
AND synnilinn like 'Tartu';

--Agregaatfunktsioonid
SUM, AVG, MIN, MAX, COUNT
Select Count(nimi) As 'laste Arv' -- 'laste Arv' stobi bylo s probelom (objazatelno '') lasteArv slitno
From laps;

Select Avg(pikkus) As 'keskmine pikkus'
From laps;
where synnilinn='Tallinn';

--näita keskmine pikkus linnade järgi
-- Group by
Select Avg(pikkus) As 'keskmine pikkus', synnilinn
From laps;
Group by synnilinn;
