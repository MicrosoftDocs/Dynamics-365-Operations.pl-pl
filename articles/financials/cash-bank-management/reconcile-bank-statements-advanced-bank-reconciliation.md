---
title: "Uzgadnianie wyciągów bankowych przy użyciu funkcji Zaawansowane uzgadnianie konta bankowego"
description: "Funkcja Zaawansowane uzgadnianie konta bankowego umożliwia importowanie elektronicznych wyciągów bankowych oraz ich automatyczne uzgadnianie z transakcjami bankowymi w programie Microsoft Dynamics 365 for Finance and Operations Enterprise Edition. W tym temacie opisano proces uzgadniania."
author: saraschi2
manager: AnnBe
ms.date: 09/11/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 98243
ms.assetid: 9df13adf-aa9d-4f6b-bde6-25a214611692
ms.search.region: global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: a89ed8055b33af4ee39695cf6d8b4d6e1aad9c92
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---

# <a name="reconcile-bank-statements-by-using-advanced-bank-reconciliation"></a>Uzgadnianie wyciągów bankowych przy użyciu funkcji Zaawansowane uzgadnianie konta bankowego

[!include[banner](../includes/banner.md)]


Funkcja Zaawansowane uzgadnianie konta bankowego umożliwia importowanie elektronicznych wyciągów bankowych oraz ich automatyczne uzgadnianie z transakcjami bankowymi w programie Microsoft Dynamics 365 for Finance and Operations Enterprise Edition. W tym temacie opisano proces uzgadniania.  

<a name="import-an-electronic-bank-statement"></a>Importowanie elektronicznego wyciągu bankowego
-----------------------------------

Wyciągi bankowe importuje się przy użyciu operacji **Importowanie wyciągu** dostępnej na karcie **Wyciągi bankowe**. Na wyciągu bankowym konto bankowe jest identyfikowane za pomocą kombinacji wartości ustawianych w szczegółach konta bankowego. Wartości te obejmują nazwę banku, numer konta bankowego, numer rozliczeniowy, kod SWIFT (Stowarzyszenie na rzecz Światowej Międzybankowej Telekomunikacji Finansowej) i międzynarodowy numer konta bankowego (IBAN). 

Można przekazać wyciąg bankowy zawierający informacje dla jednego konta lub wielu kont. Jeśli istnieje wiele kont, mogą one należeć do różnych firm.

-   Aby zaimportować jeden plik wyciągu bankowego dla jednego konta, w opcji **Importuj wyciąg obejmujący wiele kont bankowych we wszystkich firmach** ustaw wartość **Nie**, a następnie wybierz konto bankowe skojarzone z wyciągiem. Kliknij przycisk **Przeglądaj**, zaznacz powiązany plik wyciągu bankowego i kliknij przycisk **Przekaż**.
-   Aby zaimportować jeden plik wyciągu bankowego dla wielu kont, w opcji **Importuj wyciąg obejmujący wiele kont bankowych we wszystkich firmach** ustaw wartość **Tak**. Kliknij przycisk **Przeglądaj**, zaznacz powiązany plik wyciągu bankowego i kliknij przycisk **Przekaż**.

Jeśli któregokolwiek wyciągu w pliku elektronicznym nie można powiązać z kontem bankowym przy użyciu pól identyfikujących, nie zostaną one zaimportowane. Jednak pozostałe wyciągi w pliku nadal można zaimportować. Użytkownik otrzyma komunikat informujący, że import wyciągów bankowych nie powiódł się dla określonych kont bankowych. Należy zauważyć, że użytkownik importujący plik wyciągów bankowych musi mieć dostęp do firmy będącej posiadaczem kont bankowych, których wyciągi chce zaimportować. 

Można użyć pliku .zip i przekazać wiele plików wyciągów do programu Finance and Operations w jednym procesie. Aby zaimportować wiele plików wyciągów bankowych dla wielu kont, należy połączyć wszystkie pliki wyciągów bankowych w jeden plik zip. W oknie dialogowym **Import wyciągów bankowych** w opcji **Importuj wyciąg obejmujący wiele kont bankowych we wszystkich firmach** ustaw wartość **Tak**. Kliknij przycisk **Przeglądaj**, zaznacz plik zip zawierający pliki wyciągów bankowych i kliknij przycisk **Przekaż**. Proces importu rozpozna plik .zip i przekaże każdy znajdujący się w nim wyciąg, niezależnie od firmy będącej posiadaczem konta bankowego. 

Dostępna jest opcja **Uzgodnij po imporcie**. Gdy ta opcja ma ustawioną wartość **Tak**, w trakcie przekazywania wyciągu bankowego system automatycznie sprawdza poprawność wyciągu, tworzy nowe uzgodnienie konta bankowego i arkusz oraz uruchamia domyślny zestaw reguł uzgadniania. Ta funkcja automatyzuje proces aż do momentu, gdy transakcje trzeba uzgodnić ręcznie.

## <a name="validate-the-bank-statement"></a>Sprawdzanie poprawności wyciągu bankowego
Aby sprawdzić poprawność wyciągu, na stronie **Wyciągi bankowe** kliknij przycisk **Sprawdź poprawność**. Aby można było uzgodnić wyciągi bankowe, muszą zostać najpierw zweryfikowane. Ten krok jest wykonywany automatycznie, jeśli podczas importu opcja **Uzgodnij po imporcie** ma wartość **Tak**. 

Sprawdzanie poprawności wyciągu bankowego weryfikuje, czy:

-   Wyciąg bankowy pasuje do wybranego konta bankowego.
-   Waluta wyciągu bankowego pasuje do waluty konta bankowego.
-   Saldo otwarcia na wyciągu jest równe saldu zamknięcia na poprzednim wyciągu z tego konta bankowego.
-   Data nie pokrywa się z datą innego wyciągu bankowego dla tego samego konta bankowego.
-   Nie ma przerw w datach między kolejnymi wyciągami z tego konta bankowego.
-   Daty w wierszach wyciągu bankowego mieszczą się między datami początkowymi i końcowymi wyciągu.
-   Saldo otwarcia i suma kwot w wierszach są równe saldu końcowemu.

Po zakończeniu sprawdzania poprawności stan wyciągu bankowego jest aktualizowany na **Zweryfikowano**. Aby można było uzgodnić wyciąg bankowy, musi on zostać najpierw zweryfikowany.

## <a name="reconcile-the-bank-statement"></a>Uzgadnianie wyciągu bankowego
Po zaimportowaniu elektronicznego wyciągu bankowego i sprawdzeniu jego poprawności na stronie **Wyciągi bankowe** można uzgodnić wyciąg, używając do tego stron **Uzgadnianie konta bankowego** i **Arkusz uzgadniania konta bankowego** stron. 

Na stronie **Uzgadnianie konta bankowego** kliknij przycisk **Nowy**, aby utworzyć nowe uzgodnienie, a następnie zaznacz konto bankowe zaimportowanego wyciągu. Konto bankowe może mieć tylko jedno otwarte uzgodnienie. Data graniczna określa transakcje wyciągu bankowego i transakcje bankowe programu Operations, które są uwzględnione w arkuszu uzgadniania. Domyślnie datą graniczną jest bieżąca data systemowa, ale można zmienić datę uzgodnienia. Pozostałe informacje nagłówka są automatycznie pobierane z wyciągu. Ten krok jest wykonywany automatycznie, jeśli podczas importu opcja **Uzgodnij po imporcie** ma wartość **Tak**. 

Na stronie **Uzgadnianie konta bankowego** kliknij opcję **Arkusz**, aby otworzyć stronę **Arkusz uzgadniania konta bankowego**. Jeśli w opcji **Uzgodnij po imporcie** była ustawiona opcja **Tak**, dla uzgadniania jest uruchamiany domyślny zestaw reguł uzgadniania. Aby ręcznie uruchomić reguły uzgadniania, kliknij opcję **Uruchom reguły uzgadniania** i wybierz zestaw reguł uzgadniania lub indywidualne reguły uzgadniania, których chcesz użyć dla transakcji bankowych. Jeśli masz wiele transakcji do przetworzenia, możesz wykonać ten krok jako proces wsadowy. 

Strona **Arkusz uzgadniania konta bankowego** zawiera cztery siatki z transakcjami. Dwie górne siatki pokazują transakcje z wyciągu bankowego i programu Operations, które jeszcze nie zostały uzgodnione. Dwie niższe siatki pokazują uzgodnione transakcje. Na karcie **Szczegóły transakcji wyciągu bankowego** są wyświetlane szczegóły nieuzgodnionej transakcji wyciągu bankowego zaznaczonej w górnej siatce. 

Istnieją trzy sposoby uzgadniania transakcji figurujących na wyciągach bankowych:

-   Uzgadnianie transakcji z transakcjami bankowymi w programie Operations.
-   Uzgadnianie transakcji z transakcją stornującą na wyciągu bankowym.
-   Oznaczanie transakcji jako **Nowa**, tak aby można je było zaksięgować później jako transakcje bankowe w programie Finance and Operations.

Aby ręcznie uzgodnić transakcje, zaznacz transakcje w siatce **Transakcje z wyciągu bankowego**, zaznacz odpowiadające im transakcje w siatce **Transakcje bankowe w rozwiązaniu Operations**, a następnie kliknij przycisk **Uzgodnij**. Zaznaczone transakcje zostaną przeniesione z górnych siatek nieuzgodnionych transakcji do dolnych siatek uzgodnionych transakcji. Ponadto łączne kwoty uzgodnionych i nieuzgodnionych transakcji zostaną zaktualizowane. Można mieć uzgodnienia transakcji jeden-do-jednego, wiele-do-jednego i wiele-do-wielu. Uzgodnienia muszą przestrzegać reguł dozwolonych różnic między datami i mapowania typów transakcji. Te reguły ustawia się stronie **Parametry modułu Zarządzanie gotówką i bankami**.

W uzgodnieniu mogą wystąpić różnice groszowe. Można uzgodnić jedną transakcję na wyciągu bankowym z jedną transakcją w programie Operations, gdy transakcje te mają różnice groszowe, ale różnice muszą się mieścić w granicach kwoty tolerancji zdefiniowanej w polu **Dopuszczalna różnica groszowa** na wyciągu bankowym. Kwota jest wyświetlana w polu **Kwota korekty** w uzgodnionej transakcji bankowej w programie Operations. Gdy konto bankowe jest oznaczone jako uzgodnione, korekty są księgowane automatycznie za pomocą konta głównego zdefiniowanego w powiązanym typie transakcji bankowej. Korekty nie są obsługiwane dla typów dokumentów **Czek** i **Wpłata**. 

Storna transakcji na wyciągach bankowych są uzgadniane za pomocą arkusza uzgadniania. Można uzgodnić dwa wiersze wyciągu, jeśli kwoty są przeciwne, a jedna z transakcji jest oznaczona jako wycofanie (storno). Można także skonfigurować regułę uzgadniania dla operacji **Wyczyść wycofane wiersze wyciągu**.

Wycofane transakcje bankowe w programie Operations muszą być uzgadniane za pomocą strony **Transakcje bankowe w rozwiązaniu Operations**. Można uzgodnić między sobą dwie transakcje bankowe programu Operations, jeżeli dokumenty mają to samo konto bankowe, typ dokumentu i odwołanie do płatności, a przeciwne kwoty. Można również uzgodnić jeden anulowany czek, aby zapobiec wyszczególnianiu tych transakcje w arkuszu uzgadniania. 

Jeżeli istnieją nowe transakcje inicjowane przez bank, dotyczące np. odsetek i opłat, których jeszcze nie ma w programie Finance and Operations, można dodać je do arkusza skojarzonego z wybranym uzgodnieniem konta bankowego. Wybierz nieuzgodnioną transakcję wyciągu bankowego w siatce **Transakcje z wyciągu bankowego** i kliknij przycisk **Oznacz jako nowe**. Stan transakcji zostanie ustawiony na **Nowy**, a transakcja zostanie przeniesiona do siatki **Transakcje z wyciągu bankowego** uzgodnionych transakcji. Transakcje oznaczone jako **Nowy** zaksięgujesz później, na stronie **Wyciąg bankowy**. 

Można anulować uzgodnienie błędnie uzgodnionych transakcji. Zaznacz uzgodnioną transakcję wyciągu bankowego i kliknij przycisk **Usuń uzgodnienie**. Wszystkie powiązane transakcje zostaną przeniesione z powrotem do górnych siatek nieuzgodnionych transakcji oraz nastąpi aktualizacja łącznych kwot transakcji uzgodnionych i nieuzgodnionych. 

Po ukończeniu procesu uzgadniania należy oznaczyć arkusz uzgadniania konta bankowego jako uzgodniony.  Ten proces automatycznie zaksięguje kwoty korekty przy użyciu kont ustawionych na stronie **Typ transakcji bankowej**.  Uzgodnienie bankowe wyciągu można oznaczyć jako uzgodnione w dowolnej chwili, nawet jeżeli istnieją wiersze wyciągu bankowego, które nie zostały jeszcze uzgodnione.  Nieuzgodnione transakcje zostaną automatycznie przeniesione do następnego arkusza uzgadniania jako nieuzgodnione transakcje wyciągu bankowego do uzgodnienia.  Należy pamiętać, że po oznaczeniu uzgodnienia wyciągu bankowego jako uzgodnionego nie można tego cofnąć.  Nie będzie można edytować uzgodnienia i nie będzie możliwości aktualizowania uzgodnienia.

## <a name="post-new-transactions-that-are-associated-with-the-reconciliation"></a>Księgowanie nowych transakcji skojarzonych z uzgodnieniem
Transakcje na wyciągu bankowym, które w arkuszu uzgadniania zostały oznaczone jako **Nowy**, są księgowane na stronie **Wyciąg bankowy**. Na stronie **Wyciąg bankowy** zaznacz identyfikator wyciągu, aby wyświetlić szczegóły wyciągu. W menu **Księgowanie** można użyć opcji **Wyświetl dystrybucje** i **Wyświetl księgowanie**, aby wyświetlić szczegóły stojące za nowymi transakcjami i powiązanymi zapisami księgi. Zaznacz opcję **Księguj**, aby w księdze głównej księgować wiersze wyciągu bankowego oznaczone jako **Nowy**. Należy pamiętać, że księgowanie można wykonać tylko raz dla każdego wyciągu bankowego.




