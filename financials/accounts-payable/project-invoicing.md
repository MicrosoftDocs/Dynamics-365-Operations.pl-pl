---
title: Fakturowanie projektu
description: "Ten artykuł zawiera omówienie zasad fakturowania projektów rozliczanych według czasu i materiałów oraz projektów o stałej cenie. Znajdują się tu informacje dotyczące propozycji faktur (faktur wstępnych), kontroli faktur, fakturowania akonto, wystawiania faktur przed dostawców i faktur korygujących."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: ProjInvoiceCashFlow, ProjInvoiceControl, ProjInvoiceListPage, ProjInvoiceProposalDetail, ProjInvoiceProposalListPage
audience: Application User, IT Pro
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 23111
ms.assetid: 1812d6f2-8b34-4258-8f5f-dcf12281547f
ms.search.region: Global
ms.author: kfend
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: a76abfa35e53673f9780d1a6f8816bd24f9f8e48
ms.openlocfilehash: f09aef9cf1e516b80f908c34b2b3c3397dde8a0f
ms.lasthandoff: 03/31/2017


---

# <a name="project-invoicing"></a>Fakturowanie projektu

[!include[banner](../includes/banner.md)]


Ten artykuł zawiera omówienie zasad fakturowania projektów rozliczanych według czasu i materiałów oraz projektów o stałej cenie. Znajdują się tu informacje dotyczące propozycji faktur (faktur wstępnych), kontroli faktur, fakturowania akonto, wystawiania faktur przed dostawców i faktur korygujących.

Typ projektu określa, która procedura fakturowania powinna zostać zastosowana. Tylko dwa typy projektów zewnętrznych, czas i materiały oraz o stałej cenie, mogą być fakturowane. Projekty typu czas i materiały oraz projekty o stałej cenie są zawsze dołączane do umowy dotyczącej projektu.

-   **Projekty o stałej cenie** – kwota faktury dla odbiorcy jest obliczona na podstawie planów płatności faktury. Fakturowanie jest wykonywane za pośrednictwem ustawień akonto, również używanych jako harmonogram fakturowania. Projekty o stałej cenie mogą być fakturowane według projektów lub według umów dotyczących projektu.
-   **Projekty typu czas i materiały** — kwota faktury dla odbiorcy oparta jest na wierszach transakcji wprowadzonych w projekcie. Transakcje w projektach typu czas i materiały mogą być fakturowane według projektów lub według umowy dotyczącej projektu.

Projekty typu czas i materiały oraz projekty o stałej cenie mogą być dołączane do projektów rozliczanych na trzy sposoby:

-   **Fakturowanie akonto** — projekty typu czas i materiały oraz projekty o stałej cenie mogą być fakturowane akonto. Dla tych dwóch typów projektów wymagane są odrębne typy konfiguracji akonto.
-   **Fakturowanie okresowe** — przy użyciu funkcji okresowych transakcje mogą być fakturowane w projektach. Funkcje okresowe umożliwiają przegląd transakcji, które muszą być zafakturowane.
-   **Przy użyciu faktur korygujących** — faktura korygująca może zostać utworzona zarówno dla projektów typu czas i materiały, jak i dla projektów o stałej cenie.

## <a name="invoice-proposals"></a>Propozycje faktur
Przed utworzeniem faktury odbiorcy dla projektu, można utworzyć fakturę wstępną lub propozycję faktury. W propozycji faktury można wybrać transakcje projektu, które zostaną uwzględnione na fakturze projektu. Można również przejrzeć szczegóły faktury przed zaksięgowaniem faktury projektu i wysłać ją do odbiorcy lub źródła finansowania.

### <a name="creating-invoice-proposals"></a>Tworzenie propozycji fakturowania

Propozycje faktur można utworzyć, wybierając opcję ręcznie z listy transakcji dla określonego projektu. Można również skonfigurować reguły fakturowania określające moment automatycznego tworzenia propozycji faktury. Na przykład można utworzyć regułę fakturowania służącą do tworzenia propozycji faktury po ukończeniu 25 procent, 75procent, 50 procent i 100 procent pracy nad projektem. 

Propozycje faktur mogą zostać utworzone dla następujących transakcji:

-   Godziny, wydatki i inne transakcje projektu
-   Kwoty, które zostały cofnięte przez odbiorców na poprzednich fakturach projektu
-   Faktury korygujące
-   Kwoty, które zostały zapłacone przez odbiorcę przed rozpoczęciem projektu

Można utworzyć w propozycji faktury transakcje opłat. Można także modyfikować ceny sprzedaży dla godzin, wydatków, towarów i transakcji opłat. Podczas księgowania propozycji faktury, zaktualizowane ceny i transakcje są dodawane do raportów projektu i historii transakcji. 

Aby utworzyć wiele faktur odbiorcy dla projektu, należy utworzyć propozycję faktury dla każdej faktury. Na przykład faktury można utworzyć na podstawie typu transakcji. Aby określić godziny na jednej fakturze dla odbiorcy, a na innej towary, należy utworzyć osobne propozycje faktur dla transakcji godzinowych i transakcji opłat. 

Jeśli projekt ma więcej niż jedno źródło finansowania, można utworzyć oddzielną propozycję faktury dla każdego źródła finansowania. Na stronie **reguły alokacji finansowania** można określić wartość procentową kwoty transakcji do alokacji dla każdego źródła finansowania, i źródło do księgowania różnic zaokrąglania.

### <a name="creating-customer-invoices-from-invoice-proposals"></a>Tworzenie faktur dla odbiorcy na podstawie propozycji faktur

Po utworzeniu i zaksięgowaniu propozycji faktury, faktura dla odbiorcy jest tworzona automatycznie dla transakcji, które są uwzględnione w propozycji faktury. 

Można dodawać lub usuwać transakcje w propozycji faktury przed jej zaksięgowaniem. Na przykład można usunąć transakcje wydatków, które zostały zaksięgowane w projekcie, ale nie są płatne przez odbiorcę. 

Jeśli organizacja wymaga, aby propozycje faktur były przeglądane przed zaksięgowaniem, może zaistnieć konieczność, aby propozycja faktury została zatwierdzona za pośrednictwem przepływu pracy „Przegląd propozycji faktur projektu” przed zaksięgowaniem.

## <a name="on-account-invoicing"></a>Fakturowanie akonto
Kwota wprowadzona do faktury akonto dla projektu opiera się na czasie, procencie ukończenia oraz innych warunkach fakturowania, określonych w umowie powiązanego projektu. Kwota jest nie obliczana na podstawie godzin, towarów, wydatków lub opłat, które zostały zaksięgowane do projektu. 

Należy najpierw utworzyć transakcję akonto dla projektu typu czas i materiały lub projektu o stałej cenie, aby można było dodać transakcję akonto do projektu faktury. Do transakcji akonto wprowadź kwotę, na jaką ma być wystawiona faktura dla odbiorcy. Aby utworzyć fakturę projektu dla kwoty, należy utworzyć fakturę wstępną lub propozycję faktury. W propozycji faktury wybierz transakcję akonto. Przed utworzeniem faktury projektu można przeglądać informacje dotyczące akonta w propozycji faktury.

### <a name="fixed-price-projects"></a>Projekty typu stała cena

Dla projektów o stałej cenie transakcje akonto są oparte na uzgodnionymi punkcie kontrolnym, jednostce dostawy lub uzgodnienia dotyczącego fakturowania uwarunkowane stanem realizacji umowy określonych w umowie projektu. Zostaje utworzony jeden wiersz dla każdej płatności, która ma być odebrana od odbiorcy projektu. Nie są wymagane żadne potrącenia.

### <a name="time-and-material-projects"></a>Projekty typu czas i materiał

Dla projektów typu czas i materiały można wystawić rachunek dla odbiorcy lub innego źródła finansowania dla kwoty przedpłaty za pomocą propozycji faktur akonto. Wprowadź transakcje akonto w jednym wierszu. Opcjonalnie można wprowadzić dodatkowe wiersze jako potrącenia, żeby skompensować wszelkie przedpłaty wprowadzone już przez odbiorcę. Aby utworzyć wiersze potrącenia, należy poprzedzić kwotę ze znakiem minus.

## <a name="invoice-control"></a>Kontrola faktury
Kontrola faktury służy do śledzenia zafakturowanych i niezafakturowanych transakcji oraz analizowania tych transakcji względem ofert w celu uzyskania kompleksowego oglądu projektu od etapu oferty do zakończenia. Możesz zobaczyć, za które transakcje zostały naliczone opłaty w określonym projekcie, i które wiersze zostały zafakturowane. Ponadto można wyświetlać pojedyncze transakcje, dzięki czemu można je skorygować po zaksięgowaniu.

## <a name="invoicing-fixed-price-projects"></a>Fakturowanie projektów o stałej cenie
Aby zafakturować projekt o stałej cenie, trzeba zdefiniować harmonogram fakturowania i wykonać procedurę fakturowania.

### <a name="billing-schedule"></a>Harmonogram fakturowania

Możesz zafakturować projekty o stałej cenie zgodnie z harmonogramem fakturowania. Harmonogram fakturowania jest zdefiniowany w kategoriach jednego lub więcej punktów kontrolnych projektu. Dla każdego punktu kontrolnego można zdefiniować określoną datę, waluty sprzedaży, ceny sprzedaży i działania. 

Na przykład można skonfigurować następujący harmonogram fakturowania:

-   20% po podpisaniu umowy dotyczącej projektu
-   30% po pierwszej dostawie
-   15% po drugiej dostawie
-   35% po ostatecznej dostawie

### <a name="invoicing-procedure"></a>Procedura fakturowania

Gdy płatności kamieni milowych są gotowe do zafakturowania, można zastosować tę procedurę do fakturowania kwot akonto.

## <a name="vendor-invoicing"></a>Dostawca wystawiający fakturę
Jeśli zamawiasz towar od dostawcy i przypisujesz ten towar do projektu, właściwość wiersza wybrana dla wiersza zamówienia zakupu dla tego towaru określa, czy za kupiony towar zostanie wystawiona faktura dla odbiorcy. Jeśli ustawisz domyślne właściwości wiersza, będą one wyświetlane dla towaru w wierszu zamówienia zakupu (Szczegóły wiersza &gt; Projekt &gt; Właściwość wiersza). Istnieją dwa sposoby modyfikowania właściwości wiersza:

-   Faktura dla odbiorcy projektu za towar: ustaw właściwość wiersza towaru jako wartość płatną w zamówieniu zakupu, a następnie wystaw fakturę dla odbiorcy używając odpowiedniej metody fakturowania.
-   Nie wystawiaj odbiorcy projektu faktury za towar: nie zaznaczaj właściwości wiersza **płatne** w wierszu zamówienia zakupu dla towaru. Następnie możesz zafakturować zamówienie zakupu i nie są wymagane dalsze akcje.

## <a name="credit-notes"></a>Faktury korygujące
Jeśli kwota na fakturze dla odbiorcy ma wartość ujemną, faktura zostanie zakwalifikowana jako faktura korygująca. Podczas drukowania dokumentu ma tytuł „Faktura korygująca". 

Tworząc fakturę korygującą w celu skorygowania wcześniej zafakturowanej kwoty, najpierw należy wybrać zafakturowaną kwotę, która zostanie zaksięgowana po stronie kredytowej. Następnie należy utworzyć fakturę korygującą, postępując zgodnie z tą samą procedurą, która służy do utworzenia zwykłej faktury dla odbiorcy. Trzeba wybrać transakcje wcześniej księgowane na fakturze dla odbiorcy, a następnie utworzyć i zaksięgować propozycję faktury korygującej. 

W tym samym dokumencie mogą się znaleźć transakcje wybrane do księgowania po stronie kredytowej, transakcje kredytowe i transakcje, które zostały zaksięgowane. Dokument jest klasyfikowany jako faktura lub faktura korygująca na podstawie tego, czy łączna kwota ma wartość dodatnią, czy ujemną. 

Tworząc fakturę korygującą w celu skorygowania wcześniej zafakturowanej kwoty, najpierw należy wybrać zafakturowaną kwotę, która zostanie zaksięgowana po stronie kredytowej. Należy utworzyć fakturę korygującą, postępując zgodnie z tą samą procedurą, która służy do utworzenia zwykłej faktury dla odbiorcy. 

Można utworzyć fakturę z kwotą ujemną i taka faktura jest klasyfikowana jako faktura korygująca. Aby utworzyć i wydrukować fakturę korygującą, trzeba wybrać transakcje wcześniej księgowane na fakturze dla odbiorcy, a następnie edytować transakcje. Z wyjątkiem firm, których adres podstawowy znajduje się w Niemczech, tytuł takiej faktury brzmi Faktura korygująca.




