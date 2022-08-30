---
title: Rozpoznawanie odroczonego przychodu
description: W tym artykule podano informacje o sposobie rozpoznawania przychodu za pomocą funkcji Rozpoznawanie przychodów.
author: bking
ms.date: 08/24/2018
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: Customer
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: bking
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.openlocfilehash: c749415ecd6a0cda8a29e19998c295afa2ef5fd5
ms.sourcegitcommit: 1909d18a74cef85aad020a6a7473281e451f58c7
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/24/2022
ms.locfileid: "9348218"
---
# <a name="recognize-deferred-revenue"></a>Rozpoznawanie odroczonego przychodu

[!include [banner](../includes/banner.md)]

> [!NOTE]
> Funkcji Rozpoznawanie przychodów nie można włączyć za pomocą modułu Zarządzanie funkcjami. Obecnie można ją włączyć tylko przy użyciu kluczy konfiguracji.

W tym artykule opisano proces rozpoznawania przychodów w harmonogramie uznawania przychodów. Po zaksięgowaniu faktury dla zamówienia sprzedaży harmonogram rozpoznawania przychodów jest tworzony dla każdego wiersza zamówienia sprzedaży z harmonogramem przychodów. Harmonogram przychodów w wierszu służy do określenia, czy przychód w wierszu ma zostać odroczony.

## <a name="view-revenue-recognition-schedule-details"></a>Wyświetlanie szczegółów harmonogramu rozpoznawania przychodów

Istnieją dwa sposoby uzyskiwania dostępu do szczegółów harmonogramu rozpoznawania przychodów.

- Harmonogram rozpoznawania przychodów można otworzyć bezpośrednio z zafakturowanego zamówienia sprzedaży. W takim przypadku informacje w harmonogramie przychodów są filtrowane w celu wyświetlenia szczegółów tylko dla wybranego zamówienia sprzedaży. Ta metoda jest przydatna podczas sprawdzania poprawności szczegółów harmonogramu zamówienia sprzedaży.
- Harmonogram rozpoznawania przychodów można otworzyć na stronie **Rozpoznawanie przychodów \> Zadania okresowe**. Takie podejście jest często stosowane, gdy przychód jest rozpoznawany na koniec okresu. Po pierwszym otwarciu strony żadne informacje nie są wyświetlane. Filtry powyżej siatki służą do definiowania kryteriów dotyczących szczegółów harmonogramu, które mają być wyświetlane. Można filtrować daty faktur, wprowadzając zakres dat, zamówienie sprzedaży, odbiorcę, identyfikator projektu lub województwo.

[![Ilustracja strony Harmonogramy przychodów.](./media/revenue-recognition-schedule-page.png)](./media/revenue-recognition-schedule-page.png)

Skrócona karta **Wymiar finansowy** poniżej siatki pokazuje wymiary finansowe wiersza zamówienia sprzedaży. Te wymiary zostały uwzględnione podczas księgowania odroczonego przychodu. Są one również brane pod uwagę przy rozpoznawaniu przychodu. Używane wartości wymiarów zależą od struktury konta przypisanej do kont głównych przychodów i odroczonego przychodu.

## <a name="recognize-revenue"></a>Rozpoznawanie przychodu

Przychód jest rozpoznawany przez uruchomienie procesu **Utwórz arkusz** na stronie **Rozpoznawanie przychodu**. Tę stronę można otworzyć z poziomu zamówienia sprzedaży lub na stronie **Zadania okresowe**. Jeśli proces jest uruchamiany z poziomu zamówienia sprzedaży, przychód jest rozpoznawany tylko dla wybranego zamówienia sprzedaży. Zazwyczaj proces jest uruchamiany z poziomu strony **Zadania okresowe**, dzięki czemu rozpoznawany jest przychód dla wszystkich zaksięgowanych faktur zamówień sprzedaży.

Aby zdefiniować kryteria wybierania i księgowania przychodu, wybierz opcję **Utwórz arkusz**, aby otworzyć okno dialogowe **Utwórz arkusz**.

[![Parametry opcji tworzenia arkusza.](./media/revenue-recognition-create-journal.png)](./media/revenue-recognition-create-journal.png)

W oknie dialogowym użyj opcji w grupie pól **Data przetwarzania**, aby zdefiniować datę księgowania używaną przy rozpoznawaniu przychodu. W przypadku wybrania opcji **Wybrana data** można wprowadzić datę księgowania w polu **Data transakcji**. W przypadku wybrania opcji **Data harmonogramu przychodów** data transakcji nie jest używana. Zamiast tego wartość pola **Rozpoznaj datę** w każdym wierszu harmonogramu jest używana jako data księgowania.

Następnie w polu **Na dzień** wprowadź datę rozpoczęcia uznania przychodu. Wiersze harmonogramu, w których data rozpoznania jest zgodna z datą rozpoczęcia lub wcześniejsza, zostaną rozpoznane, pod warunkiem, że nie zostały wstrzymane.

Po zdefiniowaniu dat wybierz **OK** w oknie dialogowym, aby utworzyć arkusz. Wyświetlony zostanie komunikat, który pokazuje liczbę utworzonych transakcji i arkusz, w którym zostały utworzone. Arkusz nie jest księgowany automatycznie. W związku z tym menedżer rozpoznawania przychodów może sprawdzić, które wiersze harmonogramu są rozpoznawane.

Po uruchomieniu procesu wiersze w harmonogramie, które zostały przeniesione do arkusza, są oznaczane jako **Przetworzone**. Flaga **Przetworzony** wskazuje, że wiersze zostały przeniesione do arkusza, ale można je zaksięgować lub nie zaksięgować. Flaga **Przetworzony** pozostaje widoczna po zaksięgowaniu arkusza rozpoznawania przychodów. Jeśli arkusz rozpoznawania przychodów lub wiersz zostanie usunięty, flaga **Przetworzony** zostanie usunięta. W ten sposób można rozpoznać wiersz po ponownym uruchomieniu procesu **Utwórz arkusz**.

[![Strona harmonogramy rozpoznawania przychodów.](./media/revenue-recognition-rev-recog-schedule-02.png)](./media/revenue-recognition-rev-recog-schedule-02.png)

Na stronie **Arkusz rozpoznawania przychodów** (**Rozpoznawanie przychodów \> Wpisy w arkuszu \> Arkusz rozpoznawania przychodów**) otwórz opcję **Wiersze**, aby wyświetlić szczegóły dotyczące tego, co jest rozpoznawane. Dla każdego wiersza rozpoznawanego harmonogramu zawsze jest tworzona osobna transakcja, nawet jeśli wszystkie wiersze są księgowane z tą samą datą przy użyciu tych samych kont księgowych.

[![Strona z załącznikiem arkusza.](./media/revenue-recognition-journal-voucher.png)](./media/revenue-recognition-journal-voucher.png)

W kolumnie **Konto** jest wyświetlane konto księgowe odroczonego przychodu. Nie można edytować tego konta księgowego. To ograniczenie pomaga zagwarantować zwolnienie poprawnego konta księgowego dotyczącego odroczonego przychodu. To konto księgowe nie jest sprawdzane w odniesieniu do struktury konta, ponieważ mogło ulec zmianie od momentu zaksięgowania na określonym koncie księgowym przychodu.

W kolumnie **Konto przeciwstawne** jest wyświetlane konto księgowe odroczonego przychodu. Domyślnie konto księgowe przychodu jest pobierane z profilów księgowania zapasów, a wymiary finansowe są pobierane z wiersza zamówienia sprzedaży. To konto księgowe jest sprawdzane w odniesieniu do bieżącej struktury konta. Można je jednak edytować, jeśli struktura konta uległa zmianie i wymaga dodatkowych wymiarów finansowych.

Kwota domyślna pochodzi z odpowiedniego wiersza harmonogramu i nie można jej zmienić.

Domyślnie, jeśli zamówienie sprzedaży jest wielowalutowym zamówieniem sprzedaży, kurs wymiany jest ustawiany na kurs wymiany z faktury. To zachowanie pomaga zagwarantować, że waluta rozliczeniowa i kwoty w walucie raportowania są w pełni zwolnione. Ze względu na zaokrąglenie kurs wymiany dla ostatniego wiersza harmonogramu może się nieco różnić od stawki na fakturze.

Po zaksięgowaniu arkusza rozpoznawania przychodów załącznik jest wprowadzany do harmonogramu. Jeśli dla tego samego wiersza harmonogramu istnieje więcej niż jeden załącznik, w wierszu pojawi się gwiazdka (\*). Aby wyświetlić załączniki zaksięgowane dla danego wiersza, wybierz opcję **Transakcje na załączniku**.

## <a name="modify-the-revenue-recognition-schedule-details"></a>Modyfikowanie szczegółów harmonogramu rozpoznawania przychodów

Nie można edytować większości danych w harmonogramie przychodów. Nie można dodać nowych wierszy do harmonogramu, a istniejące wiersze nie mogą zostać usunięte. Szczegóły harmonogramu przychodów dla każdego wiersza zamówienia sprzedaży muszą być zachowane, aby zagwarantować, że w danym czasie organizacja rozpozna tę samą odroczoną kwotę.

### <a name="edit-schedule-lines"></a>Edytowanie wierszy harmonogramu

Niektóre czynności edytowania są dozwolone w wierszach harmonogramu. W wierszach można zmieniać następujące pola:

- **Wstrzymane** — tę flagę można ustawiać lub wyczyścić przed przetworzeniem wiersza. Aby wyczyścić flagę, zaznacz wiersz, a następnie wybierz opcję **Usuwanie wstrzymania**. Nie można rozpoznać przychodu w wstrzymanych wierszach. Wiersze mogą być wstrzymywane automatycznie, jeśli harmonogram przychodów został skonfigurowany dla automatycznych wstrzymań.

    [![Harmonogramy przychodów — edytowanie wierszy harmonogramu.](./media/revenue-recognition-rev-revenue-schedules.png)](./media/revenue-recognition-rev-revenue-schedules.png)

- **Data rozpoznania** — data rozpoznania może zostać zmieniona przed przetworzeniem wiersza. W przypadku uruchomienia procesu tworzącego arkusz w celu rozpoznania przychodu w polu **Rozpoznaj przychód od dnia** wprowadzana jest data. Ta data jest porównywana z datą w polu **Data rozpoznania** w celu określenia, które wiersze powinny zostać rozpoznane.
- **Kwota do zwolnienia** — kwotę, która zostanie zwolniona, można zmienić przed przetworzeniem wiersza. Można zmniejszyć kwotę rozpoznanego przychodu, ale nie można jej zwiększyć. To pole umożliwia organizacji rozpoznanie części przychodu w dniu rozpoznania. Jeśli kwota zostanie zmieniona, kwota w polu **Pozostała kwota** wskazuje przychód pozostały do rozpoznania.
- **Ilość do zwolnienia** — jeśli harmonogram przychodów jest ustawiony dla jednego wystąpienia lub jednego miesiąca, pole **Ilość do zwolnienia** pokazuje ilość dla wiersza zamówienia sprzedaży. To pole można również edytować i zapewnia ono inny sposób rozpoznawania części przychodu. Jeśli na przykład ilość w wierszu wynosi 5, można ją zastąpić, aby była mniejsza niż 5. Kwota w polu **Kwota do zwolnienia** jest proporcjonalnie aktualizowana.

### <a name="update-contract-terms"></a>Aktualizowanie warunków umowy

Szczegóły harmonogramu przychodów są tworzone na podstawie harmonogramu przychodów przypisanego do wiersza zamówienia sprzedaży podczas księgowania faktury. Jeśli harmonogram przychodów w wierszu zamówienia sprzedaży jest niepoprawny, nie można go zmienić w zamówieniu sprzedaży po zafakturowaniu zamówienia sprzedaży. Aby zmienić harmonogram przychodów, należy zamiast tego użyć przycisku **Aktualizuj warunki umowy**. Harmonogram przychodów można zmienić przed rozliczeniem przychodu lub po rozliczeniu.

Aby zmienić harmonogram, wybierz dowolny wiersz harmonogramu dla zmienianego elementu. Na poniższej ilustracji zaznaczono wiersz dotyczący pozycji S0008, która została zaksięgowana z użyciem harmonogramu przychodów 12-miesięcznych. Po wybraniu opcji **Aktualizuj warunki umowy** w oknie dialogowym zostaną wyświetlone daty rozpoczęcia i zakończenia umowy oraz harmonogram przychodów.

[![Daty rozpoczęcia i zakończenia umowy.](./media/revenue-recognition-rev-revenue-schedule-update-cntrct-dates-schedule.png)](./media/revenue-recognition-rev-revenue-schedule-update-cntrct-dates-schedule.png)

Zmień daty rozpoczęcia i zakończenia umowy, tak aby odpowiadały poprawnym zakresom dat. W przypadku zmiany zakresu dat wartość w polu **Liczba wystąpień** musi być zgodna z harmonogramem przychodów zdefiniowanym w systemie. W tym przykładzie, ponieważ umowa została zmieniony na 24-miesięczną, należy skonfigurować 24-miesięczny harmonogram przychodów. Ponieważ istnieje harmonogram przychodów 24-miesięcznych, jest on wprowadzany domyślnie, a umowa może zostać zmieniona. Jeśli harmonogram przychodów o zgodnej liczbie wystąpień nie istnieje, nie można zmienić umowy. Po zakończeniu aktualizacji warunków umowy i harmonogramu przychodów wybierz **OK** w oknie dialogowym, aby zapisać zmiany.

[![Zaktualizowany zakres dat umowy.](./media/revenue-recognition-rev-revenue-schedule-update-cntrct-dates-schedule-02.png)](./media/revenue-recognition-rev-revenue-schedule-update-cntrct-dates-schedule-02.png)

Zmiany umowy mają następujący wpływ na szczegóły harmonogramu przychodów:

- Jeśli dla produktu nie rozpoznano żadnego przychodu, wszystkie poprzednie szczegóły harmonogramu zostaną usunięte i zastąpione nowymi szczegółami harmonogramu przychodu. Na przykład pozycja S0008 miała początkowo 12 wierszy w szczegółach planowania. Te 12 wierszy zostało usuniętych i zastąpionych 24 wierszami zgodnie z nowym harmonogramem przychodów.
- Jeśli przychód został rozpoznany dla produktu, część przychodu została niepoprawnie rozpoznana, ponieważ uznanie zostało oparte na nieprawidłowym harmonogramie przychodów. Te wiersze muszą zostać wycofane i ponownie rozpoznane na podstawie nowego harmonogramu. W tym scenariuszu tworzone są nowe wiersze harmonogramu przychodu z kwotami ujemnymi w początkowej dacie rozpoznania. Następnie zostaną utworzone nowe wiersze w celu rozpoznania kwot na podstawie nowego harmonogramu przychodów. Na przykład 8 sierpnia 2019 r. uznano przychód na kwotę 10,53 USD. 8 września 2019 r. uznano przychód 13,16 USD. Dlatego dla tej samej daty tworzone są dwa nowe wiersze. Jeden wiersz dla kwoty 10,53 USD, a drugi dla 13,16 USD. Następnie zostaną utworzone 24 nowe wiersze, a między nimi zostanie rozdzielony łączny przychód 160,61 USD. Wiersze wycofujące można zaksięgować, uruchamiając proces **Tworzenie arkusza**.

[![Harmonogram rozpoznawania przychodów.](./media/revenue-recognition-rev-recog-schedule-03.png)](./media/revenue-recognition-rev-recog-schedule-03.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
