---
title: Zatwierdzanie dostawców określonych produktów
description: W tej procedurze pokazano sposób zatwierdzania dostawców dla określonych produktów.
author: RichardLuan
manager: tfehr
ms.date: 07/22/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductDetailsExtended, PdsApprovedVendorList, VendTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d08791caba34908903ce330df0f91e44fbdfcaea
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5237282"
---
# <a name="approve-vendors-for-specific-products"></a>Zatwierdzanie dostawców określonych produktów

[!include [banner](../../includes/banner.md)]

W tej procedurze pokazano sposób zatwierdzania dostawców dla określonych produktów. Pozwala to na kontrolowanie, którzy dostawcy mogą być używani podczas dodawania produktu do zamówienia zakupu. Można wykonać tę procedurę przy użyciu danych firmy demonstracyjnej USMF lub własnych danych. To zadanie zazwyczaj wykonuje menedżer ds. zakupów.

1. W okienku nawigacji przejdź do opcji **Moduły > Zarządzanie informacjami o produktach > Produkty > Wydane produkty**.
2. Na liście znajdź i zaznacz odpowiedni rekord.
3. Na liście kliknij łącze w wybranym wierszu.
4. Rozwiń skróconą kartę **Zakup**. Jeśli w polu **Dostawca** jest wyświetlany główny dostawca, należy dodać tego dostawcy jako zatwierdzonego dostawcę w poniższych krokach. Zanotuj numer dostawcy, jeśli jest wyświetlany.  
5. W okienku akcji kliknij pozycję **Zakup.**
6. Kliknij przycisk **Ustawienia**.
7. Kliknij przycisk **Dodaj**.
8. W polu Dostawca wprowadź lub wybierz wartość. Wybierz zatwierdzonego dostawcę. Co najmniej jeden wiersz musi określać głównego dostawcę, jeśli taki dostawca istniał w rekordzie produktu. Jeśli wcześniej spisano numer dostawcy, zaznacz go w tym miejscu.  
9. W polu **Data wygaśnięcia** wprowadź datę. Wybierz datę przypadającą za kilka miesięcy.  
10. Kliknij przycisk **Dodaj**.
11. W polu **Dostawca** wprowadź lub wybierz wartość.
12. W polu **Data wygaśnięcia** wprowadź datę. Wybierz datę, która różni się od poprzedniej daty ważności.  
13. Zamknij stronę.
14. W okienku akcji kliknij pozycję **Zatwierdzeni dostawcy**.
15. W polu **Data wygaśnięcia** wprowadź datę. Ta data ta pełni rolę filtra pozwalającego zobaczyć zatwierdzonych dostawców ważnych do określonego dnia.  
16. Zamknij stronę.
17. W okienku akcji kliknij pozycję **Okres obowiązywania**.
18. W polu **Pokaż dostawców wygasających** w wprowadź datę. Można używać tej strony do identyfikowania dostawców, gdy stan zatwierdzenia wygasa po określonej dacie.  
19. Zamknij stronę.
20. Kliknij przycisk **Edytuj**.
21. W polu **Metoda sprawdzania zatwierdzonych dostawców** zaznacz opcję. To pole umożliwia wybór zasad mówiących o tym, co ma się stać, jeśli produkt zostanie dodany do wiersza zamówienia zakupu, gdy dostawca nie jest zatwierdzonym dostawcą.  
22. Kliknij przycisk **Zapisz**.
23. Zamknij stronę.
24. Zamknij stronę.
25. W okienku nawigacji wybierz kolejno **Moduły > Zaopatrzenie i sourcing > Dostawcy > Relacje dostawca/pozycja > Lista zatwierdzonych dostawców wg pozycji**. Ta strona zawiera przegląd wszystkich produktów i zatwierdzonych dostawców.  
26. Zamknij stronę.
27. W okienku nawigacji przejdź do **Moduły > Zaopatrzenie i sourcing > Dostawcy > Wszyscy dostawcy.** Można także rozpocząć od dostawcy, a następnie przejść do wykazu produktów zatwierdzonych dla tego konta dostawcy.  
28. Na liście znajdź i zaznacz odpowiedni rekord.
29. W okienku akcji kliknij pozycję **Zaopatrzenie**.
30. Kliknij opcję **Lista zatwierdzonych dostawców wg dostawców**.
31. Zamknij stronę.
32. Zamknij stronę.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]