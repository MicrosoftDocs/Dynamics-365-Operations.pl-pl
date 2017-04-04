---
title: "Autoryzować skorygowana Prognoza"
description: "Nie wszystkie prognozy muszą być autoryzowane natychmiast. W tym artykule wyjaśniono, jak można określić okres, dla którego prognoza jest autoryzowana. Opisano również, jak można autoryzować prognozę dla konkretnych firm i modeli prognozy."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: ReqDemPlanImportForecastDialog
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 72734
ms.assetid: cb8fd809-605a-4a8b-a390-636edfec21f9
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: f151f4b4290df0b2bf1b5d1159654bd248a439b1
ms.lasthandoff: 03/31/2017


---

# <a name="authorize-an-adjusted-forecast"></a>Autoryzować skorygowana Prognoza

Nie wszystkie prognozy muszą być autoryzowane natychmiast. W tym artykule wyjaśniono, jak można określić okres, dla którego prognoza jest autoryzowana. Opisano również, jak można autoryzować prognozę dla konkretnych firm i modeli prognozy.

Nie wszystkie prognozy muszą być autoryzowane natychmiast. Można określić daty rozpoczęcia i zakończenia okresu, dla którego prognoza jest autoryzowana. Ta funkcja umożliwia zamrożenie określonych przedziałów. 

Daty rozpoczęcia i zakończenia, które określisz musi odpowiadać daty rozpoczęcia i zakończenia łańcucha wygenerowanych w prognozie. System wymusza ograniczenie to i automatycznie dostosowuje daty, jeśli konieczne jest dostosowanie. 

Na karcie **Szczegóły** na stronie **Autoryzacja** można wyświetlić szczegółowe informacje o ostatnio wygenerowanej prognozie. 

Można wybrać firmy i modele prognozy do autoryzacji prognozy w celu jej użycia. Domyślnie siatka zawiera wszystkie firmy, dla których utworzono prognozę popytu. Dla każdej firmy model prognozy odpowiadający aktualnemu planowi prognozy skonfigurowanemu w parametrach planowania głównego jest wstępnie wypełniany. Można też zmienić ten model prognozy na dowolny inny model prognozy należący do danej firmy. Jeśli dla danej firmy nie ma wygenerowanych danych prognozy, podczas importowania wyświetli się ostrzeżenie. 

Bardzo ważne jest, aby zrozumieć, jak działa pole wyboru **Zapisz korekty ręczne podstawowej prognozy popytu**. Jeżeli dokonano ręcznego dopasowania do linii bazowej statystycznej prognozy, skorygowane wartości są upoważnione do użytku, nawet jeśli to pole wyboru jest wyczyszczone. Zmiany zostaną jednak odrzucone po autoryzacji. Dlatego przy następnym wygenerowaniu prognozy jest ona jedynie danymi statycznymi i nie zawiera żadnych zmian wprowadzonych ręcznie, nawet jeśli opcja **Przenieś ręczne korekty prognozy popytu** jest zaznaczona. Dlatego pole wyboru **Zapisz korekty ręczne podstawowej prognozy popytu** należy traktować jako sposób odrzucania wszystkich zmian wprowadzonych ręcznie.

<a name="see-also"></a>Informacje dodatkowe
--------

[Making manual adjustments to the baseline forecast](manual-adjustments-baseline-forecast.md)

[Monitoring forecast accuracy](monitor-forecast-accuracy.md)


