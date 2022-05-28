---
title: Dlaczego nie mogę cofnąć tej transakcji?
description: W tym temacie opisano różne powody, dla których nie można cofnąć transakcji. Zawiera również listę rozwiązań tego problemu.
author: kweekley
ms.date: 07/21/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2021-07-21
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: e18caf1dbdf8191713c17b1793f5da44cf2f182b
ms.sourcegitcommit: 631d2cea52590af15f208e9af584446e85540fcf
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/07/2022
ms.locfileid: "8724537"
---
# <a name="why-cant-i-reverse-this-transaction"></a>Dlaczego nie mogę cofnąć tej transakcji?

[!include [banner](../includes/banner.md)]

W tym temacie opisano różne powody, dla których nie można cofnąć transakcji. Zawiera również listę rozwiązań tego problemu.

## <a name="symptom"></a>Objaw

Organizacje mogą napotkać sytuacje, w których muszą wycofać zaksięgowaną transakcję. Od czasu do czasu system uniemożliwi im odwrócenie tych transakcji. To zachowanie może spowodować powstanie dwóch pytań:

- Dlaczego nie mogę cofnąć tej transakcji?
- Jak funkcja masowego wycofania wpływa na to zachowanie?

## <a name="resolution"></a>Rozwiązanie

Transakcje muszą spełniać określone kryteria, zanim będą mogły zostać wycofane. Pozostałe sekcje tego tematu zapewniają sprawdzanie poprawności dla każdego modułu. Chociaż ten temat koncentruje się na transakcjach w Microsoft Dynamics 365 Finance, niektóre pojęcia i sprawdzanie poprawności można zastosować do innych aplikacji, takich jak Dynamics 365 Supply Chain Management.

Ponadto miejsce, w którym transakcja jest wycofywana może mieć wpływ na to, czy można ją wycofać. Na przykład płatność dostawcy, która jest księgowana jako czek, może zostać wycofana tylko z sekcji **Czek** na stronie transakcji dla kont bankowych. Nie można wycofać ze strony **Transakcje voucherów** w księdze głównej.

Jeśli funkcja **Masowego wycofania wielu dokumentów** (znana również jako masowego wycofania) jest włączona w obszarze roboczym **Zarządzanie funkcjami**, wpływa ona na liczbę transakcji, które można cofnąć i gdzie można je cofnąć. Ta funkcja zapewnia dwie korzyści po włączeniu:

- W przypadku niektórych typów transakcji można wybrać i wycofać więcej niż jedną transakcję naraz z arkusza, w którym została zaksięgowana, lub ze strony **Transakcje załączników**. Jednak poszczególne transakcje muszą być odwracalne, zanim funkcja została włączona. Przed wprowadzeniem tej funkcji transakcje musiały być cofane po jednym na raz.
- *Niektóre* transakcje księgi podrzędnej można wycofać z poziomu arkusza (dziennika głównego) lub strony **Transakcje załącznika**. Nie trzeba ich odwracać ze strony księgi podrzędnej. Na przykład arkusz faktury od dostawcy można wcześniej wycofać tylko ze strony **Transakcje dostawcy**. Jednak teraz można go odwrócić również ze strony Księga główna, z arkusza lub strony **Transakcje załącznika**. Każda sekcja tego tematu wyjaśnia typy transakcji, które nie mają zastosowania do tej korzyści.

Funkcja wycofywania masowego **nie** umożliwia wycofywania większej liczby typów transakcji. Jeśli nie można wcześniej cofnąć typu transakcji, po włączeniu funkcji nadal nie można go cofnąć. Na przykład faktury od dostawcy zamówienia zakupu nie można cofnąć, niezależnie od tego, czy funkcja wycofywania masy jest włączona.

Aby uzyskać więcej informacji na temat funkcji wycofywania masowego, zobacz [Wycofywanie księgowania arkusza](reverse-journal-posting.md).

## <a name="general-ledger"></a>Księga główna

Korekty księgi głównej są wprowadzane tylko przy użyciu kont księgowych. W związku z tym aktualizują tylko księgę główną.

Jeśli funkcja wycofywania masowego jest wyłączona, większość korekt księgi głównej można wycofać indywidualnie ze strony **Transakcje dla \<main account\>** dla księgi (**LedgerTransAccount**). (Dokładny tytuł strony różni się w zależności od wybranego konta głównego). Strona pokazuje każdą transakcję zaksięgowaną na koncie głównym. Zazwyczaj jest otwierany ze strony **listy bilansu próbnego** lub przez wybranie opcji **Transakcje** na stronie **Transakcje załącznika**.

Jeśli funkcja wycofywania masowego jest włączona, jeden lub więcej załączników księgi głównej można teraz wycofać ze strony **Transakcje załączników** i z arkusza, w których zaksięgowano transakcję. Wyjątkiem są przeszacowania w walucie obcej księgi głównej, konsolidacja i transakcje zamknięcia na koniec roku. Te transakcje są wycofywane ze stron, na których zostało uruchomione zamknięcie na koniec roku.

### <a name="reasons-why-transactions-cant-be-reversed"></a>Powody, dla których nie można cofnąć transakcji

Nie można cofnąć transakcji z następujących powodów:

- Arkusze finansowe:

    - Okres obrachunkowy jest zawieszony lub trwale zamknięty:

        - Jeśli data wycofania znajduje się w okresie obrachunkowym, który nie jest otwarty, nie można cofnąć transakcji.
        - Jeśli transakcja obsługuje wpis daty cofania, transakcja nadal może zostać wycofana, zmieniając datę wycofania na okres otwarty.

    - Proces zamknięcia na koniec roku został uruchomiony:

        - Data księgowania transakcji jest w roku obrachunkowym, który został zamknięty na koniec roku. Chociaż okres w roku obrachunkowym może być nadal otwarty, nie można cofnąć transakcji, jeśli proces zamknięcia na koniec roku został uruchomiony dla roku obrachunkowego. Rok obrachunkowy ma inny stan niż okresy w nim.
        - Zamknięcie na koniec roku można cofnąć, a następnie można wycofać transakcję. Takie podejście może nie być rozwiązaniem. Może być łatwiejsze do ręcznego wprowadzenia transakcji cofania w okresie otwartym zamkniętego roku obrachunkowego lub następnego roku obrachunkowego, w zależności od stanu procesu zamknięcia fiskalnego. Jeśli nowa transakcja jest księgowana w otwartym okresie roku obrachunkowego, który został przez proces zamknięcia na koniec roku, zamknięcie na koniec roku musi zostać ponownie uruchomione.

    - Cofnięcie transakcji jest już w toku:

        - Jeśli transakcja jest w trakcie wycofywania, proces ten musi zostać zakończony. Nie można wykonać oddzielnego procesu wycofywania. 
        - Po zakończeniu wycofywania, wycofana transakcja może zostać wycofana ponownie (oznacza to, że wycofanie może zostać wycofane).

    - Rozliczenie księgi:

        - Jeśli jeden lub więcej wierszy transakcji zostało rozliczone za pomocą zadania okresowego **rozliczenia księgi** (**Księga główna\> Zadania okresowe \> Rozliczenia księgi**), tak aby rekord istniał w tabeli LedgerTransSettlement, nie można cofnąć transakcji.
        - Rozliczenie księgi można cofnąć, a następnie można wycofać załącznik.

    - Międzyfirmowe:

        - Jeśli transakcja jest transakcją międzyfirmową, nie można jej cofnąć.
        - Transakcja **nie** jest transakcją międzyfirmową, ale jest księgowana na koncie głównym „ze względu” lub „należne od”, które zostało zdefiniowane na stronie **konfiguracji międzyfirmowej**.

    - Naliczenia:

        - Jeśli naliczony załącznik księgi głównej zostanie wycofany, naliczony zapis i wszystkie odpowiadające im podtransakcyjne naliczania zostaną wycofane.
        - Nie można cofnąć poszczególnych naliczonych transakcji podrzędnych.

- Arkusz rozpoznawania przychodów:

    - Nie można cofnąć transakcji rozpoznania przychodu.
    - Gdy przychód jest rozpoznawany za pomocą arkusza rozpoznawania przychodów, załącznik jest księgowany tylko na kontach księgowych. W związku z tym na stronach takich jak **transakcje załącznika** transakcje są wyświetlane tak, jakby były tylko zapisami księgi głównej.

- Przeszacowanie w walucie obcej:

    - Transakcje przeszacowania w walucie obcej można wycofać, ale tylko ze strony **Przeszacowania waluty obcej** księgi głównej, z których uruchomiono przeszacowanie.
    - Cofnięcie można wykonać tylko wtedy, gdy jest księgowane w otwartym okresie obrachunkowym.

- Konsolidacja:

    - Transakcje konsolidacji można wycofać, ale tylko ze strony **Transakcje konsolidacyjne**.
    - Cofnięcie można wykonać tylko wtedy, gdy jest księgowane w otwartym okresie obrachunkowym.

- Zamknięcie roku:

    - Transakcje zamknięcia na koniec roku (zarówno transakcje zamknięcia, jak i otwarcia) można cofnąć w ten sposób:

        - Jeśli funkcja ulepszeń zamknięcia na koniec roku księgi głównej jest wyłączona, wybierz opcję **Cofnij poprzednie zamknięcie** w oknie dialogowym **Zamknięcie na koniec roku**.
        - Jeśli funkcja ulepszeń na koniec roku księgi głównej jest włączona, wybierz rekordy firmy i roku obrachunkowego utworzone dla zamknięcia na koniec roku na stronie **Zamknięcie roku**, a następnie wybierz pozycję **Odwróć zamknięcie roku**.

    - Należy zauważyć, że odwrócenie zamknięcia na koniec roku faktycznie usuwa zamknięcia i otwarcia transakcji. Załącznik cofania nigdy nie jest księgowany.

## <a name="accounts-payable"></a>Rozrachunki z dostawcami

Wiele typów transakcji aktualizuje księgę pomocniczą Zobowiązania. Przykłady obejmują faktury od dostawcy, arkusze faktur od dostawcy i raporty z wydatków.

Jeśli funkcja wycofywania masy jest wyłączona, transakcje można wycofać indywidualnie ze strony **Transakcje dostawcy** dla faktur lub strony **Konto bankowe** dla płatności czekowych.

Jeśli funkcja masowego odwracania jest włączona, jedna lub więcej transakcji płatniczych może być również odwrócona ze strony **Transakcje bonowe** oraz z dziennika, z którego transakcje zostały zaksięgowane. Jednak płatności dostawcy nadal można wycofać tylko z konta bankowego. Ponadto transakcji dostawcy nie można wycofać ze strony księgi **Transakcje dla \<main account\>**. Można je wycofać tylko ze strony **Transakcje załącznika**.

Należy pamiętać, że niektórych transakcji nie można w ogóle cofnąć. Przykłady obejmują faktury od dostawcy zamówienia zakupu i płatności dostawcy elektronicznego.

### <a name="reasons-why-vouchers-cant-be-reversed"></a>Powody, dla których nie można cofnąć załączników

Nie można cofnąć załączników z następujących powodów:

- Okres obrachunkowy jest zawieszony lub zamknięty:

    - Jeśli data wycofania znajduje się w okresie obrachunkowym, który nie jest otwarty, nie można cofnąć transakcji.
    - Jeśli transakcja obsługuje wpis daty cofania, transakcja nadal może zostać wycofana, zmieniając datę wycofania na okres otwarty.

- Proces zamknięcia księgi głównej na koniec roku został uruchomiony:

    - Data księgowania transakcji jest w roku obrachunkowym, który został zamknięty w księdze głównej. Chociaż okres w roku obrachunkowym może być nadal otwarty, nie można cofnąć transakcji, jeśli proces zamknięcia na koniec roku został uruchomiony dla roku obrachunkowego. Rok obrachunkowy ma inny stan niż okresy w nim.
    - Zamknięcie na koniec roku można cofnąć, a następnie można wycofać transakcję. Takie podejście może nie być rozwiązaniem. Może być łatwiejsze do ręcznego wprowadzenia transakcji cofania w okresie otwartym zamkniętego roku obrachunkowego lub następnego roku obrachunkowego, w zależności od stanu procesu zamknięcia fiskalnego. Jeśli nowa transakcja jest księgowana w otwartym okresie roku obrachunkowego, który został przez proces zamknięcia na koniec roku, zamknięcie na koniec roku musi zostać ponownie uruchomione.

- Zapis księgi podrzędnej nie został przeniesiony do księgi głównej:

    - Ta przyczyna dotyczy tylko faktur od dostawcy zamówienia niezwiązanego z zakupem.
    - Użyj **zapisów dziennika księgi podrzędnej, które nie zostały jeszcze przeniesione**, aby przenieść zapis do księgi głównej. Następnie fakturę od dostawcy zamówienia niezwiązanego z zakupem można wycofać ze strony **Transakcje dostawcy**.

- Rozliczenie:

    - Transakcja (np. faktura lub płatność) jest rozliczana lub oznaczana do rozliczenia.

        - Można sprawdzić, czy transakcja została rozliczona lub oznaczona do rozliczenia, wybierając pozycję **Wyświetl rozliczenia** lub **Rozliczenia \> Historie rozliczenia** na stronie **Transakcje dostawcy**.
        - Rozliczenie można również wycofać ze strony **Transakcje dostawcy** (**Rozliczenie \>Cofnij rozliczenie**), jeśli jedna z transakcji musi zostać wycofana.

- Załącznik zawiera więcej niż jedną transakcję podnajmowanej, która została wprowadzona przy użyciu tego samego numeru załącznika (jeden rozchodzaj załącznika).
- Faktura nie została zatwierdzona:

    - Jeśli pole wyboru **Zatwierdzenie** nie jest zaznaczone na fakturze, nie można cofnąć faktury.

        - W takim przypadku zatwierdzanie nie odwołuje się do zatwierdzeń w procesie przepływu pracy, ale do opcji **Zatwierdzanie** na fakturze. Ta opcja jest używana, aby zapobiec płaceniu faktury. Jest ona zazwyczaj używana dla faktur rejestru faktur od dostawcy.

- Transakcja znajduje się w puli faktur:

    - Faktury w puli nie można wycofać bezpośrednio ze strony **Transakcje dostawcy**. Zamiast tego musi zostać wycofana przez proces anulowania na stronie **arkusz zatwierdzania faktur**.

- Transakcja ma fakturę nadrzędną, która została poprawiona (lokalizacja indyjska).
- Transakcja ma stan promesy **faktura umorzona**.
- Transakcja jest używana do częściowego rozliczenia podatku.
- Transakcja zawiera konto dostawcy, ale jest wycofywana z niepoprawnej strony, takiej jak strona **Transakcje dla \<main account\>**:

    - Jak sugeruje ten powód, nawet po włączeniu funkcji odwrócenia masowego niektóre transakcje księgo podrzędnej można odwrócić tylko z określonych stron.

### <a name="types-of-transactions-that-cant-be-reversed"></a>Typy transakcji, których nie można cofnąć

Nie można cofnąć następujących typów transakcji:

- Przeszacowanie w walucie obcej:

    - W odróżnieniu od przeszacowania walutowego księgi głównej, przeszacowania walutowego należności i zobowiązań nie można odwrócić. Zamiast tego przeszacowania musi być uruchamiane ponownie przy użyciu daty faktury. W takim przypadku przeszacowanie używa kursu wymiany od daty faktury i zasadniczo podaje niezrealizowany zysk lub stratę do 0 (zero). W związku z tym wynik przypomina wynik odwrócenia poprzedniego przeszacowania. Należy jednak pamiętać, że ta sama kwota nie zostanie wycofana, jeśli domyślny kurs wymiany został zmieniony na fakturze.

- Zamówienie zakupu Faktura sprzedawcy:

    - Nota kredytowa musi zostać utworzona w celu odwrócenia faktury sprzedawcy. Aby uzyskać więcej informacji na temat tworzenia transakcji cofania, zobacz [Tworzenie zamówienia zwrotu zakupu](../../supply-chain/procurement/tasks/create-purchase-return-order.md).

- Skrypt dłużny
- Akredytywa bankowa przesyłka eksportowa

## <a name="accounts-receivable"></a>Rozrachunki z odbiorcami

Kilka typów transakcji aktualizuje księgi pomocnicze należności. Przykłady obejmują faktury dla odbiorców z zamówień sprzedaży, faktury dla odbiorców, które są wprowadzane za pośrednictwem dziennika głównego, faktury niezależne, płatności odbiorcy i odpisy.

Jeśli funkcja wycofywania masy jest wyłączona, transakcje można wycofać indywidualnie ze strony **Transakcje klienta** dla faktur lub strony **Konta bankowe** dla depozytów. Aby uzyskać informacje na temat wycofywania płatności, zobacz sekcję [Zarządzanie gotówką i bankami](cant-reverse-transctns.md#cash-and-bank-management) w dalszej części tego tematu.

Jeśli funkcja masowego odwracania jest włączona, jedna lub więcej transakcji z tytuły należności może być również odwrócona ze strony **Transakcje bonowe** oraz z dziennika, z którego transakcje zostały zaksięgowane. Jednak depozyty nadal mogą być wycofywane tylko z konta bankowego, a faktury niezależne mogą być wycofywane tylko ze strony źródłowej (jeśli funkcja umożliwiająca korekty jest włączona). Ponadto transakcje klienta można wycofać ze strony księgi **Transakcje dla \<main account\>**. Można je jednak wycofać ze strony **Transakcje załącznika**.

Należy pamiętać, że niektórych transakcji nie można w ogóle cofnąć. Przykłady obejmują faktury dla odbiorców zamówień sprzedaży i odpisy.

### <a name="reasons-why-transactions-cant-be-reversed"></a>Powody, dla których nie można cofnąć transakcji

Nie można cofnąć transakcji z następujących powodów:

- Okres obrachunkowy jest zawieszony lub trwale zamknięty:

    - Jeśli data wycofania znajduje się w okresie obrachunkowym, który nie jest otwarty, nie można cofnąć transakcji.
    - Jeśli transakcja obsługuje wpis daty cofania, transakcja nadal może zostać wycofana, zmieniając datę wycofania na okres otwarty.

- Proces zamknięcia księgi głównej na koniec roku został uruchomiony:

    - Data księgowania transakcji jest w roku obrachunkowym, który został zamknięty w księdze głównej na koniec roku. Chociaż okres w roku obrachunkowym może być nadal otwarty, nie można cofnąć transakcji, jeśli proces zamknięcia na koniec roku został uruchomiony dla roku obrachunkowego. Rok obrachunkowy ma inny stan niż okresy w nim.
    - Zamknięcie na koniec roku można cofnąć, a następnie można wycofać transakcję. Takie podejście może nie być rozwiązaniem. Może być łatwiejsze do ręcznego wprowadzenia transakcji cofania w okresie otwartym zamkniętego roku obrachunkowego lub następnego roku obrachunkowego, w zależności od stanu procesu zamknięcia fiskalnego. Jeśli nowa transakcja jest księgowana w otwartym okresie roku obrachunkowego, który został przez proces zamknięcia na koniec roku, zamknięcie na koniec roku musi zostać ponownie uruchomione.

- Zapis księgi podrzędnej nie został przeniesiony do księgi głównej:

    - Z tego powodu stosuje się to tylko do faktur niezależnych.
    - Użyj **zapisów dziennika księgi podrzędnej, które nie zostały jeszcze przeniesione**, aby przenieść zapis do księgi głównej. Fakturę niezależną można następnie cofnąć lub poprawić, jeśli funkcja poprawek jest włączona.

- Rozliczenie:

    - Transakcja (np. faktura lub płatność) jest rozliczana lub oznaczana do rozliczenia.

        - Można sprawdzić, czy transakcja została rozliczona lub oznaczona do rozliczenia, wybierając pozycję **Wyświetl rozliczenia** lub **Rozliczenia \> Historie rozliczenia** na stronie **Transakcje klienta**.
        - Rozliczenie można również wycofać ze strony **Transakcje klienta** (**Rozliczenie \>Cofnij rozliczenie**), jeśli jedna z transakcji musi zostać wycofana.

- Transakcja zawiera więcej niż jedną transakcję podnajmowanej, która została wprowadzona przy użyciu tego samego numeru załącznika (jeden rodzaj załącznika).
- Faktura nie została zatwierdzona:

    - Jeśli pole wyboru **Zatwierdzenie** nie jest zaznaczone na fakturze, nie można cofnąć faktury.

        - W takim przypadku zatwierdzanie nie odwołuje się do zatwierdzeń w procesie przepływu pracy, ale do opcji **Zatwierdzanie** w wierszach załącznika. Ta opcja jest używana, aby zapobiec płaceniu faktury. Chociaż ta opcja jest zwykle używana w rozrachunków z dostawcami, jest również dostępna dla faktur rozrachunków z odbiorcami, które są wprowadzane za pośrednictwem arkuszy.

- Transakcja ma fakturę nadrzędną, która została poprawiona (lokalizacja indyjska).
- Transakcja zawiera konto klienta, ale jest wycofywana z niepoprawnej strony, takiej jak strona **Transakcje dla \<main account\>**:

    - Jak sugeruje ten powód, nawet po włączeniu funkcji odwrócenia masowego niektóre transakcje księgo podrzędnej można odwrócić tylko z określonych stron.

### <a name="types-of-transactions-that-cant-be-reversed"></a>Typy transakcji, których nie można cofnąć

Nie można cofnąć następujących typów transakcji:

- Przeszacowanie w walucie obcej:

    - W odróżnieniu od przeszacowania walutowego księgi głównej, przeszacowania walutowego należności i zobowiązań nie można odwrócić. Zamiast tego przeszacowania musi być uruchamiane ponownie przy użyciu daty faktury. W takim przypadku przeszacowanie używa kursu wymiany od daty faktury i zasadniczo podaje niezrealizowany zysk lub stratę do 0 (zero). W związku z tym wynik przypomina wynik odwrócenia poprzedniego przeszacowania. Należy jednak pamiętać, że ta sama kwota nie zostanie wycofana, jeśli domyślny kurs wymiany został zmieniony na fakturze.

- Transakcja, która skorygowała potrąconą zaliczkę na podatek
- Zamówienie sprzedaży — faktura klienta:

    - Nota kredytowa lub zwrotna musi zostać utworzona w celu odwrócenia transakcji. Aby uzyskać więcej informacji na temat odwracania transakcji, zobacz temat [Zwroty sprzedaży](../../supply-chain/warehousing/sales-returns.md).

- Weksel
- Transakcja kasowa
- Zaawansowana korekta
- Nota odsetkowa
- List z ponagleniem
- Akredytywa bankowa
- Wysyłka eksportowa
- Arkusz rozpoznawania przychodów:

    - Gdy przychód jest rozpoznawany za pomocą arkusza rozpoznawania przychodów, załącznik jest księgowany tylko na kontach księgowych. W związku z tym są one wyświetlane tak, jakby były tylko zapisami księgi głównej. Tych wpisów nie można cofnąć, ponieważ harmonogram przychodów nie zostanie ponownie otwarty, aby ponownie rozpoznać przychód.

## <a name="cash-and-bank-management"></a>Zarządzanie gotówką i bankami

Kilka typów transakcji aktualizuje księgę podrzędną banku za pośrednictwem dziennika głównego. Przykłady obejmują płatności dostawcy, płatności odbiorcy i przelewy bankowe.

Jeśli funkcja wycofywania masy jest wyłączona, transakcje można wycofać indywidualnie ze strony **Konta bankowe** dla czeków i depozytów lub strony **Transakcje klienta** dla płatności klienta.

Jeśli funkcja masowego odwracania jest włączona, jedna lub więcej transakcji płatniczych może być również odwrócona ze strony **Transakcje załącznikowe** oraz z dziennika, z którego transakcje zostały zaksięgowane. Jednak depozyty nadal można wycofać tylko z konta bankowego. Ponadto transakcje bankowe można wycofać ze strony księgi **Transakcje dla \<main account\>**. Można je jednak wycofać ze strony **Transakcje załącznika**.

Należy pamiętać, że niektórych transakcji nie można w ogóle cofnąć. Przykłady obejmują płatności dostawcy elektronicznego.

### <a name="reasons-why-transactions-cant-be-reversed"></a>Powody, dla których nie można cofnąć transakcji

Nie można cofnąć transakcji z następujących powodów:

- Okres obrachunkowy jest zawieszony lub trwale zamknięty:

    - Jeśli data wycofania znajduje się w okresie obrachunkowym, który nie jest otwarty, nie można cofnąć transakcji.
    - Jeśli transakcja obsługuje wpis daty cofania, transakcja nadal może zostać wycofana, zmieniając datę wycofania na okres otwarty.

- Proces zamknięcia księgi głównej na koniec roku został uruchomiony:

    - Data księgowania transakcji jest w roku obrachunkowym, który został zamknięty w księdze głównej na koniec roku. Chociaż okres w roku obrachunkowym może być nadal otwarty, nie można cofnąć transakcji, jeśli proces zamknięcia na koniec roku został uruchomiony dla roku obrachunkowego. Rok obrachunkowy ma inny stan niż okresy w nim.
    - Zamknięcie na koniec roku można cofnąć, a następnie można wycofać transakcję. Takie podejście może nie być rozwiązaniem. Może być łatwiejsze do ręcznego wprowadzenia transakcji cofania w okresie otwartym zamkniętego roku obrachunkowego lub następnego roku obrachunkowego, w zależności od stanu procesu zamknięcia fiskalnego. Jeśli nowa transakcja jest księgowana w otwartym okresie roku obrachunkowego, który został przez proces zamknięcia na koniec roku, zamknięcie na koniec roku musi zostać ponownie uruchomione.

- Rozliczenie:

    - Transakcja (faktura) jest rozliczana lub oznaczana do rozliczenia.

        - Można sprawdzić, czy transakcja została rozliczona lub oznaczona do rozliczenia, wybierając pozycję **Wyświetl rozliczenia** lub **Rozliczenia \> Historie rozliczenia** na stronie **Transakcje dostawcy** lub **Transakcje klienta**.
        - Rozliczenie można również wycofać ze strony **Transakcje dostawcy** lub **transakcje klienta**(**Rozliczenie \> Cofnij rozliczenie**), jeśli jedna z transakcji musi zostać wycofana.

- Transakcja zawiera więcej niż jedną transakcję podnajmowanej, która została wprowadzona przy użyciu tego samego numeru załącznika (jeden rodzaj załącznika).
- Transakcje pomostowe:

    - Jeśli transakcja jest powiązana z płatnością pomostową, nie można jej cofnąć.
    - Jeśli płatność pomostowa musi zostać wycofana, płatność musi zostać najpierw rozliczona z konta pomostowego do banku. Następnie płatność może zostać wycofana, pod warunkiem że spełnia ona inne kryteria walidacji.

- Transakcja zawiera konto bankowe, ale jest wycofywana ze strony **Transakcje dla \<main account\>** lub z niepoprawnej księgi podrzędnej, takiej jak Należności lub zobowiązania:

    - Jak sugeruje ten powód, nawet po włączeniu funkcji odwrócenia masowego niektóre transakcje księgo podrzędnej można odwrócić tylko z określonych stron.

- Bank — przeszacowanie w walucie obcej:

    - Przeszacowanie w walucie obcej banku można cofnąć. Jednak odwrócenie może być uniemożliwione, jeśli zakończysz kroki odwrócenia w nieodpowiedniej kolejności. Na przykład jeśli przeszacowanie zostanie dokonane w marcu i kwietniu, przeszacowania marca nie można cofnąć, dopóki przeszacowanie z kwietnia nie zostanie wycofane.

### <a name="types-of-transactions-that-cant-be-reversed"></a>Typy transakcji, których nie można cofnąć

Nie można cofnąć następujących typów transakcji:

- Płatności dostawcy, które zostały dokonane jako elektroniczne przelewy pieniężne (EFT)
- Skrypty dłużne
- Weksle

## <a name="fixed-assets"></a>Środki trwałe

Kilka typów transakcji aktualizuje tylko księgę podrzędną środków trwałych. Przykłady obejmują przejęcia i amortyzację.

Jeśli funkcja wycofywania masowego jest wyłączona, transakcje można wycofać pojedynczo ze strony **Transakcje dostawcy**, ze strony **Transakcje środków trwałych** lub z leasingu środka trwałego, w zależności od typu transakcji.

Jeśli funkcja masowego wycofania jest włączona, jedna lub więcej transakcji środków trwałych może być również odwrócona ze strony **Transakcje załącznikowe** w ramach dziennika, z którego transakcje zostały zaksięgowane.

### <a name="reasons-why-transactions-cant-be-reversed"></a>Powody, dla których nie można cofnąć transakcji

Nie można cofnąć transakcji z następujących powodów:

- Okres obrachunkowy jest zawieszony lub trwale zamknięty:

    - Jeśli data wycofania znajduje się w okresie obrachunkowym, który nie jest otwarty, nie można cofnąć transakcji.
    - Jeśli transakcja obsługuje wpis daty cofania, transakcja nadal może zostać wycofana, zmieniając datę wycofania na okres otwarty.

- Proces zamknięcia księgi głównej na koniec roku został uruchomiony:

    - Data księgowania transakcji jest w roku obrachunkowym, który został zamknięty w księdze głównej. Chociaż okres w roku obrachunkowym może być nadal otwarty, nie można cofnąć transakcji, jeśli proces zamknięcia na koniec roku został uruchomiony dla roku obrachunkowego. Rok obrachunkowy ma inny stan niż okresy w nim.
    - Zamknięcie na koniec roku można cofnąć, a następnie można wycofać transakcję. Takie podejście może nie być rozwiązaniem. Może być łatwiejsze do ręcznego wprowadzenia transakcji cofania w okresie otwartym zamkniętego roku obrachunkowego lub następnego roku obrachunkowego, w zależności od stanu procesu zamknięcia fiskalnego. Jeśli nowa transakcja jest księgowana w otwartym okresie roku obrachunkowego, który został przez proces zamknięcia na koniec roku, zamknięcie na koniec roku musi zostać ponownie uruchomione.

- Nabycia:

    - Jeśli nabycie miało miejsce na fakturze od dostawcy zamówienia zakupu, należy to zrobić, wprowadzając fakturę korygującą dostawcy. Aby uzyskać więcej informacji na temat utworzenia transakcji wycofania, zobacz [Tworzenie zamówienia zwrotu zakupu](../../supply-chain/procurement/tasks/create-purchase-return-order.md).
    - Nabycie miało miejsce w transakcji projektu.
    - Nie można cofnąć nabycia po zaksięgowaniu amortyzacji środka trwałego. Amortyzacja musi zostać wycofana, zanim można cofnąć nabycie.
    - Jeśli stan modelu ewidencji lub księgi amortyzacji środka trwałego nie jest otwarty, nie można cofnąć transakcji.

- Likwidacje:

    - Utylizacja odbywa się za pomocą faktury tekstowej:

        - Korekta faktury tekstowej jest blokowana, jeśli zawiera środek trwały. Jeśli jednak środek trwały jest usuwany za pośrednictwem arkusza, fakturę niezależną można wycofać z rekordu środka trwałego.

    - Jeśli stan modelu ewidencji lub księgi amortyzacji środka trwałego nie jest otwarty, nie można cofnąć transakcji.

- Amortyzacja:

    - Amortyzację **można** cofnąć, jeśli zaksięgowana jest również późniejsza amortyzacja. Jednak otrzymasz ostrzeżenie, ponieważ takie podejście nie jest najlepszym rozwiązaniem.
    - Jeśli stan modelu ewidencji lub księgi amortyzacji środka trwałego nie jest otwarty, nie można cofnąć transakcji.

- Transakcje (lub transakcje wycofane) dla określonego składnika aktywów i księgi środków trwałych istnieją dla daty transakcji załącznika lub później.
- Transakcja zawiera konto środka, ale jest wycofywana ze strony **Transakcje dla \<main account\>** lub z niepoprawnej księgi podrzędnej, takiej jak Należności lub zobowiązania:

    - Jak sugeruje ten powód, nawet po włączeniu funkcji odwrócenia masowego niektóre transakcje księgo podrzędnej można odwrócić tylko z określonych stron.
    - Jeśli nabycie występuje na fakturze dostawcy zamówienia innego zakupu lub arkuszu faktury od dostawcy, można go wycofać tylko ze strony **Transakcje dostawcy** w rozrachunkach z dostawcami.
    - Jeśli składnik aktywów zostanie nabyty z leasingu aktywów, można go wycofać ze strony **Transakcje z tytułu obciążeń** w leasingu aktywów.
