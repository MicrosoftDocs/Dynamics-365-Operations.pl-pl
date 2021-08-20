---
title: Serie czynności konserwacyjnych
description: W tym temacie wyjaśniono serie czynności konserwacyjnych w module Zarządzanie składnikami majątku.
author: johanhoffmann
ms.date: 08/27/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetRoundTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: dc0d8ec546e7455187a87ac124c5e56a93f5bafd2270bf275af950991fc4b87e
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6740726"
---
# <a name="maintenance-rounds"></a>Serie czynności konserwacyjnych

[!include [banner](../../includes/banner.md)]

 

Serie czynności konserwacyjnych można konfigurować w **Zarządzanie składnikami majątku** odniesieniu do różnych składników majątku, na których trzeba wykonywać podobne zadania w regularnych odstępach czasu. Na przykład zadania smarowania lub inspekcje bezpieczeństwa, które trzeba wykonać na kilku maszynach w tych samych interwałach. Pierwszym krokiem jest utworzenie rundy serwisowego, w tym środków trwałych wymagających tej samej formy zadania konserwacji. Następnie należy zaplanować zaokrąglenia obsługi. Po ukończeniu harmonogramu zaokrąglania eksploatacji można wyświetlić wszystkie rekordy zadań odnoszące się do tej rundy we **Wszystkich wierszach harmonogramu konserwacji** i **Otwieranie wierszy harmonogramu konserwacji**.

>[!NOTE]
>Liczby zaokrąglania konserwacji można również skonfigurować w lokalizacjach funkcjonalnych, które mają być wykonane na środkach trwałych instalowanych w lokalizacji funkcjonalnej w momencie tworzenia zamówienia pracy opartego na zaokrąglaniu. Aby uzyskać więcej informacji temat konfiguracji funkcji serii czynności konserwacyjnych w [Tworzenie lokalizacji czynności konserwacyjnych](../functional-locations/create-functional-locations.md).

## <a name="set-up-a-maintenance-round"></a>Ustaw serii czynności konserwacyjnych

1. Kliknij **Zarządzanie składnikami majątku** > **Konfiguracja** > **Konserwacja zapobiegawcza** > **Serie czynności konserwacyjnych**.

2. Kliknij przycisk **Nowy**, aby utworzyć nową serię czynności konserwacyjnych.

3. Wstaw identyfikator polu **Seria czynności konserwacyjnych**, a następnie wprowadź nazwę dla opcji Konserwacja w polu **nazwa**.

4. W polu **Data rozpoczęcia** wybierz datę rozpoczęcia.

5. W polach **Zakończ w ciągu dni** i **Zakończ w ciągu godzin** się w godzinach można wstawić oczekiwaną datę zakończenia w dniach lub godzinach. Oczekiwana data końcowa jest obliczana w odniesieniu do daty początkowej, która jest obliczana podczas tworzenia wierszy harmonogramu konserwacji. Na przykład można wstawić wartość „7” w polu **zakończenie w ciągu dni**, aby wskazać, że powiązane zadanie powinno zostać wykonane w ciągu tygodnia od daty rozpoczęcia.

6. Wybierz wartość „tak” w przycisku przełącznika **Automatyczne tworzenie** jeśli zlecenia pracy mają być automatycznie tworzone z wierszy harmonogramu konserwacji, które zostały utworzone na podstawie tej serii czynności konserwacyjnych.

7. W polu **Typ zlecenia pracy** wybierz typ zlecenia pracy, które ma być używane dla zleceń produkcyjnych utworzonych na podstawie tej serii czynności konserwacyjnych.

8. W polu **Poziom usług** wybierz poziom usług zlecenia pracy, które ma być używane dla zleceń produkcyjnych utworzonych na podstawie tej serii czynności konserwacyjnych.

9. Na skróconej karcie kliknij **wiersze składników majątku** kliknij przycisk **Dodaj**, aby dodać składnik majątku do serii czynności konserwacyjnych.

10. Numer wiersza jest automatycznie wstawiany w polu **Numer wiersza** w celu wskazania kolejności środków trwałych w serii czynności konserwacyjnych.

11. Wybierz składnik majątku w polu **Składnik majątku**.

12. W polu typ zadania konserwacji Wybierz **typ zadania konserwacji**.

13. W razie potrzeby wybierz **Wariant typu zadania konserwacji** i **Zawód** powiązany z typem zadania konserwacji.

14. Wybierz cykl (dzień, tydzień itd.) w polu **Typ okresu**.

15. W polu **częstotliwość okresu** wstaw liczbę powtórzeń dla serii czynności konserwacyjnych. Przykład: Jeśli w polu **Typ okresu** wybrano wartość dzień, a w tym polu zostanie wstawiony numer 7, nowe wiersze serii czynności konserwacyjnych są tworzone tylko raz w tygodniu.

16. W polu **Data rozpoczęcia** wybierz datę początkową środka trwałego, który ma zostać uwzględniony w serii czynności konserwacyjnych. Ta data może być inna od daty początkowej ustawionej dla serii czynności konserwacyjnych.

17. Aby dodać więcej składników majątku do serii czynności konserwacyjnych, powtarzaj kroki od 9 do 16.

18. Na skróconej karcie kliknij **Wiersze lokalizacji czynności konserwacyjnych** kliknij przycisk **Dodaj**, aby dodać składnik majątku do serii czynności konserwacyjnych. Zobacz opis powiązanych pól powyżej. Te same pola są dostępne w przypadku tworzenia wierszy środków trwałych, ale w razie potrzeby można również wybrać **producenta** i **model** dla lokalizacji czynności konserwacyjnych. Jeśli w wierszu wybrano tylko lokalizację czynności konserwacyjnych, ale nie zostaną wybrane opcje w **Typ składnika majątku**, **producent**, **model**, **Typ zadania konserwacji**, **Wariant typu zadania konserwacji** i **Zawód**, wszystkie składniki majątku związane z tą lokalizacją czynności konserwacyjnych w czasie planowania konserwacji zostaną uwzględnione w serii czynności konserwacyjnych.

19. Na skróconej karcie **pule** kliknij przycisk **Dodaj**, aby wybrać pulę zleceń pracy, która ma zostać uwzględniona w serii czynności konserwacyjnych. Kilka pul zleceń pracy można połączyć z jedną serią czynności konserwacyjnych.

20. Zapisz ustawienia.

>[!NOTE]
>Pola **Składniki majątku** i **Wiersze** znajdujące się w grupie **Szczegóły** na skróconej karcie **Nagłówek** zawierają łączną liczbę środków trwałych i wierszy związanych z wybraną serią czynności konserwacyjnych.

Poniższa ilustracja przedstawia i przykład cyklu eksploatacji zawierającego trzy składniki majatku.

![Rysunek 1.](media/13-preventive-maintenance.png)


## <a name="schedule-maintenance-rounds"></a>Planowanie serii czynności konserwacyjnych

Po skonfigurowaniu serii czynności konserwacyjnych należy uruchomić zadanie harmonogramu w celu zaplanowania wszystkich zadań związanych z serią czynności konserwacyjnych.

1. Kliknij **Zarządzanie składnikami majątku** > **Okresowe** > **Konserwacja zapobiegawcza** > **Planowanie serii czynności konserwacyjnych** lub **Zarządzanie składnikami majątku** > **Wspólne** > **Harmonogram konserwacji** > **Wszystkie harmonogramy konserwacji** lub **Otwieranie wierszy harmonogramu konserwacji** lub **Otwieranie puli harmonogramów konserwacji** > na liście wybierz harmonogram konserwacji > przycisk **Serie czynności konserwacyjnych**.

2. W polu **okres** wybierz typ okresu, który ma być używany dla zadania planowania.

3. W polu **częstotliwość okresu** wstaw liczbę okresów, które mają zostać uwzględnione w zadaniu planowania. Rozpoczęcie planowania to data bieżąca.

4. Wybierz wartość tak w polu przełącznik **automatyczne tworzenie**, jeśli zlecenie ma być automatycznie tworzone na podstawie serii czynności konserwacyjnych

>[!NOTE]
>Jeśli ten przycisk przełącznika ma wartość "tak", a przycisk przełącznika **automatyczne tworzenie** jest również zaznaczone jako "tak" w serii czynności konserwacyjnych w formularzu **Serie czynności konserwacyjnych**, to zlecenia są tworzone na podstawie wierszy serii czynności konserwacyjnych, a zostaną również utworzone wiersze harmonogramu konserwacji ze stanem „utworzone zlecenie pracy”. Jeśli tylko jeden z opcji **automatycznego tworzenia** jest skonfigurowany jako „tak” w menu rozwijanym w **Serie czynności konserwacyjnych** są tworzone tylko wiersze harmonogramu konserwacji o stanie „utworzone”. W takim przypadku zlecenia pracy nie są tworzone.

5. W razie potrzeby można wybrać serir czynności konserwacyjnych lub inną datę rozpoczęcia zadania planowania. Kliknij **Filtruj** i dodaj serie czynności konserwacyjnych, które mają zostać uwzględnione.

6. Kliknij przycisk **OK**.

7. Teraz widzisz serie czynności konserwacyjnych w **Zarządzanie składnikami majątku** > **Wspólne** > **harmonogram konserwacji** > **Wszystkie harmonogramy konserwacji** lub **Otwieranie wierszy harmonogramu konserwacji**. Jeśli zaplanowane seria czynności konserwacyjnych jest połączone z pulą zleceń roboczych, wiersze harmonogramu konserwacji można również wyświetlać w **Otwieranie puli harmonogramów konserwacji**. Wiersze harmonogramu konserwacji utworzone z serii mają typ odwołania „serie czynności konserwacyjnych”.

W dwóch poniższych ilustracjach przedstawiono zadanie planowania w oknie dialogowym **Planowanie serii czynności konserwacyjnych** oraz wiersze harmonogramu konserwacji utworzone we **Wszystkich harmonogramach konserwacji** na podstawie tego zadania harmonogramu.

![Rysunek 2.](media/14-preventive-maintenance.png)

![Rysunek 3.](media/15-preventive-maintenance.png)

- Jeśli zlecenia produkcyjne są tworzone ręcznie na środkach, które zostały objęte gwarancją dostawcy, wyświetlane jest okno dialogowe, które użytkownik będzie wiedział o gwarancji. Utworzenie zlecenia produkcyjnego może zostać anulowane. Sprawdzanie relacji gwarancji jest pomijane dla automatycznie tworzonych zleceń produkcyjnych.  
- Istnieje możliwość skonfigurowania zadania wsadowego w skróconej karcie **Uruchom w tle** w celu zaplanowania serii w regularnych odstępach czasu.  
- Jeśli seria jest uwzględniona w kilku pulach zleceń pracy (zapoznaj się z [Pule zleceń pracy](../work-orders/work-order-pools.md)), jest wyświetlany jeden rekord dla każdej puli w **Otwieranie puli harmonogramów konserwacji**. W ten sposób można zoptymalizować opcje filtrowania dla pul zleceń pracy.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]