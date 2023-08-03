# COVID-DATA-EXPLORATION-
-- Within the data exploration of Covid, We are going to be using these queries to visualize our data For Tableau. 

## Table 1: Global Number

Select SUM(new_cases) as TC , SUM(CAST(new_deaths as INT64)) as TD, SUM(CAST(new_deaths as INT64))/SUM(total_cases) *100 as DeathPercentage

FROM `project-000-392922.CDD.covid_data_death`

Where total_cases is not null AND total_deaths is not null 

## Table 2: Total Death Per Country 

Select location, SUM(new_deaths) as TotalDeathCount

FROM `project-000-392922.CDD.covid_data_death`

WHERE continent is null

 AND location not in ('World', 'European Union', 'High income', 'Upper middle income', 'Lower middle income', 'Low income')
 
Group By location 

ORDER BY TotalDeathCount DESC 

## Table 3: Percent of Population Infected 

SELECT location, population, MAX(total_cases) AS HighestInfectionCount, MAX((total_cases/population))*100 as PercentPopulationInfected

FROM `project-000-392922.CDD.covid_data_death`

WHERE location not in ('High income','Upper middle income','Lower middle income','Low income')

GROUP BY location, population

ORDER BY PercentPopulationInfected DESC 


## Table 4: Percent of Population Infected Per Country 

SELECT location, population, date, MAX(total_cases) AS HighestInfectionCount, MAX((total_cases/population))*100 as PercentPopulationInfected

FROM `project-000-392922.CDD.covid_data_death`

WHERE location not in ('High income','Upper middle income','Lower middle income','Low income')

GROUP BY location, population, date

ORDER BY PercentPopulationInfected DESC 
