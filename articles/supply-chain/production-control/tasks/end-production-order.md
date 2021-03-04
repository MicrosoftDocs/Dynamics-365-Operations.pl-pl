---
title: Kończenie zlecenia produkcyjnego
description: W tej procedurze pokazano sposób kończenia zlecenia produkcyjnego.
author: johanhoffmann
manager: tfehr
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: fade659c320e0ea1059644324859c9a3cb273c96
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4434922"
---
# <a name="end-a-production-order"></a>Kończenie zlecenia produkcyjnego

[!include [banner](../../includes/banner.md)]

W tej procedurze pokazano sposób kończenia zlecenia produkcyjnego. Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF. Jest to ostatnia z siedmiu procedur, które wyjaśniają cykl życia zlecenia produkcyjnego.


## <a name="end-a-production-order"></a>Kończenie zlecenia produkcyjnego
1. Wybierz kolejno opcje Kontrola produkcji > Zlecenia produkcyjne > Wszystkie zlecenia produkcyjne.
    * Zaznacz zlecenie produkcyjne o stanie Zgłoszone jako gotowe.  
2. W okienku akcji kliknij opcję Zlecenie produkcyjne.
3. Kliknij opcję Koniec.
    * Na tej stronie możesz potwierdzić, że chcesz zakończyć zlecenie produkcyjne.  
4. Kliknij kartę Ogólne.
5. W polu Data wprowadź datę.
6. W polu Metoda odpadków wybierz opcję „Alokacja”.
    * Po wybraniu metody alokacji koszty z materiałów uznanych za odpadki są dodawane do wyrobów gotowych.  
7. Kliknij przycisk OK.

## <a name="validate-calculation-results"></a>Sprawdzanie poprawności wyników obliczeń
1. W okienku akcji kliknij pozycję Zarządzanie kosztami.
2. Kliknij przycisk Wyświetl porównanie kosztów.
    * Po zakończeniu zlecenia produkcyjnego można porównywać szacowany koszt własny ze zrealizowanym kosztem własnym w celu uzyskania obrazu odchyleń względem kosztów produkcji.  


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]