---
title: Utwórz propozycję amortyzacji
description: W tej procedurze opisano sposób działania propozycji amortyzacji partii i wyjaśniono, jak proponować amortyzację dla środków trwałych.
author: abruer
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransAsset
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d11554ee5f26ef5a85e799194d2f75757a31c254
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2019
ms.locfileid: "1549542"
---
# <a name="create-depreciation-proposal"></a>Utwórz propozycję amortyzacji

[!include [task guide banner](../../includes/task-guide-banner.md)]

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

