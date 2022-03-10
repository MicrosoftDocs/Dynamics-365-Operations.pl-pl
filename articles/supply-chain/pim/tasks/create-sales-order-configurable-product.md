---
title: Tworzenie zamówienia sprzedaży dla konfigurowalnego produktu
description: Ta procedura pokazuje sposób zastosowania szablonu konfiguracji do produktu w zamówieniu sprzedaży.
author: t-benebo
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, SalesOrderProcessingWorkspace, SalesCreateOrder, SalesTable, PCRuntimeConfigurator, PCTemplateConfigurationSelection
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e42f121d1efa66f85a3dd811606962b907ed177d
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/29/2021
ms.locfileid: "7570592"
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