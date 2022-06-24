---
title: Korygowanie wynajmów
description: W artykule wyjaśniono sposób korygowania wynajmu. Korekta może być wymagana w przypadku zmodyfikowania warunków wynajmu, wydłużenia wynajmu lub zmiany innych okoliczności.
author: moaamer
ms.date: 03/18/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 48d1a261a43d6e3a68dfc0aae6f06c0d7d6b82db
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8898335"
---
# <a name="adjust-leases"></a>Korygowanie wynajmów

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

W artykule wyjaśniono sposób korygowania wynajmu. Korekta może być wymagana w przypadku zmodyfikowania warunków wynajmu, wydłużenia wynajmu lub zmiany innych okoliczności. Wynajem składników majątku jest zgodny z przepisami Accounting Standards Codification Topic 842 (ASC 842) i International Financial Reporting Standard 16 (IFRS 16) dotyczącymi korekt wynajmów. ASC 842-20-15-1 definiuje modyfikację wynajmu jako dowolną zmianę postanowień umowy, która powoduje zmianę zakresu wynajmu lub uwag do niego. Akapit 39 IFRS 16 wskazuje, że najemca musi zmienić wartość zobowiązania z tytułu wynajmu, tak aby odzwierciedlała ona zmiany w opłatach z tytułu wynajmu.

W przypadku organizacji, które stosują się do ASC 842 lub IFRS 16, wynajem jest zmieniany w celu odzwierciedlenia zmiany bieżącej wartości przyszłych opłat z tytułu wynajmu (PVFMLP). Jeśli PVFMLP wzrośnie, utworzony wpis w arkuszu dla różnicy między nowym PVFMLP a poprzednim PVFMLP będzie debetowy w składniku majątku konta z PDU i kredytowy w zobowiązaniu z tytułu wynajmu. Jeśli PVFMLP zmniejszy się, wpis w arkuszu dla tej różnicy będzie debetowy w zobowiązaniu z tytułu wynajmu konta oraz kredytowy w składniku majątku kota z PDU.

Jeśli korekta spowoduje obniżenie wartości składnika majątku z PDU poniżej 0 (zera), reszta zostanie zaksięgowana po stronie kredytowej na koncie księgowania modyfikacji zysku z wynajmu, który jest określony na stronie **Konta księgowania wynajmów**. Konta systemowe dla tych transakcji i innych wpisów korekty, takich jak zmiany klasyfikacji, początkowe koszty bezpośrednie, prowizje stymulujące wynajem, przedpłaty czy koszty demontażu powstające w wyniku modyfikacji wynajmu.

Aby uzyskać szczegółowe wskazówki dotyczące transakcji korekty wynajmu, zaleca się zapoznanie się z IFRS 16 i ASC 842.

## <a name="lease-adjustment-wizard"></a>Kreator korekty wynajmu

Aby dostosować wynajem, wykonaj następujące kroki. Zmodyfikowane dane zaktualizują harmonogramy dzierżawy po zaksięgowaniu za pomocą kreatora **Korekta wynajmu**. Możesz zapisać swoją pracę i zamknąć kreatora w dowolnym momencie, a następnie wrócić później, aby wznowić pracę.

Aby otworzyć kreatora **Korekta wynajmu** z podsumowania wynajmu, należy wykonać następujące kroki.

1. Przejdź do **Wynajem składnika majątku \> Wynajmy \> Podsumowanie wynajmu**. 
2. Wybierz wynajem do skorygowania, a następnie wybierz **Kreatora korekt**.
3. Postępuj zgodnie z monitami w kreatorze, aby wprowadzić wymagane zmiany.

Aby otworzyć kreatora **Korekta wynajmu** ze strony **Korekty wynajmu**, dla korekty, która jest już w toku, wykonaj następujące kroki.

1.  Przejdź do **Wynajem \> Wynajem \> Korekty wynajmu**.
2.  Wybierz wynajem o stanie korekty **W toku**, a następnie wybierz **Kreatora korekt**.
3.  W polach **Data rozpoczęcia modyfikacji** i **Data księgowania** wprowadź odpowiednie daty.
4.  Wybierz pozycję **Następny**.

    Dzierżawa zostanie dodana do strony **Korekty wynajmu**, na której możesz wprowadzić nowe informacje na jej temat.

    Po dostosowaniu wynajmu mają do niego zastosowanie pola dotyczące prawa do użytkowania. Jeśli ze zmodyfikowanym wynajmem nie są powiązane koszty bezpośrednie, prowizje stymulujące wynajem, przedpłaty lub koszty demontażu, należy pozostawić odpowiednie pola puste. Oryginalne kwoty nie będą stosowane do zaktualizowanego wynajmu. 

    Na przykład najmodawca oferuje 1000 dolarów prowizji stymulującej wynajem za przedłużenie wynajmu. W takim przypadku podczas korygowania wynajmu, aby uwzględnić to przedłużenie, wprowadź **1000** w polu **Prowizje stymulujące wynajem wynikające z korekty**.

    W wierszach harmonogramu płatności są teraz wyświetlane wszystkie płatności z miesiąca i późniejszych miesięcy, w polu **Data rozpoczęcia modyfikacji**. Ponieważ modyfikacje są potencjalne, wiersze harmonogramu płatności nie mogą rozpocząć się przed rozpoczęciem modyfikacji. Aby wyświetlić wiersze harmonogramu płatności przed datą rozpoczęcia modyfikacji, przejdź na stronę **Historia wersji wynajmu**.

8.  Wybierz pozycję **Następny**.

    Na następnej stronie przedstawiono kluczowe szczegóły dotyczące oczekiwanej korekty z tytułu leasingu, takie jak wartość bilansowa zobowiązania z tytułu leasingu przed modyfikacją oraz nowe oczekiwane zobowiązanie z tytułu leasingu po modyfikacji. Strona zawiera również podgląd zapisu księgowego dla oczekiwanej korekty wynajmu.

9.  Wybierz opcję **Prześlij do przepływu pracy**, aby przesłać korektę wynajmu do systemu przepływu pracy, jeśli przepływ pracy korekty wynajmu jest aktywny, a korekta nie została jeszcze zatwierdzona. Aby uzyskać więcej informacji o używaniu przepływu pracy korekty wynajmu, zobacz [Używanie przepływów pracy korekt wynajmów](use-create-lease-wrkflw.md).

    > [!NOTE]
    > Na tym etapie system ponownie oblicza zmienne korekty, aby sprawdzić, czy żadne transakcje nie zostały zaksięgowane w odniesieniu do wynajmu od czasu pierwszego obliczenia przeglądu korekt i zapisu księgowego korekty. Jeśli jakiekolwiek wartości ulegną zmianie, siatka przeglądu korekt zostanie zaktualizowana i można przejrzeć informacje przed ponownym przesłaniem korekt wynajmu do systemu przepływu pracy.

10. Jeśli przepływ pracy jest nieaktywna lub jeśli korekta wynajmu została zatwierdzona, wybierz przycisk **Zakończ**, aby przetworzyć zmiany i zaksięgować wpis w arkuszu korekt.

    > [!NOTE] 
    > Na tym etapie system ponownie oblicza zmienne korekty, aby sprawdzić, czy żadne transakcje nie zostały zaksięgowane w odniesieniu do wynajmu od czasu pierwszego obliczenia przeglądu korekt i zapisu księgowego korekty. Jeśli jakieś wartości się zmienią, siatka przeglądu korekt zostanie zaktualizowana i będzie można przejrzeć zmiany przed wybraniem opcji **Zakończ**. Jeśli przepływ pracy jest aktywny, a korekta wynajmu została zatwierdzona, wszelkie zmiany przeglądu korekt powodują ustawienie stanu zatwierdzenia na **Nie przesłane**. W takim przypadku należy ponownie przesłać korektę wynajmu do systemu przepływu pracy.

    Na stronie **Korekty wynajmu** stan korekty jest teraz ustawiany na **Zakończono**.

    Na stronie **Korekty wynajmu** nadal można wyświetlić skrócone karty **Przegląd korekty** i **Podgląd wpisu korekty**. Szczegóły wynajmu oraz informacje o dacie są wyświetlane w historii wersji wynajmu.

    Nowa wersja wynajmu i nowy zestaw harmonogramów są tworzone na podstawie zmodyfikowanych informacji. 

13. Aby wyświetlić nowe harmonogramy, przejdź do wynajmu, a następnie wybierz pozycję **Księgi**.
14. Aby wyświetlić nowo wygenerowany harmonogram płatności, wybierz opcję **Harmonogram płatności**.
15. Aby wyświetlić nowy harmonogram zobowiązań z tytułu leasingu finansowego generowany na podstawie nowych informacji, zamknij stronę **Harmonogram płatności** i otwórz stronę **Harmonogram amortyzacji zobowiązań**.
16. Aby wyświetlić nowo wygenerowany harmonogram amortyzacji środków trwałych, otwórz stronę **Harmonogram amortyzacji składników majątku** na stronie **Szczegóły księgi**.
17. Aby wyświetlić wpis w arkuszu korekty, należy wybrać **Arkusze \> Arkusz wynajmu składnika majątku**.

## <a name="cancel-a-lease-adjustment"></a>Anulowanie korekty wynajmu

Aby usunąć trwającą korektę wynajmu, wykonaj następujące kroki.

1.  Przejdź do **Wynajem \> Wynajem \> Korekty wynajmu**.
2.  Wybierz korektę wynajmu w toku do anulowania.
3.  Wybierz przycisk **Anuluj korektę**. 
4.  Kliknij przycisk **OK**.

    > [!NOTE] 
    > Jeśli wybierzesz opcję **Anuluj** w kreatorze **Korekt wynajmu**, wycofasz ostatnią zmianę ukończoną w kreatorze, ale nie usuniesz korekty, która jest w toku.

## <a name="use-the-lease-adjustment-workflow"></a>Użyj przepływu pracy korekty wynajmu

W tej sekcji opisano sposób używania przepływu pracy korekty wynajmu. Przepływ pracy korekty wynajmu pomaga spójnie zarządzać korektami wynajmu, dostarczając zestaw kroków zatwierdzania i przypisując je określonym użytkownikom, którzy zatwierdzają korektę wynajmu, zanim stanie się ona ostateczna. Po zatwierdzeniu korekty wynajmu w przepływie pracy można użyć **Kreatora korekt wynajmu** w celu ukończenia korekty wynajmu.

1.  Aby przesłać korektę wynajmu do zatwierdzenia, przejdź do ustawień **Wynajem \> Wynajem \> Korekty wynajmu**.
2.  Wybierz identyfikator dzierżawy korekty wynajmu, a następnie wybierz **Kreatora korekt**.
3.  Na ostatniej stronie kreatora wybierz pozycję **Prześlij do zatwierdzenia**.
4.  Wprowadź komentarz na temat korekty, a następnie wybierz przycisk **OK**.

    Stan przepływu pracy zmienia się na **Oczekujące na zatwierdzenie**, a wszystkie pola w kreatorze są zablokowane do edycji.

5.  Aby zatwierdzić korektę wynajmu, przejdź do ustawień **Wynajem \> Wynajem \> Korekty wynajmu**.
6.  Wybierz identyfikator dzierżawy korekty wynajmu i wyświetlić skrócone karty **Przegląd korekty** i **Podgląd wpisu korekty**.
7.  Wybierz **Przepływ pracy \> Zatwierdzona**.

    Na stronie **Korekty wynajmu** stan przepływu pracy jest teraz ustawiany na **Zatwierdzona**. W tym momencie korekta wynajmu jest gotowa do zaksięgowania za pośrednictwem wpisu w arkuszu korekt.

8.  Aby kontynuować przetwarzanie korekty wynajmu i księguj wpis korekty, przejdź do pozycji **Wynajm \> Wynajm \> Korekty wynajmu**.
9.  Wybierz identyfikator dzierżawy korekty wynajmu, a następnie wybierz **Kreatora korekt**.
10. Wybierz przycisk **Dalej**, dopóki nie osiągniesz ostatniej strony kreatora, a następnie wybierz przycisk **Zakończ**.

System ponownie obliczy wartości bilansowania wynajmu, aby upewnić się, że zatwierdzone zmienne korekty są aktualne. W przypadku zmian stan zatwierdzenia jest ustawiany z powrotem na **Wersja robocza** i należy ponownie przesłać korektę wynajmu do systemu przepływu pracy.

## <a name="view-lease-versions"></a>Przeglądanie wersji wynajmu

Jeśli wynajem został dostosowany, można wyświetlić jego różne wersje. Można również wyświetlić harmonogramy historyczne i szczegóły dotyczące przeszłych wynajmów.

1. Na stronie **Podsumowanie wynajmu** wybierz wynajem do skopiowania, a następnie w okienku akcji wybierz opcję **Historia wersji wynajmu**.

    Jeśli wybrany wynajem został skorygowany, na stronie **Historia wersji wynajmu** zostaną wyświetlone jego różne wersje. Pierwotny wynajem jest oznaczony jako **1**, a kolejne wersje mają rosnącą kolejność liczbową.

    W przypadku wybranej wersji wynajmu można wyświetlić wymiary finansowe, szczegóły umowy, lokalizację i wiersze harmonogramu płatności.

2. Aby wyświetlić harmonogramy historyczne, otwórz zmodyfikowany wynajem na stronie **Podsumowanie wynajmu**, wybierz żądaną księgę, a następnie w okienku akcji wybierz opcję **Historia wersji księgi**.
3. Na stronie **Wersja księgi** wybierz wersję i harmonogram do wyświetlenia.

## <a name="adjust-a-lease-book"></a>Korygowanie księgi wynajmu

Wykonaj poniższe kroki, aby dostosować tylko księgę wynajmu.

1. Przejdź do **Wynajem składnika majątku** \> **Wynajmy** \> **Podsumowanie wynajmu**.
2. Wybierz i otwórz wynajem.
3. Na stronie **Szczegóły wynajmu** wybierz pozycję **Księgi**.
4. W Okienku akcji na karcie **Szczegóły księgi** w grupie **Obsługa** wybierz **Dostosuj księgę**. 
5. Usuń wiersze harmonogramu płatności.
6. W polu **Data modyfikacji wynajmu** wpisz datę modyfikacji. Następnie rozważ usunięcie wszystkich dodatkowych czynników związanych z aktywami/pasywami (początkowy koszt bezpośredni, zachęta do wynajmu, przedpłata, koszt demontażu i gwarancja wartości końcowej), jeśli takie istnieją. 
7. Aby uniknąć niedokładnych obliczeń korekty wynajmu, dodaj nowe wiersze harmonogramu płatności dla nowych dat płatności, które odpowiadają dacie modyfikacji. 

> [!NOTE] 
> Zalecamy, abyś do dostosowania wynajmu użył kreatora **Korekta leasingu**. Kreator zmniejsza liczbę kroków wykonywanych ręcznie, daje podgląd sald po korekcie i pozwala zmienić kwoty przed zaksięgowaniem.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
