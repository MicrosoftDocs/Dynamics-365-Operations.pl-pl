---
title: Obsługa magazynów dla ładunków przychodzących dla zamówień zakupu
description: W tym temacie opisano proces obsługi magazynu dla ładunków przychodzących zamówień zakupu.
author: omulvad
manager: AnnBe
ms.date: 03/21/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2020-03-21
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 709a75a259b1f8daa5b72e76b56942573c403f43
ms.sourcegitcommit: 3a823444005d316bd95fc663e2dbc8252ac7d93a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/14/2020
ms.locfileid: "3261364"
---
# <a name="warehouse-handling-of-inbound-loads-for-purchase-orders"></a>Obsługa magazynów dla ładunków przychodzących dla zamówień zakupu

W tym temacie opisano proces obsługi magazynu dla ładunków przychodzących zamówień zakupu.

Dla każdego ładunku przychodzącego system powinien już zawierać powiązane zamówienie sprzedaży i może również zawierać powiązaną specyfikację ładunku i/lub plan transportu. Aby uzyskać więcej informacji na temat tworzenia ładunków przychodzących i zarządzania nimi, odwiedź temat [Proces biznesowy: planowanie transportu dla ładunków przychodzących](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/business-process-planning-transportation-for-inbound-loads).

## <a name="overview-how-inbound-loads-are-created-registered-and-received"></a>Omówienie: sposób tworzenia, rejestrowania i odbierania ładunków przychodzących

Na poniższej ilustracji przedstawiono typowy przepływ obsługi ładunków przychodzących w ilości zamówienia zakupu, w momencie gdy docierają do magazynu.

![Proces obsługi ładunku przychodzącego](media/inbound-process.png "Proces obsługi ładunku przychodzącego")

1. **Dostawca potwierdza zamówienie zakupu.**

    Proces rozpoczyna się w momencie wprowadzenia zamówienia zakupu do systemu, a następnie dostarczenia go dostawcy, który potwierdzi zamówienie. Aby można było utworzyć rekord ładunku przychodzącego, musi istnieć zamówienie zakupu. Można jednak utworzyć ładunek przychodzący, nawet jeśli zamówienie nie zostało potwierdzone. Aby uzyskać więcej informacji, zobacz [Zatwierdzanie i potwierdzanie zamówień zakupu](../procurement/purchase-order-approval-confirmation.md).

1. **Tworzony jest rekord ładunku przychodzącego w celu zaplanowania przyjęcia i jego zawartości.**

    Rekord ładunku przychodzącego reprezentuje wysyłkę przez dotawcę jednego lub więcej zamówień zakupu. Oczekuje się, że ładunek dociera do magazynu jako jedna fizyczna jednostka transportowa (np. ładunek ciężarówki). Rekord ładunku przychodzącego jest używany do planowania i umożliwia koordynatorowi logistyki śledzenie postępu ładunku od dostawcy. Służy on również do rejestrowania ilości w wierszach zamówienia oraz do zarządzania postępem w ramach operacji magazynowych, takich jak przybycie i praca odkładania. Ładunki mogą być tworzone automatycznie lub ręcznie i mogą być oparte na zamówieniu zakupu lub zaawansowanym zawiadomieniu o wysyłce (ASN) od dostawcy. Aby uzyskać więcej informacji, zajrzyj do części [Tworzenie lub modyfikowanie ładunku przychodzącego](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/create-or-modify-an-inbound-load).

1. **Dostawca potwierdza wysyłkę ładunku.**

    Po wysłaniu ładunku przez dostawcę koordynator logistyki w magazynie odbierającym potwierdza wysyłkę ładunku. Jeśli firma odbierająca używa modułu **Zarządzanie transportem**, potwierdzenie przychodzącej wysyłki wyzwoli inne procesy zarządzania ładunkiem, które są skojarzone z ładunkami przychodzącymi. Aby uzyskać więcej informacji, zajrzyj do [Potwierdzenie ładunku do wysyłki](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/confirm-a-load-for-shipping).

1. **Ładunek dociera do magazynu, a pracownicy rejestrują ilości.**

    Po nadejściu ładunku samochodu ciężarkowego do doku przyjęcia magazynowego pracownicy magazynowi rejestrują ilości ładunku. Gdy używany jest moduł **Zarządzanie magazynem**, pracownicy wykonują rejestrację za pomocą urządzeń przenośnych. Aby uzyskać więcej informacji, zobacz [Przyjęcie produktu na podstawie zamówień zakupu - rejestracja](../procurement/product-receipt-against-purchase-orders.md#registration) oraz sekcję [Zarejestruj ilości produktów, które docierają z ładunkiem przychodzącym](#register-item-quantities-arriving).

1. **Zarejestrowane ilości ładunku są zaksięgowane z zamówieniem zakupu.**

    Po zarejestrowaniu ilości ładunku jako dostarczonych, ilości te muszą być dokumentem przyjęcia produktów — zaksięgowane w księdze zapasów firmy w celu zarejestrowania wzrostu zapasów fizycznych. Aby uzyskać więcej informacji, zajrzyj do [Odbiór produktu na podstawie zamówień zakupu - odbiór produktu](../procurement/product-receipt-against-purchase-orders.md#product-receipt) i [Księguj zarejestrowane ilości produktów na podstawie zamówień zakupu](#post-registered-quantities).

## <a name="register-item-quantities-that-arrive-on-an-inbound-load"></a><a name="register-item-quantities-arriving"></a>Rejestrowanie ilości towarów przychodzących w ładunku przychodzącym

Microsoft Dynamics 365 Supply Chain Management obsługuje kilka podejść operacyjnych do rejestrowania przybycia zamówionych produktów. System można więc skonfigurować w taki sposób, aby odpowiadał określonym wymaganiom biznesowym. W tej sekcji opisano sposób rejestrowania przychodzących ilości towarów przy użyciu urządzenia przenośnego, gdy w systemie jest włączona funkcja zaawansowanego zarządzania magazynem. Istnieje jednak alternatywny przepływ oparty na korzystaniu z arkusza przyjęcia towaru zamiast urządzenia przenośnego. Aby uzyskać więcej informacji o tym przepływie, zobacz [Rejestrowanie pozycji dla zaawansowanego magazynowania za pomocą arkusza przyjęć towarów](tasks/register-items-advanced-warehousing.md).

Gdy ładunek przychodzący po raz pierwszy dociera do magazynu, pracownicy magazynowi muszą rejestrować ilości towarów, które są uwzględnione w wysyłce. Zazwyczaj korzystają ze skanerów podręcznych. Ten przepływ pracy jest dostępny tylko wtedy, gdy w systemie istnieją następujące elementy:

- **Rekord ładunku przychodzącego opisujący ilości towaru oczekiwane w wysyłce**

    Zazwyczaj dostawca potwierdza rekord ładunku przychodzącego przed nadejściem wysyłki do magazynu. Z tego względu ładunek ma stan _wysłane_. Jednak pracownicy magazynowi mogą rejestrować ilości towarów dla ładunków o stanie _Otwarte_ lub _Odebrane_.

- **Menu urządzenia przenośnego jest skonfigurowane do wsparcia odbierania ładunku**

    [Dynamics 365 for Finance and Operations – aplikacja Magazynowanie](install-configure-warehousing-app.md) na urządzenia przenośne obsługuje następujące procesy tworzenia pracy:

    - Odbierana pozycja ładunku
    - Odbierana i odłożona pozycja ładunku
    - Przyjmowanie mieszanego numeru identyfikacyjnego, w którym pole **Metoda identyfikacji wiersza dokumentu źródłowego** dla elementu menu urządzenia przenośnego jest skonfigurowane na _Odbierana pozycja ładunku_. Aby uzyskać więcej informacji, zobacz [Przyjmowanie mieszanego numeru identyfikacyjnego](mixed-license-plate-receiving.md).
    - Przyjmowanie i odkładanie mieszanego numeru identyfikacyjnego, w którym pole **Metoda identyfikacji wiersza dokumentu źródłowego** dla elementu menu urządzenia przenośnego jest skonfigurowane na _Odbierana pozycja ładunku_. Aby uzyskać więcej informacji, zobacz [Przyjmowanie mieszanego numeru identyfikacyjnego](mixed-license-plate-receiving.md).

    > [!NOTE]
    > Niezależnie od procesu system wygeneruje pracę, aby pobrać ilości zarejestrowane w lokalizacji przyjęcia i odłożyć je w zwyczajowym miejscu przechowywania. Podczas korzystania z procesu _Odbierana i odłożona pozycja ładunku_ lub _Przyjęcie i odłożenie mieszanego numeru identyfikacyjnego_, pracownik, który zarejestrował ilość ładunku, będzie również poinstruowany przez urządzenie do wykonania pracy odkładania w ramach zadania rejestracji. Z drugiej strony dla procesów _Odbierana pozycja ładunku_ i _Przyjęcie mieszanego numeru identyfikacyjnego_ zakłada się, że praca odłożenia jest wykonywana niezależnie od zadania resjestracji.

- **Szablon pracy, który definiuje pracę pobierania i odkładania dla ładunków przychodzących**

    Ten towar jest powiązany z poprzednimi towarami. Należy mieć co najmniej jeden szablon pracy dla typu zlecenia pracy _Zamówienie zakupu_ i musi on zawierać zestaw typów pracy odbiór/odłożenie.

Urządzenie przenośne prowadzi pracownika przyjmującego magazynu za pośrednictwem przepływu rejestracji ilości ładunku. Przepływ ten obejmuje co najmniej następujące kroki dla każdego identyfikatora ładunku:

1. Wprowadź identyfikator ładunku.
2. Wprowadź numer towaru dla otrzymanego towaru.
3. Wprowadź ilość dla otrzymanego numeru towaru.
4. Wprowadź numer identyfikacyjny dla początkowej lokalizacji towaru, jeśli system nie jest skonfigurowany do automatycznego generowania tego numeru.
5. Naciśnij **OK**.

Po ukończeniu tych kroków przez pracownika system dokona na odpowiednich jednostkach następujących aktualizacji, pod warunkiem że w wiersz zamówienia zakupu otrzymanej ilości wynosi jeden ładunek i wszystkie ilości ładunku zostały zarejestrowane:

| Jednostka | Aktualizacje | Notatka |
|---|---|---|
| Obciążenie pracą | Pole **Ilość stworzonych prac** w wierszu ładunku jest aktualizowane w celu wyświetlenia zarejestrowanej ilości. | Wartość **Stanu ładunku** pozostaje _Wysłano_ lub _Otwarte_, jeśli nie zostało uruchomione potwierdzenie wysyłki dotyczące ładunku. Jeśli rozpoczęto co najmniej jedne wiersz pracy odkładania, jest ona zmieniana na _w toku_. |
| Transakcja magazynowa zamówienia zakupu, dla którego zarejestrowano powiązane ilości ładunku |<p>Zostaną zaktualizowane następujące pola:</p><ul><li>W polu <b>Odbiór</b> jest ustawiona wartość <i>Zarejestrowane</i>.</li><li>Pole <b>Lokalizacja</b> jest aktualizowane, aby zawierało kod lokalizacji doku przyjęcia. (Kod ten jest określany w polu <b>Domyślna lokalizacja odbioru</b> dla każdego magazynu.)</li><li>Pole <b>Numer identyfikacyjny</b> jest aktualizowane, aby zawierało numer identyfikacyjny, który był wprowadzony lub wygenerowany podczas rejestracji.</li><li>Pole <b>identyfikator ładunku</b> jest aktualizowane na podstawie numeru ładunku, dla którego została zarejestrowana ilość. (Zajrzyj do notatki.)</li></ul> | Możliwość łączenia między transakcją magazynową zamówienia zakupu a ilościami zarejestrowanymi na ładunku została wprowadzona w wersji 10.0.9 jako funkcja opcjonalna nazwana _Skojarz transakcje magazynowe zamówienia zakupu z ładunkiem_. Ta funkcja jest szczególnie przydatna w przypadku przepływów operacyjnych, w których jedno zamówienie zakupionych towarów zostało dostarczone jako wielokrotne ładunki, lub gdy ładunek zawiera ilości dla wielu zamówień zakupu. |
| Odłożenie magazynowe | Praca jest tworzona na podstawie szablonu pracy, aby zlecić pracownikowi przeniesienie zarejestrowanych ilości z lokalizacji przyjęcia do zwykłego miejsca przechowywania. | Wybór lokalizacji magazynu jest kontrolowany przez dyrektywę Umieszczenia lokalizacji. Jeśli dyrektywa lokalizacji nie została zdefiniowana, lokalizacja odłożenia w pracy jest pusta. |

Należy zwrócić uwagę, że pracownicy magazynowi mogą rejestrować odbiór zamówienia zakupu z co najmniej jednym skojarzonym załadunkiem bez korzystania z procesu _Odbierana pozycja ładunku_. Dostępne są następujące metody:

- **Na urządzeniu przenośnym:** należy skorzystać z procesów _Przyjęcie wiersza zamówienia zakupu_ i _Przyjęcie i odłożenie wiersza zamówienia zakupu_. (Jeśli dla ilości w wierszu zamówienia zakupu istnieje więcej niż jeden ładunek, pracownik nie może skorzystać z procesu _Przyjęcie wiersza zamówienia zakupu_. Zamiast tego pracownik otrzyma polecenie użycia akcji dotyczącej urządzenia, która jest skojarzona zprocesem _Odbierana pozycja ładunku_).
- **W kliencie:** należy skorzystać z arkusza przyjęcia towaru.
- **W kliencie:** należy skorzystać z akcji **Rejestracja**, do której można uzyskać dostęp z wiersza zamówienia zakupu.

> [!NOTE]
> Jeśli przyjęcie zamówienia zakupu jest zarejestrowane za pomocą dowolnej z powyższych metod, nie są tworzone żadne łącza między transakcją magazynową zamówienia zakupu a ładunkiem, nawet jeśli jest włączona funkcja _Skojarz transakcje magazynowe zamówienia zakupu z ładunkiem_. Jednym z wyjątków od tej reguły jest użycie opcji **Przyjęcie wiersza zamówienia zakupu**, a tylko jeden ładunek ma stan inny niż _Otrzymany_ dla wiersza zamówienia.

### <a name="handle-discrepancies-during-registration-of-inbound-load-quantities"></a>Obsługa rozbieżności podczas rejestracji ilości ładunku przychodzącego

Pracownicy magazynowi mogą wykonać rejestrację przyjęcia częściowego ładunku. Każda część częściowego przyjęcia ładunku jest tworzona jako oddzielna transakcja magazynowa o stanie _Zarejestrowane_ dla zarejestrowanej ilości, a identyfikator partii odwołuje się do wiersza oryginalnego zamówienia zakupu.

#### <a name="load-under-receiving"></a>Niedostateczy odbiór ładunku

Po otrzymaniu ładunku, jeśli ilości towaru są mniejsze niż ilości określone w rekordzie ładunku, pracownik otrzymujący magazynu może pracować bezpośrednio z klientem w celu potwierdzenia tej rozbieżności, zmniejszając ilość w wierszu ładunku, tak aby odpowiadała rzeczywistej ilości, która dotarła i została zarejestrowana.

#### <a name="load-over-receiving"></a><a name="load-over-receiving"></a>Przekroczenia odbioru ładunku

Przekroczenie odbioru następuje po nadejściu ładunku, gdy ilość towaru przekracza oczekiwaną ilość w wierszu ładunku. Można określić, czy i w jakim stopniu ma być dozwolone przekroczenie odbioru podczas rejestracji ładunku.

W celu określenia, co dzieje się w przypadku, gdy pracownik magazynu usiłuje zarejestrować nadwyżkę, należy skorzystać z pola **Przekroczony odbiór ładunku** dla odpowiednich elementów menu urządzeń przenośnych. To pole jest dostępne dla elementów menu urządzeń przenośnych, które używają następujących typów procesów tworzenia pracy:

- Odbierana pozycja ładunku
- Odbierana i odłożona pozycja ładunku
- Przyjmowanie mieszanego numeru identyfikacyjnego (kiedy pole **Metoda identyfikacji wiersza dokumentu źródłowego** jest skonfigurowane na _Odbierana pozycja ładunku_)
- Przyjmowanie i odkładanie mieszanego numeru identyfikacyjnego (kiedy pole **Metoda identyfikacji wiersza dokumentu źródłowego** jest skonfigurowane na _Odbierana pozycja ładunku_)

W poniższej tabeli wyjaśniono opcje dostępne dla pola **Przekroczony odbiór ładunku**.

| Wartość | opis |
|---|---|
| Zezwalaj | Pracownicy mogą rejestrować odbiór ilości przekraczających pozostałą niezarejestrowana ilość dla wybranego ładunku, ale tylko wtedy, gdy łączna ilość zarejestrowana nie przekracza ilości wiersza zamówienia zakupu skojarzonej z ładunkiem (po korekcie dla procentu nadwyżki w dostawie). |
| Zablokuj | <p>Pracownicy nie mogą rejestrować przyjęcia ilości większej niż pozostała niezarejestrowana ilość dla wybranego ładunku (po skorygowaniu o wartość procentu nadwyżki w dostawie). Pracownik próbujący zarejestrować odbiory otrzyma komunikat o błędzie i nie będzie mógł kontynuować, dopóki nie zarejestruje ilości równej lub mniejszej od pozostałej niezarejestrowanej ilości ładunku.</p><p>Domyślnie wartość procentu nadwyżki w dostawie w wierszu ładunku jest kopiowana z wiersza skojarzonego zamówienia zakupu. Jeśli w polu <b>Przekroczony odbiór ładunku</b> ustawiono wartość <i>Zablokuj</i>, system używa wartości procentowej nadwyżki w dostawie w celu obliczenia całkowitej ilości, którą można zarejestrować w wierszu ładunku. Jednak wartość ta może zostać zastąpiona dla pojedynczych ładunków w zależności od potrzeb. To zachowanie staje się istotne podczas przyjmowania przepływów, jeśli część lub całość nadwyżki, która reprezentuje procent nadwyżki w dostawie wiersza zamówienia, jest nieproporcjonalnie rozłożona na wiele ładunków. Oto przykładowy scenariusz:</p><ul><li>Istnieje wiele ładunków dla jednego wiersza zamówienia zakupu.</li><li>W wierszu zamówienia zakupu jest procent nadwyżki w dostawie, który jest większy niż 0 (zero).</li><li>Ilości zostały już zarejestrowane w odniesieniu do jednego lub większej liczby ładunków bez uwzględnienia procentu nadwyżki w dostawie.</li><li>Ilość nadwyżki w dostawie przychodzi z ostatnim ładunkiem.</li></ul><p>W tym scenariuszu urządzenie przenośne może być użyte do zarejestrowania nadwyżki ilości dla ostatniego ładunku tylko wtedy, gdy kierownik magazynu zwiększy wartość procentową nadwyżki w dostawie dla odpowiedniego wiersza ładunku z domyślnej wartości na wartość wystarczająco dużą, aby można było zarejestrować pełną nadwyżkę w dostawie wraz z końcowym ładunkiem.</p> |
| Zablokuj tylko dla zamkniętych ładunków | Pracownicy mogą odbierać nadwyżki ilości wierszy ładunku dla ładunków otwartych, ale nie dla ładunków o stanie _Odebrane_. |

> [!NOTE]
> Wartością domyślną pola **Przekroczony odbiór ładunku** jest _Zezwalaj_. Jeśli ta wartość jest używana, zachowanie jest zgodne z zachowaniem standardowym, które było dostępne przed wprowadzeniem funkcji _Przyjęcie nadwyżki ilości ładunku_ w wersji 10.0.11.

### <a name="put-away-the-registered-quantities"></a>Odkładanie zarejestrowanych ilości

Po zakończeniu rejestracji na urządzeniu przenośnym akcja _Rejestracja przyjęcia ilości_ powoduje zaktualizowanie zapasów i rekordów magazynowych w celu wskazania, że ilości są teraz w lokalizacji doku przyjęcia i dostępne do rezerwacji. Jednak operacje magazynowe firmy zwykle wymagają przeniesienia ilości z doku przyjęcia do przechowania w zwykłym magazynie, dzięki czemu mogą wystąpić kolejne procesy pobierania. Instrukcje dotyczące odłożenia są przechwytywane w ramach pracy odłożenia, która jest generowana automatycznie, gdy ładunek przychodzący jest zarejestrowany jako przyjęty.

Gdy pracownik magazynu zakończy pracę odłożenia, system rejestruje i śledzi wynik, aktualizując aktualizacje kilku jednostek zgodnie jak podsumowano w poniższej tabeli.

| Jednostka | Aktualizacje | Notatka |
|---|---|---|
| Obciążenie pracą | <p>Zostaną zaktualizowane następujące pola:</p><ul><li>Wartość <b>Stan ładunku</b> jest zmieniana na <i>w trakcie</i>.</li><li>Wartość <b>Stan pracy</b> jest zmieniana na <i>wykonano 100,00% pracy</i>.</li></ul> | Wartość **Stan ładunku** jest zmieniana na _W toku_, gdy pracownik rozpocznie zadanie odłożenia dla co najmniej jednego wiersza pracy odłożenia. |
| Transakcje magazynowe pracy, dla której skojarzone ilości zostały odłożone | Pola **Odbiór** i **Lokalizacja** oraz inne stosowne pola są aktualizowane w celu odzwierciedlenia przepływu z lokalizacji przyjęcia do lokalizacji magazynu. | Wartość **Stan przyjęcia** transakcji magazynowej zamówienia zakupu pozostanie _Zarejestrowane_. |
| Odłożenie magazynowe | Wartość **Stan pracy** zmieni się na _Zamknięte_. | |

## <a name="post-registered-product-quantities-against-purchase-orders"></a><a name="post-registered-quantities"></a>Księguj zarejestrowane ilości produktów na podstawie zamówień zakupu

Po zarejestrowaniu w systemie przychodzących ilości produktów stają się one dostępne do rezerwacji w związku ze sprzedażą i innymi operacjami wychodzącymi i wewnętrznymi. Jednak system nie aktualizuje jeszcze kont magazynowych (tymczasowo). Ta aktualizacja może wystąpić tylko wtedy, gdy zespół operacji zaksięguje zarejestrowane przyjęcia produktów.

Aby otworzyć stronę, na której mogą być księgowane przyjęcia produktów, członkowie zespołu operacji mogą wykonać _jedną_ z następujących czynności:

- Otwórz odpowiedni rekord ładunku, a następnie wybierz akcję **Przyjęcie produktu**.
- Przejdź do **Zarządzanie magazynem \> Zadania okresowe \> Aktualizowanie dokumentów przyjęcia produktów**, a następnie w polu **Identyfikator ładunku** określ ładunek, który ma zostać zaksięgowany.
- Otwórz odpowiednie zamówienie zakupu, a następnie wybierz akcję **Przyjęcie produktu**.
- Przejdź do **Zaopatrzenie i sourcing \> Zamówienia zakupu \> Przyjęcia produktów \> Księgowanie zadania przyjęcia produktów**.

Akcja **Przyjęcia produktów**, która jest dostępna na stronie **Ładunek** (oraz na odpowiedniej stronie zadania aktualizacji, stronie **Aktualizowanie dokumentów przyjęcia produktów**), umożliwia aktualizowanie ilości dokumentów przyjęcia produktów tylko w ilościach zamówień zakupu, które mają stan _Zarejestrowane_. Jednak akcja dokumentu **Przyjęcia produktów**, która jest dostępna na stronie **Zamówienia zakupu**, może zawierać ilości w obu stanach przetwarzania (_Zamówione_ i _Zarejestrowane_). Może również kontrolować zakres księgowania dokumentu przyjęcia produktów za pośrednictwem dodatkowych parametrów, takich jak _Ilość dostarczana teraz_ i _Zarejestrowane ilości i usługi_.

Tylko zamówienia o stanie _Potwierdzone_ mogą być dokumentami przyjęcia produktów — zaksięgowane. W przypadku niepotwierdzonych zamówień zakupu akcja **Przyjęcia produktu** zostanie wyświetlona jako niedostępna.

### <a name="post-registered-quantities-from-the-load-page"></a>Księguj zarejestrowane ilości ze strony ładunku

Do dokumentu przyjęcia produktów — zaksięguj zarejestrowane ilości ze strony **Ładunek**, muszą być spełnione następujące wymagania wstępne:

- Ładunek musi mieć co najmniej jedną jednostkę ilości o stanie _Zarejestrowany_.
- Stan ładunku musi wynosić _Wysłany_.
- Zamówienie zakupu skojarzone z ładunkiem musi mieć stan _Potwierdzone_.

> [!NOTE]
> Jeśli stan ładunku nie został określony jako _Wysłany_, system automatycznie potwierdzi ładunek przed uruchomieniem aktualizacji dokumentu przyjęcia produktów. (Stan ładunku jest ustawiany na _Wysłany_, gdy użytkownik rejestruje wychodzącą dostawę ładunku)

Do dokumentu przyjęcia produktów — księgowanie rejestracji przyjęcia skojarzonych z wybranym ładunkeim, przez co pracownik wybiera akcję **Przyjecia produktu** na stronie **Ładunek**. Otwarta strona zawiera następujące szczegóły kluczowe:

- W polu **Ilość** w sekcji **Parametry** na karcie **Ustawienia** wyświetlana jest _zarejestrowana ilość_. W tym miejscu nie są dostępne żadne inne opcje.
- Siatka na skróconej karcie **Omówienie** zawiera listę wszystkich zamówień zakupu uwzględnionych w wybranym ładunku.
- Siatka na skróconej karcie **Wiersze** wyświetla listę wszystkich wierszy zamówienia, dla których zarejestrowano ilość.

> [!NOTE]
> Ilości dla wierszy zamówienia wyświetlanych na karcie **Wiersz** są obliczane w różny sposób, w zależności od tego , czy w danej wersji Supply Chain Management jest dostępna i włączona funkcja _Zezwalaj na wiele odbiorów produktów na ładunek_.
>
> | Wersja | Obliczenie |
> |---|---|
> | Wersje przed wersją 10.0.10 i nowsze wersje,w których nie jest włączona funkcja _Zezwalaj na wiele odbiorów produktów na ładunek_ | Ilość w wierszu to suma wszystkich zarejestrowanych ilości _dla danego wiersza zamówienia zakupu_, niezależnie od tego, czy rejestracja została wykonana na wielu ładunkach, niezależnie od ładunku, od urządzenia przenośnego ani od klienta. |
> | Wersje 10.0.10 i nowsze,w których jest włączona funkcja _Zezwalaj na wiele odbiorów produktów na ładunek_ | Ilość w wierszu to suma wszystkich zarejestrowanych ilości _dla rekordu ładunku_, z którego zainicjowano akcję **księgowania przyjęcia produktów**. |

Gdy użytkownik wybierze **OK**, aby potwierdzić księgowanie dokumentu przyjęcia produktów, system wykonuje następujące aktualizacje kluczy w odpowiednich jednostkach.

| Jednostka | Aktualizacje |
|---|---|
| Transakcja magazynowa zamówienia zakupu, dla której w zakresie księgowania uwzględniono ilości wierszy | <p>Następujące pola są aktualizowane (ale zauważ, że istnieje także wiele innych aktualizacji):</p><ul><li>W polu <b>Odbiór</b> jest ustawiona wartość <i>Odebrano</i>.</li><li>Pole <b>Data fizycznej transakcji</b> jest aktualizowane na podstawie daty księgowania.</li></ul> |
| Ładunek, z którego użytkownik zaksięgował dokument przyjęcia produktów | Aktualizacje ładunku będą zależeć od używanej wersji i ustawienia pola **Zezwalaj na przyjęcie wielu produktów na ładunek**. Reguły są opisane w tabeli, która znajduje się w dalszej części tej sekcji. |

Pole **Zezwalaj na wiele odbiorów produktów na ładunek** umożliwia wybranie zasady odbioru ładunku przychodzącego. W zależności od ich przepływów operacyjnych firmy mogą zezwalać na księgowanie lub zezwalanie na tworzenie wielu dokumentów przyjęcia produktów dla tego samego ładunku. Zaleca się, aby menedżer logistyki ustawił pole **Zezwalaj na wiele odbiorów produktów na ładunek** na jedną z następujących wartości:

- **Nie** — tę wartość należy wybrać, jeśli pracownik etatowy w magazynie zawsze rejestruje wszystkie ilości zamówień, które przychodzą z każdym ładunkiem w określonym przedziale czasu. Jeśli nie zarejestrowano żadnych ilości ładunku, system zakłada, że nie dotarły lub nie były w ładunku i dlatego nie powinny być uważane za część ładunku. Podczas księgowania dokumentu przyjęcia produktów uruchamianego na ładunku jest używane to samo założenie. Oprócz dokumentu przyjęcia produktów — aktualizacja wszystkich zarejestrowanych ilości (jego główna funkcja) deklaruje zakończenie ładunku i zamknięcie w celu dodatkowego przetworzenia. W takim przypadku wszystkie ilości wiersza ładunku zostanie automatycznie zaktualizowana do zarejestrowanych ilości, wiersze ładunku bez zarejestrowanej ilości zostaną usunięty, a stan ładunku zmieni się na _Odebrany_.
- **Tak** — tę wartość należy wybrać, jeśli pracownik etatowy magazynu wymaga więcej czasu na rejestrację wszystkich ilości w ładunku, który dotarł, ale w międzyczasie musi być dokument przyjęcia produktów — zaksięgowanie ilości dla już zarejestrowanych ilości. W takim przypadku menedżer logistyki chce zachować ładunek otwarty nawet po uruchomieniu zadania księgowania dokumentu przyjęcia produktów, aby można było na bieżąco rejestrować pozostałe ilości ładunku i dokument przyjęcia produktów — aktualizowane regularnie w księdze.
- **Monituj** — tę wartość należy wybrać, jeśli metody odbierania ładunku są mieszane, a decyzja jest wymagana przy każdym uruchomieniu księgowania dokumentu przyjęcia produktów.

W poniższej tabeli zestawiono wyniki dla ustawienia **Zezwalaj na wiele odbiorów produktów na ładunek**.

| Zezwalaj na wiele odbiorów produktów na ładunek | Ilość ładunku | Stan ładunku | Notatka |
|---|---|---|---|
| Jeśli to pole nie jest dostępne (wersje przed 10.0.10) | <p>Ilość ładunku jest ustawiona tak, aby była równa zarejestrowanej ilości.</p><p>Jeśli ilość ładunku jest zaktualizowana na 0 (zero), co oznacza, że nie dokonano rejestracji, wiersz ładunku jest usuwany.</p><p>Jeśli ładunek nie zawiera żadnych wierszy ładunku, ładunek jest usuwany.</p> | _Odebrane_ | Jeśli dla zarejestrowanej ilości wiersza zamówienia istnieje wiele ładunków, tylko stan ładunku, z którego zaksięgowano przyjęcie jest aktualizowany na _Odebrano_. |
| Nr | <p>Ilość ładunku jest ustawiona w taki sposób, aby była równa ilości zarejestrowanej, która jest skojarzona z identyfikatorem ładunku.</p><p>Jeśli dla transakcji magazynowej nie zarejestrowano żadnego identyfikatora ładunku, zachowanie jest zgodne z zachowaniem w wersjach przed 10.0.10.</p> | _Odebrane_ | |
| Tak | Bez aktualizacji | _Odebrano_, jeśli całkowita zarejestrowana ilość ładunku jest równa lub większa od ilości ładunku | |
| Tak | Bez aktualizacji | _Wysłano_ lub _W toku_, jeśli całkowita zarejestrowana ilość ładunku jest mniejsza od ilości ładunku | |

Po ustawieniu pola **Stan ładunku** na wartość _Odebrano_ nie można już księgować dokumentów przyjęcia produktów dla tego ładunku. Pracownik może jednak zarejestrować pozostałą ilość zamówienia w odniesieniu do przyjętego ładunku w następujących warunkach: (Aby uzyskać więcej informacji, zobacz sekcję [Przekroczenia odbioru ładunku](#load-over-receiving) we wcześniejszej części tego tematu.)

- Wersja Supply Chain Management jest starsza niż wersja 10.0.11.
- Funkcja _Przyjęcie nadwyżki ilości ładunku_ jest włączona, a pole **Odbiór ilości nadwyżki wiersza ładunku** w elemencie menu urządzenia przenośnego dla akcji odbiór towaru ładunku jest ustawiona na wartość _Zezwalaj_.

Do dokumentu przyjęcia produktów — księgowanie dodatkowych zarejestrowanych ilości ładunku w odniesieniu do ładunku o stanie _Odebrano_, a użytkownik musi uruchomić akcję księgowania ze skojarzonego zamówienia zakupu.

### <a name="post-registered-quantities-from-the-purchase-order-page"></a>Księguj zarejestrowane ilości ze strony Zamówienia zakupu

Aby dokument przyjęcia produktów — księgowanie zarejestrowanych ilości na stronie **Zamówienie zakupu**, użytkownik wypełnia następujące zadania przed wybraniem akcji **Dokumentu przyjęcia produktów**:

- Ustaw pole **Ilość** w sekcji **Parametry** na karcie **Ustawienia** na _Zarejestrowana ilość_.
- W polu **Dokument przyjęcia produktów** wprowadź numery zamówień zakupu, które zostaną uwzględnione w księgowaniu.

> [!NOTE]
> Ilość w wierszu, które mają być uwzględnione w zakresie księgowania, to suma wszystkich zarejestrowanych ilości dla danego wiersza zamówienia, niezależnie od tego, czy rejestracja ilości została wykonana na wielu ładunkach, niezależnie od ładunku, od urządzenia przenośnego ani od klienta. Ta sama reguła ma zastosowanie w przypadku, gdy księgowanie dokumentu przyjęcia produktów odbywa się z ładunku, jeśli pole **Zezwalaj na wiele odbiorów produktów na ładunek** jest niedostępne lub nie jest włączone.

Gdy użytkownik wybierze **OK**, aby potwierdzić księgowanie dokumentu przyjęcia produktów, system wykonuje następujące aktualizacje kluczy w odpowiednich jednostkach.

| Jednostka | Aktualizacje |
|---|---|
| Transakcja magazynowa zamówienia zakupu, dla której w zakresie księgowania uwzględniono ilości wierszy | <p>Następujące pola są aktualizowane (ale zauważ, że istnieje także wiele innych aktualizacji):</p><ul><li>W polu <b>Odbiór</b> jest ustawiona wartość <i>Odebrano</i>.</li><li>Pole <b>Data fizycznej transakcji</b> jest aktualizowane na podstawie akcji księgowania przyjęcia produktów.</li></ul> |
| Obciążenie pracą | Aktualizacje ładunku zależą od tego, czy dla pole **Zezwalaj na wiele odbiorów produktów na ładunek** jest dostępne i włączone. Reguły te są opisane w następnej tabeli. |

W poniższej tabeli zestawiono wyniki dla ustawienia **Zezwalaj na wiele odbiorów produktów na ładunek**.

| Zezwalaj na wiele dokumentów przyjęcia produktów na ładunek | Ilość ładunku | Stan ładunku | Notatka |
|---|---|---|---|
| Jeśli to pole jest wyłączone lub niedostępne (w wersjach przed 10.0.10) | Bez aktualizacji | Nie wykonano żadnych aktualizacji. ( Stan pozostaje _Otwarte_, _Wysłane_ lub _W toku_.) | Ponieważ księgowanie dokumentu przyjęcia produktów jest inicjowane z poziomu zamówienia zakupu, logika aktualizacji nie zawiera informacji o skojarzeniu między zarejestrowanymi ilościami w jego zakresie a ładunkami, na które zarejestrowano rekord. W związku z tym nie można wybrać ładunku dla aktualizacji stanu. |
| Włączono | Bez aktualizacji | <p>Następuje jedna z następujących czynności:</p><ul><li>Stan jest zmieniany na <i>Odebrane</i>, jeśli łączna ilość odebranych i nabytych ilości transakcji magazynowych zamówienia zakupu jest większa lub równa ilości ładunku, z którym jest skojarzona.</li><li>Stan pozostaje <i>Otwarty</i>, <i>Wysłano</i> lub <i>W toku</i>, jeśli poprzedni warunek nie jest spełniony dla wszystkich wierszy ładunku.</li></ul> | |

### <a name="select-the-appropriate-product-receipt-posting-option-for-your-logistics-operations"></a>Wybierz odpowiednią opcję księgowania dokumentu przyjęcia produktów dla operacji logistycznych

Jak poprzednio opisano, system oferuje dwie opcje księgowania dokumentów przyjęcia produktów. Dostęp do opcji można uzyskać w następujących miejscach:

- Na stronie **Ładunek** lub z menu **Zarządzanie magazynem \> Zadania okresowe** jako zadania aktualizacji
- Na stronie **Zamówienie zakupu** lub z menu **Zaopatrzenie i sourcing \> Zamówienia zakupu \> Przyjęcia produktów** jako zadanie aktualizacji

Dla firm korzystających z ładunków do planowania i zarządzania transportem i obsługą magazynów związanych z ich zamówieniami przychodzącymi zaleca się użycie następujących funkcji, które są przeznaczone do pracy z ładunkami:

- Akcje **Odbierana pozycja ładunku** na swoich urządzeniach przenośnych magazynowych, aby zarejestrować przybycie ilości produktów w ładunku
- Akcje **Księgowania przyjęcia produktów** inicjowane z ładunku w celu zaktualizowania księgi zapasów

> [!NOTE]
> Do obsługi odpowiednich przychodzących procesów operacyjnych można używać innych funkcji rejestracji ilości i księgowania dokumentów przyjęcia produktów. Jeśli jednak są one stosowane zamiennie z użyciem lub zamiast dedykowanych funkcji ładunku, można zmniejszyć dokładność danych rekordów ładunku, a w konsekwencji uniemożliwić płynność przepływów zarządzania ładunkiem.

## <a name="example-scenarios"></a>Przykładowe scenariusze

### <a name="prepare-your-system-to-run-the-sample-scenarios"></a>Przygotuj system do uruchomienia przykładowych scenariuszy

Aby pracować z przykładowymi scenariuszami opisanymi w tej sekcji, należy najpierw upewnić się, że wszystkie wymagane funkcje są włączone w systemie. Wymagane dane demonstracyjne muszą być również dostępne w systemie.

#### <a name="turn-on-the-required-features"></a>Włącz wymagane funkcje

Te scenariusze wymagają funkcji _Księgowanie wielu odbiorów produktów na ładunek_ i jej wstępnie wymaganej funkcji. Administratorzy mogą włączać te funkcje, wykonując następujące kroki:

1. Otwórzz obszar roboczy **Zarządzanie funkcjami**. (Aby uzyskać pełne informacje na temat znajdowania i używania tego obszaru roboczego, zobacz [Zarządzanie funkcjami — omówienie](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).)

1. Włącz funkcję  _Skojarz transakcje magazynowe zamówienia zakupu z ładunkiem_, która jest wymieniona w następujący sposób:

    - **Moduł:** _Zarządzanie magazynem_
    - **Nazwa funkcji:** _Skojarz transakcje magazynowe zamówienia zakupu z ładunkiem_

1. Włącz funkcję _Księgowanie wielu odbiorów produktów na ładunek_, która jest wymieniona w następujący sposób:

    - **Moduł:** _Zarządzanie magazynem_
    - **Nazwa funkcji:** _Księgowanie wielu odbiorów produktów na ładunek_

#### <a name="enable-sample-data"></a>Włącz dane przykładowe

Aby pracować z tymi scenariuszami przy użyciu określonych przykładowych rekordów i wartości, należy użyć systemu, w którym są zainstalowane standardowe dane demonstracyjne. Należy również wybrać firmę **USMF** przed rozpoczęciem.

#### <a name="add-a-menu-item-for-receiving-load-items-when-a-mobile-device-is-used"></a>Dodaj element menu na potrzeby odbierania elementów ładunku, gdy jest używane urządzenie przenośne

Zanim pracownik etatowy magazynu będzie mógł skorzystać z urządzenia przenośnego w celu zarejestrowania zapasów przychodzących, które są połączone z ładunkiem, należy utworzyć w tym celu element menu urządzenia przenośnego.

W tej sekcji zostanie utworzony element menu urządzenia przenośnego i dodany do istniejącego menu. Pracownik magazynu może następnie wybrać pozycję menu w aplikacji Magazynowanie.

1. Przejdź do **Zarządzanie magazynem \> Ustawienia \> Urządzenie przenośne \> Elementy menu urządzenia przenośnego** i upewnij się, że menu urządzenia przenośnego zawiera element menu z następującymi ustawieniami:

    - **Tryb:** _Praca_
    - **Proces tworzenia pracy:** _Odbierana pozycja ładunku_
    - **Generuj numer identyfikacyjny:** _Tak_

    Istnieje możliwość pozostawienia wszystkich pozostałych ustawień w wartościach domyślnych.

    ![Ustawienia pozycji menu urządzenia mobilnego](media/inbound-mobile-menu-items.png "Ustawienia pozycji menu urządzenia mobilnego")

    Aby uzyskać więcej informacji o konfigurowaniu elementów menu urządzeń przenośnych, zapoznajsię z tematem [Konfigurowanie urządzeń przenośnych do pracy magazynowej](configure-mobile-devices-warehouse.md).

2. Po skończeniu ustawiania elementu menu, przejdź do **Zarządzanie magazynem \> Ustawienia \> Urządzenie przenośne \> Elementy menu urządzenia przenośnego** i dodaj je ddo struktury menu dla twoich urządzeń przenośnych.

### <a name="example-scenario-1-register-a-load-where-some-items-are-missing"></a>Przykładowy scenariusz 1: Zarejestruj ładunek, w którym brakuje niektórych towarów

W tym scenariuszu przedstawiono sposób rejestrowania ilości dla ładunku przychodzącego, w którym nie wszystkie oczekiwane ilości są obecne. Następnie pokazuje sposób księgowania dokumentu przyjęcia produktów dla zamówienia zakupu.

#### <a name="create-a-load-to-plan-receipt-of-a-purchase-order"></a>Tworzenie ładunku w celu zaplanowania przyjęcia zamówienia zakupu

W tej procedurze ręcznie utworzysz zamówienie zakupu i powiązany ładunek. Następnie wykonasz aktualizację każdego ładunku w celu symulacji, że został on wysłany przez dostawcę (który aktualizuje stan ładunku). Następnie w terminarzach magazynowych można filtrować ładunki według **Stanu ładunku**, aby znaleźć oczekiwane ładunki przychodzące.

1. Wybierz kolejno opcje **Zaopatrzenie i sourcing \> Zamówienia zakupu \> Wszystkie zamówienia zakupu**.
1. Wybierz pozycję **Nowy**.
1. W oknie dialogowym **Tworzenie zamówienia zakupu** w polu **Konto dostawcy** należy określić wartość _1001_.
1. Naciśnij przycisk **OK**, aby zamknąć okno dialogowe i utworzyc zamówienie zakupu.
1. Nowe zamówienie zakupu już zawiera wiersz pod **Wierszami zamówienia zakupu**. Dla tego wiersza należy określić następujące wartości:

    - **Numer pozycji:** _A0001_
    - **Magazyn:** _24_
    - **Ilość:** _10_

1. W okienku akcji na karcie **Zakup** wybierz **Akcje \> Potwierdź**. Stan zamówienia jest teraz _Potwierdzone_.
1. W okienku akcji na karcie **Magazyn** wybierz **Akcje \> Warsztat planowania wysyłki ładunku**.
1. Na stronie **Warsztat planowania wysyłki ładunku**, w okienku akcji, na karcie **Podaż i popyt** wybierz opcję **Dodaj \> Do nowego ładunku**.
1. W oknie dialogowym **Przydział szablonu ładunku**, w polu **Identyfikator szablonu ładunku** określ wartość _20 kontenerów_.
1. Naciśnij przycisk **OK**, aby zamknąć okno dialogowe i wróć do warsztatu.
1. W sekcji **Ładunek** wybierz opcję **Identyfikator ładunku**, aby otworzyć nowo utworzony ładunek.
1. Przejrzyj nagłówek ładunku i szczegóły wiersza i zwróć uwagę na następujące kwestie:

    - W na skróconej karcie **Ładunek** pole **Stan ładunku** jest ustawione na wartość _Otwarte_.
    - W sekcji **Wiersze ładunku** znajduje się jeden wiersz, w którym w polu **Ilość** jest ustawiona wartość _10_, a w polu **Ilość stworzonych prac** wartość wynosi _0_ (zero).

    ![Szczegóły ładunku](media/inbound-load-details.png "Szczegóły ładunku")

1. W okienku akcji na karcie **Wyślij i odbierz** wybierz **Potwierdź \> Przychodząca dostawa**. Zwróć uwagę, że **Stan ładunku** zmienił się na _Wysłane_.
1. Zanotuj wartość **Identyfikatora ładunku**, aby można było z niej skorzystać w następnej procedurze.

#### <a name="register-receipt-of-the-quantities-that-arrived-on-the-load"></a>Rejestrowanie przyjęcia ilości, które dotarły do ładunku

Gdy ładunek dociera do doku przyjęcia do magazynu, pracownik otrzymujący rejestruje ilości ładunku na urządzeniu przenośnym.

1. Zaloguj się do magazynu 24 przy użyciu urządzenia przenośnego. (W standardowych danych demonstracyjnych zaloguj się, używając _24_ jako identyfikatora użytkownika i _1_ jako hasła.)
1. Wybierz element menu _Odbierana pozycja ładunku_, który został utworzony dla tego scenariusza.
1. Postępuj zgodnie z instrukcjami dotyczącymi wprowadzania danych na ekranie, aby wprowadzić następujące wartości: (Kolejność może być inna w zależności od używanego urządzenia przenośnego lub emulatora.)

    - **Ładunek** — umożliwia wprowadzenie identyfikatora ładunku utworzonego w poprzedniej procedurze.
    - **Pozycja** — wpowadź _A0001_, czyli towar, który jest oczekiwany dla tego ładunku.
    - **Ilość** — należy wprowadzić wartość _9_ jako rzeczywistą ilość, która jest obecna w ładunku. Zauważ, że ta ilość jest mniejsza niż ilość oczekiwana.

1. Kontynuuj przechodzenie przez przepływ pracy, pozostawiając wszystkie pozostałe pola puste lub ustawione na wartości domyślne, dopóki urządzenie nie poinformuje, że praca została ukończona.

Zadanie odbierania ładunku jest teraz zakończone, a pracownik odbierający jest w stanie przenieść się do jego następnego zadania. Jednak pracownicy otrzymujący magazynu będą dokonywać przeglądu rekordu ładunku i będą mogli zobaczyć, że przyjęta ilość była mniejsza niż ilość oczekiwana. Następnie wykonają poniższą procedurę, korzystając z klienta sieci Web.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ładunki \> Wszystkie ładunki**.
1. Na liście znajdź dopiero co odebrany ładunek. (Może być konieczne zaznaczenie pola wyboru **Wyświetl zamknięte**, aby uwzględnić ładunki przychodzące mające stan ładunku _Wysłane_.) Następnie wybierz łącze w kolumnie **Identyfikator ładunku**, aby otworzyć ładunek.
1. W rekordzie ładunku zwróć uwagę, że wartość **Stanu ładunku** pozostanie _Wysłany_, ale wartość w polu **Ilość stworzonych prac** w wierszu ładunku została zmieniona na _9_.
1. Wybierz kolejno opcje **Zaopatrzenie i sourcing \> Zamówienia zakupu \> Wszystkie zamówienia zakupu**.
1. Na liście znajdź nabyty zakup, a następnie wybierz łącze w kolumnie **Zamówienie zakupu**, aby otworzyć zamówienie.
\
1. Na skróconej karcie **Wiersze zamówienia zakupu** wybierz **Zapasy \> Wyświetl \> Transakcje**.
1. Umożliwia przejrzenie szczegółów dwóch transakcji zamówienia zakupu. (Konieczne może być spersonalizowanie strony **Transakcje magazynowe**, aby wyświetlić pole **Identyfikator ładunku** w siatce.) Powinny zostać wyświetlone dwie transakcje:

    - Transakcja mająca przychód w stanie _Zarejestrowanym_ reprezentuje ilość zarejestrowaną _9_, która została uruchomiona w ramach określonego ładunku za pomocą urządzenia przenośnego. **Identyfikator ładunku** jest skojarzony z daną transakcją.
    - Transakcja mająca przychód w stanie _Zamówione_ reprezentuje pozostałą niezarejestrowana ilość w wierszu zamówienia równą _1_.

#### <a name="product-receiptpost-the-registered-load-quantities-against-purchase-orders"></a>Przyjęcie produktu - zaksięguj zarejestrowane ilości załadunku na podstawie zamówień zakupu

W tej procedurze dokument przyjęcia produktów — księgowanie zapasów zarejestrowanych na potrzeby ładunku. W wyniku tego odebrane zapasy i koszty związane z nimi zostaną dodane do księgi głównej firmy.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ładunki \> Wszystkie ładunki**.
1. Na liście znajdź odebrany ładunek. (Może być konieczne zaznaczenie pola wyboru **Wyświetl zamknięte**, aby uwzględnić ładunki przychodzące mające stan ładunku _Wysłane_.) Następnie wybierz łącze w kolumnie **Identyfikator ładunku**, aby otworzyć ładunek.
1. W okienku akcji na karcie **Wyślij i odbierz** wybierz **Odbierz \> Przyjęcie produktu**. Kliknij **Tak**, jeśli zostanie wyświetlony monit o potwierdzenie wyboru.
1. W oknie dialogowym **Księgowanie dokumentu przyjęcia produktów** na skróconej karcie **Wiersz** sprawdź siatkę. Powinien być widoczny wiersz zamówienia zakupu, dla którego ilość została zarejestrowana w odniesieniu do wybranego ładunku.

    > [!NOTE]
    > W wersjach, w których funkcja _Księgowanie wielu odbiorów produktów na ładunek_ jest niedostępna lub nie jest włączona, domyślną ilością wyświetlaną w siatce **Wwierszy ładunku** będzie ilość całkowita, która została zarejestrowana dla wszystkich ładunków skojarzonych z wierszem zamówienia zakupu.

1. Na skróconej karcie **Omówienie** sprawdź pole **Dokument przyjęcia produktów** w siatce. Zwróć uwagę, że jest ustawione na numer, który zawiera identyfikator wybranego ładunku.
1. Wybierz **OK**, aby zaksięgować dokument przyjęcia produktów i zamknąć okno dialogowe **Księgowanie dokumentu przyjęcia produktów**.
1. Powrócisz do szczegółów ładunku. Należy zauważyć następujące informacje:

    - Pole **Stan ładunku** jest teraz ustawione na wartość _Odebrano_.
    - W wierszu ładunku wartość **Ilość** dla ładunku została zmieniona z _10_ na _9_ sztuk w celu dopasowania do zarejestrowanej ilości, ale wartość w polu **Ilość stworzonych prac** pozostanie _9_.

Jeśli zespół kupujący nie oczekuje, że pozostała ilość zamówienia wynosi 1, można zamknąć zamówienie, aktualizując resztę dostawy wiersza do wartości _0_. Jeśli jednak okaże się, że brakująca część dotarła do oryginalnego ładunku, personel magazynu może wykonać jedną z następujących akcji:

- Zarejestruj ilość w odniesieniu do tego samego ładunku. W takim przypadku pole **Stan ładunku** zostanie zresetowane do wartości _Wysłane_, a wartość w polu **Ilość stworzonych prac** zostanie zaktualizowana na _10_. Ta opcja jest dostępna tylko w następujących sytuacjach:

    - Funkcja _Przyjęcie nadwyżki ilości ładunku_ jest niedostępna lub nie jest włączona.
    - Funkcja _Przyjęcie nadwyżki ilości ładunku_ jest dostępna i włączona, a pole **Odbiór ilości nadwyżki wiersza ładunku** jest ustawione na wartość _Zezwalaj_.

- Dodaj ilość do nowego lub istniejącego ładunku i przetwórz ją w zwykły sposób.
- Zarejestruj i/lub przyjmij ilość w sposób, który nie wymaga obsługi ładunku.

### <a name="example-scenario-2-register-quantities-that-arrive-on-multiple-inbound-loads-where-some-items-are-missing"></a>Przykładowy scenariusz 2: Zarejestruj ilości, które przychodzą z wieloma ładunkami przychodzącymi w przypadku braku niektórych towarów

W tym scenariuszu wysyłka przychodząca, która jest powiązana z pojedynczym wierszem zamówienia zakupu, zostanie podzielona na dwa ładunki. Na przykład wiersz zamówienia zakupu może być podzielony na kilka ładunków z powodu fizycznych ograniczeń dotyczących wagi i/lub objętości.

W tym scenariuszu opisano również sposób przetwarzania księgowania wielu dokumentów przyjęcia produktów dla tego samego ładunku. Użytkownik będzie rejestrował ilości przychodzące z wieloma ładunkami przychodzącymi, ale gdy ilości nie odpowiadają oczekiwanym ilościom. Aktualizacje kosztów, które wystąpiły za pomocą księgowania odbioru produktów, zostaną wielokrotnie wykonane dla tego samego ładunku.

#### <a name="set-up-load-receiving-policies"></a>Skonfiguruj zasady odbierania ładunków

W tej procedurze zostanie włączone księgowanie wielu odbiorów produktów na ten sam ładunek.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Parametry zarządzania magazynem**.
1. Na karcie **Ładunek**, w polu **Zezwalaj na wiele odbiorów produktów na ładunek** ustaw wartość _Tak_.

#### <a name="create-two-loads-to-plan-receipt-of-a-purchase-order"></a>Tworzenie dwóch ładunków w celu zaplanowania przyjęcia zamówienia zakupu

W tej procedurze utworzysz zamówienie zakupu i dwa ładunki. Następnie wykonasz ręczną aktualizację każdego ładunku w celu symulacji, że został on wysłany przez dostawcę (który aktualizuje stan ładunku). Następnie w terminarzach magazynowych można filtrować ładunki według **Stanu ładunku**, aby znaleźć oczekiwane ładunki przychodzące.

Można również dowiedzieć się, jak skonfigurować wiersz zamówienia zakupu, tak aby można było przyjąć ilość, która jest o 20 procent większa od ilości określonej dla danego wiersza.

1. Wybierz kolejno opcje **Zaopatrzenie i sourcing \> Zamówienia zakupu \> Wszystkie zamówienia zakupu**.
1. Wybierz pozycję **Nowy**.
1. W skróconej karcie **Dostawcy** określ wartość w polu **Konto dostawcy** na _1001_, a następnie kliknij przycisk **OK**.
1. Nowe zamówienie zakupu zostało otwarte i zawiera pusty wiersz w siatce **Wiersze zamówienia zakupu**. Dla tego wiersza zamówienia należy określić następujące wartości:

    - **Numer pozycji:** _A0001_
    - **Magazyn:** _24_
    - **Ilość:** _10_

1. Na skróconej karcie **Szczegółów wiersza** na karcie **Dostawa** należy określić wartość w polu **Nadwyżka** na _20_.
1. W okienku akcji na karcie **Zakup** wybierz **Akcje \> Potwierdź**. Stan zamówienia jest teraz _Potwierdzone_.
1. W okienku akcji na karcie **Magazyn** wybierz **Akcje \> Warsztat planowania wysyłki ładunku**.
1. Na stronie **Warsztat planowania wysyłki ładunku**, w okienku akcji, na karcie **Podaż i popyt** wybierz opcję **Dodaj \> Do nowego ładunku**.
1. W oknie dialogowym **Przydział szablonu ładunku**, w polu **Identyfikator szablonu ładunku** określ wartość _20 kontenerów_. Na karcie **Szczegóły** zmień wartość **Ilości** z _10_ na _5_, aby częściowo dodać ilość w wierszu zamówienia zakupu.
1. Wybierz przycisk **OK**, aby zastosować ustawienia i zamknąć okienko dialogowe.
1. Powtórz kroki od 8 do 10, aby utworzyć drugi ładunek. Tym razem pole **Ilość** powinno być już ustawione na _5_.
1. Na stronie **Warsztat planowania wysyłki ładunku** w siatce **Ładunek** wybierz wartość **Identyfikatora ładunku** dla pierwszego utworzonego ładunku. Zostanie wyświetlona strona **Szczegóły ładunku**, która pokazuje wybrany ładunek. Wykonaj następujące kroków:

    1. W okienku akcji na karcie **Wyślij i odbierz** wybierz **Potwierdź \> Przychodząca dostawa**.
    1. Zwróć uwagę, że wartość **Stan ładunku** zmieniła się na _Wysłane_.
    1. Wybierz przycisk zamknij, aby powrócić do strony **Warsztat planowania wysyłki ładunku**.

1. Powtórz poprzedni krok w odniesieniu do drugiego utworzonego ładunku.
1. Zanotuj dwie wartości **Identyfikator ładunku**, które znajdują się w siatce **Ładunku**.

#### <a name="register-partial-receipt-of-the-quantities-that-arrived-on-the-first-load-and-post-the-registered-load-quantities"></a>Umożliwia rejestrowanie częściowego przyjęcia ilości, które dotarły z pierwszym ładunkiem i zaksięgowanie zarejestrowanych ilości ładunku

Gdy ładuneki docierają do doku przyjęcia do magazynu, pracownik otrzymujący rejestruje ilości ładunku na urządzeniu przenośnym. Zarejestrowane zapasy, które są powiązane z ładunkiem, są następnie aktualizowane wraz z kosztami w księdze głównej firmy przez zaksięgowanie dokumentu przyjęcia produktów zamówienia zakupu na podstawie ładunku.

W tej procedurze przedstawiono sposób rejestrowania przez pracownika odbierającego ilości ładunku na urządzeniu przenośnym.

1. Zaloguj się do magazynu 24 przy użyciu urządzenia przenośnego. (W standardowych danych demonstracyjnych zaloguj się, używając _24_ jako identyfikatora użytkownika i _1_ jako hasła.)
1. Wybierz element menu _Odbierana pozycja ładunku_, który został utworzony dla tego scenariusza.
1. Postępuj zgodnie z instrukcjami dotyczącymi wprowadzania danych na ekranie, aby wprowadzić następujące wartości: (Kolejność może być inna w zależności od używanego urządzenia przenośnego lub emulatora.)

    - **Ładunek** — umożliwia wprowadzenie identyfikatora pierwszego ładunku utworzonego w poprzedniej procedurze.
    - **Pozycja** — wpowadź _A0001_, czyli towar, który jest oczekiwany dla tego ładunku.
    - **Ilość** — wprowadź wartość _3_. Zauważ, że ta ilość jest mniejsza niż ilość oczekiwana. W tym scenariuszu załóżmy, że użytkownik, jako pracownik otrzymujący, nie ma czasu na rejestrowanie wszystkich ilości tego ładunku. W dalszej części tej procedury zarejestrowano pozostałe sztuki, powtarzając ten krok i ustawiając wartość pola **Ilość** na _2_.

1. Kontynuuj przechodzenie przez przepływ pracy, pozostawiając wszystkie pozostałe pola puste lub ustawione na wartości domyślne, dopóki urządzenie nie poinformuje, że praca została ukończona.
1. W kliencie sieci Web wybierz kolejno opcje **Zarządzanie magazynem \> Ładunki \> Wszystkie ładunki**.
1. Na liście znajdź otrzymany ładunek i wybierz wartość **Identyfikatora ładunku**, aby otworzyć ładunek. Zwróć uwagę, że wartość **Stanu ładunku** pozostanie _Wysłany_, ale wartość w polu **Ilość stworzonych prac** w wierszu ładunku została zmieniona na _3_.
1. W okienku akcji na karcie **Wyślij i odbierz** wybierz **Odbierz \> Przyjęcie produktu**. Kliknij **Tak**, jeśli zostanie wyświetlony monit o potwierdzenie wyboru.
1. W oknie dialogowym **Księgowanie dokumentu przyjęcia produktów** sprawdź, ale nie zmieniaj wartości, które są widoczne, a następnie kliknij **OK**.
1. Powrócisz na stronę **Szczegóły ładunku** dla wybranego ładunku. Należy zauważyć następujące informacje:

    - Pole **Stan ładunku** pozostaje ustawione na wartość _Wysłano_.
    - W wierszu ładunku wartość **Ilości** dla ładunku pozostanie równa _5_ sztuk, która jest oryginalną ilością ładunku, a **Ilość stworzonych prac** nadal będzie równa _3_.

1. Zakończ rejestrację pozostałej ilości w tym ładunku, powtarzając tę procedurę. Jednak w kroku 3 należy określić wartość pola **ilość** równą _2_.

Zadanie przyjęcia dla pierwszego ładunku jest teraz zakończone. Utworzono dwa arkusze dokumentów przyjęcia produktów — jeden dla każdej z dwóch uruchomionych aktualizacji dokumentów przyjęcia produktów.

#### <a name="register-receipt-of-the-quantities-that-arrived-on-the-second-load-and-account-for-the-overdelivered-quantity"></a>Rejestrowanie przyjęcia ilości, które dotarły do drugiego ładunku i konta dostarczonej nadwyżki

W tym scenariuszu pracownik otrzymujący zarejestruje przychodzące ilości przekraczające ilość istniejącą w ładunku. Odbiór nadwyżki będzie dozwolony, ponieważ system jest skonfigurowany tak, aby zezwalał na nadwyżkę w dostawie.

1. Zaloguj się do magazynu 24 przy użyciu urządzenia przenośnego. (W standardowych danych demonstracyjnych zaloguj się, używając _24_ jako identyfikatora użytkownika i _1_ jako hasła.)
1. Wybierz element menu _Odbierana pozycja ładunku_, który został utworzony dla tego scenariusza.
1. Postępuj zgodnie z instrukcjami dotyczącymi wprowadzania danych na ekranie, aby wprowadzić następujące wartości: (Kolejność może być inna w zależności od używanego urządzenia przenośnego lub emulatora.)

    - **Ładunek** — wprowadź drugi wcześniej utworzony identyfikator ładunku.
    - **Pozycja** — wpowadź _A0001_, czyli towar, który jest oczekiwany dla tego ładunku.
    - **Ilość** — wprowadź wartość _7_, która jest pozostałą ilością, jaką dostawca ma do dostarczenia jako część całkowitej ilości zamówienia zakupu równą 12 (gdzie 10 jest oryginalną ilością zamówienia), a wartość 2 to dozwolona ilość nadwyżki w dostawie równa 20%). Należy pamiętać, że 5 sztuk już zarejestrowano w pierwszym ładunku.

Drugi ładunek został zaktualizoway z ilością 7 i może być odbiorem produktu — aktualizowanym na podstawie tej ilości.
