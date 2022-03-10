---
title: Zarządzanie foliami
description: W tym temacie opisano sposób pracy z folio. Folio zazwyczaj składa się z towarów jednego dostawcy dla jednego podmiotu lub firmy na przesyłkę. Towary w folio mogą znajdować się w jednym kontenerze lub można je rozłożyć na wiele kontenerów.
author: sherry-zheng
ms.date: 12/14/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ITMFolioTable, ITMFolioTableListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-12-14
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 5b84237844ec1d8f6c0716a0a13b05c83b358901
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/29/2021
ms.locfileid: "7575783"
---
# <a name="manage-folios"></a>Zarządzanie foliami

[!include [banner](../../includes/banner.md)]

Folio jest często określone przez przepisy celne. Może ono składać się z jednego towaru dostawcy dla jednej jednostki lub firmy na wysyłkę. Towary w folio mogą znajdować się w jednym kontenerze lub można je rozłożyć na wiele kontenerów.

Aby otworzyć stronę **Wszystkie folio**, przejdź do strony **Koszt z wyładunkiem \> Folio \> Wszystkie folio**. Ta strona pokazuje listę wszystkich aktualnych folio. Możesz używać przycisków w Okienku akcji do tworzenia, usuwania i pracy z folio. Wybierz dowolne folio na liście, aby wyświetlić jego szczegóły na stronie **Folio**.

## <a name="action-pane"></a>Okienko akcji

Okienko akcji na stronie **Wszystkie folio** i **Folio** zawiera przyciski, które umożliwiają pracę z wybranym folio. Każdy przycisk wykonuje pojedynczą akcję. W okienku akcji znajdują się także karty, z których każdy z kolei zawiera zestaw powiązanych przycisków. Oprócz tych różnic wszystkie przyciski i karty opisane w poniższych podsekcjach są dostępne zarówno w widoku listy (to jest na stronie **Wszystkie folio**), jak i w widoku szczegółowym (tj. na stronie **Folio**).

### <a name="buttons-that-appear-directly-on-the-action-pane"></a>Przyciski wyświetlane bezpośrednio w okienku akcji

W poniższej tabeli opisano przyciski, które są dostępne bezpośrednio w okienku akcji.

| Przycisk | opis |
|---|---|
| Nowa | Tworzenie folio. |
| Usuwanie | Usuń otwarte lub wybrane folio. |
| Koszty podróży | Otwórz stronę **Koszty podróży**, na której możesz przeglądać i dodawać koszty na poziomie folio do wszystkich towarów w podróży. Gdy koszty folio są dodawane ręcznie do podróży, są one automatycznie dodawane do strony Zapytania o koszty i przydzielane do każdego towaru zgodnie z metodą określoną na stronie **Koszty podróży**. |

### <a name="buttons-on-the-manage-tab"></a>Przyciski na karcie Zarządzanie

W poniższej tabeli opisano przyciski, które są dostępne bezpośrednio na karcie **Zarządzanie** w okienku akcji.

| Przycisk | opis |
|---|---|
| Księguj listę przychodu | Opublikuj listę potwierdzeń dla wszystkich linii zamówień w folio. Jeśli używane są przesyłki obejmujące wiele firm, dla każdej firmy otwierane jest nowe okno dialogowe księgowania listy przyjęć. |
| Księguj dokument przyjęcia produktów | Zaksięguj pokwitowanie produktu dla wszystkich linii zamówienia w folio. W przypadku podróży obejmujących wiele firm otwierane jest nowe okno dialogowe księgowania przyjęcia produktów dla każdej firmy. |
| Księguj fakturę | Opublikuj fakturę dla wszystkich linii zamówień w folio. W przypadku podróży obejmujących wiele firm otwierane jest nowe okno dialogowe księgowania faktur dla każdej firmy. |
| Wyślij zamówienie przeniesienia | Zaksięguj polecenie przeniesienia dla wszystkich wierszy zamówienia przeniesienia, które są związane z bieżącym folio w powiązanej przesyłce. |
| Przyjmuj zamówienie przeniesienia | Zaksięguj paragon polecenia przeniesienia dla wszystkich wierszy zamówienia przeniesienia, które są związane z bieżącym folio w powiązanej przesyłce. |
| Przyjmuj towar w drodze | Odbierz wszystkie linie zamówień, które są w trakcie folio. |
| Otrzymano dokumenty | Zaktualizuj ustawienie w opcji **Dokumenty otrzymane** ustawiono wartość *Tak*. Możesz użyć tego przycisku, aby zablokować pozycję i/lub linię zakupu, aby nie można było ich dalej aktualizować. |
| Znajdź koszty automatyczne | Znajdź odpowiednie koszty podróży. Jeśli te koszty zostały już znalezione lub zaktualizowane, pojawi się następujący komunikat: „Istnieją niezafakturowane wiersze kosztów. Czy chcesz je zastąpić?" Zwróć uwagę, że koszty podróży dołączone do folio i zafakturowane nie zostaną nadpisane. |
| Utwórz arkusz przyjęcia | Arkusz przybycia do organizacji można wygenerować za pomocą zaawansowanych funkcji magazynu. Można wybrać **Zainicjuj ilość** (zalecane), a następnie **Utwórz z towarów w drodze** i/lub **Utwórz na pomocą zamówień zakupu**. Ostatnia opcja zależy od tego, czy używane jest przetwarzanie towarów w drodze. |
| Nalicz koszty | Koszty można naliczać, gdy typ kosztu ma konto księgowe określone dla obciążenia. Ten przycisk jest zwykle używany, gdy zapasy są w transporcie lub gdy towary zostały odebrane i zafakturowane. |

### <a name="buttons-on-the-general-tab"></a>Przyciski na karcie Ogólne

W poniższej tabeli opisano przyciski, które są dostępne bezpośrednio na karcie **Ogólne** w okienku akcji.

| Przycisk | opis |
|---|---|
| Lista przychodu | Opublikuj listę potwierdzeń dla wszystkich linii zamówień w folio. Jeśli używane są podróże obejmujące wiele firm, dla każdej firmy otwierane jest nowe okno dialogowe księgowania listy przyjęć. |
| Dokument przyjęcia produktów | Umożliwia wyświetlenie rekordu dokumentu przyjęcia produktów, jeśli jest używany. |
| Przyjęcie pozycji | Wyświetl dziennik przybycia towarów, jeśli jest używany. |
| Zapytanie dotyczące kosztów | Otwórz stronę zapytania o koszty, aby wyświetlić wszystkie koszty podróży, w tym kontener wysyłkowy, folio i zamówienie zakupu. Przy użyciu akcji Wyświetl można skorygować dokładny widok strony. Na stronie zapytania o koszty można wyświetlić dowolne obszary plus kod towaru i typu kosztu. Usuwając te elementy, możesz dostosować stronę, grupując razem koszty. Ta funkcja może być przydatna, jeśli używasz rozmiarów i kolorów. Wymiary wyświetlane na stronie można zmieniać. Na stronie **Koszty** są dostępne tylko kody typów kosztów, dla których wpis **Dr** na karcie **Księgowanie** jest ustawione na *Pozycja*. |

## <a name="header-view"></a>Widok nagłówka

Aby otworzyć widok **Nagłówek**, otworzyć folio, a następnie wybrać kartę **Nagłówek** w prawym górnym rogu nagłówka folio.

### <a name="settings-on-the-general-fasttab"></a>Ustawienia na skróconej karcie Ogólne

W poniższej tabeli opisano pola dostępne na skróconej karcie **Ogólne** w widoku **Nagłówka** folio.

| Pole | opis |
|---|---|
| Folio | Nazwa folio. Jest ona generowana automatycznie podczas tworzenia folio.|
| Podróż | Podróż związana z folio. |
| Broker urzędu celnego | Wybierz brokera celnego dla folio. Brokerzy celni są zdefiniowani dla dostawcy. Umożliwiają one automatyczne ustalane koszty utworzone. |
| Spedytorski lotniczy list przewozowy/list przewozowy | Określ list przewozowy lub list przewozowy dla folio. |
| Firma | Podmiot prawny (firma) powiązany z folio. |
| Identyfikator kontrolny ładunku | To pole jest używane przez działy celne w niektórych krajach lub regionach. |
| Miara | To pole umożliwia wyświetlanie miary określonej w module **Koszt z wyładunkiem**. Pomiary są często używane przez organizacje, które nie znają indywidualnej objętości lub wagi towarów, ale wymagają dokładniejszego podziału niż ilość lub ilość. Spedytor poda wagę lub miarkę sześcienną i możesz ją umieścić na poziomie towaru lub zamówienia. Może być aktualizowany automatycznie, jeśli parametr jest wybrany, lub wprowadzony ręcznie. |
| Jednostka miary | Jednostka stosowana dla określonej miary. |
| Liczba kartonów | Liczba kartonów w folio. To pole może być aktualizowane automatycznie w zależności od wybranego parametru. |
| Konto dostawcy | Wybierz dostawcę skojarzonego z folio. To pole jest używane wyłącznie w celach informacyjnych. Nie wpływa to na żadną funkcjonalność. |
| Imię i nazwisko | Nazwa wybranego konta dostawcy. |
| Uwagi | Służy do wprowadzania dodatkowych informacji powiązanych z folio. |
| Opis towarów | Umożliwia wybór opisu towarów, który pomaga w identyfikacji folio. Aby uzyskać więcej informacji, zobacz temat [Opis towaru](shipping-information-setup.md#description-of-goods). |
| Data szacowania | To pole jest powiązane ze stroną wprowadzania cła. W module **Koszt z wyładunkiem** będzie dla ustawionej w tym miejscu daty zostanie ustawiony kurs wymiany urzędu celnego. Domyślną wartością jest data na stronie wprowadzania cła. |
| Identyfikator płatności celnych | Wprowadź identyfikator cła. Ten identyfikator są dostarczane przez działy celne w krajach lub regionach. |
| Kod taryfy | Wprowadź kod taryfy, który ma zostać powiązany z folio. Kod ten jest zazwyczaj wymagany (i definiowany) w kraju lub regionie, do których jest wysyłana przesyłka. |

### <a name="settings-on-the-delivery-fasttab"></a>Ustawienia na skróconej karcie Dostawa

W poniższej tabeli opisano ustawienia dostępne na skróconej karcie **Dostawa** w widoku **Nagłówka** folio.

| Pole | opis |
|---|---|
| Data folio | Wybierz datę, która ma zostać powiązana z folio. Wartością domyślną jest data utworzenia podróży. |
| Szacowany czas przybycia w porcie wysyłki | Szacowany czas przybycia (ETA) do portu docelowego („do” portu). |
| Szacowana data dostawy | Zazwyczaj termin przybycia towarów do magazynu. To pole nie jest używane podczas obliczania szacowanej daty dostawy. (Zamiast tego jest używana szacowana data dostawy w ramach kontroli śledzenia). Aby ustawić to pole tak, aby wartość odpowiadała szacowanej dacie dostawy w ramach kontroli śledzenia, należy użyć funkcji za pomocą [Centrum kontroli śledzenia](delivery-information-setup.md#tracking-control-center). |
| Otrzymano oryginalne dokumenty | Data, kiedy otrzymano oryginalne dokumenty. |
| Polecony broker | Datę poinformowania brokera. |
| Wysłano oryginalny list przewozowy | Datę wysłania oryginalnego listu przewozowego. |
| Zwolnione towary | Data wydania towarów. |
| Termin odbiorcy | Data terminu dla odbiorcy. |
| Dostarczono do magazynu | Data dostarczenia towarów do magazynu. |
| Data weryfikacji | Data potwierdzenia. |
| Instrukcje dotyczące dostawy | Data otrzymania instrukcji dostawy. |
| Port źródłowy | Port, z którego wypływa rejs. |
| Port docelowy | Port, w którym kończy się podróż. Kontener wysyłkowy może mieć inny port, ponieważ statek może zatrzymywać się w wielu portach. |

### <a name="settings-on-the-export-fasttab"></a>Ustawienia na skróconej karcie Eksportuj

W poniższej tabeli opisano ustawienia dostępne na skróconej karcie **Eksportuj** w widoku **Nagłówka** folio.

| Pole | opis |
|---|---|
| Eksporter | Eksporter może być przechowywany na folio. W handlu zagranicznym zamówienie zakupu można wysłać do jednej firmy, ale odebrać towary od innej firmy. Śledzenie i dokumentacja są wymagane przez urząd celny. W tym miejscu można przechowywać nazwę i adres eksportera. |
| Imię i nazwisko | Nazwa wybranego eksportera. |

## <a name="lines-view"></a>Widok wierszy

Aby otworzyć widok **Wiersze**, otworzyć folio, a następnie wybrać kartę **Wiersze** w prawym górnym rogu nagłówka folio.

### <a name="information-on-the-folio-fasttab"></a>Informacje na skróconej karcie Folio

Skrócona karta **Folio** w widoku **Wierszy** zawiera informacje o folio. Większość z tych informacji będzie też wyświetlana w widoku **Nagłówek**, zgodnie z opisem opisanym powyżej w tym temacie.

### <a name="information-and-buttons-on-the-lines-fasttab"></a>Informacje i przyciski na skróconej karcie Wiersze

Skrócona karta **Wiersze** w widoku **Wiersze** zawiera szczegóły dotyczące poszczególnych pełnych lub częściowych wierszy zamówienia zakupu zawartych w bieżącym folio.

W poniższej tabeli opisano przyciski, które są dostępne bezpośrednio na skróconej **Wiersze** w widoku **Wiersze**.

| Przycisk | opis |
|---|---|
| Usuń | Usuń wybrany wiersz zamówienia zakupu z podróży. |
| Zapasy \> Transakcje | Wyświetl transakcje magazynowe dla wybranej linii zamówienia zakupu. Pamiętaj, że jeśli używasz towarów w transporcie, wyświetlane jest również oryginalne zamówienie i zamówienia towarów w transporcie. |
| Zapasy \> Wyświetl wymiary | Umożliwia otwarcie okna dialogowego, w którym można wybrać wymiary magazynowe wyświetlane dla wyświetlanych transakcji. |
| Odśwież | Zaktualizuj informacje związane z kwotą, wagą lub objętością wiersza wybranego wiersza zamówienia zakupu. |

### <a name="information-on-the-lines-details-fasttab"></a>Informacje na skróconej karcie Wiersze

Skrócona karta **Szczegóły wiersza** w widoku **Wiersze** pokazuje więcej informacji o wierszu zamówienia zakupu, który jest aktualnie wybrany na skróconej karcie **Wiersze**.
