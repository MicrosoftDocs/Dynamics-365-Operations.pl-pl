---
title: Autoryzowanie skorygowanej prognozy
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
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: 7ff7891e9a12be75b9171a23f0a9288b3c723730
ms.contentlocale: pl-pl
ms.lasthandoff: 04/25/2017


---

# <a name="authorize-an-adjusted-forecast"></a>Autoryzowanie skorygowanej prognozy

[!include[banner](../includes/banner.md)]


Nie wszystkie prognozy muszą być autoryzowane natychmiast. W tym artykule wyjaśniono, jak można określić okres, dla którego prognoza jest autoryzowana. Opisano również, jak można autoryzować prognozę dla konkretnych firm i modeli prognozy.

Nie wszystkie prognozy muszą być autoryzowane natychmiast. Można określić daty rozpoczęcia i zakończenia okresu, dla którego prognoza jest autoryzowana. Ta funkcja umożliwia zamrożenie określonych przedziałów. 

Określone daty rozpoczęcia i zakończenia muszą odpowiadać datom rozpoczęcia i zakończenia przedziału, w którym powstała prognoza. System wymusza to ograniczenie i w razie potrzeby automatycznie koryguje daty. 

Na karcie **Szczegóły** na stronie **Autoryzacja** można wyświetlić szczegółowe informacje o ostatnio wygenerowanej prognozie. 

Można wybrać firmy i modele prognozy do autoryzacji prognozy w celu jej użycia. Domyślnie siatka zawiera wszystkie firmy, dla których utworzono prognozę popytu. Dla każdej firmy model prognozy odpowiadający aktualnemu planowi prognozy skonfigurowanemu w parametrach planowania głównego jest wstępnie wypełniany. Można też zmienić ten model prognozy na dowolny inny model prognozy należący do danej firmy. Jeśli dla danej firmy nie ma wygenerowanych danych prognozy, podczas importowania wyświetli się ostrzeżenie. 

Bardzo ważne jest, aby zrozumieć, jak działa pole wyboru **Zapisz korekty ręczne podstawowej prognozy popytu**. Wprowadzenie ręcznych zmian w bazowej prognozie popytu sprawia, że skorygowane wartości są autoryzowane do użycia, nawet wtedy, gdy to pole wyboru nie jest zaznaczone. Zmiany zostaną jednak odrzucone po autoryzacji. Dlatego przy następnym wygenerowaniu prognozy jest ona jedynie danymi statycznymi i nie zawiera żadnych zmian wprowadzonych ręcznie, nawet jeśli opcja **Przenieś ręczne korekty prognozy popytu** jest zaznaczona. Dlatego pole wyboru **Zapisz korekty ręczne podstawowej prognozy popytu** należy traktować jako sposób odrzucania wszystkich zmian wprowadzonych ręcznie.

<a name="see-also"></a>Informacje dodatkowe
--------

[Wprowadzanie ręcznych korekt prognozy bazowej](manual-adjustments-baseline-forecast.md)

[Monitorowanie dokładności prognozy](monitor-forecast-accuracy.md)




