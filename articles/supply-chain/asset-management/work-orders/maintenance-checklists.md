---
title: Listy kontrolne konserwacji
description: W tym temacie opisano listy kontrolne konserwacji w module Zarządzanie składnikami majątku.
author: josaw1
manager: AnnBe
ms.date: 08/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-15
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 325ff1fa0811d6aac5189cc69f21483fce6b3e8f
ms.sourcegitcommit: f5bfa3212bc3ef7d944a358ef08fe8863fd93b91
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/16/2019
ms.locfileid: "1875846"
---
# <a name="maintenance-checklists"></a>Listy kontrolne konserwacji


[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

Listy kontrolne konserwacji służą do ustawiania typów zadań konserwacji i używane podczas pracy z zleceniem pracy. Wypełnianie list kontrolnych konserwacji jest częścią ukończenia zlecenia produkcyjnego. Aby uzyskać więcej informacji zobacz sekcję [Kategorie typów zadań obsługi i typy zadań serwisowych, warianty typu zadań obsługi, handel zadaniami konserwacyjnymi oraz listy kontrolne konserwacji](../setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md), aby dowiedzieć się więcej o tym jak rozpocząć listy kontrolne konserwacji na typach zadań konserwacji w formularzu **Ustawienia domyślne typu zadania konserwacji**

Podczas pracy z listami kontrolnymi na zleceniu pracy można wypełnić wstępnie zdefiniowane listy kontrolne konserwacji, które są związane z typami zadań konserwacji. Można również dodać dodatkowe listy kontrolne konserwacji.

## <a name="fill-out-a-maintenance-checklist"></a>Wypełnij listę kontrolną konserwacji

1. Kliknij **Zarządzanie składnikami majątku** > **Wspólne** > **Zlecenia pracy** > **Wszystkie zlecenia pracy** lub **Aktywne zlecenia pracy**.

2. Wybierz zlecenie pracy z listy i kliknij przycisk **Lista kontrolna konserwowanego składnika majątku**.

3. Na **Lista kontrolna konserwowanego składnika majątku zadania zlecenia pracy** są wyświetlane listy kontrolne obsługi wszystkich zadań związanych z zleceniem pracy. Jeśli zadania zlecenia produkcyjnego mają różne typy zadań obsługi, listy kontrolne konserwacji mogą się różnić w poszczególnych zadaniach zlecenia Wybierz zadanie zlecenia pracy, które ma być używane z pokrewną listą kontrolną obsługi technicznej. Szczegóły wybranego wiersza listy prac są wyświetlane w skróconej karcie **Szczegóły wiersza**.

4. Wypełnij wszystkie wiersze listy prac, pojedynczo, w kolejności, w jakiej są pokazywane. Wiersz listy kontrolnej obsługi typu „nagłówek” jest używany jako nagłówek do grupowania poniższych wierszy listy czynności konserwacyjnych. Nie jest wymagane wypełnianie nagłówka, ale podobnie jak we wszystkich typach wierszy listy kontrolnej obsługi, można dodać **notatkę** do nagłówka

5. Jeśli instrukcje są powiązane z wierszem listy kontrolnej obsługi, jest zaznaczone pole wyboru **instrukcje,**. Przeczytaj instrukcje dotyczące wybranego wiersza listy kontrolnej obsługi w skróconej karcie **Szczegóły wiersza** > sekcja **Instrukcje**.

6. Informacje wymagane do wykonania wiersza listy kontrolnej dotyczącego obsługi mogą się różnić w zależności od typu listy kontrolnej obsługi. Wiersz listy kontrolnej eksploatacji można wypełnić, wypełniając pola w skróconej karcie **Szczegóły wiersza**. Na przykład w wierszu typu „tekst” należy dodać **notatkę** opisującą wynik tego wiersza listy kontrolnej. W wierszu typu „miara” należy dodać **wartość licznika** przeczytaną na sprzęcie, a w razie potrzeby można również dodać **notatkę**.

- Po zakończeniu wiersza listy kontroli eksploatacji zaznacz pole wyboru **zaznaczone** w wierszu, aby je oznaczyć jako zakończone. Aby odrzucić wiersz listy kontrolnej obsługi, ponieważ nie jest on odpowiedni dla zadania zlecenia, zaznacz pole wyboru **N/D** w wierszu. Jeśli wiersz listy kontrolnej obsługi jest oznaczony jako **obowiązkowy**, należy go oznaczyć jako „zaznaczone” lub „N/D”.  
- Rejestracje listy kontrolnej obsługi można aktualizować tylko wtedy, gdy zlecenie produkcyjne jest w stanie cyklu życia: [Aktywne](../setup-for-work-orders/work-order-lifecycle-states.md).  


## <a name="add-a-maintenance-checklist-line"></a>Dodaj wiersze listy kontrolnej konserwowanego składnika majątku

Listy kontrolne konserwacji są tworzone na podstawie definicji zadania obsługi typu domyślnego i przenoszonego do zadania zlecenia. W razie potrzeby można dodać wiersze listy prac do zadania zlecenia. Ręcznie dodane wiersze listy kontrolnej obsługi pobierają odwołanie „ręczne”.

1. Na **Lista kontrolna konserwowanego składnika majątku zadania zlecenia pracy** wybierz zlecenie pracy, dla którego chcesz dodać listę kontrolną.

2. W wierszach skróconej karty **Wiersze listy kontrolnej konserwowanego składnika majątku** wybierz wiersz listy kontrolnej konserwacji i naciśnij przycisk strzałki w dół na klawiaturze, jeśli chcesz wstawić nowy wiersz po wybranym wierszu listy prac konserwacyjnych. Ten numer jest generowany automatycznie na podstawie sekwencji numerów zdefiniowanej w polu **Numer wiersza** . Można również wybrać wiersz listy prac i kliknąć przycisk **Dodaj wiersz**, jeśli nowy wiersz ma zostać wstawiony powyżej wybranego wiersza listy czynności konserwacyjnych.

3. Wstaw nazwę lokalizacji listy kontrolną konserwowanego składnika majątku w polu **Nazwa**.

4. W polu **Typ** wybierz typ wiersza listy kontrolnej konserwacji. Dla każdej listy kontrolną konserwowanego składnika majątku pola powiązane są wyświetlane w skróconej karcie **Szczegóły wiersza**.  
  a. „Tekst” służy do dodawania wiersza listy kontrolnej obsługi z tekstem opisu elementu do wykonania. Ten typ listy kontrolnej obsługi może być używany, jeśli pracownik ma sprawdzać lub sprawdzać coś, bez oczekiwania określonego (mierzalnego) wyniku. Wstaw opis czynności, które należy wykonać , w sekcji **instrukcje** w skróconej karcie **szczegóły wiersza**. b. Nagłówek służy do grupowania wierszy listy czynności, które są widoczne poniżej nagłówka. Jest to przydatne w przypadku kilku wierszy listy kontrolnej obsługi, które można podzielić na określone obszary. Wpisz nazwę opisową w polu **Nazwa**.  
  c. „Szablon” nie ma stosowania, jeśli wiersz listy kontrolnej obsługi został dodany ręcznie w zadaniu zlecenia produkcyjnego.  
  dz. „Zmienna” służy do definiowania możliwego wyniku w zakresie w wierszu listy kontrolnej obsługi. Zarządzanie wariantami w listach kontrolnych konserwowanych składników majątku jest opisane w [Kategorie typów zadań obsługi i typy zadań serwisowych, warianty typu zadań obsługi, handel zadaniami konserwacyjnymi oraz listy kontrolne konserwacji](../setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md). Wstaw nazwę opisującą wariant w polu **Nazwa**. Zaznacz typ zmiennej w polu **Zmienna**. Wstaw opis czynności, które należy wykonać , w sekcji **instrukcje** w skróconej karcie **szczegóły wiersza**.  
  e. „Miara” jest używana do rejestrowania konkretnej miary. Wstaw nazwę miary w polu **Nazwa**. W skróconej karcie **szczegóływiersza** wybierz opcję **licznik** i **jednostka**. Wstaw opis czynności, które należy wykonać, w sekcji **instrukcje**.  

5. Po zakończeniu ręcznego dodawania wierszy listy prac należy wypełnić wiersze w sposób opisany w sekcji powyżej.

>[!NOTE]
>W obszarze **Lista kontrolna konserwowanego składnika majątku zadania zlecenia pracy** nie można usuwać wierszy listy prac z odwołaniem „typ zadania”. Wiersze listy kontrolnej obsługi można usunąć tylko z odwołaniem „ręczna”, które zostało utworzone ręcznie lub przez innych pracowników obsługi technicznej


![Rysunek 1](media/14-work-orders.png)

