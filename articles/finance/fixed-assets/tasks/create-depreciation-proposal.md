---
title: Tworzenie propozycji amortyzacji
description: W tym temacie opisano sposób działania propozycji amortyzacji partii i wyjaśniono, jak proponować amortyzację dla środków trwałych.
author: abruer
manager: AnnBe
ms.date: 08/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransAsset
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b3d62e982d26afbec7ac04dd80592a73f4a3286f
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4968911"
---
# <a name="create-a-depreciation-proposal"></a>Tworzenie propozycji amortyzacji

[!include [banner](../../includes/banner.md)]

W tym temacie opisano sposób działania propozycji amortyzacji partii i wyjaśniono, jak proponować amortyzację dla środków trwałych. Zadanie używa firmy demonstracyjnej USMF i roli Księgowy.


## <a name="create-a-depreciation-proposal"></a>Tworzenie propozycji amortyzacji
1. W okienku nawigacji przejdź do **Moduły > Środki trwałe > Wpisy w arkuszu > Utwórz propozycję amortyzacji**.
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