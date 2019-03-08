---
title: Tworzenie zamówienia powtórnego zakupu
description: W tej procedurze pokazano, jak utworzyć powtarzalne zamówienie zakupu poprzez skopiowanie wierszy z wcześniejszego dokumentu zamówienia zakupu do nowego lub istniejącego zamówienia zakupu.
author: FrankDahl
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable, PurchCreateOrder, PurchCopying
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: fdahl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 74dcee8a614363cf1f1ebc71e3e39a14c59bb774
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "345888"
---
# <a name="create-a-repeat-purchase-order"></a>Tworzenie zamówienia powtórnego zakupu

[!include [task guide banner](../../includes/task-guide-banner.md)]

W tej procedurze pokazano, jak utworzyć powtarzalne zamówienie zakupu poprzez skopiowanie wierszy z wcześniejszego dokumentu zamówienia zakupu do nowego lub istniejącego zamówienia zakupu. Istnieją dwie metody tworzenia powtarzalnych zamówień. Można użyć akcji dostępnych na poziomie dokumentu w okienku akcji albo akcji dostępnych na poziomie szczegółów wiersza. Akcje na poziomie dokumentu są przeznaczone głównie do tworzenia nowego zamówienia zakupu przez dodanie wierszy i informacji nagłówka z innego zamówienia, podczas gdy akcje na poziomie szczegółów wiersza służą głównie do dodawania wierszy do istniejącego zamówienia. Przykład zawarty w tym przewodniku można wykonać na danych firmy demonstracyjnej USMF. To zadanie zazwyczaj wykonuje pracownik działu zakupów.


## <a name="create-a-new-repeat-purchase-order"></a>Tworzenie nowego powtarzalnego zamówienia zakupu
1. Wybierz kolejno opcje Zaopatrzenie i sourcing > Zamówienia zakupu > Wszystkie zamówienia zakupu.
    * Najpierw wypróbujemy opcję skopiowania informacji do nowego zamówienia.  
2. Kliknij przycisk Nowy.
3. W polu Konto dostawcy wpisz wartość US-101.
4. Kliknij przycisk OK.
5. W okienku akcji kliknij pozycję Zamówienie zakupu.
6. Kliknij opcję Ze wszystkich.
    * To jest strona, na której możesz kopiować dane z istniejących zamówienia do swojego zamówienia. Istnieją różne opcje kopiowania wierszy i różne rodzaje dokumentów, z których można kopiować. Najpierw przyjrzymy się opcjom kopiowania wierszy.   
7. Rozwiń sekcję Parametry.
    * Pole Wskaźnik ilości jest przydatne, jeśli chcesz użyć ilości innej niż ilość w zamówieniu, z którego kopiujesz. Na przykład jeśli chcesz zamówić dwukrotność ilości figurującej w wierszach, z których kopiujesz, wpisz w tym polu wartość „2”. System doda wiersze, których ilość została podwojona względem pierwotnej.  
    * Pole Zmień znak umożliwia również zmianę zamówionej ilości poprzez zmianę znaku ilości w dodawanych wierszach zamówienia. Może to być przydatne, jeśli trzeba wycofać transakcję. Można wtedy utworzyć wiersze zamówienia neutralizujące transakcję. Ta opcja jest automatycznie zaznaczona po otwarciu strony za pomocą akcji Tworzenie faktury korygującej.  
    * Opcja Kopiuj opłaty umożliwia skopiowanie opłat do nowego zamówienia z dokumentu, z którego kopiujesz wiersze zamówienia.  
    * Opcja Oblicz ponownie ceny powoduje użycie bieżących cen i rabatów zamiast kopiowania ich z dokumentu, z którego kopiujesz pozostałe informacje.  
    * Opcja Kopiuj dokładnie tworzy dokładną kopię wartości we wszystkich polach w nagłówku i wierszach dokumentu zamówienia. Jeśli ta opcja nie jest zaznaczone, używane są wartości domyślne dla wielu pól odnoszących się do dostawcy i produktów, tak jakby nowe zamówienie było tworzone ręcznie. Na przykład jeśli zamówienie, z którego kopiujesz, spowodowało zastąpienie domyślnego konta płatnika dla dostawcy, to samo konto faktury zostałoby skopiowane do Twojego zamówienia. Jeśli nie wybrano opcji Kopiuj dokładnie, w Twoim zamówieniu zostałoby użyte domyślne konto faktury dla dostawcy.  
    * Opcja Usuń wiersze zakupu powoduje usunięcie wszystkich wierszy zamówienia zakupu już istniejących w zamówieniu zakupu, do którego kopiujesz, a następnie zastosowanie nowych wierszy. Tej opcji należy używać ostrożnie, ponieważ usuwa wszystkie istniejące wiersze bez dalszego ostrzeżenia.  
    * Jeśli używasz opcji Kopiuj nagłówek zamówienia, nie trzeba ręcznie tworzyć informacji nagłówka w nowym zamówieniu. Należy zauważyć, że ta opcja spowoduje użycie domyślnych wartości w polach skojarzonych z dostawcą. Jeśli dokument, z którego kopiujesz, zawiera wartości inne niż domyślne, które chcesz skopiować, użyj dodatkowo opcji Kopiuj dokładnie.  
8. Zwiń sekcję Parametry.
    * Istnieją różne źródła dokumentów, z których można kopiować, i każde z nich ma osobną sekcję na tej stronie. Na przykład sekcja Zamówienia zakupu umożliwia kopiowanie z istniejących zamówień zakupu.  
9. Kliknij wiersz zamówienia zakupu o identyfikatorze 00015. 
10. Zaznacz wiersz, klikając jego pole wyboru.
11. Wyczyść pole wyboru wiersza, tak aby nie był on kopiowany do Twojego zamówienia.
    * Wybrano 4 wiersze do skopiowania do zamówienia zakupu. Można wybrać dodatkowe wiersze zamówienia zakupu z innych zamówień zakupu i skopiować je do swojego zamówienia. Możesz również dodać wiersze z innych rodzajów dokumentów zakupu. W następnych kilku krokach przyjrzymy się różnym opcjom.  
12. Zwiń sekcję Zamówienia zakupu.
13. Rozwiń sekcję Potwierdzenie.
    * W tym miejscu można wybrać potwierdzenia zamówień zakupu, z których zostanie wykonane kopiowanie. Potwierdzenia zamówień zakupu są identyfikowane przez powiązany identyfikator arkusza zakupów lub identyfikator zamówienia zakupu.  
14. Zwiń sekcję Potwierdzenie.
15. Rozwiń sekcję Dokumenty przyjęcia produktów.
    * W tym miejscu można wybrać arkusze dokumentów przyjęcia produktów, z których zostanie wykonane kopiowanie. Arkusze dokumentów przyjęcia produktów są identyfikowane za pomocą załącznika dokumentu przyjęcia produktów lub identyfikatora zamówienia zakupu.   
16. Zwiń sekcję Dokumenty przyjęcia produktów.
17. Rozwiń sekcję Faktury.
    * W tym miejscu można wybrać faktury od dostawców, z których zostanie wykonane kopiowanie. Faktury są identyfikowane za pomocą załącznika faktury lub identyfikatora zamówienia zakupu.   
18. Zwiń sekcję Faktury.
19. Rozwiń sekcję Wybrane wiersze lub nagłówek do skopiowania.
    * Ten widok zawiera zestawienie wszystkich dokumentów i wierszy, które zostały wybrane do skopiowania do zamówienia.   
20. Zwiń sekcję Wybrane wiersze lub nagłówek do skopiowania.
21. Kliknij przycisk OK.
    * Wybrane 4 wiersze zostały skopiowane do nowego zamówienia zakupu.   

## <a name="copy-lines-to-an-existing-purchase-order"></a>Kopiowanie wierszy do istniejącego zamówienia zakupu
    * Zamiast kopiować całe zamówienie, częściej tworzy się nowe zamówienie zakupu i wypełnia informacje w nagłówku zamówienia zakupu, a następnie kopiuje poszczególne wiersze z istniejących zamówień.  
1. Kliknij opcję Wiersz zamówienia zakupu.
2. Kliknij opcję Ze wszystkich.
    * Otwarta strona jest taka sama, jak pokazana wcześniej, ale po otwarciu z widoku wierszy zamówienia są zaznaczone inne opcje. Przyjrzyjmy się parametrom.   
3. Rozwiń sekcję Parametry.
    * Opcja Usuń wiersze zakupu nie jest zaznaczona. Oznacza to, że można skopiować nowe wiersze do zamówienia bez usuwania istniejących wierszy.   
    * Opcja Kopiuj nagłówek zamówienia również nie jest zaznaczona, ponieważ tylko dodajemy kolejne wiersze do zamówienia.   
4. Zwiń sekcję Parametry.
    * W tym przykładzie skopiujemy wiersze z istniejącego zamówienia zakupu.   
5. Kliknij wiersz zamówienia zakupu o identyfikatorze 00034. 
6. Zaznacz wiersz, klikając jego pole wyboru.
    * Należy zauważyć, że został zaznaczony również pojedynczy wiersz zamówienia znajdujący się w tym zamówienia zakupu.  
7. Kliknij przycisk OK.
    * Dodatkowy wiersz zamówienia został dodany do zamówienia zakupu.  

