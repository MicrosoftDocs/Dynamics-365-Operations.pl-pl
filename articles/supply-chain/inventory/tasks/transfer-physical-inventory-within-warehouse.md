---
title: Przenoszenie zapasów fizycznych w magazynie
description: Ta procedura poprowadzi Cię przez proces tworzenia i księgowania arkusza przeniesienia zapasów w celu zarejestrowania przesunięcia towaru z jednej lokalizacji w magazynie do innej.
author: MarkusFogelberg
manager: tfehr
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventJournalTransfer, InventJournalCreate, InventItemIdLookupSimple, InventLocationIdLookup, WMSLocationIdLookup, InventTrans
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mafoge
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c00b6d18b036482cd96e2287119ddb7fd80bfa2d
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "5011454"
---
# <a name="transfer-physical-inventory-within-the-warehouse"></a>Przenoszenie zapasów fizycznych w magazynie

[!include [banner](../../includes/banner.md)]

Ta procedura poprowadzi Cię przez proces tworzenia i księgowania arkusza przeniesienia zapasów w celu zarejestrowania przesunięcia towaru z jednej lokalizacji w magazynie do innej. Przed rozpoczęciem tego zadania trzeba mieć skonfigurowany arkusz zapasów dla przeniesień zapasów. Procedurę można wykonać przy użyciu firmy demonstracyjnej USMF z przykładowymi wartościami, które są wyświetlane, lub za pomocą własnych danych, jeśli masz skonfigurowane produkty i lokalizacje. Te zadania zazwyczaj wykonuje pracownik magazynu.


## <a name="create-an-inventory-transfer-journal"></a>Tworzenie arkusza przeniesienia zapasów
1. W **okienku nawigacji** przejdź do **Zarządzanie zapasami > Wpisy w arkuszu > Pozycje > Transfer**.
2. Kliknij przycisk **Nowy**.
3. W polu **Nazwa** wprowadź lub wybierz wartość.
4. Kliknij przycisk **OK**. Istnieje opcja umożliwiająca określenie wymiarów „Z” i „Do” dla każdego wiersza arkusza. Są one niezbędne dla tego typu arkusza. Towary można przenosić do lokalizacji za pomocą różnych reguł. W tym przykładzie przeniesiemy towar w ramach tego samego magazynu z lokalizacji kontrolowanej przez numer identyfikacyjny do lokalizacji, która nie jest kontrolowana przez numer identyfikacyjny.   

## <a name="create-journal-lines"></a>Utwórz wiersze arkusza
1. Na **Wiersze arkusza skróconej karcie**, kliknij przycisk **Nowy**.
2. W polu **Kod towaru** wpisz lub wprowadź wartość. Jeśli używasz firmy USMF, możesz wybrać opcję „A0001”.  
3. W polu **Z oddziału** wprowadź lub wybierz wartość. Jeśli używasz firmy USMF, możesz wybrać opcję „2”.  
4. W polu **Do oddziału** wprowadź lub wybierz wartość. Jeśli używasz firmy USMF, możesz wybrać opcję „2”.  
5. W polu **Z magazynu** wprowadź lub wybierz wartość. Jeśli używasz firmy USMF, możesz wybrać opcję „24”.  
6. W polu **Do magazynu** wprowadź lub wybierz wartość. Jeśli używasz firmy USMF, możesz wybrać opcję „24”.  
7. W polu **Z lokalizacji** wprowadź lub wybierz wartość. Jeśli używasz firmy USMF, możesz wybrać opcję „FL-001”.  
8. W polu **Do lokalizacji** wprowadź lub wybierz wartość. Jeśli używasz firmy USMF, możesz wybrać opcję „BULK-001”.  
9. W polu **Ilość** wpisz liczbę.
10. W skróconej karcie **Szczegóły wiersza** kliknij kartę **Wymiary magazynowe**.
11. W **Od wymiarów magazynowych** w polu **Numer identyfikacyjny** wprowadź lub wybierz wartość. Jeśli używasz firmy USMF, możesz wybrać opcję „24”.  
12. Kliknij przycisk **Zapisz**.

## <a name="post-the-inventory-transfer-journal"></a>Księgowanie arkusza przeniesienia zapasów
1. W **okienku akcji** kliknij pozycję **Księguj**.
2. Kliknij przycisk **OK**.

## <a name="view-inventory-transactions"></a>Wyświetlanie transakcji magazynowych
1. Kliknij przycisk **Zapasy**.
2. Kliknij opcję **Transakcje**. W tym miejscu widać transakcje, które zostały utworzone podczas księgowania arkusza.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]