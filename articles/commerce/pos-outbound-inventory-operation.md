---
title: Wychodząca operacja magazynowa w punkcie sprzedaży
description: W tym temacie opisano możliwości wychodzących operacji magazynowych w punkcie sprzedaży (POS).
author: hhaines
manager: annbe
ms.date: 07/30/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: hhaines
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.9
ms.openlocfilehash: b8f0daf96e782e5ba6c985847bad81312e48d30b
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4976621"
---
# <a name="outbound-inventory-operation-in-pos"></a>Wychodząca operacja magazynowa w punkcie sprzedaży

[!include [banner](includes/banner.md)]


W systemie Microsoft Dynamics 365 Commerce w wersji 10.0.10 lub późniejszych operacje przychodzące i wychodzące w punkcie sprzedaży (POS) zastępują operację pobrania i przyjęcia.

> [!NOTE]
> W wersji 10.0.10 lub nowszej każda nowa funkcja w punkcie sprzedaży, która jest związana z odbieraniem zapasów sklepu z zamówieniami zakupu i zamówieniami przeniesienia, zostanie dodana do operacji przychodzących. Jeśli obecnie jest używana operacja pobrania i przyjęcia w punkcie sprzedaży, zaleca się opracowanie strategii przenoszenia z tej operacji do nowych operacji przychodzących i wychodzących. Mimo że operacja pobrania i przyjęcia nie zostanie usunięta z produktu, nie będzie już można w niej zainwestować, z perspektywy funkcjonalnej lub wydajności po wersji 10.0.9.

## <a name="prerequisite-configure-an-asynchronous-document-framework"></a>Wymaganie wstępne: Skonfiguruj strukturę dokumentów asynchronicznych

Operacja wychodząca obejmuje udoskonalenia wydajności zapewniające, że użytkownicy, którzy mają wysokie ilości księgowania przyjęć w wielu sklepach lub firmach, oraz duże dokumenty dot. zapasów, mogą przetwarzać te dokumenty w module Centrali Commerceheadquarters (HQ) bez kłopotów z limitami czasu oraz bez błędów. Te udoskonalenia wymagają użycia struktury dokumentów asynchronicznych.

Gdy jest używana struktura dokumentów asynchronicznych, można przekazać zmiany dokumentów wychodzących z puktu sprzedaży do Centrali Commerce headquarters (HQ), a następnie przenieść je do innych zadań, gdy przetwarzanie w Centrali Commerce headquarters (HQ) odbywa się w tle. Stan dokumentu można sprawdzić na stronie listy dokumentów **Operacji wychodzących** w punkcie sprzedaży, aby upewnić się, że Księgowanie zakończyło się pomyślnie. W aplikacji punktu sprzedaży można również skorzystać z listy dokumentów aktywnej dla operacji wychodzącej, aby wyświetlić dokumenty, których nie można było zaksięgować w Centrali Commerce headquarters (HQ). Jeśli dokument nie powiedzie się, użytkownicy punktu sprzedaży będą mogli wprowadzać poprawki, a następnie ponownie próbować przetworzyć go w Centrali Commerce headquarters (HQ).

> [!IMPORTANT]
> Należy skonfigurować strukturę dokumentów asynchronicznych, zanim firma podejmie próbę użycia operacji wychodzącej w punkcie sprzedaży.

Aby skonfigurować strukturę dokumentów asynchronicznych, należy wykonać następujące procedury:

### <a name="create-and-configure-a-number-sequence"></a>Utwórz i skonfiguruj sekwencję numerów

1. Wybierz kolejno opcje **Administrowanie organizacją \> Numery kolejne \> Numery kolejne**.
2. Na stronie **Numery kolejne** utwórz dwie nowe sekwencje numerów.
3. W polach **Kod sekwencji numerów** i **nazwa** wprowadź wartości zdefiniowane przez użytkownika.
4. Na skróconej karcie **Referencje** wybierz pozycję **Dodaj**.
5. W polu **Obszar** wybierz **Parametry rozwiązania Commerce**.
6. W polu **referencje** wybierz **Identyfikator operacji dokumentu sieci sprzedaży**.
7. Na skróconej karcie **Ogólne** w sekcji **Konfiguracja** ustaw opcję **Ciągłe** na wartość **Nie**, aby upewnić się, że nie występują żadne problemy z wydajnością.

### <a name="create-and-schedule-two-batch-jobs-for-the-document-processing-and-monitoring-tasks"></a>Utwórz i Zaplanuj dwa zadania wsadowe dla zadań przetwarzania dokumentów i monitorowania

> [!NOTE]
> W Commerce w wersji 10.0.13 lub nowszej nie trzeba konfigurować zadań wsadowych za pomocą struktury zadań wsadowych. Procesy wsadowe można konfigurować za pomocą menu **Retail i Commerce > Retail i Commerce — składniki IT**. Aby skonfigurować zadania wsadowe, należy skorzystać z opcji menu **Detaliczny monitor operacji dokumentów** oraz z **Przetwarzanie operacji na dokumentach detalicznych**

Tworzone zadania wsadowe będą używane do przetwarzania dokumentów, które nie powiodą się lub przekroczą limit czasu. Będą one również używane, gdy liczba aktywnych dokumentów magazynowych, które są przetwarzane z punktu sprzedaży, przekracza wartość skonfigurowaną przez system.

1. Wybierz kolejno opcje **Administrowanie systemem \> Zapytania \> Zadania wsadowe**.
2. Na stronie **Zadanie wsadowe** utwórz dwa zadania wsadowe:

    - Skonfiguruj jedno zadanie do uruchamiania klasy **RetailDocumentOperationMonitorBatch**.
    - Skonfiguruj inne zadanie do uruchamiania klasy **RetailDocumentOperationProcessingBatch**.

3. Umożliwia zaplanowanie nowych zadań wsadowych, które będą uruchamiane cyklicznie. Na przykład można skonfigurować harmonogram, tak aby zadania były uruchamiane co pięć minut.

## <a name="prerequisite-add-outbound-operation-to-the-pos-screen-layout"></a>Wymaganie wstępne: Dodaj operację wychodzącą do układu ekranu punktu sprzedaży

Zanim organizacja będzie mogła skorzystać z funkcji operacji wychodzących, musi skonfigurować **operację wychodzącą** w punkcie sprzedaży w jednym lub kilku [układach ekranu punktu sprzedaży](https://docs.microsoft.com/dynamics365/unified-operations/retail/pos-screen-layouts). Przed wdrożeniem nowej operacji w środowisku produkcyjnym należy upewnić się, że została ona gruntownie przetestowana i przeszkolić użytkowników do jej używania.

## <a name="overview"></a>Omówienie

Użytkownicy punktu sprzedaży dotyczącego operacji wchodzących wykonują następujące zadania:

- Księgowanie wysyłek dla dokumentów zamówień przeniesienia, w przypadku których sklep użytkownika jest wyznaczonym magazynem wychodzącym.
- Wyświetlanie informacji o historycznych wysyłkach zamówień przeniesienia, które zostały zaksięgowane przez sklep.
- Tworzenie nowego żądania wchodzącego zamówienia przeniesienia.

Po rozpoczęciu operacji wchodzącej z poziomu aplikacji punktu sprzedaży wyświetlany jest widok strony listy. Ten widok pokazuje otwarte dokumenty zlecenia przeniesienia, które mają wiersze zapasów, które bieżący sklep użytkownika ma wysłać i zrealizować. Aby znaleźć i wybrać dokument, użytkownicy mogą przewijać listę lub skorzystać z funkcji wyszukiwania.

Lista dokumentów zapasów wchodzących zawiera trzy karty.

- **Aktywna** — na tej karcie są wyświetlane zamówienia przeniesienia ze stanem **Wnioskowane** lub **Częściowo wysłane** Zamówienia zawierają wiersze lub ilości w wierszach, które muszą zostać wysłane przez bieżący sklep użytkownika. Na tej karcie wyświetlane są również zamówienia, które mają stan **Przetwarzanie w centrali** (czyli oczekiwanie na potwierdzenie pomyślnego księgowania z Centali Commerce headquarters (HQ)) lub **Przetwarzanie nie powiodło się** (to znaczy, że księgowanie w Centrali Commerce headquarters (HQ) nie powiodło się, a użytkownik musi poprawić dane i ponowić próbę przesłania zamówień).
- **Wersja robocza** — na tej karcie są wyświetlane nowe żądania wychodzącego zamówienia przeniesienia, które utworzono w sklepie użytkownika. Jednak dokumenty zostały zapisane lokalnie. Nie zostały one jeszcze przesłane do Centrali Commerce headquarters (HQ) w celu przetworzenia.
- **Zakończone** — na tej karcie jest wyświetlana lista dokumentów przeniesienia zakupu, które sklep w pełni wysłał w ciągu ostatnich siedmiu dni. Ta karta jest używana wyłącznie w celach informacyjnych. Wszystkie informacje o dokumentach są tylko do odczytu dla sklepu.

W przypadku wyświetlania dokumentów na dowolnej z tych kart pole **Stan** może pomóc w zrozumieniu etapu, w którym znajduje się dokument.

- **Wersja robocza** — dokument zamówienia przeniesienia został zapisany lokalnie tylko w bazie danych kanału sklepu. Żadne informacje dotyczące wniosku o zamówienie przeniesienia nie zostały jeszcze przesłane do Centrali Commerce headquarters (HQ).
- **Zażądano** — zamówienie zakupu lub zamówienie przeniesienia zostało utworzone w module Centrali Commerce headquarters (HQ) i jest w pełni otwarte. Bieżący sklep użytkownika jeszcze przetworzył wszelkie wysyłki w odniesieniu do dokumentu.
- **Częściowo wysłano** — dokument zamówienia przeniesienia zawiera jedną lub więcej wierszy lub częściową, które zostały zaksięgowane jako wysłane przez magazyn wychodzący. Wiersze wysłane są dostępne do odebrania w ramach operacji przychodzącej.
- **W pełni wysłane** — zlecenie przesunięcia zawierało wszystkie wiersze i pełne ilości wierszy zaksięgowane jako wysłane przez magazyn wychodzący.
- **W toku** — ten stan jest używany do informowania użytkowników urządzenia, że dokument jest aktywnie opracowywany przez innego użytkownika.
- **Wstrzymana** — ten stan jest pokazywany po wybraniu opcji **Wstrzymaj przyjmowanie** w celu tymczasowego zatrzymania procesu przyjmowania.
- **Przetwarzanie w Centrali** — dokument został przesłany do Centrali Commerce headquarters (HQ) z aplikacji punktu sprzedaży, ale nie został jeszcze zaksięgowany pomyślnie w Centrali Commerce headquarters (HQ). Dokument przechodzi przez proces asynchronicznego księgowania dokumentu. Po pomyślnym zaksięgowaniu dokumentu w module Commerce headquarters (HQ) jego stan powinien zostać zaktualizowany do **w pełni odebranego** lub **częściowo odebranego**.
- **Przetwarzanie nie powiodło się** — dokument został zaksięgowany w Centrali Commerce headquarters (HQ) i odrzucony. W **Szczegółach** jest wyświetlana przyczyna niepowodzenia księgowania. Dokument musi być edytowany w celu usunięcia problemów z danymi, a następnie musi zostać ponownie przesłany do Centrali Commerce headquarters (HQ) w celu przetworzenia.

Po wybraniu wiersza dokumentu z listy zostanie wyświetlone okienko **Szczegółów**. W tym okienku są wyświetlane dodatkowe informacje o dokumencie, takie jak informacje o wysyłce i dacie. Na pasku postępu widać, ile towarów trzeba będzie przetworzyć. Jeśli dokument nie został pomyślnie przetworzony w Centrali Commerce headquarters (HQ), w okienku **Szczegółów** są wyświetlane także komunikaty o błędach związane z tym niepowodzeniem.

W widoku strony listy dokumentów możesz wybrać **Szczegóły zamówienia** na pasku aplikacji, aby wyświetlić szczegóły dokumentu. Można również uaktywnić przetwarzanie paragonów w uprawnionych wierszach dokumentu.

W widoku strony listy dokumentów można również utworzyć nowe zamówienia przeniesienia wchodzącego dla sklepu.

## <a name="transfer-order-shipping-process"></a>Proces wysyłania zamówienia przeniesienia

Po wybraniu dokumentu zamówienia przeniesienia na karcie **Aktywne** można wybrać **Szczegóły zamówienia**, aby rozpocząć proces wypełniania. Zostanie wyświetlony widok **Pełna lista zamówień**. Na tej stronie są wyświetlane wszystkie wiersze dokumentu zawierające dany towar. Zawiera także szczegóły zamówionej ilości.

Każde skanowanie kodu kreskowego aktualizuje ilość w polu **Wysyłane teraz** o jedną jednostkę. Można również wprowadzić ilość wysyłkową, wybierając **Wyślij produkt** dostarczany na pasku aplikacji, wprowadzić identyfikator towaru, a następnie wprowadzając ilość. Jeśli towar jest objęty kontrolą lokalizacji, można potwierdzić lub skonfigurować lokalizację wysyłki dla wiersza dokumentu.

W widoku **Pełna lista zamówień** można ręcznie wybrać wiersz z listy, a następnie zaktualizować ilość **Wysyłane teraz** dla wybranego wiersza w okienku **Szczegółów**.

### <a name="over-delivery-shipping-validations"></a>Sprawdzanie poprawności nadwyżki w wysyłce

Sprawdzanie poprawności nastąpiło podczas procesu odbierania dla wierszy dokumentu. Obejmują one sprawdzanie nadwyżki w dostawie. Jeśli użytkownik spróbuje uzyskać więcej zapasów niż zamówiono w zamówieniu zakupu, ale nadwyżka w dostawie nie jest skonfigurowana lub otrzymana ilość przekracza tolerancję nadwyżki w dostawie skonfigurowaną dla wiersza zamówienia zakupu, zostanie wyświetlony błąd i nie można przyjąć nadmiarowej ilości.

### <a name="underdelivery-close-lines"></a>Wiersze zamknięcia niedoboru w dostawie

W aplikacji Commerce w wersji 10.0.12 dodano funkcjonalność, dzięki której użytkownicy punktu sprzedaży mogą zamykać lub anulować pozostałe ilości podczas wysyłki zamówienia wychodzącego, jeśli magazyn wychodzący ustali, że nie może wysłać pełnej żądanej ilości. Ilości można także zamknąć lub anulować później. Aby korzystać z tej możliwości, firma musi być skonfigurowana tak, aby zezwalać na niedobór w dostawie zamówień przeniesienia. Ponadto dla wiersza zamówienia przeniesienia musi zostać wartość procentowa niedoboru w dostawie.

Aby skonfigurować firmę tak, aby zezwalała na niedobór w dostawie zamówień przeniesienia w module Commerce headquarters (HQ), przejdź do pozycji **Zarządzanie zapasami \> Ustawienia \> Parametry modułu Zarządzanie zapasami i magazynem**. Na stronie **Parametry modułu Zarządzanie zapasami i magazynem** na karcie **Zamówienia przeniesienia** włącz parametr **Akceptacja niedoboru w dostawie**. Następnie uruchom **1070** zadanie harmonogramu dystrybucji w celu zsynchronizowania zmian parametrów w kanale sklepu.

Wartości procentowe niedoboru w dostawie dla wiersza zamówienia przeniesienia mogą być wstępnie zdefiniowane dla produktów jako część konfiguracji produktu w module Commerce Headquarters. Można je również ustawić lub zastąpić w określonym wierszu zamówienia przeniesienia za pośrednictwem modułu Commerce headquarters (HQ).

Po zakończeniu konfigurowania niedoboru w dostawie zamówień przeniesienia w organizacji użytkownicy punktu sprzedaży będą widzieć nową opcję **Zamknij pozostałą ilość** w okienku **Szczegóły**, gdy zostanie wybrany wiersz zamówienia przeniesienia wychodzącego za pośrednictwem funkcji **operacji wychodzącej**. Następnie, gdy użytkownik zakończy wysyłkę przy użyciu operacji **Zakończ realizację**, będą mogli wysłać żądanie do modułu Commerce Headquarters (HQ), aby anulować pozostałą niewysłaną ilość. Jeśli użytkownik zamknie pozostałej ilości, aplikacja Commerce zweryfikuje, czy anulowana ilość mieści się w tolerancji procentowej wartości niedoboru w dostawie określonej w wierszu zamówienia przeniesienia. Jeśli przekroczona zostanie tolerancja niedostatecznej dostawy, zostanie wyświetlony komunikat o błędzie, a użytkownik nie będzie w stanie zamknąć pozostałej ilości, dopóki poprzednio wysłana i „wyślij teraz” ilość nie osiągnie lub nie przekroczy tolerancji niedostatecznej dostawy.

Po zsynchronizowaniu wysyłki z modułem Commerce Headquarters (HQ) ilości określone w polu **Wyślij teraz** dla wiersza zamówienia przeniesienia w punkcie sprzedaży są aktualizowane do stanu wysłania w module Commerce Headquarters (HQ). Niewysłane ilości, które wcześniej byłyby uznane za ilości „pozostałe do wysłania” (czyli ilości, które zostaną wysłane później) zostaną w zamian uznane za ilości anulowane. Ilość „pozostała do wysłania” dla wiersza zamówienia przeniesienia jest równa **0** (zero), a wiersz jest uznawany za całkowicie wysłany.

### <a name="shipping-location-controlled-items"></a>Towary kontrolowane w lokalizacji wysyłki

Jeśli wysyłane produkty są kontrolowane pod względem lokalizacji, użytkownicy mogą wybrać lokalizację, z której chcą wystawić zapasy podczas procesu wysyłki. Zaleca się skonfigurowanie domyślnej lokalizacji sprawy dla magazynu sklepu, aby ten proces był bardziej wydajny. Nawet w przypadku skonfigurowania lokalizacji domyślnej użytkownicy mogą zastępować lokalizację sprawy w wybranych wierszach w miarę ich obowiązywania.

Operacja uwzględnia konfigurację **Dozwolony pusty przychód** dla pozycji **lokalizacji** w wymiarze przechowywania i nie wymaga wprowadzenia wymiaru lokalizacji, jeśli jest skonfigurowany pusty przychód. Jeśli puste lokalizacje przychodu nie są dozwolone dla towaru, w aplikacji punktu sprzedaży jest wyświetlany komunikat o błędzie i wymagane jest wprowadzenie lokalizacji przed zaksięgowaniem przychodu.

### <a name="ship-all"></a>Wyślij wszystko

Jeśli jest to wymagane, można wybrać opcję **Wyślij wszystko** na pasku aplikacji, aby szybko zaktualizować ilość **Wysyłane teraz** dla wszystkich wierszy dokumentu do wartości maksymalnej, która jest dostępna do realizacji dla tych wierszy.

### <a name="cancel-fulfillment"></a>Anuluj realizację

Funkcji **Anulowanie realizacji** należy użyć na pasku aplikacji tylko wtedy, gdy chcesz wycofać się z dokumentu i nie chcesz zapisywać żadnych zmian. Na przykład początkowo zaznaczono niewłaściwy dokument i nie ma potrzeby zapisywania żadnego z poprzednich danych wysyłki.

### <a name="pause-fulfillment"></a>Wstrzymaj realizację

W przypadku realizacji zamówienia przeniesienia można użyć funkcji **Wstrzymaj realizację**, jeśli proces ma zostać podzielony od procesu. Na przykład można wykonać inną operację z punktu sprzedaży, na przykład dzwonienie do sprzedaży odbiorcy lub opóźnienie księgowania wysyłki do Centrali Commerce headquarters (HQ).

Po wybraniu opcji **Wstrzymaj realizację** stan dokumentu zostanie zmieniony na **Wstrzymany**. Dlatego użytkownick będzie wiedzieć, że wprowadzono dane do dokumentu, ale dokument nie został jeszcze zatwierdzony. Aby wznowić proces realizacji, wybierz wstrzymany dokument, a następnie wybierz **Szczegóły zamówienia**. Wszystkie **Wysyłane teraz** ilości odbieranych towarów są zachowywane i można je przeglądać z poziomu widoku **Pełna lista zamówień**.

### <a name="review"></a>Przegląd

Przed ostatecznym zaangażowaniem realizacji modułu Commerce Headquarter (HQ) można użyć funkcji **Przeglądu** w celu sprawdzenia dokumentu wychodzącego. Ta funkcja informuje użytkownika o brakujących lub niepoprawnych danych, które mogą spowodować błąd przetwarzania, i umożliwia naprawienie problemów przed przesłaniem żądania realizacji. Aby włączyć funkcję **Przeglądu** na pasku aplikacji, włącz opcję **Włącz walidację w przychodzących i wychodzących operacjach magazynowych POS** w Zarządzaniu funkcjami w Commerce Headquarter (HQ).

Funkcja **Przeglądu** sprawdza poprawność następujących problemów w dokumencie wychodzącym:
- **Nadwyżka w wysyłce** — ilość wysyłana teraz jest większa niż zamówiona Ilość. Waga tego zagadnienia jest określana na podstawie konfiguracji nadwyżki w module Commerce Headquarter (HQ).
- **Niedostateczna wysyłka** — ilość wysyłana teraz jest mniejsza niż zamówiona Ilość. Waga tego zagadnienia jest określana na podstawie konfiguracji niedoboru w module Commerce Headquarter (HQ).
- **Numer seryjny** — numer seryjny nie został podany lub nie jest dostępny dla towaru seryjnego, który wymaga zarejestrowania numeru seryjnego w magazynie.
- **Lokalizacja nie ustawiona** — nie określono lokalizacji dla pozycji kontrolowanej w lokalizacji, w której lokalizacja nie może być pusta.
- **Usunięte wiersze** — Zamówienie zawiera wiersze usunięte przez użytkownika z modułu Commerce Headquarter (HQ), który nie jest znany w aplikacji punktu sprzedaży.

Jeśli dla parametru **Włącz automatyczne sprawdzanie poprawności** zostanie ustawiona wartość **Tak** w **Parametry Commerce** > **Zapasy** > **Operacje magazynowe w sklepie**, sprawdzanie poprawności jest wykonywane automatycznie po wybraniu funkcji **Zakończ realizację**.

### <a name="finish-fulfillment"></a>Zakończ realizację

Po zakończeniu wprowadzania wszystkich ilości **Wysyłane teraz** dla produktów należy wybrać opcję **Zakończ realizację** na pasku aplikacji.

Gdy jest używane przetwarzanie dokumentów asynchronicznych, paragon jest przesyłany za pośrednictwem struktury dokumentów asynchronicznych. Czas potrzebny na zaksięgowanie dokumentu jest zależny od rozmiaru dokumentu (liczby wierszy) i ogólnego ruchu przetwarzania występującego na serwerze. Zazwyczaj proces ten odbywa się w ciągu kilku sekund. Jeśli Księgowanie dokumentu nie powiedzie się, użytkownik zostanie powiadomiony za pośrednictwem listy dokumentów **Operacja wychodząca** na karcie **Aktywne**, gdzie stan dokumentu zostanie zaktualizowany jako **Proces nie powiódł się**. Użytkownik może następnie wybrać nieuszkodzony dokument w punkcie sprzedaży, aby wyświetlić komunikaty o błędach oraz przyczynę niepowodzenia w okienku **Szczegółów**. Uszkodzony dokument pozostaje niezaksięgowany i wymaga powrotu użytkownika do wierszy dokumentu przez wybranie **Szczegółów zamówienia** w punkcie sprzedaży. Użytkownik musi wówczas zaktualizować dokument, używając korekt, na podstawie błędów. Po poprawieniu dokumentu użytkownik może spróbować ponownie go przetworzyć, wybierając opcję **Zakończ realizację** na pasku aplikacji.

## <a name="create-an-outbound-transfer-order"></a>Utworzenie wychodzącego zamówienia przeniesienia

Z punktu sprzedaży użytkownicy mogą tworzyć nowe dokumenty zamówienia przeniesienia. Aby rozpocząć proces, należy wybrać opcję **Nowy** na pasku aplikacji, gdy znajdujesz się na liście głównych dokumentów **Operacji wychodzących**. Następnie zostanie wyświetlony monit o wybranie **Przeniesienia do** magazynu lub sklepu, do którego obecny sklep wyśle zapasy. Wartości są ograniczone do wyboru zdefiniowanego w konfiguracji grupy realizacji sklepu. W żądaniu przeniesienia wychodzącego bieżący sklep będzie zawsze **Przenoszony z** magazynu dla zamówienia przeniesienia. Tej wartości nie można zmienić.

W razie konieczności można wprowadzić wartości w polach **Data wysyłki**, **Data odebrania** i **Metoda dostawy**. Można również dodać notatkę, która będzie przechowywana razem z nagłówkiem zamówienia przeniesienia, jako załącznik do dokumentu w Centrali Commerce headquarters (HQ).

Po utworzeniu informacji nagłówka można dodać produkty do zamówienia przeniesienia. Aby rozpocząć proces dodawania towarów i żądanych ilości, zeskanuj kody kreskowe lub wybierz pozycję **Dodaj produkt**.

Po wprowadzeniu wierszy w zamówieniu przeniesienia wychodzącego należy wybrać opcję **Zapisz**, aby zapisać zmiany w dokumencie lokalnie lub **Przeslij żądanie**, aby przesłać szczegóły zamówienia do Centrali Commerce headquarters (HQ) w celu dalszego przetwarzania. Jeśli zostanie wybrana **Zapisz**, dokument wersji roboczej zostanie zapisany w bazie danych kanału, a magazyn wychodzący nie będzie mógł uruchomić dokumentu, dopóki nie zostanie on pomyślnie przetworzony przez **Prześlij żądanie**. Wybierz **Zapisz** tylko w przypadku, gdy nie można zatwierdzić żądania w celu przetworzenia w Centrali Commerce headquarters (HQ).

Jeśli dokument jest zapisany lokalnie, można go znaleźć na karcie **Wersje robocze** na liście dokumentów dla **Operacji przychodzących**. Gdy dokument jest w stanie **Wersji roboczej**, można go edytować, wybierając **Edytuj**. W razie konieczności można zaktualizować, dodać lub usunąć wiersze. Można również usunąć cały dokument, gdy jest on w stanie **Wersji roboczej**, zaznaczając opcję **Usuń** na karcie **Wersje robocze**.

Po pomyślnym przesłaniu wersji roboczej do modułu Commerce Headquarters (HQ) zostanie ona wyświetlona na karcie **Aktywne** i stan zmieni się na **Wnioskowane**. W tym momencie tylko użytkownicy z magazynu wychodzącego mogą edytować dokument, wybierając **Operację wychodzącą** w aplikacji punktu sprzedaży. Użytkownicy w magazynie przychodzącym mogą wyświetlać zamówienie przeniesienia na karcie **Aktywne** na liście dokumentów **Operacja przychodząca**, ale nie mogą ich edytować ani usuwać. Blokada edycji zapewnia, że nie występują żadne konflikty, ponieważ przychodzący zleceniodawca zmienia zamówienie przeniesienia w tym samym czasie, gdy wychodzący spedytor będzie aktywnie pobierał i wysyłał zamówienie. Jeśli po przesłaniu zamówienia przeniesienia wymagane są zmiany z magazynu lub magazynu przychodzącego, należy skontaktować się z odbiorcą w sprawie wychodzącego spedytora i poprosić o wprowadzenie zmian.

Po zmiany stanu na **Wnioskowane** jest on gotowy do przetworzenia przez magazyn wychodzący. Ponieważ przesyłka jest przetwarzana przy użyciu operacji wychodzącej, status dokumentów zlecenia przeniesienia jest aktualizowany na z **Wnioskowany** do **Wysłane** lub **Częściowo wysłane**. Gdy dokumenty są w stanie **W pełni wysłane** lub **Częściowo wysłane**, magazyn lub magazyn przychodzący może zaksięgować przychody z nich przy użyciu procesu przyjęcia operacji przychodzącej.

W pełni wysłane zamówienia przeniesienia są przenoszone na kartę **Zakończone** na liście dokumentów **Operacji wychodzącej**. Są one widoczne dla użytkowników w magazynie lub sklepie wychodzącym, w trybie tylko do odczytu, przez siedem dni.

## <a name="related-topics"></a>Powiązane tematy

[Operacja zapasów przychodzących w punkcie sprzedaży](pos-inbound-inventory-operation.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]