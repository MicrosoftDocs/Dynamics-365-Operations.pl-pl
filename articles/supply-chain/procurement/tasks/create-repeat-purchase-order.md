---
title: Tworzenie zamówienia powtórnego zakupu
description: W tym artykule pokazano, jak utworzyć powtarzalne zamówienie zakupu poprzez skopiowanie wierszy z wcześniejszego dokumentu zamówienia zakupu do nowego lub istniejącego zamówienia zakupu.
author: GalynaFedorova
ms.date: 09/30/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: PurchTable, PurchTablePart, PurchCreateOrder, PurchCopying
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: gfedorova
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 335461d60fa0bc92e9711806c6e42643a3f75d02
ms.sourcegitcommit: 073604c07116e0a87f78ab2c76cb89ae83ebba3c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/30/2022
ms.locfileid: "9608119"
---
# <a name="create-a-repeat-purchase-order"></a>Tworzenie zamówienia powtórnego zakupu

[!include [banner](../../includes/banner.md)]

W tym artykule pokazano, jak utworzyć powtarzalne zamówienie zakupu poprzez skopiowanie wierszy z wcześniejszego dokumentu zamówienia zakupu do nowego lub istniejącego zamówienia zakupu. Istnieją dwie metody tworzenia powtarzalnych zamówień. Można użyć akcji dostępnych na poziomie dokumentu w okienku akcji albo akcji dostępnych na poziomie szczegółów wiersza. Akcje na poziomie dokumentu są przeznaczone do tworzenia nowego zamówienia zakupu przez dodanie wierszy i informacji nagłówka z innego zamówienia, podczas gdy akcje na poziomie szczegółów wiersza służą głównie do dodawania wierszy do istniejącego zamówienia. Przykład zawarty w tym przewodniku można wykonać na danych firmy demonstracyjnej USMF. To zadanie zazwyczaj wykonuje pracownik działu zakupów.

## <a name="create-a-new-repeat-purchase-order"></a>Tworzenie nowego powtarzalnego zamówienia zakupu

1. W okienku nawigacji wybierz kolejno **Moduły \> Zaopatrzenie i sourcing \> Zamówienia zakupu \> Wszystkie zamówienia zakupu**. Najpierw wypróbujemy opcję skopiowania informacji do nowego zamówienia.  
1. Wybierz pozycję **Nowy**.
1. W polu **Konto dostawcy** wpisz wartość `US-101`.
1. Kliknij przycisk **OK**.
1. W okienku akcji otwórz kartę **Zamówienie zakupu w grupie** **Kopiuj** i wybierz **Ze wszystkich**. Zostanie otwarte okno dialogowe **Kopiuj z innych dokumentów**. W tym miejscu można skopiować z istniejących zamówień do własnego zamówienia. Istnieją różne opcje kopiowania wierszy i różne rodzaje dokumentów, z których można kopiować. Najpierw przyjrzymy się opcjom kopiowania wierszy.
1. Rozwiń skróconą kartę **Parametry**.

    - Pole **Wskaźnik ilości** jest przydatne, jeśli chcesz użyć ilości innej niż ilość w zamówieniu, z którego kopiujesz. Na przykład jeśli chcesz zamówić dwukrotność ilości figurującej w wierszach, z których kopiujesz, wpisz w tym polu wartość „2”. System doda wiersze, których ilość została podwojona względem pierwotnej.  
    - Pole **Zmień znak** umożliwia również zmianę zamówionej ilości poprzez zmianę znaku ilości w dodawanych wierszach zamówienia. Może to być przydatne, jeśli trzeba wycofać transakcję. Można wtedy utworzyć wiersze zamówienia neutralizujące transakcję. Ta opcja jest automatycznie zaznaczona po otwarciu strony za pomocą akcji **Tworzenie faktury korygującej**.  
    - Opcja **Kopiuj opłaty** umożliwia skopiowanie opłat do nowego zamówienia z dokumentu, z którego kopiujesz wiersze zamówienia.  
    - Opcja **Oblicz ponownie ceny** powoduje użycie bieżących cen i rabatów zamiast kopiowania ich z dokumentu, z którego kopiujesz pozostałe informacje.  
    - Opcja **Kopiuj dokładnie** tworzy dokładne kopie wartości w kilku polach w nagłówku i wierszach dokumentu zamówienia. Jeśli ta opcja nie jest zaznaczone, używane będą wartości domyślne dla wielu pól odnoszących się do dostawcy i produktów, tak jakby nowe zamówienie było tworzone ręcznie. Na przykład jeśli ustawisz **Kopiuj dokładnie** na *Tak* i skopiujesz zamówienie, które nadpisuje domyślne konto faktury dla dostawcy, to samo konto faktury będzie skopiowane do nowego zamówienia. Jeśli ustawisz **Kopiuj dokładnie** na *Nie*, zamiast tego domyślne konto faktury dla dostawcy zostałoby użyte w nowym zamówieniu. Wartości następujących pól są kopiowane, jeśli opcja **Kopiuj dokładnie** jest ustawiona na *Tak*:
        - Język
        - Warunki płatności
        - Metoda płatności
        - Specyfikacja płatności
        - Grupa sekwencji numerów
        - Rabat gotówkowy
        - Procent rabatu
        - Waluta
        - Warunki dostawy
        - Metoda dostawy
        - Wymiar
        - Grupa podatków
        - Zastąp podatek
        - Ceny zawierają podatek
        - Transport
        - Port
        - Procedura statystyk
        - Identyfikator szablonu
        - Nazwa dostawy
        - Adres pocztowy
        - Odwołanie
        - Identyfikator tabeli odwołań
    - Opcja **Usuń wiersze zakupu** powoduje usunięcie wszystkich wierszy zamówienia zakupu już istniejących w zamówieniu zakupu, do którego kopiujesz, a następnie zastosowanie nowych wierszy. Tej opcji należy używać ostrożnie, ponieważ usuwa wszystkie istniejące wiersze bez dalszego ostrzeżenia.  
    - Jeśli używasz opcji **Kopiuj nagłówek zamówienia**, nie trzeba ręcznie tworzyć informacji nagłówka w nowym zamówieniu. Ta opcja spowoduje użycie domyślnych wartości w polach skojarzonych z dostawcą. Jeśli dokument, z którego kopiujesz, zawiera wartości inne niż domyślne, które chcesz skopiować, użyj dodatkowo opcji **Kopiuj dokładnie**.
    - Istnieją różne źródła dokumentów, z których można kopiować, i każde z nich ma osobną sekcję na tej stronie. Na przykład sekcja **Zamówienia zakupu** umożliwia kopiowanie z istniejących zamówień zakupu.  

1. W sekcji **Zamówieniaczakupu** wybierz wiersze, które chcesz skopiować do Schowka. Można wybrać dodatkowe wiersze zamówienia zakupu z innych zamówień zakupu i skopiować je do swojego zamówienia. Możesz również dodać wiersze z innych rodzajów dokumentów zakupu. W następnych kilku krokach przyjrzymy się różnym opcjom.  
1. Rozwiń sekcję **Potwierdzenie**. W tym miejscu można wybrać potwierdzenia zamówień zakupu, z których zostanie wykonane kopiowanie. Potwierdzenia zamówień zakupu są identyfikowane przez powiązany identyfikator arkusza zakupów lub identyfikator zamówienia zakupu.  
1. Rozwiń sekcję **Dokumenty przyjęcia produktów**. W tym miejscu można wybrać arkusze dokumentów przyjęcia produktów, z których zostanie wykonane kopiowanie. Arkusze dokumentów przyjęcia produktów są identyfikowane za pomocą załącznika dokumentu przyjęcia produktów lub identyfikatora zamówienia zakupu.
1. Rozwiń sekcję **Faktury**. W tym miejscu można wybrać faktury od dostawców, z których zostanie wykonane kopiowanie. Faktury są identyfikowane za pomocą załącznika faktury lub identyfikatora zamówienia zakupu.
1. Rozwiń sekcję **Wybrane wiersze lub nagłówek do skopiowania**. Ten widok zawiera zestawienie wszystkich dokumentów i wierszy, które zostały wybrane do skopiowania do zamówienia.
1. Kliknij przycisk **OK**. Wybrane wiersze zostały skopiowane do nowego zamówienia zakupu.

## <a name="copy-lines-to-an-existing-purchase-order"></a>Kopiowanie wierszy do istniejącego zamówienia zakupu  

Zamiast kopiować całe zamówienie, częściej tworzy się nowe zamówienie zakupu i wypełnia informacje w nagłówku zamówienia zakupu, a następnie kopiuje poszczególne wiersze z istniejących zamówień.  

1. Wybierz wiersz **Zamówienie zakupu**.
1. Wybierz **Ze wszystkich**. Otwarta strona jest taka sama, jak pokazana wcześniej, ale po otwarciu z widoku wierszy zamówienia są zaznaczone inne opcje. Przyjrzyjmy się parametrom.
1. Rozwiń sekcję **Parametry**.

    - Opcja **Usuń wiersze zakupu** nie jest zaznaczona. Oznacza to, że można skopiować nowe wiersze do zamówienia bez usuwania istniejących wierszy.
    - Opcja **Kopiuj nagłówek zamówienia** również nie jest zaznaczona, ponieważ tylko dodajemy kolejne wiersze do zamówienia.
    - W tym przykładzie skopiujemy wiersze z istniejącego zamówienia zakupu.

1. Wybierz wiersz dla żadanego zamówienia zakupu. Należy zauważyć, że został zaznaczony również pojedynczy wiersz zamówienia znajdujący się w tym zamówienia zakupu.  
1. Kliknij przycisk **OK**. Dodatkowy wiersz zamówienia został dodany do zamówienia zakupu.  

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]