--- 
title: "Tworzenie zamówienia sprzedaży dla konfigurowalnego produktu"
description: "Ta procedura pokazuje sposób zastosowania szablonu konfiguracji do produktu w zamówieniu sprzedaży."
author: BibiSp
manager: AnnBe
ms.date: 10/12/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bibis
ms.search.scope: Operations
ms.search.region: Global
ms.author: bibis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 6546d504a2fda255cb5183408dfe84a3074543ab
ms.contentlocale: pl-pl
ms.lasthandoff: 07/27/2017

---
# <a name="create-a-sales-order-for-a-configurable-product"></a>Tworzenie zamówienia sprzedaży dla konfigurowalnego produktu

[!include[task guide banner](../../includes/task-guide-banner.md)]

Ta procedura pokazuje sposób zastosowania szablonu konfiguracji do produktu w zamówieniu sprzedaży. W przykładzie użyto modelu głośnika D0006 zawartego w danych firmy demonstracyjnej USMF. Zazwyczaj z tej procedury korzysta osoba przetwarzająca zamówienia sprzedaży.


## <a name="create-a-sales-order"></a>Utwórz zamówienie sprzedaży
1. Kliknij opcję Przetwarzanie zamówienia sprzedaży i dotyczące go zapytania.
2. Kliknij przycisk Nowy.
3. Kliknij opcję zamówienie sprzedaży.
4. W polu Konto odbiorcy zaznacz wartość US-001. 
5. Kliknij przycisk OK.
6. W polu Numer pozycji wybierz wartość D0006.
    * Dla tego zadania należy wybrać konfigurowalny produkt.  
7. Kliknij opcję Produkt i dostawa.
8. Kliknij opcję Konfiguruj wiersz.
    * Należy zauważyć, że cena zmieniła się na podstawie wybranej konfiguracji, a pole Uwzględnij kabel jest teraz ustawiony na wartość Prawda.  
    * Zwróć uwagę na domyślną cenę i ustawienia wybrane dla kabla.  
9. Kliknij przycisk Szablon ładunku.
    * W tym przykładzie pokazano, jak można zastosować szablon w celu wybrania wstępnie zdefiniowanej konfiguracji. Jeśli używasz tej procedury jako przewodnika po zadaniu i chcesz widzieć inne dostępne wartości atrybutów, kliknij przycisk Odblokuj.  
10. Kliknij przycisk OK.
11. Kliknij przycisk OK.
12. Rozwiń sekcję Szczegóły wiersza.
13. Kliknij kartę Produkt.
    * Konfiguracja towaru jest teraz wyświetlana w obszarze wymiarów produktu.  
14. Zamknij stronę.

## <a name="select-the-product-configuration"></a>Wybór konfiguracji produktu


