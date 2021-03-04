---
title: Autoryzowanie skorygowanej prognozy
description: Nie wszystkie prognozy muszą być autoryzowane natychmiast. W tym artykule wyjaśniono, jak można określić okres, dla którego prognoza jest autoryzowana. Opisano również, jak można autoryzować prognozę dla konkretnych firm i modeli prognozy.
author: roxanadiaconu
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqDemPlanImportForecastDialog
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 72734
ms.assetid: cb8fd809-605a-4a8b-a390-636edfec21f9
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5b599385f4bc79707ac7b6b814dd106813cbf3c9
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4435471"
---
# <a name="authorize-an-adjusted-forecast"></a>Autoryzowanie skorygowanej prognozy

[!include [banner](../includes/banner.md)]

Nie wszystkie prognozy muszą być autoryzowane natychmiast. W tym artykule wyjaśniono, jak można określić okres, dla którego prognoza jest autoryzowana. Opisano również, jak można autoryzować prognozę dla konkretnych firm i modeli prognozy.

Nie wszystkie prognozy muszą być autoryzowane natychmiast. Można określić daty rozpoczęcia i zakończenia okresu, dla którego prognoza jest autoryzowana. Ta funkcja umożliwia zamrożenie określonych przedziałów. 

Określone daty rozpoczęcia i zakończenia muszą odpowiadać datom rozpoczęcia i zakończenia przedziału, w którym powstała prognoza. System wymusza to ograniczenie i w razie potrzeby automatycznie koryguje daty. 

Na karcie **Szczegóły** na stronie **Autoryzacja** można wyświetlić szczegółowe informacje o ostatnio wygenerowanej prognozie. 

Można wybrać firmy i modele prognozy do autoryzacji prognozy w celu jej użycia. Domyślnie siatka zawiera wszystkie firmy, dla których utworzono prognozę popytu. Dla każdej firmy model prognozy odpowiadający aktualnemu planowi prognozy skonfigurowanemu w parametrach planowania głównego jest wstępnie wypełniany. Można też zmienić ten model prognozy na dowolny inny model prognozy należący do danej firmy. Jeśli dla danej firmy nie ma wygenerowanych danych prognozy, podczas importowania wyświetli się ostrzeżenie. 

Bardzo ważne jest, aby zrozumieć, jak działa pole wyboru **Zapisz korekty ręczne podstawowej prognozy popytu**. Wprowadzenie ręcznych zmian w bazowej prognozie popytu sprawia, że skorygowane wartości są autoryzowane do użycia, nawet wtedy, gdy to pole wyboru nie jest zaznaczone. Zmiany zostaną jednak odrzucone po autoryzacji. Dlatego przy następnym wygenerowaniu prognozy jest ona jedynie danymi statycznymi i nie zawiera żadnych zmian wprowadzonych ręcznie, nawet jeśli opcja **Przenieś ręczne korekty prognozy popytu** jest zaznaczona. Dlatego pole wyboru **Zapisz korekty ręczne podstawowej prognozy popytu** należy traktować jako sposób odrzucania wszystkich zmian wprowadzonych ręcznie.

<a name="additional-resources"></a>Dodatkowe zasoby
--------

[Wprowadzanie ręcznych korekt prognozy bazowej](manual-adjustments-baseline-forecast.md)

[Monitorowanie dokładności prognozy](monitor-forecast-accuracy.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]