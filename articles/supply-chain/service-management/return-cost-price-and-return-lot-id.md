---
title: Koszt własny dla zwrotu i identyfikator partii zwrotu
description: Czasami jest potrzebna sytuacja, aby koszt zwróconych produktów był równy kosztowi produktów w momencie, gdy były sprzedawane odbiorcy. Można to uzyskać za pomocą ustawienia **Identyfikator partii zwrotu**.
author: ShylaThompson
manager: tfehr
ms.date: 04/30/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReturnTableListPage, ReturnInventTransIdLookup, ReturnItemNumLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0d5ac48dd390e2f57a7312e3c54af53dd49fd4f7
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4435315"
---
# <a name="return-cost-price-and-return-lot-id"></a>Koszt własny dla zwrotu i identyfikator partii zwrotu        

[!include [banner](../includes/banner.md)]



Koszt produktów zwracanych do zapasów jest obliczany przy użyciu bieżącego kosztu produktów. Jednak czasami jest potrzebna sytuacja, aby koszt zwróconych produktów był równy kosztowi produktów w momencie, gdy były sprzedawane odbiorcy. Można to uzyskać za pomocą pola **Identyfikator partii zwrotu** znajdującego się na skróconej karcie **Szczegóły wiersza** w formularzu **Zamówienie sprzedaży**.

Na przykład rozważmy następujący scenariusz. Wystawiasz odbiorcy fakturę. Następnie odbiorca zwraca Ci otrzymane produkty. Ty zwracasz produkty do zapasów. W takim przypadku kiedy uznajesz konto odbiorcy za zwrócone produkty, koszt tych produktów jest obliczany przy użyciu bieżącego kosztu produktów. Jednak jeśli użyjesz pola **Identyfikator partii zwrotu**, koszt zwróconych produktów jest obliczany przy użyciu kosztu z faktury za pierwotną sprzedaż do odbiorcy.

Aby do zwrotów od odbiorcy zastosować koszt inny niż bieżący, należy użyć jednej z następujących metod.

## <a name="method-1-manually-enter-the-return-cost-price"></a>Metoda 1: Ręczne wprowadzenie kosztu własnego zwrotu

Domyślnie podczas dodawania towarów do zamówienia zwrotu towary są zwracane do zapasów według bieżącego kosztu własnego. Aby określić inny koszt własny zwrotu, wykonaj następujące kroki:

1.  Kliknij kolejno opcje **Sprzedaż i marketing** \> **Wspólne** \> **Zamówienia zwrotu** \> **Wszystkie zamówienia zwrotu**.

2.  W **okienku akcji** w grupie **Nowy** kliknij opcję **Zamówienie zwrotu**.

3.  W formularzu **Utwórz zamówienie zwrotu** wybierz konto odbiorcy, a następnie kliknij przycisk **OK**.

4.  W formularzu **Zamówienie zwrotu — numer autoryzacji zwrotu: %1, %2** zaznacz towar, a następnie wprowadź ilość ujemną w polu **Ilość**.

5.  Kliknij skróconą kartę **Szczegóły wiersza**.

6.  Na karcie **Ogólne** wprowadź wartość w polu **Koszt własny dla zwrotu**. Ta wartość będzie używana podczas zwracania towarów do zapasów. Jeśli nie wprowadzisz wartości, podczas zwrotu towarów do zapasów będzie używany bieżący koszt własny.

## <a name="method-2-automatically-generate-the-cost-price-based-on-the-customer-invoice-line"></a>Metoda 2: Automatyczne generowanie kosztu własnego na podstawie wiersza faktury dla odbiorcy

Jest to preferowana metoda tworzenia wierszy zwrotu. Aby użyć kosztu produktów z chwili, gdy produkty były sprzedawane odbiorcy, utwórz zamówienie zwrotu i wskaż wiersz sprzedaży do zwrotu.

1.  Kliknij kolejno opcje **Sprzedaż i marketing** \> **Wspólne** \> **Zamówienia zwrotu** \> **Wszystkie zamówienia zwrotu**.

2.  W **okienku akcji** w grupie **Nowy** kliknij opcję **Zamówienie zwrotu**.

3.  W formularzu **Utwórz zamówienie zwrotu** wybierz konto odbiorcy, a następnie kliknij przycisk **OK**.

4.  W formularzu **Zamówienie zwrotu — numer autoryzacji zwrotu: %1, %2** w **okienku akcji** kliknij przycisk **Znajdź zamówienie sprzedaży**.

5.  W formularzu **Znajdź zamówienie sprzedaży** wybierz wiersz faktury, z którego produkty chcesz zwrócić, a następnie kliknij przycisk **OK**.
    
    Na skróconej karcie **Szczegóły wiersza** na karcie **Ogólne** pole **Identyfikator partii zwrotu** pokazuje wartość z oryginalnego wiersza sprzedaży. Ponadto pole **Koszt własny dla zwrotu** zawiera wartość kosztu z oryginalnego wiersza sprzedaży.

## <a name="cost-calculation-example"></a>Przykład obliczania kosztu

Jeżeli do określenia kosztu własnego zwrotu użyjesz pola **Identyfikator partii zwrotu** w wierszu zamówienia zwrotu, zostanie użyty koszt z wiersza zamówienia zwrotu. Po uruchomieniu funkcji zamknięcia lub ponownego obliczania zapasów nastąpi korekta kosztu w oryginalnym wierszu sprzedaży. Koszt w wierszu zamówienia zwrotu zostanie automatycznie skorygowany, aby pokazywać ten sam koszt za sztukę.

1.  Utwórz i zwolnij produkt o nazwie Test. W formularzu **Szczegóły zwolnionego produktu** określ następujące informacje:
    
    1.  Na skróconej karcie **Zarządzanie kosztami** w polu **Grupa pozycji** zaznacz grupę **Części**.
    
    2.  Na skróconej karcie **Ogólne** w polu **Grupa modeli pozycji** zaznacz opcję **DEF**.
    
    3.  Na skróconej karcie **Zakup** w polu **Cena** wpisz wartość 10,00 jako koszt własny towaru.
    
    4.  W **okienku akcji** kliknij pozycję **Grupy wymiarów**. W polu **Grupa wymiarów magazynowania** zaznacz opcję **Tylko oddział i magazyn**. W polu **Grupa wymiarów śledzenia** zaznacz opcję **Brak aktywnych wymiarów śledzenia**.

2.  Utwórz zamówienie zakupu na 10 sztuk towaru Test w cenie 6,00 za sztukę, a następnie zaksięguj fakturę dla zamówienia zakupu.
    
    Utwórz drugie zamówienie zakupu na 10 sztuk towaru Test w cenie 8,00 za sztukę, a następnie zaksięguj fakturę dla zamówienia zakupu.

3.  Zaksięguj fakturę dla zamówienia sprzedaży dotyczącego sprzedaży 5 sztuk towaru Test.
    
    W takim przypadku wiersz zamówienia sprzedaży zostanie wyceniony na 35,00 (5 sztuk \* 7,00 średni koszt za sztukę).

4.  Utwórz zamówienie zwrotu dla odbiorcy. W formularzu **Znajdź zamówienie sprzedaży** wybierz wiersz faktury, a następnie kliknij przycisk **OK**.

5.  W formularzu **Zamówienie zwrotu — numer autoryzacji zwrotu: %1, %2** sprawdź, czy zostało wygenerowane zamówienie zwrotu dotyczące zwrotu towaru Test. Ilość w zamówieniu zwrotu powinna być ustawiona na -5,00.
    
    W polu **Identyfikator partii zwrotu** jest wyświetlany identyfikator partii. Ten identyfikator partii pochodzi z oryginalnego zamówienia sprzedaży na towar sprzedany odbiorcy. Pole **Koszt własny dla zwrotu** zawiera koszt własny z oryginalnego wiersza sprzedaży.

6.  Zarejestruj przyjęcie zwróconych towarów.

7.  Zaksięguj dokument dostawy zwróconych towarów.

8.  Zaksięguj fakturę dla zamówienia zwrotu. Na stronie listy **Wszystkie zamówienia sprzedaży** wybierz zamówienie sprzedaży, dla którego typem zamówienia jest **Zwrot towaru**.

9.  Otwórz formularz **Transakcje magazynowe**. Sprawdź, czy zwrot jest wyceniony na 7,00 za sztukę, oglądając w tym celu wartość w polu **Koszt własny dla zwrotu**, i łącznie 35,00 w polu **Kwota kosztu**. Formularz **Transakcje magazynowe** można otworzyć z poziomu formularza **Zamówienie zwrotu — numer autoryzacji zwrotu: %1, %2**. W siatce **Wiersze** kliknij kolejno opcje **Zapasy** \> **Transakcje**.

10. W module Zarządzanie zapasami i magazynem użyj formularza **Zamknięcie i korekta**, aby wykonać procedurę **3. Zamknij**.
    
    Ta akcja spowoduje skorygowanie kosztu oryginalnego wiersza sprzedaży, który został wyceniony na -35,00 (5 sztuk \* 7,00), na -30,00 (5 sztuk \* 6,00). Stanie się tak dlatego, że grupa modeli zapasów używa schematu Pierwszy na wejściu — pierwszy na wyjściu (First in, first out; FIFO), a 6,00 za sztukę jest kosztem FIFO z pierwszego zamówienia zakupu. Ponadto działanie spowoduje korektę kosztu w wierszu sprzedaży zwrotu w celu dopasowania kosztu za sztukę w oryginalnym wierszu sprzedaży. W efekcie koszt wiersza zwrotu zostanie skorygowany z 35,00 na 30,00.






[!INCLUDE[footer-include](../../includes/footer-banner.md)]