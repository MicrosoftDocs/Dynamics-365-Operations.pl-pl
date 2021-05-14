---
title: Obsługa funkcji podatków dla zamówień przeniesienia
description: W tym temacie wyjaśniono, że nowa funkcja podatków obsługuje zamówienia przeniesienia, używając usługi obliczania podatku.
author: kailiang
ms.date: 04/20/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: d1b99046b0e439c9dadbb240050e270a7b2a6914
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/20/2021
ms.locfileid: "5920962"
---
# <a name="tax-feature-support-for-transfer-orders"></a>Obsługa funkcji podatków dla zamówień przeniesienia

[!include [banner](../../includes/banner.md)]

Ten temat zawiera informacje dotyczące obliczania podatku i księgowania integracji w zamówieniach przeniesienia. Ta funkcja umożliwia konfigurowanie obliczania podatku i księgowania w zamówieniach przeniesienia dla przeniesień zapasów. Zgodnie z obowiązującymi w Unii Europejskiej (UE) przepisami dotyczącymi podatku od wartości dodanej przeniesienia zapasów są traktowane jako wewnątrzunijne oraz wewnątrzunijne nabycia.

Aby skonfigurować i korzystać z tej funkcji, musisz wykonać trzy główne kroki:

1. **Ustawienia usługi RCS:** W usłudze konfiguracji wymogów prawnych skonfiguruj funkcję podatków, kody podatków i kody podatków, które mogą być aplikacyjne do określania kodów podatków w zamówieniach przeniesienia.
2. **Ustawienia finansów:** W firmie Microsoft Dynamics 365 Finance włącz funkcję **Podatek w zamówieniu przeniesienia**, skonfiguruj parametry usługi podatkowej dla zapasów i skonfiguruj podstawowe parametry podatku.
3. **Konfiguracja zapasów:** konfigurowanie konfiguracji zapasów dla transakcji zamówienia przeniesienia.

## <a name="set-up-rcs-for-tax-and-transfer-order-transactions"></a>Konfigurowanie RCS dla transakcji zamówień podatku i przeniesienia

Aby skonfigurować podatek związany z zamówieniem przeniesienia, należy wykonać następujące kroki. W przykładzie, który zostanie pokazany, zamówienie przeniesienia jest z Holandii do Belgii.

1. Na stronie **Funkcje podatkowe** na karcie **Wersje** wybierz wersję roboczą funkcji, a następnie wybierz pozycję **Edytuj**.

    ![Wybieranie edycji](../media/image1.png)

2. Na stronie **Ustawienia funkcji podatków**, na karcie **Kody podatków** wybierz opcję **Dodaj**, aby utworzyć nowe kody podatków. W tym przykładzie tworzone są trzy kody podatków:**NL-Exempt**, **BE-RC-21** i **BE-RC+21**.

    - Gdy zamówienie przeniesienia jest wysyłane z magazynu w Holandii, stosowany jest holenderski kod zwolnienia z podatku VAT (**NL-Exempt**).
      
        Utwórz kod podatku **NL-Exempt**.
        1. Wybierz opcję **Dodaj** i wprowadź numer **NL-Exempt** w polu **Kod podatku**.
        2. Wybierz **Według kwoty netto** w polu **Składnik podatku**.
        3. Wybierz opcję **Zapisz**.
        4. Na karcie **Stawka** wybierz **Dodaj**.
        5. Przełącz **Jest zwolniony** na **Tak** w sekcji **Ogólne**.

        ![Kod zwolnienia z podatku (NL)](../media/image2.png)

    - Gdy zamówienie przeniesienia zostanie odebrane w magazynie belgijskim, mechanizm opłaty zwrotnej jest stosowany przy użyciu kodów podatków **BE-RC-21** i **BE-RC+21**.
        
        Utwórz kod podatku **BE-RC-21**.      
        1. Wybierz opcję **Dodaj** i wprowadź numer **BE-RC-21** w polu **Kod podatku**.
        2. Wybierz **Według kwoty netto** w polu **Składnik podatku**.
        3. Wybierz opcję **Zapisz**.
        4. Na karcie **Stawka** wybierz **Dodaj**.
        5. Wprowadź **-21** w polu **Stawka podatku**.
        6. Czy swtich **Wsteczna opłata** z **Tak** w sekcji **Ogólne**.
        7. Wybierz opcję **Zapisz**.

        ![Kod podatku BE-RC-21 dla opłat zwrotnych](../media/image3.png)
        
        Utwórz kod podatku **BE-RC+21**.
        1. Wybierz opcję **Dodaj** i wprowadź numer **BE-RC-21** w polu **Kod podatku**.
        2. Wybierz **Według kwoty netto** w polu **Składnik podatku**.
        3. Wybierz opcję **Zapisz**.
        4. Na karcie **Stawka** wybierz **Dodaj**.
        5. Wprowadź **21** w polu **Stawka podatku**.
        6. Wybierz opcję **Zapisz**.

        ![Kod podatku BE-RC+21 dla opłat zwrotnych](../media/image4.png)

3. Zdefiniuj możliwości zastosowania kodów podatków.

    1. Wybierz opcję **Zarządzaj kolumnami**, a następnie wybierz kolumny, które mają być używane do tworzenia tabeli możliwości zastosowania.

        > [!NOTE]
        > Pamiętaj, aby dodać do tabeli kolumny **Proces biznesowy** i **Kierunki podatków**. Obie kolumny są niezbędne do funkcjonalności podatku w zamówieniach przeniesienia.

    2. Dodaj Reguły zastosowania. Nie pozostaw pustych pól **Kody podatków**, **Grupa podatków** i **Grupa podatków dla pozycji**.
        
        Dodaj nową regułę wysyłki zamówienia przeniesienia.
        1. Na karcie **Stawka** wybierz tabelę **Reguły stosowania**.
        2. W polu **Proces biznesowy** wybierz pozycję **Zapasy**, aby reguła obowiązywała dla zamówienia przeniesienia.
        3. W polu **Kraj/region wysyłki** wprowadź nazwę **NLD**.
        4. W polu **Kraj/region wysyłki** wprowadź nazwę **BEL**.
        5. W polu **Kierunek podatku** wybierz opcję **Dane wyjściowe**, aby reguła obowiązywała dla wysyłki zamówienia przeniesienia.
        6. W polu **Kod podatku** wybierz opcję **NL-Exempt**.
        7. W polach **Grupa podatków** i **Grupa podatków dla pozycji** wprowadź powiązaną grupę podatków i grupę podatków dla towaru zdefiniowaną w systemie Finance.
        
        Dodaj kolejną regułę dotyczącą potwierdzenia przelewu.
        1. Na karcie **Stawka** wybierz tabelę **Reguły stosowania**.
        2. W polu **Proces biznesowy** wybierz pozycję **Zapasy**, aby reguła obowiązywała dla zamówienia przeniesienia.
        3. W polu **Kraj/region wysyłki** wprowadź nazwę **NLD**.
        4. W polu **Kraj/region wysyłki** wprowadź nazwę **BEL**.
        5. W polu **Kierunek podatku** wybierz opcję **Wejście**, aby reguła obowiązywała dla odbioru zamówienia przeniesienia.
        6. W polu **Kody podatków** wybierz **BE-RC+21** i **BE-RC-21**.
        7. W polach **Grupa podatków** i **Grupa podatków dla pozycji** wprowadź powiązaną grupę podatków i grupę podatków dla towaru zdefiniowaną w systemie Finance.

        ![Reguły zastosowania](../media/image5.png)

4. Ukończ i opublikuj nową wersję funkcji podatkowej.

    [![Zmiana statusu nowej wersji](../media/image6.png)](../media/image6.png)

## <a name="set-up-finance-for-transfer-order-transactions"></a>Konfigurowanie Finance dla transakcji zamówień podatku i przeniesienia

Wykonaj poniższe czynności, aby włączyć i skonfigurować podatki dla zleceń przelewów.

1. W Finance kliknij kolejno opcje **Obszary robocze** \> **Zarządzanie danymi**.
2. Na liście znajdź i wybierz funkcję **Podatek w zamówieniu przeniesienia**, a następnie wybierz opcję **Włącz teraz**, aby ją włączyć.

    > [!IMPORTANT]
    > Funkcja **Podatek w zamówieniu przeniesienia** jest w pełni zależna od usługi podatkowej. Dlatego można ją włączona tylko po zainstalowaniu usługi podatkowej.

    ![Podatek funkcji zamówienia przeniesienia](../media/image7.png)

3. Włącz usługę podatkową i wybierz proces biznesowy **Zapasy**.

    > [!IMPORTANT]
    > Ten krok należy wykonać dla każdej firmy w oknie Finance, gdzie ma być dostępna usługa podatkowa i funkcja podatku w zamówieniach przeniesienia.

    1. przejdź do **Podatek** \> **Ustawienia** \> **Konfiguracja podatku** \> **Konfiguracja usług podatkowych**.
    2. W polu **Proces biznesowy** wybierz pozycję **Zapasy**.

    ![Ustawianie pola Proces biznesowy](../media/image8.png)

4. Sprawdź, czy jest ustawiony mechanizm opłaty zwrotnej. Przejdź do **Księga główna** \> **Ustawienia** \> **Parametry**, a następnie na karcie **Opłata zwrotna** sprawdź, czy opcja **Włącz opłatę zwrotną** ma wartość **Tak**.

    ![Włącz opcję opłaty zwrotnej](../media/image9.png)

5. Sprawdź, czy powiązane kody podatków, grupy podatków, grupy podatków dla pozycji i numery rejestracji VAT zostały ustawione w finansach zgodnie z wytycznymi usługi podatkowej.
6. Konfigurowanie tymczasowego konta tranzytowego. Ten krok jest wymagany tylko w przypadku, gdy podatek zastosowany do zamówienia przeniesienia nie ma zastosowania do mechanizmu zwolnienia z podatku lub opłaty zwrotnej.

    1. Wybierz kolejno opcje **Podatek** \> **Ustawienia** \> **Podatek** \> **Grupy księgowania**.
    2. W polu **Tranzyt tymczasowy** wybierz konto księgowe.

    ![Konfigurowanie tymczasowego konta tranzytowego](../media/image10.png)

## <a name="set-up-basic-inventory-for-transfer-order-transactions"></a>Konfigurowanie Finance dla transakcji zamówień podatku i przeniesienia

Aby włączyć transakcje zamówień przeniesienia, należy wykonać następujące czynności, aby skonfigurować magazyn podstawowy.

1. Należy utworzyć miejsca wysyłki i wysyłki dla magazynów w różnych krajach lub regionach, a następnie dodać adres podstawowy dla poszczególnych lokalizacji.

    1. Wybierz kolejno opcje **Zarządzanie magazynem** \> **Ustawienia** \> **Magazyn** \> **Lokalizacja**.
    2. Wybierz **opcję Nowy**, aby utworzyć witrynę, która zostanie później przypisana do magazynu.
    3. Powtórz krok 2 dla wszystkich innych witryn, które musisz utworzyć.

    > [!NOTE]
    > Jedno z tworzyć witryn powinno mieć nazwę **Tranzyt**. W kolejnych krokach tej procedury należy przypisać ten obiekt do magazynu tranzytowego, aby załączniki magazynowe powiązane z podatkami można było księgować w transakcjach „wyślij” i „odbierz” dla zamówień przeniesienia. Adres miejsca tranzytowego nie ma znaczenia w obliczeniach podatku. Dlatego możesz zostawić to pole puste.

    ![Konfigurowanie lokalizacji](../media/image11.png)

2. Umożliwia tworzenie magazynów miejsc wysyłki, tranzytu i wysyłki do. Wszystkie informacje adresowe zachowywane w magazynie zastępują adres lokalizacji podczas obliczania podatku.

    1. Wybierz kolejno opcje **Zarządzanie magazynem** \> **Ustawienia** \> **Magazyn** \> **Magazyny**.
    2. Wybierz **opcję Nowy**, aby utworzyć witrynę, która zostanie później przypisana do magazynu.
    3. Powtórz krok 2, aby utworzyć magazyn dla każdego wymaganego magazynu.

    ![Ustawianie magazynów](../media/image12.png)

    > [!NOTE]
    > W przypadku magazynu wysyłki z transakcji zamówienia przeniesienia w polu **Magazyn tranzytowy** musi być wybrany magazyn tranzytowy.
    >
    > ![Wybieranie magazynu tranzytowego](../media/image13.png)

3. Sprawdź, czy konfiguracja księgowania zapasów jest skonfigurowana dla transakcji zlecenia przeniesienia.

    1. Przejdź do **Zarządzanie zapasami** \> **Konfiguracja** \> **Księgowanie** \> **Księgowanie**.
    2. Na karcie **Zapasy** sprawdź, czy konto księgowe jest ustawione zarówno dla księgowania **wydania z magazynu**, jak i księgowania **przyjęcia na magazyn**.

        ![Konfigurowanie księgowania wydania z magazynu i przyjęcia na magazyn](../media/image14.png)

    3. Sprawdź, czy konto księgowe jest ustawione do księgowania zobowiązań **międzyjednostkowych**.

        ![Konfigurowanie księgowania zobowiązań międzyjednostkowych](../media/image15.png)

    4. Sprawdź, czy konto księgowe jest ustawione do księgowania **Odbiorów między jednostkami**.

        ![Konfigurowanie księgowania rachunków z odbiorami między jednostkami](../media/image16.png)
