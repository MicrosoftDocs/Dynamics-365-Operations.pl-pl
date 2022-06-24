---
title: Omówienie posiadaczy zaliczek
description: Ten artykuł zawiera informacje dotyczące funkcji posiadacza zaliczki.
author: liza-golub
ms.date: 09/15/2021
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: HcmWorkerAdvHolderTableListPage_RU
audience: Application User
ms.reviewer: kfend
ms.custom:
- "262574"
- intro-internal
ms.search.region: Czech Republic, Estonia, Hungary, Latvia, Lithuania, Poland, Russia
ms.author: elgolu
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 7b514b7332a7ef73136c2f534c64db7c889f76f0
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8902369"
---
# <a name="advance-holders-overview"></a>Omówienie posiadaczy zaliczek

[!include [banner](../includes/banner.md)]

*Posiadacz zaliczki* to pracownik firmy, który odpowiada za kwotę wydatku pokrytą przez organizację. Posiadaczem zaliczki może być tylko pracownik firmy. Gdy następuje zaopatrzenie, posiadacz zaliczki informuje firmę o dokonanych wydatkach. Wtedy firma zwraca pracownikowi wydatkowaną kwotę. Firma kontroluje salda wszystkich posiadaczy zaliczek. Użytkownicy w firmach w Estonii, na Łotwie, Litwie, w Polsce, Czechach, na Węgrzech i w Rosji mogą wykazywać konkretne transakcje towarzyszące operacjom z udziałem pracowników firmy odpowiedzialnych za kwoty wydatków pokrywane przez organizację.

## <a name="set-up-an-advance-holder"></a>Konfigurowanie posiadacza zaliczki
Wykonaj poniższe zadania aż do posiadacza zaliczki. Pamiętaj, aby wykonać te zadania w podanej kolejności.

1. Utwórz grupę posiadaczy zaliczek.
2. Konfiguruj profil księgowania pracownika.
3. Konfiguruj parametry modułu Rozrachunki z dostawcami.
4. Utwórz szczegółowe warunki płatności dla posiadacza zaliczki.
5. Utwórz szczegółowe warunki płatności dla posiadacza zaliczki.
6. Utwórz posiadacza zaliczki.


### <a name="advance-holder-groups"></a>Grupy posiadaczy zaliczek

Użyj strony **Grupy posiadaczy zaliczek**, aby utworzyć grupę posiadaczy zaliczek. Można określić nazwę, opis i konto przeciwstawne dla grupy posiadaczy zaliczek.
### <a name="employee-posting-profile"></a>Profil księgowania pracownika

Użyj strony **Profile księgowania pracowników**, aby utworzyć profil dla transakcji posiadaczy zaliczek. W profilu księgowania pracownika można podać następujące informacje:

|      Pole      |                                            opis                                            |
|-----------------|---------------------------------------------------------------------------------------------------|
| **Profil księgowania** |  Wprowadź kod identyfikacyjny profilu księgowania dla posiadacza zaliczki.               |
|   **opis**   |  Wprowadź krótki opis profilu księgowania.                         |
|    **Ważny dla**    |  Wybierz jedną z następujących opcji poziomu grupowania dla konfiguracji profilu księgowania: <ul> <li>**Tabela** — Ta opcja służy do konfigurowania profilu księgowania dla jednego posiadacza zaliczki. Należy podać kod posiadacza zaliczki w polu **Odwołanie**.</li> <li>**Grupa** — Ta opcja służy do konfigurowania profilu księgowania dla grupy posiadaczy zaliczek. Należy podać kod grupy w polu **Odwołanie**.</li> <li>**Wszystkie** — Ta opcja służy do konfigurowania profilu księgowania dla wszystkich posiadaczy zaliczki.</li></ul> |
| **Odwołanie** | Wybierz kod posiadacza zaliczki, jeśli wybrano **tabelę** w polu **ważny dla** lub wybierz grupę posiadaczy zaliczek, jeśli wybrano **grupę** w polu **ważne dla**. |
| **Konto rozrachunkowe** | Wybierz konto podsumowujące do księgowania transakcji. |



### <a name="account-payable-parameters"></a>Parametry modułu rozrachunków z dostawcami

Aby wykazywać transakcje posiadaczy zaliczek, należy skonfigurować następujące pola na stronie **Parametry modułu rozrachunków z dostawcami** w sekcji **Posiadacze zaliczek**.

|  Pole                                         | Opis       |
|------------------------------------------------|-------------------|
| **Profil księgowania**                            | Wybierz domyślny profil do realizowania transakcji posiadaczy zaliczek.                                                                                                         |
| **Sortowanie posiadaczy zaliczek**                     | Jeśli zaznaczysz tę opcję, posiadacze zaliczek będą wyświetlani na początku listy na stronie **Posiadacze zaliczek**.                                                                     |
| **Rozchody przy otwartym saldzie**                 | Jeśli zaznaczysz tę opcję, będzie dozwolone wydanie zaliczki gotówkowej posiadaczowi zaliczki mającemu otwarte saldo dodatnie.                                                                      |
| **Zamykanie salda za pośrednictwem kasy** | Wybierz kod arkusza dokumentu kasowego. Ten kod arkusza jest używany do generowania dokumentów KW i KP podczas zamykania sald posiadacza zaliczki za pośrednictwem kasy. |
| **Kasa**                                       | Wybierz konto kasowe, które będzie decydowało o załącznikach używanych do zamykania sald posiadacza zaliczki.                                                                 |
| **Zamykanie salda za pośrednictwem banku** | Wybierz kod arkusza transakcji, który będzie używany do zamykania sald za pośrednictwem banku.                                                                                                   |
| **Typ konta**                               | Wybierz bank, który będzie używany do zamykania sald posiadacza zaliczki za pośrednictwem banku.                                                                                                        |
| **Konto główne**                               | Wybierz kod konta bankowego, który będzie używany do zamykania sald posiadacza zaliczki za pośrednictwem banku.                                                                                           |

### <a name="terms-of-payment-for-advance-holder"></a>Warunki płatności dla posiadacza zaliczki

Aby poprawnie zarejestrować i zaksięgować zamówienie zakupu w kontekście posiadacza zaliczki, należy użyć warunków płatności skonfigurowanych z opcją **Od posiadacza zaliczki** ustawioną na wartość **Prawda**.

### <a name="create-an-advance-holder"></a>Tworzenie posiadacza zaliczki

Przed utworzeniem posiadacza zaliczki muszą już istnieć skonfigurowani pracownicy. Aby uzyskać więcej informacji, zobacz [Wprowadzanie informacji o pracowniku (przewodnik po zadaniu)](../../human-resources/hr-personnel-enter-worker-information.md). 

1. Wybierz kolejno opcje **Rozrachunki z dostawcami** > **Posiadacze zaliczek** > **Posiadacze zaliczek**.

    > [!NOTE]
    > Na stronie **Posiadacze zaliczek** nie można dodawać ani usuwać pracowników etatowych. Pracownicy muszą zostać najpierw zatrudnieni w module **Zasoby ludzkie**. Na stronie **Profile księgowania pracowników** można skonfigurować profil księgowania pracownika, który jest używany do księgowania sald posiadacza zaliczki.

2. Zaznacz pracownika i kliknij przycisk **Edytuj**.
3. Na skróconej karcie **Ogólne** w opcji **Posiadacz zaliczki** ustaw wartość **Tak**, aby wskazać, że pracownik etatowy jest posiadaczem zaliczki.
4. W polu **Grupa** wybierz grupę posiadaczy zaliczek, do której należy pracownik etatowy.
5. W obszarze **Dokument tożsamości** podaj dane dokumentu identyfikacyjnego.
    - **Seria**: wprowadź serię dokumentu używanego do weryfikacji tożsamości posiadacza zaliczki.
    - **Numer**: wprowadź numer dokumentu używanego do weryfikacji tożsamości posiadacza zaliczki.
    - **Data wystawienia**: wybierz lub wprowadź datę wydania dokumentu.
    - **Wystawione przez**: Wprowadź dane organu lub osoby, która wydała dokument.
6. Wybierz przycisk **Zapisz**, aby zamknąć stronę.

> [!NOTE]
> Jeśli na stronie **Parametry modułu rozrachunków z dostawcami** opcja **Sortowanie posiadaczy zaliczek** jest ustawiona na **Tak**, posiadacze zaliczek są wyświetlani w górnej części siatki na stronie **Posiadacze zaliczek**.


## <a name="advance-holder-inquiries-and-reports"></a>Zapytania i raporty dotyczące posiadaczy zaliczek

### <a name="advance-holder-transactions-inquiry"></a>Zapytania o transakcje posiadaczy zaliczek

Aby uzyskać listę transakcji posiadacza zaliczki, wybierz opcję **Transakcje** znajdującą się na stronie **Posiadacze zaliczek**. Aby wyświetlić transakcje wszystkich posiadaczy zaliczek lub utworzyć szczegółowe zapytanie dotyczące transakcji posiadaczy zaliczek, wybierz kolejno opcje **Rozrachunki z dostawcami** > **Zapytania i raporty** > **Zapytania i raporty posiadaczy zaliczek** > **Transakcje**. Wybierz opcję **Załącznik**, a zostanie otwarta strona **Transakcje na załączniku**.

### <a name="advance-holder-balance-inquiry"></a>Zapytania o salda posiadaczy zaliczek

Aby zobaczyć saldo posiadacza zaliczki, użyj strony **Posiadacze zaliczek**. Aby wyświetlić salda wszystkich posiadaczy zaliczek lub utworzyć szczegółowe zapytanie dotyczące kont posiadaczy zaliczek, wybierz kolejno opcje **Rozrachunki z dostawcami** &gt; **Zapytania i raporty** &gt; **Zapytania i raporty posiadaczy zaliczek** &gt; **Saldo**.
### <a name="advance-holder-balance-report"></a>Raport salda posiadacza zaliczki

Aby wyświetlić podgląd i wydrukować raport oparty na informacjach o saldach posiadaczy zaliczek, wybierz kolejno opcje **Rozrachunki z dostawcami** &gt; **Zapytania i raporty** &gt; **Zapytania i raporty posiadaczy zaliczek** &gt; **Raport salda posiadacza zaliczki**.
### <a name="advance-holder-transactions-report"></a>Raport transakcji posiadacza zaliczki

Aby wyświetlić podgląd i wydrukować raport oparty na transakcjach posiadaczy zaliczek, wybierz kolejno opcje **Rozrachunki z dostawcami** &gt; **Zapytania i raporty** &gt; **Zapytania i raporty posiadaczy zaliczek** &gt; **Raport transakcji posiadacza zaliczki**.

## <a name="advance-holder-transactions"></a>Transakcje posiadacza zaliczki

Transakcje dla pracowników będących posiadaczami zaliczek mogą być księgowane przy użyciu kont posiadaczy zaliczek. Identyfikator pracownika określony dla każdego posiadacza zaliczki może służyć do śledzenia wszystkich transakcji danego posiadacza zaliczki. Ten numer jest pobierany jako numer konta dla transakcji posiadacza zaliczki na stronach **Arkusze finansowe** i **Transakcje posiadacza zaliczki**.

### <a name="create-and-post-a-purchase-order-with-advance-holder-details"></a>Tworzenie i księgowanie zamówienia zakupu z danymi posiadacza zaliczki
Aby uzyskać bardziej ogólne informacje o zamówieniach zakupu, zobacz [Omówienie zamówień zakupu](../../supply-chain/procurement/purchase-order-overview.md). Jeśli faktura od dostawcy zostanie utworzona i zaksięgowana z danymi posiadacza zaliczki, salda posiadacza zaliczki zostaną zaksięgowane na koncie bilansowym pracownika, a nie na koncie bilansowym dostawcy. Aby dodać szczegóły posiadacza zaliczki do zamówienia zakupu, wykonaj następujące czynności:

1. W sekcji **Cena i rabat** w polu **Warunki płatności** wybierz termin płatności. Aby uzyskać więcej informacji o **Warunkach płatności**, zobacz temat [Definiowanie warunków płatności dostawcy](../accounts-payable/tasks/define-vendor-payment-terms.md). 
2. Wybierz termin płatności, który ma zaznaczoną opcję **Od posiadacza zaliczki** na stronie **Warunki płatności**. 
3. Na skróconej karcie **Cena i rabat** w polu **Posiadacz zaliczki** wybierz posiadacza zaliczki dla zamówienia zakupu.

Proces księgowania zamówienia zakupu utworzy dwie transakcje z dostawcą o przeciwnych kwotach oraz jedną transakcję posiadacza zaliczki. Bez szczegółów posiadacza zaliczki byłaby tworzona tylko jedna transakcja z dostawcą.

### <a name="settle-advance-holder-balances-by-using-the-bank"></a>Rozliczanie salda posiadacza zaliczki za pośrednictwem banku
Podczas rozliczania sald posiadaczy zaliczek za pośrednictwem banku zapisy w arkuszu dotyczące zamknięcia tych sald są tworzone w arkuszu finansowym. Można skonfigurować kod dla arkusza i banku w obszarze **Posiadacze zaliczek** na stronie **Parametry modułu rozrachunków z dostawcami**. 

1. Aby zamknąć saldo posiadacza zaliczki za pośrednictwem banku, wybierz kolejno opcje **Rozrachunki z dostawcami** > **Posiadacze zaliczek** > **Posiadacze zaliczek**. 
2. W okienku akcji wybierz opcję **Saldo** > **Zamknij za pośrednictwem banku**. 
3. Wprowadź poniższe informacje na stronie **Zamknij — bank**:

    | Pole                    | opis |
    |------------------------------|-------------------|
    | **Data płatności**          | Wprowadź dzień, w którym płatność powinna zostać zaksięgowana.|
    | **Kwota do przeniesienia** | Wprowadź kwotę salda istniejącą podczas zamknięcia. Domyślnie jest wyświetlana kwota wskazana w polu **Kwota** na stronie **Saldo**. |
    | **Automatyczna**                | Zaznacz pole wyboru **Automatycznie**, aby automatycznie tworzyć i zaksięgować arkusz wstępnie ustawiony na stronie **Parametry modułu rozrachunków z dostawcami**.|

### <a name="settle-advance-holder-balances-by-using-cash"></a>Rozliczanie salda posiadacza zaliczki używając gotówki
Podczas rozliczenia sald posiadaczy zaliczek używając gotówki zapisy w arkuszu dotyczące zamknięcia tych sald są tworzone w arkuszu kasowym. Można skonfigurować kod dla arkusza i kasy na karcie **Posiadacze zaliczek** na stronie **Parametry modułu rozrachunków z dostawcami**. 

1. Aby zamknąć saldo posiadacza zaliczki używając gotówki, wybierz kolejno opcje **Rozrachunki z dostawcami** > **Posiadacze zaliczek** > **Posiadacze zaliczek**. 
2. W okienku akcji wybierz opcję **Saldo** > **Zamknij używając gotówki**. 
3. Wprowadź poniższe informacje na stronie **Zamknij — kasa**:

    | Pole                    | opis
    |------------------------------|-----------------|
    | **Data płatności**          | Wprowadź dzień, w którym płatność powinna zostać zaksięgowana.|
    | **Kwota do przeniesienia** | Wprowadź kwotę salda istniejącą podczas zamknięcia. Domyślnie jest wyświetlana kwota wskazana w polu **Kwota** na stronie **Saldo**. |
    | **Automatyczna**                | Zaznacz pole wyboru **Automatycznie**, aby automatycznie tworzyć i zaksięgować arkusz wstępnie ustawiony na stronie **Parametry modułu rozrachunków z dostawcami**.     |

Jeśli po przetwarzaniu arkusza kasowego kwota w polu **Kwota do przeniesienia** była ujemna, jest generowany dokument KW dla posiadacza zaliczki po zamknięciu sald. Jeśli kwota w polu **Kwota do przeniesienia** była dodatnia, jest generowany dokument KP.

## <a name="additional-resources"></a>Dodatkowe zasoby

- [Zaliczki na rzecz pracownika etatowego (Europa Wschodnia)](tasks/advance-payment-employee.md)
- [Omówienie posiadaczy zaliczek dla Rosji](rus-advance-holders.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
