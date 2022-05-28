---
title: Wstrzymania kredytu dla zamówień sprzedaży
description: W tym temacie opisano ustawienia reguł używanych do umieszczania wstrzymania kredytu zamówienia sprzedaży.
author: JodiChristiansen
ms.date: 07/20/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 2d8966f993e7ca82b10a2ef5a023256a05682980
ms.sourcegitcommit: 5d1772bdeb21a9bec6dc49e64550aaf34127a4e2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/10/2022
ms.locfileid: "8734341"
---
# <a name="credit-holds-for-sales-orders"></a>Wstrzymania kredytu dla zamówień sprzedaży
[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

W tym temacie opisano ustawienia reguł używanych do umieszczania wstrzymania kredytu zamówienia sprzedaży. Reguły blokowania zarządzania kredytami mogą dotyczyć pojedynczego odbiorcy lub grupy odbiorców. Reguły blokowania definiują odpowiedzi na następujące okoliczności:

1. Liczba zaległych dni
2. Stan kont
3. Warunki płatności
4. Limit kredytu wygasł
5. Zaległa kwota
6. Kwota zamówienia sprzedaży
7. Część wykorzystana dostępnych kredytów

Ponadto istnieją dwa parametry kontrolujące dodatkowe scenariusze, które zablokują zamówienie sprzedaży:

1. Zmiana w warunkach płatności
2. Zmiana w rabatach w rozliczeniu

## <a name="set-up-blocking-rules-and-exclusion-rules"></a>Konfigurowanie reguł blokowania i reguł wykluczeń

Gdy odbiorca zainicjuje transakcję sprzedaży, informacje zawarte w zamówieniu sprzedaży są przeglądane według zbioru reguł blokowania, które kierują decyzję o przyznaniu kredytu odbiorcy i umożliwieniu kontynuowania transakcji sprzedaży. Można również zdefiniować wykluczenia, które zastąpią reguły blokowania i umożliwiają przetwarzanie zamówienia sprzedaży. Istnieje możliwość skonfigurowania reguł blokowania i reguł wykluczeń na stronie **Zarządzanie kredytem > Ustawienia > Ustawienia zarządzania kredytem > Reguły blokowania**.

Od wersji 10.0.21 zasady blokowania w zarządzaniu kredytami zostały ponownie zaprojektowane w następujący sposób, aby zapewnić większą elastyczność:

- Żądania rozszerzalności zostały włączone, dzięki czemu można utworzyć własne reguły blokowania.
- Pole wyboru **Zwolnij zamówienie sprzedaży** jest teraz dostępne dla wszystkich reguł blokowania. Wcześniej była dostępna tylko dla reguły blokowania zamówienia sprzedaży. Gdy to pole wyboru jest zaznaczone, reguła wykluczenia zwolni zamówienie sprzedaży bez uwzględniania innych reguł, które mogą blokować zamówienia sprzedaży. To pole wyboru jest dostępne tylko dla typu reguły **wykluczeń**.

### <a name="days-overdue"></a>Dni po terminie

Otwórz kartę **zaległe dni**, jeśli reguła blokowania ma zastosowanie do odbiorcy z jedną lub kilkoma fakturami, które zostały już niezapłacone przez określoną liczbę dni.
1. Wybierz zakres odbiorcy, dla którego regułą jest **Ważne dla**.
   - Opcję **Tabela** należy wybrać, jeśli reguła ma zastosowanie do określonego odbiorcy.
   - Wybierz **Grupa**, jeśli reguła jest stosowana na poziomie grupy odbiorców. 
   - Wybierz **Wszyscy** jeśli zasada dotyczy wszystkich odbiorców.
2. Po określeniu zakresu należy określić **konto/grupę**, które będą używane w zakresie.
   - W przypadku zakresu **tabeli** wyszukiwanie będzie zawierać listę odbiorców do wybrania. 
   - Umożliwia wybranie **grupy**, jeśli reguła jest stosowana do grupy kredytowej odbiorcy.
   - Wybierz **Wszyscy** jeśli zasada dotyczy wszystkich odbiorców. 
3. Wybierz opcję **Grupa ryzyka**, aby zastosować kryteria dotyczące stosowania wstrzymania zarządzania kredytami dla odbiorców, którzy są pogrupowani według wspólnego zbioru współczynników, takich jak rating Dun and Bradstreet, liczba lat prowadzenia działalności, czas bycia odbiorcą, itd.  
4. Służy do wybierania typu reguły, dla której wprowadzane są ustawienia. Opcja **blokowania** powoduje utworzenie reguły blokującej zamówienie. Opcja **wykluczania** powoduje utworzenie reguły, która będzie wykluczać inną regułę z zablokowania zamówienia. 
5. Wybierz **Typ wartości**. Domyślny wpis to stała liczba dni. W przypadku tworzenia wykluczenia zamiast tego można użyć stałej liczby dni lub ilości. 
6. Umożliwia wprowadzenie liczby dni **zaległych**, które będą dozwolone dla wybranej reguły blokowania, zanim zamówienie zostanie umieszczone w wstrzymaniu zarządzania kredytem do przeglądu. Liczba dni do realizacji jest równa dodatkowej liczbie dni prolongaty, która jest dodawana do liczby dni przekraczającej termin płatności, którą może mieć faktura, zanim zostanie uznana za zaległą. Jeśli **Typ wartości** został określony jako kwota wykluczenia, należy wprowadzić liczbę i walutę tej kwoty.

### <a name="account-status"></a>Stan konta

Umożliwia otwarcie karty **Stan konta**, jeśli reguła blokowania dotyczy odbiorcy o wybranym stanie konta.
1. Służy do wybierania typu reguły, dla której wprowadzane są ustawienia.  **Blokowanie** powoduje utworzenie reguły blokującej zamówienie. **Wykluczanie** tworzy regułę, która będzie wykluczać regułę z zablokowania zamówienia. 
2. Umożliwia wybranie **Stanu konta**, które spowoduje, że reguła będzie zawierać zamówienie sprzedaży zablokowane lub wyłączone.

### <a name="terms-of-payment"></a>Warunki płatności

Wybierz **Warunki płatności**, jeśli reguła blokowania dotyczy wybranego warunku płatności.
1. Służy do wybierania typu reguły, dla której wprowadzane są ustawienia.  **Blokowanie** powoduje utworzenie reguły blokującej zamówienie. **Wykluczanie** tworzy regułę, która będzie wykluczać regułę z zablokowania zamówienia. 
2. Umożliwia wybranie **Warunków płatności**, które spowoduje, że reguła będzie zawierać zamówienie sprzedaży zablokowane lub wyłączone.

### <a name="credit-limit-expired"></a>Limit kredytu wygasł

Otwórz kartę **Wygasł limit kredytu**, jeśli reguła blokowania dotyczy odbiorców z limitami kredytowymi, które wygasły.
1. Wybierz zakres odbiorcy, dla którego regułą jest **Ważne dla**.
   - Opcję **Tabela** należy wybrać, jeśli reguła ma zastosowanie do określonego odbiorcy.
   - Wybierz **Grupa**, jeśli reguła jest stosowana na poziomie grupy odbiorców. 
   - Wybierz **Wszyscy** jeśli zasada dotyczy wszystkich odbiorców.
2. Po określeniu zakresu należy określić **konto/grupę** używane w zakresie.
   - W przypadku zakresu **tabeli** wyszukiwanie będzie zawierać listę odbiorców do wybrania. 
   - Umożliwia wybranie **grupy**, jeśli reguła jest stosowana do grupy zarządzania kredytem odbiorcy.
   - Wybierz **Wszyscy** jeśli zasada dotyczy wszystkich odbiorców. 
3. Wybierz **Grupę ryzyka**, aby dodatkowo ograniczyć listę odbiorców, którzy będą umieszczani w wstrzymaniu zarządzania kredytami. 
4. Służy do wybierania typu reguły, dla której wprowadzane są ustawienia. 
   - Wybierz **Blokowanie**, aby spowodować utworzenie reguły blokującej zamówienie. 
   - Wybierz **Wykluczenie**, aby stworzyć reguły, która będzie wykluczać inną regułę z zablokowania zamówienia. 
5. Należy wprowadzić **Dni po wygaśnięciu limitu kredytu** dla wybranej reguły blokowania, zanim zamówienie zostanie umieszczone w wstrzymaniu zarządzania kredytem. Liczba zaległych dni reprezentuje dodatkowe dni prolongaty, które są dodawane do liczby dni po upłynięciu limitu kredytu.

### <a name="overdue-amount"></a>Zaległa kwota

Otwórz kartę **Zaległa kwota**, jeśli reguła blokowania dotyczy odbiorców z zaległymi kwotami.
1. Wybierz zakres odbiorcy, dla którego regułą jest **Ważne dla**.
   - Opcję **Tabela** należy wybrać, jeśli reguła ma zastosowanie do określonego odbiorcy.
   - Wybierz **Grupa**, jeśli reguła jest stosowana na poziomie grupy odbiorców. 
   - Wybierz **Wszyscy** jeśli zasada dotyczy wszystkich odbiorców.
2. Po określeniu zakresu należy określić **konto/grupę** używane w zakresie.
   - W przypadku zakresu **tabeli** wyszukiwanie będzie zawierać wyszukiwanie odbiorców. 
   - Umożliwia wybranie **grupy**, jeśli reguła jest stosowana do grupy zarządzania kredytem odbiorcy.
   - Wybierz **Wszyscy** jeśli zasada dotyczy wszystkich odbiorców. 
3. Wybierz **Grupę ryzyka**, aby dodatkowo ograniczyć listę odbiorców, którzy będą umieszczani w wstrzymaniu zarządzania kredytami. 
4. Służy do wybierania typu reguły, dla której wprowadzane są ustawienia. 
   - Wybierz **Blokowanie**, aby spowodować utworzenie reguły blokującej zamówienie. 
   - Wybierz **Wykluczenie**, aby stworzyć reguły, która będzie wykluczać inną regułę z zablokowania zamówienia. 
5. Należy wprowadzić **Zaległa kwota** dla wybranej reguły blokowania, zanim zamówienie zostanie umieszczone w wstrzymaniu zarządzania kredytem do przeglądu. 
6. Umożliwia wybranie **Typu wartości** określającego typ wartości, który zostanie użyty do sprawdzenia, jaka część limitu kredytu została użyta. Reguły blokowania i reguły wykluczania zezwalają na wartość procentową tylko dla **Zaległej kwoty**. Próg odnosi się do limitu kredytu.
7. Umożliwia wprowadzenie **wartości progowej limitu kredytu** dla wybranej reguły przed przejściem odbiorcy do wstrzymania zarządzania kredytem. Może to być kwota lub wartość procentowa na podstawie typu wartości, który można wybrać w polu Typ wartości.
8. Reguła sprawdza, czy **zaległa kwota** została przekroczona i czy przekroczono **próg limitu kredytu**. 

### <a name="sales-order"></a>Zamówienie sprzedaży 

Wybierz **Zamówienie sprzedaży**, jeśli reguła blokowania ma zastosowanie do wartości w zamówieniu sprzedaży.
1. Wybierz zakres odbiorcy, dla którego regułą jest **Ważne dla**.
   - Opcję **Tabela** należy wybrać, jeśli reguła ma zastosowanie do określonego odbiorcy.
   - Wybierz **Grupa**, jeśli reguła jest stosowana na poziomie grupy odbiorców. 
   - Wybierz **Wszyscy** jeśli zasada dotyczy wszystkich odbiorców.
2. Po określeniu zakresu należy określić **konto/grupę** używane w zakresie.
   - W przypadku zakresu **tabeli** wyszukiwanie będzie zawierać wyszukiwanie odbiorców. 
   - Umożliwia wybranie **grupy**, jeśli reguła jest stosowana do grupy zarządzania kredytem odbiorcy.
   - Wybierz **Wszyscy** jeśli zasada dotyczy wszystkich odbiorców. 
3. Wybierz **Grupę ryzyka**, aby dodatkowo ograniczyć listę odbiorców, którzy będą umieszczani w wstrzymaniu zarządzania kredytami. 
4. Służy do wybierania typu reguły, dla której wprowadzane są ustawienia.  
   - Wybierz **Blokowanie**, aby spowodować utworzenie reguły blokującej zamówienie. 
   - Wybierz **Wykluczenie**, aby stworzyć reguły, która będzie wykluczać inną regułę z zablokowania zamówienia. 
5. Należy wprowadzić **Kwota zamówienia sprzedaży** dla wybranej reguły blokowania, zanim zamówienie zostanie umieszczone w wstrzymaniu zarządzania kredytem. 

### <a name="credit-limit-used"></a>Wykorzystany limit kredytu

Wybierz **Wykorzystany limit kredytu**, jeśli reguła blokowania dotyczy wykorzystanej kwoty limitu kredytu odbiorcy.
1. Wybierz zakres odbiorcy, dla którego regułą jest **Ważne dla**.
   - Opcję **Tabela** należy wybrać, jeśli reguła ma zastosowanie do określonego odbiorcy.
   - Wybierz **Grupa**, jeśli reguła jest stosowana na poziomie grupy odbiorców. 
   - Wybierz **Wszyscy** jeśli zasada dotyczy wszystkich odbiorców.
2. Po określeniu zakresu należy określić **konto/grupę** używane w zakresie.
   - W przypadku zakresu **tabeli** wyszukiwanie będzie zawierać wyszukiwanie odbiorców. 
   - Umożliwia wybranie **grupy**, jeśli reguła jest stosowana do grupy zarządzania kredytem odbiorcy.
   - Wybierz **Wszyscy** jeśli zasada dotyczy wszystkich odbiorców. 
3. Wybierz **Grupę ryzyka**, aby dodatkowo ograniczyć listę odbiorców, którzy będą umieszczani w wstrzymaniu zarządzania kredytami. 
4. Służy do wybierania typu reguły, dla której wprowadzane są ustawienia.
   - Wybierz **Blokowanie**, aby spowodować utworzenie reguły blokującej zamówienie. 
   - Wybierz **Wykluczenie**, aby stworzyć reguły, która będzie wykluczać inną regułę z zablokowania zamówienia. 
5. Umożliwia wybranie **Pozostałego progu** określającego procent limitu kredytowego, który będzie blokować zamówienie sprzedaży. Jeśli wartość zamówienia zwiększa kwotę wykorzystanego limitu kredytu powyżej wartości procentowej, zamówienie zostanie wstrzymane. 

## <a name="put-a-sales-order-on-hold-based-on-other-criteria"></a>Umożliwia wstrzymanie zamówienia sprzedaży na podstawie innych kryteriów
  
### <a name="rank-payment-terms"></a>Klasyfikuj warunki płatności  

W przypadku zmiany warunków płatności można wymusić wykonanie reguł kontroli kredytu. Należy określić warunki płatności i przypisać im wartość rankingu. Jeśli warunki płatności w zamówieniu zostaną zmienione na warunki płatności, które są wyższe w rankingu od starych warunków płatności, zamówienie zostanie wysłane do zarządzania kredytami i wymagane jest zatwierdzenie.

Można ustawić klasyfikację warunków płatności na stronie **Zarządzanie kredytem > Ustawienia > Ustawienia zarządzania kredytami > Oceń warunki płatności**.

1. Wybierz warunki płatności dla pola **Warunki płatności** dla klasyfikacji; Po wybraniu terminu opis zostanie wyświetlony w polu **Opis**.
2. Wybierz miejsce w rankingu warunku w polu **Stopień**. Wszystkie te wartości odnoszą się do siebie, tak aby można było stosować 1, 2, 3 lub 10, 20, 30. Można również zastosować tę samą wartość dla większości warunków płatności, tak aby tylko jednen lub dwa warunki płatności powodowały wyzwolenie sprawdzania kredytu.

### <a name="rank-settlement-discounts"></a>Klasyfikuj rabaty rozliczeń   

W przypadku zmiany rabatów w rozliczeniu można wymusić wykonanie reguł kontroli kredytu. Należy określić rabaty w rozliczeniu i przypisać im wartość rankingu. Jeśli rabaty w rozliczeniu w zamówieniu zostaną zmienione na rabaty w rozliczeniu, które są wyższe w rankingu od starych rabatów w rozliczeniu, zamówienie zostanie wysłane do zarządzania kredytami i wymagane jest zatwierdzenie.

Można ustawić klasyfikację warunków płatności na stronie **Zarządzanie kredytem > Ustawienia > Ustawienia zarządzania kredytami > Oceń rabaty w rozliczeniu**.

1. Wybierz **Rabat gotówkowy**, który chcesz ocenić. Zostanie wyświetlony **Opis** rabatu w rozliczeniu.
2. Zaznacz wartość **Stopień**. Wszystkie te wartości odnoszą się do siebie, tak aby można było stosować 1, 2, 3 lub 10, 20, 30. Można również zastosować tę samą wartość dla większości rabatów w rozliczeniu, tak aby tylko jednen lub dwa rabaty w rozliczeniu powodowały wyzwolenie sprawdzania kredytu.

## <a name="sequence-the-application-of-rules"></a>Kolejność stosowania reguł

Reguły są uruchamiane w określonym zamówieniu, które można zmienić zgodnie z potrzebami danej organizacji. 

- Jedno wystąpienie reguł wykluczania zamówienia sprzedaży umożliwia zastąpienie wszystkich reguł, które mogą blokować zamówienie sprzedaży. Utwórz regułę wykluczania zamówienia sprzedaży i zaznacz opcję **Zwolnij zamówienie sprzedaży**. Zamówienie nie zostanie wstrzymane, jeśli reguła wykluczania jest spełniona, a żadne inne reguły nie zostaną sprawdzone.
- Blokowanie reguł może zablokować zamówienie.
- Reguły wykluczania są stosowane po regułach blokowania. Reguły wykluczania wpływają tylko na regułę, na której są zdefiniowane. 
- Reguły blokowania i wykluczania są uruchamiane w tabeli, następnie w grupie, następnie na wszystkich zamówieniach. Z powodu tej kolejności przetwarzania można mieć regułę blokowania na poziomie Wszystkich zamówień, który nie będzie uruchamiany, ponieważ jest uruchamiana reguła wykluczania na poziomie tabeli lub grupy.
- Wykluczenia nie zastępują reguły blokowania, jeśli znajdują się na tym samym poziomie. Na przykład reguła wykluczania na poziomie grupy nie zastępuje reguły blokowania na poziomie grupy. Wykluczenia nie muszą być konfigurowane na poziomie Wszystkich, chyba że z jednym wystąpieniem reguły wykluczania zamówienia sprzedaży jak zaznaczono powyżej. 

Zachowanie reguły **Wykorzystany limit kredytu** zmieni się na podstawie ustawień dla parametru **Sprawdzanie limitu kredytu dla zamówienia sprzedaży**, który znajduje się w formularzu Parametry kredytu i windykacji.
- Jeśli parametr ma wartość Nie, reguła wykorzystanego limitu kredytu nie zostanie uruchomiona.
- Jeśli parametr ma wartość Tak, a **Komunikat przy przekroczeniu limitu kredytu** jest ustawiany na ostrzeżenie, po przekroczeniu limitu kredytu zostanie wyświetlone ostrzeżenie. W celu sprawdzenia, czy istnieją reguły, które mają być uruchamiane, zostaną uruchomione reguły **Wykorzystany limit kredytu**. Jednak w tym scenariuszu zazwyczaj nie są dodawane żadne reguły.
- Jeśli parametr ma wartość Tak, a **Komunikat przy przekroczeniu limitu kredytu** jest ustawiany jako błąd, limit kredytu zostanie sprawdzony i zamówienie zostanie wstrzymane w przypadku przekroczenia limitu kredytu. Dodatkowo w celu sprawdzenia, czy istnieją dodatkowe reguły, które mają być uruchamiane, zostaną uruchomione reguły **Wykorzystany limit kredytu**. Komunikat o błędzie nie zostanie wyświetlony, ale zostanie wyświetlona przyczyna **Przekroczono limit kredytu**. 

## <a name="settings-that-will-change-the-way-an-order-is-placed-on-hold"></a>Ustawienia, które zmienią sposób wstrzymania zamówienia

Zamówienia można wykluczyć z zarządzania kredytami, nawet jeśli istnieją reguły. 

- W przypadku zmiany ustawień **Wykluczenie odbiorcy z zarządzania kredytem** w **Wszyscy odbiorcy > wybierz odbiorcę > skrócona karta Kredyt i windykacje** i ma wartość **Tak**, nie będą przetwarzane żadne zamówienia dla tego odbiorcy
- Jeśli zmienisz wartość **Wyklucz z funkcji zarządzania kredytami** w **nagłówku zamówień sprzedaży** na **skróconej karcie zarządzanie kredytami** na wartość **Tak**, reguły zarządzania kredytami nie zostaną przetworzone. To ustawienie może wykonać tylko pracownik lub menedżer kredytów kredytowych.

## <a name="processing-orders-on-hold-using-the-credit-management-hold-list"></a>Zamówienia przetwarzania wstrzymane przy użyciu listy wstrzymania zarządzania kredytami

Menedżerowie kredytów na liście wstrzymania zarządzania kredytami wyświetlają wszystkie zamówienia sprzedaży, które zostały wstrzymane i umożliwiają ich usunięcie w przypadku złagodzenia problemów z kredytem. Na stronie **Lista wstrzymań zarządzania kredytem** są wyświetlane wszystkie zamówienia sprzedaży, które zostały wstrzymane. Listę blokad można wyświetlić na stronie **Wszystkie wstrzymania kredytu** (**Zarządzanie kredytami > Lista wstrzymań zarządzania kredytem > Wszystkie blokady kredytowe**).
Zamówienia sprzedaży ze wszystkich firm są wysyłane do tej samej listy wstrzymań zarządzania kredytami, co zapewnia scentralizowany widok wszystkich transakcji wymagających uwagi. Użytkownicy zobaczą tylko informacje dla firm, do których ma uprawnienia dostępu.

Zamówienie sprzedaży można umieścić na liście blokad z następujących przyczyn:
1. Odbiorca ma fakturę, która jest zaległa przez określoną liczbę dni. 
2. Zamówienie ma określony stan konta.
3. Zamówienie ma określone warunki płatności.
4. Odbiorca ma wygasły limit kredytu.
5. Odbiorca ma zaległą kwotę i użyła określonego procentu limitu kredytowego
6. Zamówienie sprzedaży przekracza określoną kwotę.
7. Odbiorca przekroczył określony procent swojego limitu kredytowego.
8. Warunki płatności różnią się od domyślnych warunków płatności dla odbiorcy.
9. Rabaty rozliczenia różnią się od domyślnego rabatu rozliczanego dla odbiorcy.

Przyczyna blokowania jest wyświetlana dla każdego zamówienia sprzedaży z listy blokad. Jeśli istnieje więcej niż jedna przyczyna wstrzymania, przyczyna zostanie wyświetlona jako **Wielokrotność**. Menu **Przyczyny blokowania** w okienku akcji służy do wyświetlania wszystkich przyczyn wstrzymania zamówienia sprzedaży. Istnieje również możliwość wyświetlenia **przyczyn blokowania** w polu informacji.

### <a name="releasing-orders-from-the-hold-list-for-processing"></a>Zwalnianie zamówień z listy blokad na potrzeby przetwarzania

Po ponownym wyszukiwaniu przyczyn wstrzymania i ograniczeniu ich przyczyny można zwolnić zamówienia sprzedaży do dalszego przetwarzania.

1) Wybierz wiersz na liście wstrzymań. Można zwolnić wiele zamówień, wybierając więcej niż jeden wiersz.
2) Umożliwia wybranie **Przyczyny zwolnienia** zamówienia, które zostało wybrane do zwolnienia.  
3) Wpisz **Data przeglądu** dla każdego zamówienia, które zostało wybrane do zwolnienia.  
4) Wybierz menu **Zwolnij** w okienku akcji, aby zwolnić zamówienie. To menu będzie dostępne tylko po wybraniu transakcji. Użytkownik ma dwie opcje:
   - Wybierz opcję **przy księgowaniu**, aby usunąć wstrzymanie i zaksięgowanie dokumentu przy użyciu tego samego procesu księgowania, który był używany, gdy został on wstrzymany. Na przykład, jeśli potwierdzenie zamówienia sprzedaży zostało wstrzymane, potwierdzenie zamówienia sprzedaży zostanie zakończone po zwolnieniu. Zostanie wyświetlony formularz księgowania zamówienia sprzedaży, który pozwoli użytkownikowi na zaksięgowanie potwierdzenia.
   - Wybierz opcję **bez księgowania**, aby usunąć wstrzymanie bez wykonywania dalszego przetwarzania. Zamówienie sprzedaży można teraz ręcznie zaksięgować.

### <a name="rejecting-orders-in-the-hold-list"></a>Odrzucanie zamówień na liście blokad
Aby odrzucić zamówienie sprzedaży, można skorzystać z menu **Odrzuć** w okienku akcji
1. Wybierz wiersz na liście wstrzymań. Można zwolnić wiele zamówień, wybierając więcej niż jeden wiersz.
2. Zamówienie zostanie usunięte z listy blokad, a nagłówek zamówienia sprzedaży zostanie zaktualizowany w celu pokazania, że zamówienie zostało odrzucone.

### <a name="automatically-releasing-credit-management-holds"></a>Automatyczne zwalnianie blokad zarządzania kredytami
Zamówienia sprzedaży są umieszczane na liście blokad na podstawie reguł blokowania. Jednak niektóre przyczyny wstrzymania mogą ulec zmianie w czasie, jeśli zamówienie sprzedaży pozostanie na liście blokad przez pewien czas. Na przykład odbiorca może zapłacić swój rachunek, zwalniając swój limit kredytu. 

Można użyć menu **Ocena dla zwolnienia**, aby przejrzeć zamówienia sprzedaży na liście blokad i zwolnić je automatycznie, jeśli przyczyna wstrzymania została skorygowana.
1.  Wybierz menu **Ocena dla zwolnienia**
2.  Wybierz opcję **Reguły blokowania procesów**, aby przejrzeć wszystkie zamówienia sprzedaży. Wybierz **Reguły blokowania procesów dla wybranych wierszy**, aby przejrzeć tylko wybrane wiersze.
3. Zostanie wyświetlony suwak, dzięki czemu można wybrać jednego klienta. Pozostaw menu rozwijane dla odbiorcy puste dla wszystkich odbiorców. 
4. Po kliknięciu przycisku OK proces zostanie uruchomiony w tle i będzie można kontynuować pracę nad innymi zadaniami. W przypadku wybrania przetwarzania wsadowego przed kliknięciem przycisku OK proces zostanie uruchomiony w trybie wsadowym po kliknięciu przycisku OK. Przetwarzanie wstrzymanych zamówień na liście może zająć trochę czasu, więc w celu zaktualizowania stanu zamówień należy skorzystać z funkcji odświeżania. 
5.  Jeśli dla zamówienia nie ma już przyczyny blokowania, przyczyna blokowania zostanie uznana za nieprawidłową i po wyświetleniu przyczyn blokowania pojawi się znacznik wyboru widoczny obok przyczyny.
6.  Jeśli wszystkie przyczyny blokowania są wyczyszczone, nowy powód, **Gotowy do wydania**, zostanie dodany do listy przyczyn blokowania. Zamówienie sprzedaży można teraz automatycznie zwolnić.
7.  Jeśli parametr **Automatyczne zwolnienie** na karcie **Kredyt i windykacje > Konfiguracja > Parametry kredyt i windykacje > Kredyt > Automatyczne zwalnianie** jest ustawione **z księgowaniem**, zostanie wyświetlony monit o księgowaniu przy użyciu formularza księgowania zablokowanego dokumentu.
8.  Jeśli parametr **Automatyczne zwolnienie** na karcie **Kredyt i windykacje > Konfiguracja > Parametry kredyt i windykacje > Kredyt > Automatyczne zwalnianie** jest ustawione **bez księgowania**, wtedy należy księgować ręcznie.

### <a name="credit-management-approval-workflow"></a>Przepływ pracy zatwierdzania zarządzania kredytami

Można również tworzyć **Przepływy pracy zarządzania kredytami**, aby kontrolować zwalnianie blokad. Po skonfigurowaniu przepływu pracy za pomocą ustawienia **Zarządzanie kredytami > Ustawienia > Przepływy pracy zarządzania kredytami**, zamówienia oznaczone do zwolnienia lub odrzucenia będą wysyłane do przepływu pracy, w którym muszą zostać zatwierdzone jako pierwsze przed zwolnieniem lub odrzuceniem. 

Jeśli zostaną uwzględnione zadania zwolnienia z zaksięgowaniem lub zwolnieniem bez księgowania w przepływie pracy, zatwierdzenie przepływu pracy spowoduje również zwolnienie zamówienia sprzedaży. Jeśli jednak wystąpi błąd w procesie zwalniania z powodu braku informacji konfiguracyjnych lub innych przyczyn, należy odwołać zamówienie sprzedaży z przepływu pracy, usunąć problem powodujący awarię, a następnie ponownie przesłać zamówienie do przepływu pracy.

Jeśli nie zostaną uwzględnione zadania do wydania z zaksięgowaniem lub zwolnieniem bez księgowania w przepływie pracy, proces zatwierdzania przepływu pracy będzie po prostu umożliwiał ręczne zwolnienie zamówienia sprzedaży po zakończeniu zatwierdzania.

### <a name="forced-credit-hold"></a>Wymuszone wstrzymanie kredytu  
  
Czasami zamówienia sprzedaży mogą być blokowane nawet wtedy, gdy zamówienie nie spełnia kryteriów reguł blokowania. Na przykład menedżer kredytów może być powiadamiany o niezwiązanym z kredytowym rozwiązaniu z odbiorcą i zdecydować o ręcznym wprowadzaniu zamówień wstrzymanych natychmiast do momentu wyczyszczenia tego zagadnienia. Jeśli wystąpi taka sytuacja, można ręcznie wymusić wstrzymanie zamówienia sprzedaży.

1. Otwórz zamówienie sprzedaży, które chcesz wstrzymać.  
2. Wybierz opcję **Wymuszaj wstrzymanie kredytu** na karcie **Zarządzanie kredytami** w okienku akcji **Zarządzanie kredytami**.
3. Służy do wybrania **Przyczyny wymuszenia wstrzymania**.
4. Kliknij przycisk **OK**. Zamówienie sprzedaży zostanie zwrócone na listę wstrzymań zarządzania kredytem.

Można również wymusić wstrzymanie wielu zamówień przy użyciu strony **Zarzadzanie kredytem > Zadania okresowe > Wymuś wstrzymanie kredytu**. Na przykład można umieścić wszystkie zamówienia sprzedaży wstrzymane dla określonego odbiorcy.
1. Służy do wybrania **Przyczyny wymuszenia wstrzymania**. 
2. Kliknij **Rekordy do uwzględnienia**, aby wybrać zamówienia sprzedaży, które mają zostać wstrzymane. 
3. Należy kliknąć przycisk **OK**, aby przetworzyć wybrane zamówienia sprzedaży.

Zamówień sprzedaży, które zostały wstrzymane w procesie wymuszenia, nie można przetworzyć w przepływie pracy.

#### <a name="releasing-orders-that-were-added-to-the-credit-management-hold-list-with-a-forced-credit-hold"></a>Zwalnianie zamówień dodanych do listy wstrzymania zarządzania kredytami z wymuszonym wstrzymaniem kredytowym
Zamówienia sprzedaży o wymuszonej przyczynie wstrzymania nie mogą zostać zwolnione automatycznie. Jeśli zamówienie sprzedaży zostało wstrzymane i użyto procesu, który automatycznie zwalnia zamówienia sprzedaży, to zamówienie sprzedaży będzie wyświetlane jako **Gotowe do wydania** i pozostanie na liście blokad. Aby zwolnić zamówienie, należy skorzystać z menu **Zwolnij**.
 
## <a name="free-text-invoices-orders-and-project-invoice-support-in-credit-management"></a>Obsługa faktur niezależnych, zamówień i obsługi faktur projektu w zarządzaniu kredytami 
Zarządzanie kredytami może być używane obecnie tylko dla zamówień sprzedaży. Faktury niezależne, punkty zamówień sprzedaży i biura obsługi zamówień będą używały tymczasowych limitów kredytowych oraz ubezpieczeń/gwarancji dodawanych do korekty limitu kredytu. Nie będą one używały reguł blokowania i nie zostaną umieszczone na liście blokad, jeśli wystąpił problem z limitem kredytu.

Brak obsługi faktur projektu w zarządzaniu kredytami.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
