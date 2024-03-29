---
title: Realizacja zapasów bezpieczeństwa dla towarów
description: W tym artykule opisano realizację zapasów bezpieczeństwa oraz sposób konfigurowania ilości zapasów bezpieczeństwa dla towarów.
author: t-benebo
ms.date: 8/23/2021
ms.topic: article
ms.search.form: ReqSafetyKey, ReqItemTableSetup, ReqItemJournalName, ReqItemTable, EcoResProductDetailsExtended, ReqSafetyKeyDefaultDataWizard
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.dyn365.ops.version: 7.2999999999999998
ms.search.validFrom: 2017-12-31
ms.openlocfilehash: 70461ad1de94c984cb41e6b1d46af9e310a928d6
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8887407"
---
# <a name="safety-stock-fulfillment-for-items"></a>Realizacja zapasów bezpieczeństwa dla towarów

[!include [banner](../includes/banner.md)]

Zapas bezpieczeństwa oznacza dodatkową ilość towarów przechowywaną w zapasach w celu ograniczenia ryzyka braku dostępu towarów w magazynie. Zapas bezpieczeństwa służy jako zapas buforowy w przypadku gdy po otrzymaniu zamówień dostawca nie może dostarczyć dodatkowych towarów w celu dotrzymania wymaganej przez klienta daty wysyłki. Jeżeli zapasy bezpieczeństwa są używane do realizacji zamówienia sprzedaży, zapasy bezpieczeństwa zostaną zmniejszone. Można użyć funkcji Planowanie główne w celu automatycznego przywrócenia bezpiecznego poziomu zapasów.

## <a name="set-up-safety-stock-levels-for-items"></a>Konfigurowanie poziomów zapasu bezpieczeństwa dla towarów

Zapas bezpieczeństwa jest konfigurowany w ramach zapotrzebowania na towary na stronie **Zapotrzebowanie na towary** w obszarze **Zwolnione produkty \> Plan \> Zapotrzebowanie**.

W polu **Minimum** wprowadź poziom zapasów bezpieczeństwa, który chcesz zachować dla towarów. Wartość jest wyrażona w jednostkach magazynowych. Jeśli to pole jest puste, ilością domyślną jest zero. To pole jest dostępne w przypadku wybrania pozycji **Okres**, **Zapotrzebowanie** lub **Minimum/Maksimum** z listy **Kod zapotrzebowania**. Limit poziomu zapasów dotyczy dostępnych zapasów, co oznacza że rezerwacje i oznaczenia mogą spowodować uzupełnienie zapasów bezpieczeństwa zanim ilość fizyczna spadnie poniżej określonego poziomu minimalnego.

> [!NOTE]
> Przed zdefiniowaniem pola **Minimum** należy zdefiniować wszystkie inne planowane wymiary zapotrzebowania. Zapobiega to użyciu nieprawidłowego rekordu podczas planowania głównego. Taka sytuacja może na przykład wystąpić, jeśli grupa wymiarów zostanie rozszerzona o dodatkowy planowany wymiar zapotrzebowania, dla którego nie zdefiniowano jeszcze minimalnej i maksymalnej ilości zapasów.

Do obsługi sezonowych zmian popytu można użyć kluczy minimum. Na przykład poza sezonem można zmniejszyć poziom zapasów towaru i stopniowo zwiększać go w kolejnych miesiącach. Klucz minimum można utworzyć przechodząc do okna **Planowanie główne \> Konfiguracja \> Zapotrzebowanie \> Klucze minimum/maksimum**. Klucz minimum umożliwiający dostosowanie poziomu zapasów bezpieczeństwa według sezonu można określić w polu **Klucz minimum** na stronie **Zapotrzebowanie na towary**.

## <a name="example-minimum-key"></a>Przykład: klucz minimum

Poniższy przykład przedstawia sposób skonfigurowania klucza minimum, który uwzględnia zwiększony sezonowy popyt w miesiącach wiosennych i letnich.

1. Przejdź do menu **Planowanie główne \> Konfiguracja \> Zapotrzebowanie \> Klucze minimum/maksimum**.
1. Wybierz opcję **Nowy**, aby utworzyć klucz minimum/maksimum.
1. W polu **Klucz minimum lub maksimum** wprowadź identyfikator klucza. W polu **Nazwa** nadaj nazwę kluczowi.
1. Ustaw wartość *Tak* dla opcji **Użyj daty obowiązywania** i pozostaw pole **Data obowiązywania** puste, aby klucz był ważny od pierwszego dnia bieżącego roku.

    > [!NOTE]
    > Wartości w polach **Użyj daty obowiązywania** i **Data obowiązywania** wyznaczają datę, od których obowiązuje klucz.
    >
    > - Gdy opcja **Użyj daty obowiązywania** ma wartość *Nie*, klucz obowiązuje od daty bieżącej lub systemowej.
    > - Gdy opcja **Użyj daty obowiązywania** ma wartość *Tak*, klucz jest ważny od daty określonej w polu **Data obowiązywania**.

1. W sekcji **Okresy** utwórz 12 wierszy i ustaw dla nich następujące wartości:

    - **Zmień** — każdemu wierszowi przypisywany jest unikatowy numer z zakresu od 1 do 12. To pole wskazuje przyrostową zmianę w jednostce czasu określonej w polu **Jednostka**.
    - **Jednostka** — w każdym wierszu należy wybrać wartość *Miesiące*.
    - **Od dnia**, **Do dnia** i **Miesiąc** — te pola są ustawiane automatycznie na podstawie ustawień **Zmień** i **Jednostka**. Okresy miesięczne rozpoczynają się od pierwszego dnia bieżącego roku.
    - **Współczynnik** — wprowadź wartości opisane w poniższej tabeli. To pole definiuje współczynnik, przez który mają zostać pomnożone minimalne zapasy.

        | Wiersz (Zmień) | Współczynnik | Wynik |
        |---|---|---|
        | 1–3 | 1 | Minimalne stan magazynowy jest oparty na ustawieniu w miesiącach od stycznia do marca na stronie **Zapotrzebowanie na towary**. |
        | 4–5 | 2 | Minimalny stan magazynowy jest podwojony w okresie od kwietnia do maja. |
        | 6–8 | 2.5 | Minimalny stan magazynowy jest mnożony przez współczynnik 2,5 w okresie od czerwca do sierpnia. |
        | 9–12 | 1 | Minimalny stan magazynowy powraca do stanu dla okresu od września do grudnia określonego na stronie **Zapotrzebowanie na towary**. |

    Te ustawienia powinny teraz przypominać ustawienia na poniższej ilustracji.

    ![Okresy klucza minimum lub maksimum.](media/min-max-key-periods.png "Okresy klucza minimum lub maksimum")

> [!NOTE]
> Klucze minimum/maksimum można również utworzyć za pomocą kreatora. Na stronie **Klucze minimum lub maksimum** w okienku akcji wybierz opcję **Kreator**, aby otworzyć kreatora **Klucze minimum/maksimum**. Kreator przeprowadzi Cię krok po kroku przez proces tworzenia i konfigurowania klucza minimum/maksimum.

Jeżeli kod zapotrzebowania to *Minimum/Maksimum*, można także określić maksymalną ilość magazynową, jaką chcesz utrzymać dla towaru. Wartość jest także wyrażona w jednostkach magazynowych. Jeżeli prognozowane dostępne zapasy spadną poniżej minimalnej ilości, planowanie główne generuje planowane zamówienie w celu realizacji wszystkich otwartych wymagań i zwiększa dostępne zapasy do określonej ilości maksymalnej. Podobnie jak w przypadku konfigurowania minimalnej ilości zapasów, należy zdefiniować wszystkie inne wymiary planowanego zapotrzebowania przed ustawieniem wartości pola **Maksimum**.

## <a name="example-minmax-coverage-code"></a>Przykład: kod zapotrzebowania minimum/maksimum

Minimalna wartość wynosi 10, a maksymalna wynosi 15 minut. Aktualnie dostępne zapasy: 4. Oznacza to, że minimalna wymagana ilość wynosi 6. Jednak ilość maksymalna wynosi 15, dlatego planowanie główne wygeneruje zamówienie planowane na 11 sztuk.

W przypadku towarów, których dotyczy zapotrzebowanie sezonowe konieczne może być utrzymanie innych poziomów maksymalnych. W tym celu należy zdefiniować **Klucze maksimum**, przechodząc do okna **Planowanie główne \> Konfiguracja \> Zapotrzebowanie \> Klucze minimum/maksimum**. Wypełnij pole **Klucz maksimum** na stronie **Zapotrzebowanie na towary**. Informacje o poziomach zapasu bezpieczeństwa zdefiniowane za pomocą kluczy minimum można wyświetlić na karcie **Minimum/Maksimum** na stronie **Zapotrzebowanie na towary**. Należy upewnić się, że przez pewien okres minimalne i maksymalne wartości są zsynchronizowane.

## <a name="safety-stock-fulfillment"></a>Realizacja zapasów bezpieczeństwa

Parametr **Uzupełnij stany minimalne** umożliwia wybranie daty i okresu, w który poziom zapasów musi być zgodny z ilością określoną w polu **Minimum**. To pole jest dostępne w przypadku wybrania pozycji **Okres**, **Zapotrzebowanie** lub **Minimum/Maksimum** z listy **Kod zapotrzebowania**.

Jeżeli używane są **klucze minimum**, zaznacz pole wyboru **Okresy minimalne**, aby zapewnić minimalny poziom zapasów dla wszystkich okresów ustawionych dla klucza minimum. Jeśli usuniesz zaznaczenie pola wyboru, minimalna ilość zapasów jest spełniona dla tylko bieżącego okresu.

Poniższy scenariusz pokazuje, jak działa ten parametr i jakie są różnice między jego wartościami.

> [!NOTE]
> Na wszystkich ilustracjach w tym artykule oś x-oznacza zapasy, oś y-oznacza dni, paski oznaczają poziom zapasów, strzałki oznaczają transakcje, takie jak wiersze zamówień sprzedaży, wiersze zamówień zakupu lub planowane zamówienia.

[![Wspólny scenariusz realizacji zapasów bezpieczeństwa.](media/Scenario1.png)](media/Scenario1.png)

Parametr **Zrealizuj minimum** może mieć następujące wartości:

### <a name="todays-date"></a>Data dzisiejsza

Określona ilość minimalna jest spełniona w dniu planowania głównego. System próbuje zrealizować limit zapasów bezpieczeństwa jak najszybciej, mimo że może to być nierealne ze względu na czas realizacji.

[![Zapotrzebowanie na dzisiaj.](media/TodayReq.png)](media/TodayReq.png)

Planowane zamówienie P1 jest tworzone dla dnia dzisiejszego w celu zwiększenia dostępnych zapasów powyżej poziomu zapasów bezpieczeństwa w tym dniu. Wiersze zamówienia sprzedaży S1 do S3 kontynuują zmniejszanie poziomu zapasów. Planowane zamówienia P2 do P4 są generowane przez planowanie główne w celu przywrócenia poziomu zapasów do bezpiecznego limitu po każdym zapotrzebowaniu z zamówienia sprzedaży.

Gdy używany jest kod **Zapotrzebowanie**, tworzonych jest wiele planowanych zamówień. Warto zawsze używać zapotrzebowania **Okres** lub **Minimum/Maksimum** dla towarów i materiałów o dużym popycie w celu uzupełnienia zapasów. Na poniższej ilustracji przedstawiono przykład kodu zapotrzebowania **Okres**.

[![Okres. Dzisiejsza data.](media/TodayPeriod.png)](media/TodayPeriod.png)

Na poniższej ilustracji przedstawiono przykład kodu zapotrzebowania **Min./Maks.**.

[![Min/maks. dzisiejsza data.](media/TodayMinMax.png)](media/TodayMinMax.png)

### <a name="todays-date--procurement-time"></a>Data dzisiejsza + czas zaopatrzenia

Określona ilość minimalna jest spełniona w dniu planowania głównego wydłużonego o czas zakupu lub produkcji. Czas ten uwzględnia marginesy bezpieczeństwa. Jeśli towar zawiera umowę handlową, a pole wyboru **Znajdź umowy handlowe** jest zaznaczone na stronie **Parametry planowania głównego**, czas realizacji dostawy z umowy handlowej nie jest uwzględniany. Czasy realizacji są określane na podstawie ustawień zapotrzebowania na towar lub na podstawie ustawień towaru.

Ten tryb realizacji spowoduje utworzenie planów z mniejszą liczbą opóźnień i planowanych zamówień bez względu na ustawione grupy zapotrzebowania ustawione dla towaru.

Na poniższej ilustracji przedstawiono wyniki planu, jeśli kod zapotrzebowania to **Zapotrzebowanie** lub **Okres**.

[![Wymaganie lub okres. Dzisiejsza data i czas realizacji.](media/TodayPLTReq.png)](media/TodayPLTReq.png)

Na poniższej ilustracji przedstawiono wyniki planu, jeśli kod zapotrzebowania to **Min./Maks.**.

[![Min/maks. Dzisiejsza data i czas realizacji.](media/TodayPLTMinMax.png)](media/TodayPLTMinMax.png)

### <a name="first-issue"></a>Pierwszy rozchód

Określona ilość minimalna jest spełniona w dniu, gdy dostępne zapasy spadną poniżej minimalnego poziomu, jak pokazano na poniższej ilustracji. Nawet jeżeli poziom dostępnych zapasów jest niższy od minimalnego w dniu planowania głównego, funkcja **Pierwszy rozchód** nie podejmie próby jego zwiększenia do momentu odebrania następnego zapotrzebowania.

Na poniższej ilustracji przedstawiono przykład kodu zapotrzebowania **Zapotrzebowanie**.

[![Planowanie towaru za pomocą kodu zapotrzebowania Zapotrzebowanie i realizacji Pierwszy rozchód.](media/FirstIssueReq.png)](media/FirstIssueReq.png)

Na poniższej ilustracji przedstawiono przykład kodu zapotrzebowania **Okres**.

[![Planowanie towaru za pomocą kodu zapotrzebowania Okres i realizacji Pierwszy rozchód.](media/FirstIssuePeriod.png)](media/FirstIssuePeriod.png)

Na poniższej ilustracji przedstawiono przykład kodu zapotrzebowania **Min./Maks.**.

[![Planowanie towaru za pomocą kodu zapotrzebowania MinMaks i realizacji Pierwszy rozchód.](media/FirstIssueMinMax.png)](media/FirstIssueMinMax.png)

W dniu planowania głównego, jeżeli dostępne zapasy są już niższe od limitu zapasów bezpieczeństwa, opcje **Data dzisiejsza** i **Data dzisiejsza + czas zaopatrzenia** spowodują natychmiastowe uzupełnienie zapasów. Funkcja **Pierwszy rozchód** będzie czekać na kolejną transakcję rozchodu, taką jak zamówienie sprzedaży i wymaganie wiersza BOM dla towaru, a następnie uruchomi uzupełnianie zapasów w dniu tej transakcji.

W dniu planowania głównego, jeżeli poziom dostępnych zapasów nie będzie niższy od limitu zapasów bezpieczeństwa, opcje **Data dzisiejsza** i **Pierwszy rozchód** spowodują uzyskanie dokładnie takiego samego wyniku, jak pokazano na poniższej ilustracji.

[![Nie poniżej limitu.](media/ReqFirstIssue.png)](media/ReqFirstIssue.png)

W dniu planowania głównego, jeżeli poziom dostępnych zapasów nie będzie niższy od limitu zapasów bezpieczeństwa, opcja **Data dzisiejsza + czas zaopatrzenia** spowoduje uzyskanie poniższego wyniku, ponieważ odkłada realizację aż do zakończenia czasu realizacji zaopatrzenia.

![Realizacja opóźniona do końca czasu realizacji zaopatrzenia.](media/ReqTodayLT.png)

### <a name="coverage-time-fence"></a>Horyzont czasowy zapotrzebowania

Określona ilość minimalna jest spełniona w okresie podanym w polu **Horyzont czasowy zapotrzebowania**. Ta opcja jest przydatna, gdy planowanie główne nie zezwala na użycie dostępnych zapasów na potrzeby rzeczywistych zamówień, takich jak sprzedaż lub przeniesienia, w celu zachowania poziomu bezpieczeństwa. Jednak w przyszłej wersji ten tryb uzupełniania zapasów nie będzie potrzebny, ponieważ ta opcja zostanie wycofana.

## <a name="plan-safety-stock-replenishment-for-first-expired-first-out-fefo-items"></a>Planowanie uzupełnienia zapasów bezpieczeństwa dla towarów FEFO

W dowolnej chwili odbiór zapasów z najdłuższą datą ważności zostanie użyty dla zapasów bezpieczeństwa aby umożliwić realizację rzeczywistego zapotrzebowania, takiego jak wiersze sprzedaży lub BOM w zamówieniu FEFO.

Aby pokazać, jak to działa, rozważmy następujący scenariusz.

[![Scenariusz FEFO.](media/FEFOScenario.png)](media/FEFOScenario.png)

Po uruchomieniu planowania zrealizuje pierwsze zamówienie sprzedaży z istniejących dostępnych zapasów i dodatkowe zamówienie zakupu dla pozostałej ilości.

[![FEFO 1.](media/FEFO1.png)](media/FEFO1.png)

Tworzone jest planowane zamówienie, aby zapewnić zwiększenie dostępnych zapasów do poziomu limitu bezpieczeństwa.

[![FEFO 2.](media/FEFO2.png)](media/FEFO2.png)

Gdy planowane jest drugie zamówienie sprzedaży, wcześniej utworzone planowane zamówienie, które obejmuje zapasy bezpieczeństwa jest używane do obsługi tej ilości. Dlatego poziom zapasów bezpieczeństwa stale się zmienia.

[![FEFO 3.](media/FEFO3.png)](media/FEFO3.png)

Wreszcie tworzone jest kolejne planowane zamówienie do obsługi zapasów bezpieczeństwa.

[![FEFO 4.](media/FEFO4.png)](media/FEFO4.png)

Wszystkie partie wygasają odpowiednio i tworzone są planowane zamówienia do uzupełnienia zapasów bezpieczeństwa po ich wygaśnięciu.

## <a name="how-master-planning-handles-the-safety-stock-constraint"></a>Jak planowanie główne obsługuje ograniczenie zapasów bezpieczeństwa

Zapasy bezpieczeństwa są śledzone w systemie jako typ zapotrzebowania, podobnie jak wiersze sprzedaży lub zapotrzebowania BOM. Wiersz zapotrzebowania zapasów bezpieczeństwa jest widoczny na stronie **Zapotrzebowanie netto** po usunięciu filtra domyślnego w kolumnie **Typ wymagania**.

Priorytet realizacji zapotrzebowania na zapasy bezpieczeństwa jest obniżany, jeżeli system określi, że powoduje to opóźnienia w realizacji rzeczywistego zapotrzebowania, takiego jak wiersze sprzedaży, wiersze BOM, zapotrzebowanie przeniesienia lub wiersze prognozy popytu. W przeciwnym wypadku sprawdzenie, czy poziom dostępnych zapasów jest wyższy od ilości zapasów bezpieczeństwa ma taki sam priorytet jak inne typy zapotrzebowania. Zapewnia to brak opóźnień w realizacji rzeczywistych transakcji i ułatwia zapobieganie nadmiernemu uzupełnieniu zapasów i wczesnemu uzupełnieniu zapasów bezpieczeństwa.

Na etapie realizacji zapotrzebowania planowania głównego priorytet uzupełniania zapasów bezpieczeństwa nie jest już obniżany. Dostępnych zapasów można użyć przed innymi typami zapotrzebowania. Podczas obliczania opóźnienia zostanie dodana nowa logika w celu uniknięcia opóźnionych wierszy sprzedaży, zapotrzebowania wiersza BOM i wszystkich innych typów zapotrzebowania w celu określenia, czy mogą zostać dostarczone na czas, pod warunkiem że używane są zapasy bezpieczeństwa. Jeżeli system określi, że może zminimalizować opóźnienia, używając zapasów bezpieczeństwa, wiersze sprzedaży lub BOM zastąpią początkowe zapotrzebowania zapasami bezpieczeństwa, a system uruchomi uzupełnianie zapasów bezpieczeństwa.

Jeżeli plan lub towar nie jest skonfigurowany do opóźnionego obliczania, ograniczenie zapasów bezpieczeństwa będzie miało taki sam priorytet jak inne typy zapotrzebowania. Oznacza to, że występuje rezerwa dostępnych zapasów i innych dostępnych zapasów przed innymi typami popytu.

## <a name="additional-resources"></a>Dodatkowe zasoby

- [Używanie arkusza zapasu bezpieczeństwa do aktualizowania minimalnego zapotrzebowania dla pozycji](safety-stock-journal.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
