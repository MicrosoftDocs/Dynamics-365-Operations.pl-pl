---
title: Obliczanie BOM przy użyciu struktury wielopoziomowej (luty 2016)
description: W tej procedurze pokazano, jak obliczyć koszt wyrobu gotowego przy użyciu wielopoziomowego rozłożenia opartego na arkuszu wyceny.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResProductDetailsExtended, InventItemPrice, BOMCalcDialog, BOMCalcTrans
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 859f7b7c828dcdad1aa836044d2cc26847630f1e
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5821424"
---
# <a name="calculate-a-bom-by-using-a-multilevel-structure-february-2016"></a>Obliczanie BOM przy użyciu struktury wielopoziomowej (luty 2016)

[!include [banner](../../includes/banner.md)]

W tej procedurze pokazano, jak obliczyć koszt wyrobu gotowego przy użyciu wielopoziomowego rozłożenia opartego na arkuszu wyceny. Jest to siódme zadanie w serii zadań obliczania BOM. Dane wykorzystane do stworzenia tego zadania pochodzą z firmy demonstracyjnej USMF.

1. Przejdź do Zarządzanie informacjami o produktach > Produkty > Zwolnione produkty.
2. Na liście znajdź i zaznacz odpowiedni rekord.
    * Wybierz produkt BOM_1.  
3. W okienku akcji kliknij pozycję Zarządzanie kosztami.
4. Kliknij opcję Cena pozycji.
5. Kliknij opcję Oblicz koszt pozycji.
    * Może być konieczne kliknięcie przycisku wielokropka (...), aby wyświetlić tę opcję w górnym menu.  
6. W polu Wersja wyceny wprowadź lub wybierz wartość.
    * Wybierz wersję wyceny 20, ponieważ ma ona typ Koszt planowany, a w ustawieniu Tryb rozłożenia wartość Wiele poziomów.   Tryb rozłożenia Wiele poziomów jest przeznaczony dla planowanych kosztów i symulacji. Nie jest używany do kosztu standardowego.  
7. Kliknij przycisk OK.
8. Kliknij opcję Wyświetl szczegóły obliczeń.
    * Może być konieczne kliknięcie przycisku wielokropka (...), aby wyświetlić tę opcję w górnym menu.  W tym przypadku zauważ, jak koszt towaru BOM_2 został obliczony z uwzględnieniem kosztów surowca, przetwarzania i ogólnych na łączną kwotę 29,40 zamiast według kosztu standardowego 10, który był włączony w pierwszym przewodniku po zadaniu w tej serii.  
9. Kliknij kartę Arkusz wyceny.
    * Przejdźmy do karty Arkusz wyceny. Sumy dla każdej grupy kosztów są różne w porównaniu do obliczenia przeprowadzonego w poprzednim przewodniku po zadaniu.  
10. W polu Poziom wybierz wartość „Wiele”.
    * Po wybraniu opcji wielu poziomów koszty są klasyfikowane według składu BOM_2, gdzie wartość 10 jest ustalana na podstawie grupy kosztów M1 (ITEM_C), a wartość 15,60 jest ustalana na podstawie produkcji, w której grupą kosztów jest L2. Koszty pośrednie również się różnią.  
11. Zamknij stronę.
12. Zamknij stronę.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]