---
title: Działania w ramach przerwy konserwacyjnej
description: Ten temat wyjaśnia, jak przestoje prac konserwacyjnych służą do uzyskiwania przeglądu zdolności produkcyjnych wymaganych do wykonania zadań konserwacyjnych dotyczących konkretnych składników majątku w danym okresie.
author: josaw1
manager: tfehr
ms.date: 08/27/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 2f864e7fe0129f8487cddadc99b32f75a2b6d9ca
ms.sourcegitcommit: 5bb36b74935ffe140367fd6ecf956b4857ad12e5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/14/2020
ms.locfileid: "3802828"
---
# <a name="maintenance-downtime-activities"></a>Działania w ramach przerwy konserwacyjnej

[!include [banner](../../includes/banner.md)]

Przestoje prac konserwacyjnych służą do uzyskiwania przeglądu zdolności produkcyjnych wymaganych do wykonania zadań konserwacyjnych dotyczących konkretnych składników majątku w danym okresie. Można na przykład utworzyć rejestrację przestojów dla wiersza produkcji 10 w korytarzu produkcji 29-A w oddziale produkcyjnym 02. Rejestracja przestojów konserwacyjnych ma godzinę rozpoczęcia i zakończenia, wskazującą okres, w którym składniki majątku związane z zatrzymaniem konserwacji są niedostępne do produkcji.

**Działania związane z przerwami konserwacyjnymi** pracą to przegląd wierszy harmonogramu konserwacji i zadań obsługi zleceń pracy dotyczących powiązanych składników majątku w podanym okresie. Wiersze powiązane z zadaniami konserwacyjnymi zlecenia pracy mają oczekiwaną datę rozpoczęcia w okresie zatrzymania konserwacji. Można wyodrębnić użyteczne informacje i dostosować do planowanych zadań konserwacji:

- Umożliwia uzyskanie przeglądu wymaganych okresów zamknięcia urządzeń produkcyjnych (składników majątku).  
- Umożliwia uzyskanie przeglądu planowanej konserwacji (godzin), pogrupowanych według kompetencji (grup pracowników obsługi technicznej lub pracowników obsługi technicznej), na przykład obciążenia zdolności produkcyjnych w odniesieniu do elektryków, kowali lub innych grup prac konserwacyjnych wymaganych do przeprowadzenia planowanej konserwacji.  
- Umożliwia wprowadzanie korekt do wierszy harmonogramu konserwacji lub zadań obsługi zleceń pracy związanych z składnikami majątku, na przykład zmiana oczekiwanych godzin rozpoczęcia i zakończenia w wierszu, a także wybranie innych konserwatorów w celu zoptymalizowania przepływu pracy dla konserwatorów i grup konserwatorów.

Po wybraniu składników majątku w rejestracji czasu przestoju, wszystkie otwarte wiersze harmonogramu konserwacji i zadania obsługi zleceń pracy związane z aktywnymi zleceniami pracy są uwzględniane w rejestracji przestojów serwisowych.

## <a name="maintenance-downtime-activities"></a>Działania w ramach przerwy konserwacyjnej

Kliknij **Zarządzanie składnikami majątku** > **Wspólne** > **Działania w ramach przerwy konserwacyjnej** > **Wszystkie działania w ramach przerwy konserwacyjnej**, aby otworzyć listę wszystkich działań związanych z przestojami serwisowych i zobaczyć niektóre informacje dotyczące działań. Kliknij łącze w kolumnie **Działania w ramach przerwy konserwacyjnej**, aby otworzyć widok szczegółów. Na poniższej ilustracji pokazano przykład strony listy **Działania w ramach przerwy konserwacyjnej**.

![Rysunek 1](media/19-preventive-maintenance.png)


## <a name="create-a-maintenance-downtime-activity"></a>Tworzenie działania w ramach przerwy konserwacyjnej

1. Kliknij **Zarządzanie składnikami majątku** > **Wspólne** > **Działania w ramach przerwy konserwacyjnej** > **Wszystkie działania w ramach przerwy konserwacyjnej** lub **Aktywne działania w ramach przerwy konserwacyjnej**.

2. Kliknij przycisk **Nowy**.

3. Wstaw Identyfikator w polu **Działania w ramach przerwy konserwacyjnej** oraz nazwę w polu **Nazwa**.

4. Wstaw okres zatrzymania obsługi w polach **Data/godzina rozpoczęcia** i **Data/godzina zakończenia**.

5. W skróconej karcie **Składniki majątku działań w ramach przerwy konserwacyjnej** > kliknij przycisk **Dodaj wiersz**, aby dodać wszystkie składniki majatku, pojedynczo, do działania dotyczącego przestoju w czasie konserwacji.

6. Kliknij **Zapisz** po dodaniu wszystkich składników. Poniższa ilustracja przedstawia przykład działania w ramach przerwy konserwacyjnej i związanych z nim zadań konserwacyjnych.

7. Zadania obsługi zleceń i otwarte wiersze harmonogramu konserwacji związane z wybranymi środkami są wyświetlane na **Wynikowe zadania konserwacyjne zleceń pracy** i kartach skróconych **Wiersze harmonogramu konserwacji**. Na skróconej karcie **Ogólne** > grupa **Zlecenia pracy** > pole **Godziny prognozy konserwacji** i skrócona karta **Ogólne** > grupa **Harmonogram konserwacji** > pole **Godziny prognozy konserwacji**, wyświetlana łączna liczba godzin prognozowanych zadań obsługi zleceń i wierszy harmonogramu konserwacji.

Na poniższej ilustracji pokazano przykład widoku szczegółów **Działania w ramach przerwy konserwacyjnej**.

![Rysunek 2](media/20-preventive-maintenance.png)

>[!NOTE]
>Wiersze zadań obsługi zleceń i harmonogram konserwacji związane z wybranymi składnikami są aktualizowane automatycznie, jeśli po utworzeniu działania dotyczącego przestojów konserwacyjnych zostaną utworzone nowe zlecenia pracy lub wiersze harmonogramu konserwacji. Jeśli na przykład planujesz plany obsługi lub zaokrąglanie obsługi w odniesieniu do powiązanych środków trwałych dwa dni po utworzeniu działania dotyczącego przestojów, nowe wiersze harmonogramu konserwacji są automatycznie dodawane do działania dotyczącego przestojów konserwacyjnych.

8. We **Wszystkie działania w ramach przerwy konserwacyjnej** > **Działania w ramach przerwy konserwacyjnej** > wybierz działanie w ramach przerwy konserwacyjnej na liście i kliknij pozycję **Obciążenie wydajności**, aby otworzyć okienko dialogowe **Obliczanie obciążenia wydajności**. To okno dialogowe umożliwia uzyskanie przeglądu obciążenia zdolności produkcyjnych, na przykład dat, składników majątku, typów składników majątku i zadań konserwacyjnych. Należy pamiętać, że daty wyświetlane w oknie dialogowym są datami rozpoczęcia i zakończenia wybranymi w **Działania w ramach przerwy konserwacyjnej**. To obliczenie uwzględnia składniki majątku związane z działaniem przestoju w eksploatacji.

9. W oknie **Obliczanie obciążenia zdolności produkcyjnych** zdolności produkcyjnych, w razie potrzeby zmień godziny rozpoczęcia i zakończenia, a następnie wybierz opcję, jeśli mają być uwzględniane zlecenia produkcyjne i harmonogramy konserwacji w obliczeniach. Pola **Poziom** można użyć, aby wskazać, jak szczegółowe mają być wiersze obliczeń obciążenia wydajności dotyczące lokalizacji czynności konserwacyjnych. Jeśli na przykład w polu wstawiono liczbę „1” i istnieje wielopoziomowa struktura lokalizacji czynności konserwacyjnych, wszystkie wszystkie składniki majątku dla lokalizacji czynności konserwacyjnych, które zostały wybrane w ramach przerwy konserwacyjnej, będą wyświetlane na najwyższym poziomie, dlatego godziny w wierszu mogą być dodawane z lokalizacji czynności konserwacyjnych znajdujących się na niższym poziomie. W przypadku wstawienia liczby „0” w polu **Poziom** zostanie wyświetlony szczegółowy wynik zawierający wszystkie wiersze obciążenia wydajności na każdym poziomie lokalizacji czynności konserwacyjnych, z którymi są powiązane.

10. Kliknij przycisk **OK**, aby rozpocząć obliczanie. Łączna liczba godzin jest wyświetlana w przeglądzie **Obciążenie wydajności**. Na karcie **Obciążenie wydajności** > **Grupuj według...** (grupy okienka akcji), kliknij odpowiednie przyciski, aby uzyskać bardziej szczegółowy przegląd alokacji prognozowanych godzin. Na poniższej ilustracji przedstawiono wyniki obliczenia **Obciążenia wydajności**.

![Rysunek 3](media/21-preventive-maintenance.png)

11. Po uzyskaniu przeglądu obciążenia zdolności produkcyjnych, jeśli chcesz wprowadzić korekty dotyczące zadań obsługi zleceń lub wierszy harmonogramu konserwacji, Wróć do widoku szczegółowego **Działania w ramach przerwy konserwacyjnej** i wybierz wiersze, które chcesz dopasować na skróconych kartach **Wynikowe zadania konserwacyjne zleceń pracy** i **Wiersze harmonogramu konserwacji**.

12. Kliknij przycisk **Koryguj** i Aktualizuj oczekiwane daty rozpoczęcia/zakończenia, poziom usług lub pracowników obsługi technicznej dla wybranych zadań obsługi lub wierszy harmonogramu konserwacji zleceń.

13. Po dokonaniu wymaganych korekt kliknij przycisk **OK**. 

>[!NOTE]
>Zadania obsługi i wiersze harmonogramu konserwacji zlecenia produkcyjnego, które nie zostały uwzględnione w okresie przestoju w czasie konserwacji po dokonaniu korekt są automatycznie usuwane z **Działania w ramach przerwy konserwacyjnej**.

14. We **Wszystkie działania w ramach przerwy konserwacyjnej** > **Działania w ramach przerwy konserwacyjnej** > wybierz działanie na liście i kliknij pozycję **Prognoza dla pozycji**, aby otworzyć okienko dialogowe **Obliczanie prognozy dla pozycji**. To okno dialogowe służy do obliczania prognoz dla towarów (części zamiennych i innych wymaganych towarów) oraz do grupowania ich w celu uzyskania przeglądu, na przykład według daty, środka trwałego, typu środka i typu zadania konserwacji. Należy pamiętać, że daty wyświetlane w oknie dialogowym są datami rozpoczęcia i zakończenia wybranymi w **Działania w ramach przerwy konserwacyjnej**. To obliczenie obejmuje części zamienne i towary związane z środkami trwałymi wybranymi w ramach działania dotyczącego przestojów konserwacyjnych.

15. W oknie **Obliczanie prognozy dla pozycji** zdolności produkcyjnych, w razie potrzeby zmień godziny rozpoczęcia i zakończenia, a następnie wybierz opcję, jeśli mają być uwzględniane zlecenia produkcyjne i harmonogramy konserwacji w obliczeniach. Pola **Poziom** można użyć, aby wskazać, jak szczegółowe mają być wiersze obliczeń obciążenia wydajności dotyczące lokalizacji czynności konserwacyjnych. Jeśli na przykład w polu wstawiono liczbę „1” i istnieje wielopoziomowa struktura lokalizacji czynności konserwacyjnych, wszystkie wszystkie składniki majątku dla lokalizacji czynności konserwacyjnych, które zostały wybrane w ramach przerwy konserwacyjnej, będą wyświetlane na najwyższym poziomie, dlatego godziny w wierszu mogą być dodawane z lokalizacji czynności konserwacyjnych znajdujących się na niższym poziomie. W przypadku wstawienia liczby „0” w polu **Poziom** zostanie wyświetlony szczegółowy wynik zawierający wszystkie wiersze obciążenia wydajności na każdym poziomie lokalizacji czynności konserwacyjnych, z którymi są powiązane.

16. Kliknij przycisk **OK**, aby rozpocząć obliczanie. Łączna liczba prognoz dla pozycji jest wyświetlana w przeglądzie  **Prognoza dla pozycji**. Na karcie **Prognoza dla pozycji** > **Grupuj według...** (grupy okienka akcji), kliknij odpowiednie przyciski, aby uzyskać bardziej szczegółowy przegląd alokacji prognozowanych pozycji. Ilustracja poniżej przedstawia wyniki obliczeń typu **Prognozy dla pozycji**.

![Rysunek 4](media/22-preventive-maintenance.png)

- Istnieje możliwość kopiowania zasobów z jednej czynności związanej z obsługą przestojów do innej. We **Wszystkie działania w ramach przerwy konserwacyjnej**, wybierz przycisk **Kopiuj działania w ramach przerwy konserwacyjnej** i dokonaj wyboru w polach **Z działań w ramach przerwy konserwacyjnej** i **Do działań w ramach przerwy konserwacyjnej** i kliknij **OK**.
- We **Wszystkie działania w ramach przerwy konserwacyjnej** kliknij przycisk **Wiersze harmonogramu konserwacji** lub **Aktywne zlecenia pracy**, aby otworzyć powiązane listy i wyświetlić wiersze związane z wybraną obsługą działań dotyczących przerw.

