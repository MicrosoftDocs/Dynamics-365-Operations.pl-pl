---
title: Tworzenie propozycji amortyzacji
description: W tym artykule opisano sposób działania propozycji amortyzacji partii i wyjaśniono, jak proponować amortyzację dla środków trwałych.
author: abruer
ms.date: 08/01/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransAsset
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a1f39a1412c6f96fe0a8261602a88a6a3c3cd6b8
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8858504"
---
# <a name="create-a-depreciation-proposal"></a>Tworzenie propozycji amortyzacji

[!include [banner](../../includes/banner.md)]

W tym artykule opisano sposób działania propozycji amortyzacji partii i wyjaśniono, jak proponować amortyzację dla środków trwałych. Zadanie używa firmy demonstracyjnej USMF i roli Księgowy.


## <a name="create-a-depreciation-proposal"></a>Tworzenie propozycji amortyzacji
1. W okienku nawigacji przejdź do **Środki trwałe > Wpisy w arkuszu > Utwórz propozycję amortyzacji**.
2. W polu **Nazwa arkusza** wybierz opcję z menu rozwijanego.
3. Wprowadź datę w polu **Do dnia**.

    - Wybierz opcję **Podsumowanie amortyzacji**, aby zsumować miesięczne amortyzacje w jednym wierszu arkusza.  
    - Na przykład jeśli wartość pola Do dnia wynosi 31 marca 2015, zostanie wygenerowany następujący opis: „Amortyzacja od 31 stycznia 2015”. Pole **Data** w proponowanych wierszach arkusza zostanie następnie ustawione na wartość 31 marca 2015 r.  
    - Propozycję amortyzacji można filtrować według składników majątku, grup składników majątku lub innych kryteriów przy użyciu opcji **Filtruj**.  
    - W przypadku używania formularza **Tworzenie propozycji nabycia lub amortyzacji środków trwałych** można zaproponować amortyzację partiami. Jest to zalecane dla większych propozycji, które zużywają więcej zasobów systemowych. Jeśli zostanie wybrana opcja przetwarzania wsadowego, możliwe jest wykonywanie innych zadań w tym samym czasie. Gdy proponujesz amortyzację w ten sposób, amortyzacja jest obliczana dla modeli ewidencji środków trwałych.  

4. Wybierz **Utwórz arkusz**.

## <a name="review-depreciation-entries"></a>Przeglądanie zapisów amortyzacji
1. W okienku nawigacji przejdź do **Moduły > Środki trwałe > Wpisy w arkuszu > Arkusz środków trwałych**.
2. Na liście znajdź i zaznacz odpowiedni rekord.
3. Wybierz **Linie**.
4. Wybierz opcję **Zaksięguj**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
