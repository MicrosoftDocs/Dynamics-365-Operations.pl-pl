---
title: Listy kontrolne konserwacji
description: W tym artykule opisano listy kontrolne konserwacji w module Zarządzanie składnikami majątku.
author: johanhoffmann
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetWorkOrderChecklist, EntAssetMobileWorkOrderLineChecklistDetails
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 25e9139ce57283482d8da4b7f1e5d6275c74ad28
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8854537"
---
# <a name="maintenance-checklists"></a>Listy kontrolne konserwacji

[!include [banner](../../includes/banner.md)]



Lista kontrolna konserwowanego składnika majątku jest konfigurowana w obrębie typów zadań konserwacji. Listy kontrolne konserwowanego składnika majątku są wypełniane w ramach procesu ukończenia zlecenia produkcyjnego. Aby uzyskać więcej informacji o tym, jak skonfigurować listy kontrolne konserwowanego składnika majątku w obrębie typów zadań konserwacji na stronie **Ustawienia domyślne typu zadania konserwacji**, zobacz [Kategorie typów zadań obsługi i typy zadań serwisowych, warianty typu zadań obsługi, zawody zadań konserwacji oraz listy kontrolne konserwacji](../setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md).

Podczas pracy z listami kontrolnymi konserwowanych składników majątku na zleceniu pracy można wypełnić wstępnie zdefiniowane listy kontrolne, które są związane z typami zadań konserwacji. Można również dodać więcej list kontrolnych konserwowanych składników majątku.


## <a name="fill-in-a-maintenance-checklist"></a>Wypełnianie listy kontrolnej konserwowanego składnika majątku

1. Kliknij **Zarządzanie składnikami majątku** > **Wspólne** > **Zlecenia pracy** > **Wszystkie zlecenia pracy** lub **Aktywne zlecenia pracy**.

2. Wybierz zlecenie produkcyjne, a następnie w okienku akcji na karcie **Zlecenie pracy**, w grupie **Wiersze** wybierz pozycję **Lista kontrolna konserwowanego składnika majątku**.

3. Strona **Lista kontrolna konserwowanego składnika majątku zadania zlecenia pracy** są wyświetlane listy kontrolne wszystkich zadań związanych z zleceniem pracy. Jeśli zadania zlecenia pracy mają różne typy zadań konserwacji, listy kontrolne konserwowanego składnika majątku mogą się różnić w poszczególnych zadaniach zlecenia pracy. Wybierz zadanie zlecenia pracy, które ma być używane z pokrewną listą kontrolną obsługi technicznej. Szczegóły wybranego wiersza listy kontrolnej konserwowanego składnika majątku są wyświetlane na skróconej karcie **Szczegóły wiersza**.

4. Wypełnij wszystkie wiersze listy kontrolnej konserwowanego składnika majątku, pojedynczo, w kolejności, w jakiej są wyświetlane. Wiersz listy kontrolnej konserwowanego składnika majątku można wypełnić, wypełniając pola na skróconej karcie **Szczegóły wiersza**. Informacje wymagane do wypełnienia wiersza mogą się różnić w zależności od jego typu. Na przykład w wierszu typu **Tekst** jest dodawana notatka opisującą wynik kontroli. W wierszu typu **Miara** jest wprowadzana wartość licznika odczytana na sprzęcie, a w razie potrzeby można również dodać notatkę. Wiersz listy kontrolnej konserwowanego składnika majątku typu **Nagłówek** jest używany jako nagłówek do grupowania wierszy listy kontrolnej konserwowanego składnika majątku wyświetlanych pod nagłówkiem. Nagłówka nie trzeba wypełniać. Podobnie jak w przypadku wszystkich innych typów wierszy listy kontrolnej konserwowanego składnika majątku do wiersza typu **Nagłówek** można dodać notatkę.

5. Jeśli instrukcje są powiązane z wierszem listy kontrolnej obsługi, jest zaznaczone pole wyboru **instrukcje,**. Przeczytaj instrukcje dotyczące wybranego wiersza listy kontrolnej konserwowanego składnika majątku w polu **Instrukcje** na skróconej karcie **Szczegóły wiersza**.

6. Po zakończeniu wiersza listy kontrolnej konserwowanego składnika majątku zaznacz pole wyboru **Sprawdzono** w tym wierszu, aby oznaczyć go jako zakończony. Aby odrzucić wiersz listy kontrolnej konserwowanego składnika majątku, ponieważ nie jest on odpowiedni dla zadania zlecenia pracy, zaznacz pole wyboru **N/D** w wierszu. Jeśli pole wyboru **Wymagany** zostało zaznaczone w wierszu listy kontrolnej konserwowanego składnika majątku, należy zaznaczyć pole wyboru **Sprawdzono** lub pole wyboru **N/D**.

>[!NOTE]
>Rejestracje listy kontrolnej obsługi można aktualizować tylko wtedy, gdy zlecenie produkcyjne jest w stanie cyklu życia: [Aktywne](../setup-for-work-orders/work-order-lifecycle-states.md).  


## <a name="add-a-maintenance-checklist-line"></a>Dodaj wiersze listy kontrolnej konserwowanego składnika majątku

Listy kontrolne konserwowanego składnika majątku są tworzone na podstawie definicji domyślnego typu zadania konserwacji i przenoszone do zadania zlecenia pracy. W razie potrzeby można dodać wiersze listy kontrolnej konserwowanego składnika majątku do zadania zlecenia pracy. Wiersze listy kontrolnej konserwowanego składnika majątku, które dodajesz ręcznie, otrzymują oznaczenie **Ręczne**.

1. Na stronie **Lista kontrolna konserwowanego składnika majątku zadania zlecenia pracy** wybierz zadanie zlecenia pracy, dla którego chcesz dodać taką listę kontrolną.

2. Na skróconej karcie **Wiersze listy kontrolnej konserwowanego składnika majątku** wybierz wiersz listy. Następnie — aby wstawić nowy wiersz po wybranym wierszu — naciśnij klawisz ze **strzałką w dół**. Kolejny numer w sekwencji jest automatycznie wprowadzany w polu **Numer wiersza**. Aby wstawić nowy wiersz przed wybranym wierszem, wybierz pozycję **Dodaj wiersz**. 

3. W polu **Nazwa** wprowadź nazwę listy kontrolnej konserwowanego składnika majątku.

4. W polu **Typ** wybierz typ wiersza listy kontrolnej konserwacji. Skrócona karta **Szczegóły wiersza** zawiera powiązane pola dla każdego typu listy kontrolnej konserwowanego składnika majątku.
    - **Tekst** — ten typ służy do dodawania wiersza listy kontrolnej konserwowanego składnika majątku z tekstem opisującym zadanie do wykonania. Można na przykład użyć tego typu, jeśli pracownik chce coś sprawdzić lub zbadać, ale nie oczekujesz określonego (mierzalnego) wyniku. Po wybraniu tego typu wprowadź tekst opisujący zadanie do wykonania na skróconej karcie **Szczegóły wiersza** w polu **Instrukcje**.
    - **Nagłówek** — wiersz listy kontrolnej konserwowanego składnika majątku tego typu jest używany jako nagłówek do grupowania wierszy listy kontrolnej konserwowanego składnika majątku wyświetlanych pod nim. ten typ jest przydatny w przypadku kilku wierszy listy kontrolnej obsługi, które można podzielić na określone obszary. Po wybraniu tego typu w polu **Nazwa** wprowadź opisową nazwę.
    - **Szablon** — ten typ nie ma zastosowania, jeśli ręcznie dodajesz wiersz listy kontrolnej konserwowanego składnika majątku w zadaniu zlecenia pracy.  
    - **Zmienna** — ten typ służy do definiowania możliwego wyniku w zakresie w wierszu listy kontrolnej konserwowanego składnika majątku. Informacje na temat konfigurowania zmiennych na listach kontrolnych konserwowanych składników majątku można znaleźć w temacie [Kategorie typów zadań obsługi i typy zadań serwisowych, warianty typu zadań obsługi, zawody zadań konserwacyjnych oraz listy kontrolne konserwacji](../setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md). Po wybraniu tego typu w polu **Nazwa** wprowadź nazwę opisującą zmienną. Na skróconej karcie **Szczegóły wiersza** w polu **Zmienna** wybierz zmienną. W polu **Instrukcje** wprowadź tekst opisujący czynności do wykonania.
    - **Miara** — ten typ służy do rejestrowania określonej miary w wierszu listy kontrolnej konserwowanego składnika majątku. Po wybraniu tego typu w polu **Nazwa** wprowadź nazwę miary. Na skróconej karcie **Szczegóły wiersza** w polach **Licznik** i **Jednostka** wybierz odpowiednie wartości. W polu **Instrukcje** wprowadź tekst opisujący czynności do wykonania.

5. Po zakończeniu ręcznego dodawania wierszy listy kontrolnej konserwowanego składnika majątku wypełnij wiersze w powyższej sekcji **Wypełnianie listy kontrolnej konserwowanego składnika majątku**.

>[!NOTE]
>Na stronie **Lista kontrolna konserwowanego składnika majątku zadania zlecenia pracy** nie można usuwać wierszy listy kontrolnej konserwowanego składnika majątku z oznaczeniem **Typ zadania**. Można usuwać tylko wiersze listy kontrolnej konserwowanego składnika majątku, które zostały utworzone ręcznie przez Ciebie lub innych konserwatorów i które mają oznaczenie **Ręczne**.

Na poniższej ilustracji pokazano przykład listy kontrolnej konserwowanego składnika majątku.

![Rysunek 1.](media/14-work-orders.png)



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]