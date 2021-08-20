---
title: Rozwiązywanie problemów dotyczących wytwarzania dyskretnego
description: W tym temacie opisano, jak rozwiązać problemy, które mogą wystąpić podczas pracy z wytwarzaniem dyskretnym.
author: SmithaNataraj
ms.date: 11/04/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-11-04
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 895126d9c80c2eb6328c5c6c24140d1a7dc0818762f3f93c737a7858843d3eb7
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6780035"
---
# <a name="troubleshoot-discrete-manufacturing"></a>Rozwiązywanie problemów dotyczących wytwarzania dyskretnego

W tym temacie opisano, jak rozwiązać problemy, które mogą wystąpić podczas pracy z wytwarzaniem dyskretnym.

## <a name="i-receive-the-following-error-message-warehouse-management-processes-are-currently-being-used-if-work-lines-are-not-yet-registered-you-can-cancel-the-created-work-and-any-load-or-shipment-lines-and-then-continue-with-the-picking-or-shipping-process"></a>Otrzymuję następujący komunikat o błędzie: „Obecnie używane są procesy zarządzania magazynem. Jeśli wiersze robocze nie są jeszcze zarejestrowane, można anulować utworzoną pracę i wszelkie wiersze załadunku lub wysyłki, a następnie kontynuować proces pobierania lub wysyłki ”.

### <a name="issue-description"></a>Opis problemu

Ten problem występuje w przypadku próby rezerwacji lub zwolnienia pracy dla wiersza, ale transakcja magazynowa ma stan *Pobrane*, co oznacza, że materiał został pobrany.

### <a name="issue-resolution"></a>Rozwiązywanie problemów

Aby naprawić ten problem, należy wykonać jedną z następujących czynności.

- Zmień stan zlecenia produkcyjnego z powrotem na *Oszacowanie* lub *Zwolnione*.
- Otwórz stronę szczegółów dla odpowiedniego zlecenia produkcyjnego. W okienku akcji na karcie **Magazyn** w grupie **Zatrzymaj** wybierz opcję **Zatrzymaj i usuń zaznaczenie**, aby zrezygnować z pobrania wszystkich pobranych transakcji. Następnie wybierz pozycję **Usuń zatrzymanie**, aby przetworzyć zlecenie produkcyjne.

Poniżej znajduje się objaśnienie funkcji *Cofnięcia pobrania* i *Zatrzymaj*:

- **Cofnięcie pobrania** — Ta funkcja odwraca stan transakcji magazynowych dla wierszy BOM i wierszy formuły o stanie od *Pobrane* aż do stanu *Zamówione*. W przypadku ukończenia pobierania surowca, stan wierszy jest ustawiany na *Pobrane*. Ten stan uniemożliwia zresetowanie zlecenia produkcyjnego do stanu *Utworzone*. W takim przypadku można skorzystać z funkcji *Cofnięcia pobrania*, aby przywrócić transakcje ze stanu *Pobrane*, a następnie zresetować zlecenie produkcyjne do stanu *Utworzone*.
- **Zatrzymaj** — Ta funkcja ustawia flagę **Zatrzymane** w zleceniu produkcyjnym, co zapobiega aktualizacji stanu w zamówieniu. Flagę **Zatrzymane** można znaleźć na skróconej karcie **Magazyn** na stronie szczegółów zlecenia produkcyjnego.

> [!NOTE]
>
> - Przyciski są widoczne tylko wtedy, gdy zlecenie produkcyjne jest tworzone dla towarów, dla których włączono procesy magazynowe.
> - Grupa **Zatrzymaj** jest widoczna tylko na karcie **Magazyn** w okienku akcji na stronie Szczegóły zlecenia produkcyjnego. Nie jest on widoczny na skróconej karcie **Magazyn** strony listy **Zlecenia produkcyjne**.

## <a name="the-matching-resource-name-isnt-updated-after-i-change-a-worker-name-in-the-global-address-book"></a>Pasująca nazwa zasobu nie jest aktualizowana po zmianie nazwy pracownika w globalnej książce adresowej.

### <a name="issue-description"></a>Opis problemu

Jeśli zmienisz nazwę pracownika w globalnej książce adresowej, pasująca nazwa zasobu nie zostanie zaktualizowana w wzorcu grupy zasobów.

### <a name="issue-resolution"></a>Rozwiązywanie problemów

Ten scenariusz nie jest obecnie obsługiwany. Aby rozwiązać ten problem, należy ręcznie zaktualizować nazwę zasobu.

## <a name="when-i-create-a-new-production-order-i-dont-receive-the-following-message-insert-the-active-version-of-bill-of-material-and-route"></a>Kiedy tworzę nowe zlecenie produkcyjne, nie otrzymuję następującego komunikatu: "Wstawić aktywną wersję BOM i trasy?"

### <a name="issue-description"></a>Opis problemu

Podczas tworzenia nowego zlecenia produkcyjnego, po wprowadzeniu numeru towaru, pola **Oddział** i **Magazyn** są automatycznie ustawiane na domyślny oddział i magazyn, które są zdefiniowane na stronie **Domyślne ustawienia zamówienia** dla towaru gotowego. Ponadto automatycznie jest wprowadzany numer aktywnego BOM i numer trasy. Nie pojawia się następujący komunikat, który wyświetla monit o podanie tych wartości:

> Czy wstawić aktywną wersję BOM i trasy?

### <a name="issue-resolution"></a>Rozwiązywanie problemów

Nie jest wyświetlany monit o wstawienie numerów BOM i nrasy w przypadku wybrania produktu, dla którego zdefiniowano oddział i magazyn na stronie **Ustawienia domyślne zamówień**. Monit jest wyświetlany tylko wtedy, gdy nie zdefiniowano tych wartości dla wybranego produktu.

## <a name="production-orders-arent-shown-on-the-marking-page"></a>Zlecenia produkcyjne nie są wyświetlane na stronie Zaznaczanie.

### <a name="issue-description"></a>Opis problemu

Niektóre zlecenia produkcyjne nie są wyświetlane na stronie **Zaznaczanie**.

### <a name="issue-resolution"></a>Rozwiązywanie problemów

Produkty, które mają poniższą konfigurację, nie są dostępne do oznaczenia. Z tego powodu nie będą one widoczne na stronie **Zaznaczanie**:

- Produkty definiuje się jako produkty o typie *ilości efektywnej*.
- Są one włączone dla zaawansowanych procesów magazynowych.
- Są one skonfigurowane do sterowania przez zasadę *Kosztu standardowego*.

## <a name="when-i-try-to-end-a-production-order-i-receive-the-following-error-message-calculating-bom-consumptioncost-value-must-be-negative-upon-issue-from-inventory"></a>Kiedy próbuję zakończyć zlecenie produkcyjne, pojawia się następujący komunikat o błędzie: „Obliczanie kosztu zużycia BOM musi być ujemne w momencie wydania z magazynu”.

Ten błąd został rozwiązany w wersji 10.0.15.

## <a name="when-the-status-of-a-production-order-is-changed-from-reported-as-finished-to-end-i-receive-the-following-error-messages-update-conflict-the-standard-cost-does-not-match-with-the-financial-inventory-value-after-the-update-and-a-critical-error-has-occurred-in-function-inventcostmovementcheckvariance"></a>Gdy status zlecenia produkcyjnego zostanie zmieniony z Zgłoszono jako zakończone na Zakończone, otrzymuję następujące komunikaty o błędach: „Konflikt aktualizacji. Koszt standardowy nie zgadza się z wartością zapasów finansowych po aktualizacji” i „Wystąpił błąd krytyczny w funkcji InventCostMovement.checkVariance”.

Ten problem występuje, ponieważ dane źródłowe zostały zmienione przez inny proces. Proces podejmie próbę zaktualizowania danych do pięciu razy. Jeśli konflikt wciąż istnieje po pięciu próbach, zostaną wyświetlone następujące komunikaty o błędach:

> Aktualizuj konflikt. Koszt standardowy jest niezgodny z wartością zapasów finansowych po aktualizacji.

> Wystąpił błąd krytyczny w funkcji InventCostMovement.checkVariance.

Jest to celowe. Aby złagodzić ten problem, wznów zadanie wsadowe. Należy zakończyć pracę.

Jeśli zadanie wsadowe konsekwentnie kończy się niepowodzeniem po jego wznowieniu, sprawdź, czy dokładność zaokrąglania dla domyślnej waluty księgi jest zgodna z zaokrągleniem zastosowanym do wartości w tabeli InventSum. Jeśli precyzja zaokrąglania została zmieniona na niezgodną wartość, prawdopodobnie trzeba ją zmienić z powrotem na zgodną wartość. Wyszukaj **ModifiedDateTime**. W tym przypadku wartość zwykle pokazuje, że dokładność zaokrąglenia była ostatnio zmieniona.

## <a name="when-i-release-to-a-warehouse-i-receive-the-following-error-message-item-rm-could-not-be-fully-reserved-ensure-that-the-full-quantity-is-available-or-reserve-the-items-manually-if-the-reservation-field-on-the-bom-line-is-set-to-manual-or-started-could-not-release-the-order-to-warehouse-because-some-materials-could-not-be-reserved-however-the-status-is-updated-to-released"></a>Kiedy wysyłam do magazynu, otrzymuję następujący komunikat o błędzie: „Nie można w pełni zarezerwować pozycji RM. Upewnij się, że dostępna jest pełna ilość, lub zarezerwuj towary ręcznie, jeśli pole Rezerwacja w wierszu BOM jest ustawione na Ręcznie lub Rozpoczęto. Nie można zwolnić zamówienia do magazynu, ponieważ nie zarezerwowano pewnych materiałów". Stan jest jednak aktualizowany do Zwolnione.

### <a name="issue-description"></a>Opis problemu

Jeśli nie wszystkie pozycje wierszy BOM są fizycznie dostępne, gdy zlecenie produkcyjne jest zwalniane, a zasada **Zwolnij do magazynu** jest ustawiona na *Wymagaj pełnej rezerwacji* w zleceniu produkcyjnym, pojawi się następujący komunikat o błędzie:

> Nie można w pełni zarezerwować elementu RM pozycji. Upewnij się, że dostępna jest pełna ilość, lub zarezerwuj towary ręcznie, jeśli pole Rezerwacja w wierszu BOM jest ustawione na Ręcznie lub Rozpoczęto. Nie można zwolnić zamówienia do magazynu, ponieważ nie zarezerwowano pewnych materiałów.

### <a name="issue-resolution"></a>Rozwiązywanie problemów

Zachowanie to zgodnie z projektem i działa zgodnie z oczekiwaniami.

## <a name="when-i-try-to-end-a-production-order-and-report-as-finished-i-receive-the-following-error-message-total-good-quantity-reported-as-finished-for-the-production-will-be-1-feedback-for-the-last-operation-is-000-in-total"></a>Kiedy próbuję zakończyć zlecenie produkcyjne i zgłosić jako zakończone, pojawia się następujący komunikat o błędzie: „Całkowita ilość towaru zgłoszona jako gotowa dla produkcji wyniesie %1. Informacja zwrotna dla ostatniej operacji wynosi w sumie 0,00".

### <a name="issue-description"></a>Opis problemu

Podczas próby zaksięgowania arkusza zgłoszonych towarów gotowych w zleceniu produkcyjnym wyświetlany jest następujący komunikat o błędzie:

> Całkowita ilość gotowych wyrobów dobrych dla produkcji będzie wynosić %1. Informacja zwrotna dla ostatniej operacji wynosi w sumie 0,00.

### <a name="possible-cause"></a>Możliwa przyczyna

Ten problem występuje, jeśli ilości zaksięgowane w ostatniej operacji były nieprawidłowe. Na przykład jeśli rozpoczęto produkcję, ale ilość, która musi zostać uruchomiona, nie została przydzielona, arkusz karty marszruty zostanie zaksięgowany bez żadnych wierszy. Aby potwierdzić sytuację, otwórz zlecenie produkcyjne, a następnie w okienku akcji na karcie **Widok** wybierz opcję **Karta marszruty**.

### <a name="workaround"></a>Obejście

Ten problem można rozwiązać, księgując dodatkowe arkusze dla operacji, dla których nie zaksięgowano prawidłowo arkuszy. Uruchom ponownie zlecenie produkcyjne i zaznacz opcję, aby zaksięgować dodatkowe arkusze. Ta akcja nie spowoduje rozpoczęcia zlecenia produkcyjnego, ale spowoduje zaksięgowanie arkuszy. Karta marszruty powinna wtedy pokazywać zaksięgowane ilości i powinno być możliwe pomyślne zakończenie zleceń produkcyjnych.

## <a name="can-i-report-a-production-order-as-finished-while-i-report-the-error-quantity-but-not-while-i-report-the-time-or-material-quantity"></a>Czy mogę zgłosić zlecenie produkcyjne jako zakończone, gdy zgłaszam ilość błędów, ale nie podczas zgłaszania czasu lub ilości materiału?

Nie możesz zgłosić błędnej ilości w zleceniu produkcyjnym, chyba że zgłosisz również dobrą ilość. Ten scenariusz **nie** jest obsługiwany. Raport jako zakończona aktualizacja ostatecznie zakończy się niepowodzeniem podczas próby zakończenia zlecenia produkcyjnego i pojawi się następujący komunikat o błędzie:

> Brak raportu zakończonych ilości.

## <a name="can-i-trace-the-serial-numbers-of-finished-goods-against-the-serial-numbers-of-consumed-goods"></a>Czy mogę prześledzić numery seryjne wyrobów gotowych w porównaniu z numerami seryjnymi towarów zużytych?

Nie można prześledzić numerów seryjnych wyrobów gotowych względem numerów seryjnych materiałów, które zlecenie produkcyjne zużywa do wytworzenia tych wyrobów gotowych. Ten scenariusz nie jest obecnie obsługiwany. Obejściem jest tworzenie zleceń produkcyjnych dla ilości 1.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]