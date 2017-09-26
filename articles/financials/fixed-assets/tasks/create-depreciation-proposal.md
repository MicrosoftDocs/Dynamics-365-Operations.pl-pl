--- 
title: Tworzenie propozycji amortyzacji
description: "W tej procedurze opisano sposób działania propozycji amortyzacji partii i wyjaśniono, jak proponować amortyzację dla środków trwałych."
author: saraschi2
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: ffc358fa7db0ae40fb39d3acdfee7783949f0e1f
ms.contentlocale: pl-pl
ms.lasthandoff: 07/27/2017

---
# <a name="create-a-depreciation-proposal"></a>Tworzenie propozycji amortyzacji

[!include[task guide banner](../../includes/task-guide-banner.md)]

W tej procedurze opisano sposób działania propozycji amortyzacji partii i wyjaśniono, jak proponować amortyzację dla środków trwałych. Zadanie używa firmy demonstracyjnej USMF i roli Księgowy.


## <a name="create-depreciation-proposal"></a>Utwórz propozycję amortyzacji
1. Wybierz kolejno opcje Środki trwałe > Wpisy w arkuszu > Utwórz propozycję amortyzacji.
2. W polu Nazwa arkusza kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
3. Na liście kliknij łącze w wybranym wierszu.
4. Wprowadź datę w polu Do dnia.
    * Wybierz opcję Podsumowanie amortyzacji, aby zsumować miesięczne amortyzacje w jednym wierszu arkusza.  
    * Na przykład jeśli wartość pola Do dnia wynosi 31 marca 2015, zostanie wygenerowany następujący opis: „Amortyzacja od 31 stycznia 2015”. Pole Data w proponowanych wierszach arkusza zostanie następnie ustawione na wartość 31 marca 2015.  
    * Propozycję amortyzacji można filtrować według składników aktywów, grup składników aktywów lub innych kryteriów przy użyciu opcji Filtr.  
    * W przypadku używania formularza Tworzenie propozycji nabycia lub amortyzacji środków trwałych można zaproponować amortyzację partiami. Jest to zalecane dla większych propozycji, które zużywają więcej zasobów systemowych. Jeśli zostanie wybrana opcja przetwarzania wsadowego, możliwe jest wykonywanie innych zadań w tym samym czasie. Gdy proponujesz amortyzację w ten sposób, amortyzacja jest obliczana dla modeli ewidencji środków trwałych.  
5. Kliknij opcję Utwórz arkusz.

## <a name="review-depreciation-entries"></a>Przeglądanie zapisów amortyzacji
1. Wybierz kolejno opcje Środki trwałe > Wpisy w arkuszu > Arkusz środków trwałych.
2. Na liście znajdź i zaznacz odpowiedni rekord.
3. Kliknij przycisk Wiersze.
4. Kliknij przycisk Księguj.


