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
ms.openlocfilehash: 8607de5705354aa58c985fb536f3e1d52acd1f37
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/20/2021
ms.locfileid: "5921296"
---
# <a name="create-a-sales-order-for-a-configurable-product"></a>Tworzenie zamówienia sprzedaży dla konfigurowalnego produktu

[!include [banner](../../includes/banner.md)]

Ta procedura pokazuje sposób zastosowania szablonu konfiguracji do produktu w zamówieniu sprzedaży. W przykładzie użyto modelu głośnika D0006 zawartego w danych firmy demonstracyjnej USMF. Zazwyczaj z tej procedury korzysta osoba przetwarzająca zamówienia sprzedaży.

## <a name="create-a-sales-order"></a>Utwórz zamówienie sprzedaży

1. Przejdź do lokalizacji **Sprzedaż i marketing \> Obszary robocze \> Przetwarzanie zamówienia sprzedaży i zapytania o nie**.
1. Wybierz pozycję **Nowy**.
1. Wybierz opcję **Zamówienie sprzedaży**.
1. W polu **Konto odbiorcy** zaznacz wartość *US-001*. 
1. Kliknij przycisk **OK**.
1. W polu **Numer pozycji** wybierz wartość *D0006*.
    * Dla tego zadania należy wybrać konfigurowalny produkt.  
1. Wybierz opcję **Produkt i dostawa**.
1. Wybierz pozycję **Konfiguruj wiersz**.
    * Należy zauważyć, że cena zmieniła się na podstawie wybranej konfiguracji, a pole **Uwzględnij kabel** jest teraz ustawiony na wartość *Prawda*.  
    * Zwróć uwagę na domyślną cenę i ustawienia wybrane dla kabla.  
1. Wybierz opcję **Szablon ładunku**.
    * W tym przykładzie pokazano, jak można zastosować szablon w celu wybrania wstępnie zdefiniowanej konfiguracji. Jeśli używasz tej procedury jako przewodnika po zadaniu i chcesz widzieć inne dostępne wartości atrybutów, musisz nacisnąć przycisk **Odblokuj**.  
1. Kliknij przycisk **OK**.
1. Kliknij przycisk **OK**.
1. Rozwiń sekcję **Szczegóły wiersza**.
1. Wybierz kartę **Produkt**.
    * Konfiguracja towaru jest teraz wyświetlana w obszarze wymiarów produktu.  
1. Zamknij stronę.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]