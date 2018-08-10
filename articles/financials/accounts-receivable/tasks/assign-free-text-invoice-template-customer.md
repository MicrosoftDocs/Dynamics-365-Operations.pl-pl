--- 
title: "Przypisywanie szablonu faktury niezależnej do odbiorcy"
description: "To zadanie przedstawia sposób przypisywania szablonu faktury niezależnej do odbiorcy."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 3bcb59c6edd04877dc2a052002be513205ae840a
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---
# <a name="assign-a-free-text-invoice-template-to-a-customer"></a>Przypisywanie szablonu faktury niezależnej do odbiorcy

[!include [task guide banner](../../includes/task-guide-banner.md)]

To zadanie przedstawia sposób przypisywania szablonu faktury niezależnej do odbiorcy. To zadanie wykorzystuje firmę demonstracyjną USMF i jest przeznaczone dla użytkownika, który odpowiada za zarządzanie i przetwarzanie faktur dla odbiorców.

1. Wybierz kolejno opcje Rozrachunki z odbiorcami > Odbiorcy > Wszyscy odbiorcy.
2. Na liście znajdź i zaznacz odpowiedni rekord.
3. W okienku akcji kliknij pozycję Faktura.
4. Kliknij opcję Faktury cykliczne.
    * Ta strona służy do przypisania szablonów faktur niezależnych do odbiorców oraz określania, jak często faktury będą wysyłane do odbiorców.  
5. Kliknij przycisk Nowy, aby przypisać nowy szablon do odbiorcy.
6. Zaznacz szablon faktury niezależnej, który chcesz przypisać odbiorcy.
7. Na liście znajdź i zaznacz odpowiedni rekord.
8. Na liście kliknij łącze w wybranym wierszu.
9. Wprowadź datę, kiedy zostanie wygenerowana pierwsza faktura.
    * Wprowadź datę zakończenia cyklu.  
    * Wybierz jedną z następujących opcje: Brak daty zakończenia — Faktury będą generowane bezterminowo do czasu usunięcia szablonu z konta odbiorcy.  Data zakończenia fakturowania — Zaznacz tę opcję i wprowadź ostatni dzień, w którym fakturę można wygenerować.  
    * Maksymalna kwota skumulowana, po której generowanie faktur się zatrzyma.  
    * Wprowadź maksymalną kwotę skumulowaną, jaką można osiągnąć za pomocą wybranego szablonu. Na przykład wprowadzenie wartości 1 000,00 i generowanie faktur miesięcznych dla każdej kwoty 100,00 spowoduje, że faktury przestaną być generowane po wygenerowaniu dziesiątej faktury.  
    * Umożliwia generowanie faktur cyklicznych przy użyciu domyślnych wartości z szablonu faktury niezależnej lub konta odbiorcy.  
    * Umożliwia określenie, czy ma być używany szablon faktury niezależnej czy konto odbiorcy do określania wartości domyślnych języka, profilu księgowania, grupy podatków, grupy podatków towaru, kodu listy, kraju/regionu dostawy, waluty, warunków płatności, metody płatności, specyfikacji płatności, harmonogramu płatności, rabatu gotówkowego, wymiarów finansowych oraz przekazu GIRO podczas tworzenia faktur.  
10. Wybierz wzorzec cyklu.
    * Dziennie — Wybierz tę opcję i podaj liczbę dni w polu Na. Na przykład, jeśli zostanie wprowadzona wartość 15, co 15 dni będzie generowana faktura dla tego odbiorcy.  Tygodniowo — Wybierz tę opcję i podaj liczbę tygodni w polu Na. Na przykład, jeśli zostanie wprowadzona wartość 2, co 2 tygodnie będzie generowana faktura dla tego odbiorcy.  Miesięcznie — Wybierz tę opcję i podaj liczbę miesięcy w polu Na. Na przykład, jeśli zostanie wprowadzona wartość 6, co 6 miesięcy będzie generowana faktura dla tego odbiorcy.  Rocznie — Wybierz tę opcję i podaj liczbę lat w polu Na. Na przykład, jeśli zostanie wprowadzona wartość 2, co 2 lata będzie generowana faktura dla tego odbiorcy.  
11. W polu Na wprowadź liczbę.


