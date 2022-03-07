---
title: Tworzenie zamówienia sprzedaży dla konfigurowalnego produktu
description: Ta procedura pokazuje sposób zastosowania szablonu konfiguracji do produktu w zamówieniu sprzedaży.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, SalesOrderProcessingWorkspace, SalesCreateOrder, SalesTable, PCRuntimeConfigurator, PCTemplateConfigurationSelection
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 81e573593fbbb0bf87e53c5cbd985b38a8db89ac
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5841606"
---
# <a name="create-a-sales-order-for-a-configurable-product"></a>Tworzenie zamówienia sprzedaży dla konfigurowalnego produktu

[!include [banner](../../includes/banner.md)]

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



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]