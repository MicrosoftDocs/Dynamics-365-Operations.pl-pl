---
title: Domyślne wymiary finansowe w arkuszach finansowych
description: W tym temacie opisano reguły definiujące sposób, w jaki wartości wymiarów finansowych są ustawiane dla transakcji wprowadzanych za pomocą arkuszy finansowych. Zawiera on również szczegółowe scenariusze, w których są używane wymiary stałe.
author: kweekley
ms.date: 09/04/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTransDaily, LedgerJournalTransVendInvoice, LedgerJournalTransVendPaym, LedgerJournalTransCustPaym
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2020-12-14
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 327bc27f068e1f9eefacc6b5defa27044cb1a77e
ms.sourcegitcommit: d420b96d37093c26f0e99c548f036eb49a15ec30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/03/2021
ms.locfileid: "7472539"
---
# <a name="default-financial-dimensions-on-financial-journals"></a>Domyślne wymiary finansowe w arkuszach finansowych

[!include [banner](../includes/banner.md)]

W tym temacie opisano reguły definiujące sposób, w jaki wartości wymiarów finansowych są ustawiane dla transakcji wprowadzanych za pomocą arkuszy finansowych (ale nie za pomocą arkuszy magazynowych lub arkuszy projektu). Zawiera on również szczegółowe scenariusze, w których są używane wymiary stałe.

## <a name="symptom"></a>Objaw

Wartości wymiarów finansowych nie są ustawione zgodnie z oczekiwaniami na koncie lub koncie przeciwstawnym w arkuszu finansowym. Oto dwa przykłady następujących scenariuszy:

Załącznik jest wprowadzany w arkuszu arkusza ogólnego. Konto jest kontem dostawcy, a konto przeciwstawne kontem bankowym. Wymiary finansowe dostawcy są domyślnie wprowadzane na koncie, ale wymiary finansowe banku nie są domyślnie wprowadzane na koncie przeciwstawnym. Zamiast tego wartości wymiaru z konta są domyślnie wprowadzane na koncie przeciwstawnym.

Odbiorcy przypisano domyślne wartości wymiarów finansowych, a konto główne przychodów ma wartość wymiaru stałego przypisaną do wymiaru finansowego działu. Załącznik jest wprowadzany w arkuszu ogólnym.  Konto jest odbiorcą, a konto przeciwstawne jest kontem księgowym, a konkretnie kontem przychodów z wartością wymiaru stałego. Nie ustawiono wymiaru stałego na koncie przeciwstawnym dla konta głównego przychodów. Zamiast tego jest ustawiana wartość wymiaru działu z konta, która pochodzi od odbiorcy.  Po zaksięgowaniu załącznika w zaksięgowanym wpisie księgowym jest używana wartość wymiaru stałego, ale mimo to załącznik zawiera wartość działu odbiorcy na koncie przychodów. 

Jakie reguły są stosowane dla wartości wymiarów finansowych ustawionych dla załączników w arkuszu?

## <a name="resolution"></a>Rozwiązanie

Poniżej przedstawiono reguły domyślnego wprowadzania wartości wymiarów finansowych w wierszach załącznika w arkuszach finansowych, takich jak arkusz finansowy lub arkusz faktur od dostawcy. 

1. **Nagłówek arkusza**

   - Wymiary nagłówka arkusza są domyślnie wprowadzane z wymiarów nazwy arkusza.

2. **Konto wiersza arkusza**

   - Wymiary konta wiersza arkusza są domyślnie wprowadzane z wymiarów nagłówka arkusza.
   - Jeśli jakiekolwiek wymiary finansowe są puste, ich wartości są domyślnie wprowadzane z wymiarów odbiorcy, dostawcy, banku, środka trwałego, projektu lub księgi.

     - Jeśli typem konta jest **Księga**, podczas wprowadzania transakcji wymiar stały na koncie księgowym jest traktowany jak wymiar domyślny.
     - Jeśli konto jest typu **Odbiorca**, **Dostawca**, **Bank**, **Środki trwałe** lub **Projekt**, nie można jeszcze ustalić konta głównego. W związku z tym wymiar stały nigdy nie będzie wprowadzany domyślnie dla konta.

3. **Konto przeciwstawne wiersza arkusza**

 - Najpierw wymiary konta przeciwstawnego wiersza arkusza są domyślnie wprowadzane z wymiarów konta wiersza arkusza.

 - Jeśli jakiekolwiek wymiary finansowe są puste, następne wartości domyślnie będą wprowadzane z domyślnych wymiarów odbiorcy, dostawcy, banku, środka trwałego, projektu lub księgi.
   1. Jeśli typem konta przeciwstawnego jest **Księga**, podczas wprowadzania transakcji wymiar stały na koncie księgowym jest traktowany jak wymiar domyślny. Jeśli wartość wymiaru została już wprowadzona domyślnie w ustawieniach konta, wartość domyślna lub wartość wymiaru stałego konta głównego nie zastąpi istniejącej wartości.
   2. Jeśli konto przeciwstawne jest typu **Odbiorca**, **Dostawca**, **Bank**, **Środki trwałe** lub **Projekt**, konto główne nie jest jeszcze znane, więc wymiar stały nigdy nie będzie domyślny dla konta przeciwstawnego.

4. **Księgowanie**

    1. Podczas księgowania oceniane jest konto główne dla każdego wiersza wpisu księgowania (dla konta i konta przeciwstawnego) w celu ustalenia, czy istnieje wartość wymiaru stałego. Jeśli zdefiniowano wymiar stały, istniejące lub puste wartości zostaną zastąpione wartością tego stałego wymiaru.

        Wartość wymiaru stałego **nie** jest wyświetlana w wierszach arkusza po zaksięgowaniu. Jest on zamiast tego ukazany we wpisie księgowania podczas wyświetlania załącznika po jego zaksięgowaniu.

    2. Podczas księgowania nie są domyślnie wprowadzane żadne inne wartości wymiarów, w tym dodatkowe konta księgowe, które mogą być dodawane podczas księgowania, takie jak konta zaokrąglania groszowego i międzyfirmowe należne dla lub należne z kont. Domyślne wpisy wymiarów dla dodatkowych kont księgowych są pobierane z kont lub kont przeciwstawnych.

Na potrzeby domyślnego wprowadzania wartości wymiarów proces domyślny arkusza nie może ustalić, czy wartość pustego wymiaru została pozostawiona pusta celowo, czy też domyślny wpis nie został dokonany. Jeśli wartość wymiaru została pozostawiona pusta celowo, wartość może ciągle być wprowadzona domyślnie przy użyciu opisanej wcześniej kolejności domyślnej. Jeśli wymiar musi mieć pustą wartość, może być konieczne utworzenie wymiaru o wartości **0** (zero) lub **Puste**, aby można było go użyć w miejsce pustego wymiaru.

Przejrzyj poniższe scenariusze, aby zapoznać się z przykładami domyślnej kolejności wymiarów finansowych.

### <a name="scenario-1"></a>Scenariusz 1

Przejdź do opcji **Księga główna \> Ustawienia arkusza \> Nazwy arkusza** i wybierz nazwę arkusza **GenJrn**. Następnie na skróconej karcie **Wymiary finansowe** zdefiniuj następujące wartości dla domyślnych wymiarów finansowych:

- **BUSINESSUNIT:** 001
- **DEPARTMENT:** 024

[![Strona nazw arkuszy](./media/financial-dimension-defaulting-jrnl-names-01.png)](./media/financial-dimension-defaulting-jrnl-names-01.png)

Przejdź do opcji **Księga główna \> Wpisy w arkuszu \> Arkusz główny** i utwórz nowy arkusz główny, który używa nazwy arkusza **GenJrn**. Wymiary są domyślnie wprowadzane z nazwy arkusza (tabela LedgerJournalName) do nagłówka arkusza (tabela LedgerJournalTable), jak pokazano na karcie **Wymiary finansowe**.

[![Karta Wymiary finansowe na stronie Arkusze główne](./media/financial-dimension-defaulting-genrl-jrnl-02.png)](./media/financial-dimension-defaulting-genrl-jrnl-02.png)

Przejdź do opcji **Wiesze**. W polu **Typ konta** wybierz opcję **Księga**, a następnie w polu **Konto** wprowadź wartość **170150**. Następnie wybierz klawisz **Tab**, aby przenieść poza pole. Wymiary są domyślnie wprowadzane z nagłówka arkusza. Dlatego wartość **Konto** jest pokazywana jako **170150-001-024**.

[![Wiersze arkusza dla arkusza finansowego na stronie załącznika arkusza](./media/financial-dimension-defaulting-jrnl-vchr-03.png)](./media/financial-dimension-defaulting-jrnl-vchr-03.png)

Zmień wartość **Konto** na **170150-001-023**. Wprowadź kwotę debetu lub kwotę kredytu. W polu **Typ konta przeciwstawnego** wybierz opcję **Księga**, a następnie w polu **Konto przeciwstawne** wprowadź wartość **600150**. Wartości wymiaru są domyślnie wprowadzane z konta. Dlatego wartość **Konto przeciwstawne** jest pokazywana jako **600150-001-023**.

### <a name="scenario-2"></a>Scenariusz 2

Użyj tych samych wymiarów finansowych, które zostały zdefiniowane dla nazwy arkusza w scenariuszu 1. Następnie przejdź do opcji **Rozrachunki z odbiorcami \> Odbiorcy \> Wszyscy odbiorcy** i zdefiniuj domyślne wartości wymiarów finansowych dla odbiorcy US-001. Wybierz odbiorcę, aby otworzyć szczegóły dotyczące odbiorcy. Na karcie **Wymiary finansowe** zachowaj domyślną wartość wymiaru **BUSINESSUNIT** (**001**). Dodaj wymiar **COSTCENTER** i wprowadź wartość **007**.

Utwórz nowy arkusz finansowy, który używa nazwy arkusza **GenJrn**. Na karcie **Wymiary finansowe** zmień domyślną wartość **BUSINESSUNIT** z **001** na **002**.

Przejdź do opcji **Wiesze**. W polu **Typ konta** wybierz opcję **Odbiorca**, a następnie w polu **Konto** wprowadź wartość **US-001**. Aby wyświetlić wymiary finansowe dla typów kont innych niż księgowe, wybierz **Wymiary finansowe \> Konto**. Wprowadzane są następujące wpisy domyślne dla wartości wymiarów finansowych:

- **BUSINESSUNIT:** 002 — domyślny wpis pochodzi z nagłówka arkusza. Wartość **001** nie jest wprowadzana domyślnie z odbiorcy US-001, ponieważ została już wprowadzona wartość domyślna.
- **COSTCENTER:** 007 — domyślny wpis pochodzi z ustawień odbiorcy US-001.
- **DEPARTMENT:** 024 — domyślny wpis pochodzi z nagłówka arkusza.

W wierszu w polu **Typ konta przeciwstawnego** wybierz opcję **Księga**, a następnie w polu **Konto przeciwstawne** wprowadź wartość **600150**. W wierszu wprowadzane są następujące wartości wymiarów finansowych:

- **BUSINESSUNIT:** 002 — domyślny wpis pochodzi z wymiarów finansowych konta. (Początkowo został domyślnie wprowadzony z nagłówka arkusza.)
- **DEPARTMENT:** 024 — domyślny wpis pochodzi z wymiarów finansowych konta. (Początkowo został domyślnie wprowadzony z nagłówka arkusza.)
- **COSTCENTER:** 007 — domyślny wpis pochodzi z wymiarów finansowych konta. (Początkowo został domyślnie wprowadzony z odbiorcy.)

### <a name="scenario-3"></a>Scenariusz 3

W tym samym arkuszu, który został użyty dla scenariusza 2, dodaj nowy wiersz. W polu **Typ konta** wybierz opcję **Księga**, a następnie w polu **Konto** wprowadź wartość **170150**. Wyczyść domyślne wartości wymiarów, aby pozostało tylko konto główne 170150. W polu **Typ konta przeciwstawnego** wybierz opcję **Odbiorca**, a następnie w polu **Konto przeciwstawne** wprowadź wartość **US-001**. Wprowadzane są następujące wpisy domyślne dla wartości wymiarów finansowych:

- **BUSINESSUNIT:** 002 — domyślny wpis pochodzi z nagłówka arkusza, ponieważ wartość wymiaru Konto jest pusta. Wartość **001** nie jest wprowadzana domyślnie z odbiorcy US-001, ponieważ wartość domyślna została już pobrana z nagłówka arkusza. Jeśli wartość **BUSINESSUNIT** została celowo pozostawiona pusta, należy także usunąć wymiar finansowy z konta przeciwstawnego.
- **COSTCENTER:** 007 — domyślny wpis pochodzi od odbiorcy US-001, ponieważ wartości wymiaru konta i wymiaru nagłówka arkusza są puste. Jeśli wartość **COSTCENTER** została celowo pozostawiona pusta, należy także usunąć wymiar finansowy z konta przeciwstawnego.
- **DEPARTMENT:** 024 — domyślny wpis pochodzi z nagłówka arkusza, ponieważ wartość wymiaru Konto jest pusta. Jeśli wartość **DEPARTMENT** została celowo pozostawiona pusta, należy także usunąć wymiar finansowy z konta przeciwstawnego.

### <a name="scenario-4"></a>Scenariusz 4

Użyj tych samych domyślnych wartości wymiarów finansowych, które zostały zdefiniowane dla nazwy arkusza i odbiorcy w scenariuszach 1 i 2. Następnie zdefiniuj stałą wartość wymiaru dla wymiaru **BUSINESSUNIT** na koncie głównym 170150. Wybierz opcje **Księga główna \> Plan kont \> Konta \> Konta główne**. W polu **Konto główne** wybierz opcję **170150**, a następnie na karcie **Firma zastępuje** wybierz opcję **Dodaj**. Wybierz **USMF** jako osobę prawną, a następnie wybierz opcję **Dodaj**. Wybierz ten rekord, a następnie wybierz pozycję **Wymiary domyślne**. Zmień wymiar **BUSINESSUNIT** na **Wartość stała** i wprowadź wartość **003**.

Utwórz nowy arkusz finansowy, który używa nazwy arkusza **GenJrn**. Z karty **Wymiary finansowe** usuń wszystkie domyślne wartości wymiarów.

Przejdź do opcji **Wiesze**. W polu **Typ konta** wybierz opcję **Księga**, a następnie w polu **Konto** wprowadź wartość **170150**. Następnie wybierz klawisz **Tab**, aby przenieść poza pole. Zamiast tego wartości wymiarów z konta są domyślnie wprowadzane z ustawienia konta głównego dla konta 170150. Dlatego wartość **Konto** jest pokazywana jako **170150-003-**.

Zmień wartość **Konto** na **170150-004-**. **Funkcja arkusza nie uniemożliwia zmiany stałej wartości wymiaru.** Wprowadź kwotę debetu lub kwotę kredytu. W polu **Typ konta przeciwstawnego** wybierz opcję **Księga**, a następnie w polu **Konto przeciwstawne** wprowadź wartość **170250**. Wartość wymiaru finansowego 004 jest domyślnie wprowadzana z konta. Następnie zaksięguj dokument. W arkuszu wybierz pozycję **Załącznik**. Zwróć uwagę, że podczas księgowania wartość **BUSINESSUNIT** została przywrócona do stałej wartości wymiaru — **003**.

Po powrocie do załącznika w arkuszu wymiar **BUSINESSUNIT** **nie** odzwierciedla stałej wartości wymiaru. Przed zaksięgowaniem ma ona zawsze wartość wyświetlaną na ekranie. Proces księgowania nie zmienia żadnych wartości wprowadzonych w załączniku. Podczas księgowania zmieniany jest tylko wpis księgowania.

## <a name="developer-notes"></a>Uwagi dewelopera

Jeśli jesteś deweloperem i chcesz sprawdzić kod domyślnego procesu, przejrzyj następujące metody:

- **LedgerJournalEngine.accountModified()** — ta metoda jest głównym punktem wejścia dla domyślnego procesu wymiaru konta głównego, który jest standardem dla wszystkich arkuszy (i jest zastępowany przez niektóre typy arkuszy).
- **LedgerJournalEngine.offsetAccountModified()** — ta metoda jest głównym punktem wejścia dla domyślnego procesu wymiaru konta przeciwstawnego.
