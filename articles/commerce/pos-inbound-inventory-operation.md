---
title: Operacja zapasów przychodzących w punkcie sprzedaży
description: W tym temacie opisano możliwości przychodzących operacji magazynowych w punkcie sprzedaży (POS).
author: hhaines
manager: annbe
ms.date: 09/17/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: hhaines
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.9
ms.openlocfilehash: 89021a85c2b215695d7cc25215c049205f71956d
ms.sourcegitcommit: 6e0d6d291d4881b16a677373f712a235e129b632
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/08/2020
ms.locfileid: "3971504"
---
# <a name="inbound-inventory-operation-in-pos"></a>Operacja zapasów przychodzących w punkcie sprzedaży

[!include [banner](includes/banner.md)]

W systemie Microsoft Dynamics 365 Commerce w wersji 10.0.10 lub późniejszych operacje przychodzące i wychodzące w punkcie sprzedaży (POS) zastępują operację pobrania i przyjęcia.

> [!NOTE]
> W wersji 10.0.10 Commerce lub nowszej każda nowa funkcja w punkcie sprzedaży, która jest związana z odbieraniem zapasów sklepu z zamówieniami zakupu i zamówieniami przeniesienia, zostanie dodana do operacji w punkcie sprzedaży dla **operacji przychodzących**. Jeśli obecnie jest używana operacja pobrania i przyjęcia w punkcie sprzedaży, zaleca się opracowanie strategii przenoszenia z tej operacji do nowych operacji przychodzących i wychodzących. Mimo że operacja pobrania i przyjęcia nie zostanie usunięta z produktu, nie będzie już można w niej zainwestować, z perspektywy funkcjonalnej lub wydajności po wersji 10.0.9.

## <a name="prerequisite-configure-an-asynchronous-document-framework"></a>Wymaganie wstępne: Skonfiguruj strukturę dokumentów asynchronicznych

Operacja przychodząca obejmuje udoskonalenia wydajności zapewniające, że użytkownicy, którzy mają wysokie ilości księgowania przyjęć w wielu sklepach lub firmach, oraz duże dokumenty dot. zapasów, mogą przetwarzać te dokumenty w module Centrali Commerce bez kłopotów z limitami czasu oraz bez błędów. Te udoskonalenia wymagają użycia struktury dokumentów asynchronicznych.

Gdy jest używana struktura dokumentów asynchronicznych, można przekazać zmiany dokumentów przychodzących z puktu sprzedaży do Centrali Commerce, a następnie przenieść je do innych zadań, gdy przetwarzanie w Centrali Commerce odbywa się w tle. Stan dokumentu można sprawdzić na stronie listy dokumentów **Operacji przychodzących** w punkcie sprzedaży, aby upewnić się, że Księgowanie zakończyło się pomyślnie. W aplikacji punktu sprzedaży można również skorzystać z listy dokumentów aktywnej dla operacji przychodzącej, aby wyświetlić dokumenty, których nie można było zaksięgować w Centrali Commerce. Jeśli dokument nie powiedzie się, użytkownicy punktu sprzedaży będą mogli wprowadzać poprawki, a następnie ponownie próbować przetworzyć go w Centrali Commerce.

> [!IMPORTANT]
> Należy skonfigurować strukturę dokumentów asynchronicznych, zanim firma podejmie próbę użycia operacji przychodzącej w punkcie sprzedaży.

Aby skonfigurować strukturę dokumentów asynchronicznych, należy wykonać następujące procedury:

### <a name="create-and-configure-a-number-sequence"></a>Utwórz i skonfiguruj sekwencję numerów

1. Wybierz kolejno opcje **Administrowanie organizacją \> Numery kolejne \> Numery kolejne**.
2. Na stronie **Numery kolejne** utwórz dwie nowe sekwencje numerów.
3. W polach **Kod sekwencji numerów** i **nazwa** wprowadź wartości zdefiniowane przez użytkownika.
4. Na skróconej karcie **Referencje** wybierz pozycję **Dodaj**.
5. W polu **Obszar** wybierz **Parametry rozwiązania Commerce**.
4. W polu **referencje** wybierz **Identyfikator operacji dokumentu sieci sprzedaży**.
5. Na skróconej karcie **Ogólne** w sekcji **Konfiguracja** ustaw opcję **Ciągłe** na wartość **Nie**, aby upewnić się, że nie występują żadne problemy z wydajnością.

### <a name="create-and-schedule-two-batch-jobs-for-the-document-processing-and-monitoring-tasks"></a>Utwórz i Zaplanuj dwa zadania wsadowe dla zadań przetwarzania dokumentów i monitorowania

> [!NOTE]
> W Commerce w wersji 10.0.13 lub nowszej nie trzeba konfigurować zadań wsadowych za pomocą struktury zadań wsadowych. Procesy wsadowe można konfigurować za pomocą menu **Retail i Commerce > Retail i Commerce — składniki IT**. Aby skonfigurować zadania wsadowe, należy skorzystać z opcji menu **Detaliczny monitor operacji dokumentów** oraz z **Przetwarzanie operacji na dokumentach detalicznych**.

Tworzone zadania wsadowe będą używane do przetwarzania dokumentów, które nie powiodą się lub przekroczą limit czasu. Będą one również używane, gdy liczba aktywnych dokumentów magazynowych, które są przetwarzane z punktu sprzedaży, przekracza wartość skonfigurowaną przez system.

1. Wybierz kolejno opcje **Administrowanie systemem \> Zapytania \> Zadania wsadowe**.
2. Na stronie **Zadanie wsadowe** utwórz dwa zadania wsadowe:

    - Skonfiguruj jedno zadanie do uruchamiania klasy **RetailDocumentOperationMonitorBatch**.
    - Skonfiguruj inne zadanie do uruchamiania klasy **RetailDocumentOperationProcessingBatch**.

2. Umożliwia zaplanowanie nowych zadań wsadowych, które będą uruchamiane cyklicznie. Na przykład można skonfigurować harmonogram, tak aby zadania były uruchamiane co pięć minut.

## <a name="prerequisite-add-inbound-operation-to-the-pos-screen-layout"></a>Wymaganie wstępne: Dodaj operację przychodzącą do układu ekranu punktu sprzedaży

Zanim organizacja będzie mogła skorzystać z funkcji operacji przychodzących, musi skonfigurować **operację przychodzącą** w punkcie sprzedaży w jednym lub kilku [układach ekranu punktu sprzedaży](https://docs.microsoft.com/dynamics365/unified-operations/retail/pos-screen-layouts). Przed wdrożeniem nowej operacji w środowisku produkcyjnym należy upewnić się, że została ona gruntownie przetestowana i przeszkolić użytkowników do jej używania.

## <a name="overview"></a>Omówienie

Użytkownicy punktu sprzedaży dotyczącego operacji przychodzących wykonują następujące zadania:

- Umożliwia odebranie zapasów w magazynie sklepu z poziomu dokumentów potwierdzonych zamówień zakupu lub wysłanych zamówień przeniesienia.
- Umożliwia wyświetlenie informacji o historycznych przychodach zapasów na okres siedmiu dni od dnia, w którym dokument został w pełni przyjęty.
- Tworzenie nowego żądania przychodzącego zamówienia przeniesienia.

Po rozpoczęciu operacji przychodzącej z poziomu aplikacji punktu sprzedaży wyświetlany jest widok strony listy. Ten widok pokazuje otwarte zamówienia zakupu i zamówienia przeniesienia z wierszami zapasów, które są planowane do odebrania przez bieżący sklep. Aby znaleźć i wybrać określony dokument, użytkownicy mogą przewijać listę lub skorzystać z funkcji wyszukiwania.

Lista dokumentów zapasów przychodzących zawiera trzy karty:

- **Aktywne** — na tej karcie są wyświetlane dokumenty, które są w pełni lub częściowo otwarte oraz które zawierają wiersze lub ilości na wierszach, które muszą być wciąż otrzymane.
- **Wersja robocza** — na tej karcie są wyświetlane nowe żądania przychodzącego zamówienia przeniesienia, które utworzono w sklepie. Jednak dokumenty zostały zapisane lokalnie. Nie zostały one jeszcze przesłane do Centrali Commerce w celu przetworzenia.
- **Zakończone** — na tej karcie jest wyświetlana lista dokumentów zamówień zakupu lub zamówień przeniesienia, które sklep w pełni odebrał w ciągu ostatnich siedmiu dni. Ta karta jest używana wyłącznie w celach informacyjnych. Wszystkie informacje o dokumentach są tylko do odczytu dla sklepu.

W przypadku wyświetlania dokumentów na dowolnej z tych kart pole **Stan** może pomóc w zrozumieniu etapu, w którym znajduje się dokument.

- **Wersja robocza** — dokument zamówienia przeniesienia został zapisany lokalnie tylko w bazie danych kanału sklepu. Żadne informacje dotyczące wniosku o zamówienie przeniesienia nie zostały jeszcze przesłane do Centrali Commerce.
- **Zażądano** — zamówienie zakupu lub zamówienie przeniesienia zostało utworzone w module Centrali Commerce i jest w pełni otwarte. Nie przetworzono jeszcze żadnych przychodów z dokumentu. W przypadku dokumentów typu dokument zamówienia zakupu przyjęcie może się rozpocząć w dowolnym momencie, w którym stan jest **Wnioskowany**.
- **Częściowo wysłano** — dokument zamówienia przeniesienia zawiera jedną lub więcej wierszy lub częściową, które zostały zaksięgowane jako wysłane przez magazyn wychodzący. Wiersze wysłane są dostępne do odebrania w ramach operacji przychodzącej.
- **W pełni wysłane** — zlecenie przesunięcia zawierało wszystkie wiersze i pełne ilości wierszy zaksięgowane jako wysłane przez magazyn wychodzący. Cały dokument jest dostępny do odebrania w ramach operacji przychodzącej.
- **Częściowo odebrane** — niektóre wiersze lub ilości w wierszu w zamówieniu zakupu lub dokumencie zamówienia przeniesienia zostały odebrane przez sklep, ale niektóre wiersze pozostają otwarte.
- **W pełni odebrano** — wszystkie wiersze i ilości z zamówienia zakupu lub dokumentu zamówienia przeniesienia zostały w pełni odebrane. Dokumenty są dostępne tylko na karcie **Pełne** i są tylko do odczytu przez użytkowników sklepów.
- **W toku** — ten stan jest używany do informowania użytkowników urządzenia, że dokument jest aktywnie opracowywany przez innego użytkownika.
- **Wstrzymana** — ten stan jest pokazywany po wybraniu opcji **Wstrzymaj przyjmowanie** w celu tymczasowego zatrzymania procesu przyjmowania.
- **Przetwarzanie w Centrali** — dokument został przesłany do Centrali Commerce z aplikacji punktu sprzedaży, ale nie został jeszcze zaksięgowany pomyślnie w Centrali Commerce. Dokument przechodzi przez proces asynchronicznego księgowania dokumentu. Po pomyślnym zaksięgowaniu dokumentu w module Commerce Headquarter jego stan powinien zostać zaktualizowany do **w pełni odebranego** lub **częściowo odebranego**.
- **Przetwarzanie nie powiodło się** — dokument został zaksięgowany w Centrali Commerce i odrzucony. W **Szczegółach** jest wyświetlana przyczyna niepowodzenia księgowania. Dokument musi być edytowany w celu usunięcia problemów z danymi, a następnie musi zostać ponownie przesłany do Centrali Commerce w celu przetworzenia.

Po wybraniu wiersza dokumentu z listy zostanie wyświetlone okienko **Szczegółów**. W tym okienku są wyświetlane dodatkowe informacje o dokumencie, takie jak informacje o wysyłce i dacie. Na pasku postępu widać, ile towarów trzeba będzie przetworzyć. Jeśli dokument nie został pomyślnie przetworzony w Centrali Commerce, w okienku **szczegółów** są wyświetlane także komunikaty o błędach związane z tym niepowodzeniem.

W widoku strony listy dokumentów możesz wybrać **Szczegóły zamówienia** na pasku aplikacji, aby wyświetlić szczegóły dokumentu. Można również uaktywnić przetwarzanie paragonów w uprawnionych wierszach dokumentu.

W widoku strony listy dokumentów można również utworzyć nowe żądanie zamówienia przeniesienia przychodzącego dla sklepu. Dokumenty pozostają w stanie **Wersji roboczej** i mogą być korygowane lub usuwane dopiero po przesłaniu ich do Centrali Commerce w celu przetworzenia. Po przesłaniu ich do Centrali Commerce, wiersze zamówienia przeniesienia nie mogą być już zmieniane z poziomu aplikacji punktu sprzedaży.

## <a name="receiving-process"></a>Proces przyjęcia

Po wybraniu zamówienia zakupu lub dokumentu zamówienia przeniesienia na karcie **Aktywne** można wybrać **Szczegóły zamówienia**, aby rozpocząć proces przyjmowania.

Domyślnie jest wyświetlany widok **Przyjmowane teraz**. Ten widok jest zoptymalizowany pod kątem skanowania kodu kreskowego. Można go użyć do utworzenia listy przeskanowanych towarów, tak aby można było odebrać te towary. Aby rozpocząć proces odbierania, można rozpocząć skanowanie kodów kreskowych towarów.

Gdy w widoku **Przyjmowane teraz** są skanowane kody kreskowe towarów, aplikacja sprawdza poprawność towarów względem wybranego dokumentu zakupu lub zamówienia przeniesienia, aby upewnić się, że każdy zeskanowany towar będzie odpowiadał prawidłowemu towarowi w dokumencie. W widoku **Przyjmowane teraz** zakładane jest, że każde skanowanie kodu kreskowego reprezentuje przyjęcie ilości jednej jednostki, chyba że w kodzie kreskowym zostanie osadzona ilość. W tym widoku można wielokrotnie skanować kody kreskowe, aby utworzyć listę wszystkich towarów i ilości dla paragonu.

### <a name="example-scenario"></a>Przykładowy scenariusz

Użytkownik otrzymuje zamówienie zakupu zawierające 10 jednostek kodu kreskowego 5657900266. Użytkownik może skanować kod kreskowy 10 razy w celu zaktualizowania pola **Przyjmowane teraz** przez jedną jednostkę na skanowanie. Gdy użytkownik zakończy skanowanie, w polu **Przyjmowane teraz** dla wiersza towaru zostanie wyświetlona ilość równa 10.

Alternatywnie, w scenariuszu, w którym ilość towaru jest duża, użytkownik może ręcznie wprowadzić ilość zamiast skanowania kodu kreskowego każdego otrzymanego towaru. W takim przypadku użytkownik może raz zeskanować kod kreskowy, aby dodać go do listy **Przyjmowane teraz**. Użytkownik może następnie zaznaczyć skojarzony wiersz w widoku **Przyjmowane teraz**, a następnie w okienku **Szczegółów**, które pojawiają się po prawej stronie witryny. należy, zaktualizować pole **Ilość przyjęcia** dla tego towaru.

Mimo że widok **Przyjmowane teraz** jest zoptymalizowany pod kątem skanowania kodu kreskowego, użytkownicy mogą również zaznaczyć opcję **Przyjęcie produktu** na pasku aplikacji, a następnie wprowadzić identyfikator towaru lub kod kreskowy za pomocą okna dialogowego. Po sprawdzeniu towaru, który został wprowadzony, użytkownik jest poproszony o wprowadzenie przyjmowanej ilości.

Widok **Przyjmowane teraz** stanowi skoncentrowany sposób wyświetlania przez użytkowników produktów, które są w nich odbierane. Można również użyć widoku **Pełnej listy zamówień**. W tym widoku jest wyświetlana cała lista wierszy dokumentu dla wybranego dokumentu zakupu lub zamówienia przeniesienia. Użytkownicy mogą ręcznie wybierać wiersze z listy, a następnie w okienku **Szczegółów** zaktualizować pole **Ilość przyjęcia** dla wybranego wiersza. W widoku **Pełna lista zamówień** użytkownicy mogą skanować kody kreskowe lub, korzystając z funkcji **Przyjęcie produktu**, wprowadzić identyfikator towaru lub kod kreskowy oraz dane dotyczące przyjętej ilości, bez uprzedniego wybrania zgodnego wiersza towaru z listy.

### <a name="over-receiving-validations"></a>Sprawdzanie przekroczeń odbioru

Sprawdzanie poprawności nastąpiło podczas procesu odbierania dla wierszy dokumentu. Obejmują one sprawdzanie nadwyżki w dostawie. Jeśli użytkownik spróbuje uzyskać więcej zapasów niż zamówiono w zamówieniu zakupu, ale nadwyżka w dostawie nie jest skonfigurowana lub otrzymana kwota przekracza tolerancję nadwyżki w dostawie skonfigurowaną dla wiersza zamówienia zakupu, zostanie wyświetlony błąd i nie można przyjąć nadmiarowej ilości.

Nadmierne odbieranie nie jest dozwolone dla dokumentów zamówienia przeniesienia. Użytkownicy będą zawsze otrzymywali błędy, jeśli próbują przyjąć więcej niż wysłano w wierszu zamówienia przeniesienia.

### <a name="close-purchase-order-lines"></a>Zamykanie wierszy zamówień zakupu

Pozostałą ilość w zamówieniu zakupu można zamknąć w trakcie procesu odbierania, jeśli spedytor potwierdził, że nie może wysłać pełnej wymaganej ilości. W tym celu firma musi być skonfigurowana tak, aby zezwalać na niedobór w dostawie zamówień zakupu. Ponadto dla wiersza zamówienia zakupu musi zostać wartość tolerancja procentowa niedoboru w dostawie.

Aby skonfigurować firmę w taki sposób, aby zezwalała na niedobór zamówień zakupu w module Commerce Headquarters, przejdź do **Zaopatrzenie i sourcing** > **Konfiguracja** > **Parametry modułu Zaopatrzenie i sourcing**. Na karcie **Dostawa** włącz parametr **Akceptacja niedoboru w dostawie**. Następnie uruchom zadanie harmonogramu dystrybucji **1070** (**Konfiguracja kanałów**), aby zsynchronizować zmiany z kanałami.

Wartości procentowe tolerancji niedoboru dla wiersza zamówienia mogą być wstępnie zdefiniowane dla produktów jako część konfiguracji produktu w module Commerce Headquarters. Można je również ustawić lub zastąpić w określonym zamówieniu zakupu w module Commerce Headquarters.

Po zakończeniu konfigurowania niedoboru w zamówienia zakupu w organizacji użytkownicy punktu sprzedaży będą widzieć nową opcję **Zamknij pozostałą ilość** w okienku **Szczegóły**, gdy w operacji **Zapasy przychodzące** zostanie wybrany wiersz przychodzącego zamówienia zakupu. Jeśli użytkownik zamknie pozostałej ilości, POS zweryfikuje, czy zamykana ilość mieści się w tolerancji procentowej wartości niedoboru w dostawie określonej w wierszu zamówienia zakupu. Jeśli tolerancja niedoboru w dostawie zostanie przekroczona, wyświetlany jest komunikat o błędzie, a użytkownik nie będzie mógł zamknąć pozostałej ilości, dopóki wcześniej otrzymana ilość **Przyjmowana teraz** będzie równa lub przekroczy minimalną ilość, która musi zostać przyjęta na podstawie wartości procentowej tolerancji niedoboru dostawy. 

Po włączeniu opcji **Zamknij pozostałą ilość** dla wiersza zamówienia zakupu, gdy użytkownik zakończy przyjęcie przy użyciu akcji **Zakończ przyjęcie**, żądanie zamknięcia zostanie również wysyłane do modułu Commerce Headquarters, a każda nieodebrana ilość z tego wiersza zamówienia zostanie anulowana. W tym momencie wiersz jest uznawany za całkowicie odebrany. 

### <a name="receiving-location-controlled-items"></a>Odbieranie towarów kontrolowanych w lokalizacji

Jeśli otrzymywane towary są sterowane lokalizacjami, użytkownicy mogą wybrać lokalizację, w której mają być odbierane towary podczas procesu odbierania. Zaleca się skonfigurowanie domyślnej lokalizacji przyjęcia dla magazynu sklepu, aby ten proces był bardziej wydajny. Nawet w przypadku skonfigurowania lokalizacji domyślnej użytkownicy mogą zastępować lokalizację przyjęcia w wybranych wierszach w miarę ich obowiązywania.

Operacja uwzględnia konfigurację **Dozwolony pusty przychód** dla pozycji **lokalizacji** w wymiarze przechowywania i nie wymaga wprowadzenia wymiaru lokalizacji, jeśli jest skonfigurowany pusty przychód. Jeśli puste lokalizacje przychodu nie są dozwolone dla towaru, w aplikacji punktu sprzedaży jest wyświetlany komunikat o błędzie i wymagane jest wprowadzenie lokalizacji przed zaksięgowaniem przychodu.

### <a name="receive-all"></a>Przyjmij wszystko

Jeśli jest to wymagane, można wybrać opcję **Przyjmij wszystko** na pasku aplikacji, aby szybko zaktualizować ilość **Przyjmowane teraz** dla wszystkich wierszy dokumentu do wartości maksymalnej, która jest dostępna dla tych wierszy.

### <a name="receipt-of-unplanned-items-on-purchase-orders"></a>Przyjęcie nieplanowanych towarów na zamówieniach zakupu

W wersji Commerce 10.0.14 lub nowszej użytkownicy mogą uzyskać produkt, który nie znajdował się na pierwotnym zamówieniu zakupu. Aby włączyć tę funkcję, należy włączyć opcję **Dodawania wierszy do zamówienia zakupu podczas otrzymywania w punkcie sprzedaży**.  

Ta funkcja działa tylko dla przyjęcia zamówienia zakupu. Nie można przyjmować towarów w ramach zamówień przeniesienia, jeśli towary nie zostały wcześniej zamówione i wysłane z magazynu wychodzącego.

Użytkownicy nie mogą dodawać nowych produktów do zamówienia zakupu podczas odbierania w punkcie sprzedaży, jeśli [zarządzanie zmianami przepływu pracy](https://docs.microsoft.com/dynamics365/supply-chain/procurement/purchase-order-approval-confirmation) jest uruchomione w Commerce Headquarter (HQ). Aby umożliwić zarządzanie zmianami, wszystkie zmiany w zamówieniu zakupu należy najpierw zatwierdzić przed zezwoleniem na odebranie. Ponieważ ten proces umożliwia odbiorcy dodawanie nowych wierszy do zamówienia zakupu, odbieranie nie powiedzie się, jeśli jest włączony przepływ pracy zarządzania zmianami. Jeśli funkcja zarządzania zmianami jest włączona dla wszystkich zamówień zakupu lub dla dostawcy połączonego z zamówieniem zakupu, które w tym momencie odbierane w punkcie sprzedaży, użytkownik nie może dodawać nowych produktów do zamówienia zakupu podczas przyjmowania w punkcie sprzedaży.

Funkcja umożliwiająca dodawanie wierszy nie może być używana jako obejście do przyjmowania dodatkowych ilości produktów już znajdujących się w zamówieniu zakupu. Nadmierne odbieranie jest zarządzane przy użyciu standardowych ustawień [nadwyżki w odbiorze](https://docs.microsoft.com/dynamics365/commerce/pos-inbound-inventory-operation#over-receiving-validations) dla wiersza produktu w zamówieniu zakupu.

Jeśli jest włączona funkcja **Dodawania wierszy do zamówienia zakupu podczas otrzymywania w punkcie sprzedaży**, a użytkownik odbiera w punkcie w ramach **Operacji przychodzącej**, w przypadku skanowania kodu kreskowego lub numeru produktu, który nie został rozpoznany jako towar w bieżącym zamówieniu zakupu, ale jest rozpoznawany jako prawidłowy towar, użytkownik otrzymuje komunikat dotyczący dodawania towaru do zamówienia zakupu. Jeśli użytkownik doda towar do zamówienia zakupu, ilość wprowadzona w polu **Przyjęcie** jest uważana za zamówioną ilość dla wiersza zamówienia zakupu.

Gdy przyjęcie zamówienia zakupu zostało zakończone i przesłane do HQ w celu przetworzenia, dodane wiersze są tworzone w dokumencie głównym zamówienia zakupu. W wierszu zamówienia zakupu w HQ w pojawi się flaga **Dodane w POS**, w zakładce **Ogólne** w wierszu zamówienia zakupu. Flaga **Dodana przez POS** wskazuje, że wiersz zamówienia zakupu został dodany przez proces odbierania w punkcie sprzedaży i nie był wierszem, który był na zamówieniu zakupu przed jego przyjęciem.

### <a name="cancel-receiving"></a>Anuluj przyjmowanie

Funkcji **Anulowanie odbioru** należy użyć na pasku aplikacji tylko wtedy, gdy chcesz wycofać się z dokumentu i nie chcesz zapisywać żadnych zmian. Na przykład początkowo zaznaczono niewłaściwy dokument i nie ma potrzeby zapisywania żadnego z poprzednich danych przyjęcia.

### <a name="pause-receiving"></a>Wstrzymaj przyjmowanie

W przypadku przyjmowania zapasów można użyć funkcji **Wstrzymaj przyjęcie**, jeśli proces ma zostać podzielony od procesu odbierającego. Na przykład można wykonać inną operację z punktu sprzedaży, na przykład dzwonienie do sprzedaży odbiorcy lub opóźnienie księgowania paragonu.

Po wybraniu opcji **Wstrzymaj przyjęcie**stan dokumentu zostanie zmieniony na **Wstrzymany**. Dlatego użytkownicy będą wiedzieć, że wprowadzono dane do dokumentu, ale dokument nie został jeszcze zatwierdzony. Aby wznowić proces przyjmowania, wybierz wstrzymany dokument, a następnie wybierz **Szczegóły zamówienia**. Wszystkie **Przyjmowane teraz** ilości odbieranych towarów są zachowywane i można je przeglądać z poziomu widoku **Pełna lista zamówień**.

### <a name="review"></a>Przegląd

Przed ostatecznym potwierdzeniem przyjęcia do centrali Commerce (HQ) można skorzystać z funkcji przeglądu w celu sprawdzenia poprawności dokumentu przychodzącego. Przegląd zaalarmuje o brakujących lub niepoprawnych danych, które mogą spowodować niepowodzenie przetwarzania i zapewni możliwość rozwiązania problemów przed wysłaniem prośby o pokwitowanie. Aby włączyć funkcję **Przeglądu** na pasku aplikacji, włącz opcję **Włącz walidację w przychodzących i wychodzących operacjach magazynowych POS** w obszarze roboczym **Zarządzanie funkcjami** w Commerce Headquarter (HQ).

Funkcja **Przeglądu** sprawdza poprawność następujących problemów w dokumencie przychodzącym:

- **Nadwyżka w odbiorze** — ilość odebrana teraz jest większa niż zamówiona Ilość. Waga tego zagadnienia jest określana na podstawie konfiguracji nadwyżki w module Commerce Headquarter (HQ).
- **Niedobór w odbiorze** — ilość odebrana teraz jest mniejsza niż zamówiona Ilość. Waga tego zagadnienia jest określana na podstawie konfiguracji niedoboru w module Commerce Headquarter (HQ).
- **Numer seryjny** — numer seryjny nie został podany lub potwierdzony dla towaru seryjnego, który wymaga zarejestrowania numeru seryjnego w magazynie.
- **Lokalizacja nie ustawiona** — nie określono lokalizacji dla pozycji kontrolowanej w lokalizacji, w której lokalizacja nie może być pusta.
- **Usunięte wiersze** — Zamówienie zawiera wiersze usunięte przez użytkownika z modułu Commerce Headquarter (HQ), który nie jest znany w aplikacji punktu sprzedaży.

Jeśli dla parametru **Włącz automatyczne sprawdzanie poprawności** zostanie ustawiona wartość **Tak** w **Parametry Commerce** > **Zapasy** > **Zapasy w sklepie**, aby wykonać sprawdzanie poprawności po wybraniu funkcji **Zakończenie odbioru**.

### <a name="finish-receiving"></a>Zakończ przyjmowanie

Po zakończeniu wprowadzania wszystkich ilości **Przyjmowane teraz** dla produktów należy wybrać opcję **Zakończ przyjmowanie** na pasku aplikacji, aby przetworzyć przyjęcie.

Jeśli użytkownik zakończy przyjęcie zamówienia zakupu, zostanie wyświetlony monit o wprowadzenie wartości w polu **Numer paragonu**, jeśli ta funkcja zostanie skonfigurowana. Zazwyczaj ta wartość jest równoważna identyfikatorowi dokumentu dostawy dostawcy. Dane o **numerze paragonu** będą przechowywane w arkuszu dokumentów przyjęcia produktów w Centrali Commerce. Numery paragonów nie są przechwytywane dla przyjęć zamówień przeniesienia.

Gdy jest używane przetwarzanie dokumentów asynchronicznych, paragon jest przesyłany za pośrednictwem struktury dokumentów asynchronicznych. Czas potrzebny na zaksięgowanie dokumentu jest zależny od rozmiaru dokumentu (liczby wierszy) i ogólnego ruchu przetwarzania występującego na serwerze. Zazwyczaj proces ten odbywa się w ciągu kilku sekund. Jeśli Księgowanie dokumentu nie powiedzie się, użytkownik zostanie powiadomiony za pośrednictwem listy dokumentów **Operacja przychodząca**, gdzie stan dokumentu zostanie zaktualizowany jako **Proces nie powiódł się**. Użytkownik może następnie wybrać nieuszkodzony dokument w punkcie sprzedaży, aby wyświetlić komunikaty o błędach oraz przyczynę niepowodzenia w okienku **Szczegółów**. Uszkodzony dokument pozostaje niezaksięgowany i wymaga powrotu użytkownika do wierszy dokumentu przez wybranie **Szczegółów zamówienia** w punkcie sprzedaży. Użytkownik musi wówczas zaktualizować dokument, używając korekt, na podstawie błędów. Po poprawieniu dokumentu użytkownik może spróbować ponownie go przetworzyć, wybierając opcję **Zakończ realizację** na pasku aplikacji.

## <a name="create-an-inbound-transfer-order"></a>Utworzenie przychodzącego zamówienia przeniesienia

Z punktu sprzedaży użytkownicy mogą tworzyć nowe dokumenty zamówienia przeniesienia. Aby rozpocząć proces, należy wybrać opcję **Nowy** na pasku aplikacji, gdy znajdujesz się na liście głównych dokumentów **operacji przychodzących**. Następnie zostanie wyświetlony monit o wybranie **Przeniesienia z** magazynu lub sklepu, które dostarczy zapasy do lokalizacji w sklepie. Wartości są ograniczone do wyboru zdefiniowanego w konfiguracji grupy realizacji sklepu. W żądaniu przeniesienia przychodzącego bieżący sklep będzie zawsze **Przenoszony do** magazynu dla zamówienia przeniesienia. Tej wartości nie można zmienić.

W razie konieczności można wprowadzić wartości w polach **Data wysyłki**, **Data odebrania** i **Metoda dostawy**. Można również dodać notatkę, która będzie przechowywana razem z nagłówkiem zamówienia przeniesienia, jako załącznik do dokumentu w Centrali Commerce.

Po utworzeniu informacji nagłówka można dodać produkty do zamówienia przeniesienia. Aby rozpocząć proces dodawania towarów i żądanych ilości, wybierz pozycję **Dodaj produkt**. W okienku **Szczegółów** można również dodać uwagę specyficzną dla wiersza do wierszy arkusza. Te notatki będą przechowywane jako załączniki do wierszy.

Po wprowadzeniu wierszy w zamówieniu przeniesienia przychodzącego należy wybrać opcję **Zapisz**, aby zapisać zmiany w dokumencie lokalnie lub **Przeslij żądanie**, aby przesłać szczegóły zamówienia do Centrali Commerce w celu dalszego przetwarzania. Jeśli zostanie wybrana **Zapisz**, dokument wersji roboczej zostanie zapisany w bazie danych kanału, a magazyn wychodzący nie będzie mógł uruchomić dokumentu, dopóki nie zostanie on pomyślnie przetworzony przez **Prześlij żądanie**. Opcję **Zapisz** należy wybrać tylko w przypadku, gdy nie można zatwierdzić żądania w celu przetworzenia w Centrali Commerce.

Jeśli dokument jest zapisany lokalnie, można go znaleźć na karcie **Wersje robocze** na liście dokumentów dla **Operacji przychodzących**. Gdy dokument jest w stanie **Wersji roboczej**, można go edytować, wybierając **Edytuj**. W razie konieczności można zaktualizować, dodać lub usunąć wiersze. Można również usunąć cały dokument, gdy jest on w stanie **Wersji roboczej**, zaznaczając opcję **Usuń** na karcie **Wersje robocze**.

Po pomyślnym przesłaniu wersji roboczej do modułu Commerce Headquarter zostanie ona wyświetlona na karcie **Aktywne** i stan zmieni się na **Wnioskowane**. W tym momencie użytkownicy w magazynie lub magazynie przychodzącym nie mogą już edytować żądanego dokumentu zamówienia przeniesienia przychodzącego. Tylko użytkownicy z magazynu wychodzącego mogą edytować dokument, wybierając **Operację wychodzącą** w aplikacji punktu sprzedaży. Blokada edycji zapewnia, że nie występują żadne konflikty, ponieważ przychodzący zleceniodawca zmienia zamówienie przeniesienia w tym samym czasie, gdy wychodzący spedytor będzie aktywnie pobierał i wysyłał zamówienie. Jeśli po przesłaniu zamówienia przeniesienia wymagane są zmiany z magazynu lub magazynu przychodzącego, należy skontaktować się z odbiorcą w sprawie wychodzącego spedytora i poprosić o wprowadzenie zmian.

Gdy dokument stanie **Wnioskowany**, jego stan jest widoczny na karcie **Aktywne**. Nie można go jednak odebrać przez magazyn lub sklep przychodzący. Po dostarczeniu przez magazyn wyjściowy części lub całości zamówienia przeniesienia, sklep lub magazyn przychodzący może księgować przychody w punkcie sprzedaży. Gdy strona wychodząca przetwarza zamówienia przeniesienia, jego stan jest aktualizowany na z **Wnioskowany** do **Wysłane** lub **Częściowo wysłane**. Gdy dokumenty są w stanie **Wysłane** lub **Częściowo wysłane**, magazyn lub magazyn przychodzący może zaksięgować przychody z nich przy użyciu procesu przyjęcia operacji przychodzącej.

## <a name="related-topics"></a>Powiązane tematy

[Operacja zapasów wychodzących w punkcie sprzedaży](pos-outbound-inventory-operation.md)
