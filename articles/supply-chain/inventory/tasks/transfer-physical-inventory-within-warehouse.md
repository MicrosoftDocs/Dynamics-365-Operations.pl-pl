---
title: "Przenoszenie zapasów fizycznych w magazynie"
description: "Ta procedura poprowadzi Cię przez proces tworzenia i księgowania arkusza przeniesienia zapasów w celu zarejestrowania przesunięcia towaru z jednej lokalizacji w magazynie do innej."
author: MarkusFogelberg
manager: AnnBe
ms.date: 03/02/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mafoge
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: bfba69731a4897906d08ff9fb9ce69e79121efeb
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---
# <a name="transfer-physical-inventory-within-the-warehouse"></a>Przenoszenie zapasów fizycznych w magazynie

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ta procedura poprowadzi Cię przez proces tworzenia i księgowania arkusza przeniesienia zapasów w celu zarejestrowania przesunięcia towaru z jednej lokalizacji w magazynie do innej. Przed rozpoczęciem tego zadania trzeba mieć skonfigurowany arkusz zapasów dla przeniesień zapasów. Procedurę można wykonać przy użyciu firmy demonstracyjnej USMF z przykładowymi wartościami, które są wyświetlane, lub za pomocą własnych danych, jeśli masz skonfigurowane produkty i lokalizacje. Te zadania zazwyczaj wykonuje pracownik magazynu.


## <a name="create-an-inventory-transfer-journal"></a>Tworzenie arkusza przeniesienia zapasów
1. Przejdź do okna Przeniesienie.
2. Kliknij przycisk Nowy.
3. W polu Nazwa wprowadź lub wybierz wartość.
4. Kliknij przycisk OK.
    * Istnieje opcja umożliwiająca określenie wymiarów „Z” i „Do” dla każdego wiersza arkusza. Są one niezbędne dla tego typu arkusza. Towary można przenosić do lokalizacji za pomocą różnych reguł. W tym przykładzie przeniesiemy towar w ramach tego samego magazynu z lokalizacji kontrolowanej przez numer identyfikacyjny do lokalizacji, która nie jest kontrolowana przez numer identyfikacyjny.   

## <a name="create-journal-lines"></a>Tworzenie wierszy arkusza
1. Kliknij przycisk Nowy.
2. W polu Numer towaru wprowadź lub wybierz wartość.
    * Jeśli używasz firmy USMF, możesz wybrać opcję „A0001”.  
3. W polu Z oddziału wprowadź lub wybierz wartość.
    * Jeśli używasz firmy USMF, możesz wybrać opcję „2”.  
4. W polu Do oddziału wprowadź lub wybierz wartość.
    * Jeśli używasz firmy USMF, możesz wybrać opcję „2”.  
5. W polu Z magazynu wprowadź lub wybierz wartość.
    * Jeśli używasz firmy USMF, możesz wybrać opcję „24”.  
6. W polu Do magazynu wprowadź lub wybierz wartość.
    * Jeśli używasz firmy USMF, możesz wybrać opcję „24”.  
7. W polu Z lokalizacji wprowadź lub wybierz wartość.
    * Jeśli używasz firmy USMF, możesz wybrać opcję „FL-001”.  
8. W polu Do lokalizacji wprowadź lub wybierz wartość.
    * Jeśli używasz firmy USMF, możesz wybrać opcję „BULK-001”.  
9. Wprowadź liczbę w polu Ilość.
10. Kliknij kartę Wymiary magazynowe.
11. W polu Numer identyfikacyjny wprowadź lub wybierz wartość.
    * Jeśli używasz firmy USMF, możesz wybrać opcję „24”.  
12. Kliknij przycisk Zapisz.

## <a name="post-the-inventory-transfer-journal"></a>Księgowanie arkusza przeniesienia zapasów
1. Kliknij przycisk Księguj.
2. Kliknij przycisk OK.

## <a name="view-inventory-transactions"></a>Wyświetlanie transakcji magazynowych
1. Kliknij opcję Zapasy.
2. Kliknij opcję Transakcje.
    * W tym miejscu widać transakcje, które zostały utworzone podczas księgowania arkusza.  

